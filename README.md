#Requerimientos

## Creación y gestión de instancias EC2 (3 puntos)
Crear una instancia EC2 en AWS usando GitHub Actions.
El flujo de trabajo debe incluir la creación de la instancia, la configuración de los parámetros básicos y su inicio.

Se creo la instancia mediante github actions

## 2.Tipos de instancias y casos de uso (2 puntos)
Definir el tipo de instancia que se utilizará (por ejemplo, t2.micro, t3.medium,
etc.) y justificar la elección según el caso de uso propuesto

Tipo seleccionado: t2.micro
Razón:
Ahorro de costos, ya que está cubierta por el nivel gratuito.
Ideal para tareas de desarrollo o prueba con bajo uso de recursos.
Es la que aprendimos a usar en clases.



Justificaciones para eleccion de opciones:

## Tipo de instancia
- **Tipo seleccionado**: `t2.micro`
- **Razón**: 
  - Ahorro de costos, ya que está cubierta por el nivel gratuito.
  - Ideal para tareas de desarrollo o prueba con bajo uso de recursos.

## 3. Seguridad y acceso (2 puntos)
Configurar un grupo de seguridad para la instancia EC2, asegurando que solo se permita el acceso SSH a través de una clave privada.
Asegurarse de que la clave SSH sea correctamente generada y gestionada en el flujo de trabajo de GitHub Actions.

Esta ok, ya que se puede revisar que funciona con el SSH que esta en los secretos.

Está configurado en el puerto 22 con SSH, la ip esta en 0.0.0.0/0 ya que como el despliegue sse hace desde github no es una ip que yo controle, pero si quisiéramos tener acceso desde mi propia ip basta con cambiar el campo source y poner myip.

La clave está guardada como un secreto en github con el nombre de EC2_SSH_PRIVATE_KEY y dentro de ese secreto esta el valor y por ende github action la puede usar

## 4. Configuración de redes y VPC (1 punto)
Asegurarse de que la instancia EC2 esté lanzada dentro de una VPC adecuada y de que la configuración de subredes y rutas sea correcta.

Funciona y se uso la VPC por defecto de aws en mi cuenta, no era necesario crear otra segun los requirimientos.

## 5 .Uso de AMIs personalizadas (2 puntos)
Crear una imagen de máquina de Amazon (AMI) personalizada basada en la instancia EC2 creada, asegurando que pueda ser utilizada para lanzar nuevas instancias con configuraciones similares en el futuro.

Cada vez que creó una AMIi me aseguro que el nombre tome la fecha para no tener problemas con los nombres repetidos y se crean en función de EC2 levantada anteriormente.

