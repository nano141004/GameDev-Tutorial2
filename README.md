### Mariano Gerardus Senduk / 2206814236

## Latihan: Playtest
1. Apa saja pesan log yang dicetak pada panel Output?

    Saat pertama kali di-play, pesan log yang muncul adalah "Platform initialized". Kemudian setelah dilakukan intruksi menggerakkan objek landasan  ke atas sehingga objek pesawatnya hampir menyentuh batas atas area permainan/window, maka muncul pesan log "Reached objective!".

2. Coba gerakkan landasan ke batas area bawah, lalu gerakkan kembali ke atas hingga hampir menyentuh batas atas. Apa saja pesan log yang dicetak pada panel Output?

    Ada pesan log "Reached objective!" lagi yang muncul.

3. Buka scene `MainLevel` dengan tampilan workspace 2D. Apakah lokasi scene ObjectiveArea memiliki kaitan dengan pesan log yang dicetak pada panel Output pada percobaan sebelumnya?

    Ya, saat objek pesawat sampai ke area pojok kiri atas window game maka objek tersebut berarti masuk juga ke area biru `CollisionShape2D`(child dari `ObectiveArea`), sehingga muncul pesan log "Reached objective!". Jika dilihat dari berkas ObjectiveArea.gd pada script, maka ada function "`_on_ObjectiveArea_body_entered`" yang akan melakukan print "Reached objective!" yang adalah pesan log tersebut.

## Latihan: Memanipulasi Node dan Scene
1. Scene `BlueShip` dan `StonePlatform` sama-sama memiliki sebuah child node bertipe `Sprite`. Apa fungsi dari node bertipe `Sprite`?

    Node `Sprite` berfungsi untuk menampilkan suatu texture/image. Dengan kata lain node ini yang dapat menampilkan objek pesawat dan landasan pada saat di-play.

2. Root node dari scene `BlueShip` dan `StonePlatform` menggunakan tipe yang berbeda. `BlueShip` menggunakan tipe `RigidBody2D`, sedangkan `StonePlatform` menggunakan tipe `StaticBody2D`. Apa perbedaan dari masing-masing tipe node?

    Bedanya adalah pada node tipe `RigidBody2D` dapat bergerak jika terdapat aksi yang diberikan pada node tersebut misalnya ada node lain yang ditabrakkan maka akan ada reaksi gerak pada node. Sedangkan pada node tipe `StaticBody2D` tidak dapat digerakkan oleh aksi yang diberikan pada node tersebut, kecuali digerakkan secara manual misalnya dengan script code.

3. Ubah nilai atribut `Mass` pada tipe `RigidBody2D` secara bebas di scene `BlueShip`, lalu coba jalankan scene `MainLevel`. Apa yang terjadi?

    Tidak ada perbedaan. Misalnya saat saya menambahkan nilai atribut `Mass` menjadi 1000 kg, tidak tampak saat landasan digerakkan ke bawah maka objek pesawat akan turun lebih cepat dari sebelumnya. Begitu juga saat saya menurunkan nilai atribut `Mass`, tidak tampak saat landasan digerakkan ke bawah maka objek pesawat akan turun lebih lambat dari sebelumnya.

4. Ubah nilai atribut `Disabled` pada tipe `CollisionShape2D` di scene `StonePlatform`, lalu coba jalankan scene `MainLevel`. Apa yang terjadi?

    Objek pesawat langsung turun menembus objek landasar ke bawah window sampai menghilang dari window. 

5. Pada scene `MainLevel`, coba manipulasi atribut `Position`, `Rotation`, dan `Scale` milik node `BlueShip` secara bebas. Apa yang terjadi pada visualisasi `BlueShip` di Viewport?



6. Pada scene `MainLevel`, perhatikan nilai atribut `Position` node `PlatformBlue`, `StonePlatform`, dan `StonePlatform2`. Mengapa nilai `Position` node `StonePlatform` dan `StonePlatform2` tidak sesuai dengan posisinya di dalam scene (menurut `Inspector`) namun visualisasinya berada di posisi yang tepat?

