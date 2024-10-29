# Readme!

**Pasos previos** -> Para configurar un contenedor coa imaxe oficial de bind9 usando o docker-compose, primeiro teremos que crear unha carpeta cos archivos de configuración que precisemos para arrincar o docker compose.

Nesta carpeta crearemos como mínimo un archivo .yml no que teremos que engadir as opcións necesarias para que funcione como desexamos.

Configuración do .yml O primeiro que teremos que saber para entender o seguinte arquivo é que se divide en diversas zonas (nas versións antiguas na primeira parte tiñas que indicar a versión, esta línea pódese evitar nas novas versións), falarei delas individualmente:

**_services_**: Nesta parte teremos que definir os contenedores empregados, como só é un trataremos os apartados do contendedor bind9, estos apartados saen das especificacións da imaxe oficial de bind9.

_image_ -> neste campo definiremos a imaxe que imos empregar, neste caso teremos quye escibir a ruta na que se atopa a imaxen, isto consultamolo na páxina oficial da imaxe.

_container-name_ -> aquí so escribiremos o nome co que nos referiremos o contenedor, para atopalo de forma mais sinxela.

_restart_ -> esta parte permitiranos que no caso de que o contenedor falle por algún motivo, este reinicese de forma automática.

_ports_ -> nesta parte indicanse os portos que publicamos, neste caso son 3, empregaremos o mesmo para tcp e udp, será o 54 dado que na máquina virtual non podemos usar o 53, e publicamos o porto 953 para consultas de control de localhost.

_volumes_ -> aquí teremos que definir os volumes nos que se montan os datos, o caché e os logs. Nun primer momento tratei de definir os volumes onde se van aloxar os datos, sin embargo dabame a error dadoq que non tiña os volumes funcionales na máquina, por eso comenteinos para evitar errores.

_network_ -> este apartado só indicara a rede á que se anclará o contenedor

**_networks_**: Nesta parte teremos que definir a rede xa que queremos que cree unha, en caso de que xa existira a rede poderíamos só indicalo no apartado anterior e omitiríamos este.

_red-bind9_ -> Indicamos o nome da rede xa que se non por defecto poñeranos o nome da rede por defecto co nome do proxecto onde se aloxa.

_driver_ -> Indica o tipo de rede, neste caso e ponte.