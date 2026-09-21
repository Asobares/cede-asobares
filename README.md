# C.E.D.E. — Ventanilla Única Digital Empresarial de Asobares Colombia

Documento de entrega funcional y técnica para Asobares y su webmaster.

**Versión:** piloto demostrativo, corte de entrega 18 de septiembre de 2026.
**Código de referencia:** 52312bcf22d854de7153cd0d0a79b695cc8925a3.
**Promotor:** Asobares Colombia.
**Dirección propuesta para una futura publicación:** `cede.asobares.org` (no configurada en esta entrega).
**Piloto alojado:** https://cede-asobares-piloto.camilo-ospina.chatgpt.site

## 1. En qué consiste

C.E.D.E. significa **Cédula Digital Empresarial**. Es una propuesta de ventanilla nacional para organizar en un expediente por establecimiento las evidencias asociadas a los requisitos del artículo 87 del Código Nacional de Seguridad y Convivencia Ciudadana, facilitar su consulta mediante QR y anticipar actualizaciones documentales.

Integra conceptualmente al empresario, Asobares, cámaras de comercio, Policía, autoridades territoriales y entidades relacionadas con requisitos especiales. Añade una Biblioteca de formación y normativa y un sistema de puntos por buenas prácticas.

La C.E.D.E. identifica el expediente; no constituye una licencia adicional ni una certificación oficial de cumplimiento integral. Las condiciones reales de operación pueden requerir inspección aunque existan documentos.

## 2. Qué se entrega y qué no está implementado

Se entrega **todo el código del piloto actual**, escrito en HTML, CSS y JavaScript, y los seis PDF alojados en su Biblioteca. Puede ejecutarse en un servidor estático sin ChatGPT, sin API de inteligencia artificial y sin compilación.

| Capacidad | Estado real de esta entrega |
|---|---|
| Navegación, interfaz adaptable, buscadores y filtros | Implementados |
| Perfil y expediente de un establecimiento ficticio | Implementados en el navegador |
| Registro de referencias y fechas documentales | Implementado; no carga archivos de empresarios |
| Semáforo y escenarios de prueba | Implementados; verificaciones simuladas |
| Puntos por buenas prácticas | Implementados con referencias, vigencia y validación simulada |
| Biblioteca | 26 recursos: 6 PDF locales, 19 documentos externos y 1 portal |
| Horarios de Bogotá | Investigación incorporada, con fuentes y corte de revisión |
| Otros municipios | Formulario y búsqueda externa; investigación pendiente |
| QR | Imagen escaneable hacia la consulta del sitio original; un expediente demo |
| Datos compartidos entre dispositivos | No implementados |
| Usuarios, contraseñas y permisos por entidad | No implementados dentro de la aplicación |
| Base de datos, servidor de negocio y API | No implementados |
| Consulta a cámaras, OSA o autoridades | No conectada |
| Correos, SMS o WhatsApp | No implementados |
| Actualización automática de normas | No implementada |
| Certificación o validación oficial | No implementada |

La restricción de acceso del sitio original depende de su alojamiento. **El código exportado no contiene ese control de acceso.** Si el webmaster publica la carpeta en un servidor público, cualquier visitante podrá abrirla y utilizar sus controles de simulación. No deben introducirse expedientes reales en esta versión.

## 3. Usuarios previstos

En producción se proponen cuatro perfiles, todavía sin implementar:

- **Empresario y delegado:** gestionar sus establecimientos y aportar evidencias.
- **Asobares:** administrar contenidos, acompañar empresarios y revisar evidencias dentro del alcance acordado.
- **Entidad competente / inspector IVC:** consultar información autorizada y registrar verificaciones atribuibles a su entidad.
- **Público:** consultar información mínima del QR y recursos que Asobares decida publicar.

El reconocimiento gremial y las verificaciones oficiales deben conservar identidades, atribuciones y responsabilidades diferenciadas.

## 4. Módulos y navegación

Las vistas usan fragmentos de URL; todas cargan el mismo `index.html`.

| Ruta | Módulo | Función |
|---|---|---|
| `#inicio` | Mi establecimiento | Perfil, semáforo, puntos, pendientes y acceso al QR |
| `#documentos` | Expediente digital | Matriz de controles, filtros, referencias y verificaciones de prueba |
| `#cedula` | Mi C.E.D.E. | Identificador, QR, impresión y enlace de consulta |
| `#practicas` | Buenas prácticas | Registro de evidencias, vigencias y puntos |
| `#alertas` | Alertas y vigencias | Seguimiento interno y actividad local |
| `#horarios` | Horarios por municipio | Municipio, departamento, actividad, zona y fuentes normativas |
| `#biblioteca` | Biblioteca | Buscar, filtrar, abrir y descargar recursos |
| `#entidades` | Entidades | Mapa de integraciones propuestas |
| `#verificar` | Consulta IVC | Consulta del código ficticio `DEMO-0001` |
| `#modelo` | Modelo del piloto | Alcance y arquitectura propuesta |

## 5. Matriz del expediente

El piloto desglosa los diez numerales del artículo 87 en doce controles, separando seguridad, sanidad y ambiente.

| ID en código | Control | Entidad o fuente prevista |
|---|---|---|
| `suelo` | Uso del suelo y destinación | Planeación municipal o distrital |
| `mercantil` | Matrícula y certificado | Cámara de Comercio de la jurisdicción / RUES |
| `apertura` | Comunicación de apertura | Policía Nacional |
| `moviles` | Comercialización de equipos móviles | MinTIC o delegado; condicionado a actividad |
| `ruido` | Intensidad auditiva | Autoridad competente; verificación técnica cuando corresponda |
| `horarios` | Horario de operación | Alcaldía y autoridades territoriales competentes |
| `seguridad` | Condiciones de seguridad | Autoridades locales según competencia |
| `sanidad` | Condiciones sanitarias | Secretaría de Salud territorial |
| `ambiente` | Condiciones ambientales | Autoridad ambiental territorial |
| `objeto` | Actividad registrada | Registro mercantil y contraste con operación real |
| `autor` | Derechos de autor y conexos | OSA y otros titulares o gestores según repertorio y legitimación |
| `rnt` | Registro Nacional de Turismo | Sistema RNT / cámaras / MinCIT; según actividad y normas especiales |

Los controles de música causante de pago, alojamiento y equipos móviles se activan desde el perfil. La clasificación «no aplica» es preliminar, no una decisión jurídica automática. El perfil inicial tiene diez controles aplicables.

### Estados internos

`pass`: verificado en simulación. `fail`: incumplimiento simulado. `ok`: evidencia ficticia, sin validación. `soon`: actualización próxima. `stale`: evidencia desactualizada. `pending`: pendiente. `visit`: requiere verificación en sitio. `na`: no aplica al perfil. `review`: referencia aportada, por validar.

Una referencia documental no pasa automáticamente a cumplimiento. Registrar una nueva referencia elimina la verificación simulada anterior del control.

## 6. Semáforo

Es un criterio operativo propuesto, no una clasificación sancionatoria legal.

| Color | Regla |
|---|---|
| Rojo | Más del 50 % de los controles aplicables tienen incumplimiento registrado, o falla un control crítico |
| Amarillo | No se configura rojo, pero faltan verificaciones, existen pendientes o evidencia mercantil desactualizada |
| Verde | Todos los controles aplicables tienen verificación positiva en la simulación y el certificado mercantil no supera 30 días |

**Críticos:** uso del suelo, matrícula mercantil vigente, seguridad y sanidad. En el código, marcar la renovación mercantil como no registrada también activa rojo. Esta simplificación debe revisarse al desarrollar producción: ausencia de dato y ausencia de renovación no son lo mismo.

Los «no aplica» se excluyen del denominador. Para el perfil inicial de diez controles, seis incumplimientos activan rojo por mayoría. Un incumplimiento crítico lo activa individualmente.

Los botones «Probar rojo», «Probar amarillo» y «Probar verde» reemplazan las verificaciones y referencias legales locales por un escenario demo. No deben existir en la operación institucional de producción.

## 7. Vigencias y alertas

- La regla de **30 días** corresponde a la antigüedad propuesta para la evidencia mercantil dentro de C.E.D.E.; no se atribuye al artículo 87 como renovación mensual obligatoria.
- Se muestra seguimiento desde el día 23; superar 30 días impide el verde.
- La renovación anual de matrícula es un control distinto; el piloto utiliza una casilla declarativa.
- Las preferencias de correo se guardan localmente; no se envía ningún mensaje.
- No hay tareas programadas: el seguimiento se calcula al abrir o renderizar la aplicación.
- La versión operativa deberá usar fechas confiables, zona horaria de Colombia y un proceso diario de notificación con registro de entrega.

## 8. Buenas prácticas — hasta 100 puntos

| Práctica | Puntos |
|---|---:|
| Conductores elegidos para clientes | 15 |
| Hidratación de cortesía | 10 |
| Alianza con parqueaderos | 10 |
| Taxis seguros verificados | 15 |
| Formaciones organizadas por Asobares | 20 |
| Implementación del programa «Pregunta por Ángela» | 10 |
| Opciones atractivas sin alcohol | 5 |
| Acuerdo de convivencia con vecinos | 5 |
| Formación en atención inclusiva | 5 |
| Alianza de aprovechamiento de residuos | 5 |
| **Total** | **100** |

Cada práctica exige una referencia, fecha de evidencia y fecha de revisión. La revisión no puede superar doce meses desde la evidencia; debe utilizarse un plazo menor si el soporte vence antes. Solo suma una práctica vigente con validación simulada positiva. Una evidencia pendiente o vencida aporta cero puntos.

El código impide repetir exactamente una referencia entre prácticas, sin distinguir mayúsculas. Esto no detecta por sí solo documentos duplicados con otro nombre; producción necesita identificadores y huellas de archivo.

La regla propuesta de formación Asobares pide dos formaciones distintas en doce meses, con participación conjunta de un responsable y personal operativo. Es un criterio del piloto, no un reglamento aprobado.

| Puntaje | Nivel |
|---|---|
| 0–39 | En camino |
| 40–69 | Comprometido |
| 70–89 | Destacado |
| 90–100 | Excelencia |

**Los puntos nunca modifican el semáforo legal.** El reconocimiento se activa desde 40 puntos y únicamente con semáforo verde. Con rojo o amarillo se conserva el puntaje y se suspende el reconocimiento. En todos los casos actuales es demostrativo.

## 9. Horarios por municipio

El formulario identifica ciudad, departamento, tipo de actividad y declaración de pertenencia a una zona extendida. No hay georreferenciación ni validación de polígonos.

La investigación incorporada para Bogotá tiene corte **18/09/2026** y remite al Decreto 644 de 2025 y su modificación mediante el Decreto 183 de 2026. Estas son las referencias del piloto, no una promesa de vigencia futura. Deben revisarse sus modificaciones y restricciones temporales antes de una decisión operativa.

Para otras ciudades, la interfaz registra el municipio y abre una búsqueda externa en dominios gubernamentales. No investiga, extrae ni valida automáticamente resultados. Cambiar municipio, actividad o zona desde este formulario borra la referencia y verificación previas del control de horarios.

Para producción: usar códigos municipales, catálogo de normas versionado, delimitación geográfica de zonas, vigencia temporal y revisión jurídica. Incorporar tanto actos generales como restricciones excepcionales. La detección actual de Bogotá por texto es una simplificación que debe reemplazarse.

## 10. Biblioteca

El catálogo reside en `web/catalog.js`. Contiene título, categoría, URL, fuente, nota, formato y un indicador de archivo local. Se carga antes de `app.js`.

Incluye seis PDF dentro del paquete:

1. Pregunta por Ángela — estrategia y protocolo.
2. Pregunta por Ángela — presentación.
3. Pregunta por Ángela — flyer.
4. Guía normativa Área en Vivo / Clúster de Música CCB, último archivo localizado en la web de Asobares, publicado en junio de 2026.
5. Artículo 87 — copia de consulta.
6. Artículo 93 — copia con notas de modificación y textos históricos identificados.

También enlaza cuatro protocolos: IVC sanitaria, IVC derechos de autor, IVC ambiental y visitas DIAN. Hay quince políticas y formatos adicionales y un acceso al portal de formación de Asobares.

Los 19 documentos externos **no están descargados en este ZIP**: se conservan sus enlaces originales y permisos. La fecha de publicación de la guía no garantiza la actualización de todas las normas citadas. Los PDF de los artículos son reproducciones para consulta, no copias certificadas.

Consultar `CATALOGO_BIBLIOTECA.md`, incluido en el ZIP, para el inventario completo y sus fuentes. La entrega no otorga una licencia abierta sobre documentos de terceros ni cambia sus permisos.

## 11. Cómo funciona técnicamente

### Estructura del paquete

| Archivo o carpeta | Propósito |
|---|---|
| `README.md` | Este documento |
| `CATALOGO_BIBLIOTECA.md` | Inventario completo con fuentes |
| `SHA256SUMS.txt` | Huellas de los archivos entregados |
| `web/index.html` | Estructura principal y carga de estilos y scripts |
| `web/style.css` | Apariencia, adaptación móvil e impresión |
| `web/catalog.js` | Catálogo de Biblioteca |
| `web/app.js` | Datos demo, navegación, formularios y reglas |
| `web/qr.svg` | QR estático del piloto original |
| `web/biblioteca/` | Seis documentos PDF locales |

No hay `package.json`, instalación npm, base de datos ni paso de compilación. Los archivos de `web/` son el código fuente y los archivos publicables del piloto.

### Persistencia

Se utiliza `localStorage`, clave `cede-pilot-v1`. El objeto `state` contiene perfil, referencias, verificaciones, eventos, preferencias, buenas prácticas y datos de horarios. Es un único expediente local, no una colección multiempresa.

El contenido es modificable por quien controla el navegador. No es una bitácora confiable ni un mecanismo de autenticación. No se sincroniza, respalda o migra automáticamente. Cambiar de dominio genera un almacenamiento independiente.

### Funciones principales

| Función | Responsabilidad |
|---|---|
| `render()` | Selección y renderizado de vista |
| `status()` | Estado por requisito |
| `assessment()` | Resultado del semáforo |
| `scenario()` | Carga de escenario demostrativo |
| `documentSave()` / `checkOne()` | Referencia y verificación simulada |
| `merit()` / `practiceStatus()` | Puntos y reconocimiento |
| `savePractice()` / `validatePractice()` | Evidencias de buenas prácticas |
| `hoursPage()` / `saveHours()` | Consulta territorial |
| `libraryPage()` / `filterLibrary()` | Biblioteca y filtros |
| `verify()` / `lookup()` | Consulta demo por código |

## 12. Ejecutar en el computador del webmaster

1. Descomprimir el ZIP.
2. Abrir una terminal en la carpeta `CEDE_Asobares`.
3. Con Python 3 instalado, ejecutar:

```bash
python -m http.server 8080 --bind 127.0.0.1 --directory web
```

En Windows puede utilizarse `py -m http.server 8080 --bind 127.0.0.1 --directory web`. En sistemas donde el ejecutable se llama `python3`, sustituir `python` por `python3`.

4. Abrir `http://localhost:8080` en el navegador.
5. Detener el servidor con Ctrl+C al terminar.

Este servidor es solo para revisión local. También puede usarse cualquier servidor estático existente. Conviene evitar abrir mediante `file://`, por diferencias de almacenamiento y permisos entre navegadores.

Para reiniciar los datos demo de ese origen, ejecutar en la consola del navegador:

```javascript
localStorage.removeItem('cede-pilot-v1');
location.reload();
```

Esto elimina únicamente el expediente de prueba guardado para ese origen.

## 13. Publicar en Asobares

### Opción de subdominio

1. El webmaster elige el alojamiento de la aplicación y crea su carpeta pública.
2. Sube **el contenido de `web/`**, conservando nombres y subcarpetas.
3. Configura `cede.asobares.org` con los valores DNS entregados por ese alojamiento. No hay un CNAME o IP universal en este paquete.
4. Habilita HTTPS.
5. Prueba las rutas, PDF, filtros y formularios con datos ficticios.
6. Añade en `www.asobares.org` un enlace «Ventanilla Única C.E.D.E.».
7. Mantiene visibles los avisos de demostración mientras no exista operación real.

El paquete puede alojarse fuera de ChatGPT. No requiere una cuenta de ChatGPT para ejecutarse en otro servidor.

### Opción dentro de la web principal

Se puede publicar bajo una carpeta como `/cede/` si el webmaster configura el servidor para servir estos archivos sin que el gestor de contenidos intercepte la ruta. Los recursos locales usan rutas relativas. No es un plugin WordPress y no debe pegarse `app.js` en el editor de una página.

### QR y textos que deben ajustarse antes de migrar

**El QR incluido apunta al sitio original**, a su vista `#verificar`. Cambiar el DNS o copiar archivos no cambia esa imagen. Regenerar `web/qr.svg` con la URL final del piloto en el nuevo dominio y probarlo desde un teléfono. La función de copiar enlace ya usa el origen y la ruta del navegador.

La cédula contiene un aviso relativo al acceso privado del alojamiento original. Ajustarlo para reflejar el acceso del nuevo alojamiento, manteniendo explícito que el expediente es ficticio. En producción, reemplazar el identificador único `DEMO-0001` y el QR fijo por un identificador opaco y una consulta en servidor para cada sede.

## 14. Desarrollo necesario para operar con datos reales

Estas capacidades son **diseño propuesto**, no código incluido:

1. Autenticación propia y recuperación de cuenta; permisos en servidor por usuario, entidad y establecimiento.
2. Base de datos central que separe empresas y sedes, con copias de respaldo y recuperación probada.
3. Almacenamiento privado de archivos, validación de tipo y tamaño, controles de acceso y versiones.
4. Reglas del semáforo calculadas en servidor y un historial de verificaciones atribuible al responsable.
5. Separación entre dato aportado, evidencia revisada por Asobares y respuesta oficial de una entidad.
6. QR por sede, respuesta pública mínima y acceso restringido a datos o documentos personales.
7. Notificaciones programadas con preferencias, historial de envío y reintentos.
8. Gestión editorial de Biblioteca y normativa por personal autorizado.
9. Integraciones autorizadas con entidades; una falla de conexión no debe declararse incumplimiento.
10. Revisión jurídica y de tratamiento de datos, pruebas de acceso entre empresas y operación con un grupo controlado de establecimientos.

### Modelo de datos orientativo

| Entidad | Datos esenciales |
|---|---|
| Empresa | Identificador, NIT, razón social |
| Establecimiento | Empresa, matrícula, municipio, dirección, actividad, ubicación |
| Usuario / membresía | Identidad, rol y establecimientos autorizados |
| Requisito | Norma, aplicabilidad, territorio y versión |
| Evidencia | Requisito, archivo privado, fechas, fuente y huella |
| Verificación | Evidencia, resultado, actor, entidad, fecha y motivo |
| Buena práctica | Criterio, puntaje, soporte, revisión y vigencia |
| Norma territorial | Acto, municipio, fuente, fechas, zonas y restricciones |
| Notificación | Destinatario autorizado, canal, motivo y entrega |
| Auditoría | Acción, responsable, momento y cambios |
| Recurso de Biblioteca | Título, archivo/enlace, versión, categoría y visibilidad |

## 15. Revisiones técnicas prioritarias del código demo

Antes de escalar, además del backend, revisar estos detalles observados:

- El formulario de horario reemplaza la gestión documental del control `horarios`; la demostración global permite marcarlo verificado sin constancia individual. En producción debe existir una actuación trazable.
- Las fechas usan el reloj del navegador y una referencia calculada al cargar la página. Reemplazarlo por una política uniforme de fechas en servidor.
- El aviso mercantil aparece al llegar al día 30, mientras el estado desactualizado se calcula al superar 30; armonizar texto y umbral.
- Cambiar la ciudad desde «Editar establecimiento» elimina la verificación de horario, pero puede conservar una referencia previa. Invalidar conjuntamente evidencia y verificación en producción.
- Las marcas «no aplica» deben validarse por actividad y normas especiales, no solo por casillas.
- El código usa manejadores de eventos en HTML; una política de seguridad de contenidos estricta requerirá refactorizarlos.
- La lectura del navegador incluye escape de textos, pero esto no reemplaza validación en servidor, gestión de sesiones ni pruebas de seguridad.
- Revisar los documentos externos con las cuentas destinatarias: conservar un enlace no garantiza permiso de lectura.

## 16. Prueba de aceptación del piloto

- Abrir los diez módulos sin errores de JavaScript.
- Editar un nombre ficticio, recargar y confirmar persistencia en ese navegador.
- Probar rojo, amarillo y verde; revisar los criterios.
- Registrar una buena práctica, simular validación y comprobar sus puntos.
- Verificar que los puntos no cambien el color legal.
- Consultar `DEMO-0001` y un código inexistente.
- Elegir Bogotá y después otro municipio: no trasladar sus horarios al otro municipio.
- Buscar «Ángela» y filtrar «Protocolos» en Biblioteca.
- Abrir los seis PDF y comprobar los enlaces externos según permisos.
- Tras migrar, escanear el QR y verificar que vaya al dominio elegido.

Se comprobaron sintaxis JavaScript, lógica básica del semáforo y puntos, rutas y presencia de archivos locales durante la construcción. Esta entrega no constituye una auditoría de seguridad ni prueba integral multiusuario.

## 17. Fuentes incorporadas

Las referencias siguientes corresponden a la investigación previa incorporada al piloto; la exportación no realiza una nueva certificación de vigencia:

- [Ley 1801 de 2016 — Régimen Legal de Bogotá](https://www.alcaldiabogota.gov.co/sisjur/normas/Norma1.jsp?i=66661).
- [Decreto 644 de 2025 — Bogotá](https://www.alcaldiabogota.gov.co/sisjur/normas/Norma1.jsp?i=191864).
- [Decreto 183 de 2026 — Bogotá](https://www.alcaldiabogota.gov.co/sisjur/normas/Norma1.jsp?i=193251).
- [Pregunta por Ángela — Asobares](https://asobares.org/angela/).
- [Documentos legales y protocolos — Asobares](https://asobares.org/documentos-legales/).
- [Guía normativa publicada por Asobares](https://asobares.org/wp-content/uploads/2026/06/Guia-normativa.pdf).
- [Biblioteca virtual Asobares](https://asobares-biblioteca.vercel.app/).

## 18. Alcance del paquete y continuidad

La carpeta `web/` reproduce los archivos publicados del piloto de referencia. El ZIP omite el historial Git, credenciales y metadatos internos del alojamiento. No contiene un backend oculto ni conexiones institucionales adicionales.

La primera entrega al webmaster permite revisar y publicar una demostración independiente. El siguiente hito de desarrollo consiste en sustituir la persistencia local y las verificaciones de prueba por cuentas propias, datos centrales y revisión atribuible a responsables autorizados.
