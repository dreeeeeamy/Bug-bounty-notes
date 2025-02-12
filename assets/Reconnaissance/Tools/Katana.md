# Katana

## Descripción

Es un rastreador web (crawler) de alto rendimiento desarrollado por **ProjectDiscovery**. Se utiliza para **enumerar URLs, descubrir endpoints ocultos y extraer enlaces dinámicos** en aplicaciones web.

Katana está diseñado para ser **rápido, flexible y escalable**, permitiendo su integración con otras herramientas de reconocimiento y explotación, como **Nuclei, HTTPX y Subfinder**.

---

## Uso básico

### 1. Escanear una URL
```bash
katana -u https://example.com
```

### 2. Escanear múltiples dominios desde un archivo
```bash
katana -list domains.txt
```

### 3. Extraer URLs desde archivos JavaScript
```bash
katana -u https://example.com -js
```

### 4. Guardar resultados en un archivo
```bash
katana -u https://example.com -o results.txt
```

### 5. Integración con HTTPX para validación de URLs
```bash
katana -u https://example.com | httpx -status-code
```

### 6. Rastrear en profundidad con múltiples niveles
```bash
katana -u https://example.com -depth 3
```

## Consejos para optimizar resultados
- **Usar con `httpx` para validar URLs activas**.
- **Ajustar la profundidad (`-depth 3`)** para explorar más enlaces.
- **Filtrar URLs relevantes con `grep` o `jq`**.
- **Combinar con `nuclei` para escaneo automatizado de vulnerabilidades**.
