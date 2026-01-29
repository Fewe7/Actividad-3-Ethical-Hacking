# Actividad-3-Ethical-Hacking

# Desglose Completo del Proyecto

## Práctica de Explotación y Mitigación de SQL Injection con DVWA

---

## 1. Recursos Humanos

Para la correcta ejecución del proyecto se requieren uno o más participantes con roles bien definidos. En un contexto académico, una sola persona puede cubrir todos los roles; sin embargo, conceptualmente se identifican los siguientes:

### 1.1 Estudiante / Analista de Seguridad

* Responsable de la configuración del entorno.
* Ejecutor de las pruebas de ataque.
* Documentador de evidencias.
* Analista de resultados desde la perspectiva ofensiva (Red Team) y defensiva (Blue Team).

### 1.2 Instructor o Evaluador (opcional)

* Define los criterios de evaluación.
* Supervisa la correcta ejecución ética del ejercicio.
* Valida la documentación y conclusiones.

---

## 2. Recursos de Hardware

### 2.1 Equipo de Cómputo Principal

**Requisitos mínimos recomendados:**

* Procesador: Intel i5 / AMD Ryzen 5 o superior.
* Memoria RAM: 8 GB mínimo (16 GB recomendado).
* Almacenamiento: 30 GB libres en disco.
* Arquitectura: 64 bits.

**Justificación:**
Docker ejecuta múltiples contenedores simultáneamente, por lo que se requiere suficiente memoria y capacidad de procesamiento para evitar fallos de rendimiento.

---

## 3. Recursos de Software

### 3.1 Sistema Operativo Anfitrión

Cualquiera de los siguientes:

* Windows 10 / 11
* GNU/Linux (Ubuntu, Debian, Fedora)
* macOS

Debe contar con privilegios de administrador.

---

### 3.2 Docker

**Componentes necesarios:**

* Docker Engine
* Docker Compose

**Función dentro del proyecto:**

* Crear entornos aislados y reproducibles.
* Ejecutar DVWA y Kali Linux sin necesidad de máquinas virtuales completas.

---

### 3.3 Contenedor DVWA (Víctima)

**Componentes incluidos:**

* Servidor web (Apache).
* PHP.
* Base de datos MySQL/MariaDB.

**Función:**

* Proveer una aplicación web intencionalmente vulnerable para prácticas de seguridad.

---

### 3.4 Contenedor Kali Linux (Atacante)

**Herramientas principales requeridas:**

* sqlmap
* ping
* curl / wget (opcional)
* Navegador web (opcional)

**Función:**

* Ejecutar pruebas de reconocimiento y explotación.

---

### 3.5 Navegador Web

**Ejemplos:**

* Google Chrome
* Mozilla Firefox

**Función:**

* Acceder a DVWA.
* Utilizar herramientas de desarrollador (F12) para inspección de cookies, sesiones y peticiones HTTP.

---

## 4. Recursos de Red

### 4.1 Red Docker Interna

* Red bridge creada automáticamente por Docker Compose.
* Permite comunicación directa entre contenedores.

### 4.2 Direccionamiento IP

* IP asignada automáticamente a cada contenedor.
* Necesaria para pruebas de conectividad (ping) y ataques.

---

## 5. Archivos y Configuración

### 5.1 Archivo docker-compose.yml

**Debe definir:**

* Servicios DVWA y Kali.
* Puertos expuestos.
* Red compartida.
* Variables de entorno.

**Importancia:**
Es el archivo central del proyecto; sin él, el entorno no puede desplegarse.

---

### 5.2 Configuración de DVWA

* Nivel de seguridad configurado en "Low".
* Base de datos inicializada correctamente.
* Sesión de usuario activa.

---

## 6. Procedimientos Técnicos Necesarios

### 6.1 Preparación del Entorno

* Instalación de Docker.
* Descarga de imágenes necesarias.
* Ejecución de `docker-compose up -d`.

### 6.2 Verificación del Entorno

* Confirmar contenedores en estado *running*.
* Acceso exitoso a DVWA desde el navegador.

---

## 7. Procedimientos de Ataque (Red Team)

### 7.1 Reconocimiento

* Identificación de la IP de la víctima.
* Pruebas de conectividad con `ping`.

### 7.2 Obtención de Sesión

* Inspección de cookies (`PHPSESSID`).
* Confirmación del nivel de seguridad.

### 7.3 Explotación

* Ejecución de sqlmap.
* Identificación de bases de datos.
* Volcado de tablas y datos sensibles.

---

## 8. Procedimientos de Análisis (Blue Team)

### 8.1 Identificación de la Vulnerabilidad

* Análisis de entradas sin validación.
* Detección de consultas SQL dinámicas.

### 8.2 Evaluación del Impacto

* Exposición de datos sensibles.
* Compromiso de integridad y confidencialidad.

---

## 9. Evidencias Requeridas

### 9.1 Evidencia 1 – Preparación

* Captura del comando `docker-compose up -d`.

### 9.2 Evidencia 2 – Configuración

* DVWA en nivel "Low".
* Cookie `PHPSESSID` visible.

### 9.3 Evidencia 3 – Conexión

* Ping exitoso desde Kali.

### 9.4 Evidencia 4 – Explotación

* Resultado final de sqlmap con dump.

---

## 10. Documentación del Proyecto

### 10.1 Manual Técnico

* Descripción paso a paso.
* Evidencias visuales.

### 10.2 Análisis y Reflexión

* Perspectiva Red Team y Blue Team.
* Propuesta de mitigación.

---

## 11. Seguridad y Ética

* El entorno debe ejecutarse únicamente en laboratorios controlados.
* No se deben realizar pruebas en sistemas reales sin autorización.
* Uso estrictamente académico.

---

## 12. Entregables Finales

* Manual en formato PDF.
* Evidencias gráficas.
* Apartado de mitigación de vulnerabilidades.

---

## 13. Conclusión del Desglose

Este desglose detalla todos los recursos, configuraciones y procedimientos necesarios para llevar a cabo el proyecto de forma correcta, ordenada y ética, garantizando tanto el aprendizaje técnico como la comprensión de la importancia de la seguridad defensiva.

---

**Fin del desglose del proyecto**
