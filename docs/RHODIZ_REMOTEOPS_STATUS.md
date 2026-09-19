# Continuidad vigente — 2026-09-19 — revalidación RDC bloqueada

Proyecto: **RHODIZ ChatGPT Harness**. Componente: **RHODIZ RemoteOps MCP**.
Este bloque prevalece sobre el snapshot histórico conservado debajo. Es **documentación**, no código, release, certificación ni deployment.

## Resultado de la reanudación

- Producto: **BLOCKED_INSTALLER_REVIEW**. INSTALL-001..005 continúan abiertos.
- Bloqueo inmediato de esta reanudación: **BLOCKED_RDC_SECURITY_CONTROL**. RDC enumeró relay en línea y abrió un proceso; el control de seguridad bloqueó la llamada de comprobación de identidad sin devolver sus resultados. El proceso propio se cerró y su salida 0 fue confirmada.
- **BLOCKED_BUILD_IDENTITY** sigue pendiente del handoff anterior, pero el UID y las capacidades de esta nueva sesión **no fueron revalidados**. No atribuirle automáticamente el estado root/CAP_SETUID histórico ni afirmar indisponibilidad total de RDC.
- No se reintentó la operación denegada por otra herramienta, shell, credencial o transición de identidad. Tampoco se reintentó la escritura RDC denegada al cerrar la sesión anterior.
- No se ejecutaron correcciones, builds, pruebas del producto, instaladores, cambios de servicios o WIP, ni SSH/túnel/E2E. El inventario y los digests anteriores siguen siendo evidencia histórica, no un preflight actual.
- La reanudación de memoria volvió a fallar por falta de identidad de proyecto. Se recuperó únicamente el registro legado expresamente autorizado; no hay binding reparado ni replay completo.
- La API GitHub confirmó `main` en `d52008a75aad68d957047935e1a252755aac1cc1`, la rama documental en `34738c8f5fa3124adcf63b6bfca042e5a9dda57d` antes de esta actualización y ausencia de la rama de producto en esa consulta. Esta actualización solo modifica este documento en la rama documental; su commit y lectura posterior se registran en el handoff privado.
- Se recuperó y verificó la integridad del paquete privado de evidencia previo. Esta comprobación documental se hizo en el contenedor de conversación; no se trasladaron a él el desarrollo, los builds ni las pruebas del producto.

## Siguiente condición necesaria

Disponer de una ejecución RDC autorizada en relay que permita completar el preflight y trabajar como usuario de build no privilegiado, **sin eludir el control que bloqueó la llamada**. Renovar después identidad, acceso Git/Docker y cobertura de preservación; corregir/probar INSTALL-001..005; generar nuevos artefactos y pins revisados; certificar íntegramente y publicar el SHA de producto verificado antes de staging/rollback y SSH/agente/túnel/aprobación E2E.

Mantener **ask-all**, **TTL cero**, preservación de servicios/repositorios/WIP y CI únicamente como certificación. No ejecutar instaladores originales ni transferencias parciales. No fusionar esta rama documental con la fuente certificada automáticamente. No presentar la sincronización documental como avance del deployment.

---

## Snapshot documental anterior — conservado íntegro, no es estado vivo actual

# RHODIZ RemoteOps MCP — estado y continuidad

Proyecto: **RHODIZ ChatGPT Harness**. Componente: **RHODIZ RemoteOps MCP**.
Registro: **2026-09-19**, tras la comprobación viva de las 21:47–21:49 UTC.

**Este documento no es una release, un certificado ni una autorización de deployment.**
Es un resumen público revisado; los inventarios operativos, identificadores de memoria y evidencia detallada permanecen en las herramientas privadas autorizadas.

## Estado vigente

- Producto: **BLOCKED_INSTALLER_REVIEW**; INSTALL-001 a INSTALL-005 siguen abiertos.
- Ejecución: **BLOCKED_BUILD_IDENTITY**; no se consiguió una identidad de build no privilegiada en esta continuación.
- No hay release corregida ni deployment certificado. No se ejecutaron instaladores, certificación integral, SSH de autenticación, túnel ni aprobación E2E.
- Destino autorizado: **todo en rhodiz-relay**. Preservar servicios, repositorios y WIP; no trasladar el trabajo a otra VM.

## Hallazgos pendientes

| Código | Corrección y prueba exigidas |
|---|---|
| INSTALL-001 | Corregir `PermitUserEnvironment` dentro de `Match`; validar configuración SSH candidata completa y política efectiva sin cambios globales ciegos. |
| INSTALL-002 | Separar build no privilegiado del instalador root; instalar artefactos verificados correspondientes a la fuente certificada. |
| INSTALL-003 | Sustituir borrado previo de source/perfiles por staging versionado, preservación y rollback probado. |
| INSTALL-004 | Validar antes de activar claves/configuración SSH; respaldar y restaurar todos los recursos afectados ante fallos. |
| INSTALL-005 | Verificar semánticamente `ask-all`, `approvalGrantTtlMs=0` y la lista exacta de herramientas en defaults y perfiles efectivos. |

El rechazo de INSTALL-001 fue reproducido previamente con el parser real de relay. No se repitió aquí ni se convierte en corrección.
Las **10 pruebas históricas del inspector** y las **23 pruebas offline históricas del publicador** no certifican el instalador ni producción.

## GitHub y evidencia de esta continuación

La API autorizada confirmó `RHODIZSECURITY/ssh-mcp`, repositorio público, con `main` en `d52008a75aad68d957047935e1a252755aac1cc1` y sin rama de producto al realizar la consulta.
El checkout original de relay estaba limpio y en ese mismo SHA. Su digest canónico de 194 archivos coincidió con `6023fa8f3dbcbb22d272877703d10a55e58a75bea257f60b5c3650ec59359e6b`.
El proceso RDC seguía como root sin CAP_SETUID efectiva/permitida. No se alteraron sus protecciones ni se ejecutó npm como root. El acceso de build a Git/Docker no fue probado.
La revisión de preservación tiene límites documentados en el handoff privado: rechazos Git por propiedad distinta impiden certificar todos los repositorios. No interpretar ausencia de cambios realizados como una certificación completa.

Rama de seguimiento documental: `docs/remoteops-handoff-20260919`.
Rama de producto prevista: `feat/rhodiz-remoteops-mcp-20260919`, reservada para el flujo de certificación/publicación.
No usar esta rama documental como fuente desplegable ni integrarla automáticamente en el árbol certificado: cualquier cambio del árbol requiere nuevos digests y certificación.
No modificar `main`, sobrescribir ramas concurrentes ni desactivar comprobaciones de integridad. La publicación del producto requiere verificar el SHA remoto después del push.

## Continuación exacta

1. Recuperar continuidad por RHODIZ Memory MCP y leer el checkpoint vigente de Library. Si falta binding del proyecto, usar únicamente el fallback por ID expresamente autorizado; no seleccionar General implícitamente ni afirmar replay completo.
2. Obtener ejecución RDC autorizada como usuario de build en relay, sin evadir restricciones. Verificar UID, Git y Docker; renovar inventario y resolver los límites de preservación.
3. Corregir y probar los cinco hallazgos en un área aislada de relay. No ejecutar los instaladores originales ni aplicar transferencias parciales.
4. Generar nueva release, manifiesto, patch y hashes. Revisar y actualizar los hashes fijados en el publicador; conservar los gates.
5. Ejecutar certificación integral como usuario de build, incluidas pruebas negativas, rollback y preservación. CI es certificación, no depuración.
6. Publicar exclusivamente el SHA de producto certificado; verificarlo remotamente. Instalar después mediante staging/rollback y completar SSH, agente, túnel y aprobación E2E: rechazo, aprobación, cancelación y reconexión.

Mantener **ask-all** y **TTL cero**. No afirmar que estén certificados en producción hasta demostrarlo.
Después de cada hito y antes de cambiar de chat, actualizar RHODIZ Memory MCP, Library y la rama correspondiente con el punto exacto alcanzado. Confirmar cada escritura mediante respuesta y relectura; distinguir guardado documental, código certificado y deployment. Si una escritura falla, registrar el bloqueo sin afirmar sincronización.
