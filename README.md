# 🛡️ SOC-Lab-SSH-BruteForce

# 🔐 Simulación de Ataque de Fuerza Bruta SSH con Hydra

---

## 📌 Descripción del proyecto

Este laboratorio simula un ataque de fuerza bruta contra un servicio SSH en un entorno controlado utilizando Kali Linux como atacante y Ubuntu Server como sistema objetivo.

El objetivo del ejercicio es analizar el ciclo completo de un incidente de seguridad:

* Ejecución del ataque
* Detección mediante logs del sistema
* Análisis de tráfico de red
* Aplicación de medidas de mitigación
* Verificación del resultado

---

## 🧱 Entorno del laboratorio

* 🖥️ Atacante: Kali Linux
* 🖥️ Víctima: Ubuntu Server
* 🔐 Servicio objetivo: SSH (puerto 22)
* 🌐 Entorno: Red local controlada

---

## 🔴 Ejecución del ataque

![Hydra Attack](01-hydra-attack.png)

Se ejecuta la herramienta Hydra realizando múltiples intentos automatizados de autenticación contra el servicio SSH.

Este comportamiento es característico de un ataque de fuerza bruta, donde se prueban múltiples credenciales de forma secuencial.

---

## 📋 Detección en logs del sistema

![Auth Log](02-authlog-failed.png)

El sistema registra múltiples intentos fallidos de autenticación en el archivo `/var/log/auth.log`.

Se observan accesos repetidos desde la misma dirección IP, lo que indica un patrón automatizado de ataque.

---

## 🌐 Análisis de tráfico de red

![TCPDump](03-tcpdump-syn.png)

Se identifican múltiples paquetes TCP SYN dirigidos al puerto 22 del sistema víctima.

Este patrón corresponde al establecimiento repetido de conexiones TCP, característico de herramientas automatizadas de ataque como Hydra.

Se observa el comportamiento del protocolo de enlace TCP (SYN → SYN-ACK → ACK).

---

## 🛑 Mitigación del ataque

![iptables](04-iptables-block.png)

Se aplica una regla de firewall utilizando iptables para bloquear el tráfico procedente de la IP atacante.

Esta medida interrumpe la comunicación y evita nuevos intentos de conexión al servicio SSH.

---

## ✅ Resultado final

![Ataque detenido](05-attack-stopped.png)

Tras la aplicación de la regla de bloqueo, el ataque deja de ser efectivo.

No se observan nuevas conexiones exitosas ni intentos adicionales desde la IP atacante.

---

## 📌 Conclusión

Este laboratorio demuestra el ciclo completo de un incidente de seguridad SSH:

* Identificación de un ataque de fuerza bruta
* Detección mediante logs del sistema
* Análisis de tráfico de red
* Contención mediante firewall

Este ejercicio refleja escenarios reales de análisis y respuesta en entornos SOC (Security Operations Center).
 y no se establecen nuevas conexiones.
