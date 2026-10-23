# CyberLab | SSH Security Assessment & Hardening

## Descripción del proyecto

Laboratorio práctico de ciberseguridad desarrollado en un entorno virtualizado y controlado, orientado a la evaluación de seguridad de servicios SSH, análisis de tráfico de red y aplicación de medidas de endurecimiento (*hardening*).

## Entorno de laboratorio

- **Atacante / equipo de auditoría:** Kali Linux 2025.4 — `192.168.56.10`
- **Sistema evaluado:** Ubuntu Server 24.04 LTS — `192.168.56.20`
- **Virtualización:** Oracle VirtualBox
- **Red de laboratorio:** CyberLab
- **Servicio evaluado:** OpenSSH, puerto TCP 22

## Herramientas utilizadas

- Nmap: descubrimiento de servicios y enumeración.
- Wireshark: captura y análisis de tráfico ICMP, TCP y SSH.
- OpenSSH: revisión de configuración y controles de acceso.
- Linux: administración, actualización y validación de servicios.

## Metodología

1. Configuración y validación de conectividad del laboratorio.
2. Reconocimiento y enumeración del servicio SSH.
3. Revisión de algoritmos criptográficos y configuración.
4. Análisis del tráfico de red mediante Wireshark.
5. Identificación preliminar de posibles vulnerabilidades.
6. Actualización y endurecimiento del servicio.
7. Verificación posterior a los cambios.

## Hallazgos y medidas correctivas

| Observación | Acción |
|---|---|
| Acceso SSH directo de root permitido mediante claves | Configuración de `PermitRootLogin no` |
| Reenvío X11 habilitado | Configuración de `X11Forwarding no` |
| Actualización de seguridad disponible para OpenSSH | Actualización a `1:9.6p1-3ubuntu13.20` |
| Posibles CVE identificadas mediante escaneo | Revisión preliminar; sin explotación ni confirmación de vulnerabilidad |

## Validación

Se comprobó la configuración efectiva de SSH mediante `sshd -T`, se verificó la sintaxis con `sshd -t` y se confirmó posteriormente la disponibilidad del servicio mediante Nmap.

**Resultado del escaneo final:**

`22/tcp open ssh OpenSSH 9.6p1 Ubuntu 3ubuntu13.20`

## Alcance y limitaciones

Todas las pruebas se realizaron sobre sistemas propios en un laboratorio autorizado. El proyecto documenta una evaluación de configuración y endurecimiento de SSH, no una intrusión exitosa ni la explotación demostrada de vulnerabilidades.

## Evidencias

Las capturas de pantalla y los resultados relevantes se organizarán en la carpeta `evidencias/`.
