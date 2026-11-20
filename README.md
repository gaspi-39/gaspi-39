<div align="center">

# Gaspar Lazarte

![Typing](https://readme-typing-svg.demolab.com?font=Fira+Code&size=17&duration=3500&pause=1200&color=7EE787&width=560&lines=Backend+developer+%7C+Java+21+%2B+Spring+Boot;Arquitectura+as%C3%ADncrona+%7C+RabbitMQ;ORM+desde+cero+%7C+Open+source)

Desarrollador backend en formación · Estudiante de Analista Programador · En búsqueda de mi primera experiencia profesional

[![GitHub stats](https://github-readme-stats.vercel.app/api?username=gaspi-39&show_icons=true&theme=tokyonight&include_all_commits=true&count_private=false)](https://github.com/gaspi-39)
[![Top languages](https://github-readme-stats.vercel.app/api/top-langs/?username=gaspi-39&layout=compact&theme=tokyonight)](https://github.com/gaspi-39)

</div>

---

## 👋 Sobre mí

Me especializo en desarrollo backend con **Java y Spring Boot**, con foco en arquitectura asíncrona, persistencia y diseño de APIs. Actualmente consolido bases sólidas mientras aprendo a trabajar en equipo y a aplicar buenas prácticas: pruebas, reflexión y entender el _por qué_ detrás de cada herramienta.

Prefiero construir desde cero para comprender cómo funcionan las cosas: de ahí salió mi mini ORM. Hoy canalizo eso en sistemas con colas, reintentos y estados persistentes, y aporto a proyectos open source del ecosistema Java.

---

## 🧰 Stack

> Hacé click en cada categoría para ver las tecnologías (pasá el mouse por cada icono).

<details>
<summary><b>☕ Backend</b></summary>
<br>

<img src="https://img.shields.io/badge/Java%2021-007396?style=flat-square&logo=openjdk&logoColor=white" title="Java 21 — lenguaje principal" alt="Java 21">
<img src="https://img.shields.io/badge/Spring%20Boot-6DB33F?style=flat-square&logo=springboot&logoColor=white" title="Spring Boot 3.5" alt="Spring Boot">
<img src="https://img.shields.io/badge/Node.js-339933?style=flat-square&logo=node.js&logoColor=white" title="Node.js" alt="Node.js">
<img src="https://img.shields.io/badge/Express-000000?style=flat-square&logo=express&logoColor=white" title="Express" alt="Express">
<img src="https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white" title="TypeScript" alt="TypeScript">
<img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black" title="JavaScript" alt="JavaScript">

</details>

<details>
<summary><b>🗄️ Datos y mensajería</b></summary>
<br>

<img src="https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white" title="PostgreSQL" alt="PostgreSQL">
<img src="https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white" title="MySQL" alt="MySQL">
<img src="https://img.shields.io/badge/SQLite-003B57?style=flat-square&logo=sqlite&logoColor=white" title="SQLite" alt="SQLite">
<img src="https://img.shields.io/badge/RabbitMQ-FF6600?style=flat-square&logo=rabbitmq&logoColor=white" title="RabbitMQ — colas, DLX y delayed exchange" alt="RabbitMQ">

</details>

<details>
<summary><b>🛠️ Herramientas y prácticas</b></summary>
<br>

<img src="https://img.shields.io/badge/Maven-C71A36?style=flat-square&logo=apachemaven&logoColor=white" title="Maven" alt="Maven">
<img src="https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white" title="Docker y Docker Compose" alt="Docker">
<img src="https://img.shields.io/badge/JUnit-25A162?style=flat-square&logo=junit5&logoColor=white" title="JUnit — tests unitarios" alt="JUnit">
<img src="https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white" title="Git y pull requests" alt="Git">
<img src="https://img.shields.io/badge/Markdown-000000?style=flat-square&logo=markdown&logoColor=white" title="Markdown" alt="Markdown">

</details>

---

## 🚀 Proyectos recientes

### 🧵 Async Task Processor — [queue-task-processor](https://github.com/gaspi-39/queue-task-processor)

API que recibe tareas pesadas, las encola y las procesa con workers en background. El cliente recibe `202 Accepted` con un id y consulta el estado después.

- **Java 21 + Spring Boot 3.5**, PostgreSQL y RabbitMQ levantados con Docker Compose.
- El mensaje de la cola lleva solo el `id`: el payload vive en Postgres, así el estado es consultable aunque el worker esté caído.
- **Reintentos con backoff exponencial** (`2^intentos * 10s`) mediante TTL + Dead Letter Exchange. Agotados los reintentos, la tarea queda en `FAILED` con su error y se publica en `task.dlq`.
- **Prioridades** (`x-max-priority=10`) y **tareas programadas** con exchange `x-delayed-message` + header `x-delay`.
- Tareas periódicas con `@Scheduled`, configurables por `task.periodic.cron`.

[Ver código](https://github.com/gaspi-39/queue-task-processor) · [Arquitectura y ejemplos](https://github.com/gaspi-39/queue-task-processor#readme)

### 🗃️ mini-orm — [mini-orm](https://github.com/gaspi-39/mini-orm)

ORM escrito desde cero para entender cómo funciona Hibernate y afianzar programación orientada a objetos.

- Anotaciones propias (`@Table`, `@Id`, `@Column`) y mapeo reflexivo de filas a entidades (`EntityMapper`).
- `Repository<T>` genérico y `ReflectiveRepository` con operaciones CRUD.
- `ConnectionFactory` y suite de tests unitarios con JUnit.

[Ver código](https://github.com/gaspi-39/mini-orm)

### 🤝 Contribuciones open source — [JVM-MCP](https://github.com/oscarbol09/jvm-mcp)

Servidor MCP en Java 21 que expone memoria, threads, beans de Spring y pools HikariCP en vivo mediante Attach API, sin modificar la aplicación destino.

- [PR #295](https://github.com/oscarbol09/jvm-mcp/pull/295) mergeado: fix de timeout e interrupción del worker en la herramienta `tools`.
- [PR #237](https://github.com/oscarbol09/jvm-mcp/pull/237) mergeado: explicar correctamente un pool HikariCP vacío cuando faltan MBeans.
- Participación en issues y revisión de cambios del upstream.

[Fork Personal](https://github.com/gaspi-39/jvm-mcp) · [Upstream](https://github.com/oscarbol09/jvm-mcp)

---

## 📈 Estado actual

- [x] API REST con persistencia y lógica de negocio
- [x] Worker asíncrono con colas, reintentos y DLQ
- [x] ORM propio con reflexión y tests
- [x] Primeros PRs mergeados en open source
- [ ] Documentar decisiones de arquitectura del procesador de tareas
- [ ] Sumar tests de integración con Testcontainers

<details>
<summary>🕹️ Otros proyectos</summary>
<br>

- [impostor](https://github.com/gaspi-39/impostor) — API para jugar al impostor con amigos.
- [booking-system](https://github.com/gaspi-39/booking-system) — sistema de gestión de reservas.
- [veterinaria-api](https://github.com/gaspi-39/veterinaria-api) — API REST para una clínica veterinaria.
- [sistema-numerico](https://github.com/gaspi-39/sistema-numerico) — operaciones con cadenas numéricas usando POO en PHP.
- [iglesia-live](https://github.com/gaspi-39/iglesia-live) — monitor web de secuencias en Lua.

</details>

---

<div align="center">

### 📫 Contacto

<a href="mailto:lazartegaspar@gmail.com"><img src="https://img.shields.io/badge/Email-lazartegaspar%40gmail.com-EA4335?style=flat-square&logo=gmail&logoColor=white" alt="Email"></a>
<a href="https://www.linkedin.com/in/gasparlazarte/"><img src="https://img.shields.io/badge/LinkedIn-gasparlazarte-0A66C2?style=flat-square&logo=linkedin&logoColor=white" alt="LinkedIn"></a>
<a href="https://github.com/gaspi-39"><img src="https://img.shields.io/badge/GitHub-gaspi--39-181717?style=flat-square&logo=github&logoColor=white" alt="GitHub"></a>

[![Streak](https://streak-stats.demolab.com/?user=gaspi-39&theme=tokyonight&hide_border=true)](https://github.com/gaspi-39)

</div>
