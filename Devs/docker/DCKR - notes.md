#### **Reinicia los contenedores**

Después de aplicar estos cambios, intenta nuevamente levantar los contenedores:

`docker-compose up -d`
#### **Limpia los contenedores e imágenes actuales**

Para evitar conflictos, limpia cualquier intento previo de creación de contenedores o imágenes descargadas con problemas:

`docker-compose down --rmi all --volumes --remove-orphans`