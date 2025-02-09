# Amass

## Descripción

Es una herramienta de código abierto utilizada para la enumeración de subdominios y el reconocimiento pasivo/activo en pruebas de seguridad. Es ampliamente usada para descubrir subdominios ocultos objetivo.

---
## Comandos esenciales

### Enumeración pasiva (OSINT)
```bash
amass enum -passive -d example.com
```
*Este modo usa solo fuentes OSINT sin interactuar directamente con los servidores del objetivo.*

### Enumeración activa
```bash
amass enum -active -d example.com
```
*Realiza consultas DNS activas y fuerza bruta para encontrar más subdominios.*

### Combinación de pasivo y activo
```bash
amass enum -brute -d example.com
```
*Habilita la fuerza bruta de subdominios junto con la enumeración estándar.*

### Uso de múltiples fuentes
```bash
amass enum -d example.com -src
```
*Muestra de dónde provienen los resultados obtenidos.*

### Exploración en profundidad
```bash
amass enum -d example.com -active -brute -o resultados.txt
```
*Guarda los subdominios descubiertos en un archivo.*

## Consejos para optimizar resultados
- Usa `-timeout 10` para evitar bloqueos por tiempo de espera.
- Combina con `-config amass_config.ini` para personalizar fuentes y APIs.
- Usa `-src` para identificar las fuentes de los datos obtenidos.
- Ejecuta `amass viz -d3` para generar una visualización gráfica de los subdominios.
