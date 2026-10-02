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

Para el control de versiones de todos los productos de VitaHealth (Tata) se utiliza Git gestionado desde GitHub, aplicando GitFlow como workflow, Semantic Versioning para los releases y Conventional Commits para los mensajes de commit.
 
## Repositorios
 
| Producto | Repositorio | Contenido |
|---|---|---|
| Landing Page | `https://github.com/<org>/<landing-page>` | Sitio estático (HTML5, CSS3, JavaScript), publicado en GitHub Pages |
| Web Services | `https://github.com/<org>/<back-end>` | Proyecto del backend (RESTful API), pruebas unitarias y pruebas de integración/aceptación (archivos `.feature`) |
| Mobile Application | `https://github.com/<org>/<mobile-app>` | App Tata en Kotlin (Android) |
| Frontend Web Application | `https://github.com/<org>/<web-app>` | Aplicación web (si aplica a su alcance) |
 
## GitFlow Workflow
 
Se trabaja con dos ramas de vida larga y tres tipos de ramas de apoyo.
 
### Ramas permanentes
 
- **`main`**: contiene únicamente código estable y listo para producción. Cada merge a `main` corresponde a un release y se etiqueta con su versión.
- **`develop`**: rama de integración. Recibe todas las features terminadas y es la base de los release branches.
### Ramas de apoyo
 
#### Feature branches
 
- Se crean desde `develop` y se fusionan de vuelta a `develop` mediante Pull Request.
- Convención: `feature/<descripcion-corta-en-kebab-case>`
- Ejemplos: `feature/medication-reminders`, `feature/user-login`, `feature/caregiver-linking`
- Se eliminan después del merge.
#### Release branches
 
- Se crean desde `develop` cuando el conjunto de features del sprint está completo. Solo admiten correcciones menores, ajustes de versión y documentación.
- Convención: `release/<MAJOR.MINOR.PATCH>`, por ejemplo `release/1.0.0`
- Se fusionan a `main` (con tag `vX.Y.Z`) y de vuelta a `develop`.
#### Hotfix branches
 
- Se crean desde `main` para corregir errores críticos detectados en producción.
- Convención: `hotfix/<MAJOR.MINOR.PATCH>` con el siguiente PATCH, por ejemplo `hotfix/1.0.1`
- Se fusionan a `main` (con nuevo tag) y a `develop`.
### Reglas de colaboración
 
- No se hace push directo a `main` ni a `develop`; todo cambio entra por Pull Request con al menos una revisión de otro integrante.
- Las ramas de feature se actualizan desde `develop` antes de abrir el PR para minimizar conflictos.
## Semantic Versioning 2.0.0
 
Los releases siguen el formato `MAJOR.MINOR.PATCH`:
 
- **MAJOR**: cambios incompatibles con versiones anteriores (por ejemplo, cambios que rompen la API).
- **MINOR**: nueva funcionalidad compatible hacia atrás.
- **PATCH**: corrección de errores compatible hacia atrás.
Los tags se nombran `v1.0.0`, `v1.1.0`, `v1.1.1`. Las versiones previas a producción pueden usar sufijos como `v0.1.0` o `v1.0.0-beta.1`.
 
## Conventional Commits
 
Los mensajes siguen la estructura:
 
```
<type>(<scope opcional>): <descripción en inglés, en imperativo>
 
<cuerpo opcional>
 
<footer opcional>
```
 
| Type | Uso |
|---|---|
| `feat` | Nueva funcionalidad |
| `fix` | Corrección de un error |
| `docs` | Cambios en documentación |
| `style` | Formato, sin cambio de lógica |
| `refactor` | Reestructuración de código sin cambiar comportamiento |
| `test` | Creación o modificación de pruebas |
| `chore` | Tareas de mantenimiento, configuración, dependencias |
| `ci` | Cambios en integración/despliegue continuo |
 
Ejemplos:
 
- `feat(medication): add daily reminder scheduling`
- `fix(auth): correct token expiration handling`
- `test(medication): add acceptance scenarios for dose confirmation`
- `feat(api)!: rename patient endpoint` (el `!` indica breaking change)
## Evidencia de commits
 
| Repository | Branch | Commit Id | Commit Message | Commit Message Body | Committed on (Date) |
|---|---|---|---|---|---|
| user/repositoryname | feature/... | `abc1234` | `feat: ...` | ... | dd/mm/aaaa |

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

En esta sección el equipo especifica la configuración y los pasos para desplegar o publicar cada producto digital de Tata a partir de su repositorio de código fuente. La solución comprende cuatro productos desplegables y una base de datos:

| Producto | Repositorio | Plataforma de despliegue | Rama que se despliega | URL / forma de acceso |
| --- | --- | --- | --- | --- |
| Landing Page |  | GitHub Pages | `main` |  |
| Web Services (API Gateway y módulos de los 9 Bounded Contexts) |  | Render, como Web Service con Docker | `main` |  |
| Base de datos central | — | Render PostgreSQL | — | Solo accesible desde el backend, por URL interna |
| Aplicación Android nativa (Kotlin) |  | Firebase App Distribution | `main` | Invitación por correo a los testers |
| Aplicación multiplataforma (Flutter) |  | Firebase App Distribution | `main` | Invitación por correo a los testers |

**Relación con el flujo de trabajo.** De acuerdo con el modelo GitFlow descrito en la sección 4.1.2, solo la rama `main` se despliega en producción. El trabajo diario se integra en `develop` y se prueba en local. Cuando una versión está lista, se crea la rama `release/x.y.z`, se integra en `main` y se etiqueta como `vx.y.z` siguiendo Semantic Versioning. Esa integración en `main` es la que dispara o habilita cada despliegue descrito a continuación.

**Manejo de credenciales.** Ningún repositorio contiene contraseñas, API keys ni keystores de firma. Estos valores se configuran como variables de entorno en Render o se guardan fuera del repositorio (archivos incluidos en `.gitignore`) y se comparten solo entre los integrantes del equipo.

#### Landing Page: GitHub Pages

El Landing Page es un sitio estático (HTML5, CSS3 y JavaScript), por lo que se publica directamente desde su repositorio sin un proceso de compilación.

1. Verificar que el repositorio del Landing Page sea **público** dentro de la organización `vitaHealth-UPC`, ya que GitHub Pages para organizaciones con plan gratuito solo publica repositorios públicos.
2. Verificar que `index.html` se encuentre en la raíz de la rama `main`.
3. Verificar que las rutas a estilos, scripts e imágenes sean **relativas** (`assets/css/styles.css` y no `/assets/css/styles.css`). GitHub Pages sirve el sitio bajo la subruta `/<repositorio>/`, y las rutas absolutas dejarían el sitio sin estilos.
4. En el repositorio, ir a **Settings → Pages → Build and deployment**, seleccionar **Source: Deploy from a branch**, elegir la rama `main` y la carpeta `/ (root)`, y guardar.
5. GitHub ejecuta automáticamente el workflow `pages-build-deployment`, cuyo avance puede verse en la pestaña **Actions**. Al terminar, el sitio queda disponible en `https://vitahealth-upc.github.io/<repositorio>/`.
6. Cada nueva integración en `main` vuelve a publicar el sitio automáticamente. Después de cada publicación se verifica en el navegador que carguen las secciones del Landing Page y que las meta tags de la sección 3.1.2.3 aparezcan en el código fuente de la página.

#### Web Services: Render y PostgreSQL

Según la sección 2.5.3.3, el API Gateway y los módulos de los nueve Bounded Contexts se ejecutan juntos en un único desplegable. Por ello el backend se publica como **un solo Web Service** en Render, conectado a **una instancia de PostgreSQL** administrada por la misma plataforma. Render no ofrece un entorno nativo para Java, así que el despliegue se realiza mediante una imagen Docker construida desde el repositorio.

**Configuración requerida en el repositorio del backend:**

a) Un `Dockerfile` en la raíz, que compila el proyecto con Maven y ejecuta el `.jar` resultante:

```dockerfile
# Etapa 1: compilación
FROM maven:3.9-eclipse-temurin-21 AS build
WORKDIR /app
COPY pom.xml .
COPY src ./src
RUN mvn -q clean package -DskipTests

# Etapa 2: ejecución
FROM eclipse-temurin:21-jre
WORKDIR /app
COPY --from=build /app/target/*.jar app.jar
EXPOSE 8080
ENTRYPOINT ["java", "-jar", "app.jar"]
```

El proyecto se gestiona con Maven, por lo que la compilación usa el `pom.xml` de la raíz. Las imágenes base (`eclipse-temurin-21`) deben coincidir con la versión de Java elegida al crear el proyecto en Spring Initializr; si se elige Java 17, se reemplaza `21` por `17` en ambas etapas.

b) Un archivo `application-prod.properties` que toma la configuración de variables de entorno, en lugar de valores escritos en el código:

```properties
server.port=${PORT:8080}
spring.datasource.url=${DATABASE_URL}
spring.datasource.username=${DATABASE_USERNAME}
spring.datasource.password=${DATABASE_PASSWORD}
spring.jpa.hibernate.ddl-auto=update
management.endpoints.web.exposure.include=health
```

c) Las dependencias `springdoc-openapi-starter-webmvc-ui`, que publica la documentación Swagger/OpenAPI indicada en la sección 4.1.1, y `spring-boot-starter-actuator`, que expone `/actuator/health` para que Render verifique el estado del servicio.

**Pasos en Render:**

1. Crear la cuenta del equipo en Render iniciando sesión con GitHub, y autorizar el acceso de Render al repositorio del backend dentro de la organización `vitaHealth-UPC`.
2. Crear la base de datos desde **New → PostgreSQL**, con el nombre `tata-db`. Elegir la región y anotarla, porque el Web Service debe crearse en la misma región.
3. Una vez creada la base de datos, copiar desde su panel el host, el nombre de la base, el usuario y la contraseña. Render entrega la URL con el formato `postgresql://usuario:contraseña@host/base`, pero Spring Boot requiere el formato JDBC, por lo que `DATABASE_URL` se arma como `jdbc:postgresql://<host>:5432/<base>`. Se usa el **host interno**, ya que el backend y la base de datos están en la misma región.
4. Crear el servicio desde **New → Web Service**, seleccionando el repositorio del backend, la rama `main` y el entorno **Docker**. Render detecta el `Dockerfile` de la raíz.
5. En la sección **Environment**, registrar las variables de entorno:

| Variable | Valor |
| --- | --- |
| `SPRING_PROFILES_ACTIVE` | `prod` |
| `DATABASE_URL` | `jdbc:postgresql://<host interno>:5432/<base>` |
| `DATABASE_USERNAME` | Usuario de `tata-db` |
| `DATABASE_PASSWORD` | Contraseña de `tata-db` |
| `JWT_SECRET` | Clave de firma de tokens para la autenticación del familiar y la validación del PIN del adulto mayor |
| `FIREBASE_CREDENTIALS` | Credenciales de la cuenta de servicio de Firebase para el envío de notificaciones push mediante Firebase Cloud Messaging |
| `SPEECH_TO_TEXT_API_KEY` | API key del servicio Speech-to-Text seleccionado en el Spike 1 |
| `MAIL_USERNAME` / `MAIL_PASSWORD` | Credenciales del servicio de correo usado para la verificación de cuentas |

Las variables de los servicios externos se registran en el momento en que se integra cada servicio en el backend; mientras tanto, el Web Service funciona solo con las variables de base de datos y autenticación.

6. En **Advanced**, configurar el **Health Check Path** como `/actuator/health` y dejar **Auto-Deploy** activado, para que cada integración en `main` genere un nuevo despliegue.
7. Ejecutar el primer despliegue y revisar los logs en el panel de Render hasta ver que Spring Boot inició correctamente. La variable `PORT` la define Render y la aplicación la toma mediante `server.port=${PORT:8080}`.
8. Verificar el despliegue abriendo la documentación en `https://<servicio>.onrender.com/swagger-ui/index.html` y ejecutando desde ella una operación de prueba, por ejemplo la consulta de la próxima toma (US-20).

**Consideraciones del plan gratuito de Render:**
- El Web Service se suspende tras un periodo sin tráfico y la primera solicitud posterior puede tardar cerca de un minuto. Antes de cada sustentación y de las entrevistas de validación, el equipo abre la URL del backend para activarlo.
- La base de datos PostgreSQL gratuita tiene una duración limitada. El equipo verifica la fecha de expiración en el panel de Render y, antes de que venza, exporta los datos con `pg_dump` y los restaura en una nueva instancia (o migra a un plan de pago) para llegar al TB2 con la información intacta.

#### Aplicaciones móviles: Firebase App Distribution

Las dos aplicaciones móviles se distribuyen como archivos APK firmados mediante **Firebase App Distribution**, que es el servicio que el enunciado exige para el TB2. Se usa un único proyecto de Firebase para Tata, que también provee Firebase Cloud Messaging para las notificaciones push. Dentro de ese proyecto se registran dos aplicaciones Android con identificadores distintos, para que ambas puedan instalarse en el mismo dispositivo.

**Preparación común (una sola vez):**

1. En la consola de Firebase, crear el proyecto de Tata con la cuenta del equipo.
2. Registrar la aplicación Android nativa con el identificador `com.vitahealth.tata.android` y la aplicación Flutter con `com.vitahealth.tata.flutter`, y descargar el archivo `google-services.json` de cada una.
3. En **App Distribution**, crear el grupo de testers `vitahealth-team` con los correos de los seis integrantes, y el grupo `validation-users` para los participantes de las entrevistas de validación (sección 4.3).
4. Generar una llave de firma (*keystore*) por aplicación. El archivo `.jks` y sus contraseñas se guardan **fuera del repositorio** y se comparten solo dentro del equipo, porque cada versión nueva de una app debe firmarse con la misma llave para poder instalarse sobre la anterior.

**Aplicación Android nativa (Kotlin):**

1. Copiar `google-services.json` en la carpeta `app/`.
2. Definir la URL del backend según el tipo de compilación en `app/build.gradle.kts`: en `debug` apunta al backend local y en `release` al backend desplegado en Render.

```kotlin
android {
    buildFeatures { buildConfig = true }
    buildTypes {
        debug {
            buildConfigField("String", "API_BASE_URL", "\"http://10.0.2.2:8080/api/v1/\"")
        }
        release {
            buildConfigField("String", "API_BASE_URL", "\"https://<servicio>.onrender.com/api/v1/\"")
            signingConfig = signingConfigs.getByName("release")
        }
    }
}
```

3. Configurar `signingConfigs.release` para que lea la ruta y las contraseñas de la llave desde un archivo `keystore.properties`, incluido en `.gitignore`.
4. Actualizar `versionName` con la versión semántica de la release (por ejemplo, `1.0.0`) e incrementar `versionCode` en cada distribución.
5. Generar el APK firmado con `./gradlew assembleRelease`. El archivo se genera en `app/build/outputs/apk/release/app-release.apk`.
6. En **Firebase → App Distribution**, seleccionar la aplicación `com.vitahealth.tata.android`, subir el APK, escribir las notas de versión con las User Stories incluidas y distribuirlo a los grupos correspondientes.
7. Cada tester recibe un correo de invitación, acepta la distribución e instala el APK en su dispositivo físico, habilitando la instalación de aplicaciones de origen desconocido. Este es el dispositivo que se usa en la sustentación, como exige el enunciado.

**Aplicación multiplataforma (Flutter):**

1. Copiar `google-services.json` en `android/app/`.
2. Declarar la versión en `pubspec.yaml` con el formato `version: 1.0.0+1`, donde la parte anterior al `+` es la versión semántica y la posterior es el número de compilación, que se incrementa en cada distribución.
3. Leer la URL del backend en tiempo de compilación, para no escribirla dentro del código:

```dart
const apiBaseUrl = String.fromEnvironment(
  'API_BASE_URL',
  defaultValue: 'http://10.0.2.2:8080/api/v1',
);
```

4. Configurar la firma en `android/app/build.gradle.kts` a partir de un archivo `android/key.properties`, incluido en `.gitignore`, siguiendo la guía oficial de Flutter para compilaciones Android de release.
5. Generar el APK firmado con `flutter build apk --release --dart-define=API_BASE_URL=https://<servicio>.onrender.com/api/v1`. El archivo se genera en `build/app/outputs/flutter-apk/app-release.apk`.
6. Subir el APK en **Firebase → App Distribution** para la aplicación `com.vitahealth.tata.flutter` y distribuirlo igual que la aplicación nativa.

En el alcance actual, ambas aplicaciones se distribuyen como APK para Android, que es la plataforma de los dispositivos físicos usados en la sustentación y en las entrevistas de validación. La distribución de una compilación para iOS requiere una cuenta de Apple Developer Program y no forma parte de esta configuración.

#### Deployment Diagram

El siguiente Deployment Diagram del C4 Model, presentado inicialmente en la sección 2.5.3.3, muestra la distribución de los productos de Tata en producción. Con la configuración descrita en esta sección, los nodos del diagrama corresponden a las siguientes plataformas:

| Nodo del diagrama | Plataforma elegida |
| --- | --- |
| Hosting web estático / CDN | GitHub Pages |
| Plataforma de aplicaciones en la nube (API Gateway y módulos de los Bounded Contexts) | Render Web Service (Docker) |
| Servicio administrado de PostgreSQL | Render PostgreSQL |
| Dispositivo Android / Dispositivo móvil multiplataforma | Dispositivos físicos de los testers, con las apps instaladas desde Firebase App Distribution |
| Servicio de notificaciones | Firebase Cloud Messaging |
| Servicio Speech-to-Text | Proveedor seleccionado en el Spike 1, consumido desde Intake Execution BC |
| Servicio de correo | Proveedor de correo transaccional, consumido desde Identity & Subscription BC |

![Diagrama de Despliegue de Tata](assets/software-architecture-deployment-diagram.svg)

*Figura. Deployment Diagram de Tata en producción.*

Las evidencias de la ejecución de estos pasos en cada Sprint (creación de cuentas, configuración de recursos y capturas de los despliegues) se presentan en la sección *Software Deployment Evidence for Sprint Review* del Sprint correspondiente.


 
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
