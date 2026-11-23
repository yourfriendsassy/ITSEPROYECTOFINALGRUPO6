# Diagrama inicial del laboratorio

> **Nota:** Reemplazar este archivo con el diagrama real (`03-diagrama-laboratorio.png`) cuando esté disponible.

## Segmentación de red (VMware Workstation Pro 26H1)
┌──────────────────────────────────────────────────────────────────────┐
│ Host · VMware Workstation Pro 26H1 │
│ │
│ ┌──────────────────┐ ┌──────────────────┐ ┌──────────────────┐ │
│ │ Usuarios·VMnet2 │ │ Servidores·VMnet3│ │ Administración │ │
│ │ │ │ │ │ ·VMnet4 │ │
│ │ WKS01 (opcional)│──▶│ DC01 │◀──│ Host de salto │ │
│ │ Windows 11 Ent. │ │ Windows Server │ │ (RDP/SSH) │ │
│ │ o Ubuntu 24.04 │ │ 2022 · AD DS │ │ │ │
│ │ │ │ DNS · GPO │ │ ATK01 (Kali) │ │
│ │ │ │ │ │ Validación S13 │ │
│ │ │ │ SRV-LNX01 │ │ │ │
│ │ │ │ Ubuntu 24.04 │ │ │ │
│ │ │ │ Docker Compose │ │ │ │
│ └──────────────────┘ └────────┬─────────┘ └──────────────────┘ │
│ │ │
│ ┌──────────▼──────────┐ │
│ │ VMnet8 · NAT │ │
│ │ salida solo para │ │
│ │ actualizaciones │ │
│ └─────────────────────┘ │
└──────────────────────────────────────────────────────────────────────┘

text

## Flujos permitidos (borrador inicial)

| Origen | Destino | Puerto/Servicio | Justificación |
|---|---|---|---|
| WKS01 | DC01 | DNS (53), Kerberos (88), LDAP (389/636), SMB (445) | Unión al dominio y autenticación |
| Host de salto | DC01 | RDP (3389) | Administración Windows |
| Host de salto | SRV-LNX01 | SSH (22) | Administración Linux |
| DC01 / SRV-LNX01 | VMnet8 NAT | 80/443 (salida) | Solo actualizaciones |
| ATK01 | Servidores | Según plan S13 | Solo semana 13, validación cruzada |

## VMs del laboratorio común

| VM | Sistema | Función mínima | Recursos |
|---|---|---|---|
| DC01 | Windows Server 2022 Standard | Controlador de dominio, DNS, GPO | 2 vCPU, 4 GB RAM, 60 GB |
| SRV-LNX01 | Ubuntu Server 24.04 LTS | Docker Engine + Docker Compose | 2 vCPU, 4 GB RAM, 40 GB |
| WKS01 (opcional) | Windows 10/11 Ent. o Ubuntu Desktop 24.04 | Estación unida al dominio | 2 vCPU, 4 GB RAM, 40 GB |
| ATK01 | Kali Linux | Validación ofensiva controlada (S13) | 2 vCPU, 2 GB RAM, 30 GB |
