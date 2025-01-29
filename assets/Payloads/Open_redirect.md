# Open Redirect

## Descripción

La vulnerabilidad de **Open Redirect** ocurre cuando una aplicación redirige a los usuarios a URLs externas sin validar adecuadamente el destino. Esto puede ser explotado por atacantes para realizar ataques de phishing, robo de credenciales o redirecciones maliciosas.

Un atacante podría engañar a las víctimas para que accedan a enlaces aparentemente legítimos pero que los redirigen a sitios controlados por ellos.

---

## Dónde buscar Open Redirect

### Endpoints comunes
- **Páginas de autenticación** (`/login?redirect=URL`).
- **Confirmación de acciones** (`/confirm?next=URL`).
- **Sistemas de pago o checkout** (`/checkout?return=URL`).
- **Errores o logout** (`/logout?next=URL`).
- **Sistemas de soporte o contacto** (`/support?redirect=URL`).

### Cabeceras HTTP
- **Referer**: Puede incluir URLs externas manipuladas.
- **Location**: En respuestas HTTP que usan `302 Found` o `301 Moved Permanently`.

### Formularios y datos del usuario
- **Inputs ocultos** en formularios de login o confirmaciones de compra.
- **JSON o XML**: Datos estructurados que pueden contener URLs manipuladas.

---

## Payloads comunes

### Básicos
```bash
https://malicious.com
//malicious.com
```

### Codificados
```bash
%68%74%74%70%73%3A%2F%2F%6D%61%6C%69%63%69%6F%75%73%2E%63%6F%6D
```

### Redirecciones en protocolos alternativos
```bash
data:text/html;base64,PHNjcmlwdD5hbGVydCgnSGFja2VkIScpPC9zY3JpcHQ+
```

### ByPass con subdominios
```bash
https://trusted.com@malicious.com
```
