Keterangan Panduan
-----------------------------------------------------------------------------
Chapter 1.    Persiapan Perangkat Lunak.
      Berisi Panduan Script dan Perintah Perintah Untuk Memasang Perkakas di
      Hostsistem dari Project Remaster. Hostsistem Disarankan Keluarga dari
      Debian atau Distro Keluarga Ubuntu. (Distro Selain Keluarga Debian dan 
      Ubuntu Belum di Test)
      
Chapter 2a.   Membuat Kerangka Project Remaster.
      Berisi Panduan Script dan Perintah Perintah Untuk Membuat Kerangka dari
      Project Remaster Pertama Kali. 

      Keterangan Directory Kerangka Project Remaster :
        * (edit)
          edit adalah sebuah filesystem dari hasil extrak filesystem Distro
          Awal dari Project Remaster. Dihasilkan dari Mengektrak 
          ./mnt/casper/filesystestem.squashfs.
          Di Directory inilah yang nantinya akan di Modifikasi atau Membuat
          Distro Remastering. 
          Untuk Modifikasinya Baca di "xenta-remaster/Indonesia/Panduan/Distro"
          
          CATATAN: UNTUK MEMODIFIKASINYA DIPERLUKAN CHROOT
          Panduannya ada di : 
            "2b.   Memulai Chroot Project Remaster Pertamakali"
          Untuk Melanjutkan Project Remaster Sebelumnya.
          Panduannya ada di :
            "3.    Memulai Kembali Chroot Project Remaster Sebelumnya".
            
        * (extract-cd)
        extract-cd adalah sebuah struktur dari hasil extrak image ISO Distro
          Awal dari Project Remaster. Dihasilkan dari Mengektrak 
          ./mnt/*
          Di Directory inilah yang nantinya akan di Modifikasi Image ISO
          atau Membuat Image ISO Distro Remastering. 
          Untuk Modifikasinya Baca di "xenta-remaster/Indonesia/Panduan/ISO"
          
        * (mnt)
        mnt adalah sebuah directori sementara untuk mengaikatkan Image ISO Distro
        Awal dari Project Remaster. Setelah Selesai Membuat Kerangka Project Remaster
        Directory ini akan dihapus.
        
Chapter 2b.   Memulai Chroot Project Remaster Pertamakali.
      Berisi Panduan Script dan Perintah Perintah Untuk Memulai Chroot Remaster 
      Pertama Kali.
      
Chapter 3.    Memulai Kembali Chroot Project Remaster Sebelumnya.
      Berisi Panduan Script dan Perintah Perintah Untuk Memulai Kembali Chroot 
      Project Remaster Sebelumnya.
  
Chapter 4.    Keluar dari Chroot Project Remaster.
      Berisi Panduan Script dan Perintah Perintah Untuk Keluar dari Chroot 
      Project Remaster.
  
Chapter 5.    Membuat Image ISO Project Remaster.
      Berisi Panduan Script dan Perintah Perintah Untuk Membuat Image ISO
      dari Hasil Project Remaster.
  
