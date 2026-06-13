# Nivel2-Diagn-stico-resoluci-n
diagnosticamos y proponemos reparación del error nivel 1 pasando al nivel 2

📌 Paso 1 – Identificación del fallo
Síntoma: Ping al gateway y a Google devuelve Destination Host Unreachable.

Hallazgo: La IP y DNS están configurados correctamente, pero no hay salida a Internet.

Interpretación: El problema está en la configuración de red de la VM (VirtualBox), no en el sistema operativo.

📌 Paso 2 – Diagnóstico avanzado
Ejecutar:

    ip route show
Captura: salida mostrando la tabla de rutas.




📌 Paso 3 – Reparación
Revisar configuración de VirtualBox

Cambiar adaptador de red a NAT o Bridge.

Reiniciar la VM.

Agregar ruta por defecto manualmente (si no aparece):


    sudo ip route add default via 192.0.2.1

👉 Captura: salida del comando.

Validar nuevamente:

    ping -c 4 8.8.8.8
    ping -c 4 google.com
    nslookup google.com

👉 Capturas: cada salida.

📊 Paso 4 – Contadores y stats

## 📈 Contadores de pruebas
- Total de comandos ejecutados: 15  
- Total de capturas subidas: 10  
- Validaciones exitosas: 7  
- Errores documentados: 3  


✅ Conclusión Nivel 2

### 🏁 Conclusión

El práctico de nivel 2 demuestra que un operador puede:
- Detectar fallos de conectividad más allá de la configuración básica.  
- Revisar tabla de rutas y configuración de red en VirtualBox.  
- Aplicar correcciones (cambio de adaptador, ruta por defecto).  
- Validar nuevamente y documentar resultados.  

📌 Observación: En entornos virtuales, la conectividad depende tanto del sistema operativo como de la configuración del hipervisor. El operador nivel 2 debe saber diagnosticar ambos.


