# Tarea 3 SXE

## Descarga de la imagen Docker de alpine
Para descargar la imagen de Docker alpine, sin necesidad de arrancarlo, con el siguiente comando

```sh
docker pull alpine
```

El resultado de este comando es este 
<img width="1380" height="348" alt="imagen" src="https://github.com/user-attachments/assets/f0863e4e-ad23-4657-969e-76a2df756125" />

Sí, vemos las imágenes instaladas usando `docker image ls`

<img width="1256" height="304" alt="imagen" src="https://github.com/user-attachments/assets/04dec11e-7de2-46b2-be4b-e31eb9088379" />

## Manejo del contenedor
Ahora queremos crear un contenedor Docker, pero no queremos arrancarlo, para eso usamos

```sh
docker create alpine
```
Esto se ejecutará con el siguiente contenedor y se verá esto en la terminal

<img width="1208" height="190" alt="imagen" src="https://github.com/user-attachments/assets/d78a4fe2-5647-40a7-bac2-dbb81c875427" />

Ahora el contenedor no está arrancado, pero imagina que queremos ver si está creado y obtener su nombre
para eso usaremos el comando `docker ps -a` que nos mostrara lo siguiente

<img width="1818" height="184" alt="imagen" src="https://github.com/user-attachments/assets/d9f5cbb9-fc08-4920-b723-56e58bd2d3cf" />

Podemos ver que el contenedor existe y su nombre es priceless_swanson

Para arrancarlo podemos usar el comando `docker start -a priceless_swanson` él -a es una abreviatura que la utilidad de línea de comandos de Docker que es como equivalente a `--attach`.

Ahora vamos a generar un contenedor de nombre `dam_alp1` con el siguiente comando

```sh
docker create -q --name dam_alp1 alpine tail -f /dev/null
```
Advertencia, si el contenedor no encuentra un proceso activo, sale inmediatamente, por eso le pongo eso para que el contenedor siga ejecutando
El comando nos genera el siguiente output, el output es más o menos igual con el comando que aparece en esa captura y lo que yo he puesto, a lo mejor no sacaría la salida, pero no es muy diferente

<img width="1330" height="118" alt="imagen" src="https://github.com/user-attachments/assets/55a1c4dc-51c0-4b30-b311-6cb13f499d4e" />

Esto crea un contenedor con el nombre `dam_alp1`

<img width="2272" height="160" alt="imagen" src="https://github.com/user-attachments/assets/d16bfa14-21a2-4251-828f-9aa36d28bf25" />

Uso `docker start -a dam_alp1` para arrancar el contenedor para acceder a él mediante una línea de comandos

Luego usamos, la i es de interactivo y la t de un pseudo teletipo(pseudo TTY en inglés) para poder tener una terminal en la que hacer algo
```sh
docker exec -it dam_alp1 sh
```

Como podemos ver abajo aparece una terminal con esto ya estamos oficialmente en dam_alp1

Para dam_alp2 el proceso es lo mismo solo que cambiando el nombre, por lo que realmente no merece la pena ponerlo aquí

## Entrando a los contenedores 
Una vez ya en ``dam_alp1``, podemos ver la dirección ip con ``ip a``

<img width="2846" height="778" alt="imagen" src="https://github.com/user-attachments/assets/b4c90686-23c0-451c-96f5-5c24a30a1ec2" />

vemos que la ip comienza con 172 esto es parte de la interfaz de red de docker, como docker usar por defecto direcciones Ip que empiezan por 172

En ``dam_alp2`` se puede hacer lo mismo para ver la ip de la misma forma

<img width="2860" height="644" alt="imagen" src="https://github.com/user-attachments/assets/fa8eeb03-7d78-45e5-a1a1-1d29ae1331f8" />

Si se ve un icono como de Youtube es porque lo hice en casa y tenía eso en el navegador, ya que estaba escuchando música.

Pero bueno, ahora he probado a hacer ping desde dam_alp1 hacia dam_alp2

<img width="2856" height="530" alt="imagen" src="https://github.com/user-attachments/assets/440901d4-1fe7-4055-98e3-b0583d9676ec" />

Y ahora voy a probar a hacerlo desde dam_alp2 hacia dam_alp1

<img width="1200" height="284" alt="imagen" src="https://github.com/user-attachments/assets/6026e5bc-66e8-4c3b-b41a-8af92170900f" />

Al salir de dam_alp1 como el proceso que inicio originalmente el contenedor sigue activo, pues el contenedor se ha quedado en segundo plano

Para ver la memoria en el disco uso ``docker system df`` para ver cuanto los contenedores o las imagenes, aunque lo que nos interesa sean los contenedores

<img width="2746" height="512" alt="imagen" src="https://github.com/user-attachments/assets/abbb9250-65b2-46d7-b1b1-cf0ebfa0779f" />

Para ver cuanta RAM, CPU y demás ocupan los contenedores Docker que estamos ejecutando, usamos el comando ``docker stats`` de la siguiente manera

<img width="2842" height="372" alt="imagen" src="https://github.com/user-attachments/assets/eaeedc49-723e-48da-941c-044d0b1721f4" />






