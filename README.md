
# Taller: Volúmenes y Bind Mounts en Docker

## Ejercicio 1 — Bind mount en modo lectura con Nginx 

1. **Crear una carpeta y un archivo**
    ![Creación de carpeta y archivo](images/bind-mount-1.png)

2. **Levantar Nginx con bind mount de solo lectura**
    ![Levantar Nginx con bind mount](images/bind-mount-2.png)

3. **Abrir `http://localhost:8080` y verificar**
    ![Verificar en localhost:8080](images/bind-mount-3.png)

4. **Editar index.html en el host y recargar el navegador**
    ![Editar index.html](images/bind-mount-4.png)

5. **Intentar crear un archivo dentro del contenedor**
    ![Intento fallido de crear archivo](images/bind-mount-5.png)

---

## Ejercicio 2 — Named volume con PostgreSQL

1. **Crear un volumen**
    ![Creación de volumen](images/postgresql-volume-1.png)

2. **Ejecutar PostgreSQL**
    ![Ejecutar PostgreSQL](images/postgresql-volume-2.png)

3. **Crear tabla y agregar datos**
    ![Crear tabla y agregar datos](images/postgresql-volume-3.png)

4. **Eliminar el contenedor**
    ![Eliminar contenedor](images/postgresql-volume-4.png)

5. **Volver a levantarlo usando el mismo volumen y verificar los datos**
    ![Verificar datos persistentes](images/postgresql-volume-5.png)

---

## Ejercicio 3 — Volumen compartido entre dos contenedores

1. **Crear volumen**
    ![Creación del volumen](images/shared-volume-1.png)

2. **Productor (escribe timestamps cada segundo)**
    ![Correr productor](images/shared-volume-2.png)

3. **Consumidor (lee en tiempo real)**
    ![Correr consumidor](images/shared-volume-3.png)

4. **Reiniciar el productor y revisar que el archivo sigue creciendo**
    ![Revisar crecimiento del archivo](images/shared-volume-4.png)

---

## Ejercicio 4 — Backup y restauración de un volumen

1. **Crear volumen y añadir un archivo**
    ![Crear volumen y archivo](images/backup-volume-1.png)

2. **Hacer backup a un tar en el host**
    ![Hacer backup](images/backup-volume-2.png)

3. **Restaurar en un nuevo volumen**
    ![Restaurar backup](images/backup-volume-3.png)

4. **Verificar el contenido restaurado**
    ![Verificar contenido restaurado](images/backup-volume-4.png)

---

## Reflexión

- **Ejercicio 1:** Se entiende el funcionamiento del Bind mount, observando la relación entre el host y el contenedor.
- **Ejercicio 2:** Se comprueba la persistencia de datos al usar volúmenes con PostgreSQL.
- **Ejercicio 3:** Se verifica que distintos contenedores pueden usar un mismo volumen simultáneamente. Surgió el problema de no poder detener el proceso del consumidor con `Ctrl+C`, que se resuelve usando la flag `--init`. 
- **Ejercicio 4:** Se logra realizar un backup y restauración de datos de un volumen con éxito. 

