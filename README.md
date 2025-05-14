# INSTALAMOS DEBIAN

En VirtualBox instalamos la máquina Debian

![Debian](./Root/1ºInstalarVB.png)

Configuramos el usuario desde VirtualBox

![Debian](./Root/2ºUsuario.png)

Y abrimos Debian

![Debian](./Root/3ºAbrirDebian.png)

# CONFIGRAMOS KALI

Añadimos Kali a Debian

![Debian](./Root/4ºAñadirKali.png)

Pulsamos F12 para entrar en el boot menu y seleccionamos la opción de arranque (opción c)

![Debian](./Root/5ºBootMenu.png)

Arrancamos la máquina e iniciamos con el live

![Debian](./Root/6ºLive.png)

Ponemos la distribución del teclado en castellano

![Debian](./Root/7ºTeclado.png)

Iniciamos con '''sudo su''' y ejecutamos '''df -Th''' para ver que discos están conectados al equipo.

![Debian](./Root/8ºdf.png)

Hacemos '''ls /dev''' para buscar los dispositivos conectados al equipo y buscamos los '''/ds.'''
Estos serán los discos en los que está instalado el Debian y sobre el que está corriendo Kali.

![Debian](./Root/9ºls.png)

# USO DE CHROOT

Ahora vamos a usar chroot para modificar el directorio raiz de Kali para cargar el sistema de ficheros de Debian '''/dev/sda'''
Vamos a crear un directorio en la ruta, donde montamos la información.
'''mkdir /mnt/recuperar && ld -ld /mnt/recuperar'''

![Debian](./Root/10ºrecuperar1.png)

Ahora montamos el disco

![Debian](./Root/11ºmontar.png)

Una vez montado el disco comprobamos que la raíz del Debian esta en '''/mnt/recuperar'''

![Debian](./Root/12ºDentrorecuperar.png)

# MONTAMOS DIRECTORIOS

Para usar la raíz del directorio '''/recuperar''' necesitamos montar los directorios:
'''/proc, /sys y /dev''' dentro de la carpeta '''/recuperar'''.

![Debian](./Root/13ºdevprocsys.png)

Ahora usamos el comando '''chroot /mnt/recuperar /bin/bash'''

![Debian](./Root/14ºchroot.png)

Comprobamos que los ficheros son los de Debian observando el fichero '''/etc/passwd'''

![Debian](./Root/15ºusuariocontraseña.png)

Ahora somos root en Debian, lo que nos permite realizar acciones dentro de Debian.
Vamos a cambiarle la contraseña al usuario de Debian

![Debian](./Root/16ºcambiocontraseña.png)

Corroboramos en Debian que se ha cambiado la contraseña.

![Debian](./Root/17ºnewcontraseña.png)
