# Contenedores

### Crear un contenedor
Para crear un nuevo contenedor Docker a partir de una imagen específica, pero sin iniciarlo automáticamente. 

```
docker create --name <nombre contenedor> <nombre imagen>:<tag>
```
Crear el contenedor  **srv-web** usando la imagen nginx version alpine
![Srv-web](img/NginxAlpineVer.png)

Si creas un contenedor en Docker sin asignarle un nombre específico utilizando la opción --name, Docker asignará automáticamente un nombre aleatorio al contenedor. Este nombre suele consistir en una combinación de palabras y números.  

Crear el contenedor usando la imagen hello-world
![HelloWorld 3rd](img/HelloWorld3rd.png)

### Listar los contenedores ejecutándose o no

```
docker ps -a
```

### Para iniciar un contenedor

```
docker start <nombre contenedor o identificador>
```
Iniciar el contenedor srv-web 
![Srv Start](img/SrvStart.png)

### Listar los contenedores ejecutándose
```
docker ps 
docker ps | grep <nombre contenedor>
```

### Para detener un contenedor

```
docker stop <nombre contenedor>
```

### Para crear un contenedor y ejecutarlo inmediatamente

```
docker run --name <nombre contenedor> <nombre imagen>:<tag>
```
![Ecosistema de Docker](img/dockerRun.PNG)

Crear y ejecutar inmediatamente el contenedor **srv-web2** usando la imagen nginx:alpine
![Srv-Web 2](img/Srvweb2.png)

**¿Qué sucede luego de la ejecución del comando?**
Empieza una serie de mensajes sobre la ejecución del comando en cuestión y posteriormente empieza procesos de trabajo. Estos procesos se mantienen hasta que se usa el comando CTRL+C para detener la ejecución.

Cuando ejecutas un contenedor en primer plano sin la opción -d (modo detach), el contenedor captura la entrada estándar (stdin) del terminal, lo que significa que el terminal queda "atrapado" y no puedes introducir más comandos hasta que detengas el contenedor.

### Para crear un contenedor y ejecutarlo inmediatamente sin estar vinculados al mismo
-d: Es la opción que indica a Docker que ejecute el contenedor en segundo plano (en modo "detach").
Cuando un contenedor se ejecuta en segundo plano, Docker devuelve el control al terminal inmediatamente después de iniciar el contenedor, lo que permite al usuario seguir ejecutando otros comandos en el mismo terminal sin que el contenedor detenga la interacción.

```
docker run -d --name <nombre contenedor> <nombre imagen>:tag
```
Crear y ejecutar inmediatamente el contenedor **srv-web3** en modo detach usando la imagen nginx:alpine
![Srv-web 3](img/Srvweb3.png)

### Para eliminar un contenedor

```
docker rm <nombre contenedor>
```
Eliminar el contenedor que se creó a partir de la imagen hello-world 
![Rm Hello World](img/dockerRmHW.png)

Verificar que el contenedor que se eliminó
Como se puede ver en la imagen del punto anterior, se ve que no se encuentra en la lista de los contenedores disponibles. Por ende ya se encuentra eliminado.

### Para eliminar un contenedor que esté ejecutándose

```
docker rm -f <nombre contenedor>
```
Eliminar el contenedor **srv-web3** 
![Srv-web 3](img/ServWeb3Rm.png)

Verificar que el contenedor que se eliminó
Igualmente, como se mencionó antes, en el anterior punto se puede apreciar que el Srv-web 3 ya no se encuentra en la lista de los contenedores disponibles. Por ende, se comprueba que ya se encuentra eliminado. 

### Para inspecionar un contenedor 

Inspeccionar el contenedor **srv-web** 

![Inspect Srv-Web](img/inspectSrvweb.png)
