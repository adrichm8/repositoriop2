# repositoriop2
-Comproba que a tes a imaxe httpd
  Para ello se escribe el comando docker images y con  ello te muestra las imagenes

  
-Crea un contenedor de nome 'asir_httpd'.
  Para ello se escribe el comando docker run -d --name asir_httpd httpd y con ello ya estaría creado el contenedor

  
-Mapea o porto 80 do contenedor có 8080 da túa máquina. Utiliza bind mount para que o directorio do apache2 'htdocs' estea montado nun directorio da túa elección. Utiliza -v "$PWD"/htdocs:/usr/local/apache2/htdocs/
  Primero, crea el directorio en tu máquina con mkdir htdoc y posteriormente emplear docker run -d --name asir_httpd -p 8080:80 -v "$PWD"/htdocs:/usr/local/apache2/htdocs/ httpd

  
-Mostra unha páxina html aloxada no apache2 dende o teu navegador
  Para ello hago un touch htdocs/intex.html con un contenido dentro del archivo, posteriormente lo que hago es probar el servidor poniendo el puerto en el navegador

  
-Crea un contenedor 'asir_web1' que use este mesmo directorio para 'htdocs' e o puerto 8000
Para ello escribo el comando docker run -d --name asir_web1 -p 8000:80 -v "$PWD/htdocs:/usr/local/apache2/htdocs/" httpd
  

Crea outro contenedor 'asir_web2' có el mesmo directorio e otro puerto, como o 8090.
Para ello ponemos el comando docker run -d --name asir_web2 -p 8090:80 -v "$PWD/htdocs:/usr/local/apache2/htdocs/" httpd


Comproba que los dous servidores mostran a mesma páxina
Para ello en el caso de asir web pondríamos en el navegador http://localhost:8000 para asir_web1 y http://localhost:8090 para asir_web2



