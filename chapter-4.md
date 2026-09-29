# Capítulo IV: Product Implementation & Validation

# 4. Product Implementation & Validation

## 4.1. Software Configuration Management

### 4.1.1. Software Development Environment Configuration

| Actividad | Producto | Propósito | Ruta de referencia / descarga |
| --- | --- | --- | --- |
| Project Management / Requirements Management | Trello | Gestión del Product Backlog, los Sprints y las User Stories, Technical Stories y Spike Stories | https://trello.com/b/wuHmMypU/apps-moviles |
| Product UX/UI Design | Figma | Elaboración de Wireframes, Mock-ups y Prototypes del Landing Page y las aplicaciones móviles | (FALTA) |
| Product UX/UI Design | UXPressia | Elaboración de User Personas, Empathy Maps, User Journey Maps e Impact Mapping | https://uxpressia.com |
| Software Development | Android Studio | IDE para el desarrollo de la aplicación Android nativa (Kotlin) y la aplicación multiplataforma (Flutter) | https://developer.android.com/studio |
| Software Development | Spring Boot Framework (Java) | Framework para el desarrollo del backend RESTful | https://spring.io/projects/spring-boot |
| Software Development | Miro | Big Picture EventStorming, EventStorming, Candidate Context Discovery, Domain Message Flows y Bounded Context Canvases | https://miro.com/app/board/uXjVHq5Jc9w=/ |
| Software Development | Structurizr | Elaboración de los diagramas C4 (Context, Container, Deployment) de la arquitectura de software | https://structurizr.com |
| Software Development | PlantUML | Elaboración de los Class Diagrams del Domain Layer por Bounded Context | https://plantuml.com |
| Software Development | Vertabelo | Diseño de los diagramas de base de datos por Bounded Context | https://vertabelo.com |
| Software Testing | JUnit 5 + Mockito | Unit testing de las clases del backend | https://junit.org/junit5/ |
| Software Testing | Cucumber-JVM | Integration/Acceptance testing en Gherkin de los endpoints del backend | https://cucumber.io/docs/installation/java/ |
| Software Testing | Espresso | Testing de UI de la aplicación Android nativa | https://developer.android.com/training/testing/espresso |
| Software Testing | flutter_test | Unit e integration testing de la aplicación multiplataforma | https://docs.flutter.dev/testing |
| Software Deployment | Render | Despliegue del backend y de la base de datos PostgreSQL | https://render.com |
| Software Deployment | GitHub Pages | Despliegue del Landing Page | https://pages.github.com |
| Software Documentation | Swagger / OpenAPI | Documentación de los endpoints del backend | https://swagger.io |

### 4.1.2. Source Code Management

### 4.1.3. Source Code Style Guide & Conventions

En esta sección el equipo establece las guías de estilo y convenciones de código que se aplican en todos los productos de Tata. El objetivo es que el código escrito por los seis integrantes se lea como si lo hubiera escrito una sola persona, y que los nombres usados en el código correspondan a los conceptos definidos en el Ubiquitous Language (sección 2.3.6) y en el Tactical-Level Domain-Driven Design (sección 2.6).

La solución utiliza los siguientes lenguajes, y para cada uno se adopta una guía de referencia:

| Lenguaje | Producto de Tata | Guía de referencia adoptada |
| --- | --- | --- |
| HTML5 | Landing Page | HTML Style Guide and Coding Conventions (W3Schools) y Google HTML/CSS Style Guide |
| CSS3 | Landing Page | Google HTML/CSS Style Guide |
| JavaScript | Landing Page | Google JavaScript Style Guide |
| Java (Spring Boot) | Web Services (backend y API Gateway) | Google Java Style Guide y Spring Boot Features |
| Kotlin | Aplicación Android nativa | Kotlin Coding Conventions y Android Kotlin Style Guide |
| Dart (Flutter) | Aplicación móvil multiplataforma | Effective Dart |
| Gherkin | Archivos `.feature` de pruebas de aceptación (Cucumber-JVM) | Gherkin Conventions for Readable Specifications |
| SQL | Base de datos PostgreSQL | Convenciones propias del equipo, alineadas con los Database Design Diagrams de la sección 2.6 |

#### Convenciones generales

Las siguientes reglas aplican a todos los repositorios, independientemente del lenguaje:

- **Nomenclatura en inglés.** Clases, métodos, variables, archivos, carpetas, endpoints, tablas y columnas se nombran en inglés. Los conceptos del dominio se toman de la versión en inglés del Ubiquitous Language para no inventar sinónimos: `Intake` (toma), `Treatment` (tratamiento), `Medication` (medicamento), `CareLink` (vínculo de cuidado), `OlderAdult` (adulto mayor), `Caregiver` (cuidador), `OmissionCase` (caso de omisión), `Alert` (alerta), `QuietHours` (horario de silencio). Por ejemplo, se escribe `confirmIntake()` y no `confirmarToma()` ni `confirmDose()`.
- **Textos visibles en español y fuera del código.** Todo texto que ve el adulto mayor o el familiar se escribe en español y se ubica en archivos de recursos (`strings.xml` en Android, archivos de localización en Flutter y el propio HTML en el Landing Page), nunca como literal dentro de la lógica. Esto permite revisar el tono de comunicación definido en la sección 3.1.1.1 sin modificar el código.
- **Comentarios en inglés** y solo cuando explican el *porqué* de una decisión (por ejemplo, por qué una toma confirmada dos veces no genera un segundo registro). No se deja código comentado en los commits.
- **Formato de archivo.** Codificación UTF-8, fin de línea LF y un salto de línea al final de cada archivo. Cada repositorio incluye un archivo `.editorconfig` en la raíz con la indentación de su lenguaje: 2 espacios para HTML, CSS, JavaScript, Java, Dart, Gherkin y YAML; 4 espacios para Kotlin.
- **Tokens de diseño compartidos.** Los colores, tipografías y espaciados de *Tata Design Foundations* (sección 3.1.1.1) se definen una sola vez por producto con el mismo nombre de token, para que un cambio de marca se haga en un solo lugar:

| Token (sección 3.1.1.1) | Landing Page (CSS) | Android (Kotlin) | Flutter (Dart) |
| --- | --- | --- | --- |
| Primary `#173B70` | `--color-primary` | `TataColors.Primary` | `TataColors.primary` |
| Ink `#0E1729` | `--color-ink` | `TataColors.Ink` | `TataColors.ink` |
| Sage `#E8F5EB` | `--color-sage` | `TataColors.Sage` | `TataColors.sage` |
| Cream `#FFF3E2` | `--color-cream` | `TataColors.Cream` | `TataColors.cream` |
| Grid base 8 dp | `--space-unit: 8px` | `TataSpacing.Unit = 8.dp` | `TataSpacing.unit = 8.0` |
| Touch target 44 dp | `--touch-target: 44px` | `TataSpacing.TouchTarget = 44.dp` | `TataSpacing.touchTarget = 44.0` |

#### HTML5 (Landing Page)

Se sigue *HTML Style Guide and Coding Conventions* y *Google HTML/CSS Style Guide*:

- Se declara `<!DOCTYPE html>` y `<html lang="es">`, porque el contenido del Landing Page está en español. Se incluyen `<meta charset="UTF-8">`, la etiqueta `viewport` y las meta tags definidas en la sección 3.1.2.3 (title, description, keywords y author).
- Nombres de elementos y atributos en minúsculas, valores de atributos entre comillas dobles y todos los elementos cerrados correctamente.
- Se usan elementos semánticos (`header`, `nav`, `main`, `section`, `footer`) en lugar de `div` genéricos, y un único `h1` por página.
- Toda imagen tiene un atributo `alt` descriptivo en español; por ejemplo, el isotipo se describe como `alt="Logotipo de Tata, mariposa en dos tonos de morado"`.
- No se usan estilos ni scripts en línea (`style=""`, `onclick=""`); se enlazan desde archivos externos.
- Los `id` y las clases se escriben en inglés y en *kebab-case*, y se nombran por su función, no por su apariencia: `plans-section`, `plan-card`, `contact-form`, en lugar de `purple-box` o `seccion2`.
- Estructura del repositorio: `index.html` en la raíz y los recursos en `assets/css/`, `assets/js/` y `assets/images/`. Los nombres de archivo van en minúsculas y en *kebab-case* (`hero-older-adult.webp`).

#### CSS3 (Landing Page)

Se sigue *Google HTML/CSS Style Guide*:

- Una declaración por línea, un espacio después de los dos puntos, punto y coma al final de cada declaración y una línea en blanco entre reglas.
- Los colores hexadecimales se escriben en minúsculas dentro del código (`#173b70`), aunque en la documentación de diseño aparezcan en mayúsculas.
- Los tokens de diseño se declaran como variables CSS en `:root` y el resto de las reglas solo las referencia:

```css
:root {
  --color-primary: #173b70;
  --color-ink: #0e1729;
  --color-secondary: #7b879b;
  --color-lavender: #f1ecff;
  --color-canvas: #f8f8fe;
  --font-display: "DM Serif Display", serif;
  --font-body: "Inter", sans-serif;
  --space-unit: 8px;
}

.plan-card {
  padding: calc(var(--space-unit) * 3);
  border-radius: 20px;
  background-color: var(--color-lavender);
}
```

- Los tamaños de fuente se expresan en `rem` para respetar la configuración de tamaño de texto del navegador, en coherencia con el uso de `sp` en las aplicaciones móviles.

#### JavaScript (Landing Page)

Se sigue *Google JavaScript Style Guide*:

- Se usa `const` por defecto, `let` solo cuando la variable se reasigna, y nunca `var`.
- Variables y funciones en *lowerCamelCase* (`validateContactForm`); constantes de módulo en *UPPER_SNAKE_CASE* (`CONTACT_FORM_ID`).
- Comparaciones con `===` y `!==`, punto y coma al final de cada sentencia y comillas simples para cadenas.
- Los eventos se registran con `addEventListener` desde `assets/js/main.js`, no con atributos en el HTML.

```javascript
const CONTACT_FORM_ID = 'contact-form';

function validateContactForm(form) {
  const email = form.elements.email.value.trim();
  return email !== '' && email.includes('@');
}

document.getElementById(CONTACT_FORM_ID).addEventListener('submit', (event) => {
  if (!validateContactForm(event.target)) {
    event.preventDefault();
  }
});
```

#### Java y Spring Boot (Web Services)

Se sigue *Google Java Style Guide*: indentación de 2 espacios, límite de 100 caracteres por línea, una clase de nivel superior por archivo, llaves obligatorias incluso en bloques de una línea y sin importaciones con comodín (`import java.util.*`).

**Nomenclatura:**

| Elemento | Convención | Ejemplo en Tata |
| --- | --- | --- |
| Paquete | minúsculas, sin guiones bajos | `com.vitahealth.tata.intake.domain.model.aggregates` |
| Clase / Record / Enum | *UpperCamelCase*, sustantivo | `Intake`, `ToleranceWindow`, `IntakeStatus` |
| Método | *lowerCamelCase*, verbo | `confirm()`, `expireTolerance()`, `findNextByOlderAdultId()` |
| Variable / atributo | *lowerCamelCase* | `scheduledAt`, `remindersIssued` |
| Constante | *UPPER_SNAKE_CASE* | `MAX_REMINDERS_PER_INTAKE` |
| Valor de enum | *UPPER_SNAKE_CASE* | `PENDING`, `CONFIRMED`, `ESCALATED`, `TAP`, `VOICE` |

**Organización de paquetes por Bounded Context.** El backend es un único desplegable (sección 2.5.3), pero cada Bounded Context tiene su propio paquete raíz y, dentro de él, las cuatro capas definidas en la sección 2.6:

| Bounded Context | Paquete raíz |
| --- | --- |
| Identity & Subscription | `com.vitahealth.tata.identity` |
| Care Link | `com.vitahealth.tata.carelink` |
| Treatment Management | `com.vitahealth.tata.treatment` |
| Intake Execution | `com.vitahealth.tata.intake` |
| Omission & Escalation | `com.vitahealth.tata.escalation` |
| Adherence Analytics | `com.vitahealth.tata.adherence` |
| Family Monitoring | `com.vitahealth.tata.monitoring` |
| Accessibility & Preferences | `com.vitahealth.tata.accessibility` |
| Inventory & Replenishment | `com.vitahealth.tata.inventory` |
| Elementos compartidos | `com.vitahealth.tata.shared` |

Por ejemplo, el Bounded Context Intake Execution se organiza así:

```text
com.vitahealth.tata.intake
├── domain
│   ├── model
│   │   ├── aggregates        -> Intake
│   │   ├── valueobjects      -> MedicationSnapshot, ToleranceWindow, IntakeStatus, ConfirmationChannel
│   │   ├── commands          -> ConfirmIntakeCommand, GenerateIntakeScheduleCommand
│   │   ├── queries           -> GetNextIntakeQuery, GetDailyIntakeAgendaQuery
│   │   └── events            -> IntakeHistoryUpdated, IntakeToleranceExpired
│   ├── services              -> IntakeSchedulingService, VoiceConfirmationValidationService
│   └── repositories          -> IIntakeRepository
├── application
│   └── internal
│       ├── commandservices   -> ConfirmIntakeCommandHandler, ...
│       ├── queryservices     -> GetNextIntakeQueryHandler, ...
│       ├── eventhandlers     -> TreatmentActivatedEventHandler, ...
│       └── outboundservices  -> IVoiceRecognitionPort, IDomainEventPublisher
├── interfaces
│   ├── rest
│   │   ├── controllers       -> IntakeQueriesController, IntakeConfirmationController
│   │   ├── resources         -> NextIntakeResource, IntakeDetailResource, ...
│   │   └── transform         -> IntakeResourceFromEntityAssembler, ...
│   └── events                -> TreatmentActivatedEventConsumer, ...
└── infrastructure
    ├── persistence/jpa       -> IntakeRepository
    ├── scheduling            -> ReminderScheduler, ToleranceExpirationScheduler
    ├── external              -> VoiceRecognitionAdapter
    └── events                -> IntakeDomainEventPublisher, TreatmentActivatedEventListener
```

**Sufijos por tipo de elemento.** Se mantienen los nombres ya definidos en el Tactical-Level Domain-Driven Design:

| Tipo | Regla | Ejemplo |
| --- | --- | --- |
| Aggregate / Entity | Sustantivo del dominio, sin sufijo | `Intake`, `Treatment`, `CareLink`, `OmissionCase` |
| Value Object | Sustantivo, sin sufijo; se implementa como `record` cuando es inmutable | `ToleranceWindow`, `MedicationSnapshot` |
| Domain Event | Verbo en pasado, sin sufijo `Event` | `TreatmentActivated`, `IntakeToleranceExpired` |
| Command / Query | Verbo en imperativo + sufijo | `ConfirmIntakeCommand`, `GetNextIntakeQuery` |
| Handler | Nombre del command, query o evento + `Handler` | `ConfirmIntakeCommandHandler`, `GetNextIntakeQueryHandler` |
| Resource (DTO REST) | Sustantivo + `Resource` | `IntakeDetailResource`, `IntakeConfirmationResource` |
| Assembler | Destino + `From` + origen + `Assembler` | `IntakeResourceFromEntityAssembler` |
| Controller | Recurso en plural + `Controller`; si un recurso se separa por responsabilidad, recurso + responsabilidad + `Controller` | `TreatmentsController`, `IntakeConfirmationController` |
| Repositorio / puerto (contrato) | Prefijo `I` + nombre | `IIntakeRepository`, `IVoiceRecognitionPort` |
| Repositorio / adaptador (implementación) | Nombre sin prefijo + `Repository` o `Adapter` | `IntakeRepository`, `VoiceRecognitionAdapter` |
| Scheduler / Listener / Consumer | Responsabilidad + sufijo | `ReminderScheduler`, `TreatmentActivatedEventListener` |

El prefijo `I` en las interfaces es una convención propia del equipo que *Google Java Style Guide* no utiliza. Se mantiene únicamente para los contratos de repositorio y los puertos de las capas Domain y Application. Así se conserva la coherencia con el diseño de la sección 2.6 y se distingue a simple vista el contrato de su implementación en Infrastructure.

**Convenciones de Spring Boot** (según *Spring Boot Features*):

- Inyección de dependencias por constructor, con atributos `private final`; no se usa `@Autowired` sobre atributos.
- Configuración externa en `application.properties` con perfiles `dev` y `prod` (`application-dev.properties` y `application-prod.properties`). Las claves propias de Tata usan el prefijo `tata.` en *kebab-case*, por ejemplo `tata.reminders.reinforcement-interval=15m`.
- Credenciales, cadenas de conexión y API keys de servicios externos (correo, Speech-to-Text y notificaciones push) se leen de variables de entorno y nunca se versionan en el repositorio.

**Convenciones de la API REST:**

- Todas las rutas comienzan con `/api/v1`.
- Los recursos se nombran con sustantivos en plural y en *kebab-case*: `/api/v1/treatments`, `/api/v1/medications`, `/api/v1/care-links`, `/api/v1/intakes/{intakeId}`.
- Las acciones que no son CRUD se modelan como subrecursos: la confirmación de una toma (US-06, TS-04) es `POST /api/v1/intakes/{intakeId}/confirmations`.
- Las propiedades JSON se escriben en *lowerCamelCase* (`scheduledAt`, `confirmationChannel`), que es el comportamiento por defecto de Jackson.
- Los códigos HTTP se usan según su significado: `200` y `201` para éxito, `400` para validación, `401` y `403` para autenticación o permisos (por ejemplo, un familiar sin vínculo de cuidado activo) y `404` para recursos inexistentes.

**Pruebas.** Las clases de prueba se nombran como la clase probada más `Test` (`IntakeTest`, `ConfirmIntakeCommandHandlerTest`). Los métodos siguen el patrón `method_condition_expectedResult`, que *Google Java Style Guide* permite en pruebas: `confirm_whenIntakeIsPending_setsStatusConfirmed()`.

#### Kotlin (Aplicación Android nativa)

Se siguen *Kotlin Coding Conventions* y *Android Kotlin Style Guide*, usando el esquema de formato *Kotlin style guide* de Android Studio: indentación de 4 espacios y límite de 100 caracteres por línea.

- Paquete base `com.vitahealth.tata.android`, organizado primero por Bounded Context y luego por capa: `intake/data`, `intake/domain`, `intake/presentation`.
- Clases en *UpperCamelCase*; funciones y propiedades en *lowerCamelCase*; constantes (`const val`) en *UPPER_SNAKE_CASE*. El estado interno mutable de un ViewModel usa el prefijo `_` y se expone como inmutable: `private val _uiState` y `val uiState`.
- Sufijos por responsabilidad: `NextIntakeViewModel`, `IntakeRepository`, `IntakeDao` (Room), `IntakeEntity` (tabla local), `IntakeDto` (respuesta del backend), y `...Screen` o `...Activity`/`...Fragment` para las pantallas.
- Las tablas locales de Room usan los mismos nombres que en PostgreSQL (`@Entity(tableName = "intakes")`), para facilitar la sincronización de la información esencial (Technical Story de almacenamiento local).
- Los archivos de recursos se nombran en *snake_case* con prefijo de tipo: `activity_home.xml`, `ic_voice_confirmation.xml`, `bg_intake_card.xml`. Las claves de `strings.xml` llevan el prefijo de la pantalla: `home_next_intake_title`.
- Los tamaños de texto se definen en `sp` y las dimensiones en `dp`, respetando la escala de la sección 3.1.1.1 (Body 16 sp; CTA principal de 56 a 64 dp de alto).

#### Dart y Flutter (Aplicación móvil multiplataforma)

Se sigue *Effective Dart* y se aplica el formateador oficial (`dart format`, 2 espacios y 80 caracteres por línea). El análisis estático se hace con `flutter analyze` usando las reglas de `flutter_lints` declaradas en `analysis_options.yaml`.

- Archivos y carpetas en *lowercase_with_underscores*: `next_intake_screen.dart`, `intake_repository.dart`.
- Clases, enums y typedefs en *UpperCamelCase* (`NextIntakeScreen`, `IntakeStatus`). Variables, funciones, parámetros y constantes en *lowerCamelCase*, incluidas las constantes (`const primaryColor`), tal como indica *Effective Dart*.
- Los miembros privados de una librería llevan el prefijo `_` (`_confirmIntake()`).
- Las importaciones se ordenan en tres bloques: `dart:`, luego `package:` y al final las importaciones relativas.
- Estructura por Bounded Context: `lib/features/intake/{data,domain,presentation}` y los elementos comunes (tema, tokens, cliente HTTP) en `lib/core/`.
- Los widgets reutilizables se nombran por su función: `IntakeCard`, `PrimaryConfirmButton`, `VoiceConfirmationButton`.

#### Gherkin (archivos `.feature`)

Se sigue *Gherkin Conventions for Readable Specifications*:

- Las palabras clave (`Feature`, `Scenario`, `Given`, `When`, `Then`) y los textos se escriben en inglés, en coherencia con la regla de nomenclatura del enunciado.
- Un archivo `.feature` por User Story o Technical Story, ubicado en `src/test/resources/features/<bounded-context>/` y nombrado en *snake_case* con el identificador de la historia: `ts04_intake_confirmation_api.feature`.
- Cada `Feature` lleva etiquetas con el identificador de la historia y su Bounded Context (`@TS-04 @intake`), para trazarla con el Product Backlog.
- `Given` describe el contexto, `When` una sola acción y `Then` un resultado observable. Los escenarios se redactan en tercera persona y en tiempo presente, sin detalles de interfaz. Se usa `Background` para el contexto compartido y `Scenario Outline` con `Examples` cuando solo cambian los datos.
- Las clases de step definitions se nombran con el sufijo `StepDefinitions`: `IntakeConfirmationStepDefinitions`.

Ejemplo basado en los criterios de aceptación de TS-04:

```gherkin
@TS-04 @intake
Feature: Intake confirmation API
  As a developer
  I want to register the confirmation of an intake
  So that its status is updated idempotently

  Background:
    Given a pending intake with id 101 exists for an older adult

  Scenario: Confirm a pending intake by tap
    When a POST request is sent to "/api/v1/intakes/101/confirmations" with channel "TAP"
    Then the response status is 200
    And the intake 101 has status "CONFIRMED"

  Scenario: A repeated confirmation does not create a duplicate record
    Given the intake 101 has already been confirmed
    When a POST request is sent to "/api/v1/intakes/101/confirmations" with channel "TAP"
    Then intake 101 has exactly one confirmation registered
```

#### SQL (PostgreSQL)

Las convenciones siguen lo ya definido en los Database Design Diagrams de la sección 2.6:

- Tablas en plural y en *snake_case*: `intakes`, `treatments`, `care_links`, `omission_cases`.
- Columnas en *snake_case*. La clave primaria se llama `id` y las referencias lógicas a otros Bounded Contexts siguen el formato `<entidad>_id` (`treatment_id`, `older_adult_id`).
- Las fechas y horas terminan en `_at` (`scheduled_at`, `confirmed_at`) y todas las tablas incluyen las columnas de auditoría `created_at` y `updated_at`.
- Los enums se almacenan como texto en mayúsculas (`PENDING`, `TAP`), con los mismos valores que en Java.
- En las entidades JPA los atributos se escriben en *lowerCamelCase* (`scheduledAt`). La estrategia de nombres por defecto de Spring Boot los convierte automáticamente a *snake_case* (`scheduled_at`), por lo que no es necesario repetir `@Column(name = ...)` salvo excepciones.


### 4.1.4. Software Deployment Configuration


 
## 4.2. Landing Page & Mobile Application Implementation
### 4.2.1. Sprint 1
#### 4.2.1.1. Sprint Planning 1
#### 4.2.1.2. Aspect Leaders and Collaborators
#### 4.2.1.3. Sprint Backlog 1
#### 4.2.1.4. Development Evidence for Sprint Review
#### 4.2.1.5. Testing Suite Evidence for Sprint Review
#### 4.2.1.6. Execution Evidence for Sprint Review
#### 4.2.1.7. Services Documentation Evidence for Sprint Review
#### 4.2.1.8. Software Deployment Evidence for Sprint Review
#### 4.2.1.9. Team Collaboration Insights during Sprint
