# Nmap

## Descripción

Es una de las herramientas más utilizadas en seguridad informática y administración de redes. Permite descubrir dispositivos, identificar servicios y evaluar la seguridad de redes y sistemas.

Nmap puede escanear redes enteras o hosts individuales, proporcionando información detallada sobre los **puertos abiertos**, **versiones de software**, **sistemas operativos** y **vulnerabilidades**.

---

## Uso básico

### 1. Escaneo rápido de un solo host
```bash
nmap target.com
```

### 2. Escaneo de una red completa
```bash
nmap 192.168.1.0/24
```

### 3. Detectar puertos abiertos
```bash
nmap -p 1-65535 target.com
```

### 4. Escaneo detallado con detección de versiones y sistema operativo
```bash
nmap -A target.com
```

### 5. Guardar resultados en un archivo
```bash
nmap -oN resultados.txt target.com
```

### 6. Escaneo sigiloso (evitar detección por firewalls)
```bash
nmap -sS -Pn target.com
```

### 7. Uso de scripts NSE para detección de vulnerabilidades
```bash
nmap --script=vuln target.com
```

### 8. Detección de servicios y versiones de software
```bash
nmap -sV target.com
```

### 9. Escaneo agresivo con análisis de sistema operativo
```bash
nmap -A target.com
```

### 10. Escaneo de múltiples objetivos desde un archivo
```bash
nmap -iL lista_objetivos.txt
```

### 11. Escaneo completo de nmap para todos los puertos abiertos
```bash
nmap -p- --open -sS --min-rate 5000 -vvv -n -Pn target.com
```

## Consejos para optimizar resultados
- **Combinar Nmap con `masscan` para escaneos más rápidos en redes grandes**.
- **Utilizar `nmap -T4` para balancear velocidad y precisión**.
- **Filtrar resultados con `grep` o `awk` para análisis masivo**.
- **Ejecutar escaneos en segundo plano con `nohup nmap ... &`**.
