# Backend - Herkat

Este es el backend del proyecto **Herkat**, desarrollado con **Spring Boot (Java 17)** y **PostgreSQL**.

---

## ✅ Requisitos Previos

| Herramienta           | Versión recomendada | Descarga                                                       |
|-----------------------|---------------------|----------------------------------------------------------------|
| Java                  | 17                  | https://www.oracle.com/java/technologies/javase-downloads.html |
| PostgreSQL            | 14+                 | https://www.postgresql.org/download/                           |
| Postman (para probar) | —                   | https://www.postman.com/downloads/                             |
| DBeaver (opcional)    | —                   | https://dbeaver.io/download/                                   |

---

## 🗄️ Base de Datos

Antes de ejecutar, crear una base de datos vacía en PostgreSQL:

```sql
CREATE DATABASE herkatdb;
```
> La estructura de tablas se generará automáticamente cuando el proyecto se ejecute por primera vez (gracias a `spring.jpa.hibernate.ddl-auto=update`).

---

## 🔐 Variables de Entorno

En la raíz del proyecto, verifique si existe un archivo `.env` con la siguiente variable (sino, por favor crearla):

```sql
{CLOUDINARY_URL}
```

*Esta variable permite subir imágenes a Cloudinary.*

---

## ⚙️ Configuración del `application.properties`

El proyecto ya incluye configuración para ejecutar localmente:

```md
spring.datasource.url=jdbc:postgresql://localhost:5432/herkatdb
spring.datasource.username=postgres
spring.datasource.password=SU_CONTRASEÑA_LOCAL
```

> Si su usuario o contraseña son distintos, favor ajustarlos.

---

## ▶️ Cómo Ejecutar el Backend

Abrir la terminal CMD dentro de la carpeta `herkat` y ejecutar:

```cmd
mvnw.cmd spring-boot:run
```

Cuando el backend esté ejecutándose correctamente, verá algo parecido a:

```
Started HerkatApplication in X.XXX seconds
Tomcat started on port(s): 8080
```

---

## 🧪 Pruebas de API (IMPORTANTE)

No usar Swagger para probar este backend (Swagger falla con imágenes multipart).
Usar Postman.

### Ejemplo de subida de imagen:

```
POST http://localhost:8080/api/v1/banners
```

**Body → form-data**

| Clave  | Tipo | Valor                 |
|--------| ---- | --------------------- |
| name   | Text | (Según corresponda)   |
| imagen | File | (Seleccionar archivo) |

---

## 🚀 Listo

El backend queda ejecutándose localmente y listo para usar con el frontend.

---
