# [ 1 ]---------------------------------------------------------------------------------
# Membuat Kerangka Kerja Remastering
# Gunakan Perintah dibawah ini secara berurutan untuk memulai project remastering
# Pastikan tidak menggunakan user root # dan harus berada di user biasa $
cd $HOME
mkdir -p livecdtmp/{extract-cd,mnt}
cd ./livecdtmp

# [ 2 ]---------------------------------------------------------------------------------
# pastikan file iso yang mau diremaster berada di lokasi HOME User directory anda
sudo mount -o loop ~/EDIT-NAME-ISO-HERE-YANG-BUAT-DIREMASTER.iso mnt
# silahkan edit nama EDIT-NAME-ISO-HERE-YANG-BUAT-DIREMASTER dengan nama iso yang mau 
# diremastering

# [ 3 ]---------------------------------------------------------------------------------
# Mengextrak Directory dari File Iso yang di mount di mnt ke folder extract-cd
sudo rsync --exclude=/casper/filesystem.squashfs -a ./mnt/ ./extract-cd

# [ 4 ]---------------------------------------------------------------------------------
# Mengextrak filesystem.squashfs dari extract-cd folder
sudo unsquashfs ./mnt/casper/filesystem.squashfs
# CATATAN Jika Remastrting Debian ganti "casper" dengan "live"
# seperti ini sudo unsquashfs ./mnt/live/filesystem.squashfs

# [ 5 ]---------------------------------------------------------------------------------
# Menganti atau Memidahkan folder hasil extract filesystem.squashfs menjadi "edit"
sudo mv ./squashfs-root ./edit

# [ 6 ]---------------------------------------------------------------------------------
# Memutuskan Kait (umount) mnt yang berisi titik kait dari file iso
sudo umount ./mnt

# [ 7 ]---------------------------------------------------------------------------------
# Membersihkan directory "mnt" yang sudah tidak dipakai lagi
sudo rm -rf ./mnt
