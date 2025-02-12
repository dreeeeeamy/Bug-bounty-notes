# Gobuster
## Descripción

Es una herramienta rápida y eficiente para **enumeración de directorios, subdominios y fuzzing de parámetros en aplicaciones web**. Está escrita en **Go**, lo que le proporciona una ejecución optimizada en comparación con otras herramientas similares.

---

## Uso básico

### 1. Descubrimiento de directorios y archivos ocultos
```bash
gobuster dir -u https://example.com -w wordlist.txt
```
*Escanea directorios en el dominio utilizando `wordlist.txt`.*

### 2. Escaneo de subdominios
```bash
gobuster dns -d example.com -w subdomains.txt
```
*Busca subdominios de `example.com` usando `subdomains.txt`.*

### 3. Enumeración de archivos con extensiones específicas
```bash
gobuster dir -u https://example.com -w wordlist.txt -x php,html,js
```
*Incluye búsqueda de archivos con extensiones `.php`, `.html` y `.js`.*

### 4. Uso de cabeceras personalizadas
```bash
gobuster dir -u https://example.com -w wordlist.txt -H "User-Agent: Mozilla/5.0"
```
*Especifica un **User-Agent** personalizado para evitar bloqueos.*

### 5. Filtrado de códigos de respuesta HTTP
```bash
gobuster dir -u https://example.com -w wordlist.txt -b 403,404
```
*Excluye respuestas con código **403 (Prohibido)** y **404 (No encontrado)**.*

### 6. Guardar resultados en un archivo
```bash
gobuster dir -u https://example.com -w wordlist.txt -o resultados.txt
```
*Exporta los resultados en un archivo de texto.*

## Consejos para optimizar resultados
- **Usar listas de palabras adecuadas**: `SecLists` contiene diccionarios optimizados.
- **Ajustar el número de hilos (`-t 50`)**: Controla la velocidad de escaneo.
- **Evitar WAFs con User-Agents personalizados**.
- **Filtrar respuestas irrelevantes (`-b 403,404`)** para reducir el ruido.

