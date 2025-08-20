# Foro Estudiantes - API REST

Este proyecto es un **foro para estudiantes** desarrollado en **Java 17**, **Spring Boot 3** y **Maven**.  
Permite a los estudiantes registrarse, crear publicaciones y comentar en ellas.

## 🚀 Tecnologías
- Java 17
- Spring Boot 3 (Web, Data JPA, Validation)
- MySQL
- Lombok
- Springdoc OpenAPI (Swagger UI)

## 📂 Estructura principal
```
src/main/java/com/foroestudiantes/
├── controller/   # Controladores REST
├── dto/          # Objetos de transferencia de datos (DTOs)
├── model/        # Entidades JPA
├── repository/   # Repositorios Spring Data JPA
├── service/      # Lógica de negocio
└── ForoEstudiantesApplication.java
```

## ⚙️ Configuración

En `src/main/resources/application.properties` debes configurar tu conexión a MySQL:

```properties
spring.datasource.url=jdbc:mysql://localhost:3306/foro_estudiantes?useSSL=false&serverTimezone=UTC
spring.datasource.username=TU_USUARIO
spring.datasource.password=TU_PASSWORD

spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.MySQL8Dialect
server.port=8080
```

Luego, crea la base de datos en MySQL:

```sql
CREATE DATABASE foro_estudiantes;
```

## ▶️ Ejecución

1. Compila y empaqueta con Maven:
   ```bash
   mvn clean install
   ```

2. Ejecuta la aplicación:
   ```bash
   mvn spring-boot:run
   ```

La API se levantará en: [http://localhost:8080](http://localhost:8080)

Accede a la documentación Swagger en: [http://localhost:8080/swagger-ui.html](http://localhost:8080/swagger-ui.html)

## 📌 Endpoints principales

### Estudiantes
- `POST /api/estudiantes` → Crear estudiante
- `GET /api/estudiantes` → Listar estudiantes

### Posts
- `POST /api/posts` → Crear post (requiere `estudianteId`)
- `GET /api/posts` → Listar posts
- `GET /api/posts/{id}` → Obtener post por ID

### Comentarios
- `POST /api/posts/{postId}/comentarios` → Crear comentario en un post
- `GET /api/posts/{postId}/comentarios` → Listar comentarios de un post

## ✅ Mejoras futuras
- Autenticación y autorización con **Spring Security + JWT**
- Paginación y filtros en listados
- Tests unitarios e integración

---

👨‍💻 Desarrollado como ejemplo de API REST con Spring Boot.
