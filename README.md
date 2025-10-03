# Tarea3-SXE

## Descarga de la imagen docker de alpine
Para descargar la imagen de docker alpine, sin necesidad de arrancarlo, con el siguiente comando

```sh
docker pull alpine
```

El resultado de este comando es este 
<img width="1380" height="348" alt="imagen" src="https://github.com/user-attachments/assets/f0863e4e-ad23-4657-969e-76a2df756125" />

Si vemos las imagenes instaladas usando `docker image ls`

<img width="1256" height="304" alt="imagen" src="https://github.com/user-attachments/assets/04dec11e-7de2-46b2-be4b-e31eb9088379" />

## Manejo del contenedor
Ahora queremos crear un contenedor docker pero no queremos arrancarlo para eso usamos

```sh
docker create alpine
```
Esto se ejecutara con el siguiente contenedor y se vera esto en la terminal

<img width="1208" height="190" alt="imagen" src="https://github.com/user-attachments/assets/d78a4fe2-5647-40a7-bac2-dbb81c875427" />

Ahora el contenedor no esta arrancado pero imagina que queremos ver si esta creado y obtener su nombre
para eso usaremos el comando `docker ps -a` que nos mostrara lo siguiente

<img width="1818" height="184" alt="imagen" src="https://github.com/user-attachments/assets/d9f5cbb9-fc08-4920-b723-56e58bd2d3cf" />

Podemos ver que el contenedor existe y su nombre es priceless_swanson

Para arrancarlo podemos usar el comando `docker start -a priceless_swanson` el -a es una abreviatura que la utilidd de linea de comandos de docker que es como equivalente a `--attach`.

Ahora vamos a crear un contenedor de nombre `dam_alp1` con el siguiente comando

```sh
docker create -q --name dam_alp1 alpine tail -f /dev/null
```
Advertencia si el contenedor no encuentra un proceso activo, sale inmediatamente por eso le pongo eso para que el contenedor siga ejecutando
El comando nos genera el siguiente output

<img width="1330" height="118" alt="imagen" src="https://github.com/user-attachments/assets/55a1c4dc-51c0-4b30-b311-6cb13f499d4e" />

Esto crea un contenedor con el nombre `dam_alp1`

<img width="2272" height="160" alt="imagen" src="https://github.com/user-attachments/assets/d16bfa14-21a2-4251-828f-9aa36d28bf25" />

Uso `docker start -a dam_alp1` para arrancar el contenedor para acceder a el mediante una linea de comandos

Luego usamos, la i es de interactivo y la t de un pseudo teletipo(pseudo TTY en ingles) para poder tener una terminal en la que hacer algo
```sh
docker exec -it dam_alp1 sh
```










