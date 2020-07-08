# NBA-Data-Analysis---ML-Clustering

<h3>Source Dataset: https://www.kaggle.com/justinas/nba-players-data </h3>

## Overview

Project ini bertujuan untuk mengeksplor dataset NBA dan mengkluster pemain-pemain NBA berdasarkan posisinya menggunakan <b>K-Means Clustering</b>. 

## Summary

### Exploratory Data Analysis

Dataset ini diambil dari tahun 1996 sampai 2020, namun seperti yang kita tahu, untuk season 2019-2020 belum selesai. Memang seharusnya sudah selesai, tapi seperti yang Wikipedia katakan:

> The 2019–20 NBA season is the 74th season of the National Basketball Association (NBA). The regular season began on October 22, 2019 and was originally supposed to end on April 15, 2020. However, the season was suspended on March 11, 2020 as a result of the COVID-19 pandemic.[1]

[1] "NBA to suspend season following Wednesday's games". NBA.com. March 11, 2020. Retrieved March 12, 2020. https://www.nba.com/article/2020/03/11/nba-suspend-season-following-wednesdays-games

Pada eksplorasi data, dilakukannya pencarian sepuluh pemain teratas dengan Average Points Per Game (PPG), Assists Per Game (APG), dan Rebounds Per Game (RPG) terbanyak di setiap season. Dimana dari daftar PPG, <b>James Harden</b> di season 2018-19 adalah pemain dengan AVG PPG terbanyak di dataset ini. Sedangkan untuk kategori pemain dengan AVG APG dan RPG terbanyak dapat dilihat di [GitHub](http://github.com). 

Kemudian saya juga mencoba untuk melihat AVG PPG pemain yang menurut saya, salah satu pemain paling konsisten dalam mencetak poin di NBA, Kobe Bryant. Dimana grafiknya dapat dilihat di bawah:

![GitHub Logo](/images/1.png)

Ternyata di season 2005-06 adalah season dimana Kobe punya AVG PPG terbanyak untuk dataset ini. Dan adanya fakta menarik pada season 2005-06, tepatnya tanggal 22 Jan 2006, Kobe mencetak 81 poin! Dan itu menjadi skor terbanyak ke-dua sepanjang sejarah yang pemain dapat lakukan di satu game NBA. Dan banyak fakta-fakta menariknya yang terjadi pada season 2005-2006 di website ini: http://global.nba.com/news/10-years-later-10-facts-about-kobes-2005-06-season/. 

Kemudian saya juga penasaran, dengan distribusi tinggi pemain-pemain NBA. Dimana grafiknya dapat dilihat di bawah:

![GitHub Logo](/images/2.png)

Menarik, melihat ada pemain-pemain NBA yang tingginya di bawah 170 cm. Ini membuat saya penasaran, siapa-siapa saja pemain-pemain NBA yang punya tinggi di bawah 170. Setau saya, Muggsy Bogues dan dia bisa ngedunk! Dan setelah pencarian, ternyata hanya ada tiga orang: <b>Muggsy Bogues, Spud Webb, dan Earl Boykins.</b> Maka bisa kita bayangkan, betapa sulitnya untuk masuk NBA dengan tinggi 170 cm atau kurang dari 170 cm. 

Setelah itu, saya juga penasaran, siapa kira-kira <b>Rookie Of The Year untuk di season 2019-2020.</b> Di perbincangan basket seringkali mengatakan ini antara <b>Zion Wiliamson atau Ja Morant.</b> Sepertinya, saya juga setuju dengan itu, itu masih menjadi perdebatan. Mengingat dari dataset ini juga menunjukkan untuk avg pts (23.6) dan reb (6.8) ada di Zion, sedangkan untuk ast (7.0) ada di Ja Morant. Tapi ini masih bisa saja berubah, mengingat season belum selesai. Dan saya juga membandingkan mereka dengan <b>Luka Doncic</b> sebagai Rookie of The Year di season 2018-2019. Tapi menurut saya, tetap saja, peluang mereka berdua masih terbuka.

#### Correlation Analysis

Dalam analisa korelasi, saya hanya memasukkan fitur-fitur yang menurut saya penting dalam melihat pemain ini akan masuk dalam posisi apa. Seperti fisiknya, atau berapa besar dari AVG PPG nya dan lainnya. Dimana matriks korelasinya dapat dilihat di bawah:

![GitHub Logo](/images/3.png)

Dari matriks korelasi di atas, kita bisa menarik kesimpulan. Bahwa banyak fitur yang saling berkorelasi kuat. Misalnya fitur reb dengan 'dreb_pct' dan 'oreb_pct', yang dimana 'dreb' artinya Defensive Rebound dan 'oreb' artinya Offensive Rebound. Jadi kita tidak perlu memasukkan semua fitur itu ke dalam model kita, cukup satu saja. Dan juga fitur-fitur lainnya, seperti ast_pct dan ast. Maka saya putuskan hanya menggunakan fitur-fitur pentingnya. Yang korelasinya dan pairplotnya dapat dilihat di bawah:

![GitHub Logo](/images/4.png)

![GitHub Logo](/images/5.png)

Masuk akal, melihat korelasi minus antara fitur tinggi dan berat pemain dengan assist. Memang tidak menutup kemungkinan adanya pemain besar dengan court vision  dan pass yang baik, misalnya Nikola Jokić.

## Clustering 

Awalnya saya melakukan dekomposisi dengan menggunakan PCA, mengkompresnya menjadi dua dimensi. Dan informasi yang tersisa cukup lumayan, sekitar 85%. Dan juga, pada project ini, saya tidak perlu menggunakan <b>Elbow Methods</b> atau melihat <b>Silhouette Score</b> dalam menentukan <b>K</b>. Mengingat di project ini, saya ingin cluster pemain-pemain berdasarkan posisinya. Dimana dalam basket terdapat 5 posisi, yaitu <b>PG (Point Guard), SG (Shooting Guard), SF (Small Forward), PF (Power Forward),</b> dan <b>C (Center)</b>.

![GitHub Logo](/images/6.png)

## Conclusion

Setelah mencoba melakukan prediksi-prediksi pada pemain-pemain yang saya ketahui posisinya, misalnya Yao Ming (Center) atau Muggsy Bogues (Point Guard). Saya menyimpulkan bahwa:

* Cluster 0: Posisi Point Guard
* Cluster 1: Posisi Center
* Cluster 2: Posisi Small Forward
* Cluster 3: Posisi Power Forward 
* Cluster 4: Posisi Shooting Guard

> Namun adanya kekurangan dari model di atas, mengingat fitur-fitur pada dataset ini tidak terlalu memumpuni. Mengingat kalau misalnya, kita ingin membedakan posisi Shooting Guard dan Small Forward, fisik dan AVG PTS tidak bisa jadi pegangan. Seharusnya ada fitur yang membedakan mana poin dari garis 3 poin dan mana yang di dalam garis 3 poin. 














