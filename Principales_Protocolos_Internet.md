# Principales protocolos de Internet

## Protocolo

Un **protocolo** es un método estándar que permite la comunicación entre procesos (que potencialmente se ejecutan en diferentes equipos), es decir, un conjunto de reglas y procedimientos que deben respetarse para el envío y la recepción de datos a través de una red. En informática, un protocolo no es más que un conjunto de reglas formales que permiten a dos dispositivos intercambiar datos de forma no ambigua.

En Internet, los protocolos utilizados pertenecen a una sucesión de protocolos o a un conjunto de protocolos relacionados entre sí. Este conjunto de protocolos se denomina TCP/IP.

### TCP/IP

_Transmission Control Protocol_ o Protocolo de Control de Transmisión, fragmenta los datos en paquetes de información. Después, estos paquetes son enviados a la red, posiblemente sobre rutas diferentes. El IP es protocolo más básico de Internet, y provee todos los servicios necesarios para el transporte de datos. Cualquier otro protocolo de internet se basa en IP.

Fundamentalmente IP provee:

- **Direccionamiento**: Las cabeceras IP contienen las direcciones de las máquinas de origen y destino (direcciones IP), que serán usadas por los enrutadores para decidir el tramo de red por el que circularán.
- **Fragmentación**: Si la información a transmitir ("datagramas") supera el tamaño máximo "negociado" (MTU) en el tramo de red por el que va a circular, podrá ser dividida en paquetes más pequeños.
- **Tiempo de vida de Paquetes**: Cada paquete IP contiene un valor de Tiempo de Vida (TTL) que va disminuyendo cada vez que un enrutador recibe y reenvía el paquete. Cuando este valor llega a 0, el paquete deja de ser reenviado.
- **Tipo de servicio**: Valor sin definición previa, puede indicar la prioridad del paquete.
- **Otras opciones**: Ruta a seguir, seguimiento de ruta, opciones de seguridad, etc. 

Por su parte, el protocolo TCP proporciona un servicio de comunicación que forma un circuito, es decir, hace fluir los datos entre el origen y el destino para que sea continuo. Este circuito se denomina conexión.

#### FTP

_File Transfer Protocol_ o Protocolo de transferencia de archivos. Es un protocolo que define cómo transferir archivos de un ordenador a otro, de un servidor remoto a un servidor local o viceversa. 

![FTP Diagram](http://static.commentcamarche.net/es.kioskea.net/pictures/internet-images-modeleftp.gif "FTP Diagram")

Durante una conexión FTP, se encuentran abiertos dos canales de transmisión:

- Un canal de comandos (canal de control)
- Un canal de datos
 
Por lo tanto, el cliente y el servidor cuentan con dos procesos que permiten la administración de estos dos tipos de información:

- DTP (_Proceso de transferencia de datos_)
- PI (_Intérprete de protocolo_)
 
##### Los comandos FTP

Los comandos FTP hacen posible especificar:

- El puerto utilizado
- El método de transferencia de datos
- La estructura de datos
- La naturaleza de la acción que se va a realizar (Recuperar, Enumerar, Almacenar, etc.)

El objetivo del protocolo FTP es:

- permitir que equipos remotos puedan compartir archivos
- permitir la independencia entre los sistemas de archivos del equipo del cliente y del equipo del servidor.
- permitir una transferencia de datos eficaz.

**Puerto de comunicación**: 21

#### HTTP

_Hypertext Transfer Protocol_ o Protocolo de Transferencia de Hipertexto. Es el protocolo utilizado por los servidores de la World Wide Web desde su nacimiento. El protocolo HTTP es el que permite el intercambio de información hipertextual (enlaces) de las páginas web. 

El propósito de HTTP es permitir la transferencia de archivos (principalmente, en formato HTML), entre un navegadro (el cliente) y un servidor web (denominado, entre otros _httpd_ en equipos UNIX) localizado mediante una cadena de caracteres denominada dirección URL.

Este protocolo principalmente:

- Permite la transferencia de objetos multimedia, codificando los archivos binarios en cadenas de caracterres. El contenido de cada objeto intercambiado está identificado por su clasificación MIME.
- No mantiene estado. Cada petición de un cliente a un servidor no es influida por las transacciones anteriores.

La comunicación entre el navegador y el servidor se lleva a cabo en dos etapas:

- El navegador realiza una **solicitud HTTP**
- El servidor procesa la solicitud y después envía una **respuesta HTTP**
 
![HTTP](http://static.commentcamarche.net/es.kioskea.net/pictures/internet-images-comm.gif "HTTP")

##### Comandos HTTP

El protocolo HTTP/1.1 consta de los siguientes comandos:

- GET: Sirve para recoger información del servidor.
- HEAD: Similar a GET, pero pide solamente la cabecera del objeto.
- POST: Envía datos de información al servidor.
- PUT: Almacena un objeto en una URL especificada.
- DELETE: Elimina el objeto especificado.
- TRACE: Realiza un eco de la solicitud recibida,
- OPTIONS: Devuelve los métodos HTTP que soporta el cliente.
- CONNECT: Se utiliza en los servidores proxy.

##### Códigos de estado

Se clasifican en 5 categorías:

- 1xx: Mensajes informativos.
- 2xx: Mensajes asociados con operaciones realizadas correctamente.
- 3xx: Mensajes de redirección, que informan de operaciones complementarias.
- 4xx: Errores del cliente.
- 5xx: Errores del servidor.

**Puerto de comunicación**: 80

#### Protocolos de mensajería (SMTP, POP3 e IMAP4)

![Protocolos de mensajería](https://curiosoando.com/wp-content/uploads/2013/12/smtp_pop_imap.png "Protocolos de mensajería")

#### SMTP

El SMTP _Simple Mail Transfer Protocol_ o Protocolo de Transmisión de Correo Simple es el protocolo que nos permite recibir correos electrónicos y, junto con el protocolo POP (_Post Office Protocol_) o Procolo de Oficina de Correo, usado por los ordenares personales para administrar el correo electrónico, nos permitirá bajarnos los mensajes a nuestro ordenador. Para la mensajería instantánea se usa ahora el protocolo IMAP _Internet Messagins Access Protocol_ (Procolo de mensajería instantánea en Internet).

![SMTP](http://support.ricoh.com/bb_v1oi/pub_e/oi_view/0001043/0001043279/view/fax/image/cjn014.gif "SMTP")

El protocolo SMTP funciona con comandos de textos enviados al servidor SMTP. A cada comando enviado por el cliente, le sigue una respuesta del servidor STMP compuesta por un número y un mensaje descriptivo.

Las especificaciones básicas del protocolo SMTP indican que todos los caracteres enviados están codificados mediante el código ASCII de 7 bits y que el 8° bit sea explícitamente cero.

##### Comandos SMTP

Los principales comandos SMTP:

- HELO (ahora EHLO): Identificación que utiliza la dirección IP o el nombre de dominio del equipo remitente.
- MAIL FROM: Identificación del remitente.
- RCPT TO: Identificación de la dirección del destinatario.
- DATA: Cuerpo del correo electrónico.
- QUIT: Salida del servidor SMTP.

**Puerto de comunicación**: 25

#### POP3

Permite recoger el correo electrónico en un servidor remoto. 

![POP3](http://1.bp.blogspot.com/-ZQ3Jcz9hULA/T9T7evLsG2I/AAAAAAAAAG0/LNDy-N6UPNA/s1600/POP3Access1116255843783.png "POP3")

Existen dos principales versiones de este protocolo, POP2 y POP3, a los que se les asignan los:

**Puertos de comunicación**:

- POP2: 109
- POP3: 110

Al igual que con el protocolo SMTP, el protocolo POP funciona con comandos de texto enviados al servidor POP.

##### Comandos

Principales comandos POP3:

- USER identification: Permite la autenticación.
- PASS password: Permite especificar una contraseña de usuario.
- STAT: Información acerca de los mensajes del servidor.
- RETR: Número de mensaje que se va a recoger.
- DELE: Número de mensaje que se va a eliminar.
- LIST: Número de mensaje que se va a mostrar.
- QUIT: Solicita la salida del servidor POP3.

#### IMAP

![IMAP](http://www.informatica-hoy.com.ar/aprender-informatica/imagenes/imap-client-server.jpg "IMAP")

Es un protocolo alternativo a POP3, pero que ofrece más posibilidades:

- Permite administrar diversos accesos de manera simultánea.
- Permite administrar diversas bandejas de entrada.
- Brinda más criterios que pueden utilizarse para ordenar los correos electrónicos.

**Puerto de comunicación**: 143

#### ARP

Es un protocolo de comunicaciones de la capa de red, responsable de encontrar la dirección de hardware (Ethernet MAC) que corresponde a determinada dirección IP. Para ello se envía un paquete ARP (_ARP request_) a la dirección de difusión de la red (_broadcast_, MAC = FF FF FF FF FF FF) que contiene la dirección IP por la que se pregunta, y se espera a que esa máquina (u otra) responda (_ARP reply_) con la dirección Ethernet que el corresponde. Cada máquina mantiene una caché con las direcciones traducidas para reducir el retardo y la carga.

ARP se utiliza en cuatro casos referentes a la comunicación entre dos hosts:

1. Cuando dos hosts están en la misma red y uno quiere enviar un paquete a otro.
2. Cuando dos _hosts_ están sobre redes diferentes y deben usar un _gateway_ o _router_ para alcanzar otro _host_.
3. Cuando un _router_ necesita enviar un paquete a un _host_ a través de otro _router_.
4. Cuando un _router_ necesita enviar un paquete a un _host_ de la misma red.

![ARP](https://upload.wikimedia.org/wikipedia/commons/c/c5/Arp_v1.PNG "ARP")


#### IRC

IRC o _Internet Relay Chat_ es un protocolo de comunicación que permite conversaciones (_chats_) y debates en grupo o en privado, en tiempo real siguiendo la arquitectura del modelo cliente-servidor, pero foormándose entre los servidores para acoger más usuarios.

![IRC](http://raulcenteno.bligoo.es/media/users/22/1123296/images/public/302478/Red_IRC.png?v=1343333310101 "IRC")

Existen varios tipos distintos de redes IRC, cada una de ellas integrada por un grupo de servidores conectados entre sí. A tales redes se les llama:

- IRCNet
- EFNet
- DALNet

Si se desea hablar con alguien en particular, se necesitará conectarse al mismo tipo de red. Sin embargo no necesita conectarse al mismo servidor. 

Existen personas encargadas de crear y mantener los canales (los llamados CS o Chan Service), personas encargadas de mantener la red (IRCop), usuarios con privilegios de administrador del canal (Op) e incluso robots (Bot) que automatizan servicios del canal.

##### Comandos básicos

- **/SERVER [Servidor IRC] [puerto]**
- **/NICK Nombre_de_usuario**
- **/JOIN #Nombre_del_canal**: Unirse a un chat.
- **/PART #Nombre_del_canal**: Abandonar un chat.

**Puerto de comunicación**: 194


#### Telnet

Protocolo que permite la conexión remota a otro ordenador y que permite manejarlo como si estuviese físicamente ante él. Así, es posible arreglar fallos a distancia o consultar datos en la otra máquina.

Ha sido un sistema muy utilizado por las grandes bibliotecas y centros de documentación como modo de acceso a sus catálogos en línea. Sin embargo, dejó de usarse hace unos años, cuando apareció el SSH (_Secure Shell_), que puede describirse como una versión cifrada de TELNET.

El protocolo TELNET se basa en tres conceptos básicos:

- el paradigma _Terminal virtual de red_ (NVT);
- el principio de opciones negociadas;
- las reglas de negociación.

![TELNET](http://www.oocities.org/es/luis_arreaza/ihai/T3G2.gif "TELNET")

Éste es un protocolo base, al que se le aplicacn otros protocolos del conjunto TCP/IP. Las especificaciones de Telnet no mencionan la autenticación porque Telnet se encuentra totalmente separado de las aplicaciones que lo utilizan. 

##### La noción de terminal virtual

Consiste en crear una abstracción del terminal que permita a cualquier host (cliente o servidor) comunicarse con otro host sin conocer sus características.

##### El principio de opciones negociadas

Telnet ofrece un sistema de negociaciones de opciones que permite el uso de funciones avanzaas en forma de opciones, en ambos lados, al iniciar solicitudes para su autorización desde el sistema remoto.

Las opciones de Telnet afectan por separado cada dirección del canal de datos. Entonces, cada parte puede negociar las opciones, es decir, definir las opciones que:

- desea usar (_DO_);
- se niega a usar (_DON'T_);
- desea que la otra parte utilice (_WILL_);
- se niega a que la otra parte utilice (_WONT'T_).

##### Las reglas de la negociación

Permiten evitar situaciones de enrollo automático(por ejemplo, cuando una de las partes envía solicitudes de negociación de opciones a cada confirmación de la otra parte).

- Las solicitudes sólo deben enviarse en el momento de un cambio de modo.
- Cuando una de las partes recibe la solicitud de cambio de modo, sólo debe confirmar su recepción si todavía no se encuentra el modo apropiado.
- Sólo debe insertarse una solicitud en el flujo de datos en el lugar en el que surte efecto.

**Puerto de comunicación**: 23
























