**[ 1 ]---------------------------------------------------------------------------------**  
Menghapus filesistem.squashfs jika sebelumnya membuat filesistem.squashfs  
Jika Pertama kali membuat iso lewatkan perintah dibawah ini  
PENTING UNTUK DIPERHATIKAN JIKA MAU BIKIN LAGI filesystem.squashfs  
FILE YANG LAMA WAJIB HAPUS JIKA TIDAK AKAN MENGALAMI ERROR  
```
sudo rm $HOME/livecdtmp/extract-cd/casper/filesystem.squashfs 
```
**[ 2 ]---------------------------------------------------------------------------------**  
Membuat Folder Kerangka dvd (casper).  
```
cd $HOME/livecdtmp/
sudo chmod +w ./extract-cd/casper/filesystem.manifest
sudo su
sudo chroot ./edit dpkg-query -W --showformat='${Package} ${Version}\n' > ./extract-cd/casper/filesystem.manifest
printf $(sudo du -sx --block-size=1 edit | cut -f1) > ./extract-cd/casper/filesystem.size
exit
sudo cp ./extract-cd/casper/filesystem.manifest ./extract-cd/casper/filesystem.manifest-desktop
```
**[ 3 ]---------------------------------------------------------------------------------**  
**PILIH SALAH SATU DIBAWAH INI MAU STANDAR COMPRESS ATAU HIGH COMPRESS**  
**A. Membuat filesystem.squashfs dari Hasil Proyek Remastering STANDAR COMPRESS**
```
cd $HOME/livecdtmp/
sudo mksquashfs ./edit ./extract-cd/casper/filesystem.squashfs
```
**B. Membuat filesystem.squashfs dari Hasil Proyek Remastering HIGH COMPRESS BASIC**
```
cd $HOME/livecdtmp/
sudo mksquashfs ./edit ./extract-cd/casper/filesystem.squashfs -b 1048576 -comp xz -Xdict-size 100%
```
**C. Membuat filesystem.squashfs dari Hasil Proyek Remastering HIGH COMPRESS ALTERNATIF**
```
cd $HOME/livecdtmp/
sudo mksquashfs ./edit ./extract-cd/casper/filesystem.squashfs -comp xz -always-use-fragments -b 4096
```
**[ 4 ]---------------------------------------------------------------------------------**  
Menghapus md5sum.txt and calculate baru md5sums (Silahkan Hapus file md5sum.txt atau MD5SUMS).  
```
cd $HOME/livecdtmp/extract-cd/
sudo rm MD5SUMS
sudo rm md5sums.txt
```
**[ 5 ]---------------------------------------------------------------------------------**  
Membuat generate MD5SUMS baru.  
```
cd $HOME/livecdtmp/extract-cd/
find -type f -print0 | sudo xargs -0 md5sum | grep -v isolinux/boot.cat | sudo tee MD5SUMS
```
**[ 6 ]---------------------------------------------------------------------------------**  
**PILIH SALAH SATU DIBAWAH INI MAU STANDAR COMPRESS ATAU HIGH COMPRESS**  
A. Membuat File image ISO Standar Kurang Dari 4GB**  
Silahkan Ganti nama iso xentaos-1.3.2-cinnamon-amd64 sesuai yang anda inginkan.  
```
cd $HOME/livecdtmp/
sudo mkisofs -r -V "xentaos-1.3.2-cinnamon-amd64" -cache-inodes -J -l -b isolinux/isolinux.bin -c isolinux/boot.cat -no-emul-boot -boot-load-size 4 -boot-info-table -o ../xentaos-1.3.2-cinnamon-amd64.iso extract-cd
cd $HOME/ && sudo chmod 777 xentaos-1.3.2-cinnamon-amd64.iso
```
**B. Membuat File image ISO Lebih Dari 4GB BASIC**  
Silahkan Ganti nama iso xentaos-1.3.2-cinnamon-amd64 sesuai yang anda inginkan.  
```
cd $HOME/livecdtmp/
sudo mkisofs -allow-limited-size -r -V "xentaos-1.3.2-cinnamon-amd64" -cache-inodes -J -l -b isolinux/isolinux.bin -c isolinux/boot.cat -no-emul-boot -boot-load-size 4 -iso-level 3 -boot-info-table -o ../xentaos-1.3.2-cinnamon-amd64.iso ./extract-cd
cd $HOME/ && sudo chmod 777 xentaos-1.3.2-cinnamon-amd64.iso
```
**C. Membuat File image ISO Lebih Dari 4GB ALTERNATIF**  
Silahkan Ganti nama iso xentaos-1.3.2-cinnamon-amd64 sesuai yang anda inginkan.  
```
cd $HOME/livecdtmp/
sudo mkisofs -D --allow-limited-size -r -V "xentaos-1.3.2-cinnamon-amd64" -cache-inodes -J -l -b isolinux/isolinux.bin -c isolinux/boot.cat -no-emul-boot -boot-load-size 4 -boot-info-table -o ../xentaos-1.3.2-cinnamon-amd64.ISO ./extract-cd
cd $HOME/ && sudo chmod 777 xentaos-1.3.2-cinnamon-amd64.iso
```
**[ 7 ]---------------------------------------------------------------------------------**  
Membuat ISO Hybrid.  
```
cd $HOME/
isohybrid xentaos-1.3.2-cinnamon-amd64.iso
```
**[ 8 ]---------------------------------------------------------------------------------**  
Membuat Checksum File ISO MD5sum.  
```
cd $HOME/
md5sum xentaos-1.3.2-cinnamon-amd64.iso > xentaos-1.3.2-cinnamon-amd64.iso.md5sum
```
**[ 9 ]---------------------------------------------------------------------------------**  
Membuat Checksum File ISO SHA1sum.  
```
cd $HOME/
sha1sum xentaos-1.3.2-cinnamon-amd64.iso > xentaos-1.3.2-cinnamon-amd64.iso.sha1sum
```
**[ 10 ]---------------------------------------------------------------------------------**  
Membuat Checksum File ISO SHA2sum.  
```
cd $HOME/
sha2sum xentaos-1.3.2-cinnamon-amd64.iso > xentaos-1.3.2-cinnamon-amd64.iso.sha2sum
```
