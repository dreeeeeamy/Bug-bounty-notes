# GAU
## Descripción

(Get All URLs) es una herramienta que permite extraer URLs indexadas de múltiples fuentes, como **Wayback Machine, Common Crawl, URLScan, y AlienVault OTX**. Es útil en **reconocimiento web, pentesting y bug bounty** para descubrir endpoints ocultos, rutas sensibles y parámetros históricos.

---

## Uso básico

### 1. Extraer URLs de un dominio
```bash
echo "example.com" | gau
```

### 2. Guardar URLs en un archivo
```bash
echo "example.com" | gau > urls.txt
```

### 3. Extraer URLs de múltiples dominios
```bash
cat domains.txt | gau > all_urls.txt
```

### 4. Filtrar URLs con parámetros
```bash
echo "example.com" | gau | grep "?"
```

### 5. Extraer solo ciertos tipos de archivos (ejemplo: JSON, PHP, TXT)
```bash
echo "example.com" | gau | grep -E '\.(json|php|txt)$'
```

### 6. Validar URLs extraídas con HTTPX
```bash
echo "example.com" | gau | httpx -mc 200
```

## Consejos para optimizar resultados
- **Usar con `httpx` para verificar URLs activas**.
- **Combinar con `waybackurls` para ampliar la búsqueda de URLs**.
- **Filtrar extensiones irrelevantes para reducir ruido en los resultados**.
- **Utilizar junto a `ffuf` para hacer fuzzing en los endpoints obtenidos**.
