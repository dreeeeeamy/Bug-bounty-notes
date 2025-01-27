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

Para más ver todos los ejemplos, usa ```gobuster -h```.
