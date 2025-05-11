## Practica 6 - Red en produccion con 5 nodos
### 1er Paso - Crear la estructura de nuestros directorios
mkdir Practica6
cd Practica6
mkdir -p Node-1/data Node-2/data Node-3/data Node-4/data Node-5/data

### 2do Paso
Crear un archivo de configuracion donde se definirarn los parametros de la red y la cantidad de nodos
{ ibftConfigFile.json }

### 3er Paso
Generar las claves de los nodos y el archivo genesis.json
utilizaremos el comando besu operator: besu operator generate-blockchain-config --config-file=ibftConfigFile.json --to=networkFiles --private-key-file-name=key
Esto creara el archivo Genesis con la configuracion de nuestra red y un directorio con las claves privadas y publicas de cada nodo.

### 4to paso
Copiaremos el archivo genesis a nuestro directorio principal

### 5to paso
En el directorio data de los nodos deberemos copair las cables privadas y publicas correspondientes

### 6to paso Conectar los nodos entre ellos
Deberemos crear un archivo llamado static-nodes.json dentor del directorio data con las URLs enodes de los nodos

### 7to paso
Iniciaremos cada nodo ajustando los puestos y rutas segun el nodo que queramso levantar

besu \
  --data-path=Node-1/data \
  --genesis-file=genesis.json \
  --node-private-key-file=Node-1/data/key \
  --rpc-http-enabled \
  --rpc-http-port=8545 \
  --rpc-http-api=ETH,NET,IBFT \
  --host-allowlist="*" \
  --p2p-port=30303

## Errores en la Practica

No todos los nodos se conectan entre si:
Nodo 1: 
<span>[https://raw.githubusercontent.com/CrsithianC/Practica6Cristhian-Castillo/imagenes/nodo1.png](https://github.com/CrsithianC/Practica6Cristhian-Castillo/blob/main/imagenes/nodo1.png)<span>

  

