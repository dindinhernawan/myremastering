**[ 1 ]---------------------------------------------------------------------------------**  
Gunakan Perintah dibawah ini jika keluar dari chroot.  
Perintah Ini untuk membersihkan paket paket dari debian packet yang  
dari didapat dari cache saat memasang aplikasi atau paket dari apt dan aptitude  
```
apt-get clean
aptitude clean
```
**[ 2 ]---------------------------------------------------------------------------------**  
Perintah ini untuk membersihkan paket paket yang sudah tidak diperlukan lagi
```
apt-get autoremove
```
**[ 3 ]---------------------------------------------------------------------------------**  
Membersikan Chace dan Bash_History
```
rm -rf /tmp/* ~/.bash_history
```
**[ 4 ]---------------------------------------------------------------------------------**  
Menghapus ID mesin
```
rm /var/lib/dbus/machine-id
rm /sbin/initctl
dpkg-divert --rename --remove /sbin/initctl
```
**[ 5 ]---------------------------------------------------------------------------------**  
Memutuskan titik kait dari proc sys dan devpts
```
umount /proc && umount /sys && umount /dev/pts
exit
```
**[ 6 ]---------------------------------------------------------------------------------**  
Memutuskan titik kait dari edit/dev/ (umount)
```
sudo umount ./edit/dev/
```
