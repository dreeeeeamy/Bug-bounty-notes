# Aquatone

## Descripción

Es una herramienta utilizada para la **recolección y visualización de información de subdominios**. Permite capturar capturas de pantalla, recopilar títulos de páginas y encabezados HTTP, facilitando la identificación de servicios web expuestos.

Es especialmente útil en **bug bounty**, **pentesting** y **reconocimiento**, ya que proporciona una forma rápida de explorar la superficie de ataque de un dominio objetivo.

---
## Uso básico

### Entrada de subdominios desde un archivo
```bash
cat subdominios.txt | aquatone
```
*Procesa los dominios listados en `subdominios.txt`, captura pantallas y genera un reporte.*

### Uso con herramientas externas
#### Integración con Amass
```bash
amass enum -d example.com -o subdominios.txt
cat subdominios.txt | aquatone
```

#### Integración con Subfinder
```bash
subfinder -d example.com | aquatone
```

### Especificar número de hilos para escaneo paralelo
```bash
cat subdominios.txt | aquatone -threads 10
```
*Por defecto, Aquatone usa **5 threads**. Aumentar este valor puede mejorar la velocidad del análisis.*

### Cambiar resolución de las capturas
```bash
cat subdominios.txt | aquatone -resolution 1920x1080
```
*Define la resolución de las capturas de pantalla generadas.*

## Consejos para optimizar resultados
- **Combinar con otras herramientas** como `Subfinder`, `Amass`, `Masscan` o `Nmap` para mejorar el reconocimiento.
- **Ajustar el número de hilos (`-threads`)** para acelerar el análisis en entornos con más recursos.
- **Utilizar un User-Agent personalizado (`-user-agent`)** para evitar bloqueos en servidores.
- **Explorar manualmente los reportes generados** para identificar servicios ocultos o vulnerables.
