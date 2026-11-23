# Strong Heroes — Reto 6: "Treinta y Cinco Servidores, Treinta y Cinco Versiones"

**Proyecto Final ABR — Seguridad de Sistemas Operativos**
**Técnico Superior en Ciberseguridad**

## Equipo

| Integrante | Rol |
|---|---|
| Genesis Gómez | Arquitecta de infraestructura (líder) |
| Alejandro Guerrero | Especialista Windows |
| Andrés Polo | Especialista Linux y automatización |

## Reto asignado

**Reto 6 — Baselines y cumplimiento como código (Compliance as Code)**

Implementar un modelo de cumplimiento como código para una organización ficticia (Servicios Logísticos del Istmo, S.A.) con 35 servidores heterogéneos, aplicando baselines versionadas en Git y scripts de verificación automatizada en Windows Server 2022 y Ubuntu Server 24.04.

## Estructura del repositorio
strong-heroes-reto6-compliance/
├── README.md
├── docs/
│ ├── 01-acta-equipo.md
│ ├── 02-storytelling.md
│ ├── 03-diagrama-laboratorio.png
│ ├── 04-preguntas-guia.md
│ ├── 05-matriz-riesgos.md
│ └── 06-cronograma.md
├── baselines/
│ ├── windows/
│ └── linux/
├── scripts/
│ ├── ps1/
│ └── bash/
├── evidence/
│ ├── snapshots/
│ ├── diagnostico-inicial/
│ └── validacion-cruzada/
└── reports/

text

## Fases ABR

| Fase | Semana | Entregable |
|---|---|---|
| Involucrar | 8 | Acta, storytelling, pregunta esencial, diagrama, matriz de riesgos |
| Investigar | 9–10 | Laboratorio inseguro, diagnóstico base, scripts de auditoría |
| Actuar I | 11 | Aplicación de baseline, control de acceso |
| Actuar II | 12 | Scripts de compliance, matriz control ↔ configuración ↔ evidencia |
| Validación cruzada | 13 | Pruebas ATT&CK, remediación, escaneo final |
| Defensa | 14 | Presentación ante comité + informe final |

## Entregas parciales

- **13 nov 2026** — 25% (Involucrar)
- **20 nov 2026** — 25% (Investigar)
- **27 nov 2026** — 25% (Actuar I)
- **04 dic 2026** — 25% (Actuar II + énfasis)
- **11 dic 2026** — Sustentación tentativa

## Marcos de referencia

- CIS Benchmarks (Windows Server 2022, Ubuntu 24.04)
- CIS Controls v8 (control 4: Secure Configuration; control 7: Vulnerability Management)
- NIST 800-53 (CM-2, CM-3, CM-6, CM-7, AU-2, AU-12, AC-2, AC-6)
- MITRE ATT&CK (T1078, T1548, T1562.001, T1210, T1021.001)
- ISO 27001 (A.8.8, A.8.9)
