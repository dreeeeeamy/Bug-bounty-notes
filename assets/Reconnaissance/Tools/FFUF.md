# FFUF
## Descripción

Es una herramienta extremadamente rápida y flexible para **fuzzing** de directorios, subdominios, parámetros HTTP y más. Se basa en la ejecución de ataques de fuerza bruta contra aplicaciones web con el objetivo de descubrir **archivos ocultos, directorios, API endpoints, subdominios** o vulnerabilidades de inyección.

---
## Uso básico

### Descubrimiento de directorios ocultos
```bash
ffuf -u https://example.com/FUZZ -w wordlist.txt
```
*Usa `wordlist.txt` para encontrar directorios en el sitio web.*

### Escaneo de subdominios
```bash
ffuf -u https://FUZZ.example.com -w subdomains.txt -H "Host: FUZZ.example.com"
```
*Utiliza una lista de subdominios para encontrar activos adicionales.*

### Fuzzing de parámetros en una URL
```bash
ffuf -u "https://example.com/page.php?FUZZ=test" -w params.txt
```
*Prueba diferentes parámetros en la URL para identificar puntos de inyección.*

### Búsqueda de archivos con extensiones específicas
```bash
ffuf -u https://example.com/FUZZ -w wordlist.txt -e .php,.html,.js
```
*Explora archivos con extensiones `.php`, `.html` y `.js`.*

### Guardar resultados en formato JSON
```bash
ffuf -u https://example.com/FUZZ -w wordlist.txt -o resultados.json -of json
```
*Guarda la salida en un archivo JSON para análisis posterior.*

## Consejos para optimizar resultados
- **Usar diccionarios adecuados**: Para directorios, subdominios o parámetros.
- **Ajustar el número de hilos (`-t`)**: Evita ser bloqueado por WAFs.
- **Utilizar cabeceras personalizadas (`-H`)**: Para evadir restricciones.
- **Filtrar respuestas (`-fc 403,404`)**: Evita ruido en los resultados.
