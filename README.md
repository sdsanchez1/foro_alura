
# API Foro Alura

<p align="center" > 
  <img src="https://img.shields.io/badge/Java%20JDK-v.17-green"/>
  <img src="https://img.shields.io/badge/Spiring%20Boot-v.3-yellow"/>
  <img src="https://img.shields.io/badge/MySQL-v.8.0.33-blue"/>
</p>

## Tabla de Contenido

- [Descripción del proyecto](#descripcion-del-proyecto)
- [Estado del proyecto](#estado-del-proyecto)
- [Funcionalidades](#funcionalidades)
    - [Usuario](#usuario)
		- [Registrar](#registrar)
		- [Actualizar](#actualizar)
		- [Eliminar](#eliminar)
	- [Autenticacion](#autenticacion)
		- [Login](#login)
	- [Cursos](#cursos)
		- [Registrar](#registrar)
		- [Actualizar](#actualizar)
		- [Eliminar](#eliminar)
	- [Topico](#topico)
		- [Registrar](#registrar)
		- [Listar](#listar)
		- [Listar con respuestas](#listar-con-respuestas)
		- [Actualizar](#actualizar)
		- [Eliminar](#eliminar)
	- [Respuesta](#respuesta)
		- [Registrar](#registrar)
		- [Actualizar](#actualizar)
		- [Eliminar](#eliminar)
- [Acceso al proyecto](#acceso-al-proyecto)
- [Tecnologías utilizadas](#tecnologias-utilizadas)
- [Dependencias utilizadas](#dependencias-utilizadas)
- [Documentacion](#documentacion)
- [Pruebas a la API](#pruebas-a-la-api)

## Descripcion del proyecto

El foro alura es un proyecto enfocado a compartir experiencias con los demás estudias y colocar preguntas sobre ciertos temas

## Estado del proyecto

   ![Badge en Desarollo](https://img.shields.io/badge/ESTADO-FINALIZADO-green)


## Funcionalidades

### Autenticacion

#### Login

```bash
[POST] https://localhost:8080/login
```

```json
{
  "username": "string",
  "password": "string"
}
```

### Usuario

#### Registrar

```bash
[POST] https://localhost:8080/users
```

```json
{
  "name": "string",
  "email": "string",
  "username": "string",
  "password": "string"
}
```

#### Actualizar

Los unicos que pueden actualizar los datos de un usuario son el dueño de la cuenta y el adminstrador del sistema.

```bash
[PUT] https://localhost:8080/users
```

```json
{
  "id": 0,
  "name": "string",
  "email": "string",
  "username": "string",
  "password": "string"
}
```

#### Eliminar

Los unicos que pueden eliminar un usuario son el dueño de la cuenta y el adminstrador del sistema.

```bash
[DELETE] https://localhost:8080/users/{id}
```

### Curso

El unico que tiene permitido registrar, actualizar y eliminar los cursos es el administrador del sistema.


#### Registrar

```bash
[POST] https://localhost:8080/courses
```

```json
{
  "name": "string",
  "category": "string"
}
```

#### Actualizar

```bash
[PUT] https://localhost:8080/courses
```

```json
{
  "id": 0,
  "name": "string",
  "category": "string"
}
```

#### Eliminar

```bash
[DELETE] https://localhost:8080/courses/{id}
```

### Topico

#### Registrar

```bash
[POST] https://localhost:8080/topics
```

```json
{
  "title": "string",
  "message": "string",
  "idAuthor": 0,
  "idCourse": 0
}
```

#### Listar

Retorna el siguiente formato

```bash
[GET] https://localhost:8080/topics
```

```json
{
      "id": 0,
      "title": "string",
      "message": "string",
      "creatioDate": "LocalDateTime",
      "status": "string",
      "author": "string",
      "course": "string"
    },
	{
      "id": 0,
      "title": "string",
      "message": "string",
      "creationDate": "LocalDateTime",
      "status": "string",
      "author": "string",
      "course": "string"
    }
```

#### Listar con respuestas

Retorna el siguiente formato

```bash
[GET] https://localhost:8080/topics{id}
```

```json
{
  "id": 0,
  "title": "string",
  "message": "string",
  "creationDate": "LocalDateTime",
  "status": "string",
  "author": "string",
  "course": "string",
  "response": [
    {
      "id": 0,
      "message": "string",
      "creationDate": "LocalDateTime",
      "author": "string",
      "solution": false
    },
	{
      "id": 0,
      "message": "string",
      "creationDate": "LocalDateTime",
      "author": "string",
      "solution": false
    }
  ]
}

```

#### Actualizar

Los unicos que pueden actualizar la información de un topico son el creador y el administrador del sistema.

```bash
[PUT] https://localhost:8080/topics
```

```json
{
  "id": 0,
  "title": "string",
  "message": "string",
  "status": "string",
  "idCourse": 0
}
```

#### Eliminar

Los unicos que pueden eliminar un topico son el creador y el administrador del sistema.

```bash
[DELETE] https://localhost:8080/topics/{id}
```

### Respuesta

#### Registrar

```bash
[POST] https://localhost:8080/responses
```

```json
{
  "message": "string",
  "idTopic": 0,
  "idAuthor": 0
}
```

#### Actualizar

Los unicos que pueden actualizar la información de una respuesta son el creador y el administrador del sistema.

```bash
[PUT] https://localhost:8080/responses
```

```json
{
  "id": 0,
  "message": "string"
}
```

#### Eliminar

Los unicos que pueden eliminar una respuesta son el creador y el administrador del sistema.

```bash
[DELETE] https://localhost:8080/responses/{id}
```

## Acceso al proyecto

1. Descargar la versión 17 de [Java JDK.](https://www.oracle.com/java/technologies/javase/jdk17-archive-downloads.html)

2. Descargar el IDE [IntelliJ IDEA Community.](https://www.jetbrains.com/idea/download/)

3. Descargar [MySQL.](https://dev.mysql.com/downloads/installer/)

4. Descargar [MySQL Workbench.](https://dev.mysql.com/downloads/workbench/)

5. Clonar el repositoria mediante el siguiente enlace: https://github.com/juanturriago7/challenge-one-foro-alura.git

6. Abrir MySQL Workbench y crear base de datos con el siguiente nombre:

```bash
CREATE DATABASE foro_alura;
```

7. Abrir el proyecto en el IDE IntelliJ IDEA Community.

8. Ajustes dentro del proyecto ir a la carpeta **resources** y en **application.properties ** modificar los campos **spring.datasource.username** y **spring.datasource.password** con sus respectivos datos de MySQL en su ordenador.


## Tecnologias utilizadas

* Java 17

* Spring Boot 3

* MySQL

## Dependencias utilizadas

*  `Spring Web`

* `Spring Boot DevTools`

* `Lombok`

* `Spring Security`

* `Hibernate`

* `Spring Data JPA`

*  `Flyway Migration`

*  `JSON Wen Token`

* `MySQL Driver`

* `JPA`

* `Validation`

* `Spring Doc`


## Documentacion

1. Una vez ejecutador el proyecto se puede acceder a la documentacion mediante el siguiente enlace: 

```bash
http://localhost:8080/swagger-ui/index.html
```

## Pruebas a la API

1. Archivo configurado de insomia, descargar e importar en su entorno local:

2. Disfrute las prubas

*   Clic para descargar el [**Archivo**](https://drive.google.com/drive/folders/1BSyhJq-C-yrH7lfrtz65GtsbBDWt2S-F?usp=sharing)

