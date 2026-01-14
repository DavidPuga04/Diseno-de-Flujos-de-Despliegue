# Diseño de Flujos de Despliegue

## 📖 Descripción del proyecto

Este proyecto corresponde a una aplicación básica desarrollada en **Java** utilizando **Maven** y **Spring Boot**, cuyo objetivo principal es demostrar el **diseño e implementación de flujos de despliegue automatizados** mediante **GitHub Actions** y **Docker**.

El proyecto implementa un pipeline de integración continua que, ante cada cambio enviado a la rama principal (`main`), compila el proyecto, ejecuta pruebas unitarias y de integración, y construye automáticamente una imagen Docker para validar el proceso de despliegue.

---

## Integrantes

- Mateo Coronel  
- Anthonny Mosquera  
- David Puga  

---

## 🔗 Repositorio GitHub

https://github.com/DavidPuga04/Diseno-de-Flujos-de-Despliegue.git

---

## ⚙️ Tecnologías utilizadas

- Java 17  
- Maven  
- Spring Boot  
- JUnit 5  
- GitHub Actions  
- Docker  
- Eclipse Temurin JRE 17

---

## ▶️ Funcionamiento del proyecto

- La aplicación contiene una clase principal que se ejecuta desde consola.
- Maven se encarga de la compilación, ejecución de pruebas y empaquetado del proyecto.
- Se implementan:
  - **Pruebas unitarias** (`SimpleTest`)
  - **Pruebas de integración** (`ContextIT`)
- El proyecto está preparado para ser ejecutado dentro de un contenedor Docker.
- GitHub Actions automatiza todo el flujo de construcción y validación.

---

## 🧪 Pruebas implementadas

Durante el proceso de construcción se ejecutan automáticamente:

- **Test unitario:** `SimpleTest`
- **Test de integración:** `ContextIT`

Ambos tests se ejecutan correctamente utilizando el comando:

```bash
 mvn clean verify
```

---

## 🚀 Ejecución del proyecto
1️⃣ Requisitos previos

- Java 17

- Maven

- Docker

2️⃣ Compilar y verificar el proyecto

Desde la raíz del proyecto:

```bash
 mvn clean verify
```

Este comando:

- Compila el proyecto

- Ejecuta los tests unitarios

- Ejecuta los tests de integración

- Genera el archivo .jar

3️⃣ Ejecución local sin Docker
```bash
java -jar target/myapp-0.0.1-SNAPSHOT.jar
```

🐳 Docker
Construcción de la imagen Docker
```bash
docker build -t myapp .
```

Ejecución del contenedor
```bash
docker run myapp
```
---

## 🔄 GitHub Actions – Flujo de Despliegue

El proyecto utiliza GitHub Actions para automatizar el proceso de integración continua.

📌 Funcionamiento del pipeline

Cada vez que se realiza un push a la rama main, GitHub Actions ejecuta automáticamente un pipeline que:

1.- Descarga el repositorio

2.- Compila el proyecto con Maven

3.- Ejecuta pruebas unitarias

4.- Ejecuta pruebas de integración

5.- Construye una imagen Docker del proyecto

Este proceso permite validar que la aplicación:

- Compila correctamente

- Supera todas las pruebas

- Puede ser empaquetada en un contenedor Docker listo para despliegue

📌 **Nota importante:**
La imagen Docker se construye automáticamente en GitHub Actions únicamente con fines de validación.
El runner utilizado es temporal, por lo que la imagen no se persiste, pero los logs confirman que la imagen se genera exitosamente.
