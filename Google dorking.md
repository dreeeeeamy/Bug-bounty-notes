### Google Dorking
**Descripción:** Google Dorking utiliza operadores avanzados de búsqueda en Google para encontrar información específica y potencialmente sensible en dominios objetivo.

**Ejemplos de uso:**

```bash
# Buscar archivos expuestos (PDFs, Docs, Excel, etc.)
site:target.com filetype:pdf
site:target.com filetype:doc
site:target.com filetype:xlsx

# Buscar páginas de inicio de sesión
site:target.com inurl:login
site:target.com inurl:admin
site:target.com intitle:"login"

# Buscar directorios y archivos de configuración
site:target.com intitle:"index of"
site:target.com "parent directory"

# Buscar información de contacto expuesta
site:target.com intext:"email"
site:target.com intext:"phone"

# Buscar contraseñas o datos sensibles
site:target.com intext:"password"
site:target.com intext:"confidential"

# Buscar cámaras expuestas u otros dispositivos IoT (si aplica)
site:target.com inurl:cam
site:target.com inurl:view/view.shtml

# Buscar errores en el servidor
site:target.com "error" | "warning" | "exception"
site:target.com "PHP error" | "404 Not Found"

# Identificar tecnología utilizada en el dominio
site:target.com ext:js
site:target.com ext:xml
site:target.com ext:sql
```
