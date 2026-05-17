# SOC-Lab-SSH-BruteForce
# 🔐 SSH Brute Force Attack (Hydra)

---

## 🔴 Ejecución del ataque

![Hydra Attack](01-hydra-attack.png)

Se observa la herramienta Hydra ejecutando múltiples intentos de autenticación contra el servicio SSH.

---

## 📋 Evidencia en logs

![Auth Log](02-authlog-failed.png)

El sistema registra múltiples intentos fallidos de autenticación desde la IP atacante.

---

## 🌐 Análisis de red

![TCPDump](03-tcpdump-syn.png)

Se identifican múltiples paquetes SYN dirigidos al puerto 22, indicando intentos repetidos de conexión.

---

## 🛑 Mitigación

![iptables](04-iptables-block.png)

Se aplica una regla en iptables para bloquear la IP atacante.

---

## ✅ Resultado

![Ataque detenido](05-attack-stopped.png)

Tras aplicar la regla, el ataque deja de ser efectivo y no se establecen nuevas conexiones.
