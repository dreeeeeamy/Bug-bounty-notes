# HTTPX

## Descripción

Es una herramienta rápida y flexible para **sondeo y validación de servicios HTTP**. Es utilizada para descubrir información clave sobre los servidores objetivo.

HTTPX está escrito en **Go**, lo que le permite ejecutarse con gran rendimiento y soporta características avanzadas como **detección de tecnologías, HTTP probing y escaneo masivo de URLs**.

---
## Uso básico

### 1. Escanear un único host
```bash
httpx -u https://example.com
```

### 2. Escanear una lista de dominios
```bash
cat domains.txt | httpx
```

### 3. Detección de tecnologías
```bash
httpx -u https://example.com -tech-detect
```

### 4. Descubrimiento de títulos de páginas web
```bash
httpx -u https://example.com -title
```

### 5. Identificar códigos de respuesta HTTP
```bash
httpx -u https://example.com -status-code
```

### 6. Probar múltiples métodos HTTP
```bash
httpx -u https://example.com -method GET,POST,PUT
```

### 7. Guardar los resultados en un archivo
```bash
httpx -u https://example.com -o results.txt
```

### 8. Filtrado por códigos de respuesta
```bash
cat domains.txt | httpx -mc 200,302
```

## Flujo de exploración con HTTPX
Un flujo común de reconocimiento con HTTPX puede incluir:

1. **Enumerar subdominios y pasar la lista a HTTPX**
```bash
subfinder -d example.com | httpx -title -tech-detect
```
2. **Identificar endpoints expuestos**
```bash
cat urls.txt | httpx -status-code -follow-redirects
```
3. **Filtrar tecnologías específicas**
```bash
cat domains.txt | httpx -tech-detect | grep "Apache"
```

## Consejos para optimizar resultados
- **Usar con `subfinder` o `amass` para ampliar el reconocimiento**.
- **Ajustar la concurrencia (`-t 50`)** para optimizar la velocidad.
- **Filtrar respuestas irrelevantes (`-mc 200,301`)** para reducir el ruido.
- **Ejecutar con proxy (`-proxy http://127.0.0.1:8080`)** para análisis en Burp Suite.
