# Storytelling del reto (fase Involucrar)

## Organización ficticia

**Servicios Logísticos del Istmo, S.A. (SLI)** es una empresa panameña con sede en Ciudad de Panamá y operaciones en Colón y David. Gestiona la cadena de suministro de 12 clientes corporativos y opera una infraestructura híbrida de **35 servidores**: 18 Windows Server 2022 y 17 Ubuntu Server 24.04, distribuidos entre su centro de datos principal y dos sitios remotos.

## Personajes

- **Mariela Cedeño** — Gerente General de SLI.
- **Rubén Aparicio** — Jefe de TI, con un equipo de 3 personas.
- **Karla Domínguez** — Analista de seguridad recién incorporada.
- **El cliente afectado:** una cadena de supermercados que exige certificación de controles para renovar contrato.

## La crisis

Un viernes por la tarde, el proveedor de monitoreo del cliente principal alerta a SLI: uno de sus servidores Ubuntu del sitio de David está enviando tráfico saliente hacia una IP asociada a una campaña de minería de criptomonedas. La investigación interna revela algo peor:

- Ese servidor **no había recibido la última baseline** aplicada al resto de la flota porque "se configuró a mano" hace dos años.
- **Cada uno de los 35 servidores tiene una versión distinta** de configuración: contraseñas, servicios habilitados, puertos abiertos, políticas de auditoría.
- No existe un inventario confiable ni un mecanismo que **verifique** si un servidor cumple con la configuración aprobada.
- El equipo de TI invierte **tres días completos** revisando servidor por servidor para descubrir cuántos más estaban fuera de norma.

**Mariela Cedeño** convoca al equipo y da una instrucción clara:

> *"No quiero volver a descubrir por un cliente que un servidor estaba mal configurado. Quiero saber, en cualquier momento y sin revisar a mano, si mis 35 servidores cumplen o no, y quiero que corregirlos sea repetible y auditable."*

## Idea grande

> **Una flota sin baseline verificable es una ruleta rusa de configuraciones: cada servidor es una apuesta y nadie sabe cuál está cargada.**

## Pregunta esencial

> **¿Cómo garantizamos que 35 servidores mantengan una configuración segura y verificable, sin depender de revisión manual y detectando cualquier desviación a tiempo?**

## Reto

> **Diseñar e implementar un modelo de cumplimiento como código (Compliance as Code) para SLI, con baselines versionadas en Git y scripts de verificación automatizada, que detecten y reporten la deriva de configuración en Windows Server 2022 y Ubuntu Server 24.04, alineado a CIS Benchmarks, CIS Controls v8 (control 4) y NIST 800-53 (CM-2, CM-3, CM-6, CM-7).**
