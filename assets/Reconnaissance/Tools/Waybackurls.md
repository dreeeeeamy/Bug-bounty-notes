# Waybackurls

## Descripción

Es una herramienta utilizada para **extraer URLs históricas** de la Wayback Machine y otros servicios de almacenamiento web. Es muy útil para descubrir endpoints, parámetros ocultos y versiones antiguas de aplicaciones web.

Esta herramienta se basa en peticiones a la **Wayback Machine de archive.org**, permitiendo recuperar URLs indexadas con el tiempo, lo que ayuda en la identificación de posibles vectores de ataque.

---

## Uso básico

### 1. Extraer URLs archivadas de un dominio
```bash
echo "example.com" | waybackurls
```

### 2. Extraer URLs y guardarlas en un archivo
```bash
echo "example.com" | waybackurls > urls.txt
```

### 3. Extraer URLs de múltiples dominios desde un archivo
```bash
cat domains.txt | waybackurls > all_urls.txt
```

### 4. Filtrar URLs con parámetros
```bash
echo "example.com" | waybackurls | grep "?"
```

### 5. Validar URLs extraídas con HTTPX
```bash
echo "example.com" | waybackurls | httpx -status-code
```

## Consejos para optimizar resultados
- **Usar con `httpx` para validar qué URLs siguen activas**.
- **Combinar con `gau` para obtener más URLs de fuentes adicionales**.
- **Filtrar endpoints relevantes con `grep` o `jq`**.
- **Explorar parámetros descubiertos con Burp Suite o wfuzz**.
