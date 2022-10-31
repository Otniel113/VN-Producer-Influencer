# VN-Producer-Influencer
Mencari most influential Visual Novel Producer dengan 3 metode Centrality (Degree, Betweenness, Eigenvector) berdasarkan data dari VNDB

## Dataset
Data didapat dari [Query VNDB](https://query.vndb.org/) dengan melakukan query SQL:

```sql
SELECT pr.id, pr.pid, pr.relation, p1.name AS "p1_name", p2.name AS "p2_name"
FROM producers_relations pr
JOIN producers p1 ON pr.id=p1.id
JOIN producers p2 ON pr.pid=p2.id;
```

Ukuran dataset adalah 5086 x 5

## Hasil
1. Spesifikasi Graf

| Parameter | Nilai |
| -- | -- |
| Banyak node | 2934 |
| Banyak edge | 2543 |
| Berarah | Tidak |
| Berbobot | Tidak |
| Multiedge | Tidak |
| Loop | Tidak |
| Jenis graf | Simple graph |

2. Gambar Graf

![Graf VN Producer](https://user-images.githubusercontent.com/57952404/198954729-44a2821c-2efc-40d6-8dfa-81dabf4f055f.png)

3. Influential VN Producer

| Top by Degree	| Degree Centrality |	Top by Betweenness |	Betwenness Centrality |	Top by Eigenvector |	Eigenvector Centrality |
| -- | -- | -- | -- | -- | -- |
| VISUAL ARTS |	0.021821 |	VISUAL ARTS |	0.028919 |	VISUAL ARTS |	0.700779 |
| WillPlus |	0.013297 |	Hobibox |	0.026658 |	Visual Art's Motto |	0.111279 |
| Nexton |	0.009206 |	Nexton |	0.021444 |	ZERO |	0.111079 |
| Hobibox |	0.007501 |	IDES |	0.016557 |	PROTOTYPE |	0.101686 |
| Giga |	0.006478 |	F&C Co., Ltd. |	0.016385 |	Softhouse Bonbee Bonbon |	0.100301 |
| Space Project Co., Ltd. |	0.006478 |	STONE HEADS Co., Ltd. |	0.015169 |	Visual Art's MottoSP |	0.100115 |
| CD Bros. |	0.006137 |	Kirara |	0.014513 |	Studio Ring |	0.100091 |
| Interheart Co., Ltd. |	0.005796 |	CRAFTWORK |	0.013393 |	Miyabi |	0.100091 |
| PRODUCTION PENCIL |	0.005114 |	PIL	| 0.013320 |	Bonbee! |	0.098762 |
| MasterUp |	0.005114 |	Yumemiru |	0.013249 |	CRAFTWORK	0.089128 |

## Analisis
Visual Arts mengungguli dengan peringkat 1 pada ketiga metode centrality sehingga dapat dinobatkan sebagai "The Most Influential Visual Novel Producer". Hal ini wajar karena Visual Arts memiliki banyak sekali partner perusahaan dan juga anak perusahaan. Nexton dan Hobibox bisa dinobatkan sebagai peringkat 2 dan 3 secara umum karena masih ada pada top 10 pada dua metode yaitu Degree dan juga Betweenness.
