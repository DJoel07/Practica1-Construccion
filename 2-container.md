# Contenedores

### Crear un contenedor
Para crear un nuevo contenedor Docker a partir de una imagen específica, pero sin iniciarlo automáticamente. 

```
docker create --name <nombre contenedor> <nombre imagen>:<tag>
```
Crear el contenedor  **srv-web** usando la imagen nginx version alpine
```
docker create --name srv nginx:alpine
```
<img width="539" height="51" alt="image" src="https://github.com/user-attachments/assets/61489ef4-aa25-4ba1-a99b-cfcefb370a77" />

Si creas un contenedor en Docker sin asignarle un nombre específico utilizando la opción --name, Docker asignará automáticamente un nombre aleatorio al contenedor. Este nombre suele consistir en una combinación de palabras y números.  

Crear el contenedor usando la imagen hello-world
docker create hello-world
<img width="536" height="49" alt="image" src="https://github.com/user-attachments/assets/8ebe1956-ad71-4a18-b8be-86b373045949" />


### Listar los contenedores ejecutándose o no

```
docker ps -a
```
<img width="1039" height="129" alt="image" src="https://github.com/user-attachments/assets/22454cd5-7a60-433e-b081-e229b5e1b358" />


### Para iniciar un contenedor

```
docker start <nombre contenedor o identificador>
```
Iniciar el contenedor srv-web 
```
docker start srv-start
```
<img width="326" height="43" alt="image" src="https://github.com/user-attachments/assets/1af909dc-f7b6-4d00-a62f-d4d3a694f27d" />

# COMPLETAR

### Listar los contenedores ejecutándose
```
docker ps 
docker ps | grep <nombre contenedor>
```

```
docker ps 
docker ps | grep srv-start
```
<img width="850" height="68" alt="image" src="https://github.com/user-attachments/assets/9627e8ba-a0e8-4553-b7b0-462f4c9a6dc0" />

### Para detener un contenedor

```
docker stop <nombre contenedor>
docker stop srv-web
```
<img width="312" height="50" alt="image" src="https://github.com/user-attachments/assets/75bbc5e3-e382-4f53-920e-26e3706ad48e" />

### Para crear un contenedor y ejecutarlo inmediatamente

```
docker run --name <nombre contenedor> <nombre imagen>:<tag>
```
<img width="775" height="394" alt="image" src="https://github.com/user-attachments/assets/40282390-57ca-4747-8e91-e9a482634bf8" />

![Ecosistema de Docker](dockerRun.PNG)

Crear y ejecutar inmediatamente el contenedor **srv-web2** usando la imagen nginx:alpine

```
docker run --name svr-web2 nginx:alpine
```
**¿Qué sucede luego de la ejecución del comando?**
Se esta ejecutando el contenedor en primer plano, por lo cual la terminal esta usada por el contenedor 

Cuando ejecutas un contenedor en primer plano sin la opción -d (modo detach), el contenedor captura la entrada estándar (stdin) del terminal, lo que significa que el terminal queda "atrapado" y no puedes introducir más comandos hasta que detengas el contenedor.

### Para crear un contenedor y ejecutarlo inmediatamente sin estar vinculados al mismo
-d: Es la opción que indica a Docker que ejecute el contenedor en segundo plano (en modo "detach").
Cuando un contenedor se ejecuta en segundo plano, Docker devuelve el control al terminal inmediatamente después de iniciar el contenedor, lo que permite al usuario seguir ejecutando otros comandos en el mismo terminal sin que el contenedor detenga la interacción.

```
docker run -d --name <nombre contenedor> <nombre imagen>:tag
```
Crear y ejecutar inmediatamente el contenedor **srv-web3** en modo detach usando la imagen nginx:alpine

```
docker run -d --name srv-web3 nginx:alpine
```
<img width="526" height="35" alt="image" src="https://github.com/user-attachments/assets/49c5df63-7fe3-40a9-84a8-c404ec737736" />
### Para saber que se esta ejecutando :)
```
docker ps
```
<img width="937" height="112" alt="image" src="https://github.com/user-attachments/assets/e455e1fb-bba3-4ec1-896a-0c9f18548ad3" />


### Para eliminar un contenedor

```
docker rm <nombre contenedor>
```
Eliminar el contenedor que se creó a partir de la imagen hello-world 
```
docker rm dazzling_leavitt
```

Verificar que el contenedor que se eliminó
```
docker ps -a
```
<img width="1040" height="352" alt="image" src="https://github.com/user-attachments/assets/554f7018-1e70-42a8-92e5-448b2422fb1b" />


### Para eliminar un contenedor que esté ejecutándose

```
docker rm -f <nombre contenedor>
```
Eliminar el contenedor **srv-web3** 
```
docker rm -f srv-web3
```

Verificar que el contenedor que se eliminó
<img width="1027" height="311" alt="image" src="https://github.com/user-attachments/assets/1aa4b492-f458-466c-a5c9-1c19c898678f" />


### Para inspecionar un contenedor 

Inspeccionar el contenedor **srv-web** 
```
docker inspect srv-web
```
<img width="1512" height="819" alt="image" src="https://github.com/user-attachments/assets/95009106-eebf-4063-ad2b-3567895d8966" />

