### Katana
**Descripción:** Katana es una herramienta rápida y liviana para la búsqueda de rutas (web crawling). Está diseñada para realizar descubrimientos en aplicaciones web, recopilando URLs, endpoints y otros recursos útiles para análisis y explotación.
**Ejemplos:**
```bash
# Escaneo básico de una URL
katana -u https://target.com  

# Escaneo con extracción de JavaScript y endpoints
katana -u https://target.com -js  

# Escaneo incluyendo subdominios descubiertos
katana -u https://target.com -subs  

# Guardar resultados en un archivo
katana -u https://target.com -o resultados.txt  

# Escaneo con concurrencia personalizada (10 hilos)
katana -u https://target.com -c 10 
```

Para más ver todos los ejemplos, usa ```katana -h```.
