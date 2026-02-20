# Tutorial 2 - Introduction to Game Engine

## Latihan Playtest
- Apa saja pesan log yang dicetak pada panel Output?
- Coba gerakkan landasan ke batas area bawah, lalu gerakkan kembali ke atas hingga hampir menyentuh batas atas. Apa saja pesan log yang dicetak pada panel Output?
- Buka scene MainLevel dengan tampilan workspace 2D. Apakah lokasi scene ObjectiveArea memiliki kaitan dengan pesan log yang dicetak pada panel Output pada percobaan sebelumnya?

Output mengeluarkan pesan **Platform initialized** saat playtest di start dan **Reached Objective!** saat pesawat menyentuh batas atas dari scene. Pesan tersebut akan terulang terus setiap kali pesawat melewati area CollisionShape2 yang terdapat pada scene tersebut. Jadi iya, lokasi scene ObjectiveArea memiliki kaitan dengan pesan log yang dicetak. Tab signals dari ObjectiveArea juga menunjukkan bahwa iya memiliki beberapa signal seperti area_entered yang mengindikasi bahwa setiap kali ada benda yang melewati area tersebut akan terjadi sebuah action.

## Latihan: Memanipulasi Node dan Scene

- Scene BlueShip dan StonePlatform sama-sama memiliki sebuah child node bertipe Sprite2D. Apa fungsi dari node bertipe Sprite2D?

Sprite2D adalah node yang berfungsi untuk menampilkan gambar 2D pada sebuah scene 2D. Dalam kasus ini gambar pesawat pixel tersebut adalah sprite yang digunakan pada node Sprite2D ini. 

- Root node dari scene BlueShip dan StonePlatform menggunakan tipe yang berbeda. BlueShip menggunakan tipe RigidBody2D, sedangkan StonePlatform menggunakan tipe StaticBody2D. Apa perbedaan dari masing-masing tipe node?

RigidBody2D adalah tipe node yang biasanya digunakan pada objek yang dinamis atau memiliki gerakan. RigidBody2D umumnya memiliki *physics*. StaticBody2D biasanya digunakan sebagai tembok atau pembatas pada game karena umumnya tidak memiliki *physics*.

- Ubah nilai atribut Mass pada tipe RigidBody2D secara bebas di scene BlueShip, lalu coba jalankan scene MainLevel. Apa yang terjadi?

Tidak ada perubahan yang terjadi saat mengubah mass node RigidBody2D pada BlueShip. 

- Ubah nilai atribut Disabled milik node CollisionShape2D pada scene StonePlatform, lalu coba jalankan scene MainLevel. Apa yang terjadi?

Saat Disabled di centang hidup pada CollisionShape2D, StonePlatform seolah tidak ada dan ditembus langsung oleh pesawat.

- Pada scene MainLevel, coba manipulasi atribut Position, Rotation, dan Scale milik node BlueShip secara bebas. Apa yang terjadi pada visualisasi BlueShip di Viewport?

Tampilan BlueShip sendiri tidak berubah, tetapi saat position X dan Y valuesnya diubah BlueShip pindah posisi. Saat value rotation diubah BlueShip *rotate* secara dua dimensi dan mengubah value Scale dapat membuat ukuran dari BlueShip lebih besar atau lebih kecil. 

- Pada scene MainLevel, perhatikan nilai atribut Position node PlatformBlue, StonePlatform, dan StonePlatform2. Mengapa nilai Position node StonePlatform dan StonePlatform2 tidak sesuai dengan posisinya di dalam scene (menurut Inspector) namun visualisasinya berada di posisi yang tepat?

Position pada StonePlatform dan StonePlatform2 tidak sesuai karena pada tab inspector yang ditampilkan adalah posisi lokal (local position) yang relatif terhadap parent node yaitu PlatformBlue, bukan posisi global dari keseluruhan scene tersebut. 