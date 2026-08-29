# four-color-theorem-experiment
## A simple experiment on simplifying the number of objects and rings
### Project Status: Testing / Almost Done / Paused

Misalkan Teorema $n$-Pewarnaan adalah salah.<br>
Maka, berdasarkan Prinsip Sarang Burung Merpati, akan terdapat setidaknya **satu graf planar** yang merupakan **Peta gagal terkecil ($G$)** yang mungkin memiliki setidaknya $n+1$ warna agar pewarnaan bersifat valid *(proper coloring)*.<br>

Sehingga pada graf $G$ tersebut, dijamin **pasti muncul minimal satu sub-graf terinduksi berupa konfigurasi Rantai Asimetris $T$**, yang didefinisikan sebagai berikut:
1. $T$ terdiri dari sekumpulan simpul bertetangga *(adjacent vertices)* $v_1, \ v_2, \ \dots, \ v_m$. 
2. Setiap simpul $v_i \in T$ memiliki **Derajat Simpul *(Vertex Degree)*** $d(v_i) \in \{3, 4, 5\}$.
3. Untuk semua simpul yang saling terhubung langsung oleh sebuah Sisi *(Edge)* $(v_i, v_j)$ di dalam sub-graf $T$, berlaku syarat ketat: $d(v_i) \neq d(v_j)$. Artinya, tidak ada dua simpul bertetangga yang memiliki derajat sama *(Non-isomorphic adjacent degrees)*, seperti simpul berderajat 3 yang bertetangga dengan simpul berderajat 5.

Misalkan $G$ adalah graf planar maksimal (triangulasi).<br>
Kita definisikan fungsi muatan awal untuk setiap simpul $v$ sebagai $M_0 (v) = 6-d(v)$.<br>
Untuk meengeliminasi hambatan struktural simetris (kondisi dimana simpul berderajat sama saling bertetangga langsung) sekaligus mengunci sifat asimetri tangga, diterapkan aturan transfer muatan berikut:
1. Kondisi Kluster Simetris ($r \sim r$)
   Jika terdapat dua simpul bertetangga $v_i \sim v_j$ yang memiliki derajat simpul yang sama $d(v_i) = d(v_j) = r$ dimana $r \in \{3, 4, 5\}$, maka pasangan simpul ini didefinisikan satu kesatuan kluster **Muatan gabungan** sebagai berikut:
   $$M_{shared} = +2 M_0(r)$$
2. Fungsi Alter-Lintasan Tangga
   Untuk setiap sub-graf yang membentuk lintasan rantai anak tangga $T = \{v_1, v_2, \dots, v_m\}$ perpindahan muatan antar-simpul berderajat $r \in \{3, 4, 5\}$ di sepanjang lintasan tersebut diatur secara otomatis oleh Fungsi Lintasan berdasarkan posisi langkah anak tangga ($n$):
   $$M_{transfer} (n) = 2 (-1)^{n+1} M_0 (r)$$
