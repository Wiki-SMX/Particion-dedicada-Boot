# Partición Boot Dedicada FEDORA

1. Creamos una particion de 200MB

2. Crear una Carpeta para montar la particion
 > mkdir /mnt/tmp

3. Montar la nueva particion
 > Localizamos nuestra particion de 200Mb con lsblk 
 > Supongamos que es /dev/sda9
 > mount /dev/sda9 /mnt/tmp

5. Copiamos nuestro actual boot a la particion
 > cp -af /boot /mnt/tmp

6. Instalamos el Grub apuntando a la nueva particion
 > grub2-install --root-directory=/mnt/tmp /dev/sda

7. Modificar /etc/fstab para añadir /boot al montado al inicio
 > /dev/sda9 /boot		ext4	defaults	1 2
