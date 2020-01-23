# AMERO CORE

-  Con la siguiente documentacion se podra instalar el Core de Amero y ser parte de la red blockchain.

![](https://avatars2.githubusercontent.com/u/60229353?s=100&u=b9b3bdc2c70b0d5b6e99ddc63dcb73b3613e20f2&v=4)

# Instalación

### Requisitos Previos

**Hardware**
- Espacio en Disco: 120 GB SSD
- Memoria: 4 GB RAM
- Procesador : 4 VCPUs

**Software**
- Linux (Ubuntu 16.04 , 18.04)

**Network**
-  Acceso a internet con velocidad minima de 1/1 mbps
- 1 IPv4 Publica
- Apuertura de Puertos UDP y TCP :  59706/59707

Puerto TCP/UDP Main Net: 59706 
Puerto TCP/UDP Test Net: 59707

### Preparacion del Entorno

-  Actualizar en sistema operativo

`sudo apt-get update`

`sudo apt-get upgrade`

-  Instalacion de dependencias GIT

`sudo apt-get install git`


### Descargar Paqueteria

`sudo cd /var`

`sudo mkdir /core`

`sudo cd /core`

`sudo git clone https://github.com/amero-crypto/core.git`

### Configuracion

-  Acceder a folder con file de config.txt

`sudo cd /var/core/amero/data`

-  Copiar el file demo-config.txt a config.txt

`cp demo-config.txt config.txt`

-  Modificar file config.txt

`sudo nano config.txt`

    {
    "API_KEY"                       :   "INGRESE API KEY",
    "MINE_WALLET"             :   "",
    "IP_ADDRESS"                :   "IP PUBLICA DEL NODO",
    "API_ENABLED"              :   1,
    "NETWORK_MODE"        :   1,
    "SAVE_BIN_DATA"         :   1,
    "MINING_ENABLED"       :   0,
    "SSL_ENABLED"	         :   1
	}
    
#### Referencia de Parametros

- API_KEY : Se aulitiza para limitar los acceso y peticiones a la API , String sugerido 50 caracteres
- MINE_WALLET : Direccion Wallet para las Rewards de la minera
- IP_ADDRESS : Ingresar la Direccion IP Publica del Equipo Donde esta instalado el Core
- API_ENABLED : Permite Apagar/Prender las peticiones API al Nodo
- NETWORK_MODE : Modo de operacion del nodo : 1 = Main Net , 2 = Test Net
- SAVE_BIN_DATA: Modo de almacenamiento : 1 = Bin File, 2 = Txt File
- MINING_ENABLED: Permite la Mineria Directa en el nodo (no recomendado)
- SSL_ENABLED: Habilitar la comunicacion segura SSL (Main Net requiere SSL)

#### -

-  Guardar los cambios del file config.txt


# Test Amero Core

- Ir a folder de Amero Core

`cd /var/core/amero`

- Iniciar Fichero ./amero

`./amero`

- Si la Instalacion de Amero Core fue exitosa debera ver la siguiente pantalla

![](https://amero.lat/assets/images/git/example-node.png)

- Salir de  ./amero

`Ctrl + C`




# Iniciar Deamon Amero Core

#### Deamon

Utilizaremos PM2 para mantener Amero core funcionando en  Backgroud 

- Instalar PM2 (Requisito NODEJS)

`npm install pm2 -g`

`wget -qO- https://getpm2.com/install.sh | bash`

- Ir al Folder de Amero Core

`cd /var/core/amero`

- Agregar Amero Core a PM2 

`pm2 start amero`

- Finalizar Configuracion

`pm2 save`

`pm2 startup`

- Parar Amero Core

`pm2 stop amero`

- Ver Log de Amero Core

`pm2 logs`
