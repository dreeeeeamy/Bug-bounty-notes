# Masscan

## Descripción

Es una herramienta de escaneo de puertos extremadamente rápida, similar a **nmap**, pero optimizada para realizar escaneos a gran escala en redes extensas. Su motor asíncrono le permite escanear el rango completo de direcciones IPv4 en cuestión de minutos, lo que la hace ideal para **pentesting**, **reconocimiento** y **auditorías de seguridad**.

---
## Comandos esenciales

### Escaneo básico de un objetivo
```bash
sudo masscan -p80 192.168.1.1
```
*Escanea el puerto **80** en la IP especificada.*

### Escaneo de múltiples puertos
```bash
sudo masscan -p80,443,22 192.168.1.0/24
```
*Escanea los puertos **80, 443 y 22** en toda la subred.*

### Escaneo de todos los puertos
```bash
sudo masscan -p1-65535 192.168.1.1
```
*Escanea todos los puertos en una IP específica.*

### Ajustar velocidad de escaneo
```bash
sudo masscan -p80,443 192.168.1.0/24 --rate=10000
```
*Define una tasa de **10,000 paquetes por segundo** para evitar sobrecargar la red.*

### Guardar resultados en un archivo
```bash
sudo masscan -p22,80,443 192.168.1.0/24 -oX resultados.xml
```
*Guarda la salida en formato XML compatible con Nmap.*

### Especificar interfaz de red
```bash
sudo masscan -p80 192.168.1.0/24 --interface eth0
```
*Especifica una interfaz de red para el escaneo.*

## Consejos para optimizar resultados
- Ajusta `--rate` según la capacidad de la red para evitar bloqueos.
- Usa `-oX` para integrar con herramientas como **Nmap** y **Metasploit**.
- No escanees redes sin autorización para evitar problemas legales.

