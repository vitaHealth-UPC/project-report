# Capítulo III: Solution UI/UX Design

## 3.1. Product design

### 3.1.1. Style Guidelines

El equipo definió un único set de fundamentos de diseño para Tata "Tata Design Foundations" paleta de colores, tipografía y tokens de espaciado/interacción, además del logotipo oficial. Estos fundamentos se aplican de manera consistente en el Landing Page, en la aplicación Android nativa y en la aplicación multiplataforma, y son la referencia para los Wireframes, Mock-ups y Prototypes de este capítulo.

#### 3.1.1.1. General Style Guidelines

##### Branding

<p align="center">
  <img src="./assets/Tata.png" alt="Logotipo de Tata" width="320">
</p>

- **Naming:** "Tata" es el término afectivo que en el Perú se usa para referirse a un abuelo o adulto mayor querido, lo que refuerza el vínculo familiar del producto frente a nombres más funcionales o clínicos, como los de la competencia (Medisafe, MyTherapy).
- **Isotipo:** una mariposa en dos tonos de morado, en vez de la iconografía médica (cruces, pastillas) que usan los competidores. Transmite cuidado y ligereza sin verse clínica.
- **Wordmark:** el logotipo usa Dancing Script (cursiva), reservada solo para la marca. No se usa en contenido funcional de la interfaz porque su legibilidad no alcanza para el adulto mayor.

##### Typography

| Tipografía | Uso | Pesos disponibles |
| --- | --- | --- |
| DM Serif Display | Display / headings | Regular |
| Inter | UI / body | Regular, Medium, Semi Bold, Bold |
| Dancing Script | Brand only (wordmark "Tata") | Bold |

**Escala tipográfica:**

| Nivel | Tamaño | Fuente | Uso |
| --- | --- | --- | --- |
| Display / H1 | 34 sp | DM Serif Display | Títulos de pantalla y hitos importantes (p. ej. resumen semanal de adherencia) |
| Display / H2 | 29 sp | DM Serif Display | Subtítulos de sección |
| Page title | 24 sp | DM Serif Display | Título de pantalla |
| UI title | 20 sp | Inter Semi Bold | Acciones, navegación |
| Body | 16 sp | Inter Regular | Formularios y contenido, incluyendo dosis, medicamento y horario |
| Label | 13 sp | Inter Medium | Etiquetas de campos y estados |
| Caption | 11 sp | Inter Regular | Metadata secundaria o navegación |

Los tamaños entre 8.5 y 10 sp solo se usan en metadata secundaria o navegación nunca en dosis, medicamento u horario de toma. Se usa sp y no dp para que el tamaño de letra respete el ajuste de accesibilidad del sistema operativo.

![Tata Design Foundations: paleta de colores y tipografía](./assets/tata-design-foundations-colors-typography.png)

*Figura. Paleta de colores y sistema tipográfico de Tata Design Foundations.*

##### Colors

| Token | Valor | Uso |
| --- | --- | --- |
| Primary | `#173B70` | Navegación, elementos activos y acentos de identidad. |
| Ink | `#0E1729` | Texto principal sobre fondos claros. |
| Secondary | `#7B879B` | Texto secundario e iconografía inactiva. |
| Lavender | `#F1ECFF` | Superficie para contenido de seguimiento y vínculo familiar. |
| Sage | `#E8F5EB` | Estados positivos o de confirmación (toma registrada). |
| Cream | `#FFF3E2` | Estados pendientes o de atención moderada (toma por confirmar). |
| Canvas | `#F8F8FE` | Fondo general de las pantallas. |

Todo texto sobre fondo cumple un contraste mínimo de 4.5:1 (3:1 en texto grande), y ningún estado depende solo del color: siempre se refuerza con texto e ícono.

##### Spacing

| Token | Valor | Descripción |
| --- | --- | --- |
| Grid base | 8 dp | Espaciado principal en múltiplos de 8, 4 dp solo para microajustes. |
| Touch target | 44 × 44 dp | Área táctil mínima para botones, íconos y controles. |
| Card radius | 16-24 dp | 16 dp en controles, 20-24 dp en cards, 28+ dp en superficies hero. |
| Page padding | 16-24 dp | 16 dp como mínimo, 20-24 dp recomendado para contenido principal. |
| Primary CTA | 56-64 dp de altura | Confirmaciones y acciones principales, como confirmar una toma. |
| Focus | 1 acción primaria | Una única acción dominante por pantalla. |

El CTA principal (56-64 dp) es más alto que el touch target mínimo para reducir errores de precisión en el adulto mayor. La regla de una sola acción primaria por pantalla responde a la sobrecarga de decisiones identificada en las entrevistas y el Empathy Mapping del segmento.

![Tata Design Foundations: escala tipográfica y reglas de layout e interacción](./assets/tata-design-foundations-layout-interaction.png)

*Figura. Escala tipográfica y reglas de Layout & Interaction de Tata Design Foundations.*

##### Tono de comunicación

| Dimensión | Posición de Tata | Sustento |
| --- | --- | --- |
| Divertido / Serio | Serio, con calidez | Tata acompaña decisiones de salud, el humor le restaría seriedad a un recordatorio o a una alerta de omisión. |
| Formal / Casual | Casual, sin jerga | El adulto mayor necesita frases simples y directas, el familiar recibe el mismo registro para mantener consistencia. |
| Respetuoso / Irreverente | Respetuoso | Nunca condescendiente con el adulto mayor con el familiar, los mensajes son objetivos, sin dramatizar. |
| Entusiasta / Sereno | Sereno | Incluso en alertas por tomas no confirmadas, el mensaje informa con calma y propone una acción, sin generar pánico. |

### 3.1.2. Information Architecture

El equipo definió la arquitectura de información de Tata separando dos audiencias con necesidades opuestas: el adulto mayor, que requiere la mínima cantidad de decisiones y pasos posibles, y el familiar o cuidador, que necesita profundidad suficiente para configurar tratamientos y revisar resultados. El Landing Page se organiza además como una tercera experiencia, orientada a que el visitante entienda la propuesta de valor y continúe hacia el registro. Las decisiones de esta sección se apoyan en los hallazgos de las entrevistas y en los principios ya definidos en Tata Design Foundations, particularmente "Reconocimiento > memoria" y "Prioridad temporal".

#### 3.1.2.1. Organization Systems

##### Organización visual del contenido

| Sistema de organización | Grupo de contenido | Justificación |
| --- | --- | --- |
| Jerárquica (visual hierarchy) | Inicio del adulto mayor (US-20) | La próxima toma domina la pantalla; el historial y los ajustes quedan subordinados, siguiendo el principio "Prioridad temporal" ya definido en Tata Design Foundations. |
| Jerárquica (visual hierarchy) | Inicio del familiar (US-25) | El estado reciente del adulto mayor y las alertas abiertas se muestran primero; el resumen de adherencia y el acceso a tratamientos quedan en un segundo nivel. |
| Jerárquica (visual hierarchy) | Landing Page (US-46, US-47) | La propuesta de valor ocupa el hero; funcionalidades y planes se despliegan en orden descendente de importancia hacia el CTA final. |
| Secuencial (step-by-step) | Registro y vinculación de cuentas (US-10, US-11, US-02, US-13, US-12, US-01) | El familiar no puede vincular al adulto mayor sin verificar su correo, ni el adulto mayor puede ingresar sin que la cuenta esté habilitada; el flujo se presenta como pasos obligatorios en orden. |
| Secuencial (step-by-step) | Creación de un tratamiento (US-14, US-15, US-16, US-17) | Definir el medicamento, la dosis, el horario y el recordatorio son decisiones dependientes entre sí; se guía al familiar paso a paso en un wizard. |
| Secuencial (step-by-step) | Activación o cambio de suscripción (US-45) | Selección de plan, confirmación y activación se presentan en una secuencia corta y lineal. |
| Matricial | Agenda diaria de tomas (US-24) | Cruza los horarios del día con los medicamentos correspondientes a cada horario. |
| Matricial | Historial e insights de adherencia (US-32, US-09) | Cruza periodos de tiempo con el estado de cada toma (confirmada, tardía, omitida), permitiendo identificar patrones por franja horaria. |

##### Esquemas de categorización

| Esquema | Aplicación | Justificación |
| --- | --- | --- |
| Por audiencia (grupos de usuarios) | Separación completa entre la experiencia del adulto mayor, la del familiar/cuidador y el Landing Page del visitante | Es el esquema principal de Tata: cada audiencia tiene una profundidad de información y un nivel de autonomía distintos, sustentado en las entrevistas (baja alfabetización digital del adulto mayor frente a la necesidad de control remoto del familiar). |
| Cronológico | Historial reciente de tomas (US-26), historial de adherencia (US-32), notas de seguimiento (US-30) y alertas | Se listan del más reciente al más antiguo, priorizando lo que necesita atención inmediata. |
| Por tópicos | Navegación principal de la app del familiar (Medicación, Adherencia, Alertas, Cuenta) | Cada Epic (EPIC-02, EPIC-05, EPIC-04, EPIC-08) corresponde a una sección propia, evitando mezclar responsabilidades distintas en una misma pantalla. |
| Alfabético | No se utiliza en ningún listado de Tata (ni en medicamentos, ni en planes) | El orden relevante para ambas audiencias es temporal (próxima toma) o de valor (comparación de planes, US-48), no alfabético; usar orden alfabético obligaría al adulto mayor a recordar el nombre exacto en vez de reconocerlo por contexto, contradiciendo el principio "Reconocimiento > memoria". |

#### 3.1.2.2. Labelling Systems

Todas las etiquetas de Tata siguen la convención **verbo + objeto** ya definida en Tata Design Foundations (p. ej. "Confirmar toma", no "Confirmación"), evitando etiquetas vagas y manteniendo el mismo texto para la misma acción entre la app del adulto mayor y la del familiar cuando la funcionalidad es compartida.

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

**Aplicaciones móviles (ASO)**

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

La confirmación por voz (TS-11) funciona como una vía de navegación alternativa a la táctil para la acción principal, sin reemplazar el flujo por toque.

##### App del familiar o cuidador

Barra de navegación inferior con 5 secciones, el máximo definido en Tata Design Foundations:

| Tab | Contenido | Epic |
| --- | --- | --- |
| Inicio | Estado reciente del adulto mayor y alertas abiertas | EPIC-04 |
| Medicación | Tratamientos, medicamentos e inventario | EPIC-02, EPIC-07 |
| Adherencia | Resumen semanal, historial y patrones detectados | EPIC-05 |
| Alertas | Detalle, contacto y seguimiento de alertas | EPIC-04 |
| Cuenta | Vínculo, plan/suscripción y accesibilidad | EPIC-01, EPIC-08, EPIC-06 |

El acceso a cada tab mantiene la misma posición y el mismo ícono en toda la app (principio de Consistencia ya definido), y ninguna pantalla obliga a más de dos niveles de profundidad desde el tab principal (tab → lista → detalle).

##### Landing Page

Navegación de una sola página con anclas, sin cambiar de URL entre secciones, para que el visitante recorra la propuesta de valor sin fricción:

| Sección (ancla) | Contenido | Historia relacionada |
| --- | --- | --- |
| Inicio | Propuesta de valor de Tata | US-46 |
| Funcionalidades | Principales funcionalidades del producto | US-47 |
| Planes | Comparación de planes disponibles | US-48 |
| Comenzar | CTA hacia registro o contacto | US-49 |

La barra de navegación superior permanece fija (sticky) durante el scroll, y el layout se adapta entre mobile y desktop sin perder el orden de las secciones (US-50, acceso adaptable al Landing Page).

### 3.1.3. Landing Page UI Design


![Fundamentos visuales de la landing](assets/landing-foundations.png)

*Figura. Fundamentos de diseño de la landing page. Nota. Elaboración propia; exportación del [tablero de Figma](https://www.figma.com/design/jCppvxtSpLpHOrC3ZWUIVC/VitaHealth?node-id=557-2).*

La landing page de Tata fue diseñada como el principal punto de entrada público al producto. Su propósito es comunicar de forma clara la propuesta de valor, explicar las funciones principales, mostrar el proceso de uso, presentar los planes disponibles y proporcionar medios de contacto antes del registro o ingreso a la aplicación.

El diseño se desarrolló considerando dos formatos: desktop y mobile. Ambas versiones mantienen la misma arquitectura de información, contenido y jerarquía general, pero reorganizan los elementos según el espacio disponible. La versión desktop aprovecha una composición horizontal y bloques de mayor amplitud, mientras que la versión mobile transforma las secciones en recorridos verticales, ajusta el tamaño de los controles y reorganiza las tarjetas para conservar legibilidad y facilidad de interacción.

La estructura de la landing page mantiene relación visual con la aplicación móvil mediante el uso de la identidad de Tata, la misma familia cromática, componentes redondeados, jerarquías tipográficas y elementos visuales asociados con recordatorios, acompañamiento familiar y adherencia.

#### 3.1.3.1. Landing Page Wireframe

[Wireframes originales: desktop y mobile](https://www.figma.com/design/jCppvxtSpLpHOrC3ZWUIVC/VitaHealth?node-id=546-2).

El wireframe de la landing page se elaboró en baja fidelidad con el objetivo de validar la arquitectura de información, el orden de lectura y la distribución de las secciones antes de incorporar el tratamiento visual definitivo.

La estructura comienza con una barra de navegación superior y una sección hero destinada a comunicar la propuesta principal de Tata. A continuación, se presentan los beneficios centrales del producto, las funciones relacionadas con recordatorios, seguimiento familiar e insights, una explicación resumida del proceso de uso, testimonios, comparación de planes, opciones de soporte y una llamada a la acción final.

En la versión desktop, los bloques aprovechan el ancho disponible mediante composiciones horizontales, tarjetas distribuidas en columnas y una presentación paralela entre contenido textual y recursos visuales. En la adaptación mobile, los mismos elementos se reorganizan verticalmente, reduciendo el número de columnas y priorizando una secuencia de lectura continua.

![Wireframe de la landing page en versión desktop](assets/landing-page-wireframe-desktop.png)

*Figura. Wireframe desktop de la landing page de Tata.*

*Nota. Elaboración propia.*

![Wireframe de la landing page en versión mobile](assets/landing-page-wireframe-mobile.png)

*Figura. Wireframe mobile de la landing page de Tata.*

*Nota. Elaboración propia.*

La correspondencia entre ambas versiones permite validar el comportamiento responsive de la landing page desde la etapa de baja fidelidad. No se eliminan funciones esenciales en la versión mobile; únicamente se modifica la disposición de los componentes para adecuarlos al ancho reducido de pantalla.

#### 3.1.3.2. Landing Page Mock-up

[Mock-ups originales: desktop y mobile](https://www.figma.com/design/jCppvxtSpLpHOrC3ZWUIVC/VitaHealth?node-id=400-2).

El mock-up aplica el sistema visual definitivo sobre la estructura previamente validada en los wireframes. La propuesta utiliza la identidad gráfica de Tata, una paleta basada principalmente en azul oscuro, violeta, tonos neutros y colores de apoyo, además de tarjetas de bordes suaves, iconografía funcional y recursos fotográficos relacionados con el adulto mayor y su familia.

La sección hero combina la propuesta de valor con una fotografía contextual y elementos de interfaz que representan recordatorios, confirmaciones y seguimiento familiar. De esta manera, la funcionalidad del producto se comunica visualmente sin depender únicamente del texto.

Las siguientes secciones desarrollan los beneficios principales, las funcionalidades de recordatorios, seguimiento e insights, el proceso resumido en tres pasos, testimonios, planes, soporte y la llamada a la acción final. Se mantiene suficiente separación vertical entre bloques para facilitar la lectura y evitar que la landing page se perciba excesivamente comprimida.

![Mock-up de la landing page en versión desktop](assets/landing-page-mockup-desktop.png)

*Figura. Mock-up desktop de la landing page de Tata.*

*Nota. Elaboración propia.*

La versión mobile conserva el contenido esencial de la versión desktop, pero utiliza una disposición de una sola columna. Las tarjetas, botones, encabezados, imágenes y bloques informativos se adaptan al ancho disponible y aumentan el recorrido vertical. Esta adaptación evita reducir excesivamente los contenidos y conserva una jerarquía visual equivalente a la versión desktop.

![Mock-up de la landing page en versión mobile](assets/landing-page-mockup-mobile.png)

*Figura. Mock-up mobile responsive de la landing page de Tata.*

*Nota. Elaboración propia.*

En conjunto, el wireframe y el mock-up permiten comprobar que la landing page conserva su estructura y propósito en ambos formatos. La versión de alta fidelidad añade identidad visual y contenido gráfico sin modificar la arquitectura de información establecida previamente.


### 3.1.4. Mobile Applications UX/UI Design

El diseño UX/UI de la aplicación móvil de Tata se organizó mediante tres artefactos complementarios: wireframes, wireflow diagrams y mock-ups. Los wireframes permitieron definir la estructura, la jerarquía de información y la distribución de controles sin incorporar todavía el tratamiento visual definitivo. Los wireflows relacionaron estas pantallas mediante recorridos asociados con los User Goals, incluyendo rutas principales, validaciones, estados alternos y situaciones de error. Finalmente, los mock-ups trasladaron la estructura validada a una propuesta visual de alta fidelidad mediante la tipografía, la paleta, los componentes, la iconografía y los estados de interacción definidos para Tata.

La propuesta considera dos perfiles principales dentro de la aplicación: el adulto mayor y el familiar o cuidador. Además, se contempla al usuario visitante en los puntos de entrada públicos relacionados con la presentación del producto, la consulta de planes, el registro y el inicio de sesión. Esta separación se refleja en la navegación, la información disponible y las acciones permitidas para cada perfil.

El adulto mayor utiliza una navegación orientada a la rutina diaria, medicamentos, agenda, notas y confirmación de tomas. El familiar o cuidador dispone de funciones de seguimiento, alertas, notas de seguimiento, gestión de la persona vinculada, tratamientos, inventario, preferencias y suscripción.

El diseño contempla estados de validación, bloqueo, ausencia de datos, falta de consentimiento, recordatorios reforzados, accesibilidad, gestión de tratamientos, inventario, alertas, suscripción e internacionalización. De esta forma, los artefactos no representan únicamente escenarios exitosos, sino también los estados necesarios para cubrir los criterios de aceptación de las User Stories.

La versión final comprende **70 pantallas funcionales**, estructuradas de forma equivalente entre wireframes, mock-ups y prototipado. Dentro de esta organización se incorporan la pantalla **07 Login**, utilizada para el ingreso de usuarios con una cuenta existente; la pantalla **21 Notes - Adult**, correspondiente a las notas del adulto mayor; la pantalla **27 Notes - Caregiver**, correspondiente a las notas del familiar o cuidador; y la pantalla **70 Internationalization**, que permite representar el cambio de idioma de la aplicación.

Las variantes identificadas con el sufijo `EN` en Figma corresponden a traducciones al inglés de las mismas 70 pantallas y, por tanto, no se contabilizan como pantallas funcionales adicionales.

Para facilitar la lectura del informe, los wireframes y los mock-ups se presentan por grupos correspondientes a las filas organizadas en Figma. Cada grupo reúne siete pantallas relacionadas funcionalmente y evita repetir una explicación individual para cada vista. Los wireflows, en cambio, se presentan uno por uno porque cada diagrama corresponde a un User Goal específico y contiene sus propias condiciones y bifurcaciones.

#### 3.1.4.1. Mobile Applications Wireframes

Los artefactos se presentan por filas del tablero original: **70 variantes en español**, organizadas en **10 filas de 7 vistas**. Cada fila conserva la numeración visible en Figma y puede ampliarse desde la imagen. Las variantes representan vistas principales y resultados alternos; no equivalen a 70 funcionalidades independientes. [Fuente: tablero de Figma](https://www.figma.com/design/jCppvxtSpLpHOrC3ZWUIVC/VitaHealth?node-id=260-2).

Los wireframes fueron elaborados en baja fidelidad para revisar la estructura de las pantallas antes de aplicar el sistema visual definitivo. Se utilizaron bloques, campos, botones, etiquetas, controles simples y placeholders para imágenes, gráficos e ilustraciones. Este nivel de fidelidad permitió concentrar la evaluación en la arquitectura de información, la jerarquía de contenidos, la ubicación de las acciones, la navegación inferior, la accesibilidad y los estados alternos requeridos por las User Stories.

##### 01. Entry, Onboarding & Access

Este grupo reúne los puntos de entrada a Tata y las pantallas necesarias para iniciar el uso del producto. Incluye la presentación de valor, la consulta de planes, el onboarding, el registro del familiar o cuidador, la vinculación con el adulto mayor, el acceso mediante PIN y el inicio de sesión para usuarios que ya poseen una cuenta.

**Pantallas incluidas:** 01 Landing - Value & Features; 02 Landing - Plans & Contact; 03 Onboarding; 04 Caregiver Registration; 05 Link & Consent; 06 PIN Access; 07 Login.

![Wireframes de entrada, onboarding y acceso](assets/mobile-app-wireframes-entry-onboarding-access.png)

*Figura. Wireframes de entrada, onboarding y acceso a Tata.*

*Nota. Elaboración propia.*

##### 02. Older Adult Daily Experience

Este grupo corresponde a la experiencia principal del adulto mayor. Se muestran la pantalla de inicio, la consulta de medicamentos, el detalle de una pauta, la agenda semanal, la confirmación por voz, la confirmación de una toma y la configuración general de accesibilidad.

**Pantallas incluidas:** 08 Home; 09 My Medications; 10 Medication Detail; 11 Weekly Schedule; 12 Voice Confirmation; 13 Dose Confirmed; 14 Accessibility.

![Wireframes de la experiencia diaria del adulto mayor](assets/mobile-app-wireframes-older-adult-daily-experience.png)

*Figura. Wireframes de la experiencia diaria del adulto mayor.*

*Nota. Elaboración propia.*

##### 03. Monitoring, Insights & Adult Notes

Este grupo concentra las principales funciones de seguimiento y consulta. Incluye el resumen familiar, la persona vinculada, la lista de alertas, el detalle de una alerta, el historial con indicadores de adherencia y las recomendaciones derivadas del comportamiento reciente. La fila incorpora además la pantalla de notas del adulto mayor, que funciona como destino de la opción “Notas” dentro de su navegación inferior.

**Pantallas incluidas:** 15 Family Summary; 16 Linked Person; 17 Alerts; 18 Alert Detail; 19 History & Insights; 20 Adherence Recommendations; 21 Notes - Adult.

![Wireframes de seguimiento, insights y notas del adulto mayor](assets/mobile-app-wireframes-monitoring-insights-adult-notes.png)

*Figura. Wireframes de seguimiento familiar, alertas, insights y notas del adulto mayor.*

*Nota. Elaboración propia.*

##### 04. Caregiver Treatment Management & Notes

Este conjunto reúne las funciones de configuración y administración realizadas principalmente por el familiar o cuidador. Incluye el registro de medicamentos, la creación y gestión de tratamientos, el control de inventario, las preferencias de notificación, las notas del cuidador y la administración del plan contratado.

**Pantallas incluidas:** 22 Add Medication - Caregiver; 23 Create Treatment; 24 Treatment Management; 25 Inventory & Restock; 26 Notification Preferences; 27 Notes - Caregiver; 28 Plan & Subscription.

![Wireframes de gestión del tratamiento y notas del cuidador](assets/mobile-app-wireframes-caregiver-treatment-management-notes.png)

*Figura. Wireframes de gestión del tratamiento, inventario, notificaciones, notas y suscripción.*

*Nota. Elaboración propia.*

##### 05. Access, Registration & Consent States

Este grupo incorpora estados alternos relacionados con el acceso, el registro y la vinculación. Se representan la creación del PIN, un PIN incorrecto, el bloqueo temporal por intentos fallidos, un correo ya registrado, una verificación vencida, un código de vinculación inválido y el seguimiento restringido cuando no existe consentimiento.

**Pantallas incluidas:** 29 PIN Setup; 30 PIN Incorrect; 31 PIN Temporarily Blocked; 32 Duplicate Email; 33 Verification Expired; 34 Invalid Link Code; 35 Consent Required.

![Wireframes de validaciones de acceso, registro y consentimiento](assets/mobile-app-wireframes-access-registration-consent-states.png)

*Figura. Wireframes de validaciones de acceso, registro y consentimiento.*

*Nota. Elaboración propia.*

##### 06. Medication, Reminder & Adherence States

Las pantallas de este grupo muestran validaciones y estados derivados de la gestión de medicamentos y de la confirmación de tomas. Se incluyen campos obligatorios incompletos, actualización y desactivación de medicamentos, recordatorio de toma, voz no reconocida, toma previamente confirmada y ausencia de datos para calcular adherencia.

**Pantallas incluidas:** 36 Medication Required Fields Error; 37 Medication Updated; 38 Medication Deactivated; 39 Medication Reminder Due; 40 Voice Not Recognized; 41 Dose Already Confirmed; 42 No Adherence Data.

![Wireframes de estados de medicamentos, recordatorios y adherencia](assets/mobile-app-wireframes-medication-reminder-adherence-states.png)

*Figura. Wireframes de validaciones de medicamentos, recordatorios y adherencia.*

*Nota. Elaboración propia.*

##### 07. Treatment & Dose States

Este grupo representa variaciones del tratamiento y de una toma individual. Se consideran un tratamiento incompleto, un tratamiento pausado, un acceso restringido, la ausencia de una próxima toma y los estados pendiente, confirmado y tardío del detalle de una toma.

**Pantallas incluidas:** 43 Treatment Incomplete; 44 Treatment Paused; 45 Treatment Access Denied; 46 No Next Dose; 47 Dose Detail - Pending; 48 Dose Detail - Confirmed; 49 Dose Detail - Late.

![Wireframes de estados de tratamiento y toma](assets/mobile-app-wireframes-treatment-dose-states.png)

*Figura. Wireframes de estados de tratamiento y de una toma.*

*Nota. Elaboración propia.*

##### 08. Omission, Reinforcement & Follow-up States

Este grupo amplía los escenarios de adherencia y seguimiento. Se representa una toma omitida, el recordatorio reforzado, la confirmación tardía, la preservación de una omisión después del vencimiento, una agenda con estados, un historial sin resultados y la imposibilidad de contactar al adulto mayor.

**Pantallas incluidas:** 50 Dose Detail - Omitted; 51 Reinforced Reminder; 52 Late Dose Confirmed; 53 Omission Preserved; 54 Agenda With Statuses; 55 Empty Intake History; 56 Contact Unavailable.

![Wireframes de omisiones, recordatorios reforzados y seguimiento](assets/mobile-app-wireframes-omission-reinforcement-follow-up.png)

*Figura. Wireframes de omisiones, recordatorios reforzados y seguimiento.*

*Nota. Elaboración propia.*

##### 09. Follow-up & Accessibility States

Este grupo reúne resultados posteriores a acciones del cuidador y configuraciones de accesibilidad. Incluye una nota de seguimiento guardada, una alerta atendida, un cambio del periodo de análisis, la falta de evidencia suficiente para generar recomendaciones y tres estados de accesibilidad activados.

**Pantallas incluidas:** 57 Follow-up Note Saved; 58 Alert Attended; 59 Adherence Period Changed; 60 Insufficient Evidence; 61 Large Text Enabled; 62 High Contrast Enabled; 63 Reduced Motion Enabled.

![Wireframes de seguimiento y accesibilidad](assets/mobile-app-wireframes-follow-up-accessibility-states.png)

*Figura. Wireframes de seguimiento, evidencia y configuraciones de accesibilidad.*

*Nota. Elaboración propia.*

##### 10. Preferences, Inventory, Subscription & Internationalization

El último grupo reúne configuraciones guardadas y estados asociados con accesibilidad, inventario, suscripción, navegación externa e internacionalización. Se muestra la ayuda de lectura habilitada, las preferencias de notificación guardadas, una cantidad inválida de inventario, el stock repuesto, la suscripción actualizada, un destino externo no disponible y la configuración de idioma de la aplicación.

La pantalla de internacionalización mantiene la estructura de accesibilidad y añade la opción “Idioma de la aplicación”, desde la cual puede seleccionarse otra versión lingüística de la interfaz. Las vistas identificadas con `EN` en Figma representan dicha traducción y no constituyen pantallas adicionales dentro del conteo funcional.

**Pantallas incluidas:** 64 Reading Assistance Enabled; 65 Notification Preferences Saved; 66 Invalid Inventory Quantity; 67 Stock Replenished; 68 Subscription Updated; 69 External Destination Unavailable; 70 Internationalization.

![Wireframes de preferencias, inventario, suscripción e internacionalización](assets/mobile-app-wireframes-preferences-inventory-subscription-states.png)

*Figura. Wireframes de preferencias guardadas, inventario, suscripción, destino externo e internacionalización.*

*Nota. Elaboración propia.*

En conjunto, los **70 wireframes** permiten comprobar la cobertura estructural de la aplicación antes de incorporar el tratamiento visual de alta fidelidad. Los estados alternos se mantienen como pantallas independientes porque representan respuestas distintas del sistema frente a acciones, restricciones o condiciones específicas de las User Stories. Las versiones traducidas al inglés conservan la misma estructura y no modifican este conteo.

#### 3.1.4.2. Mobile Applications Wireflow Diagrams

Los wireflow diagrams relacionan los wireframes mediante recorridos de navegación asociados con User Goals concretos. Cada diagrama muestra la ruta principal y, cuando corresponde, las rutas alternativas que aparecen como consecuencia de validaciones, errores, restricciones o cambios de estado. Las flechas representan transiciones entre pantallas y sus etiquetas indican la acción o condición que produce cada cambio.

Cada wireflow mantiene correspondencia con un User Persona y utiliza como nodos los mismos estados representados en los wireframes. De este modo, cuando una interacción modifica el contenido o el estado de una pantalla, el flujo incorpora una vista específica que evidencia ese resultado.

##### WF01. Acceso con PIN y consulta de próxima toma

**User Persona:** Doña Carmen Rodríguez.

**User Goal:** Ingresar con un PIN simple y consultar la próxima toma.

**User Stories relacionadas:** US-01 y US-20.

Este wireflow representa el acceso del adulto mayor a Tata mediante un PIN de cuatro dígitos. Después de crear el PIN y realizar un acceso válido, el usuario llega al inicio y puede consultar la próxima toma. También se representan un PIN incorrecto, el bloqueo temporal por intentos fallidos y el estado en el que no existe una toma próxima.

![WF01 acceso con PIN y próxima toma](assets/mobile-app-wireflow-pin-access-next-dose.png)

*Figura. WF01, acceso con PIN y consulta de la próxima toma.*

*Nota. Elaboración propia.*

##### WF02. Confirmación de una toma por toque o por voz

**User Persona:** Doña Carmen Rodríguez.

**User Goal:** Confirmar una toma por toque o por voz y verificar el registro.

**User Stories relacionadas:** US-05, US-06 y US-23.

El recorrido muestra las dos formas principales de confirmar una toma. El usuario puede confirmar directamente desde el inicio o utilizar la confirmación por voz. El diagrama también contempla una toma previamente confirmada, una voz no reconocida, una confirmación tardía dentro del periodo de tolerancia y una omisión preservada cuando el periodo permitido ya finalizó.

![WF02 confirmación de toma](assets/mobile-app-wireflow-dose-confirmation.png)

*Figura. WF02, confirmación de una toma por toque o por voz y estados posteriores.*

*Nota. Elaboración propia.*

##### WF03. Consulta de medicamentos y estados de una pauta

**User Persona:** Doña Carmen Rodríguez.

**User Goal:** Consultar mis medicamentos y revisar una pauta y sus estados.

**User Stories relacionadas:** US-21 y US-23.

El recorrido parte del inicio, continúa hacia la lista de medicamentos y permite abrir el detalle de una pauta. Desde el detalle se representan los estados pendiente, confirmado, tardío y omitido para que el adulto mayor pueda reconocer el estado de la toma dentro de la misma estructura de navegación.

![WF03 medicamentos y estados de toma](assets/mobile-app-wireflow-medications-dose-states.png)

*Figura. WF03, consulta de medicamentos y estados de una pauta.*

*Nota. Elaboración propia.*

##### WF04. Consulta de agenda y visualización de estados

**User Persona:** Doña Carmen Rodríguez.

**User Goal:** Consultar la agenda y distinguir el estado de cada toma.

**User Stories relacionadas:** US-24.

Este wireflow muestra el acceso desde el inicio hacia la agenda semanal. La primera vista permite consultar las tomas programadas y, desde ella, se accede al estado de las tomas para distinguir visualmente cuáles se encuentran confirmadas, pendientes, tardías u omitidas dentro del periodo mostrado.

![WF04 agenda y estados](assets/mobile-app-wireflow-schedule-dose-statuses.png)

*Figura. WF04, consulta de agenda semanal y visualización de estados.*

*Nota. Elaboración propia.*

##### WF05. Configuración de accesibilidad

**User Persona:** Doña Carmen Rodríguez.

**User Goal:** Adaptar la interfaz y conservar cada preferencia de accesibilidad.

**User Stories relacionadas:** US-35, US-36, US-37 y US-38.

El recorrido parte del inicio y accede a la sección de accesibilidad. Desde esa pantalla se representan los estados generados al aumentar el tamaño del texto, activar el contraste reforzado, reducir el movimiento y habilitar la ayuda de lectura. Cada resultado conserva la estructura de configuración y evidencia que la preferencia seleccionada ha sido guardada.

![WF05 accesibilidad](assets/mobile-app-wireflow-accessibility-preferences.png)

*Figura. WF05, configuración y persistencia de preferencias de accesibilidad.*

*Nota. Elaboración propia.*

##### WF06. Registro y vinculación del familiar o cuidador

**User Persona:** Diego Dani Mendoza.

**User Goal:** Crear mi cuenta y vincular a Rosa con consentimiento.

**User Stories relacionadas:** US-10, US-11, US-02, US-12 y US-13.

Este wireflow reúne el ingreso desde la bienvenida, el registro del cuidador, la verificación del correo, la vinculación con el adulto mayor y el acceso al resumen familiar cuando el vínculo es aceptado. Como rutas alternativas se incluyen un correo ya registrado, una verificación vencida, un código de vinculación inválido y el seguimiento restringido cuando no existe consentimiento.

![WF06 registro y vinculación](assets/mobile-app-wireflow-registration-link-consent.png)

*Figura. WF06, registro, verificación y vinculación con consentimiento.*

*Nota. Elaboración propia.*

##### WF07. Registro de medicamento y gestión del tratamiento

**User Persona:** Diego Dani Mendoza.

**User Goal:** Registrar un medicamento y activar o gestionar un tratamiento.

**User Stories relacionadas:** US-03, US-14, US-15, US-16, US-17, US-18 y US-19.

El recorrido comienza en la persona vinculada, continúa con el registro de un medicamento y la creación de un tratamiento, y finaliza en la gestión del tratamiento. También se representan la falta de datos obligatorios, una pauta incompleta, un tratamiento pausado y el acceso restringido cuando el tratamiento no corresponde a la persona vinculada.

![WF07 medicamento y tratamiento](assets/mobile-app-wireflow-medication-treatment-management.png)

*Figura. WF07, registro de medicamento y gestión del tratamiento.*

*Nota. Elaboración propia.*

##### WF08. Seguimiento familiar, historial y alertas

**User Persona:** Diego Dani Mendoza.

**User Goal:** Consultar el estado reciente y profundizar en historial o alertas.

**User Stories relacionadas:** US-25, US-26, US-08, US-32 y US-33.

Este wireflow relaciona el resumen familiar con el historial y la lista de alertas. También contempla un historial sin datos suficientes para calcular adherencia, un periodo sin resultados y la actualización del periodo consultado. Estas rutas permiten representar situaciones en las que el seguimiento no dispone siempre de información completa.

![WF08 seguimiento historial y alertas](assets/mobile-app-wireflow-family-history-alerts.png)

*Figura. WF08, seguimiento familiar, historial y alertas.*

*Nota. Elaboración propia.*

##### WF09. Atención de alertas e intervención del cuidador

**User Persona:** Diego Dani Mendoza.

**User Goal:** Atender una alerta y dejar registrada la intervención.

**User Stories relacionadas:** US-27, US-29, US-30 y US-31.

El recorrido parte de la lista de alertas, abre el detalle de una alerta y permite registrar una intervención antes de marcarla como atendida. También se representa el caso en el que no existe un canal de contacto válido para la persona vinculada, por lo que la acción de contacto no puede completarse.

![WF09 atención de alertas](assets/mobile-app-wireflow-alert-intervention.png)

*Figura. WF09, atención de alertas y registro de intervención.*

*Nota. Elaboración propia.*

##### WF10. Recomendaciones basadas en evidencia

**User Persona:** Diego Dani Mendoza.

**User Goal:** Revisar patrones y aplicar un ajuste solo con evidencia suficiente.

**User Stories relacionadas:** US-09, US-32, US-33 y US-34.

El recorrido parte del historial de adherencia y conduce a la pantalla de recomendaciones cuando existen datos suficientes para detectar un patrón. Desde allí puede aplicarse un ajuste al tratamiento. Como rutas alternativas se incluyen el cambio del periodo de análisis y el estado de evidencia insuficiente, en el que no se presenta una recomendación concluyente.

![WF10 recomendaciones y evidencia](assets/mobile-app-wireflow-evidence-recommendations.png)

*Figura. WF10, análisis de adherencia y recomendaciones basadas en evidencia.*

*Nota. Elaboración propia.*

##### WF11. Inventario y reposición

**User Persona:** Diego Dani Mendoza.

**User Goal:** Controlar el stock y registrar una reposición.

**User Stories relacionadas:** US-40, US-41, US-42 y US-43.

Este wireflow muestra el acceso desde la gestión del tratamiento hacia el inventario, el registro de una reposición y el estado resultante con el stock actualizado. Como ruta alternativa se representa la validación de una cantidad inválida antes de guardar la reposición.

![WF11 inventario y reposición](assets/mobile-app-wireflow-inventory-restock.png)

*Figura. WF11, control de inventario y registro de reposición.*

*Nota. Elaboración propia.*

##### WF12. Preferencias de notificación

**User Persona:** Diego Dani Mendoza.

**User Goal:** Configurar qué notificaciones recibir y en qué horario.

**User Stories relacionadas:** US-28 y US-39.

El recorrido parte del resumen familiar, accede a las preferencias de notificación y finaliza con la configuración guardada. La pantalla permite organizar categorías de avisos, canales de comunicación y horario de silencio dentro de una misma configuración.

![WF12 preferencias de notificación](assets/mobile-app-wireflow-notification-preferences.png)

*Figura. WF12, configuración y guardado de preferencias de notificación.*

*Nota. Elaboración propia.*

##### WF13. Plan y suscripción

**User Persona:** Diego Dani Mendoza.

**User Goal:** Consultar el plan actual y cambiar de suscripción.

**User Stories relacionadas:** US-44 y US-45.

Este wireflow muestra el acceso desde el resumen familiar hacia la gestión del plan. El usuario consulta su plan actual, revisa las alternativas disponibles y confirma el cambio de suscripción. El estado final evidencia que el nuevo plan se encuentra activo sin alterar el historial ni los vínculos existentes.

![WF13 plan y suscripción](assets/mobile-app-wireflow-plan-subscription.png)

*Figura. WF13, consulta y actualización del plan de suscripción.*

*Nota. Elaboración propia.*

##### WF14. Edición o desactivación de un medicamento

**User Persona:** Diego Dani Mendoza.

**User Goal:** Editar una pauta o desactivar un medicamento sin perder el historial.

**User Stories relacionadas:** US-04.

El recorrido representa la administración de un medicamento dentro de un tratamiento. El cuidador puede guardar cambios en la pauta o desactivar el medicamento. En ambos casos se conserva el historial previo y el sistema diferencia el estado actualizado del estado desactivado.

![WF14 editar y desactivar medicamento](assets/mobile-app-wireflow-edit-disable-medication.png)

*Figura. WF14, edición y desactivación de un medicamento.*

*Nota. Elaboración propia.*

##### WF15. Recordatorio reforzado, confirmación tardía y omisión

**User Persona:** Doña Carmen Rodríguez.

**User Goal:** Recibir recordatorios reforzados y resolver una toma tardía u omitida.

**User Stories relacionadas:** US-05, US-22 y US-23.

Este flujo representa el comportamiento posterior a una toma que no fue confirmada en el momento esperado. El sistema emite un segundo recordatorio y permite una confirmación tardía mientras la toma permanece dentro del periodo de tolerancia. Cuando ese periodo vence, la toma se mantiene registrada como omitida y una confirmación posterior no reemplaza automáticamente dicho estado.

![WF15 recordatorio reforzado confirmación tardía y omisión](assets/mobile-app-wireflow-reinforced-reminder-late-omission.png)

*Figura. WF15, recordatorio reforzado, confirmación tardía y omisión.*

*Nota. Elaboración propia.*

##### WF16. Landing, comparación de planes y destino externo no disponible

**User Persona:** Usuario visitante.

**User Goal:** Conocer Tata, comparar planes y gestionar un destino externo no disponible.

**User Stories relacionadas:** US-49.

Este wireflow representa la navegación del usuario visitante. El recorrido parte de la presentación de Tata, continúa hacia la comparación de planes y contempla el caso en el que un destino externo asociado con la opción de contacto no se encuentra disponible. Este estado permite mantener una respuesta visible dentro del producto en lugar de dejar la interacción sin retroalimentación.

![WF16 landing planes y destino externo](assets/mobile-app-wireflow-landing-plans-external-destination.png)

*Figura. WF16, navegación del visitante, comparación de planes y destino externo no disponible.*

*Nota. Elaboración propia.*

Los dieciséis wireflows muestran que las pantallas no fueron diseñadas como vistas aisladas. Cada vista forma parte de un recorrido asociado con un objetivo de usuario y sus estados alternos responden a condiciones concretas de interacción. Esta relación permitió comprobar la continuidad entre la arquitectura de información, los criterios de aceptación y los cambios de estado antes de consolidar el diseño visual de alta fidelidad.

La incorporación posterior de las pantallas Login, Notes - Adult, Notes - Caregiver e Internationalization amplía los destinos disponibles en el prototipo sin modificar la lógica principal representada por estos dieciséis User Goals.

#### 3.1.4.3. Mobile Applications Mock-ups

Las diez imágenes siguientes corresponden a las diez filas del [tablero de mock-ups](https://www.figma.com/design/jCppvxtSpLpHOrC3ZWUIVC/VitaHealth?node-id=31-2), con siete variantes por fila y la misma numeración que los wireframes.

Los mock-ups representan la versión de alta fidelidad de las pantallas definidas previamente en los wireframes. La estructura funcional se mantiene, pero se incorpora el sistema visual de Tata mediante tipografías, jerarquías, colores, tarjetas, botones, iconografía, estados de navegación y elementos de apoyo visual.

La propuesta mantiene consistencia entre las pantallas del adulto mayor y las del familiar o cuidador, pero adapta la navegación y la prioridad de la información a las tareas de cada perfil. Los estados de éxito, advertencia, error, información y confirmación utilizan tratamientos visuales diferenciados para facilitar su reconocimiento. Asimismo, se aplican criterios de diseño inclusivo mediante tamaño legible de controles y textos, contraste suficiente, reducción de movimiento, confirmación por voz y ayuda de lectura.

Los mock-ups conservan correspondencia directa con los wireframes. La versión funcional final está compuesta por **70 pantallas** y mantiene la misma numeración utilizada en los wireframes y en el prototipo. Las variantes `EN` corresponden únicamente a traducciones de estas vistas y no se contabilizan como pantallas adicionales.

##### 01. Entry, Onboarding & Access

El primer grupo presenta la identidad visual de Tata desde los puntos de entrada y continúa con el onboarding, el registro, la vinculación, el acceso mediante PIN y el inicio de sesión de usuarios existentes. La composición prioriza las acciones principales, la información contextual y los estados de acceso sin perder continuidad entre pantallas.

**Pantallas incluidas:** 01 Landing - Value & Features; 02 Landing - Plans & Contact; 03 Onboarding; 04 Caregiver Registration; 05 Link & Consent; 06 PIN Access; 07 Login.

![Mock-ups de entrada, onboarding y acceso](assets/mobile-app-mockups-entry-onboarding-access.png)

*Figura. Mock-ups de entrada, onboarding y acceso a Tata.*

*Nota. Elaboración propia.*

##### 02. Older Adult Daily Experience

Este grupo representa la experiencia cotidiana del adulto mayor. El diseño prioriza la próxima toma, el progreso diario, la consulta de medicamentos, la agenda, la confirmación de toma y los ajustes de accesibilidad mediante una jerarquía visual simple y acciones de fácil reconocimiento.

**Pantallas incluidas:** 08 Home; 09 My Medications; 10 Medication Detail; 11 Weekly Schedule; 12 Voice Confirmation; 13 Dose Confirmed; 14 Accessibility.

![Mock-ups de la experiencia diaria del adulto mayor](assets/mobile-app-mockups-older-adult-daily-experience.png)

*Figura. Mock-ups de la experiencia diaria del adulto mayor.*

*Nota. Elaboración propia.*

##### 03. Monitoring, Insights & Adult Notes

Las pantallas de este grupo corresponden principalmente al seguimiento realizado por el familiar o cuidador mediante el resumen familiar, la persona vinculada, las alertas, el historial y las recomendaciones. La fila incorpora además la pantalla de notas del adulto mayor, utilizada como destino de la pestaña “Notas” dentro de su navegación principal.

**Pantallas incluidas:** 15 Family Summary; 16 Linked Person; 17 Alerts; 18 Alert Detail; 19 History & Insights; 20 Adherence Recommendations; 21 Notes - Adult.

![Mock-ups de seguimiento, insights y notas del adulto mayor](assets/mobile-app-mockups-monitoring-insights-adult-notes.png)

*Figura. Mock-ups de seguimiento familiar, alertas, insights y notas del adulto mayor.*

*Nota. Elaboración propia.*

##### 04. Caregiver Treatment Management & Notes

Este conjunto incorpora la gestión del tratamiento. La interfaz utiliza formularios, tarjetas de estado y acciones principales para registrar medicamentos, crear y administrar tratamientos, controlar inventario, configurar notificaciones, consultar las notas del cuidador y gestionar la suscripción.

**Pantallas incluidas:** 22 Add Medication - Caregiver; 23 Create Treatment; 24 Treatment Management; 25 Inventory & Restock; 26 Notification Preferences; 27 Notes - Caregiver; 28 Plan & Subscription.

![Mock-ups de gestión del tratamiento y notas del cuidador](assets/mobile-app-mockups-caregiver-treatment-management-notes.png)

*Figura. Mock-ups de gestión del tratamiento, inventario, notificaciones, notas y suscripción.*

*Nota. Elaboración propia.*

##### 05. Access, Registration & Consent States

Los estados de validación conservan la estructura principal de las pantallas base, pero incorporan mensajes y tratamientos visuales específicos para comunicar un PIN incorrecto, bloqueo temporal, correo duplicado, verificación vencida, código inválido o falta de consentimiento.

**Pantallas incluidas:** 29 PIN Setup; 30 PIN Incorrect; 31 PIN Temporarily Blocked; 32 Duplicate Email; 33 Verification Expired; 34 Invalid Link Code; 35 Consent Required.

![Mock-ups de validaciones de acceso registro y consentimiento](assets/mobile-app-mockups-access-registration-consent-states.png)

*Figura. Mock-ups de validaciones de acceso, registro y consentimiento.*

*Nota. Elaboración propia.*

##### 06. Medication, Reminder & Adherence States

Este grupo presenta estados alternos de medicamentos, confirmación de tomas e historial. Los mensajes visuales permiten diferenciar datos obligatorios faltantes, cambios guardados, desactivación, recordatorios, voz no reconocida, confirmación duplicada y ausencia de información suficiente para calcular adherencia.

**Pantallas incluidas:** 36 Medication Required Fields Error; 37 Medication Updated; 38 Medication Deactivated; 39 Medication Reminder Due; 40 Voice Not Recognized; 41 Dose Already Confirmed; 42 No Adherence Data.

![Mock-ups de medicamentos recordatorios y adherencia](assets/mobile-app-mockups-medication-reminder-adherence-states.png)

*Figura. Mock-ups de validaciones de medicamentos, recordatorios y adherencia.*

*Nota. Elaboración propia.*

##### 07. Treatment & Dose States

Las pantallas de este grupo presentan estados de configuración y de una toma individual. Se conserva la estructura de las pantallas principales y se emplean mensajes, etiquetas y tarjetas diferenciadas para tratamiento incompleto, pausado, restringido, ausencia de próxima toma y estados pendiente, confirmado y tardío.

**Pantallas incluidas:** 43 Treatment Incomplete; 44 Treatment Paused; 45 Treatment Access Denied; 46 No Next Dose; 47 Dose Detail - Pending; 48 Dose Detail - Confirmed; 49 Dose Detail - Late.

![Mock-ups de estados de tratamiento y toma](assets/mobile-app-mockups-treatment-dose-states.png)

*Figura. Mock-ups de estados de tratamiento y de una toma.*

*Nota. Elaboración propia.*

##### 08. Omission, Reinforcement & Follow-up States

Este grupo muestra los estados asociados con una omisión y el seguimiento posterior. La interfaz diferencia una toma omitida, un recordatorio reforzado, una confirmación tardía, la preservación de la omisión, la agenda con estados, la ausencia de resultados y la falta de un canal de contacto válido.

**Pantallas incluidas:** 50 Dose Detail - Omitted; 51 Reinforced Reminder; 52 Late Dose Confirmed; 53 Omission Preserved; 54 Agenda With Statuses; 55 Empty Intake History; 56 Contact Unavailable.

![Mock-ups de omisiones y seguimiento](assets/mobile-app-mockups-omission-reinforcement-follow-up.png)

*Figura. Mock-ups de omisiones, recordatorios reforzados y seguimiento.*

*Nota. Elaboración propia.*

##### 09. Follow-up & Accessibility States

Este grupo muestra resultados posteriores a acciones del cuidador y variaciones de accesibilidad. Se utilizan mensajes de confirmación para el registro de notas, la atención de alertas y el cambio de periodo, además de estados de interfaz que evidencian el aumento de texto, el contraste reforzado y la reducción de movimiento.

**Pantallas incluidas:** 57 Follow-up Note Saved; 58 Alert Attended; 59 Adherence Period Changed; 60 Insufficient Evidence; 61 Large Text Enabled; 62 High Contrast Enabled; 63 Reduced Motion Enabled.

![Mock-ups de seguimiento y accesibilidad](assets/mobile-app-mockups-follow-up-accessibility-states.png)

*Figura. Mock-ups de seguimiento, evidencia y configuraciones de accesibilidad.*

*Nota. Elaboración propia.*

##### 10. Preferences, Inventory, Subscription & Internationalization

El último grupo reúne la ayuda de lectura activada, la confirmación de preferencias de notificación, los estados de inventario y reposición, la actualización de la suscripción, la indisponibilidad de un destino externo y la selección del idioma de la aplicación.

La pantalla de internacionalización se integra dentro de la sección de accesibilidad y mantiene el mismo sistema visual de controles y configuraciones. La opción de idioma permite representar el cambio hacia la interfaz en inglés, cuyas vistas `EN` reproducen la misma arquitectura y funcionalidad de las pantallas principales.

**Pantallas incluidas:** 64 Reading Assistance Enabled; 65 Notification Preferences Saved; 66 Invalid Inventory Quantity; 67 Stock Replenished; 68 Subscription Updated; 69 External Destination Unavailable; 70 Internationalization.

![Mock-ups de preferencias inventario suscripción e internacionalización](assets/mobile-app-mockups-preferences-inventory-subscription-states.png)

*Figura. Mock-ups de preferencias guardadas, inventario, suscripción, destino externo e internacionalización.*

*Nota. Elaboración propia.*

Los **70 mock-ups** mantienen correspondencia con los wireframes y con los recorridos definidos en los wireflows. Las variaciones visuales no modifican el objetivo funcional de cada pantalla, sino que comunican con mayor claridad la jerarquía, los estados, las acciones y la retroalimentación del sistema.

Las versiones en inglés mantienen esta misma estructura y constituyen variantes de localización, por lo que no incrementan el número de pantallas funcionales considerado en el diseño.


#### 3.1.4.4. Mobile Applications User Flow Diagrams

Los recorridos se organizan por objetivo del usuario y rol. Los diagramas de la sección 3.1.4.2 muestran las transiciones entre vistas y sus estados; esta sección identifica el punto de entrada, las decisiones y el resultado de cada recorrido. Se mantiene la numeración del [tablero de wireflows](https://www.figma.com/design/jCppvxtSpLpHOrC3ZWUIVC/VitaHealth?node-id=283-2) para relacionar cada objetivo con su diagrama visual.

| Perfil | Objetivo | Recorrido y decisiones | Diagrama |
| --- | --- | --- | --- |
| Adulto mayor | Acceder y consultar la próxima toma | Ingresar PIN → validar acceso → Inicio → próxima toma; el PIN incorrecto y el bloqueo ofrecen estados alternos. | WF01 |
| Adulto mayor | Confirmar una toma | Próxima toma → confirmar por toque o voz → resultado; la voz no reconocida permite reintentar y una toma confirmada conserva su registro. | WF02 |
| Adulto mayor | Consultar medicación y agenda | Medicamentos → detalle; Agenda → toma → estado pendiente, confirmado, tardío u omitido. | WF03–WF04 |
| Adulto mayor | Ajustar accesibilidad | Más → Accesibilidad → elegir preferencia → interfaz con ajuste aplicado. | WF05 |
| Familiar/cuidador | Crear cuenta y vincular al adulto | Registro → verificación → código de vínculo → solicitud → consentimiento; los datos inválidos permiten corregir el paso. | WF06 |
| Familiar/cuidador | Configurar y administrar un tratamiento | Registrar medicamento → definir pauta → gestionar tratamiento; editar, pausar o desactivar según la acción elegida. | WF07, WF14 |
| Familiar/cuidador | Revisar adherencia y actuar ante una alerta | Resumen → persona vinculada → historial o alertas → detalle → contacto o nota → alerta atendida. | WF08–WF10 |
| Familiar/cuidador | Mantener la continuidad del cuidado | Inventario → reposición → cantidad actualizada; preferencias → guardar; plan → elegir → suscripción actualizada. | WF11–WF13 |
| Adulto mayor y familiar | Gestionar una toma fuera de horario | Recordatorio reforzado → confirmación tardía u omisión conservada → agenda e historial. | WF15 |
| Visitante | Conocer Tata y elegir un plan | Propuesta de valor → funciones → comparación de planes → registro o contacto; el destino externo dispone de un estado de indisponibilidad. | WF16 |

Cada fila de wireframes y mock-ups incluye los resultados alternos de estos recorridos, evitando tratar las validaciones, errores y confirmaciones como destinos aislados.

#### 3.1.4.5. Mobile Applications Prototyping

[Abrir prototipo interactivo en español](https://www.figma.com/proto/jCppvxtSpLpHOrC3ZWUIVC/VitaHealth?node-id=563-5). [Consultar conexiones en el archivo de diseño](https://www.figma.com/design/jCppvxtSpLpHOrC3ZWUIVC/VitaHealth?node-id=563-2).

El prototipo interactivo de la aplicación móvil de Tata fue construido a partir de los mock-ups de alta fidelidad y conserva la correspondencia de las **70 pantallas funcionales** definidas previamente. Su objetivo es validar la navegación real entre vistas, comprobar que las acciones principales conducen al estado esperado y representar de forma interactiva los recorridos previamente analizados mediante los wireflow diagrams.

Cada pantalla utilizada en el prototipo mantiene la misma numeración y estructura que su wireframe y mock-up correspondiente. Esto permite relacionar directamente los artefactos del informe con las vistas implementadas en Figma y facilita la trazabilidad entre wireframe, mock-up, flujo y prototipo.

Las versiones `EN` disponibles en Figma constituyen traducciones de las mismas pantallas y no se consideran prototipos funcionales adicionales dentro del conteo de 70 vistas.

![Vista general del prototipo móvil](assets/mobile-app-prototyping-overview.png)

*Figura. Vista general de las 70 pantallas utilizadas en el prototipo interactivo de Tata.*

*Nota. Elaboración propia.*

El prototipo contempla interacciones correspondientes al onboarding, registro del cuidador, inicio de sesión, vinculación, acceso mediante PIN, consulta de próximas tomas, medicamentos, agenda, confirmación por voz, seguimiento familiar, alertas, tratamientos, inventario, accesibilidad, preferencias, suscripción e internacionalización. Asimismo, los estados alternos de validación y error se conectan con las pantallas que representan sus respectivos resultados.

La navegación inferior también fue incorporada al prototipo. Para el perfil del adulto mayor se utilizan las opciones **Inicio, Medicamentos, Agenda, Notas y Más**. La opción **Notas** conduce a la pantalla **21 Notes - Adult**. Para el perfil del familiar o cuidador se utilizan **Inicio, Alertas, Notas, Persona y Más**, donde la opción **Notas** conduce a la pantalla **27 Notes - Caregiver**.

![Prototipo de navegación inferior del adulto mayor](assets/mobile-app-prototyping-older-adult-bottom-navigation.png)

*Figura. Navegación inferior interactiva correspondiente al perfil del adulto mayor.*

*Nota. Elaboración propia.*

![Prototipo de navegación inferior del familiar o cuidador](assets/mobile-app-prototyping-caregiver-bottom-navigation.png)

*Figura. Navegación inferior interactiva correspondiente al perfil del familiar o cuidador.*

*Nota. Elaboración propia.*

En las pantallas que incorporan una barra de navegación inferior, cada opción funciona como un destino independiente y no como un único elemento interactivo. De esta manera, el usuario puede desplazarse directamente entre las secciones principales desde las distintas vistas del prototipo, manteniendo el comportamiento esperado de una aplicación móvil.

Las acciones contextuales también fueron conectadas con sus respectivos estados. Por ejemplo, la selección de un medicamento permite abrir su detalle, la agenda permite acceder a las tomas correspondientes, la confirmación por voz conduce al resultado de la toma, una alerta puede abrir su detalle y posteriormente actualizarse como atendida, y las configuraciones de accesibilidad conducen a vistas donde se evidencia la preferencia aplicada.

La pantalla de inicio de sesión incorpora el acceso mediante correo electrónico y contraseña, además de las alternativas de continuación representadas en la interfaz. Por su parte, la pantalla de internacionalización extiende las configuraciones de accesibilidad mediante la selección del idioma de la aplicación y permite enlazar conceptualmente con las variantes traducidas de la interfaz.

Las conexiones interactivas se consultan en el [prototipo original de Figma](https://www.figma.com/design/jCppvxtSpLpHOrC3ZWUIVC/VitaHealth?node-id=563-2), donde se pueden inspeccionar los destinos de cada acción.

La incorporación de las pantallas **21 Notes - Adult** y **27 Notes - Caregiver** completa la navegación de la opción Notas para ambos perfiles. Estas vistas permiten evitar destinos inexistentes dentro de la barra inferior y mantienen la diferenciación de contenido entre la información personal del adulto mayor y las notas de seguimiento registradas por el familiar o cuidador.

Asimismo, la incorporación de **07 Login** proporciona un punto de acceso explícito para usuarios previamente registrados, mientras que **70 Internationalization** completa la configuración de idioma de la aplicación. Las traducciones `EN` derivadas de esta configuración mantienen la misma estructura funcional y no se contabilizan como pantallas independientes.

En conjunto, el prototipo permite comprobar que los componentes visuales de los mock-ups no funcionan como elementos aislados, sino como parte de recorridos navegables. La relación entre wireframes, wireflows, mock-ups y prototipado proporciona continuidad entre la estructura inicial, los escenarios funcionales, la representación visual definitiva y la interacción esperada de la aplicación móvil de Tata.
