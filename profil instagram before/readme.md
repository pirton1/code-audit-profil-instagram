1. Jelaskan keputusan grid-cols/gap di tiap breakpoint — kenapa begitu?
Grid-cols dan gap dipilih berdasarkan keterbacaan konten dan space yang tersedia di tiap ukuran layar.
    Misalnya:

   1. Mobile (sm < 640px): biasanya grid-cols-1 supaya konten tersusun ke bawah agar mudah dibaca tanpa scroll horizontal. Gap kecil (gap-2 atau gap-4) agar tidak terlalu renggang.
        
   2. Tablet (md ≥ 768px): bisa mulai grid-cols-2 agar informasi lebih padat tapi masih terbaca. Gap sedang (gap-6) biar elemen tidak terlalu rapat.
        
   3. Desktop (lg ≥ 1024px atau xl ≥ 1280px): bisa grid-cols-3 atau lebih, karena ruang lebar. Gap lebih besar (gap-8) untuk memberi ruang visual agar tidak sesak.    
Jadi, keputusan ini berdasarkan prinsip UI/UX: makin kecil layar → fokus ke keterbacaan, makin besar layar → optimalkan pemanfaatan space.

3. Bagaimana kamu memanfaatkan utility responsive Tailwind untuk memecahkan masalah layout yang muncul di mobile?

    Dengan utility responsive (misal sm:, md:, lg:), kita bisa override styling sesuai breakpoint.


   Contoh masalah:

    - Card terlalu kecil di mobile → pakai w-full sm:w-1/2 md:w-1/3.

    - Text terlalu besar di layar kecil → pakai text-lg sm:text-xl md:text-2xl.

    - Stacking vs grid → flex flex-col sm:flex-row supaya mobile stack, desktop row.
      
    Intinya, utility responsive dipakai untuk membuat desain fleksibel: layout di mobile sederhana, tapi lebih kompleks di layar besar.

4. Jelaskan trade-off antara memakai banyak utility classes vs membuat component CSS tersendiri.


    a. Utility Classes (Tailwind langsung di HTML):
        kelebihan :
            - Cepat, konsisten, mudah diubah per breakpoint.
            - Tidak perlu berpindah file (langsung di markup).
        kekurangan :
            - Bisa membuat HTML panjang dan agak sulit dibaca kalau styling rumit.
    
    b. Custom CSS Component (di file terpisah):
        kelebihan :
            - Lebih rapi, reusable, HTML lebih bersih.
            - Cocok untuk gaya yang dipakai berulang kali (misal tombol utama, card).
        kekurangan :
            - Kurang fleksibel saat perlu penyesuaian kecil di breakpoint (harus override lagi).

    Jadi, biasanya: utility classes untuk layout unik / kecil, component CSS untuk pattern berulang.

