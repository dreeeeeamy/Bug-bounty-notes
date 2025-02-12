# Subfinder - Enumeración de Subdominios

## Descripción

Es una herramienta rápida y eficiente para **enumerar subdominios** de un dominio objetivo. Es utilizada para el descubrimiento de activos digitales de una organización.

Subfinder utiliza múltiples fuentes de datos públicas y privadas para encontrar subdominios, permitiendo una exploración rápida y precisa.

---

## Uso básico

### 1. Enumerar subdominios de un dominio
```bash
subfinder -d example.com
```

### 2. Enumerar subdominios y guardar en un archivo
```bash
subfinder -d example.com -o subdomains.txt
```

### 3. Enumerar múltiples dominios desde un archivo
```bash
subfinder -dL domains.txt -o results.txt
```

### 4. Integración con HTTPX para validación de subdominios
```bash
subfinder -d example.com | httpx -status-code
```

### 5. Usar claves API para mejorar resultados
Editar el archivo de configuración en `~/.config/subfinder/config.yaml` y agregar las API Keys.


## Consejos para optimizar resultados
- **Combinar con `amass` para mayor profundidad en la enumeración**.
- **Filtrar subdominios activos con `httpx` antes de analizar vulnerabilidades**.
- **Usar API Keys para obtener más resultados de fuentes premium**.
- **Ejecutar con múltiples hilos (`-t 50`) para mayor velocidad**.
