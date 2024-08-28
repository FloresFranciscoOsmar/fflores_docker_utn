# fflores_docker_utn

## Sobre el proyecto
  

Este proyecto configura y despliega un entorno con dos instancias de Nginx y un load balancer con Docker y Docker Compose, utilizando algunos conocimientos adquiridos en el curso.
Elegí esta tecnología porque me estoy familiarizando con nginx ya que por mi puesto (sysadmin), me gustaría aprender esta tecnología y la versatilidad de usos de la misma.


### Requisitos

  
1. Docker 
2. Docker compose
3. Puertos 8080, 8081 y 8082 libres en la máquina local

## Iniciando el proyecto

  La forma de inicializar el proyecto es ejecutando esta serie de instrucciones
1. Construimos la imagen de Docker ubicando nuestra terminal en donde está este repositorio.
   docker buildx build -t fflores-nginx-alpine .
   Bindeando/asignando así el nombre "fflores-nginx-alpine" a nuestra imagen que construimos con el flag -t
2. Ejecutamos el docker compose, en el mismo directorio que el paso anterior ejecuamos lo siguiente
   docker compose up -d
   El flag -d es para que se ejecute en segundo plano en lugar de consumir la terminal.

## Puertos y consideraciones

#### Puertos utilizados y archivos de configuración
nginxsrv1:
	puerto expuesto: 80
	puerto máquina local utilizado: 8081
	archivo de configuración: nginxsrv1.conf
nginxsrv2:
	puerto expuesto: 80
	puerto máquina local utilizado: 8082
	archivo de configuración: nginxsrv2.conf
load_balancer:
	puerto expuesto: 80
	puerto máquina local utilizado: 8080
	archivo de configuración: load_balancer.conf

El funcionamiento de los archivos de configuración están comentados explicando su funcionamiento