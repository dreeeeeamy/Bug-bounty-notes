## Reconnaissance

En esta sección encontrarás herramientas y ejemplos prácticos para la fase de reconocimiento en bug bounty.

## Índice
- [Amass](#amass)
- [Subfinder](#subfinder)
- [FFUF](#ffuf)
- [Gobuster](#gobuster)
- [Nmap](#nmap)
- [Waybackurls](#waybackurls)
- [Aquatone](#aquatone)
- [HTTPX](#httpx)


### Amass
**Descripción:** Amass es una herramienta para realizar descubrimiento de subdominios y recopilar información sobre infraestructura externa mediante OSINT y consultas activas.

**Ejemplos:**
```bash
#Escaneo básico
amass enum -d target.com

# Escaneo pasivo de subdominios
amass enum -passive -d target.com

# Escaneo activo y pasivo de subdominios
amass enum -active -d target.com

# Guardar resultados en un archivo
amass enum -d target.com -o resultados.txt
```

### Subfinder 
**Descripción:** Subfinder es otra herramienta para descubrir subdominios, centrada en consultas rápidas y silenciosas a fuentes públicas.

**Ejemplos:**
```bash
# Escaneo básico
subfinder -d target.com

# Escaneo y salida en un archivo
subfinder -d target.com -o subdominios.txt
```

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

### Gobuster 
**Descripción:** Gobuster es una herramienta rápida para fuzzing de directorios y subdominios, utilizando wordlists.

**Ejemplos:**
```bash
# Enumeración de directorios
gobuster dir -u http://target.com -w /path/to/wordlist.txt

# Enumeración de subdominios
gobuster dns -d target.com -w /path/to/wordlist.txt

# Enumeración de archivos específicos
gobuster dir -u http://target.com -w /path/to/wordlist.txt -x php,html
```

### nmap 
**Descripción:** Nmap es una herramienta de escaneo de red para descubrir hosts, servicios y posibles vulnerabilidades.

**Ejemplos:**
```bash
# Escaneo básico de puertos
nmap target.com

# Escaneo de puertos específicos
nmap -p 80,443 target.com

# Escaneo de versiones y scripts
nmap -sV -sC target.com

# Escaneo completo silencioso
nmap -sS -p- --open --min-rate 5000 -vvv -n -Pn target.com
```

### Waybackurls 
**Descripción:** Waybackurls extrae URLs históricas de servicios como el Wayback Machine y Common Crawl.

**Ejemplos:**
```bash
# Extraer URLs de un dominio
echo "target.com" | waybackurls
```

### Aquatone 
**Descripción:** Aquatone es una herramienta para tomar capturas de pantalla de subdominios y hosts en una red.

**Ejemplos:**
```bash
# Tomar capturas de pantalla
cat subdominios.txt | aquatone
```
### Httpx 
**Descripción:** HTTPX verifica el estado y detalles de URLs o subdominios.

**Ejemplos:**
```bash
# Verificar subdominios activos
httpx -l subdominios.txt

# Mostrar encabezados de respuesta
httpx -l subdominios.txt -mc 200 -sr
```
