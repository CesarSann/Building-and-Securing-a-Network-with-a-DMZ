 
# Informe de configuración de DMZ con Cisco Packet Tracer - Cesar Sandino


### 1. Objetivo del laboratorio


Configurar una DMZ segura usando un router Cisco ISR, aplicando NAT y ACLs para controlar el tráfico entre LAN, DMZ y red externa.

---

### 2. Topología implementada

> Describe la red. Puedes incluir una imagen si el software lo permite (captura de Packet Tracer).
Esta topologia esta divida principalmente en tres zonas las cuales se controlan por un router central.
 
- **Red Interna (LAN)** Esta red es de acceso exclusivo para empleados internos de la corporación. 
- **DMZ (WEB)** Esta red es donde esta alojada el servidor web y la cual se aisló para evitar un acceso no autorizado desde esta red hacia la red interna. 
- **Red Externa (WAN)** Esta red representa el trafico que viene del exterior y host de internet 



### 3. Plan de direccionamiento IP


| Dispositivo             | IP               | Máscara           | Gateway           |
|-------------------------|------------------|-------------------|-------------------|
| PC_Internal             | 192.168.1.10     |  255.255.255.0    | 192.168.1.1       |
| Server_DMZ              | 192.168.1.10     |  255.255.255.0    | 192.168.2.1       |
| PC_External             | 192.168.1.10     |  255.255.255.0    | 192.168.3.1       |
| Router_FW Gi0/0 (LAN)   | 192.168.1.1      |  255.255.255.0    |                   |
| Router_FW Gi0/1 (DMZ)   | 192.168.2.1      |  255.255.255.0    |                   |
| Router_FW Gi0/2 (Ext)   | 192.168.3.1      |  255.255.255.0    |                   |


### 4. Configuración aplicada 

## Configuración de NATs estaticas
Dominio NAT implementado para que el trafico externo pueda acceder al servidor interno (en este caso DMZ) sin exponer directamtente la red interna. ademas de la configuración de interfaces de sus respectivas redes.

- Interfaces configuradas con `ip address`


- NAT:
```bash
ip nat inside source static 192.168.2.10 192.168.3.1
```
- ACLs:
```bash
access-list 101 permit tcp any host 192.168.3.1 eq 80
access-list 100 deny ip 192.168.2.0 0.0.0.255 192.168.1.0 0.0.0.255
```



### 5. Verificaciones realizadas

> Describe las pruebas y su resultado. Incluye capturas o salidas de comandos si se puede.

- `ping` desde PC_Internal al router: ✅
- Acceso web desde PC_External: ✅
- Bloqueo de acceso desde DMZ a LAN: ✅


### 6. Conclusiones y recomendaciones

> ¿Qué aprendiste con este ejercicio? ¿Qué mejorarías?

**Ejemplo:**
Aprendí a aplicar NAT y ACLs en un entorno simulado. Recomiendo verificar conectividad básica antes de aplicar reglas de firewall, ya que un error en la IP puede bloquear todo.


### 7. Capturas de evidencia

> Adjunta aquí (o en un PDF anexo) las capturas solicitadas: pings, navegador, comandos `show`, etc.
