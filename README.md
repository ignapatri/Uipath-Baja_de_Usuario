# Proceso Baja de usuario del directorio activo

### Diagrama

![Diagrama](https://github.com/ignapatri/Uipath-Baja_de_Usuario/blob/master/imagenes/Diagrama.PNG)

### Proceso
El proceso empieza recibiendo un email en el correo cuyo asunto contiene "baja de usuario", a partir de ahi, movemos correos a carpetas, los leemos, extraemos nombres y fechas
y realizamos todo el procesos de baha en directorio activo

Empezamos con el main en el cual invocamos al InitAllSettings y al InitAllAppApplications
![main](https://github.com/ignapatri/Uipath-Baja_de_Usuario/blob/master/imagenes/Main.jpg)

En InitAllSettings creamos un diccionario de variables y argumentos

![Iniciar settings](https://github.com/ignapatri/Uipath-Baja_de_Usuario/blob/master/imagenes/InitiAllSettings.jpg)

En InitAllAppApplications invocamos varios workflows

![iniciar aplicaciones](https://github.com/ignapatri/Uipath-Baja_de_Usuario/blob/master/imagenes/InitAllAppApplications.jpg)

Busqueda de email

Buscamos en a bandeja de entrada todos los correos en cuyo aunto contenga "baja de usuario y los movemos a una carpeta bajas usuario

![Obtener email](https://github.com/ignapatri/Uipath-Baja_de_Usuario/blob/master/imagenes/getEmail.jpg)

Siguiente paso busquedaEmailBaja

Obtenemos de esa carpeta bajas usuario todos los correos, los recorremos, obtenemos del cuerpo del correo el nombre de usuario y la fecha de baja de usuario
y si la fecha de baja es hoy o superior a hoy llamamos al workflow baja de usuario

![Gestionar email](https://github.com/ignapatri/Uipath-Baja_de_Usuario/blob/master/imagenes/getEmailBaja.jpg)

Baja de usuario

Finalmente buscamos en directorio activo al usuario, si existe se deshabilita el usuario, se le pone la fecha de expiración de cuenta, se elimina al usuario 
de los grupos de directorio activo, se mueve a una OU para eliminarlo y se manda correo al soporte indicando que se ha realizado correctamente,
si no se encuentra el usuario, se manda correo al soporte indicándolo.

![Baja de usuario](https://github.com/ignapatri/Uipath-Baja_de_Usuario/blob/master/imagenes/Busqueda_usuario.jpg)











