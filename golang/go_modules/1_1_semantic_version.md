# Semantic Versioning

untuk semantic ini ditulis dalam bentuk major.minor.patch, dengan 

1. Tambah angka versi MAJOR jika membuat perubahan API yang tidak lagi cocok dengan versi sebelumnya.
2. Tambah angka versi MINOR jika menambahkan fitur tanpa membuat versi lama tidak bisa digunakan.
3. Tambah angka versi PATCH jika ada perbaikan bug tanpa membuat versi lama tidak bisa digunakan.


## Spesifikasi Semantic Version

1. Perangkat lunka dengan versi semantik harus menentukan API Pulibc. bisa dijelaskan dengan kode, atau ditulis di dokjmentasi, ditulis dengan jelas dan akurat.
2. Versi HARUS ditulis dalam bentuk X.Y.Z dengan X.Y.Z dalam bentuk bulat positif, dan tidka boleh di dahului dengan angka 0
3. Setelah versi dirilis isi dari versi tersebut TIDAK BOLEH DIUBAH. setiap perubahan HARUS merilis versi baru.
4. Versi MAJOR adalah untuk pengembangan awal, saatbanyak perubahan bisa terjadi. API public dianggap tidak stabil di VERSI ini.
5. VERSI 1.0.0 merupakan titika awal API public, setiap versi baru ditulis berdasarkan versi ini.
6. VERSI MINOR harus dinaikan jika ada fitur baru, atau ada fitur lama yang sudah usang. Versi ini BISA dinaikan jika ada tambahan fungsionalitas substansial atau terjadi peningkatan. Versi ini Bia dibuah bersama dengan versi PATCH. versi ppath harus dikembalikan ke angka 0 jika minor versi dinaikan.
7. Versi PATCH Harus dinaikan jika ada penambahan bug tanpa menambah fitur.
8. Versi dari MAJOR dapat di naikan jika ada perubahan yang membuat versi baru tidak kompatible dengan versi lama, seperti penghapusan vitur lama, menambah fitur baru yang tidak bisa diguanakn di versi lama, bisa dibuah bersama dengan versi p9ath dan minor, jika versi major dinaikkan, maka versi minor dan patch harus dikembalikan ke angka 0.
9. Versi selebelum rilis BISA ditulis dengan menambahkan garis dan bisa dipisah dnengan titik tepa setelah versi patch. Versi sebelum rilis harus ditulis dengan hurus ASCII alfanumerik dan garus [0-9A-Za-z], tidak boleh kosong, dan anga tidak boleh didahului dengan angak 0. Versi sebelum rilis dianggap tidak stabli dan dikesmapingkan jika ada versi stabil. Contoh: 1.0.0-alpha, 2.3.1-beta.
10. Build Metadata bisa ditulis setlah versi sebelum rilis didahului dengan tanda tambha dan bisa dipisah dengan titik. Build Metadata harus ditulis dengan huruf ASCII ditulis dengan garus [0-9A-Za-z]. Build meta data tidak boleh kosong. Build metadata merupkan id dari hasil build, dan dikesampingkan jika ada sebelum ada rilis atau yang lebih stabil. Contoh: 1.0.0-alpha+1, 1.5.2+3312
11. P9enentuan versi mana yag didahulukan berdasarkan versi stabil, lalu versi sebelum rilis, dan versi dengan Build Metadata. jika ada versi stabil yang sama, maka diambil versi dengan anka paling tinggi. Contoh 2.0.0 lebih didahulukan dari 1.0.0. 

## Sumber :
1. [semver](https://semver.org/lang/id)