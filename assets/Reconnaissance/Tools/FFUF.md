### ffuf 
**Descripción:** FFUF (Fuzz Faster U Fool) es una herramienta para fuzzing de directorios, subdominios y otras rutas interesantes en aplicaciones web.

**Ejemplos:**
```bash
# Fuzzing de directorios
ffuf -u http://target.com/FUZZ -w /path/to/wordlist.txt

# Fuzzing de subdominios
ffuf -u http://FUZZ.target.com -w /path/to/subdomains.txt

# Filtrar resultados por tamaño de respuesta
ffuf -u http://target.com/FUZZ -w /path/to/wordlist.txt -fs 4242
```
