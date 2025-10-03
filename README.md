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

Para arrancarlo podemos usar el comando `docker start -a priceless_swanson` el -a es una abreviatura que la utilidd de linea de comandos de docker permite
