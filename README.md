# Ejecucion de DTP hopping

**Estudiante:** Masucci Franco Rincón  
**Matrícula:** 2024-1250  
**Asignatura:** Seguridad de Redes  
**Fecha:** 27/02/2026  



---https://itlaedudo-my.sharepoint.com/:v:/g/personal/20241250_itla_edu_do/IQChvRGCH5NrQr9oM7MK-VhWAcHELkD9Xhoe_YNwoZImtTo?nav=eyJyZWZlcnJhbEluZm8iOnsicmVmZXJyYWxBcHAiOiJPbmVEcml2ZUZvckJ1c2luZXNzIiwicmVmZXJyYWxBcHBQbGF0Zm9ybSI6IldlYiIsInJlZmVycmFsTW9kZSI6InZpZXciLCJyZWZlcnJhbFZpZXciOiJNeUZpbGVzTGlua0NvcHkifX0&e=ACQ81G

### Descripción y Topología 

El laboratorio se ha desplegado en un entorno virtualizado utilizando **GNS3**, simulando una infraestructura de red corporativa vulnerada desde el interior.

### Detalles de la Topología

* **Direccionamiento IP:** Subred `10.12.50.0/24`.
<img width="460" height="270" alt="image" src="https://github.com/user-attachments/assets/7c9a3f61-c78e-480f-8355-1d55e8b1dce8" />


| Dispositivo | Interfaz | Dirección IP | Máscara de Subred | Gateway Predeterminado |
| :--- | :--- | :--- | :--- | :--- |
| **R1** | e0/0 | 10.12.50.1 | 255.255.255.0 (/24) |    |
| **Sw1** | VLAN 1 | N/A  | N/A | N/A |
| **gnsattack (atacante)** | eth0 | 10.12.50.13 | 255.255.255.0 (/24) | 10.12.50.1 |
| **VPCS (víctima)** | e0/0 | 10.12.50.11 | 255.255.255.0 (/24) | 10.12.50.1 |


### Objetivo del Script
El objetivo del script es demostrar la vulnerabilidad del protocolo DTP (Dynamic Trunking Protocol) cuando los puertos del switch están configurados en modo dinámico, permitiendo que un atacante convierta un puerto de acceso en un puerto troncal sin autorización.




## Evidencia de Ejecución
## 1-
<img width="799" height="383" alt="image" src="https://github.com/user-attachments/assets/d9ef9a7b-9bae-4d56-bf7e-3fb5ec7d3605" />





---

### Requisitos para utilizar la herramienta.
Tener python3 instalado en la maquina atacante


### Medidas de Mitigación
Todos correspondiente en modo acceso
conf t
interface range fa0/1-24
switchport mode access
