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

#### 3.1.2.1. Organization Systems

#### 3.1.2.2. Labelling Systems

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

### 3.1.3. Landing Page UI Design

#### 3.1.3.1. Landing Page Wireframe

#### 3.1.3.2. Landing Page Mock-up

### 3.1.4. Mobile Applications UX/UI Design

#### 3.1.4.1. Mobile Applications Wireframes

#### 3.1.4.2. Mobile Applications Wireflow Diagrams

#### 3.1.4.3. Mobile Applications Mock-ups

#### 3.1.4.4. Mobile Applications User Flow Diagrams

#### 3.1.4.5. Mobile Applications Prototyping
