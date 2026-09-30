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

#### 3.1.3.1. Landing Page Wireframe

#### 3.1.3.2. Landing Page Mock-up

### 3.1.4. Mobile Applications UX/UI Design

#### 3.1.4.1. Mobile Applications Wireframes

#### 3.1.4.2. Mobile Applications Wireflow Diagrams

#### 3.1.4.3. Mobile Applications Mock-ups

#### 3.1.4.4. Mobile Applications User Flow Diagrams

#### 3.1.4.5. Mobile Applications Prototyping
