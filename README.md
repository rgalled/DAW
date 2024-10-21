<h3>0º, creamos ambas maquinas virtuales, para ello<h3>
<p>     Creamos un directorio<p>
<p>     Abrimos visual studio code en el directorio creado y abrimos la terminal<p>
<p>     Ejecutamos el comando "vagrant init"<p>
<p>     Dentro de este archivo configuramos y creamos las maquinas virtuales<p>
<p>     Para ponerlas en marcha ejecutamos el comando "vagrant up"<p>
<img scr="/img/vagrant_maqina.PNG">
<br>
<h3>1º-2º-3º, activar escucha del servidor para ipv4, dnssec-validation a yes, permitir consulta a ip concretas<h3>
<p>     Nos conectamos a la maquina virtual usando el protocolo ssh = "vagrant ssh 'nombre de la maquina'"<p>
<p>     En la maquina, vamos a /etc/bind, y dentro de ahí abrimos el archivo de configuración named.conf.options<p>
<p>     1-Dentro de este archivo añadimos la opción listen-on-v6 y le ponemos el valor none<p>
<p>     2-Dentro de opciones, creamos la opción dnssec-validation con valor yes<p>
<img scr="/img/options.PNG">
<p>     3-Creamos la ventana de acl autorizados<p>
<p>     3-Dentro de options, creamos una opcion allow-recursion con nombre a autorizados<p>
<p>     3-Dentro de los acl configuramos las ip que permitiran recursión<p>
<img scr="/img/acl.PNG">
<h3>4º-, Establecer venus como servidor maestro<h3>
<p>     Volvemos al archivo named.conf.options<p>
<p>     Dentro del archivo creamos un apartado nuevo para la zona "venus.sistema.test"<p>
<p>     Establecemos el tipo como maestro<p>