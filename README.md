# Building and Securing a Network with a DMZ

Proyecto práctico desarrollado en Cisco Packet Tracer para diseñar, implementar y asegurar una red segmentada mediante una **DMZ (Demilitarized Zone)**, aplicando controles de acceso, NAT estática y políticas básicas de firewall con ACL.

## Objetivo

El objetivo de este laboratorio es comprender cómo una DMZ ayuda a proteger una red interna permitiendo exponer servicios públicos (HTTP, DNS, SMTP, etc.) sin comprometer directamente la red LAN interna.

Se implementaron mecanismos de seguridad como:

- Segmentación de red (LAN / DMZ / WAN)
- ACL estándar y extendidas
- NAT estática para publicación de servicios
- Restricciones de tráfico entre zonas
- Prevención de movimientos laterales desde DMZ hacia LAN
- Exposición controlada de servicios públicos

---

## Topologia de Red
```bash
      Internet
          |
IP pública: 192.168.3.1
          |
  Router/Firewall
   ┌──────┴─────────┐
   |                |
  DMZ            LAN interna
192.168.2.0      192.168.1.0
Servidor Web
192.168.2.10

```
---

## Aprendizaje adquirido

Durante este laboratorio se practicó:

- Diseño seguro de arquitectura de red
- Configuración de ACLs Cisco
- Implementación de DMZ
- Configuración de NAT
- Segmentación y endurecimiento básico de infraestructura
- Documentación técnica de laboratorio


---
## Estructura del repositorio

```bash
├── Informe/                          # Informe detallado
├── assets/                           # Capturas, diagramas e imágenes
│   └── DMZ_PROJECT_CESAR.pkt         # Archivo Packet Tracer
└── README.md
```

---

## Informe detallado

📄 [Ver informe completo](Informe/Informe_DMZ_Laboratorio.md)

---


[@CesarSann](https://github.com/CesarSann)
