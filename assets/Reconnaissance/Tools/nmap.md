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
Para más ver todos los ejemplos, usa ```nmap -h```.
