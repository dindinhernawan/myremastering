#!/bin/bash
########################################################################
# AUTHOR    : XENTA OS
# LICENSE   : GNU GPL 3.0
# WEBSITE   : http://www.xentaos.org/
########################################################################

# Mengubah Bootscreen DVD Live
# Gunakan Perintah Dibawah ini

# 1. Membuat Kerangka Directory
cd $HOME/livecdtmp/extract-cd/casper
sudo su
mkdir temp
cd temp

# 2. Mengekstract file initrd.lz ke Kerangka directory
lzma -dc -S .lz ../initrd.lz | cpio -imvd --no-absolute-filenames

# 3. Mengubah Mengubah Bootscreen DVD Live
# Lokasi themenya ada di ada di $HOME/livecdtmp/extract-cd/casper/temp/usr/share/plymouth/themes/
# Disana Nani ada 2 Theme yaitu logo dan text
# Sample Artwork Plymouthnya ada di https://github.com/xentaos/xenta-plymouth-themes
# silahkan copy samplenya xenta-logo dan 
# xenta-text ke folder $HOME/livecdtmp/extract-cd/casper/temp/usr/share/plymouth/themes/
# Lalu silahkan rubah konfigurasinya di 2 file ini 
# text.plymouth untuk konfigurasinya plymouth textnya
text.plymouth 
#contoh
[Plymouth Theme]
Name=Xenta Text
Description=Text mode theme
ModuleName=ubuntu-text

[ubuntu-text]
title=Xenta OS 1.3
black=0x000000
white=0xeeeeee
brown=0x80c33b
blue=0xc7c7c7

# default.plymouth untuk konfigurasinya plymouth logonya
default.plymouth
# contoh
[Plymouth Theme]
Name=Xenta Logo 
Description=A theme that features a blank background with a logo.
ModuleName=script

[script]
ImageDir=/usr/share/plymouth/themes/xenta-logo
ScriptFile=/usr/share/plymouth/themes/xenta-logo/xenta-logo.script


# 4. Membangun initrd.lz lagi dari kerangka directory yang telah dimodifikasi
cd $HOME/livecdtmp/extract-cd/casper/temp
sudo su
find . | cpio --quiet --dereference -o -H newc | lzma -7 > ../initrd.lz
cd $HOME/livecdtmp/extract-cd/casper/
rm -rf temp

