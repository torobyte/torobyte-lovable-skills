# TOROBYTE Lovable Skills

Colección modular de skills para construir y mantener plataformas CRM, ERP y SaaS en Lovable, con enfoque en interfaces empresariales, seguridad y cambios seguros.

## Skills activas

| Skill | Para qué usarla |
|---|---|
| [torobyte-crm-core](skills/torobyte-crm-core/SKILL.md) | Arquitectura, convenciones y preservación de comportamiento |
| [torobyte-ui-standards](skills/torobyte-ui-standards/SKILL.md) | Diseño corporativo CRM, dashboards, tablas y formularios |
| [torobyte-responsive-design](skills/torobyte-responsive-design/SKILL.md) | Diseño para escritorio, tablet, móvil y PWA |
| [torobyte-security](skills/torobyte-security/SKILL.md) | Permisos, tenants, secretos, APIs y RLS |
| [torobyte-code-audit](skills/torobyte-code-audit/SKILL.md) | Auditoría técnica solo lectura, limpieza aprobada por lotes |
| [torobyte-debug-test](skills/torobyte-debug-test/SKILL.md) | Diagnóstico de errores, pruebas y regresiones |

## Cómo importar

En Lovable, visita **Settings → Skills → Add → Import from GitHub** y pega la URL de la carpeta de la skill:

`https://github.com/torobyte/torobyte-lovable-skills/tree/main/skills/torobyte-crm-core`

Reemplaza el último segmento por cada skill deseada. No necesitas activarlas todas en cada tarea; Lovable carga skills que correspondan a la solicitud.

## Compatibilidad y migración

La anterior [torobyte-crm-standards](skills/torobyte-crm-standards/SKILL.md) queda como entrada **legacy**, solo para proyectos que aún la invocan. Para evitar contexto redundante, deja de usarla una vez importadas las nuevas.

El contenido es una guía, **no autoriza** modificaciones automáticas de código, datos, seguridad o despliegues. Auditar o proponer un diseño implica solo lectura. Los tests y comprobaciones deben reportarse honestamente.

## Uso recomendado

- Trabajo CRM normal: `torobyte-crm-core`.
- Diseño visual: `torobyte-ui-standards`.
- Responsive o app-like: `torobyte-responsive-design`.
- Cambios de permisos o secretos: `torobyte-security`.
- Auditoría: `torobyte-code-audit`.
- Error o regresión: `torobyte-debug-test`.
