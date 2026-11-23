# Matriz de riesgos inicial (borrador)

| ID | Activo | Amenaza / Vulnerabilidad | C | I | D | Prob. | Impacto | Nivel | Control propuesto (marco) |
|---|---|---|---|---|---|---|---|---|---|
| R1 | Flota de 35 servidores | Deriva de configuración no detectada | Alta | Alta | Media | Alta | Alto | **Crítico** | Baseline versionada + verificación automatizada (NIST CM-6, CIS 4) |
| R2 | DC01 | GPO sin baseline aplicada o modificada manualmente | Alta | Alta | Media | Media | Alto | **Alto** | SCT + Policy Analyzer + verificación en Git (NIST CM-2, CM-3) |
| R3 | SRV-LNX01 | Servicios y puertos habilitados no inventariados | Media | Alta | Media | Alta | Alto | **Alto** | Lynis + CIS-CAT + script `check-baseline.sh` (CIS 4) |
| R4 | Credenciales y accesos | Privilegios excesivos y cuentas inactivas | Alta | Alta | Baja | Media | Alto | **Alto** | RBAC, sudo restringido, auditoría (NIST AC-2, AC-6) |
| R5 | Registro de eventos | Falta de auditoría y retención insuficiente | Media | Alta | Media | Alta | Medio | **Medio** | Auditoría avanzada Windows + auditd Linux (NIST AU-2, AU-12) |
| R6 | Repositorio de baselines | Cambios no auditables o pérdida de historial | Media | Alta | Baja | Media | Medio | **Medio** | Git con commits firmados y ramas protegidas (NIST CM-3) |
| R7 | Imágenes de contenedores | Versiones desactualizadas o no fijadas | Media | Media | Alta | Media | Medio | **Medio** | Fijar versiones en `docker-compose.yml`, escaneo con Trivy (CIS 7) |

**Referencias:** NIST 800-53 (familias CM, AC, AU, RA, SI), CIS Controls v8 (control 4: configuración segura; control 7: gestión de vulnerabilidades), MITRE ATT&CK (T1078, T1548, T1562.001).
