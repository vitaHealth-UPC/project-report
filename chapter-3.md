# Capítulo III: Solution UI/UX Design



## 3.1. Product design



### 3.1.1. Style Guidelines

Tata utiliza una identidad visual común en la landing y la aplicación: tipografía legible, superficies suaves y controles amplios.



#### 3.1.1.1. General Style Guidelines



##### Branding

La marca Tata utiliza un isotipo de mariposa y un logotipo en Dancing Script. El nombre expresa cercanía con el adulto mayor.

<p align="center">
  <img src="./assets/Tata.png" alt="Logotipo de Tata" width="320">
</p>

##### Typography

**Escala tipográfica:**

| Tipografía | Uso | Pesos disponibles |
| --- | --- | --- |
| DM Serif Display | Display / headings | Regular |
| Inter | UI / body | Regular, Medium, Semi Bold, Bold |
| Dancing Script | Brand only (wordmark "Tata") | Bold |

| Nivel | Tamaño | Fuente | Uso |
| --- | --- | --- | --- |
| Display / H1 | 34 sp | DM Serif Display | Títulos de pantalla y hitos importantes (p. ej. resumen semanal de adherencia) |
| Display / H2 | 29 sp | DM Serif Display | Subtítulos de sección |
| Page title | 24 sp | DM Serif Display | Título de pantalla |
| UI title | 20 sp | Inter Semi Bold | Acciones, navegación |
| Body | 16 sp | Inter Regular | Formularios y contenido, incluyendo dosis, medicamento y horario |
| Label | 13 sp | Inter Medium | Etiquetas de campos y estados |
| Caption | 11 sp | Inter Regular | Metadata secundaria o navegación |

<p align="center">
  <img src="./assets/tata-design-foundations-colors-typography.png" alt="Tata Design Foundations: paleta de colores y tipografía" width="960">
</p>

*Figura. Paleta de colores y sistema tipográfico de Tata Design Foundations.*

##### Colors

El sistema visual utiliza texto e iconos para identificar los estados y contempla contraste legible sobre las superficies.

| Token | Valor | Uso |
| --- | --- | --- |
| Primary | `#173B70` | Navegación, elementos activos y acentos de identidad. |
| Ink | `#0E1729` | Texto principal sobre fondos claros. |
| Secondary | `#7B879B` | Texto secundario e iconografía inactiva. |
| Lavender | `#F1ECFF` | Superficie para contenido de seguimiento y vínculo familiar. |
| Sage | `#E8F5EB` | Estados positivos o de confirmación (toma registrada). |
| Cream | `#FFF3E2` | Estados pendientes o de atención moderada (toma por confirmar). |
| Canvas | `#F8F8FE` | Fondo general de las pantallas. |

##### Spacing

El CTA principal (56-64 dp) es más alto que el touch target mínimo para reducir errores de precisión en el adulto mayor.

| Token | Valor | Descripción |
| --- | --- | --- |
| Grid base | 8 dp | Espaciado principal en múltiplos de 8, 4 dp solo para microajustes. |
| Touch target | 44  x  44 dp | Área táctil mínima para botones, íconos y controles. |
| Card radius | 16-24 dp | 16 dp en controles, 20-24 dp en cards, 28+ dp en superficies hero. |
| Page padding | 16-24 dp | 16 dp como mínimo, 20-24 dp recomendado para contenido principal. |
| Primary CTA | 56-64 dp de altura | Confirmaciones y acciones principales, como confirmar una toma. |
| Focus | 1 acción primaria | Una única acción dominante por pantalla. |

<p align="center">
  <img src="./assets/tata-design-foundations-layout-interaction.png" alt="Tata Design Foundations: escala tipográfica y reglas de layout e interacción" width="960">
</p>

*Figura. Escala tipográfica y reglas de Layout & Interaction de Tata Design Foundations.*

##### Tono de comunicación

| Dimensión | Posición de Tata | Sustento |
| --- | --- | --- |
| Divertido / Serio | Serio, con calidez | Tata acompaña decisiones de salud, el humor le restaría seriedad a un recordatorio o a una alerta de omisión. |
| Formal / Casual | Casual, sin jerga | El adulto mayor necesita frases simples y directas, el familiar recibe el mismo registro para mantener consistencia. |
| Respetuoso / Irreverente | Respetuoso | Nunca condescendiente con el adulto mayor con el familiar, los mensajes son objetivos, sin dramatizar. |
| Entusiasta / Sereno | Sereno | Incluso en alertas por tomas no confirmadas, el mensaje informa con calma y propone una acción, sin generar pánico. |

### 3.1.2. Information Architecture

La información se organiza para el adulto mayor, el familiar o cuidador y el visitante de la landing. Cada perfil dispone de navegación y contenido acordes con sus acciones principales.



#### 3.1.2.1. Organization Systems

El contenido se organiza por perfil, secuencia de acciones y estado de las tomas.

| Sistema | Aplicación |
| --- | --- |
| Jerárquico | Próxima toma en Inicio, alertas en el resumen familiar y propuesta de valor en la landing |
| Secuencial | Registro, verificación, vinculación y configuración del tratamiento |
| Matricial | Agenda por horarios e historial por periodos y estados |

| Categorización | Contenido |
| --- | --- |
| Por audiencia | Adulto mayor, familiar o cuidador y visitante |
| Cronológica | Tomas, alertas y notas de seguimiento |
| Por tema | Medicación, adherencia, alertas y cuenta |

#### 3.1.2.2. Labelling Systems

Todas las etiquetas de Tata siguen la convención **verbo + objeto** ya definida en Tata Design Foundations (p.



##### Etiquetas de acción

| Etiqueta | Historia relacionada | Aplica en |
| --- | --- | --- |
| Confirmar toma | US-06 | Adulto mayor |
| Ver medicación | US-19, US-21 | Adulto mayor y Familiar |
| Registrar medicamento | US-03 | Familiar |
| Editar horario | US-16 | Familiar |
| Pausar tratamiento | US-18 | Familiar |
| Registrar nota | US-30 | Familiar |
| Contactar al adulto mayor | US-29 | Familiar |
| Cambiar plan | US-45 | Familiar |
| Comenzar registro | US-49 | Visitante (Landing Page) |

##### Etiquetas de estado

| Etiqueta | Token de color | Refuerzo adicional | Significado |
| --- | --- | --- | --- |
| Confirmado | Sage | Ícono de check | La toma fue registrada dentro del horario esperado. |
| Pendiente | Cream | Ícono de reloj | La toma aún no se confirma, dentro de la ventana permitida. |
| Tardía | Cream | Ícono de reloj con alerta | La toma se confirmó después del horario, dentro del periodo de tolerancia (US-23). |
| Sin confirmar / Alerta | Cream | Ícono de alerta | La toma no fue confirmada y requiere atención del familiar (US-07, US-27); se evita un color rojo de alarma para mantener el tono "sereno" ya definido en 3.1.1. |

##### Etiquetas de navegación y formularios

| Elemento | Convención | Ejemplo |
| --- | --- | --- |
| Íconos de navegación | Texto siempre visible junto al ícono, nunca solo | "Inicio", "Medicación", "Adherencia", "Alertas", "Cuenta" |
| Campos de formulario | Label persistente, no placeholder como único indicador | "Nombre del medicamento" visible aunque el campo tenga contenido de ejemplo |
| Unidades clínicas | Formato claro, sin abreviaturas ambiguas | "500 mg", "8:00 a.m.", nunca "500mg" pegado ni "8am" sin espacio |

#### 3.1.2.3. SEO Tags and Meta Tags

**Landing Page**

| Meta tag | Contenido |
| --- | --- |
| Title | Tata - Adherencia a la medicación para adultos mayores |
| Description | App que ayuda a adultos mayores a confirmar su medicación y a sus familiares a monitorear el tratamiento en tiempo real. |
| Keywords | adherencia al tratamiento, medicación adultos mayores, cuidado remoto, recordatorio de medicamentos, salud digital Perú |
| Author | VitaHealth |

| Elemento ASO | Contenido |
| --- | --- |
| App Title | Tata: Medicación y Cuidado |
| App subtitle | Confirma tus medicinas, cuida a tu familia |
| App keywords | medicación, adulto mayor, recordatorio, adherencia, cuidado familiar, salud |
| App description | Tata ayuda a adultos mayores a confirmar sus medicamentos con un solo toque o por voz, y permite a sus familiares monitorear el tratamiento desde cualquier lugar. Recibe alertas si una toma no se confirma y accede a reportes de adherencia para actuar a tiempo. |

#### 3.1.2.4. Searching Systems



#### 3.1.2.5. Navigation Systems



##### App del adulto mayor

Navegación reducida a lo esencial, con un máximo de 3 accesos principales para minimizar la carga cognitiva identificada en las entrevistas:

| Sección | Contenido | Historias relacionadas |
| --- | --- | --- |
| Inicio | Próxima toma y confirmación por toque o voz | US-20, US-06, TS-11 |
| Mi medicación | Agenda diaria y detalle de cada tratamiento (solo lectura) | US-24, US-19, US-21 |
| Ajustes | Accesibilidad: tamaño de texto, contraste, lectura asistida | US-35, US-36, US-38 |

##### App del familiar o cuidador

Barra de navegación inferior con 5 secciones, el máximo definido en Tata Design Foundations:

| Tab | Contenido | Epic |
| --- | --- | --- |
| Inicio | Estado reciente del adulto mayor y alertas abiertas | EPIC-04 |
| Medicación | Tratamientos, medicamentos e inventario | EPIC-02, EPIC-07 |
| Adherencia | Resumen semanal, historial y patrones detectados | EPIC-05 |
| Alertas | Detalle, contacto y seguimiento de alertas | EPIC-04 |
| Cuenta | Vínculo, plan/suscripción y accesibilidad | EPIC-01, EPIC-08, EPIC-06 |

##### Landing Page

Navegación de una sola página con anclas, sin cambiar de URL entre secciones, para que el visitante recorra la propuesta de valor sin fricción:

| Sección (ancla) | Contenido | Historia relacionada |
| --- | --- | --- |
| Inicio | Propuesta de valor de Tata | US-46 |
| Funcionalidades | Principales funcionalidades del producto | US-47 |
| Planes | Comparación de planes disponibles | US-48 |
| Comenzar | CTA hacia registro o contacto | US-49 |

### 3.1.3. Landing Page UI Design

La landing presenta la propuesta de Tata, sus funcionalidades, planes y contacto. Las versiones desktop y mobile comparten el contenido y adaptan su distribución al ancho de pantalla.

<p align="center">
  <img src="assets/landing-foundations.png" alt="Fundamentos visuales de la landing" width="960">
</p>

*Figura. Fundamentos de diseño de la landing page. Nota. Elaboración propia; exportación del tablero de Figma.*

Enlace a tablero de figma:

https://www.figma.com/design/jCppvxtSpLpHOrC3ZWUIVC/VitaHealth?node-id=557-2


#### 3.1.3.1. Landing Page Wireframe

Los wireframes definen la navegación, el orden de las secciones y la distribución del contenido en desktop y mobile.

<p align="center">
  <img src="assets/landing-page-wireframe-desktop.png" alt="Wireframe de la landing page en versión desktop" width="960">
</p>

*Figura. Wireframe desktop de la landing page de Tata.*

*Nota. Elaboración propia.*

<p align="center">
  <img src="assets/landing-page-wireframe-mobile.png" alt="Wireframe de la landing page en versión mobile" width="960">
</p>

*Figura. Wireframe mobile de la landing page de Tata.*

*Nota. Elaboración propia.*

Wireframes originales: desktop y mobile:

https://www.figma.com/design/jCppvxtSpLpHOrC3ZWUIVC/VitaHealth?node-id=546-2


#### 3.1.3.2. Landing Page Mock-up

Los mockups aplican la identidad de Tata sobre la estructura de la landing, con fotografía, tarjetas, tipografía y botones adaptados a ambos formatos.

<p align="center">
  <img src="assets/landing-page-mockup-desktop.png" alt="Mock-up de la landing page en versión desktop" width="960">
</p>

*Figura. Mock-up desktop de la landing page de Tata.*

*Nota. Elaboración propia.*

<p align="center">
  <img src="assets/landing-page-mockup-mobile.png" alt="Mock-up de la landing page en versión mobile" width="960">
</p>

*Figura. Mock-up mobile responsive de la landing page de Tata.*

*Nota. Elaboración propia.*

Mock-ups originales: desktop y mobile:

https://www.figma.com/design/jCppvxtSpLpHOrC3ZWUIVC/VitaHealth?node-id=400-2


### 3.1.4. Mobile Applications UX/UI Design

El diseño móvil comprende 70 variantes en español, organizadas en diez filas de siete vistas. Incluye pantallas principales, validaciones y resultados de las acciones.



#### 3.1.4.1. Mobile Applications Wireframes

Las diez filas de wireframes presentan la estructura, los campos y las acciones de las 70 variantes.

Fuente: tablero de Figma:

https://www.figma.com/design/jCppvxtSpLpHOrC3ZWUIVC/VitaHealth?node-id=260-2


##### 01. Entry, Onboarding & Access

El acceso reúne la landing resumida, onboarding, registro, vinculación, PIN e inicio de sesión. Los campos y acciones conservan una jerarquía común.

**Pantallas incluidas:** 01 Landing - Value & Features; 02 Landing - Plans & Contact; 03 Onboarding; 04 Caregiver Registration; 05 Link & Consent; 06 PIN Access; 07 Login.

<p align="center">
  <img src="assets/mobile-app-wireframes-entry-onboarding-access.png" alt="Wireframes de entrada, onboarding y acceso" width="960">
</p>

*Figura. Wireframes de entrada, onboarding y acceso a Tata.*

*Nota. Elaboración propia.*

##### 02. Older Adult Daily Experience

La experiencia del adulto mayor reúne Inicio, medicamentos, detalle, agenda, confirmación de toma y accesibilidad. La próxima toma ocupa el primer nivel de atención.

**Pantallas incluidas:** 08 Home; 09 My Medications; 10 Medication Detail; 11 Weekly Schedule; 12 Voice Confirmation; 13 Dose Confirmed; 14 Accessibility.

<p align="center">
  <img src="assets/mobile-app-wireframes-older-adult-daily-experience.png" alt="Wireframes de la experiencia diaria del adulto mayor" width="960">
</p>

*Figura. Wireframes de la experiencia diaria del adulto mayor.*

*Nota. Elaboración propia.*

##### 03. Monitoring, Insights & Adult Notes

El seguimiento reúne el resumen familiar, persona vinculada, alertas, historial, recomendaciones y notas del adulto mayor. El estado reciente y las acciones de seguimiento se presentan en tarjetas.

**Pantallas incluidas:** 15 Family Summary; 16 Linked Person; 17 Alerts; 18 Alert Detail; 19 History & Insights; 20 Adherence Recommendations; 21 Notes - Adult.

<p align="center">
  <img src="assets/mobile-app-wireframes-monitoring-insights-adult-notes.png" alt="Wireframes de seguimiento, insights y notas del adulto mayor" width="960">
</p>

*Figura. Wireframes de seguimiento familiar, alertas, insights y notas del adulto mayor.*

*Nota. Elaboración propia.*

##### 04. Caregiver Treatment Management & Notes

La gestión del cuidador reúne el registro de medicamentos, la creación y administración del tratamiento, inventario, notificaciones, notas y suscripción.

**Pantallas incluidas:** 22 Add Medication - Caregiver; 23 Create Treatment; 24 Treatment Management; 25 Inventory & Restock; 26 Notification Preferences; 27 Notes - Caregiver; 28 Plan & Subscription.

<p align="center">
  <img src="assets/mobile-app-wireframes-caregiver-treatment-management-notes.png" alt="Wireframes de gestión del tratamiento y notas del cuidador" width="960">
</p>

*Figura. Wireframes de gestión del tratamiento, inventario, notificaciones, notas y suscripción.*

*Nota. Elaboración propia.*

##### 05. Access, Registration & Consent States

Las variantes de acceso muestran la creación de PIN, credenciales incorrectas, bloqueo, correo duplicado, verificación vencida, código inválido y consentimiento requerido.

**Pantallas incluidas:** 29 PIN Setup; 30 PIN Incorrect; 31 PIN Temporarily Blocked; 32 Duplicate Email; 33 Verification Expired; 34 Invalid Link Code; 35 Consent Required.

<p align="center">
  <img src="assets/mobile-app-wireframes-access-registration-consent-states.png" alt="Wireframes de validaciones de acceso, registro y consentimiento" width="960">
</p>

*Figura. Wireframes de validaciones de acceso, registro y consentimiento.*

*Nota. Elaboración propia.*

##### 06. Medication, Reminder & Adherence States

Las variantes de medicación muestran validaciones, edición, desactivación, recordatorio de toma, error de voz, toma ya confirmada y ausencia de datos de adherencia.

**Pantallas incluidas:** 36 Medication Required Fields Error; 37 Medication Updated; 38 Medication Deactivated; 39 Medication Reminder Due; 40 Voice Not Recognized; 41 Dose Already Confirmed; 42 No Adherence Data.

<p align="center">
  <img src="assets/mobile-app-wireframes-medication-reminder-adherence-states.png" alt="Wireframes de estados de medicamentos, recordatorios y adherencia" width="960">
</p>

*Figura. Wireframes de validaciones de medicamentos, recordatorios y adherencia.*

*Nota. Elaboración propia.*

##### 07. Treatment & Dose States

Las variantes del tratamiento muestran datos incompletos, pausa, acceso restringido, ausencia de próxima toma y detalle de toma pendiente, confirmada o tardía.

**Pantallas incluidas:** 43 Treatment Incomplete; 44 Treatment Paused; 45 Treatment Access Denied; 46 No Next Dose; 47 Dose Detail - Pending; 48 Dose Detail - Confirmed; 49 Dose Detail - Late.

<p align="center">
  <img src="assets/mobile-app-wireframes-treatment-dose-states.png" alt="Wireframes de estados de tratamiento y toma" width="960">
</p>

*Figura. Wireframes de estados de tratamiento y de una toma.*

*Nota. Elaboración propia.*

##### 08. Omission, Reinforcement & Follow-up States

Las variantes de seguimiento de la toma muestran omisión, recordatorio reforzado, confirmación tardía, agenda con estados, historial vacío y contacto no disponible.

**Pantallas incluidas:** 50 Dose Detail - Omitted; 51 Reinforced Reminder; 52 Late Dose Confirmed; 53 Omission Preserved; 54 Agenda With Statuses; 55 Empty Intake History; 56 Contact Unavailable.

<p align="center">
  <img src="assets/mobile-app-wireframes-omission-reinforcement-follow-up.png" alt="Wireframes de omisiones, recordatorios reforzados y seguimiento" width="960">
</p>

*Figura. Wireframes de omisiones, recordatorios reforzados y seguimiento.*

*Nota. Elaboración propia.*

##### 09. Follow-up & Accessibility States

Las variantes de seguimiento y accesibilidad muestran notas guardadas, alertas atendidas, cambio de periodo, evidencia insuficiente, texto grande, contraste y movimiento reducido.

**Pantallas incluidas:** 57 Follow-up Note Saved; 58 Alert Attended; 59 Adherence Period Changed; 60 Insufficient Evidence; 61 Large Text Enabled; 62 High Contrast Enabled; 63 Reduced Motion Enabled.

<p align="center">
  <img src="assets/mobile-app-wireframes-follow-up-accessibility-states.png" alt="Wireframes de seguimiento y accesibilidad" width="960">
</p>

*Figura. Wireframes de seguimiento, evidencia y configuraciones de accesibilidad.*

*Nota. Elaboración propia.*

##### 10. Preferences, Inventory, Subscription & Internationalization

Las variantes finales muestran ayuda de lectura, preferencias guardadas, validación de inventario, reposición, suscripción, destino externo e idioma.

**Pantallas incluidas:** 64 Reading Assistance Enabled; 65 Notification Preferences Saved; 66 Invalid Inventory Quantity; 67 Stock Replenished; 68 Subscription Updated; 69 External Destination Unavailable; 70 Internationalization.

<p align="center">
  <img src="assets/mobile-app-wireframes-preferences-inventory-subscription-states.png" alt="Wireframes de preferencias, inventario, suscripción e internacionalización" width="960">
</p>

*Figura. Wireframes de preferencias guardadas, inventario, suscripción, destino externo e internacionalización.*

*Nota. Elaboración propia.*

#### 3.1.4.2. Mobile Applications Wireflow Diagrams

Los dieciséis wireflows relacionan los objetivos de ambos perfiles con las vistas y sus resultados alternos.



##### WF01. Acceso con PIN y consulta de próxima toma

El adulto mayor crea o ingresa su PIN y consulta la próxima toma. El recorrido incluye PIN incorrecto, bloqueo y ausencia de una toma programada.

<p align="center">
  <img src="assets/mobile-app-wireflow-pin-access-next-dose.png" alt="WF01 acceso con PIN y próxima toma" width="960">
</p>

*Figura. WF01, acceso con PIN y consulta de la próxima toma.*

*Nota. Elaboración propia.*

##### WF02. Confirmación de una toma por toque o por voz

El adulto mayor confirma una toma por toque o voz. El flujo incluye voz no reconocida, toma ya confirmada, registro tardío y omisión.

<p align="center">
  <img src="assets/mobile-app-wireflow-dose-confirmation.png" alt="WF02 confirmación de toma" width="960">
</p>

*Figura. WF02, confirmación de una toma por toque o por voz y estados posteriores.*

*Nota. Elaboración propia.*

##### WF03. Consulta de medicamentos y estados de una pauta

El adulto mayor consulta sus medicamentos y abre el detalle de una toma. Los estados distinguen tomas pendientes, confirmadas, tardías y omitidas.

<p align="center">
  <img src="assets/mobile-app-wireflow-medications-dose-states.png" alt="WF03 medicamentos y estados de toma" width="960">
</p>

*Figura. WF03, consulta de medicamentos y estados de una pauta.*

*Nota. Elaboración propia.*

##### WF04. Consulta de agenda y visualización de estados

El adulto mayor consulta la agenda y reconoce el estado de las tomas programadas.

<p align="center">
  <img src="assets/mobile-app-wireflow-schedule-dose-statuses.png" alt="WF04 agenda y estados" width="960">
</p>

*Figura. WF04, consulta de agenda semanal y visualización de estados.*

*Nota. Elaboración propia.*

##### WF05. Configuración de accesibilidad

El adulto mayor ajusta texto, contraste, movimiento, ayuda de lectura e idioma desde Accesibilidad.

<p align="center">
  <img src="assets/mobile-app-wireflow-accessibility-preferences.png" alt="WF05 accesibilidad" width="960">
</p>

*Figura. WF05, configuración y persistencia de preferencias de accesibilidad.*

*Nota. Elaboración propia.*

##### WF06. Registro y vinculación del familiar o cuidador

El familiar crea su cuenta, verifica el correo y solicita un vínculo con consentimiento del adulto mayor. El flujo incluye validaciones del registro y del código.

<p align="center">
  <img src="assets/mobile-app-wireflow-registration-link-consent.png" alt="WF06 registro y vinculación" width="960">
</p>

*Figura. WF06, registro, verificación y vinculación con consentimiento.*

*Nota. Elaboración propia.*

##### WF07. Registro de medicamento y gestión del tratamiento

El familiar registra un medicamento, define la pauta y administra el tratamiento. Las variantes muestran datos incompletos, pausa y acceso restringido.

<p align="center">
  <img src="assets/mobile-app-wireflow-medication-treatment-management.png" alt="WF07 medicamento y tratamiento" width="960">
</p>

*Figura. WF07, registro de medicamento y gestión del tratamiento.*

*Nota. Elaboración propia.*

##### WF08. Seguimiento familiar, historial y alertas

El familiar consulta el resumen, historial y alertas. Los resultados incluyen historial vacío, ausencia de datos y cambio de periodo.

<p align="center">
  <img src="assets/mobile-app-wireflow-family-history-alerts.png" alt="WF08 seguimiento historial y alertas" width="960">
</p>

*Figura. WF08, seguimiento familiar, historial y alertas.*

*Nota. Elaboración propia.*

##### WF09. Atención de alertas e intervención del cuidador

El familiar abre una alerta y registra una intervención mediante contacto o nota. El resultado identifica la alerta atendida y la indisponibilidad del contacto.

<p align="center">
  <img src="assets/mobile-app-wireflow-alert-intervention.png" alt="WF09 atención de alertas" width="960">
</p>

*Figura. WF09, atención de alertas y registro de intervención.*

*Nota. Elaboración propia.*

##### WF10. Recomendaciones basadas en evidencia

El familiar consulta recomendaciones y revisa el tratamiento asociado. El flujo distingue los periodos con datos y los resultados con evidencia insuficiente.

<p align="center">
  <img src="assets/mobile-app-wireflow-evidence-recommendations.png" alt="WF10 recomendaciones y evidencia" width="960">
</p>

*Figura. WF10, análisis de adherencia y recomendaciones basadas en evidencia.*

*Nota. Elaboración propia.*

##### WF11. Inventario y reposición

El familiar consulta el stock y registra una reposición. La validación conserva el inventario ante cantidades inválidas.

<p align="center">
  <img src="assets/mobile-app-wireflow-inventory-restock.png" alt="WF11 inventario y reposición" width="960">
</p>

*Figura. WF11, control de inventario y registro de reposición.*

*Nota. Elaboración propia.*

##### WF12. Preferencias de notificación

El familiar configura las preferencias de notificación y guarda los cambios.

<p align="center">
  <img src="assets/mobile-app-wireflow-notification-preferences.png" alt="WF12 preferencias de notificación" width="960">
</p>

*Figura. WF12, configuración y guardado de preferencias de notificación.*

*Nota. Elaboración propia.*

##### WF13. Plan y suscripción

El familiar consulta su plan, elige una opción y recibe la confirmación del cambio de suscripción.

<p align="center">
  <img src="assets/mobile-app-wireflow-plan-subscription.png" alt="WF13 plan y suscripción" width="960">
</p>

*Figura. WF13, consulta y actualización del plan de suscripción.*

*Nota. Elaboración propia.*

##### WF14. Edición o desactivación de un medicamento

El familiar edita o desactiva un medicamento desde la gestión del tratamiento.

<p align="center">
  <img src="assets/mobile-app-wireflow-edit-disable-medication.png" alt="WF14 editar y desactivar medicamento" width="960">
</p>

*Figura. WF14, edición y desactivación de un medicamento.*

*Nota. Elaboración propia.*

##### WF15. Recordatorio reforzado, confirmación tardía y omisión

El adulto mayor recibe un recordatorio reforzado y confirma la toma dentro del periodo de tolerancia. La omisión conserva su estado cuando corresponde.

<p align="center">
  <img src="assets/mobile-app-wireflow-reinforced-reminder-late-omission.png" alt="WF15 recordatorio reforzado confirmación tardía y omisión" width="960">
</p>

*Figura. WF15, recordatorio reforzado, confirmación tardía y omisión.*

*Nota. Elaboración propia.*

##### WF16. Landing, comparación de planes y destino externo no disponible

El visitante consulta la propuesta de Tata, compara planes y continúa hacia acceso, registro o contacto. El recorrido incluye un destino externo no disponible.

<p align="center">
  <img src="assets/mobile-app-wireflow-landing-plans-external-destination.png" alt="WF16 landing planes y destino externo" width="960">
</p>

*Figura. WF16, navegación del visitante, comparación de planes y destino externo no disponible.*

*Nota. Elaboración propia.*

#### 3.1.4.3. Mobile Applications Mock-ups

Los mockups presentan las mismas 70 variantes con el sistema visual de Tata y conservan la numeración de los wireframes.

tablero de mock-ups:

https://www.figma.com/design/jCppvxtSpLpHOrC3ZWUIVC/VitaHealth?node-id=31-2


##### 01. Entry, Onboarding & Access

El acceso reúne la landing resumida, onboarding, registro, vinculación, PIN e inicio de sesión. Los campos y acciones conservan una jerarquía común.

**Pantallas incluidas:** 01 Landing - Value & Features; 02 Landing - Plans & Contact; 03 Onboarding; 04 Caregiver Registration; 05 Link & Consent; 06 PIN Access; 07 Login.

<p align="center">
  <img src="assets/mobile-app-mockups-entry-onboarding-access.png" alt="Mock-ups de entrada, onboarding y acceso" width="960">
</p>

*Figura. Mock-ups de entrada, onboarding y acceso a Tata.*

*Nota. Elaboración propia.*

##### 02. Older Adult Daily Experience

La experiencia del adulto mayor reúne Inicio, medicamentos, detalle, agenda, confirmación de toma y accesibilidad. La próxima toma ocupa el primer nivel de atención.

**Pantallas incluidas:** 08 Home; 09 My Medications; 10 Medication Detail; 11 Weekly Schedule; 12 Voice Confirmation; 13 Dose Confirmed; 14 Accessibility.

<p align="center">
  <img src="assets/mobile-app-mockups-older-adult-daily-experience.png" alt="Mock-ups de la experiencia diaria del adulto mayor" width="960">
</p>

*Figura. Mock-ups de la experiencia diaria del adulto mayor.*

*Nota. Elaboración propia.*

##### 03. Monitoring, Insights & Adult Notes

El seguimiento reúne el resumen familiar, persona vinculada, alertas, historial, recomendaciones y notas del adulto mayor. El estado reciente y las acciones de seguimiento se presentan en tarjetas.

**Pantallas incluidas:** 15 Family Summary; 16 Linked Person; 17 Alerts; 18 Alert Detail; 19 History & Insights; 20 Adherence Recommendations; 21 Notes - Adult.

<p align="center">
  <img src="assets/mobile-app-mockups-monitoring-insights-adult-notes.png" alt="Mock-ups de seguimiento, insights y notas del adulto mayor" width="960">
</p>

*Figura. Mock-ups de seguimiento familiar, alertas, insights y notas del adulto mayor.*

*Nota. Elaboración propia.*

##### 04. Caregiver Treatment Management & Notes

La gestión del cuidador reúne el registro de medicamentos, la creación y administración del tratamiento, inventario, notificaciones, notas y suscripción.

**Pantallas incluidas:** 22 Add Medication - Caregiver; 23 Create Treatment; 24 Treatment Management; 25 Inventory & Restock; 26 Notification Preferences; 27 Notes - Caregiver; 28 Plan & Subscription.

<p align="center">
  <img src="assets/mobile-app-mockups-caregiver-treatment-management-notes.png" alt="Mock-ups de gestión del tratamiento y notas del cuidador" width="960">
</p>

*Figura. Mock-ups de gestión del tratamiento, inventario, notificaciones, notas y suscripción.*

*Nota. Elaboración propia.*

##### 05. Access, Registration & Consent States

Las variantes de acceso muestran la creación de PIN, credenciales incorrectas, bloqueo, correo duplicado, verificación vencida, código inválido y consentimiento requerido.

**Pantallas incluidas:** 29 PIN Setup; 30 PIN Incorrect; 31 PIN Temporarily Blocked; 32 Duplicate Email; 33 Verification Expired; 34 Invalid Link Code; 35 Consent Required.

<p align="center">
  <img src="assets/mobile-app-mockups-access-registration-consent-states.png" alt="Mock-ups de validaciones de acceso registro y consentimiento" width="960">
</p>

*Figura. Mock-ups de validaciones de acceso, registro y consentimiento.*

*Nota. Elaboración propia.*

##### 06. Medication, Reminder & Adherence States

Las variantes de medicación muestran validaciones, edición, desactivación, recordatorio de toma, error de voz, toma ya confirmada y ausencia de datos de adherencia.

**Pantallas incluidas:** 36 Medication Required Fields Error; 37 Medication Updated; 38 Medication Deactivated; 39 Medication Reminder Due; 40 Voice Not Recognized; 41 Dose Already Confirmed; 42 No Adherence Data.

<p align="center">
  <img src="assets/mobile-app-mockups-medication-reminder-adherence-states.png" alt="Mock-ups de medicamentos recordatorios y adherencia" width="960">
</p>

*Figura. Mock-ups de validaciones de medicamentos, recordatorios y adherencia.*

*Nota. Elaboración propia.*

##### 07. Treatment & Dose States

Las variantes del tratamiento muestran datos incompletos, pausa, acceso restringido, ausencia de próxima toma y detalle de toma pendiente, confirmada o tardía.

**Pantallas incluidas:** 43 Treatment Incomplete; 44 Treatment Paused; 45 Treatment Access Denied; 46 No Next Dose; 47 Dose Detail - Pending; 48 Dose Detail - Confirmed; 49 Dose Detail - Late.

<p align="center">
  <img src="assets/mobile-app-mockups-treatment-dose-states.png" alt="Mock-ups de estados de tratamiento y toma" width="960">
</p>

*Figura. Mock-ups de estados de tratamiento y de una toma.*

*Nota. Elaboración propia.*

##### 08. Omission, Reinforcement & Follow-up States

Las variantes de seguimiento de la toma muestran omisión, recordatorio reforzado, confirmación tardía, agenda con estados, historial vacío y contacto no disponible.

**Pantallas incluidas:** 50 Dose Detail - Omitted; 51 Reinforced Reminder; 52 Late Dose Confirmed; 53 Omission Preserved; 54 Agenda With Statuses; 55 Empty Intake History; 56 Contact Unavailable.

<p align="center">
  <img src="assets/mobile-app-mockups-omission-reinforcement-follow-up.png" alt="Mock-ups de omisiones y seguimiento" width="960">
</p>

*Figura. Mock-ups de omisiones, recordatorios reforzados y seguimiento.*

*Nota. Elaboración propia.*

##### 09. Follow-up & Accessibility States

Las variantes de seguimiento y accesibilidad muestran notas guardadas, alertas atendidas, cambio de periodo, evidencia insuficiente, texto grande, contraste y movimiento reducido.

**Pantallas incluidas:** 57 Follow-up Note Saved; 58 Alert Attended; 59 Adherence Period Changed; 60 Insufficient Evidence; 61 Large Text Enabled; 62 High Contrast Enabled; 63 Reduced Motion Enabled.

<p align="center">
  <img src="assets/mobile-app-mockups-follow-up-accessibility-states.png" alt="Mock-ups de seguimiento y accesibilidad" width="960">
</p>

*Figura. Mock-ups de seguimiento, evidencia y configuraciones de accesibilidad.*

*Nota. Elaboración propia.*

##### 10. Preferences, Inventory, Subscription & Internationalization

Las variantes finales muestran ayuda de lectura, preferencias guardadas, validación de inventario, reposición, suscripción, destino externo e idioma.

**Pantallas incluidas:** 64 Reading Assistance Enabled; 65 Notification Preferences Saved; 66 Invalid Inventory Quantity; 67 Stock Replenished; 68 Subscription Updated; 69 External Destination Unavailable; 70 Internationalization.

<p align="center">
  <img src="assets/mobile-app-mockups-preferences-inventory-subscription-states.png" alt="Mock-ups de preferencias inventario suscripción e internacionalización" width="960">
</p>

*Figura. Mock-ups de preferencias guardadas, inventario, suscripción, destino externo e internacionalización.*

*Nota. Elaboración propia.*

#### 3.1.4.4. Mobile Applications User Flow Diagrams

Los recorridos agrupan las acciones por perfil y objetivo. La tabla relaciona los puntos de entrada, decisiones y resultados con sus wireflows.

| Perfil | Objetivo | Recorrido y decisiones | Diagrama |
| --- | --- | --- | --- |
| Adulto mayor | Acceder y consultar la próxima toma | Ingresar PIN  /  validar acceso  /  Inicio  /  próxima toma; el PIN incorrecto y el bloqueo ofrecen estados alternos. | WF01 |
| Adulto mayor | Confirmar una toma | Próxima toma  /  confirmar por toque o voz  /  resultado; la voz no reconocida permite reintentar y una toma confirmada conserva su registro. | WF02 |
| Adulto mayor | Consultar medicación y agenda | Medicamentos  /  detalle; Agenda  /  toma  /  estado pendiente, confirmado, tardío u omitido. | WF03-WF04 |
| Adulto mayor | Ajustar accesibilidad | Más  /  Accesibilidad  /  elegir preferencia  /  interfaz con ajuste aplicado. | WF05 |
| Familiar/cuidador | Crear cuenta y vincular al adulto | Registro  /  verificación  /  código de vínculo  /  solicitud  /  consentimiento; los datos inválidos permiten corregir el paso. | WF06 |
| Familiar/cuidador | Configurar y administrar un tratamiento | Registrar medicamento  /  definir pauta  /  gestionar tratamiento; editar, pausar o desactivar según la acción elegida. | WF07, WF14 |
| Familiar/cuidador | Revisar adherencia y actuar ante una alerta | Resumen  /  persona vinculada  /  historial o alertas  /  detalle  /  contacto o nota  /  alerta atendida. | WF08-WF10 |
| Familiar/cuidador | Mantener la continuidad del cuidado | Inventario  /  reposición  /  cantidad actualizada; preferencias  /  guardar; plan  /  elegir  /  suscripción actualizada. | WF11-WF13 |
| Adulto mayor y familiar | Gestionar una toma fuera de horario | Recordatorio reforzado  /  confirmación tardía u omisión conservada  /  agenda e historial. | WF15 |
| Visitante | Conocer Tata y elegir un plan | Propuesta de valor  /  funciones  /  comparación de planes  /  registro o contacto; el destino externo dispone de un estado de indisponibilidad. | WF16 |

tablero de wireflows:

https://www.figma.com/design/jCppvxtSpLpHOrC3ZWUIVC/VitaHealth?node-id=283-2


#### 3.1.4.5. Mobile Applications Prototyping

El prototipo conecta las vistas y sus acciones para recorrer el acceso, tratamiento, tomas y seguimiento familiar. La función de idioma permite utilizar la interfaz en inglés mediante la variante EN.

<p align="center">
  <img src="assets/mobile-app-prototyping-overview.png" alt="Vista general del prototipo móvil" width="960">
</p>

*Figura. Vista general de las 70 pantallas utilizadas en el prototipo interactivo de Tata.*

*Nota. Elaboración propia.*

<p align="center">
  <img src="assets/mobile-app-prototyping-older-adult-bottom-navigation.png" alt="Prototipo de navegación inferior del adulto mayor" width="960">
</p>

*Figura. Navegación inferior interactiva correspondiente al perfil del adulto mayor.*

*Nota. Elaboración propia.*

<p align="center">
  <img src="assets/mobile-app-prototyping-caregiver-bottom-navigation.png" alt="Prototipo de navegación inferior del familiar o cuidador" width="960">
</p>

*Figura. Navegación inferior interactiva correspondiente al perfil del familiar o cuidador.*

*Nota. Elaboración propia.*

Enlace a prototipo:

https://www.figma.com/proto/jCppvxtSpLpHOrC3ZWUIVC/VitaHealth?node-id=563-5


Enlace a archivo de diseño:

https://www.figma.com/design/jCppvxtSpLpHOrC3ZWUIVC/VitaHealth?node-id=563-2


prototipo original de Figma:

https://www.figma.com/design/jCppvxtSpLpHOrC3ZWUIVC/VitaHealth?node-id=563-2
