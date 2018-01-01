**[ 1 ]---------------------------------------------------------------------------------**  
Pastikan Berada di Lokasi Project Remastering (livecdtmp).  
```
cd $HOME/livecdtmp/
```
**[ 2 ]---------------------------------------------------------------------------------**  
Mengcopikan file resolv.conf dari host ke directoy "edit".  
```
sudo cp /etc/resolv.conf ./edit/etc/
```
**[ 3 ]---------------------------------------------------------------------------------**  
Membuat kait (mount) /dev/.  
```
sudo mount --bind /dev/ ./edit/dev/
```
**[ 4 ]---------------------------------------------------------------------------------**  
Masuk dalam chroot dari folder "edit".  
```
sudo chroot ./edit
```
**[ 5 ]---------------------------------------------------------------------------------**  
Mengaikatan proc sysfs dan devpts.  
```
mount -t proc none /proc && mount -t sysfs none /sys && mount -t devpts none /dev/pts
```
**[ 6 ]---------------------------------------------------------------------------------**  
Membuat variable dari HOME yaitu /root dan mengatur Bahasa Default "C".  
```
export HOME=/root && export LC_ALL=C
```
**[ 7 ]---------------------------------------------------------------------------------**  
Ok anda sudah dalam mode chroot dari edit. Silahkan edit mau ditambahkan   
paket atau mengurangi paket dan lain lain.  
```
cd /
```
