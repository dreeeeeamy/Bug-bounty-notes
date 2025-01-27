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
Para más ver todos los ejemplos, usa ```amass -h```.

Accede aquí para ver un [fichero de configuración](https://github.com/owasp-amass/amass/blob/master/examples/config.yaml).
