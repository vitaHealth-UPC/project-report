# Capítulo IV: Product Implementation & Validation

# 4. Product Implementation & Validation

## 4.1. Software Configuration Management

### 4.1.1. Software Development Environment Configuration

| Actividad | Producto | Propósito | Ruta de referencia / descarga |
| --- | --- | --- | --- |
| Project Management / Requirements Management | Trello | Gestión del Product Backlog, los Sprints y las User Stories, Technical Stories y Spike Stories | https://trello.com/b/wuHmMypU/apps-moviles |
| Product UX/UI Design | Figma | Elaboración de Wireframes, Mock-ups y Prototypes del Landing Page y las aplicaciones móviles | https://www.figma.com/ |
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
| Software Deployment | Render / Railway (Docker) | Despliegue del backend como contenedor Docker | https://render.com / https://railway.com |
| Software Deployment | Neon / Railway PostgreSQL | Base de datos PostgreSQL administrada | https://neon.tech |
| Software Deployment | GitHub Pages | Despliegue del Landing Page | https://pages.github.com |
| Software Documentation | Swagger / OpenAPI | Documentación de los endpoints del backend | https://swagger.io |

### 4.1.2. Source Code Management

Para el control de versiones de todos los productos de VitaHealth (Tata) se utiliza Git gestionado desde GitHub, aplicando GitFlow como workflow, Semantic Versioning para los releases y Conventional Commits para los mensajes de commit.
 
## Repositorios
 
| Producto | Repositorio | Contenido |
|---|---|---|
| Landing Page | https://github.com/vitaHealth-UPC/landing-page | Sitio estático (HTML5, CSS3, JavaScript), publicado en GitHub Pages |
| Web Services | https://github.com/vitaHealth-UPC/web-services | Proyecto del backend (RESTful API), pruebas unitarias y pruebas de integración/aceptación (archivos `.feature`) |
| Mobile Application | https://github.com/vitaHealth-UPC/mobile-android | App Tata en Kotlin (Android) |
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
- **Textos visibles fuera del código, en dos idiomas.** Todo texto que ve el adulto mayor o el familiar se escribe en inglés como idioma por defecto y se traduce a español latinoamericano (es-419). Los textos se ubican en archivos de recursos y nunca como literales dentro de la lógica: `res/values/strings.xml` y `res/values-b+es+419/strings.xml` en Android, `i18n/messages.properties` y `messages_es_419.properties` en el backend, y el diccionario de `js/i18n.js` con atributos `data-i18n` en el Landing Page. Esto permite revisar el tono de comunicación definido en la sección 3.1.1.1 sin modificar el código.
- **Comentarios en inglés** y solo cuando explican el *porqué* de una decisión (por ejemplo, por qué una toma confirmada dos veces no genera un segundo registro). No se deja código comentado en los commits.
- **Formato de archivo.** Codificación UTF-8, fin de línea LF y un salto de línea al final de cada archivo. La indentación es de 2 espacios para HTML, CSS, JavaScript, Java, Gherkin y YAML, y de 4 espacios para Kotlin. El repositorio `mobile-android` incluye un archivo `.editorconfig` en la raíz; `landing-page` y `web-services` lo incorporarán en el Sprint 2.
- **Tokens de diseño compartidos.** Los colores y espaciados de *Tata Design Foundations* (sección 3.1.1.1) se definen una sola vez por producto y los componentes los referencian por nombre, para que un cambio de marca se haga en un solo lugar: en el Landing Page como variables CSS en `:root` de `css/styles.css`, y en Android en los objetos del módulo `:shared` (`TataColors.kt` y `TataSpacing.kt`).

| Token | Landing Page (CSS) | Android (Kotlin, módulo `:shared`) |
| --- | --- | --- |
| Azul marino principal | `--tata-navy`, `--color-primary` | `TataNavy` |
| Morado de acento | `--tata-purple` | `TataPurple` |
| Texto principal | `--color-text` | `TataText` |
| Texto secundario | `--color-muted` | `TataMuted` |
| Bordes | `--color-border` | `TataBorder` |
| Fondo crema (tarjetas de estado) | — | `TataCream` |
| Espaciado base 8 | — | `TataSpacing.sm = 8.dp` |

#### HTML5 (Landing Page)

Se sigue *HTML Style Guide and Coding Conventions* y *Google HTML/CSS Style Guide*:

- Se declara `<!DOCTYPE html>` y `<html lang="en">`, porque el idioma por defecto del Landing Page es el inglés. Cuando el visitante cambia a español, `js/i18n.js` reemplaza los textos marcados con `data-i18n` y actualiza el atributo a `lang="es-419"`, para que los lectores de pantalla pronuncien el contenido correctamente. Se incluyen `<meta charset="UTF-8">`, la etiqueta `viewport` y las meta tags definidas en la sección 3.1.2.3 (title, description, keywords y author).
- Nombres de elementos y atributos en minúsculas, valores de atributos entre comillas dobles y todos los elementos cerrados correctamente.
- Se usan elementos semánticos (`header`, `nav`, `main`, `section`, `footer`) en lugar de `div` genéricos, y un único `h1` por página.
- Toda imagen informativa tiene un atributo `alt` descriptivo (por ejemplo, `alt="Tata"` en el logotipo), y las imágenes decorativas usan `alt=""` para que los lectores de pantalla las omitan. Las secciones sin encabezado visible se describen con `aria-label` (por ejemplo, `aria-label="Tata benefits"`).
- No se usan estilos ni scripts en línea (`style=""`, `onclick=""`); se enlazan desde archivos externos.
- Los `id` y las clases se escriben en inglés y en *kebab-case*, y se nombran por su función, no por su apariencia: `plans-section`, `plan-card`, `contact-form`, en lugar de `purple-box` o `seccion2`.
- Estructura del repositorio: `index.html` en la raíz, los estilos en `css/` (`styles.css` y `responsive.css`), los scripts en `js/` (`main.js` e `i18n.js`) y los recursos gráficos en `assets/` (`icons/`, `images/` y `logo/`). Los nombres de archivo van en minúsculas y en *kebab-case*.

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

Se toma como referencia *Google Java Style Guide*: una clase de nivel superior por archivo, llaves obligatorias incluso en bloques de una línea y nombres descriptivos en inglés. El formato se aplica con el formateador de IntelliJ IDEA. En el Sprint 1 una parte de los archivos quedó con indentación de 4 espacios (valor por defecto del IDE) y otra con los 2 espacios de la guía; el equipo normalizará el formato a 2 espacios en el Sprint 2 con el archivo `.editorconfig` mencionado en las convenciones generales.

**Nomenclatura:**

| Elemento | Convención | Ejemplo en Tata |
| --- | --- | --- |
| Paquete | minúsculas, sin guiones bajos, nombre completo del Bounded Context | `com.tata.intakeexecution.domain.model.aggregates` |
| Clase / Record / Enum | *UpperCamelCase*, sustantivo | `Intake`, `MedicationSnapshot`, `IntakeStatus` |
| Método | *lowerCamelCase*, verbo | `confirm()`, `registerReplenishment()`, `consumeUnit()` |
| Variable / atributo | *lowerCamelCase* | `scheduledAt`, `remainingStock` |
| Constante | *UPPER_SNAKE_CASE* | `MAX_PERIOD_DAYS`, `MINIMUM_ISSUES_FOR_PATTERN` |
| Valor de enum | *UPPER_SNAKE_CASE* | `PENDING`, `CONFIRMED`, `LATE`, `OMITTED`, `TOUCH`, `VOICE` |

**Organización de paquetes por Bounded Context.** El backend es un único desplegable (sección 2.5.3), pero cada Bounded Context tiene su propio paquete raíz bajo `com.tata` y, dentro de él, las cuatro capas definidas en la sección 2.6:

| Bounded Context | Paquete raíz |
| --- | --- |
| Identity & Subscription | `com.tata.identitysubscription` |
| Care Link | `com.tata.carelink` |
| Treatment Management | `com.tata.treatmentmanagement` |
| Intake Execution | `com.tata.intakeexecution` |
| Omission & Escalation | `com.tata.omissionescalation` |
| Adherence Analytics | `com.tata.adherenceanalytics` |
| Family Monitoring | `com.tata.familymonitoring` |
| Accessibility & Preferences | `com.tata.accessibilitypreferences` |
| Inventory & Replenishment | `com.tata.inventoryreplenishment` |
| Elementos compartidos | `com.tata.shared` |

Por ejemplo, el Bounded Context Intake Execution se organiza así en el repositorio:

```text
com.tata.intakeexecution
├── domain
│   ├── model
│   │   ├── aggregates        -> Intake
│   │   ├── valueobjects      -> MedicationSnapshot, IntakeStatus, ConfirmationChannel
│   │   ├── commands          -> ConfirmIntakeCommand, ConfirmIntakeByVoiceCommand, GenerateIntakesCommand
│   │   └── events            -> IntakeConfirmed, IntakeUnconfirmed
│   ├── services              -> VoiceConfirmationValidationService
│   └── repositories          -> IntakeRepository
├── application
│   ├── commandservices       -> ConfirmIntakeCommandService, ...          (contratos)
│   ├── queryservices         -> GetNextIntakeQueryService, ...            (contratos)
│   ├── models                -> IntakeResult, VoiceConfirmationResult
│   ├── acl                   -> IntakeContextFacadeImpl
│   └── internal
│       ├── commandservices   -> ConfirmIntakeCommandHandler, ...          (implementaciones)
│       ├── queryservices     -> GetNextIntakeQueryHandler, ...            (implementaciones)
│       └── outboundservices  -> IVoiceRecognitionPort, IVoicePreferencePort
├── interfaces
│   ├── rest                  -> IntakesController, IntakeExceptionHandler
│   │   ├── resources         -> IntakeResource, ConfirmIntakeResource, ...
│   │   └── transform         -> IntakeResourceAssembler
│   ├── acl                   -> IntakeContextFacade
│   └── events                -> TreatmentScheduleChangedEventListener, ...
└── infrastructure
    ├── persistence/jpa
    │   ├── entities          -> IntakePersistenceEntity
    │   ├── repositories      -> IntakeJpaRepository
    │   └── adapters          -> IntakeRepositoryImpl
    ├── scheduling            -> IntakeUnconfirmedScheduler
    └── external              -> VoiceRecognitionAdapter, HttpSpeechToTextProviderClient
```

**Sufijos por tipo de elemento.** Se mantienen los nombres definidos en el Tactical-Level Domain-Driven Design:

| Tipo | Regla | Ejemplo |
| --- | --- | --- |
| Aggregate / Entity | Sustantivo del dominio, sin sufijo | `Intake`, `Treatment`, `Inventory`, `Batch` |
| Value Object | Sustantivo, sin sufijo; se implementa como `record` cuando es inmutable | `MedicationSnapshot`, `StockLevel` |
| Domain Event | Verbo en pasado, sin sufijo `Event` | `IntakeConfirmed`, `LowStockDetected`, `ReplenishmentRegistered` |
| Command / Query | Verbo en imperativo + sufijo | `ConfirmIntakeCommand`, `GetRemainingStockQuery` |
| Contrato de servicio de aplicación | Nombre + `CommandService` o `QueryService` | `ConfirmIntakeCommandService`, `InventoryQueryService` |
| Implementación del servicio | Nombre + `CommandHandler`/`QueryHandler`, o contrato + `Impl` | `ConfirmIntakeCommandHandler`, `InventoryCommandServiceImpl` |
| Repositorio (contrato de dominio) | Agregado + `Repository`, sin prefijo | `IntakeRepository`, `InventoryRepository` |
| Repositorio (implementación) | Contrato + `Impl`, en `infrastructure/persistence/jpa/adapters` | `IntakeRepositoryImpl`, `InventoryRepositoryImpl` |
| Repositorio de Spring Data / entidad JPA | Agregado + `JpaRepository` / `PersistenceEntity` | `IntakeJpaRepository`, `BatchPersistenceEntity` |
| Puerto de salida (otro BC o servicio externo) | Prefijo `I` + nombre + `Port` | `IVoiceRecognitionPort`, `IMedicationLookupPort` |
| Fachada ACL | Contexto + `ContextFacade` / `ContextFacadeImpl` | `TreatmentContextFacade`, `IntakeContextFacadeImpl` |
| Resource (DTO REST) / Assembler | Sustantivo + `Resource` / `ResourceAssembler` | `InventoryResource`, `InventoryResourceAssembler` |
| Controller | Recurso en plural + `Controller` | `IntakesController`, `TreatmentsController`, `InventoryController` |
| Listener / Consumer / Scheduler | Responsabilidad + sufijo | `IntakeConfirmedEventListener`, `IntakeUnconfirmedScheduler` |

El prefijo `I` se reserva para los **puertos de salida** de la capa Application, que representan dependencias hacia otro Bounded Context o hacia un servicio externo. Los repositorios de dominio no lo llevan: el contrato se llama como el agregado (`InventoryRepository`) y su implementación en Infrastructure añade el sufijo `Impl`. Algunos repositorios creados al inicio del Sprint 1 (`IOmissionCaseRepository`, `IFamilyMonitorRepository`, `IUserPreferencesRepository`) todavía conservan el prefijo y se renombrarán en el Sprint 2.

**Convenciones de Spring Boot** (según *Spring Boot Features*):

- Inyección de dependencias por constructor, con atributos `private final`; no se usa `@Autowired` sobre atributos.
- Configuración externa en `application.properties` con perfiles `dev` y `prod` (`application-dev.properties` y `application-prod.properties`). El perfil activo se elige con `SPRING_PROFILES_ACTIVE`, que por defecto es `dev`. Las claves propias de Tata usan el prefijo `tata.` en *kebab-case*, por ejemplo `tata.cors.allowed-origins`.
- Credenciales y cadenas de conexión se leen de variables de entorno y nunca se versionan en el repositorio.
- Los mensajes de error visibles se resuelven con `MessageSource` desde `src/main/resources/i18n/messages.properties` (inglés) y `messages_es_419.properties` (español latinoamericano).

**Convenciones de la API REST:**

- Todas las rutas comienzan con `/api/v1`.
- Los recursos se nombran con sustantivos en plural y en *kebab-case*: `/api/v1/treatments`, `/api/v1/medications`, `/api/v1/care-links`, `/api/v1/inventories`.
- Las acciones que no son CRUD se modelan como subrecursos: la reposición de un inventario (US-43, TS-12) es `POST /api/v1/inventories/{medicationId}/replenishments`.
- Las propiedades JSON se escriben en *lowerCamelCase* (`remainingStock`, `replenishmentThreshold`), que es el comportamiento por defecto de Jackson.
- Los errores se devuelven con un cuerpo uniforme `{ "code": "...", "message": "..." }`. El `code` es estable y en *UPPER_SNAKE_CASE* (`INVENTORY_NOT_FOUND`, `INVENTORY_ALREADY_EXISTS`, `CONCURRENT_UPDATE`) para que las aplicaciones móviles lo traduzcan sin depender del texto.
- Los códigos HTTP se usan según su significado: `200` y `201` para éxito, `400` para validación, `401` y `403` para autenticación o permisos, `404` para recursos inexistentes y `409` para conflictos de estado.

**Pruebas.** Las clases de prueba se nombran como la clase probada más `Test` (`StockCoveragePolicyTest`, `InventoryRepositoryImplTest`). Las pruebas del backend usan una base H2 en memoria, de modo que se ejecutan sin PostgreSQL con `mvn test`.

#### Kotlin (Aplicación Android nativa)

Se siguen *Kotlin Coding Conventions* y *Android Kotlin Style Guide*, usando el esquema de formato *Kotlin style guide* de Android Studio: indentación de 4 espacios. La interfaz se construye con Jetpack Compose.

- **Un módulo Gradle por Bounded Context**: `:identity`, `:carelink`, `:treatment`, `:intake`, `:omission`, `:monitoring`, `:analytics`, `:inventory` y `:preferences`. El módulo `:shared` contiene el tema, los componentes de diseño y la sesión, y el módulo `:app` contiene la navegación y la inyección de dependencias (`AppContainer`, `TataNavHost`).
- Paquete base `com.vitahealth.tata.<contexto>` y, dentro de cada módulo, las capas `domain`, `application` (`commands`, `queries`, `handlers`, `readmodels`), `infrastructure` (`remote`, `local`) y `presentation`. Por ejemplo, `com.vitahealth.tata.inventory.presentation.inventory`.
- Clases en *UpperCamelCase*; funciones y propiedades en *lowerCamelCase*; constantes (`const val`) en *UPPER_SNAKE_CASE*. El estado interno mutable de un ViewModel usa el prefijo `_` y se expone como inmutable: `private val _uiState` y `val uiState: StateFlow<...>`.
- Sufijos por responsabilidad: `InventoryViewModel`, `InventoryUiState` (interfaz *sealed* con un estado por variante, por ejemplo `Loading`, `NotInitialized`, `Ready` y `Error`), `InventoryScreen` (composable sin estado) e `InventoryRoute` (composable que conecta el ViewModel), `RegisterReplenishmentCommand`, `RegisterReplenishmentCommandHandler`, `InventoryStockReadModel`, `InventoryApiService` (Retrofit) y `RemoteInventoryRepository`.
- Un *frame* de Figma no equivale a una pantalla: los estados de una misma vista (stock bajo, stock disponible, cantidad inválida) se representan como variantes de su `UiState`, y cada una tiene su `@Preview`.
- Los errores del backend se traducen por su `code` estable a recursos de texto; el texto nunca se toma directamente del `message` del backend.
- Recursos en *snake_case* con el prefijo del módulo o de la pantalla: `inventory_status_low`, `treatment_open_inventory`, `agenda_bell.png`.
- Los textos visibles están en `res/values/strings.xml` (inglés, por defecto) y `res/values-b+es+419/strings.xml` (español latinoamericano). Las vistas previas en español se declaran con `@Preview(locale = "b+es+419")`.
- Los tamaños de texto se definen en `sp` y las dimensiones en `dp`, respetando la escala de la sección 3.1.1.1.

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
- Los enums se almacenan como texto en mayúsculas (`PENDING`, `TOUCH`), con los mismos valores que en Java.
- Las referencias a entidades de otro Bounded Context se guardan como identificadores UUID en texto (`varchar(36)`), sin clave foránea, porque cada contexto es dueño de sus tablas. Por ejemplo, `inventories.medication_id` referencia a un medicamento de Treatment Management.
- En las entidades JPA los atributos se escriben en *lowerCamelCase* (`scheduledAt`). La estrategia de nombres del proyecto (`SnakeCaseWithPluralizedTablePhysicalNamingStrategy`, en `com.tata.shared`) los convierte automáticamente a *snake_case* y pluraliza el nombre de la tabla, por lo que no es necesario repetir `@Column(name = ...)` ni `@Table(name = ...)` salvo excepciones.


### 4.1.4. Software Deployment Configuration

En esta sección el equipo especifica la configuración y los pasos para desplegar o publicar cada producto digital de Tata a partir de su repositorio de código fuente. La solución comprende cuatro productos desplegables y una base de datos:

| Producto | Repositorio | Plataforma de despliegue | Rama que se despliega | URL / forma de acceso |
| --- | --- | --- | --- | --- |
| Landing Page | [landing-page](https://github.com/vitaHealth-UPC/landing-page) | GitHub Pages | `main` | https://vitahealth-upc.github.io/landing-page/ |
| Web Services (API Gateway y módulos de los 9 Bounded Contexts) | [web-services](https://github.com/vitaHealth-UPC/web-services) | Render o Railway, como servicio con Docker | `main` | `https://<servicio>/swagger-ui.html` |
| Base de datos central | — | PostgreSQL administrado (Neon o Railway) | — | Solo accesible desde el backend, mediante `DATABASE_URL` |
| Aplicación Android nativa (Kotlin) | [mobile-android](https://github.com/vitaHealth-UPC/mobile-android) | Firebase App Distribution | `main` | Invitación por correo a los testers |
| Aplicación multiplataforma (Flutter) |  | Firebase App Distribution | `main` | Invitación por correo a los testers |

**Relación con el flujo de trabajo.** De acuerdo con el modelo GitFlow descrito en la sección 4.1.2, solo la rama `main` se despliega en producción. El trabajo diario se integra en `develop` y se prueba en local. Cuando una versión está lista, se crea la rama `release/x.y.z`, se integra en `main` y se etiqueta como `vx.y.z` siguiendo Semantic Versioning. Esa integración en `main` es la que dispara o habilita cada despliegue descrito a continuación.

**Manejo de credenciales.** Ningún repositorio contiene contraseñas, API keys ni keystores de firma. Estos valores se configuran como variables de entorno en la plataforma de despliegue o se guardan fuera del repositorio (archivos incluidos en `.gitignore`) y se comparten solo entre los integrantes del equipo.

#### Landing Page: GitHub Pages

El Landing Page es un sitio estático (HTML5, CSS3 y JavaScript), por lo que se publica directamente desde su repositorio sin un proceso de compilación.

1. Verificar que el repositorio del Landing Page sea **público** dentro de la organización `vitaHealth-UPC`, ya que GitHub Pages para organizaciones con plan gratuito solo publica repositorios públicos.
2. Verificar que `index.html` se encuentre en la raíz de la rama `main`.
3. Verificar que las rutas a estilos, scripts e imágenes sean **relativas** (`assets/css/styles.css` y no `/assets/css/styles.css`). GitHub Pages sirve el sitio bajo la subruta `/<repositorio>/`, y las rutas absolutas dejarían el sitio sin estilos.
4. En el repositorio, ir a **Settings → Pages → Build and deployment**, seleccionar **Source: Deploy from a branch**, elegir la rama `main` y la carpeta `/ (root)`, y guardar.
5. GitHub ejecuta automáticamente el workflow `pages-build-deployment`, cuyo avance puede verse en la pestaña **Actions**. Al terminar, el sitio queda disponible en `https://vitahealth-upc.github.io/<repositorio>/`.
6. Cada nueva integración en `main` vuelve a publicar el sitio automáticamente. Después de cada publicación se verifica en el navegador que carguen las secciones del Landing Page y que las meta tags de la sección 3.1.2.3 aparezcan en el código fuente de la página.

#### Web Services: Docker en Render o Railway, y PostgreSQL administrado

Según la sección 2.5.3.3, el API Gateway y los módulos de los nueve Bounded Contexts se ejecutan juntos en un único desplegable. Por ello el backend se publica como **un solo servicio web** a partir de una imagen Docker construida desde el repositorio, conectado a **una instancia de PostgreSQL administrada**. El repositorio deja preparadas dos plataformas que construyen la misma imagen: **Render** (Web Service con entorno Docker) y **Railway** (archivo `railway.toml`). La base de datos se aloja en un servicio PostgreSQL administrado (Neon o Railway PostgreSQL), y el backend acepta directamente la URL que entregan estos servicios.

**Configuración incluida en el repositorio del backend:**

a) Un `Dockerfile` en la raíz, de dos etapas, que compila el proyecto con Maven y Java 26 y ejecuta el `.jar` resultante con el perfil `prod`:

```dockerfile
FROM maven:3.9.16-eclipse-temurin-26 AS build
WORKDIR /workspace
COPY pom.xml .
COPY src ./src
RUN mvn --batch-mode -DskipTests package

FROM eclipse-temurin:26-jre-noble
WORKDIR /app
ENV SPRING_PROFILES_ACTIVE=prod
ENV JAVA_OPTS=""
COPY --from=build /workspace/target/web-services-*.jar /app/app.jar
EXPOSE 8080
ENTRYPOINT ["sh", "-c", "java $JAVA_OPTS -jar /app/app.jar"]
```

b) Un archivo `application-prod.properties` que toma toda la configuración de variables de entorno, con valores por defecto seguros:

```properties
server.port=${PORT:8080}
spring.datasource.url=${SPRING_DATASOURCE_URL:jdbc:postgresql://${DATABASE_HOST:localhost}:${DATABASE_PORT:5432}/${DATABASE_NAME:tata}}
spring.datasource.username=${SPRING_DATASOURCE_USERNAME:${DATABASE_USER:}}
spring.datasource.password=${SPRING_DATASOURCE_PASSWORD:${DATABASE_PASSWORD:}}
spring.jpa.hibernate.ddl-auto=${DDL_AUTO:update}
tata.cors.allowed-origins=${TATA_CORS_ALLOWED_ORIGINS:*}
```

c) La clase `DatabaseUrlEnvironmentPostProcessor`, que convierte automáticamente la variable `DATABASE_URL` con formato `postgresql://usuario:contraseña@host/base?sslmode=require` (el formato que entregan Neon, Railway y Render) al formato JDBC que necesita Spring Boot, conservando `sslmode`. Así no es necesario armar la URL JDBC a mano.

d) Un endpoint de salud `GET /health` (`HealthController`), que la plataforma usa para verificar que el servicio inició, y la documentación Swagger/OpenAPI generada por `springdoc-openapi` en `/swagger-ui.html`.

e) El archivo `railway.toml`, que indica a Railway construir con el `Dockerfile`, usar `/health` como health check y reiniciar el servicio ante fallos (hasta 5 reintentos).

**Pasos de despliegue:**

1. Crear la base de datos PostgreSQL en el servicio administrado (Neon o Railway) con el nombre `tata` y copiar su cadena de conexión (`postgresql://...`).
2. En Render, iniciar sesión con GitHub, autorizar el acceso al repositorio `web-services` de la organización `vitaHealth-UPC` y crear el servicio desde **New → Web Service**, con entorno **Docker**. Render detecta el `Dockerfile` de la raíz. En Railway, el equivalente es **New Project → Deploy from GitHub repo**, que detecta el `railway.toml`.
3. Registrar las variables de entorno del servicio:

| Variable | Valor |
| --- | --- |
| `SPRING_PROFILES_ACTIVE` | `prod` (ya definida en el `Dockerfile`) |
| `DATABASE_URL` | Cadena de conexión `postgresql://...` del paso 1; se convierte a JDBC automáticamente |
| `DATABASE_HOST` / `DATABASE_PORT` / `DATABASE_NAME` / `DATABASE_USER` / `DATABASE_PASSWORD` | Alternativa a `DATABASE_URL`, con los datos de conexión por separado |
| `PORT` | La define la plataforma; la aplicación la toma con `server.port=${PORT:8080}` |
| `TATA_CORS_ALLOWED_ORIGINS` | Orígenes permitidos, separados por comas |

4. Configurar `/health` como **Health Check Path** (en Railway ya viene definido en `railway.toml`) y dejar el despliegue automático activado.
5. Ejecutar el primer despliegue y revisar los logs hasta ver que Spring Boot inició correctamente.
6. Verificar el despliegue abriendo `https://<servicio>/health` y la documentación en `https://<servicio>/swagger-ui.html`, y ejecutando desde ella una operación de prueba, por ejemplo la consulta del inventario de un medicamento (US-41).

**Consideraciones de los planes gratuitos:**
- El servicio web puede suspenderse tras un periodo sin tráfico, y la primera solicitud posterior puede tardar cerca de un minuto. Antes de cada sustentación y de las entrevistas de validación, el equipo abre `/health` para activarlo.
- Las bases de datos gratuitas tienen límites de almacenamiento o de duración. El equipo revisa esos límites en el panel del proveedor y, si es necesario, exporta los datos con `pg_dump` y los restaura en una nueva instancia para llegar al TB2 con la información intacta.

#### Aplicaciones móviles: Firebase App Distribution

Las dos aplicaciones móviles se distribuyen como archivos APK firmados mediante **Firebase App Distribution**, que es el servicio que el enunciado exige para el TB2. Se usa un único proyecto de Firebase para Tata, que también provee Firebase Cloud Messaging para las notificaciones push. Dentro de ese proyecto se registran dos aplicaciones Android con identificadores distintos, para que ambas puedan instalarse en el mismo dispositivo.

**Preparación común (una sola vez):**

1. En la consola de Firebase, crear el proyecto de Tata con la cuenta del equipo.
2. Registrar la aplicación Android nativa con el identificador `com.vitahealth.tata` y la aplicación Flutter con `com.vitahealth.tata.flutter`, y descargar el archivo `google-services.json` de cada una.
3. En **App Distribution**, crear el grupo de testers `vitahealth-team` con los correos de los seis integrantes, y el grupo `validation-users` para los participantes de las entrevistas de validación (sección 4.3).
4. Generar una llave de firma (*keystore*) por aplicación. El archivo `.jks` y sus contraseñas se guardan **fuera del repositorio** y se comparten solo dentro del equipo, porque cada versión nueva de una app debe firmarse con la misma llave para poder instalarse sobre la anterior.

**Aplicación Android nativa (Kotlin):**

1. Copiar `google-services.json` en la carpeta `app/`.
2. Definir la URL del backend. En `app/build.gradle.kts` la URL se lee de la propiedad de Gradle `TATA_API_BASE_URL` y, si no se indica, apunta al backend local desde el emulador (`http://10.0.2.2:8080/`). Para la versión distribuida se compila indicando la URL del backend desplegado, sin escribirla en el código:

```kotlin
defaultConfig {
    val apiBaseUrl = providers.gradleProperty("TATA_API_BASE_URL")
        .orElse("http://10.0.2.2:8080/").get()
    buildConfigField("String", "API_BASE_URL", "\"${apiBaseUrl}\"")
}
```

3. Configurar `signingConfigs.release` para que lea la ruta y las contraseñas de la llave desde un archivo `keystore.properties`, incluido en `.gitignore`.
4. Actualizar `versionName` con la versión semántica de la release (por ejemplo, `1.0.0`) e incrementar `versionCode` en cada distribución.
5. Generar el APK firmado con `./gradlew assembleRelease -PTATA_API_BASE_URL=https://<servicio>/`. El archivo se genera en `app/build/outputs/apk/release/app-release.apk`.
6. En **Firebase → App Distribution**, seleccionar la aplicación `com.vitahealth.tata`, subir el APK, escribir las notas de versión con las User Stories incluidas y distribuirlo a los grupos correspondientes.
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
5. Generar el APK firmado con `flutter build apk --release --dart-define=API_BASE_URL=https://<servicio>/api/v1`. El archivo se genera en `build/app/outputs/flutter-apk/app-release.apk`.
6. Subir el APK en **Firebase → App Distribution** para la aplicación `com.vitahealth.tata.flutter` y distribuirlo igual que la aplicación nativa.

En el alcance actual, ambas aplicaciones se distribuyen como APK para Android, que es la plataforma de los dispositivos físicos usados en la sustentación y en las entrevistas de validación. La distribución de una compilación para iOS requiere una cuenta de Apple Developer Program y no forma parte de esta configuración.

#### Deployment Diagram

El siguiente Deployment Diagram del C4 Model, presentado inicialmente en la sección 2.5.3.3, muestra la distribución de los productos de Tata en producción. Con la configuración descrita en esta sección, los nodos del diagrama corresponden a las siguientes plataformas:

| Nodo del diagrama | Plataforma elegida |
| --- | --- |
| Hosting web estático / CDN | GitHub Pages |
| Plataforma de aplicaciones en la nube (API Gateway y módulos de los Bounded Contexts) | Render Web Service o Railway, con la imagen Docker del backend |
| Servicio administrado de PostgreSQL | Neon o Railway PostgreSQL |
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

El Sprint Planning 1 define el alcance del primer sprint de implementación de Tata. Al ser el primer sprint del proyecto, parte de lo ya documentado en los capítulos I y II (segmentos objetivo, user stories, Product Backlog y bounded contexts) y del diseño UI/UX elaborado en Figma, que sirve de insumo directo para la implementación. El alcance corresponde a las 25 historias que el Product Backlog asigna al Sprint 1: el Landing Page (EPIC-09), el registro y la vinculación de cuentas (EPIC-01), la creación de tratamientos y la consulta de la próxima toma (EPIC-02 y EPIC-03), las Technical Stories que habilitan esos flujos en los servicios web y dos Spike Stories de investigación.

| Campo | Detalle |
| --- | --- |
| **Sprint #** | Sprint 1 |
| **Sprint Planning Background** | |
| Date | [YYYY-MM-DD] |
| Time | [HH:MM AM/PM] |
| Location | [Reunión virtual / presencial] |
| Prepared By | Diaz Yurivilca, Sofia |
| Attendees (to the meeting) | Quispe Pérez, Eder Edu / Diaz Yurivilca, Sofia / Morales Venegas, David Joel / Cabrera Novoa, Leonardo Moises / Alfaro Mallma, Joaquín Alberto / Velasquez Laquihuanaco, Eduardo David |
| **Sprint 0 Review Summary** | |
| Review | No aplica. El Sprint 1 es el primer sprint de implementación del proyecto. Como antecedente, en la entrega AV1 se completaron los capítulos I y II y el diseño del Landing Page y de las pantallas principales quedó definido en Figma. |
| Retrospective Summary | No aplica. La primera retrospectiva se documentará al cierre del Sprint 1. |
| **Sprint Goal & User Stories** | |
| Sprint 1 Goal | **Nuestro foco** está en publicar el Landing Page de Tata y construir los primeros servicios web y vistas de la aplicación Android que permiten al familiar registrarse, vincularse con el adulto mayor, configurar su tratamiento y consultar la próxima toma.<br>**Creemos que esto entrega** a los familiares de adultos mayores un primer recorrido completo, desde conocer Tata hasta dejar configurado el tratamiento, y al equipo una base técnica (APIs, agenda de tomas y autenticación) sobre la que construir los siguientes sprints.<br>**Esto se confirmará cuando** un visitante pueda recorrer el Landing Page publicado en GitHub Pages y llegar al registro o contacto, y un familiar pueda, desde la aplicación Android conectada a los servicios web, crear su cuenta, vincular al adulto mayor, registrar un medicamento con su tratamiento y ver la próxima toma.<br>**Métrica de cumplimiento:** 25 de 25 historias del Sprint 1 (81 Story Points) implementadas e integradas en `develop`. |
| Sprint 1 Velocity | 81 Story Points (asignación inicial del Product Backlog; primer sprint, sin velocidad histórica previa) |
| Sum of Story Points | 81 Story Points |

**User Stories incluidas en el Sprint 1**

| Story ID | Título | Epic | Story Points |
| --- | --- | --- | --- |
| US-05 | Recordatorio de toma de medicamento | EPIC-03 | 3 |
| US-03 | Registro de un nuevo medicamento | EPIC-02 | 5 |
| US-02 | Vinculación con la cuenta del adulto mayor | EPIC-01 | 5 |
| US-14 | Creación de un tratamiento | EPIC-02 | 3 |
| US-15 | Definición de dosis y frecuencia | EPIC-02 | 3 |
| US-16 | Configuración de horarios e instrucciones | EPIC-02 | 3 |
| US-17 | Configuración de recordatorios | EPIC-02 | 3 |
| US-20 | Consulta de la próxima toma | EPIC-03 | 2 |
| US-46 | Consulta de la propuesta de valor de Tata | EPIC-09 | 2 |
| US-47 | Consulta de funcionalidades principales | EPIC-09 | 2 |
| US-49 | Continuación hacia registro o contacto | EPIC-09 | 2 |
| US-50 | Acceso adaptable al Landing Page | EPIC-09 | 3 |
| US-48 | Comparación de planes disponibles | EPIC-09 | 2 |
| US-10 | Registro de cuenta del familiar | EPIC-01 | 3 |
| US-11 | Verificación del correo del familiar | EPIC-01 | 2 |
| US-01 | Ingreso simplificado a la aplicación | EPIC-01 | 3 |
| US-12 | Registro del perfil del adulto mayor | EPIC-01 | 3 |
| US-13 | Consentimiento para establecer el vínculo | EPIC-01 | 3 |
| TS-03 | API de medicamentos y tratamientos | EPIC-02 | 5 |
| TS-08 | Servicio de generación de agenda de tomas | EPIC-03 | 5 |
| TS-02 | API de vinculación de cuidado | EPIC-01 | 5 |
| TS-07 | API de cuenta y sesión del familiar | EPIC-01 | 5 |
| TS-01 | Servicio de autenticación mediante PIN | EPIC-01 | 3 |
| SP-01 | Investigación de reconocimiento de voz | EPIC-03 | 3 |
| SP-03 | Investigación de ejecución en segundo plano | EPIC-03 | 3 |
| **Total** | | | **81** |

#### 4.2.1.2. Aspect Leaders and Collaborators
#### 4.2.1.3. Sprint Backlog 1
#### 4.2.1.4. Development Evidence for Sprint Review

Durante el Sprint 1 el equipo trabajó en tres productos, cada uno en su propio repositorio de la organización `vitaHealth-UPC`: el Landing Page, los Web Services y la aplicación Android nativa.

El **Landing Page** se implementó como sitio estático con HTML5, CSS3 y JavaScript, siguiendo el diseño de Figma. Es responsivo, está disponible en español e inglés y se despliega en GitHub Pages mediante GitHub Actions desde `develop` y `main`.

Los **Web Services** se construyeron como un monolito modular con Java y Spring Boot, organizado en los bounded contexts definidos en el capítulo II y respaldado por PostgreSQL. Cada Technical Story se desarrolló en su propia rama (por ejemplo, `feature/ts-08-intake-schedule-generation`) y se integró a `develop` mediante Pull Request. El repositorio cuenta con pruebas automatizadas y un workflow de GitHub Actions que ejecuta `mvn test` y el empaquetado en cada PR.

La **aplicación Android** se implementó con Kotlin y Jetpack Compose en una arquitectura modular por bounded context. Dentro de ella, el bounded context de analítica de adherencia incorporó las vistas de historial de adherencia y de recomendaciones, conectadas a los endpoints `summary` e `insight` de los Web Services, con una barra de navegación inferior compartida. Estas historias (US-08, US-09, US-32, US-33, US-34 y TS-10) están asignadas al Sprint 3 en el Product Backlog y se adelantaron durante el Sprint 1.

El trabajo siguió GitFlow, tal como se describe en la sección 4.1.2. La siguiente tabla lista los commits integrados a `develop` en cada repositorio, con la rama de feature de la que proceden.

| Repository | Branch | Commit Id | Commit Message | Commit Message Body | Committed on (Date) |
| --- | --- | --- | --- | --- | --- |
| `vitaHealth-UPC/landing-page` | `develop` | `728b07f` | `chore: initialize landing page scaffold` | — | 02/10/2026 |
| `vitaHealth-UPC/landing-page` | `develop` | `e7eebc1` | `feat: add semantic landing page structure` | — | 02/10/2026 |
| `vitaHealth-UPC/landing-page` | `develop` | `a7bb651` | `style: add landing page design foundation` | — | 02/10/2026 |
| `vitaHealth-UPC/landing-page` | `develop` | `6857a2a` | `style: add responsive breakpoints` | — | 02/10/2026 |
| `vitaHealth-UPC/landing-page` | `develop` | `c42be5d` | `feat: add en_US and es_419 internationalization foundation` | — | 02/10/2026 |
| `vitaHealth-UPC/landing-page` | `develop` | `aacf8cf` | `feat: add landing page bootstrap script` | — | 02/10/2026 |
| `vitaHealth-UPC/landing-page` | `develop` | `1bcdaad` | `chore: add gitignore` | — | 02/10/2026 |
| `vitaHealth-UPC/landing-page` | `develop` | `3d1cecf` | `chore: add image assets directory` | — | 02/10/2026 |
| `vitaHealth-UPC/landing-page` | `develop` | `3049f16` | `chore: add icon assets directory` | — | 02/10/2026 |
| `vitaHealth-UPC/landing-page` | `develop` | `054545a` | `chore: add logo assets directory` | — | 02/10/2026 |
| `vitaHealth-UPC/landing-page` | `develop` | `01ef128` | `ci: add GitHub Pages preview from develop` | — | 02/10/2026 |
| `vitaHealth-UPC/landing-page` | `feature/header-hero` | `53cd222` | `feat: add Figma assets for header and hero` | — | 02/10/2026 |
| `vitaHealth-UPC/landing-page` | `feature/header-hero` | `e8c8d29` | `feat: implement Figma header and hero markup` | — | 02/10/2026 |
| `vitaHealth-UPC/landing-page` | `feature/header-hero` | `78c2c11` | `style: match Figma header and hero` | — | 02/10/2026 |
| `vitaHealth-UPC/landing-page` | `feature/header-hero` | `855e614` | `style: add responsive behavior for Figma header and hero` | — | 02/10/2026 |
| `vitaHealth-UPC/landing-page` | `feature/header-hero` | `7dda14a` | `fix: preserve Figma hero title emphasis` | — | 02/10/2026 |
| `vitaHealth-UPC/landing-page` | `feature/header-hero` | `ccfd959` | `feat: localize Figma header and hero` | — | 02/10/2026 |
| `vitaHealth-UPC/landing-page` | `develop` | `c51279d` | `feat: implement Figma header and hero` | * feat: add Figma assets for header and hero<br>* feat: implement Figma header and hero markup<br>* style: match Figma header and hero<br>* style: add responsive behavior for Figma header and hero<br>* fix: preserve Figma hero title emphasis<br>* feat: localize Figma header and hero | 02/10/2026 |
| `vitaHealth-UPC/landing-page` | `feature/value-features` | `db84c10` | `feat: add Figma assets for value strip and features` | — | 02/10/2026 |
| `vitaHealth-UPC/landing-page` | `feature/value-features` | `3e1a18d` | `feat: implement value strip and features markup` | — | 02/10/2026 |
| `vitaHealth-UPC/landing-page` | `feature/value-features` | `4029b07` | `style: match Figma value strip and features` | — | 02/10/2026 |
| `vitaHealth-UPC/landing-page` | `feature/value-features` | `ca0e3da` | `style: add responsive behavior for value strip and features` | — | 02/10/2026 |
| `vitaHealth-UPC/landing-page` | `feature/value-features` | `7af93c7` | `feat: localize value strip and features` | — | 02/10/2026 |
| `vitaHealth-UPC/landing-page` | `develop` | `a15c213` | `feat: implement value strip and features` | * feat: add Figma assets for value strip and features<br>* feat: implement value strip and features markup<br>* style: match Figma value strip and features<br>* style: add responsive behavior for value strip and features<br>* feat: localize value strip and features | 02/10/2026 |
| `vitaHealth-UPC/landing-page` | `feature/app-showcase-how-it-works` | `db06f08` | `feat: add Figma assets for app showcase and steps` | — | 02/10/2026 |
| `vitaHealth-UPC/landing-page` | `feature/app-showcase-how-it-works` | `af4e8a9` | `feat: implement app showcase and how-it-works markup` | — | 02/10/2026 |
| `vitaHealth-UPC/landing-page` | `feature/app-showcase-how-it-works` | `03bd895` | `style: match Figma app showcase and how-it-works` | — | 02/10/2026 |
| `vitaHealth-UPC/landing-page` | `feature/app-showcase-how-it-works` | `8fdc873` | `style: add responsive app showcase and steps` | — | 02/10/2026 |
| `vitaHealth-UPC/landing-page` | `feature/app-showcase-how-it-works` | `7c182e3` | `feat: localize app showcase and how-it-works` | — | 02/10/2026 |
| `vitaHealth-UPC/landing-page` | `develop` | `02a28fa` | `feat: implement app showcase and how it works` | * feat: add Figma assets for app showcase and steps<br>* feat: implement app showcase and how-it-works markup<br>* style: match Figma app showcase and how-it-works<br>* style: add responsive app showcase and steps<br>* feat: localize app showcase and how-it-works | 02/10/2026 |
| `vitaHealth-UPC/landing-page` | `feature/testimonial-about` | `d5c79fb` | `feat: add Figma assets for testimonial and about` | — | 02/10/2026 |
| `vitaHealth-UPC/landing-page` | `feature/testimonial-about` | `190a47f` | `feat: implement testimonial and about markup` | — | 02/10/2026 |
| `vitaHealth-UPC/landing-page` | `feature/testimonial-about` | `ece75a4` | `style: match Figma testimonial and about sections` | — | 02/10/2026 |
| `vitaHealth-UPC/landing-page` | `feature/testimonial-about` | `af55589` | `style: add responsive testimonial and about sections` | — | 02/10/2026 |
| `vitaHealth-UPC/landing-page` | `feature/testimonial-about` | `c06f101` | `style: load DM Serif Display for testimonial` | — | 02/10/2026 |
| `vitaHealth-UPC/landing-page` | `feature/testimonial-about` | `7c91871` | `feat: localize testimonial and about sections` | — | 02/10/2026 |
| `vitaHealth-UPC/landing-page` | `develop` | `933539c` | `feat: implement testimonial and about` | * feat: add Figma assets for testimonial and about<br>* feat: implement testimonial and about markup<br>* style: match Figma testimonial and about sections<br>* style: add responsive testimonial and about sections<br>* style: load DM Serif Display for testimonial<br>* feat: localize testimonial and about sections | 02/10/2026 |
| `vitaHealth-UPC/landing-page` | `feature/pricing-support` | `6d3b12c` | `feat: add Figma assets for pricing and support` | — | 02/10/2026 |
| `vitaHealth-UPC/landing-page` | `feature/pricing-support` | `d906991` | `feat: implement pricing and support markup` | — | 02/10/2026 |
| `vitaHealth-UPC/landing-page` | `feature/pricing-support` | `27d15a1` | `style: match Figma pricing and support` | — | 02/10/2026 |
| `vitaHealth-UPC/landing-page` | `feature/pricing-support` | `25067ec` | `style: add responsive pricing and support` | — | 02/10/2026 |
| `vitaHealth-UPC/landing-page` | `feature/pricing-support` | `f1c6d8e` | `feat: localize pricing and support` | — | 02/10/2026 |
| `vitaHealth-UPC/landing-page` | `develop` | `82d1449` | `feat: implement pricing and support` | * feat: add Figma assets for pricing and support<br>* feat: implement pricing and support markup<br>* style: match Figma pricing and support<br>* style: add responsive pricing and support<br>* feat: localize pricing and support | 02/10/2026 |
| `vitaHealth-UPC/landing-page` | `feature/cta-footer` | `f3fda48` | `feat: add Figma assets for CTA and footer` | — | 02/10/2026 |
| `vitaHealth-UPC/landing-page` | `develop` | `b43b5b3` | `feat: implement pricing and support` | * feat: add Figma assets for pricing and support<br>* feat: implement pricing and support markup<br>* style: match Figma pricing and support<br>* style: add responsive pricing and support<br>* feat: localize pricing and support | 02/10/2026 |
| `vitaHealth-UPC/landing-page` | `develop` | `8121db2` | `feat: align English and mobile landing variants with Figma` | * feat: add English and mobile Figma assets<br>* feat: add locale-aware app mockups and mobile structure<br>* style: add CTA, footer and mobile fidelity helpers<br>* style: match 393px Figma mobile layouts<br>* feat: wire mobile-specific localized copy<br>* feat: refine mobile header and footer content<br>* feat: match English, Spanish and mobile-specific Figma copy<br>* feat: add mobile app showcase pointers<br>* feat: add mobile app showcase pointers and copy hook<br>* style: hide mobile-only assets outside mobile layout<br>* style: refine exact mobile header, app and footer geometry<br>* feat: add remaining mobile-specific copy hooks<br>* fix: align English copy with dedicated Figma artboard<br>* style: center mobile app copy and support navigation menu<br>* feat: make mobile navigation functional<br>* fix: preserve responsive translation line breaks<br>* fix: localize support email addresses<br>* fix: switch localized support email with locale | 02/10/2026 |
| `vitaHealth-UPC/landing-page` | `develop` | `f67a5b1` | `fix: improve landing fidelity and responsive behavior (#9)` | Align the landing more closely with the desktop/mobile Figma variants and harden responsive/i18n behavior. | 02/10/2026 |
| `vitaHealth-UPC/landing-page` | `develop` | `02d7b16` | `fix: refresh Figma decorative assets (#10)` | Use the Figma-rendered reminder strip and CTA plant assets for closer visual fidelity. | 02/10/2026 |
| `vitaHealth-UPC/landing-page` | `develop` | `2a9d314` | `fix: keep hero overlays registered with the Figma crop (#11)` | Anchor wide-desktop hero overlays to the final exported Figma crop while preserving mobile-specific behavior. | 02/10/2026 |
| `vitaHealth-UPC/landing-page` | `develop` | `ce1c84d` | `fix: polish final landing fidelity and mobile app preview` | Align final hero, app showcase, pricing, testimonial, support and CTA details with the Figma desktop/mobile variants. | 02/10/2026 |
| `vitaHealth-UPC/landing-page` | `develop` | `d9c3acd` | `fix: enlarge app previews and sharpen mobile mockups` | Increase desktop/mobile app-preview scale, preserve the intentional mobile carousel, and replace mobile EN/ES phone renders with high-DPI Figma exports. | 02/10/2026 |
| `vitaHealth-UPC/landing-page` | `develop` | `f8d0c33` | `fix: sharpen all key landing assets` | Regenerate app mockups from Figma at 3x and visible icons/branding at 4x, preserving the intentional carousel and existing layout. | 02/10/2026 |
| `vitaHealth-UPC/landing-page` | `develop` | `e3c58c8` | `fix: polish hero branding and floating cards (#16)` | — | 02/10/2026 |
| `vitaHealth-UPC/landing-page` | `develop` | `4eb0299` | `fix: polish showcase and responsive transitions (#17)` | * fix: polish app showcase and responsive transitions<br>* fix: keep mobile translated hero card typography consistent | 02/10/2026 |
| `vitaHealth-UPC/landing-page` | `develop` | `5bdfd38` | `fix: sharpen final Figma branding assets (#18)` | — | 02/10/2026 |
| `vitaHealth-UPC/landing-page` | `develop` | `a6b8a9e` | `fix: align final hero annotation and translated card type (#19)` | — | 02/10/2026 |
| `vitaHealth-UPC/landing-page` | `develop` | `4f40664` | `fix: consolidate landing fidelity and responsive polish` | Hero, app showcase, mobile support/CTA/footer and responsive breakpoint polish consolidated from the final fix pass. | 02/10/2026 |
| `vitaHealth-UPC/landing-page` | `develop` | `25e6252` | `fix: final minor landing page refinements` | Balance the mobile hero family card, restore family member icons, document the project, and deploy Pages from develop and main. | 02/10/2026 |
| `vitaHealth-UPC/landing-page` | `fix/minor-fixes` | `ab0a9a9` | `fix: polish hero family status card` | — | 02/10/2026 |
| `vitaHealth-UPC/landing-page` | `fix/minor-fixes` | `aa4936d` | `fix: use exact Figma person icons in hero family card` | — | 02/10/2026 |
| `vitaHealth-UPC/landing-page` | `fix/minor-fixes` | `813de32` | `fix: rebalance hero family card spacing` | — | 02/10/2026 |
| `vitaHealth-UPC/landing-page` | `fix/minor-fixes` | `40bc711` | `fix: stabilize responsive fidelity across landing` | Consolidate hero family-card fidelity and responsive layout fixes for intermediate desktop, tablet, CTA and footer behavior. | 02/10/2026 |
| `vitaHealth-UPC/landing-page` | `fix/minor-fixes` | `5e7e70d` | `fix: refine family card and fluid mobile hero` | Match Figma family-card rhythm, use local avatar assets, stabilize 431–767px hero behavior, and remove stylesheet comments. | 02/10/2026 |
| `vitaHealth-UPC/landing-page` | `main` | `da4f0ec` | `sync: use local Figma avatar assets` | — | 02/10/2026 |
| `vitaHealth-UPC/landing-page` | `main` | `09212a4` | `sync: match final Figma spacing` | — | 02/10/2026 |
| `vitaHealth-UPC/landing-page` | `main` | `159f481` | `sync: apply final responsive cleanup` | — | 02/10/2026 |
| `vitaHealth-UPC/landing-page` | `fix/minor-fixes` | `d5bab1e` | `fix: match mobile family card bullets to Figma` | — | 02/10/2026 |
| `vitaHealth-UPC/landing-page` | `develop` | `0bb6015` | `fix: match mobile family card to Figma` | Remove mobile avatars, restore bullet rows, hide time lines, and match the 143x68 Figma family-card geometry. | 02/10/2026 |
| `vitaHealth-UPC/web-services` | `develop` | `08c2dc4` | `Initial commit` | — | 30/09/2026 |
| `vitaHealth-UPC/web-services` | `develop` | `049a752` | `feat(web-services): scaffold Spring Boot project with DDD bounded contexts add base project` | — | 30/09/2026 |
| `vitaHealth-UPC/web-services` | `develop` | `2fee996` | `feat: update backend structure` | — | 03/10/2026 |
| `vitaHealth-UPC/web-services` | `develop` | `a7684fe` | `chore: normalize backend scaffold and bounded context packages` | — | 04/10/2026 |
| `vitaHealth-UPC/web-services` | `develop` | `14e4488` | `docs: define backend architecture and technical story tickets` | — | 04/10/2026 |
| `vitaHealth-UPC/web-services` | `develop` | `66d6f0b` | `ci: add backend build and test workflow` | — | 04/10/2026 |
| `vitaHealth-UPC/web-services` | `develop` | `a908311` | `chore(omission-escalation): remove placeholder package-info files` | — | 06/10/2026 |
| `vitaHealth-UPC/web-services` | `develop` | `e6244e7` | `feat(intake-execution): add IntakeUnconfirmed and IntakeConfirmed events` | — | 06/10/2026 |
| `vitaHealth-UPC/web-services` | `develop` | `6b9a44d` | `feat(omission-escalation): add domain model, escalation policy and ports` | — | 06/10/2026 |
| `vitaHealth-UPC/web-services` | `develop` | `f49660d` | `feat(omission-escalation): add command handlers and event handlers` | — | 06/10/2026 |
| `vitaHealth-UPC/web-services` | `develop` | `704a733` | `feat(omission-escalation): add persistence, scheduler, event listeners and push adapter` | — | 06/10/2026 |
| `vitaHealth-UPC/web-services` | `develop` | `fd83c72` | `test: add domain tests for cases and escalation policy` | — | 06/10/2026 |
| `vitaHealth-UPC/web-services` | `develop` | `7e3342a` | `feat: add domain model, exceptions and ports` | — | 06/10/2026 |
| `vitaHealth-UPC/web-services` | `develop` | `7f88ab8` | `feat: add command, query and event handlers` | — | 06/10/2026 |
| `vitaHealth-UPC/web-services` | `develop` | `84cb6c6` | `feat: add persistence, module adapters and omission event listener` | — | 06/10/2026 |
| `vitaHealth-UPC/web-services` | `develop` | `f0cbd66` | `feat(family-monitoring): add REST controllers with OpenAPI documentation` | — | 06/10/2026 |
| `vitaHealth-UPC/web-services` | `develop` | `59b6a21` | `feat: permit all requests in dev profile until authentication exists` | — | 06/10/2026 |
| `vitaHealth-UPC/web-services` | `develop` | `c9b5051` | `test: add domain tests for alerts and notes` | — | 06/10/2026 |
| `vitaHealth-UPC/web-services` | `develop` | `062fee7` | `test: add omission to family monitoring flow test on in-memory database` | — | 06/10/2026 |
| `vitaHealth-UPC/web-services` | `develop` | `09ce4ec` | `feat(identity): caregiver account and session API (TS-07)` | Implements US-10/US-11 registration, verification and caregiver sessions with DDD/CQRS boundaries. | 05/10/2026 |
| `vitaHealth-UPC/web-services` | `develop` | `9d28e0d` | `feat(identity): PIN authentication and lockout (TS-01)` | Implements US-01 PIN registration, credential hashing, attempt tracking, temporary lockout and older-adult session issuance. | 05/10/2026 |
| `vitaHealth-UPC/web-services` | `develop` | `5b69ad7` | `feat(identity): support email verification resend` | Completes the US-11 expired-verification path with a resource-oriented resend endpoint, verification-code renewal in the Account aggregate, and domain coverage. | 05/10/2026 |
| `vitaHealth-UPC/web-services` | `develop` | `ccd0edb` | `feat(care-link): implement care linking lifecycle` | — | 05/10/2026 |
| `vitaHealth-UPC/web-services` | `develop` | `ef4c4d6` | `fix(treatment): enforce active care-link authorization` | — | 06/10/2026 |
| `vitaHealth-UPC/web-services` | `develop` | `78c5522` | `fix(treatment): authorize caregiver operations consistently` | — | 06/10/2026 |
| `vitaHealth-UPC/web-services` | `develop` | `556f804` | `fix(treatment): support multiple schedule times` | — | 06/10/2026 |
| `vitaHealth-UPC/web-services` | `feature/ts-08-intake-schedule-generation` | `0da050d` | `feat(intake): generate future doses for active treatments` | — | 06/10/2026 |
| `vitaHealth-UPC/web-services` | `feature/ts-08-intake-schedule-generation` | `7ebc040` | `fix(care-link): make service constructor injectable` | — | 06/10/2026 |
| `vitaHealth-UPC/web-services` | `feature/ts-08-intake-schedule-generation` | `23afe9a` | `fix(identity): make command services injectable` | — | 06/10/2026 |
| `vitaHealth-UPC/web-services` | `feature/ts-08-intake-read-api` | `3d58898` | `feat(intake): expose dose detail read model` | — | 06/10/2026 |
| `vitaHealth-UPC/web-services` | `feature/ts-04-intake-confirmation-api` | `fc7ff1d` | `feat(intake): implement idempotent intake confirmation` | — | 06/10/2026 |
| `vitaHealth-UPC/web-services` | `codex/intake-contract-coherence` | `5ceb58f` | `fix(intake): align cross-context UUID contracts and publish confirmation once` | — | 06/10/2026 |
| `vitaHealth-UPC/web-services` | `feature/ts-12-inventory-replenishment-api` | `b195770` | `feat(inventory): add batch entity and stock level value object` | — | 06/10/2026 |
| `vitaHealth-UPC/web-services` | `feature/ts-12-inventory-replenishment-api` | `1aded10` | `feat(inventory): add inventory aggregate with low stock detection` | — | 06/10/2026 |
| `vitaHealth-UPC/web-services` | `feature/ts-12-inventory-replenishment-api` | `1ec8026` | `feat(inventory): add inventory commands, query and repository contract` | — | 06/10/2026 |
| `vitaHealth-UPC/web-services` | `feature/ts-12-inventory-replenishment-api` | `a14f0ab` | `feat(inventory): add inventory command and query services` | - InventoryCommandService for initial inventory, replenishment and unit consumption<br>- InventoryQueryService for remaining stock<br>- One decrement per intake through consumption tracking<br>- InventoryEventPublisher outbound port for domain events<br>- InventoryApplicationException with stable error codes, including INVALID_QUANTITY | 06/10/2026 |
| `vitaHealth-UPC/web-services` | `feature/ts-12-inventory-replenishment-api` | `f124bbf` | `feat(inventory): add inventory JPA persistence` | - JPA entities for inventories, batches and per-intake consumptions<br>- Unique medication_id (logical reference, no cross-BC FK) and unique intake_id<br>- Optimistic locking with @Version to avoid lost stock updates<br>- InventoryRepositoryImpl adapter updating the managed entity | 06/10/2026 |
| `vitaHealth-UPC/web-services` | `feature/ts-12-inventory-replenishment-api` | `469f953` | `feat(inventory): add in-process domain event publisher` | — | 06/10/2026 |
| `vitaHealth-UPC/web-services` | `feature/ts-12-inventory-replenishment-api` | `6bdc2cc` | `feat(inventory): expose inventory REST API` | - InventoryController under /api/v1/inventories documented with OpenAPI<br>- Register initial inventory (US-40), get remaining stock (US-41, US-42) and register replenishment (US-43)<br>- Request/response resources and InventoryResourceAssembler<br>- InventoryExceptionHandler with stable error codes and localized messages | 06/10/2026 |
| `vitaHealth-UPC/web-services` | `feature/ts-12-inventory-replenishment-api` | `98446c2` | `feat(inventory): add inventory error messages in English and es-419` | — | 06/10/2026 |
| `vitaHealth-UPC/web-services` | `feature/ts-12-inventory-replenishment-api` | `1e6e503` | `test(inventory): cover inventory domain invariants and threshold crossing` | — | 06/10/2026 |
| `vitaHealth-UPC/web-services` | `feature/ts-12-inventory-replenishment-api` | `9b2bf00` | `test(inventory): cover command and query services with in-memory fakes` | — | 06/10/2026 |
| `vitaHealth-UPC/web-services` | `feature/ts-12-inventory-replenishment-api` | `7cd6ac3` | `test(inventory): verify JPA adapter, unique keys and optimistic locking on H2` | — | 06/10/2026 |
| `vitaHealth-UPC/web-services` | `feature/ts-12-inventory-replenishment-api` | `04803ca` | `test(inventory): verify REST contract, error codes and es-419 messages` | — | 06/10/2026 |
| `vitaHealth-UPC/web-services` | `feature/ts-08-intake-schedule-generation` | `4bb19a7` | `feat(intake): TS-08 bounded chronological agenda query` | — | 06/10/2026 |
| `vitaHealth-UPC/web-services` | `feature/ts-09-family-summary-history-api` | `6f19a6d` | `feat(monitoring): expose real intake history and status endpoints` | — | 06/10/2026 |
| `vitaHealth-UPC/web-services` | `feature/ts-10-adherence-analytics-patterns` | `2ed1cbd` | `fix(intake): align persistence entity with unconfirmed intake query` | — | 06/10/2026 |
| `vitaHealth-UPC/web-services` | `feature/ts-05-unconfirmed-intake-processing` | `e335cbc` | `feat(omission): complete TS-05 automatic intake processing` | — | 06/10/2026 |
| `vitaHealth-UPC/web-services` | `feature/ts-14-plans-subscriptions-api` | `a75faae` | `feat(subscription): implement TS-14 plans and subscriptions API` | — | 06/10/2026 |
| `vitaHealth-UPC/web-services` | `develop` | `123b3ba` | `feat(notification): complete TS-06 push notification integration` | * feat(notification): make reminder delivery policy testable<br>* feat(notification): isolate push provider behind ACL<br>* feat(notification): add push provider boundary<br>* feat(notification): add safe development provider<br>* test(notification): cover channel quiet hours and failure<br>* test(notification): cover provider mapping and failure | 06/10/2026 |
| `vitaHealth-UPC/web-services` | `develop` | `c4fbb3a` | `feat(voice): implement TS-11 speech-to-text confirmation flow` | Integrate configurable speech-to-text confirmation, validate recognized intent and confidence, preserve intake idempotency, and keep provider failures non-mutating. | 06/10/2026 |
| `vitaHealth-UPC/web-services` | `feature/ts-10-adherence-analytics-patterns` | `116aea5` | `feat(analytics): add TS-10 outcome history, patterns and follow-up insights` | — | 06/10/2026 |
| `vitaHealth-UPC/web-services` | `feature/ts-10-adherence-analytics-patterns` | `faf381e` | `feat(analytics): expose outcome breakdown and configurable recurrence criteria` | — | 06/10/2026 |
| `vitaHealth-UPC/web-services` | `feature/ts-09-family-summary-history-api` | `98b4b51` | `feat(monitoring): complete TS-09 real summaries, contact and care-link access` | — | 06/10/2026 |
| `vitaHealth-UPC/web-services` | `feature/ts-10-adherence-analytics-patterns` | `965dc37` | `feat(analytics): persist idempotent TS-10 period evidence and patterns` | — | 06/10/2026 |
| `vitaHealth-UPC/web-services` | `develop` | `f4253d4` | `chore: remove temporary dev security chain replaced by SecurityConfiguration` | — | 06/10/2026 |
| `vitaHealth-UPC/web-services` | `develop` | `85ad8a1` | `feat: publish AccountEnabled when the email is verified` | — | 06/10/2026 |
| `vitaHealth-UPC/web-services` | `develop` | `7c68ae9` | `feat: add accessibility preferences domain model and defaults factory` | — | 06/10/2026 |
| `vitaHealth-UPC/web-services` | `develop` | `0a14156` | `feat: add accessibility preferences handlers and public contract` | — | 06/10/2026 |
| `vitaHealth-UPC/web-services` | `develop` | `a25b9c3` | `feat: add accessibility preferences persistence` | — | 06/10/2026 |
| `vitaHealth-UPC/web-services` | `develop` | `b171f31` | `feat: add accessibility and notification preferences endpoints` | — | 06/10/2026 |
| `vitaHealth-UPC/web-services` | `develop` | `1427386` | `feat: read notification preferences from the accessibility contract in omission` | — | 06/10/2026 |
| `vitaHealth-UPC/web-services` | `develop` | `415a69a` | `test: add accessibility preferences and account enabled tests` | — | 06/10/2026 |
| `vitaHealth-UPC/web-services` | `develop` | `f178437` | `feat: add treatment and medication lookups by older adult and medication` | — | 06/10/2026 |
| `vitaHealth-UPC/web-services` | `develop` | `b8bd23e` | `fix: pause active treatments and republish the schedule when a medication changes` | — | 06/10/2026 |
| `vitaHealth-UPC/web-services` | `develop` | `e4b7f33` | `feat: list medications and treatments, expose medication lookup and document with OpenAPI` | — | 06/10/2026 |
| `vitaHealth-UPC/web-services` | `develop` | `3595091` | `test: add treatment consistency and API tests` | — | 06/10/2026 |
| `vitaHealth-UPC/web-services` | `develop` | `a20c0ba` | `feat: respect the voice confirmation preference when confirming by voice` | — | 06/10/2026 |
| `vitaHealth-UPC/web-services` | `develop` | `8604122` | `feat: publish adherence patterns and consolidate weekly on a schedule` | — | 06/10/2026 |
| `vitaHealth-UPC/web-services` | `develop` | `e8b4039` | `feat: show low stock and adherence insights in the older adult status` | — | 06/10/2026 |
| `vitaHealth-UPC/web-services` | `feature/ts-10-adherence-frontend-views` | `f362d4c` | `feat(analytics): add adherence summary and insights views for the family app` | — | 06/10/2026 |
| `vitaHealth-UPC/web-services` | `feature/ts-10-adherence-frontend-views` | `c084872` | `docs(adherence): group view endpoints under Adherence Analytics in Swagger and describe parameters` | — | 06/10/2026 |
| `vitaHealth-UPC/web-services` | `feature/ts-10-adherence-frontend-views` | `5c03757` | `refactor(adherence): rename the insights view to the singular insight resource` | — | 06/10/2026 |
| `vitaHealth-UPC/mobile-android` | `develop` | `6e7083c` | `chore: initialize native android repository` | — | 03/10/2026 |
| `vitaHealth-UPC/mobile-android` | `develop` | `1832fcc` | `chore: scaffold modular android architecture` | — | 03/10/2026 |
| `vitaHealth-UPC/mobile-android` | `develop` | `d8f7d30` | `fix: use AGP built-in Kotlin` | — | 03/10/2026 |
| `vitaHealth-UPC/mobile-android` | `develop` | `13a2752` | `fix: upgrade android ci workflow` | — | 03/10/2026 |
| `vitaHealth-UPC/mobile-android` | `develop` | `2827662` | `fix: align Android SDK with API 36` | Use Android API 36 in CI and all modules, target API 36, and Navigation 2.9.6 to keep dependencies compatible with the stable SDK available on GitHub runners. | 03/10/2026 |
| `vitaHealth-UPC/mobile-android` | `develop` | `1fea4f9` | `docs: add mobile user story implementation tickets` | — | 04/10/2026 |
| `vitaHealth-UPC/mobile-android` | `develop` | `f6630f5` | `docs: add mobile implementation ticket template` | — | 04/10/2026 |
| `vitaHealth-UPC/mobile-android` | `develop` | `1d6e573` | `feat(identity): implement caregiver registration` | Implements US-10 caregiver registration in Kotlin/Jetpack Compose, including the verification continuation state, Retrofit integration, shared UI primitives, and fixes validated by Android CI. | 05/10/2026 |
| `vitaHealth-UPC/mobile-android` | `develop` | `9ec3714` | `feat(identity): complete e-mail verification lifecycle` | Completes US-11 verification expiration and resend flow in the Android client, aligned with the merged backend verification request contract and Figma states. | 05/10/2026 |
| `vitaHealth-UPC/mobile-android` | `develop` | `eb053f5` | `feat(care-link): implement linking request flow` | — | 05/10/2026 |
| `vitaHealth-UPC/mobile-android` | `develop` | `ae44557` | `fix(shared): support disabled form fields` | — | 05/10/2026 |
| `vitaHealth-UPC/mobile-android` | `develop` | `829c446` | `feat(care-link): record older-adult consent` | — | 05/10/2026 |
| `vitaHealth-UPC/mobile-android` | `develop` | `781ca6b` | `feat(treatment): implement US-03 medication registration` | — | 06/10/2026 |
| `vitaHealth-UPC/mobile-android` | `develop` | `e72aca2` | `feat(treatment): implement US-14 treatment creation` | — | 06/10/2026 |
| `vitaHealth-UPC/mobile-android` | `develop` | `0dfded4` | `fix(treatment): align US-14 with backend draft contract` | — | 06/10/2026 |
| `vitaHealth-UPC/mobile-android` | `develop` | `830a10b` | `feat(treatment): rebase US-15 dose and frequency` | — | 06/10/2026 |
| `vitaHealth-UPC/mobile-android` | `develop` | `bed60a4` | `feat(treatment): implement US-16 schedule and instructions` | — | 06/10/2026 |
| `vitaHealth-UPC/mobile-android` | `develop` | `7798f38` | `feat(treatment): implement US-17 reminder policy` | — | 06/10/2026 |
| `vitaHealth-UPC/mobile-android` | `develop` | `8a8a5d4` | `feat(treatment): implement US-18 activation and pause lifecycle` | — | 06/10/2026 |
| `vitaHealth-UPC/mobile-android` | `develop` | `5c57f05` | `feat(treatment): implement US-19 treatment detail` | — | 06/10/2026 |
| `vitaHealth-UPC/mobile-android` | `feature/us-20-next-dose` | `13860f9` | `feat(intake): implement US-20 next dose home` | — | 06/10/2026 |
| `vitaHealth-UPC/mobile-android` | `feature/us-20-next-dose` | `f3c6ad7` | `fix(intake): use RowScope weight modifier` | — | 06/10/2026 |
| `vitaHealth-UPC/mobile-android` | `feature/us-21-dose-detail` | `63a4a18` | `feat(intake): add dose detail repository contract` | — | 06/10/2026 |
| `vitaHealth-UPC/mobile-android` | `feature/us-21-dose-detail` | `ae63251` | `feat(intake): implement US-21 dose detail` | — | 06/10/2026 |
| `vitaHealth-UPC/mobile-android` | `feature/us-21-dose-detail` | `85060f3` | `feat(intake): implement US-21 dose detail` | — | 06/10/2026 |
| `vitaHealth-UPC/mobile-android` | `feature/us-21-dose-detail` | `34f6420` | `feat(intake): implement US-21 dose detail` | — | 06/10/2026 |
| `vitaHealth-UPC/mobile-android` | `feature/us-21-dose-detail` | `10c3f38` | `feat(intake): implement US-21 dose detail` | — | 06/10/2026 |
| `vitaHealth-UPC/mobile-android` | `feature/us-21-dose-detail` | `bb2dbd7` | `feat(intake): implement US-21 dose detail` | — | 06/10/2026 |
| `vitaHealth-UPC/mobile-android` | `feature/us-21-dose-detail` | `315490f` | `feat(intake): connect intake detail endpoint` | — | 06/10/2026 |
| `vitaHealth-UPC/mobile-android` | `feature/us-21-dose-detail` | `83ed69e` | `feat(intake): add dose detail UI state` | — | 06/10/2026 |
| `vitaHealth-UPC/mobile-android` | `feature/us-21-dose-detail` | `a5cc071` | `feat(intake): add dose detail view model` | — | 06/10/2026 |
| `vitaHealth-UPC/mobile-android` | `feature/us-21-dose-detail` | `3a47435` | `feat(intake): add US-21 dose detail screen` | — | 06/10/2026 |
| `vitaHealth-UPC/mobile-android` | `feature/us-21-dose-detail` | `e13c353` | `feat(intake): wire dose detail dependencies` | — | 06/10/2026 |
| `vitaHealth-UPC/mobile-android` | `feature/us-21-dose-detail` | `59ac669` | `feat(intake): add dose detail destination` | — | 06/10/2026 |
| `vitaHealth-UPC/mobile-android` | `feature/us-21-dose-detail` | `ac63c0d` | `feat(intake): connect US-21 navigation` | — | 06/10/2026 |
| `vitaHealth-UPC/mobile-android` | `feature/us-21-dose-detail` | `2367f76` | `feat(intake): open dose detail from next dose` | — | 06/10/2026 |
| `vitaHealth-UPC/mobile-android` | `codex/us-06-intake-confirmation` | `0389cb3` | `feat(intake): implement touch confirmation with retry-safe server outcomes` | — | 06/10/2026 |
| `vitaHealth-UPC/mobile-android` | `feature/us-24-daily-schedule` | `a6d0306` | `feat(intake): US-24 weekly agenda with real outcomes and local calendar bounds` | — | 06/10/2026 |
| `vitaHealth-UPC/mobile-android` | `develop` | `37611b1` | `feat(sync): implement TS-13 offline intake continuity` | Persist essential intake data locally, fall back to cache during temporary connectivity loss, queue pending confirmations without duplicates, and synchronize them with WorkManager when connectivity returns. | 06/10/2026 |
| `vitaHealth-UPC/mobile-android` | `feature/us-25-recent-care-status` | `cbd5d1d` | `feat(us-25): implement Figma family summary with remote monitoring` | — | 06/10/2026 |
| `vitaHealth-UPC/mobile-android` | `feature/us-25-recent-care-status` | `19716fa` | `fix(us-25): preserve existing offline sync implementation` | — | 06/10/2026 |
| `vitaHealth-UPC/mobile-android` | `feature/us-25-recent-care-status` | `683cc0f` | `docs: remove chat continuation from project repository` | — | 06/10/2026 |
| `vitaHealth-UPC/mobile-android` | `feature/ts-10-adherence-entry-point` | `7c0254f` | `feat(analytics): add adherence history screen with sample data` | — | 06/10/2026 |
| `vitaHealth-UPC/mobile-android` | `feature/ts-10-adherence-entry-point` | `916053f` | `feat(analytics): add period selector and empty states to adherence history` | — | 06/10/2026 |
| `vitaHealth-UPC/mobile-android` | `feature/ts-10-adherence-entry-point` | `e80bdaa` | `feat(analytics): add adherence recommendations screen with sample data` | — | 06/10/2026 |
| `vitaHealth-UPC/mobile-android` | `feature/ts-10-adherence-entry-point` | `84c8ee7` | `feat(analytics): show recent intakes classified as on time, late or omitted` | — | 06/10/2026 |
| `vitaHealth-UPC/mobile-android` | `feature/ts-10-adherence-entry-point` | `73ea0e4` | `feat(analytics): show detected omission pattern card linked to recommendations` | — | 06/10/2026 |
| `vitaHealth-UPC/mobile-android` | `feature/ts-10-adherence-entry-point` | `22b494f` | `feat(analytics): connect the adherence screens to the backend endpoints` | — | 06/10/2026 |
| `vitaHealth-UPC/mobile-android` | `feature/ts-10-adherence-entry-point` | `27f6715` | `fix(analytics): call the singular adherence insight resource` | — | 06/10/2026 |
| `vitaHealth-UPC/mobile-android` | `feature/ts-10-adherence-entry-point` | `b3a71dc` | `feat(app): open the adherence history from the family summary` | — | 07/10/2026 |
| `vitaHealth-UPC/mobile-android` | `feature/ts-10-adherence-entry-point` | `ec5b326` | `feat(analytics): show the caregiver tab bar in the adherence screens` | — | 07/10/2026 |

#### 4.2.1.5. Testing Suite Evidence for Sprint Review
#### 4.2.1.6. Execution Evidence for Sprint Review

Durante el Sprint 1 el equipo implementó y publicó el Landing Page de Tata y construyó las vistas de la aplicación Android nativa para los flujos principales del familiar y del adulto mayor: acceso y registro, vinculación de cuidado, gestión de medicamentos y tratamientos, próxima toma y agenda, resumen familiar, analítica de adherencia, preferencias de accesibilidad e inventario de medicamentos. Las vistas consumen los endpoints del backend implementados en el mismo Sprint. Toda la interfaz está en inglés por defecto y traducida a español latinoamericano (es-419).

El Landing Page se encuentra desplegado en GitHub Pages y puede visitarse en: https://vitahealth-upc.github.io/landing-page/

**Landing Page**

| Sección | User Story | Captura |
| --- | --- | --- |
| Encabezado y hero ("Manage your medications without the hassle") | US-46 | Figura 1 |
| Propuesta de valor y funcionalidades | US-47 | Figura 2 |
| La app de Tata y "How it works" | US-47 | Figura 3 |
| Testimonio e historia detrás de Tata | US-46 | Figura 4 |
| Planes y sección de soporte | US-48 | Figura 5 |
| Llamado a la acción y footer | US-49 | Figura 6 |
| Vista responsive en dispositivo móvil | US-50 | Figura 7 |

![Landing Page - Hero](assets/execution-evidence/landing-hero.png)

*Figura 1. Encabezado y sección principal del Landing Page.*

![Landing Page - Funcionalidades](assets/execution-evidence/landing-value-features.png)

*Figura 2. Propuesta de valor y funcionalidades.*

![Landing Page - App y cómo funciona](assets/execution-evidence/landing-app-how.png)

*Figura 3. Presentación de la app y sección "How it works".*

![Landing Page - Testimonio](assets/execution-evidence/landing-testimonial-about.png)

*Figura 4. Testimonio e historia detrás de Tata.*

![Landing Page - Planes y soporte](assets/execution-evidence/landing-plans-faq.png)

*Figura 5. Planes de suscripción y sección de soporte.*

![Landing Page - CTA y footer](assets/execution-evidence/landing-cta-footer.png)

*Figura 6. Llamado a la acción y footer.*

![Landing Page - Vista móvil](assets/execution-evidence/landing-mobile.png)

*Figura 7. Vista del Landing Page en un dispositivo móvil.*

**Aplicación Android nativa**

| Módulo (Bounded Context) | Vista | User Stories | Descripción |
| --- | --- | --- | --- |
| `:identity` | Registro del familiar | US-10, US-11 | El familiar crea su cuenta y verifica su correo electrónico |
| `:identity` | Acceso con contraseña y PIN | US-01 | Inicio de sesión del familiar y acceso del adulto mayor con PIN, según su rol |
| `:carelink` | Perfiles de adultos mayores | US-12 | El familiar registra el perfil del adulto mayor y genera un código de vinculación |
| `:carelink` | Vinculación de cuidado | US-02, US-13 | Se solicita la vinculación y se registra el consentimiento del adulto mayor |
| `:treatment` | Registro y gestión de medicamentos | US-03, US-04 | El familiar registra, edita y desactiva medicamentos |
| `:treatment` | Creación y configuración del tratamiento | US-14, US-15, US-16, US-17 | Tratamiento, dosis, frecuencia, horarios, instrucciones y recordatorios |
| `:treatment` | Activación, pausa y detalle del tratamiento | US-18, US-19 | El familiar activa o pausa el tratamiento y consulta su resumen |
| `:intake` | Próxima toma y detalle de la toma | US-20, US-21, US-06 | El adulto mayor ve su próxima toma y la confirma |
| `:intake` | Agenda del día | US-24 | Tomas programadas del día con su estado |
| `:monitoring` | Resumen familiar | US-25 | Estado reciente del cuidado del adulto mayor |
| `:analytics` | Historial y recomendaciones de adherencia | US-08, US-09, US-32, US-33, US-34 | Tomas a tiempo, tardías u omitidas, patrones de omisión y recomendaciones |
| `:preferences` | Accesibilidad y notificaciones | US-35, US-36, US-37, US-38, US-39 | Tamaño de texto, alto contraste, movimiento reducido, asistencia de lectura y horario de silencio |
| `:inventory` | Inventario del medicamento | US-40, US-41, US-42, US-43 | Stock inicial, stock restante, alerta de stock bajo y registro de reposiciones con lote |

![App Android - Inventario](assets/execution-evidence/android-inventory.png)

*Figura 8. Vista de inventario (US-41, US-42) en sus estados de stock bajo y stock disponible.*

**Video de ejecución**

El siguiente video muestra la navegación del Landing Page y el recorrido por las vistas implementadas de la aplicación Android en el Sprint 1.

- Enlace al video: 
- Duración: 

#### 4.2.1.7. Services Documentation Evidence for Sprint Review

En el Sprint 1 el backend quedó documentado con OpenAPI mediante Swagger UI, desplegado junto con los Web Services. Se documentan 64 operaciones de los Bounded Contexts Identity & Subscription, Care Link, Treatment Management, Intake Execution, Family Monitoring, Adherence Analytics, Inventory & Replenishment y Accessibility & Preferences, más dos de estado del servicio. Omission & Escalation no expone endpoints REST. Las llamadas requieren el encabezado `Authorization: Bearer <token>`, salvo las que la tabla indica como públicas; sin él responden `401 AUTHENTICATION_REQUIRED`.

Repositorio de Web Services: https://github.com/vitaHealth-UPC/web-services

Documentación desplegada: https://web-services-yzxl.onrender.com/swagger-ui/index.html

**Treatment Management**

| Endpoint | Acción | Verbo HTTP | Sintaxis de llamada | Parámetros | Ejemplo de response | Explicación del response | Documentación |
| --- | --- | --- | --- | --- | --- | --- | --- |
| `/api/v1/older-adults/{olderAdultId}/treatments` | Crear un tratamiento (US-14) | POST | `POST /api/v1/older-adults/{olderAdultId}/treatments` | Path: `olderAdultId`.<br>Body: `caregiverId`, `name`. | `201` `{"id":"3f6c1d0e-8a52-4f0b-9c55-2f1f4d9a7b10","olderAdultId":"00000000-0000-0000-0000-000000000001","name":"Control de presión","status":"DRAFT","medicationId":null,"dose":null,"frequency":null,"scheduledTimes":null,"instructions":null,"reminderLeadMinutes":null}` | Crea el tratamiento en estado `DRAFT`, sin pauta. `400` si falta un dato; 403 si el cuidador no tiene un vínculo de cuidado activo con el adulto mayor. | [Swagger UI](https://web-services-yzxl.onrender.com/swagger-ui/index.html) · Treatments |
| `/api/v1/older-adults/{olderAdultId}/treatments` | Listar los tratamientos de un adulto mayor (US-19) | GET | `GET /api/v1/older-adults/{olderAdultId}/treatments?caregiverId={caregiverId}` | Path: `olderAdultId`.<br>Query: `caregiverId`. | `200` `[{"id":"3f6c1d0e-8a52-4f0b-9c55-2f1f4d9a7b10","olderAdultId":"00000000-0000-0000-0000-000000000001","name":"Control de presión","status":"DRAFT","medicationId":null,"dose":null,"frequency":null,"scheduledTimes":null,"instructions":null,"reminderLeadMinutes":null}]` | Devuelve la lista, del más antiguo al más reciente; vacía si no hay tratamientos. 403 si el cuidador no tiene un vínculo de cuidado activo con el adulto mayor. | [Swagger UI](https://web-services-yzxl.onrender.com/swagger-ui/index.html) · Treatments |
| `/api/v1/treatments/{treatmentId}/regimen` | Configurar dosis, frecuencia, horarios, instrucciones y recordatorio (US-15, US-16, US-17) | PUT | `PUT /api/v1/treatments/{treatmentId}/regimen` | Path: `treatmentId`.<br>Body: `caregiverId`, `medicationId`, `dose`, `frequency`, `scheduledTimes` (al menos un horario), `instructions`, `reminderLeadMinutes` (0 a 1440). | `200` `{"id":"3f6c1d0e-8a52-4f0b-9c55-2f1f4d9a7b10","olderAdultId":"00000000-0000-0000-0000-000000000001","name":"Control de presión","status":"DRAFT","medicationId":"7a1b2c3d-1111-4222-8333-444455556666","dose":"1 comprimido","frequency":"DAILY","scheduledTimes":["08:00:00","20:00:00"],"instructions":"Con un vaso de agua","reminderLeadMinutes":10}` | Devuelve el tratamiento con su pauta. `400` si la pauta es inválida; `404` si no existe el tratamiento o el medicamento; `409` si el medicamento está inactivo; 403 si el cuidador no tiene un vínculo de cuidado activo con el adulto mayor. | [Swagger UI](https://web-services-yzxl.onrender.com/swagger-ui/index.html) · Treatments |
| `/api/v1/treatments/{treatmentId}/activation` | Activar un tratamiento (US-18) | POST | `POST /api/v1/treatments/{treatmentId}/activation?caregiverId={caregiverId}` | Path: `treatmentId`.<br>Query: `caregiverId`. | `200` `{"id":"3f6c1d0e-8a52-4f0b-9c55-2f1f4d9a7b10","olderAdultId":"00000000-0000-0000-0000-000000000001","name":"Control de presión","status":"ACTIVE","medicationId":"7a1b2c3d-1111-4222-8333-444455556666","dose":"1 comprimido","frequency":"DAILY","scheduledTimes":["08:00:00","20:00:00"],"instructions":"Con un vaso de agua","reminderLeadMinutes":10}` | El tratamiento pasa a `ACTIVE`. `409` si la pauta está incompleta o el medicamento está inactivo; `404` si no existe; 403 si el cuidador no tiene un vínculo de cuidado activo con el adulto mayor. | [Swagger UI](https://web-services-yzxl.onrender.com/swagger-ui/index.html) · Treatments |
| `/api/v1/treatments/{treatmentId}/pause` | Pausar un tratamiento (US-18) | POST | `POST /api/v1/treatments/{treatmentId}/pause?caregiverId={caregiverId}` | Path: `treatmentId`.<br>Query: `caregiverId`. | `200` `{"id":"3f6c1d0e-8a52-4f0b-9c55-2f1f4d9a7b10","olderAdultId":"00000000-0000-0000-0000-000000000001","name":"Control de presión","status":"PAUSED","medicationId":"7a1b2c3d-1111-4222-8333-444455556666","dose":"1 comprimido","frequency":"DAILY","scheduledTimes":["08:00:00","20:00:00"],"instructions":"Con un vaso de agua","reminderLeadMinutes":10}` | El tratamiento pasa a `PAUSED` y conserva la pauta y el historial. `409` si no estaba activo; `404` si no existe; 403 si el cuidador no tiene un vínculo de cuidado activo con el adulto mayor. | [Swagger UI](https://web-services-yzxl.onrender.com/swagger-ui/index.html) · Treatments |
| `/api/v1/treatments/{treatmentId}/resume` | Reanudar un tratamiento pausado | POST | `POST /api/v1/treatments/{treatmentId}/resume?caregiverId={caregiverId}` | Path: `treatmentId`.<br>Query: `caregiverId`. | `200` `{"id":"3f6c1d0e-8a52-4f0b-9c55-2f1f4d9a7b10","olderAdultId":"00000000-0000-0000-0000-000000000001","name":"Control de presión","status":"ACTIVE","medicationId":"7a1b2c3d-1111-4222-8333-444455556666","dose":"1 comprimido","frequency":"DAILY","scheduledTimes":["08:00:00","20:00:00"],"instructions":"Con un vaso de agua","reminderLeadMinutes":10}` | El tratamiento vuelve a `ACTIVE`. `409` si no estaba pausado o su medicamento está inactivo; `404` si no existe; 403 si el cuidador no tiene un vínculo de cuidado activo con el adulto mayor. | [Swagger UI](https://web-services-yzxl.onrender.com/swagger-ui/index.html) · Treatments |
| `/api/v1/treatments/{treatmentId}` | Consultar el detalle de un tratamiento (US-19) | GET | `GET /api/v1/treatments/{treatmentId}?caregiverId={caregiverId}` | Path: `treatmentId`.<br>Query: `caregiverId`. | `200` `{"id":"3f6c1d0e-8a52-4f0b-9c55-2f1f4d9a7b10","olderAdultId":"00000000-0000-0000-0000-000000000001","name":"Control de presión","status":"ACTIVE","medicationId":"7a1b2c3d-1111-4222-8333-444455556666","dose":"1 comprimido","frequency":"DAILY","scheduledTimes":["08:00:00","20:00:00"],"instructions":"Con un vaso de agua","reminderLeadMinutes":10}` | Devuelve el tratamiento con su pauta; los campos de la pauta son `null` mientras esté incompleto. `404` si no existe; 403 si el cuidador no tiene un vínculo de cuidado activo con el adulto mayor. | [Swagger UI](https://web-services-yzxl.onrender.com/swagger-ui/index.html) · Treatments |
| `/api/v1/older-adults/{olderAdultId}/medications` | Registrar un medicamento (US-03) | POST | `POST /api/v1/older-adults/{olderAdultId}/medications` | Path: `olderAdultId`.<br>Body: `caregiverId`, `name`, `presentation`. | `201` `{"id":"7a1b2c3d-1111-4222-8333-444455556666","olderAdultId":"00000000-0000-0000-0000-000000000001","name":"Losartán","presentation":"50 mg, tableta","active":true}` | Crea el medicamento activo del adulto mayor. `400` si falta un dato obligatorio; 403 si el cuidador no tiene un vínculo de cuidado activo con el adulto mayor. | [Swagger UI](https://web-services-yzxl.onrender.com/swagger-ui/index.html) · Medications |
| `/api/v1/older-adults/{olderAdultId}/medications` | Listar los medicamentos de un adulto mayor (US-03) | GET | `GET /api/v1/older-adults/{olderAdultId}/medications?caregiverId={caregiverId}` | Path: `olderAdultId`.<br>Query: `caregiverId`. | `200` `[{"id":"7a1b2c3d-1111-4222-8333-444455556666","olderAdultId":"00000000-0000-0000-0000-000000000001","name":"Losartán","presentation":"50 mg, tableta","active":true}]` | Devuelve los medicamentos ordenados por nombre, incluidos los inactivos; vacía si no hay ninguno. 403 si el cuidador no tiene un vínculo de cuidado activo con el adulto mayor. | [Swagger UI](https://web-services-yzxl.onrender.com/swagger-ui/index.html) · Medications |
| `/api/v1/medications/{medicationId}` | Editar un medicamento (US-04) | PUT | `PUT /api/v1/medications/{medicationId}` | Path: `medicationId`.<br>Body: `caregiverId`, `name`, `presentation`. | `200` `{"id":"7a1b2c3d-1111-4222-8333-444455556666","olderAdultId":"00000000-0000-0000-0000-000000000001","name":"Losartán","presentation":"100 mg, tableta","active":true}` | Cambia el nombre y la presentación; los tratamientos que lo usan republican su agenda. `400` si falta un dato; `404` si no existe; `409` si está inactivo; 403 si el cuidador no tiene un vínculo de cuidado activo con el adulto mayor. | [Swagger UI](https://web-services-yzxl.onrender.com/swagger-ui/index.html) · Medications |
| `/api/v1/medications/{medicationId}/deactivation` | Desactivar un medicamento (US-04) | POST | `POST /api/v1/medications/{medicationId}/deactivation?caregiverId={caregiverId}` | Path: `medicationId`.<br>Query: `caregiverId`. | `200` `{"id":"7a1b2c3d-1111-4222-8333-444455556666","olderAdultId":"00000000-0000-0000-0000-000000000001","name":"Losartán","presentation":"50 mg, tableta","active":false}` | El medicamento queda inactivo y conserva su historial; un tratamiento activo que lo use se pausa. `404` si no existe; 403 si el cuidador no tiene un vínculo de cuidado activo con el adulto mayor. | [Swagger UI](https://web-services-yzxl.onrender.com/swagger-ui/index.html) · Medications |
| `/api/v1/medications/{medicationId}` | Consultar el detalle de un medicamento | GET | `GET /api/v1/medications/{medicationId}?caregiverId={caregiverId}` | Path: `medicationId`.<br>Query: `caregiverId`. | `200` `{"id":"7a1b2c3d-1111-4222-8333-444455556666","olderAdultId":"00000000-0000-0000-0000-000000000001","name":"Losartán","presentation":"50 mg, tableta","active":true}` | Devuelve el medicamento. `404` si no existe; 403 si el cuidador no tiene un vínculo de cuidado activo con el adulto mayor. | [Swagger UI](https://web-services-yzxl.onrender.com/swagger-ui/index.html) · Medications |

**Accessibility & Preferences**

| Endpoint | Acción | Verbo HTTP | Sintaxis de llamada | Parámetros | Ejemplo de response | Explicación del response | Documentación |
| --- | --- | --- | --- | --- | --- | --- | --- |
| `/api/v1/users/{userId}/preferences` | Consultar las preferencias de un usuario (US-35, US-36) | GET | `GET /api/v1/users/{userId}/preferences` | Path: `userId`. | `200` `{"userId":"00000000-0000-0000-0000-000000000001","textSize":"LARGE","highContrast":false,"reducedMotion":false,"readingAssistance":false,"voiceConfirmationEnabled":true,"quietHours":{"start":"22:00:00","end":"07:00:00"},"notificationChannels":[{"type":"PUSH","enabled":true},{"type":"SMS","enabled":false},{"type":"EMAIL","enabled":false}]}` | Devuelve las preferencias de accesibilidad y de notificación. Un usuario que nunca guardó nada recibe los valores por defecto, que se guardan en esa primera lectura. | [Swagger UI](https://web-services-yzxl.onrender.com/swagger-ui/index.html) · Accessibility |
| `/api/v1/users/{userId}/preferences/text-size` | Cambiar el tamaño de texto (US-35) | PUT | `PUT /api/v1/users/{userId}/preferences/text-size` | Path: `userId`.<br>Body: `textSize` (`SMALL`, `MEDIUM`, `LARGE` o `EXTRA_LARGE`). | `200` `{"userId":"00000000-0000-0000-0000-000000000001","textSize":"LARGE","highContrast":false,"reducedMotion":false,"readingAssistance":false,"voiceConfirmationEnabled":true,"quietHours":{"start":"22:00:00","end":"07:00:00"},"notificationChannels":[{"type":"PUSH","enabled":true},{"type":"SMS","enabled":false},{"type":"EMAIL","enabled":false}]}` | Devuelve las preferencias actualizadas. Cada cambio se conserva para las próximas sesiones. `400` si el tamaño no es válido. | [Swagger UI](https://web-services-yzxl.onrender.com/swagger-ui/index.html) · Accessibility |
| `/api/v1/users/{userId}/preferences/contrast` | Activar o desactivar el contraste reforzado (US-36) | PUT | `PUT /api/v1/users/{userId}/preferences/contrast` | Path: `userId`.<br>Body: `enabled` (booleano). | `200` `{"userId":"00000000-0000-0000-0000-000000000001","textSize":"LARGE","highContrast":true,"reducedMotion":false,"readingAssistance":false,"voiceConfirmationEnabled":true,"quietHours":{"start":"22:00:00","end":"07:00:00"},"notificationChannels":[{"type":"PUSH","enabled":true},{"type":"SMS","enabled":false},{"type":"EMAIL","enabled":false}]}` | Devuelve las preferencias actualizadas. Cada cambio se conserva para las próximas sesiones. | [Swagger UI](https://web-services-yzxl.onrender.com/swagger-ui/index.html) · Accessibility |
| `/api/v1/users/{userId}/preferences/reduced-motion` | Activar o desactivar la reducción de movimiento (US-37) | PUT | `PUT /api/v1/users/{userId}/preferences/reduced-motion` | Path: `userId`.<br>Body: `enabled` (booleano). | `200` `{"userId":"00000000-0000-0000-0000-000000000001","textSize":"LARGE","highContrast":false,"reducedMotion":true,"readingAssistance":false,"voiceConfirmationEnabled":true,"quietHours":{"start":"22:00:00","end":"07:00:00"},"notificationChannels":[{"type":"PUSH","enabled":true},{"type":"SMS","enabled":false},{"type":"EMAIL","enabled":false}]}` | Devuelve las preferencias actualizadas. Cada cambio se conserva para las próximas sesiones. | [Swagger UI](https://web-services-yzxl.onrender.com/swagger-ui/index.html) · Accessibility |
| `/api/v1/users/{userId}/preferences/reading-assistance` | Activar o desactivar la ayuda de lectura (US-38) | PUT | `PUT /api/v1/users/{userId}/preferences/reading-assistance` | Path: `userId`.<br>Body: `enabled` (booleano). | `200` `{"userId":"00000000-0000-0000-0000-000000000001","textSize":"LARGE","highContrast":false,"reducedMotion":false,"readingAssistance":true,"voiceConfirmationEnabled":true,"quietHours":{"start":"22:00:00","end":"07:00:00"},"notificationChannels":[{"type":"PUSH","enabled":true},{"type":"SMS","enabled":false},{"type":"EMAIL","enabled":false}]}` | Devuelve las preferencias actualizadas. Cada cambio se conserva para las próximas sesiones. | [Swagger UI](https://web-services-yzxl.onrender.com/swagger-ui/index.html) · Accessibility |
| `/api/v1/users/{userId}/preferences/voice-confirmation` | Activar o desactivar la confirmación por voz (US-06) | PUT | `PUT /api/v1/users/{userId}/preferences/voice-confirmation` | Path: `userId`.<br>Body: `enabled` (booleano). | `200` `{"userId":"00000000-0000-0000-0000-000000000001","textSize":"LARGE","highContrast":false,"reducedMotion":false,"readingAssistance":false,"voiceConfirmationEnabled":false,"quietHours":{"start":"22:00:00","end":"07:00:00"},"notificationChannels":[{"type":"PUSH","enabled":true},{"type":"SMS","enabled":false},{"type":"EMAIL","enabled":false}]}` | Devuelve las preferencias actualizadas. Solo guarda la preferencia; el reconocimiento de voz pertenece a Intake Execution. | [Swagger UI](https://web-services-yzxl.onrender.com/swagger-ui/index.html) · Accessibility |
| `/api/v1/users/{userId}/notification-preferences` | Configurar el horario de silencio y los canales de notificación (US-39) | PUT | `PUT /api/v1/users/{userId}/notification-preferences` | Path: `userId`.<br>Body: `quietHours` (`start` y `end`, o `null` para quitarlo), `channels` (lista de `type` y `enabled`; `PUSH`, `SMS` o `EMAIL`, sin repetir). | `200` `{"userId":"00000000-0000-0000-0000-000000000001","textSize":"LARGE","highContrast":false,"reducedMotion":false,"readingAssistance":false,"voiceConfirmationEnabled":true,"quietHours":{"start":"22:00:00","end":"07:00:00"},"notificationChannels":[{"type":"PUSH","enabled":true},{"type":"SMS","enabled":false},{"type":"EMAIL","enabled":false}]}` | Reemplaza ambos ajustes a la vez y devuelve las preferencias. El horario puede cruzar la medianoche. `400` si inicio y fin son iguales o se repite un canal. | [Swagger UI](https://web-services-yzxl.onrender.com/swagger-ui/index.html) · Notification Preferences |

**Identity & Subscription**

| Endpoint | Acción | Verbo HTTP | Sintaxis de llamada | Parámetros | Ejemplo de response | Explicación del response | Documentación |
| --- | --- | --- | --- | --- | --- | --- | --- |
| `/api/v1/email-verification-requests` | Solicitar el código de verificación del correo | POST | `POST /api/v1/email-verification-requests` | Body: `email`. | `202` `{"id":"string","name":"string","email":"string","status":"string","accessToken":"string","expiresAt":"2026-10-06T08:00:00Z"}` | Solicita el envío del código de verificación; responde `202`. `400` si el correo falta o no es válido. No requiere token. | [Swagger UI](https://web-services-yzxl.onrender.com/swagger-ui/index.html) · email-verification-requests-controller |
| `/api/v1/accounts` | Crear una cuenta | POST | `POST /api/v1/accounts` | Body: `name`, `email`, `password`. | `201` `{"id":"string","name":"string","email":"string","status":"string","accessToken":"string","expiresAt":"2026-10-06T08:00:00Z"}` | Crea la cuenta y devuelve sus datos y el token de acceso. `400` si faltan datos. No requiere token. | [Swagger UI](https://web-services-yzxl.onrender.com/swagger-ui/index.html) · accounts-controller |
| `/api/v1/accounts/verification` | Verificar el correo con el código recibido | POST | `POST /api/v1/accounts/verification` | Body: `email`, `code`. | `200` `{"id":"string","name":"string","email":"string","status":"string","accessToken":"string","expiresAt":"2026-10-06T08:00:00Z"}` | Valida el código y devuelve los datos de la cuenta con el token de acceso. `400` si el código es inválido. No requiere token. | [Swagger UI](https://web-services-yzxl.onrender.com/swagger-ui/index.html) · accounts-controller |
| `/api/v1/sessions` | Iniciar sesión de un cuidador o familiar | POST | `POST /api/v1/sessions` | Body: `email`, `password`. | `200` `{"accountId":"string","accessToken":"string","expiresAt":"2026-10-06T08:00:00Z"}` | Devuelve el `accessToken` y su vencimiento. `400` si faltan datos. No requiere token. | [Swagger UI](https://web-services-yzxl.onrender.com/swagger-ui/index.html) · sessions-controller |
| `/api/v1/sessions/current` | Consultar la sesión actual | GET | `GET /api/v1/sessions/current` | Ninguno. | `200` `{"subjectId":"string","role":"CAREGIVER","expiresAt":"2026-10-06T08:00:00Z","careLinkId":"string","name":"string"}` | Devuelve el sujeto de la sesión, su rol (`CAREGIVER` u otro), el vínculo de cuidado y el vencimiento. | [Swagger UI](https://web-services-yzxl.onrender.com/swagger-ui/index.html) · session-lifecycle-controller |
| `/api/v1/sessions` | Cerrar la sesión | DELETE | `DELETE /api/v1/sessions` | Header: `Authorization`. | `204` Sin cuerpo | Invalida el token enviado en `Authorization`; responde `204` sin cuerpo. | [Swagger UI](https://web-services-yzxl.onrender.com/swagger-ui/index.html) · session-lifecycle-controller |
| `/api/v1/pin-credentials` | Registrar el PIN de un adulto mayor | POST | `POST /api/v1/pin-credentials` | Body: `olderAdultId`, `pin`. | `201` Sin cuerpo | Guarda el PIN con el que el adulto mayor iniciará sesión; responde `201` sin cuerpo. | [Swagger UI](https://web-services-yzxl.onrender.com/swagger-ui/index.html) · pin-credentials-controller |
| `/api/v1/pin-sessions` | Iniciar sesión de un adulto mayor con PIN | POST | `POST /api/v1/pin-sessions` | Body: `olderAdultId`, `pin`. | `200` `{"olderAdultId":"string","accessToken":"string","expiresAt":"2026-10-06T08:00:00Z"}` | Devuelve el `accessToken` de la sesión del adulto mayor y su vencimiento. `400` si faltan datos. No requiere token. | [Swagger UI](https://web-services-yzxl.onrender.com/swagger-ui/index.html) · pin-sessions-controller |
| `/api/v1/plans` | Listar los planes disponibles | GET | `GET /api/v1/plans` | Ninguno. | `200` `[{"code":"string","name":"string","monthlyPrice":1,"currency":"string","capabilities":["REMINDERS"]}]` | Devuelve los planes con su precio mensual, moneda y capacidades. No requiere token. | [Swagger UI](https://web-services-yzxl.onrender.com/swagger-ui/index.html) · Plans and subscriptions |
| `/api/v1/accounts/{accountId}/subscription` | Consultar la suscripción de una cuenta (US-44) | GET | `GET /api/v1/accounts/{accountId}/subscription` | Path: `accountId`. | `200` `{"accountId":"string","plan":{"code":"string","name":"string","monthlyPrice":1,"currency":"string","capabilities":["REMINDERS"]},"status":"ACTIVE","renewsAt":"2026-10-06T08:00:00Z"}` | Devuelve el plan vigente, el estado de la suscripción, la fecha de renovación y las capacidades habilitadas. | [Swagger UI](https://web-services-yzxl.onrender.com/swagger-ui/index.html) · Plans and subscriptions |
| `/api/v1/accounts/{accountId}/subscription` | Activar o cambiar el plan de una cuenta (US-45) | PUT | `PUT /api/v1/accounts/{accountId}/subscription` | Path: `accountId`.<br>Body: `planCode`. | `200` `{"accountId":"string","plan":{"code":"string","name":"string","monthlyPrice":1,"currency":"string","capabilities":["REMINDERS"]},"status":"ACTIVE","renewsAt":"2026-10-06T08:00:00Z"}` | Aplica el plan indicado por `planCode` y devuelve la suscripción resultante. | [Swagger UI](https://web-services-yzxl.onrender.com/swagger-ui/index.html) · Plans and subscriptions |

**Care Link**

| Endpoint | Acción | Verbo HTTP | Sintaxis de llamada | Parámetros | Ejemplo de response | Explicación del response | Documentación |
| --- | --- | --- | --- | --- | --- | --- | --- |
| `/api/v1/older-adults` | Registrar un adulto mayor | POST | `POST /api/v1/older-adults` | Body: `caregiverId`, `fullName`, `birthDate`, `emergencyContactName`, `emergencyContactRelationship`, `emergencyContactPhone`. | `201` `{"id":"string","registeredByCaregiverId":"string","fullName":"string","birthDate":"2026-10-06","emergencyContactName":"string","emergencyContactRelationship":"string","emergencyContactPhone":"string","createdAt":"2026-10-06T08:00:00Z"}` | Crea el adulto mayor con su contacto de emergencia y devuelve sus datos; responde `201`. | [Swagger UI](https://web-services-yzxl.onrender.com/swagger-ui/index.html) · older-adults-controller |
| `/api/v1/older-adults/{olderAdultId}` | Consultar los datos de un adulto mayor | GET | `GET /api/v1/older-adults/{olderAdultId}` | Path: `olderAdultId`. | `200` `{"id":"string","registeredByCaregiverId":"string","fullName":"string","birthDate":"2026-10-06","emergencyContactName":"string","emergencyContactRelationship":"string","emergencyContactPhone":"string","createdAt":"2026-10-06T08:00:00Z"}` | Devuelve los datos del adulto mayor y de su contacto de emergencia. | [Swagger UI](https://web-services-yzxl.onrender.com/swagger-ui/index.html) · older-adults-controller |
| `/api/v1/care-links/linking-codes` | Generar un código de vinculación | POST | `POST /api/v1/care-links/linking-codes` | Body: `caregiverId`, `olderAdultId`. | `201` `{"id":"string","caregiverId":"string","olderAdultId":"string","status":"PENDING","linkingCode":"string","codeExpiresAt":"2026-10-06T08:00:00Z","codeUsedAt":"2026-10-06T08:00:00Z","consentGranted":true,"consentRecordedAt":"2026-10-06T08:00:00Z","confirmedAt":"2026-10-06T08:00:00Z","accessToken":"string","expiresAt":"2026-10-06T08:00:00Z"}` | Crea un vínculo en estado `PENDING` con un código y su vencimiento; responde `201`. | [Swagger UI](https://web-services-yzxl.onrender.com/swagger-ui/index.html) · care-links-controller |
| `/api/v1/care-links/acceptances` | Aceptar un código de vinculación | POST | `POST /api/v1/care-links/acceptances` | Body: `caregiverId`, `code`. | `200` `{"id":"string","caregiverId":"string","olderAdultId":"string","status":"PENDING","linkingCode":"string","codeExpiresAt":"2026-10-06T08:00:00Z","codeUsedAt":"2026-10-06T08:00:00Z","consentGranted":true,"consentRecordedAt":"2026-10-06T08:00:00Z","confirmedAt":"2026-10-06T08:00:00Z","accessToken":"string","expiresAt":"2026-10-06T08:00:00Z"}` | Usa el código para asociar al cuidador con el vínculo y devuelve el vínculo actualizado. | [Swagger UI](https://web-services-yzxl.onrender.com/swagger-ui/index.html) · care-links-controller |
| `/api/v1/care-links/{careLinkId}/consent` | Registrar el consentimiento del adulto mayor | POST | `POST /api/v1/care-links/{careLinkId}/consent` | Path: `careLinkId`.<br>Body: `accepted`. | `200` `{"id":"string","caregiverId":"string","olderAdultId":"string","status":"PENDING","linkingCode":"string","codeExpiresAt":"2026-10-06T08:00:00Z","codeUsedAt":"2026-10-06T08:00:00Z","consentGranted":true,"consentRecordedAt":"2026-10-06T08:00:00Z","confirmedAt":"2026-10-06T08:00:00Z","accessToken":"string","expiresAt":"2026-10-06T08:00:00Z"}` | Guarda si el adulto mayor aceptó (`accepted`) y devuelve el vínculo con la fecha del consentimiento. | [Swagger UI](https://web-services-yzxl.onrender.com/swagger-ui/index.html) · care-links-controller |
| `/api/v1/care-links` | Listar los vínculos confirmados de un cuidador | GET | `GET /api/v1/care-links?caregiverId={caregiverId}` | Query: `caregiverId`. | `200` `[{"id":"string","olderAdultId":"string","olderAdultName":"string","confirmedAt":"2026-10-06T08:00:00Z"}]` | Devuelve los vínculos activos con consentimiento, del más reciente al más antiguo; vacía si no hay ninguno. | [Swagger UI](https://web-services-yzxl.onrender.com/swagger-ui/index.html) · care-links-controller |
| `/api/v1/care-links/{careLinkId}` | Consultar un vínculo de cuidado | GET | `GET /api/v1/care-links/{careLinkId}` | Path: `careLinkId`. | `200` `{"id":"string","caregiverId":"string","olderAdultId":"string","status":"PENDING","linkingCode":"string","codeExpiresAt":"2026-10-06T08:00:00Z","codeUsedAt":"2026-10-06T08:00:00Z","consentGranted":true,"consentRecordedAt":"2026-10-06T08:00:00Z","confirmedAt":"2026-10-06T08:00:00Z","accessToken":"string","expiresAt":"2026-10-06T08:00:00Z"}` | Devuelve el vínculo con su estado, código y consentimiento. | [Swagger UI](https://web-services-yzxl.onrender.com/swagger-ui/index.html) · care-links-controller |
| `/api/v1/care-links/authorization` | Verificar si un cuidador está autorizado sobre un adulto mayor | GET | `GET /api/v1/care-links/authorization?caregiverId={caregiverId}&olderAdultId={olderAdultId}` | Query: `caregiverId`, `olderAdultId`. | `200` `true` | Devuelve `true` si existe un vínculo activo entre ambos y `false` en caso contrario. | [Swagger UI](https://web-services-yzxl.onrender.com/swagger-ui/index.html) · care-links-controller |

**Intake Execution**

| Endpoint | Acción | Verbo HTTP | Sintaxis de llamada | Parámetros | Ejemplo de response | Explicación del response | Documentación |
| --- | --- | --- | --- | --- | --- | --- | --- |
| `/api/v1/older-adults/{olderAdultId}/intakes/next` | Consultar la próxima toma | GET | `GET /api/v1/older-adults/{olderAdultId}/intakes/next` | Path: `olderAdultId`. | `200` `{"id":"string","treatmentId":"string","medicationId":"string","olderAdultId":"string","medicationName":"string","dose":"string","instructions":"string","scheduledAt":"2026-10-06T08:00:00Z","status":"PENDING","confirmedAt":"2026-10-06T08:00:00Z","confirmationChannel":"TOUCH"}` | Devuelve la próxima toma programada del adulto mayor. | [Swagger UI](https://web-services-yzxl.onrender.com/swagger-ui/index.html) · intakes-controller |
| `/api/v1/older-adults/{olderAdultId}/intakes/agenda` | Consultar la agenda de tomas de un período | GET | `GET /api/v1/older-adults/{olderAdultId}/intakes/agenda?from={from}&to={to}` | Path: `olderAdultId`.<br>Query: `from`, `to`. | `200` `[{"id":"string","treatmentId":"string","medicationId":"string","olderAdultId":"string","medicationName":"string","dose":"string","instructions":"string","scheduledAt":"2026-10-06T08:00:00Z","status":"PENDING","confirmedAt":"2026-10-06T08:00:00Z","confirmationChannel":"TOUCH"}]` | Devuelve las tomas programadas entre `from` y `to`. | [Swagger UI](https://web-services-yzxl.onrender.com/swagger-ui/index.html) · intakes-controller |
| `/api/v1/intakes/{intakeId}` | Consultar una toma | GET | `GET /api/v1/intakes/{intakeId}` | Path: `intakeId`. | `200` `{"id":"string","treatmentId":"string","medicationId":"string","olderAdultId":"string","medicationName":"string","dose":"string","instructions":"string","scheduledAt":"2026-10-06T08:00:00Z","status":"PENDING","confirmedAt":"2026-10-06T08:00:00Z","confirmationChannel":"TOUCH"}` | Devuelve el medicamento, la dosis, las instrucciones, el horario y el estado de la toma. | [Swagger UI](https://web-services-yzxl.onrender.com/swagger-ui/index.html) · intakes-controller |
| `/api/v1/intakes/{intakeId}/confirmation` | Confirmar una toma (US-05) | POST | `POST /api/v1/intakes/{intakeId}/confirmation` | Path: `intakeId`.<br>Body: `channel`. | `200` `{"id":"string","treatmentId":"string","medicationId":"string","olderAdultId":"string","medicationName":"string","dose":"string","instructions":"string","scheduledAt":"2026-10-06T08:00:00Z","status":"PENDING","confirmedAt":"2026-10-06T08:00:00Z","confirmationChannel":"TOUCH"}` | Registra la confirmación por el canal indicado (`TOUCH`) y devuelve la toma actualizada. | [Swagger UI](https://web-services-yzxl.onrender.com/swagger-ui/index.html) · intakes-controller |
| `/api/v1/intakes/{intakeId}/voice-confirmation` | Confirmar una toma por voz (US-06) | POST | `POST /api/v1/intakes/{intakeId}/voice-confirmation?language={language}` | Path: `intakeId`.<br>Query: `language` (opcional).<br>Body: `audio`. | `200` `{"status":"CONFIRMED","transcript":"string","confidence":1,"intake":{"id":"string","treatmentId":"string","medicationId":"string","olderAdultId":"string","medicationName":"string","dose":"string","instructions":"string","scheduledAt":"2026-10-06T08:00:00Z","status":"PENDING","confirmedAt":"2026-10-06T08:00:00Z","confirmationChannel":"TOUCH"}}` | Procesa el audio con el servicio de reconocimiento de voz; solo una confirmación reconocida y validada cambia el estado de la toma. | [Swagger UI](https://web-services-yzxl.onrender.com/swagger-ui/index.html) · intakes-controller |

**Family Monitoring**

| Endpoint | Acción | Verbo HTTP | Sintaxis de llamada | Parámetros | Ejemplo de response | Explicación del response | Documentación |
| --- | --- | --- | --- | --- | --- | --- | --- |
| `/api/v1/older-adults/{olderAdultId}/status` | Consultar el estado reciente de un adulto mayor (US-25) | GET | `GET /api/v1/older-adults/{olderAdultId}/status?caregiverId={caregiverId}` | Path: `olderAdultId`.<br>Query: `caregiverId`. | `200` `{"nextIntakeAt":"2026-10-05T21:00:00Z","lastIntakeStatus":"CONFIRMED","hasOpenAlert":true,"openAlerts":[{"id":1,"intakeId":"101","medicationName":"Losartan 50 mg","scheduledAt":"2026-10-05T13:00:00Z","reason":"Intake not confirmed within the grace period","status":"OPEN","openedAt":"2026-10-05T13:30:00Z","closedAt":null}],"weeklyAdherence":{"confirmedIntakes":1,"totalIntakes":1},"lowStock":[{"medicationId":"7a1b2c3d-1111-4222-8333-444455556666","medicationName":"Losartán","remainingStock":4,"replenishmentThreshold":5,"detectedAt":"2026-10-06T12:00:00Z"}],"adherenceInsights":[{"medicationId":"7a1b2c3d-1111-4222-8333-444455556666","medicationName":"Losartán","omissionDays":3,"firstDay":"2026-10-01","lastDay":"2026-10-03","detectedAt":"2026-10-06T08:00:00Z"}]}` | Devuelve la próxima toma, el resultado de la última y las alertas pendientes. `404` si el adulto mayor no tiene seguimiento activo. | [Swagger UI](https://web-services-yzxl.onrender.com/swagger-ui/index.html) · Family Monitoring |
| `/api/v1/older-adults/{olderAdultId}/intakes` | Consultar el historial reciente de tomas (US-26) | GET | `GET /api/v1/older-adults/{olderAdultId}/intakes?caregiverId={caregiverId}&days={days}` | Path: `olderAdultId`.<br>Query: `caregiverId`, `days` (opcional). | `200` `[{"intakeId":"101","medicationName":"Losartan 50 mg","scheduledAt":"2026-10-05T13:00:00Z","status":"CONFIRMED"}]` | Devuelve las tomas de los últimos días, de la más reciente a la más antigua; vacía si no hay registros. `400` si `days` es inválido; `404` si no hay seguimiento activo. | [Swagger UI](https://web-services-yzxl.onrender.com/swagger-ui/index.html) · Family Monitoring |
| `/api/v1/older-adults/{olderAdultId}/contact-channel` | Consultar el canal de contacto de un adulto mayor (US-29) | GET | `GET /api/v1/older-adults/{olderAdultId}/contact-channel?caregiverId={caregiverId}` | Path: `olderAdultId`.<br>Query: `caregiverId`. | `200` `{"type":"PHONE","value":"+51 999 888 777"}` | Devuelve el canal con el que el cuidador puede comunicarse tras una alerta. `404` si no hay seguimiento o canal. | [Swagger UI](https://web-services-yzxl.onrender.com/swagger-ui/index.html) · Family Monitoring |
| `/api/v1/older-adults/{olderAdultId}/alerts/{alertId}` | Consultar el detalle de una alerta (US-27) | GET | `GET /api/v1/older-adults/{olderAdultId}/alerts/{alertId}?caregiverId={caregiverId}` | Path: `olderAdultId`, `alertId`.<br>Query: `caregiverId`. | `200` `{"id":1,"intakeId":"101","medicationName":"Losartan 50 mg","scheduledAt":"2026-10-05T13:00:00Z","reason":"Intake not confirmed within the grace period","status":"OPEN","openedAt":"2026-10-05T13:30:00Z","closedAt":null}` | Devuelve el medicamento, el horario, el estado y el motivo de la alerta. `404` si no existe. | [Swagger UI](https://web-services-yzxl.onrender.com/swagger-ui/index.html) · Alerts |
| `/api/v1/older-adults/{olderAdultId}/alerts/{alertId}/status` | Actualizar el estado de seguimiento de una alerta (US-31) | PUT | `PUT /api/v1/older-adults/{olderAdultId}/alerts/{alertId}/status?caregiverId={caregiverId}` | Path: `olderAdultId`, `alertId`.<br>Query: `caregiverId`.<br>Body: `status`. | `200` `{"id":1,"intakeId":"101","medicationName":"Losartan 50 mg","scheduledAt":"2026-10-05T13:00:00Z","reason":"Intake not confirmed within the grace period","status":"OPEN","openedAt":"2026-10-05T13:30:00Z","closedAt":null}` | `ATTENDED` registra que el cuidador actuó; `CLOSED` la quita de las pendientes y la conserva en el historial. `400` si el estado no es válido; `404` si no existe; `409` si no puede pasar a ese estado. | [Swagger UI](https://web-services-yzxl.onrender.com/swagger-ui/index.html) · Alerts |
| `/api/v1/older-adults/{olderAdultId}/notes` | Listar las notas de seguimiento (US-30) | GET | `GET /api/v1/older-adults/{olderAdultId}/notes?caregiverId={caregiverId}` | Path: `olderAdultId`.<br>Query: `caregiverId`. | `200` `[{"id":1,"text":"I called her and she had already taken the pill.","recordedAt":"2026-10-05T14:10:00Z","familiarId":"1"}]` | Devuelve las notas registradas, de la más reciente a la más antigua; vacía si no hay. `404` si no hay seguimiento activo. | [Swagger UI](https://web-services-yzxl.onrender.com/swagger-ui/index.html) · Caregiver Notes |
| `/api/v1/older-adults/{olderAdultId}/notes` | Registrar una nota de seguimiento (US-30) | POST | `POST /api/v1/older-adults/{olderAdultId}/notes` | Path: `olderAdultId`.<br>Body: `familiarId`, `text`. | `201` `{"id":1,"text":"I called her and she had already taken the pill.","recordedAt":"2026-10-05T14:10:00Z","familiarId":"1"}` | Guarda la nota con su fecha y su autor; responde `201`. `400` si la nota es inválida; `404` si no hay seguimiento activo. | [Swagger UI](https://web-services-yzxl.onrender.com/swagger-ui/index.html) · Caregiver Notes |

**Adherence Analytics**

| Endpoint | Acción | Verbo HTTP | Sintaxis de llamada | Parámetros | Ejemplo de response | Explicación del response | Documentación |
| --- | --- | --- | --- | --- | --- | --- | --- |
| `/api/v1/older-adults/{olderAdultId}/adherence/weekly` | Consultar la adherencia semanal | GET | `GET /api/v1/older-adults/{olderAdultId}/adherence/weekly?from={from}&to={to}` | Path: `olderAdultId`.<br>Query: `from`, `to`. | `200` `{"olderAdultId":"string","from":"2026-10-06T08:00:00Z","to":"2026-10-06T08:00:00Z","confirmedIntakes":1,"totalIntakes":1,"percentage":1,"onTimeIntakes":1,"lateIntakes":1,"omittedIntakes":1}` | Devuelve las tomas confirmadas, a tiempo, tardías y omitidas del período, con el porcentaje de adherencia. | [Swagger UI](https://web-services-yzxl.onrender.com/swagger-ui/index.html) · adherence-controller |
| `/api/v1/older-adults/{olderAdultId}/adherence/summary` | Consultar el resumen de adherencia | GET | `GET /api/v1/older-adults/{olderAdultId}/adherence/summary?days={days}&zone={zone}` | Path: `olderAdultId`.<br>Query: `days` (opcional), `zone` (opcional). | `200` `{"periodDays":1,"scheduledCount":1,"adherencePercent":1,"adherenceChangePercent":1,"onTimePercent":1,"onTimeChangePercent":1,"lateCount":1,"omittedCount":1,"trend":[{"date":"2026-10-06","adherencePercent":1}],"recentIntakes":[{"scheduledAt":"2026-10-06T08:00:00Z","medicationName":"string","status":"string","minutesLate":1}],"pattern":{"timeBand":"string","omittedCount":1,"lateCount":1}}` | Devuelve los porcentajes de adherencia y puntualidad con el cambio frente al período anterior, la tendencia y las tomas recientes. `204` si no hay tomas definitivas; `400` si el período o la zona son inválidos. | [Swagger UI](https://web-services-yzxl.onrender.com/swagger-ui/index.html) · Adherence Analytics |
| `/api/v1/older-adults/{olderAdultId}/adherence/recommendations` | Consultar las recomendaciones de adherencia | GET | `GET /api/v1/older-adults/{olderAdultId}/adherence/recommendations?from={from}&to={to}&zone={zone}` | Path: `olderAdultId`.<br>Query: `from`, `to`, `zone` (opcional). | `200` `[{"medicationId":"string","code":"string","evidenceDays":1}]` | Devuelve recomendaciones por medicamento con los días de evidencia. | [Swagger UI](https://web-services-yzxl.onrender.com/swagger-ui/index.html) · adherence-controller |
| `/api/v1/older-adults/{olderAdultId}/adherence/patterns` | Consultar los patrones de omisión | GET | `GET /api/v1/older-adults/{olderAdultId}/adherence/patterns?from={from}&to={to}&zone={zone}` | Path: `olderAdultId`.<br>Query: `from`, `to`, `zone` (opcional). | `200` `[{"medicationId":"string","omissionDays":1,"firstDay":"2026-10-06","lastDay":"2026-10-06"}]` | Devuelve, por medicamento, los días de omisión y el primer y último día. | [Swagger UI](https://web-services-yzxl.onrender.com/swagger-ui/index.html) · adherence-controller |
| `/api/v1/older-adults/{olderAdultId}/adherence/insights` | Consultar las recomendaciones de seguimiento según patrones | GET | `GET /api/v1/older-adults/{olderAdultId}/adherence/insights?days={days}&zone={zone}` | Path: `olderAdultId`.<br>Query: `days` (opcional), `zone` (opcional). | `200` `{"periodDays":1,"pattern":{"type":"string","timeBand":"string","omittedCount":1,"lateCount":1,"fromHour":1,"toHour":1},"concentration":[[1]],"recommendations":["string"]}` | Devuelve el patrón detectado, la concentración por franja y las recomendaciones; solo tratan recordatorios, horarios y seguimiento, nunca la dosis. `204` si no hay evidencia suficiente; `400` si el período o la zona son inválidos. | [Swagger UI](https://web-services-yzxl.onrender.com/swagger-ui/index.html) · Adherence Analytics |
| `/api/v1/older-adults/{olderAdultId}/adherence/insight` | Consultar las recomendaciones de seguimiento según patrones (ruta alterna) | GET | `GET /api/v1/older-adults/{olderAdultId}/adherence/insight?days={days}&zone={zone}` | Path: `olderAdultId`.<br>Query: `days` (opcional), `zone` (opcional). | `200` `{"periodDays":1,"pattern":{"type":"string","timeBand":"string","omittedCount":1,"lateCount":1,"fromHour":1,"toHour":1},"concentration":[[1]],"recommendations":["string"]}` | Misma respuesta que `/adherence/insights`. | [Swagger UI](https://web-services-yzxl.onrender.com/swagger-ui/index.html) · Adherence Analytics |
| `/api/v1/older-adults/{olderAdultId}/adherence/history` | Consultar el historial de tomas del período | GET | `GET /api/v1/older-adults/{olderAdultId}/adherence/history?from={from}&to={to}` | Path: `olderAdultId`.<br>Query: `from`, `to`. | `200` `[{"medicationId":"string","scheduledAt":"2026-10-06T08:00:00Z","status":"PENDING"}]` | Devuelve cada toma con su medicamento, horario y estado entre `from` y `to`. | [Swagger UI](https://web-services-yzxl.onrender.com/swagger-ui/index.html) · adherence-controller |
| `/api/v1/older-adults/{olderAdultId}/adherence/consolidations` | Consolidar la adherencia de un período | POST | `POST /api/v1/older-adults/{olderAdultId}/adherence/consolidations?from={from}&to={to}&zone={zone}` | Path: `olderAdultId`.<br>Query: `from`, `to`, `zone` (opcional). | `200` `{"id":"string","olderAdultId":"string","from":"2026-10-06T08:00:00Z","to":"2026-10-06T08:00:00Z","zone":"string","consolidatedAt":"2026-10-06T08:00:00Z","confirmedIntakes":1,"totalIntakes":1,"percentage":1,"onTimeIntakes":1,"lateIntakes":1,"omittedIntakes":1,"patterns":[{"medicationId":"string","omissionDays":1,"firstDay":"2026-10-06","lastDay":"2026-10-06"}],"minimumOmissionDays":1}` | Calcula y guarda una captura de la adherencia entre `from` y `to` y la devuelve. | [Swagger UI](https://web-services-yzxl.onrender.com/swagger-ui/index.html) · adherence-controller |
| `/api/v1/older-adults/{olderAdultId}/adherence/consolidations/{snapshotId}` | Consultar una consolidación de adherencia | GET | `GET /api/v1/older-adults/{olderAdultId}/adherence/consolidations/{snapshotId}` | Path: `olderAdultId`, `snapshotId`. | `200` `{"id":"string","olderAdultId":"string","from":"2026-10-06T08:00:00Z","to":"2026-10-06T08:00:00Z","zone":"string","consolidatedAt":"2026-10-06T08:00:00Z","confirmedIntakes":1,"totalIntakes":1,"percentage":1,"onTimeIntakes":1,"lateIntakes":1,"omittedIntakes":1,"patterns":[{"medicationId":"string","omissionDays":1,"firstDay":"2026-10-06","lastDay":"2026-10-06"}],"minimumOmissionDays":1}` | Devuelve la captura guardada con sus totales y porcentajes. | [Swagger UI](https://web-services-yzxl.onrender.com/swagger-ui/index.html) · adherence-controller |

**Inventory & Replenishment**

| Endpoint | Acción | Verbo HTTP | Sintaxis de llamada | Parámetros | Ejemplo de response | Explicación del response | Documentación |
| --- | --- | --- | --- | --- | --- | --- | --- |
| `/api/v1/inventories` | Registrar el inventario inicial de un medicamento (US-40) | POST | `POST /api/v1/inventories` | Body: `medicationId`, `initialQuantity`, `replenishmentThreshold`. | `201` `{"id":"string","medicationId":"string","remainingStock":12,"replenishmentThreshold":5,"lowStock":true,"batches":[{"id":"string","quantity":1,"registeredAt":"2026-10-06T08:00:00Z","lot":"string"}],"createdAt":"2026-10-06T08:00:00Z","updatedAt":"2026-10-06T08:00:00Z","daysRemaining":1,"dailyConsumptionUnits":1}` | Crea el stock con su primer lote y el umbral de reposición; solo existe un inventario por medicamento. `400` si faltan datos o la cantidad es inválida; `404` si el medicamento no existe; `409` si está inactivo o ya tiene inventario. | [Swagger UI](https://web-services-yzxl.onrender.com/swagger-ui/index.html) · Inventory |
| `/api/v1/inventories/{medicationId}/replenishments` | Registrar una reposición (US-43) | POST | `POST /api/v1/inventories/{medicationId}/replenishments` | Path: `medicationId`.<br>Body: `quantity`, `lot`. | `201` `{"id":"string","medicationId":"string","remainingStock":12,"replenishmentThreshold":5,"lowStock":true,"batches":[{"id":"string","quantity":1,"registeredAt":"2026-10-06T08:00:00Z","lot":"string"}],"createdAt":"2026-10-06T08:00:00Z","updatedAt":"2026-10-06T08:00:00Z","daysRemaining":1,"dailyConsumptionUnits":1}` | Agrega un lote y aumenta el stock; devuelve el inventario actualizado. `400` si faltan datos; `404` si no hay inventario; `409` si hubo una modificación concurrente. | [Swagger UI](https://web-services-yzxl.onrender.com/swagger-ui/index.html) · Inventory |
| `/api/v1/inventories/{medicationId}` | Consultar el stock de un medicamento (US-41, US-42) | GET | `GET /api/v1/inventories/{medicationId}` | Path: `medicationId`. | `200` `{"id":"string","medicationId":"string","remainingStock":12,"replenishmentThreshold":5,"lowStock":true,"batches":[{"id":"string","quantity":1,"registeredAt":"2026-10-06T08:00:00Z","lot":"string"}],"createdAt":"2026-10-06T08:00:00Z","updatedAt":"2026-10-06T08:00:00Z","daysRemaining":1,"dailyConsumptionUnits":1}` | Devuelve las unidades restantes, el umbral, el indicador de stock bajo y los lotes. `404` si no hay inventario. | [Swagger UI](https://web-services-yzxl.onrender.com/swagger-ui/index.html) · Inventory |

**Estado del servicio**

| Endpoint | Acción | Verbo HTTP | Sintaxis de llamada | Parámetros | Ejemplo de response | Explicación del response | Documentación |
| --- | --- | --- | --- | --- | --- | --- | --- |
| `/health` | Verificar que el servicio está activo | GET | `GET /health` | Ninguno. | `200` `null` | Devuelve el estado del servicio (`UP`). No requiere token. | [Swagger UI](https://web-services-yzxl.onrender.com/swagger-ui/index.html) · health-controller |
| `/actuator/health` | Verificar el estado del servicio (Actuator) | GET | `GET /actuator/health` | Ninguno. | `200` `null` | Devuelve el estado del servicio (`UP`). No requiere token. | [Swagger UI](https://web-services-yzxl.onrender.com/swagger-ui/index.html) · health-controller |

**Capturas de la documentación**

Las capturas se tomaron ejecutando el backend en un entorno local con una base de datos en memoria y datos de muestra, desde Swagger UI con la opción *Try it out*.

![Swagger UI: operaciones del grupo Treatments.](assets/services-documentation/00-swagger-treatments.png)

*Figura 1. Swagger UI: operaciones del grupo Treatments.*

![Swagger UI: operaciones del grupo Medications.](assets/services-documentation/00-swagger-medications.png)

*Figura 2. Swagger UI: operaciones del grupo Medications.*

![Swagger UI: operaciones del grupo Accessibility.](assets/services-documentation/00-swagger-accessibility.png)

*Figura 3. Swagger UI: operaciones del grupo Accessibility.*

![Swagger UI: operación del grupo Notification Preferences.](assets/services-documentation/00-swagger-notification-preferences.png)

*Figura 4. Swagger UI: operación del grupo Notification Preferences.*

![POST /api/v1/older-adults/{olderAdultId}/medications: registra Losartán 50 mg y responde 201 con el medicamento creado.](assets/services-documentation/01-registrar-medicamento.png)

*Figura 5. `POST /api/v1/older-adults/{olderAdultId}/medications`: registra Losartán 50 mg y responde `201` con el medicamento creado.*

![GET /api/v1/older-adults/{olderAdultId}/medications: responde 200 con la lista de medicamentos.](assets/services-documentation/02-listar-medicamentos.png)

*Figura 6. `GET /api/v1/older-adults/{olderAdultId}/medications`: responde `200` con la lista de medicamentos.*

![PUT /api/v1/medications/{medicationId}: cambia la presentación a 100 mg y responde 200.](assets/services-documentation/03-editar-medicamento.png)

*Figura 7. `PUT /api/v1/medications/{medicationId}`: cambia la presentación a 100 mg y responde `200`.*

![POST /api/v1/older-adults/{olderAdultId}/treatments: crea el tratamiento en estado DRAFT y responde 201.](assets/services-documentation/04-crear-tratamiento.png)

*Figura 8. `POST /api/v1/older-adults/{olderAdultId}/treatments`: crea el tratamiento en estado `DRAFT` y responde `201`.*

![PUT /api/v1/treatments/{treatmentId}/regimen: asigna medicamento, dosis, frecuencia, horarios, instrucciones y recordatorio; responde 200.](assets/services-documentation/05-configurar-pauta.png)

*Figura 9. `PUT /api/v1/treatments/{treatmentId}/regimen`: asigna medicamento, dosis, frecuencia, horarios, instrucciones y recordatorio; responde `200`.*

![POST /api/v1/treatments/{treatmentId}/activation: el tratamiento pasa a ACTIVE.](assets/services-documentation/06-activar-tratamiento.png)

*Figura 10. `POST /api/v1/treatments/{treatmentId}/activation`: el tratamiento pasa a `ACTIVE`.*

![GET /api/v1/treatments/{treatmentId}: devuelve el tratamiento con su pauta.](assets/services-documentation/07-detalle-tratamiento.png)

*Figura 11. `GET /api/v1/treatments/{treatmentId}`: devuelve el tratamiento con su pauta.*

![POST /api/v1/treatments/{treatmentId}/pause: el tratamiento pasa a PAUSED.](assets/services-documentation/08-pausar-tratamiento.png)

*Figura 12. `POST /api/v1/treatments/{treatmentId}/pause`: el tratamiento pasa a `PAUSED`.*

![POST /api/v1/medications/{medicationId}/deactivation: el medicamento queda inactivo.](assets/services-documentation/09-desactivar-medicamento.png)

*Figura 13. `POST /api/v1/medications/{medicationId}/deactivation`: el medicamento queda inactivo.*

![GET /api/v1/older-adults/{olderAdultId}/medications con un cuidador sin vínculo activo: responde 403 CARE_LINK_NOT_AUTHORIZED.](assets/services-documentation/10-error-403-sin-vinculo.png)

*Figura 14. `GET /api/v1/older-adults/{olderAdultId}/medications` con un cuidador sin vínculo activo: responde `403 CARE_LINK_NOT_AUTHORIZED`.*

![GET /api/v1/users/{userId}/preferences: devuelve las preferencias del usuario.](assets/services-documentation/11-consultar-preferencias.png)

*Figura 15. `GET /api/v1/users/{userId}/preferences`: devuelve las preferencias del usuario.*

![PUT /api/v1/users/{userId}/preferences/text-size: cambia el tamaño de texto a LARGE.](assets/services-documentation/12-cambiar-tamano-texto.png)

*Figura 16. `PUT /api/v1/users/{userId}/preferences/text-size`: cambia el tamaño de texto a `LARGE`.*

![PUT /api/v1/users/{userId}/preferences/contrast: activa el contraste reforzado.](assets/services-documentation/13-activar-contraste.png)

*Figura 17. `PUT /api/v1/users/{userId}/preferences/contrast`: activa el contraste reforzado.*

![PUT /api/v1/users/{userId}/notification-preferences: configura el horario de silencio (22:00 a 07:00) y los canales de notificación.](assets/services-documentation/14-horario-silencio-y-canales.png)

*Figura 18. `PUT /api/v1/users/{userId}/notification-preferences`: configura el horario de silencio (22:00 a 07:00) y los canales de notificación.*

Las siguientes capturas muestran los grupos de endpoints de los demás Bounded Contexts en el Swagger UI desplegado.

![Swagger UI desplegado](assets/services-documentation/swagger-identity-subscription.png)

*Figura 19. Swagger UI desplegado: operaciones de Identity & Subscription.*

![Swagger UI desplegado](assets/services-documentation/swagger-care-link.png)

*Figura 20. Swagger UI desplegado: operaciones de Care Link.*

![Swagger UI desplegado](assets/services-documentation/swagger-intake-execution.png)

*Figura 21. Swagger UI desplegado: operaciones de Intake Execution.*

![Swagger UI desplegado](assets/services-documentation/swagger-family-monitoring.png)

*Figura 22. Swagger UI desplegado: operaciones de Family Monitoring (estado, alertas y notas).*

![Swagger UI desplegado](assets/services-documentation/swagger-adherence-analytics.png)

*Figura 23. Swagger UI desplegado: operaciones de Adherence Analytics.*

![Swagger UI desplegado](assets/services-documentation/swagger-inventory.png)

*Figura 24. Swagger UI desplegado: operaciones de Inventory & Replenishment.*

(FALTA: capturas de ejecución con datos de muestra de los endpoints de los demás Bounded Contexts)

**Commits de documentación del Sprint**

Commits que agregan o modifican la documentación OpenAPI de los endpoints, integrados en la rama `develop`.

| Repository | Branch | Commit Id | Commit Message | Commit Message Body | Commited on (Date) |
| --- | --- | --- | --- | --- | --- |
| `vitaHealth-UPC/web-services` | `develop` | `f0cbd66` | `feat(family-monitoring): add REST controllers with OpenAPI documentation` | — | 06/10/2026 |
| `vitaHealth-UPC/web-services` | `develop` | `6bdc2cc` | `feat(inventory): expose inventory REST API` | - InventoryController under /api/v1/inventories documented with OpenAPI<br>- Register initial inventory (US-40), get remaining stock (US-41, US-42) and register replenishment (US-43)<br>- Request/response resources and InventoryResourceAssembler<br>- InventoryExceptionHandler with stable error codes and localized messages | 06/10/2026 |
| `vitaHealth-UPC/web-services` | `develop` | `6f19a6d` | `feat(monitoring): expose real intake history and status endpoints` | — | 06/10/2026 |
| `vitaHealth-UPC/web-services` | `develop` | `a75faae` | `feat(subscription): implement TS-14 plans and subscriptions API` | — | 06/10/2026 |
| `vitaHealth-UPC/web-services` | `develop` | `c4fbb3a` | `feat(voice): implement TS-11 speech-to-text confirmation flow` | Integrate configurable speech-to-text confirmation, validate recognized intent and confidence, preserve intake idempotency, and keep provider failures non-mutating. | 06/10/2026 |
| `vitaHealth-UPC/web-services` | `develop` | `b171f31` | `feat: add accessibility and notification preferences endpoints` | — | 06/10/2026 |
| `vitaHealth-UPC/web-services` | `develop` | `e4b7f33` | `feat: list medications and treatments, expose medication lookup and document with OpenAPI` | — | 06/10/2026 |
| `vitaHealth-UPC/web-services` | `develop` | `f362d4c` | `feat(analytics): add adherence summary and insights views for the family app` | — | 06/10/2026 |
| `vitaHealth-UPC/web-services` | `develop` | `c084872` | `docs(adherence): group view endpoints under Adherence Analytics in Swagger and describe parameters` | — | 06/10/2026 |

#### 4.2.1.8. Software Deployment Evidence for Sprint Review

En el Sprint 1 se desplegaron el Landing Page, en GitHub Pages, y los Web Services, en Render, con la base de datos PostgreSQL en Neon. Las aplicaciones móviles no forman parte del despliegue de este Sprint. Los pasos de configuración están descritos en la sección 4.1.4.

| Producto | Plataforma | Estado en el Sprint 1 | URL |
| --- | --- | --- | --- |
| Landing Page | GitHub Pages (GitHub Actions) | Desplegado | https://vitahealth-upc.github.io/landing-page/ |
| Web Services | Render (Web Service con Docker, plan Free; rama `develop`) | Desplegado | https://web-services-yzxl.onrender.com |
| Base de datos | Neon (PostgreSQL 16, proyecto TATA, branch `production`, base `tata`) | Desplegada | (conexión privada) |

**Landing Page: GitHub Pages**

El repositorio `landing-page` incluye el workflow `.github/workflows/pages.yml` (*Deploy landing page to GitHub Pages*). Se ejecuta con cada push a `develop` o `main` y manualmente. Hace el checkout del repositorio, configura Pages, sube el sitio estático y lo publica con `actions/deploy-pages`. En *Settings → Pages* la fuente de compilación es *GitHub Actions* y la opción *Enforce HTTPS* está activa.

![GitHub Pages del repositorio landing-page: sitio publicado con GitHub Actions como fuente y HTTPS forzado.](assets/githubPageEvidence.png)

*Figura 1. GitHub Pages del repositorio `landing-page`: sitio publicado con GitHub Actions como fuente y HTTPS forzado.*

![Landing Page publicada en https://vitahealth-upc.github.io/landing-page/.](assets/landingPageEvidence.png)

*Figura 2. Landing Page publicada en https://vitahealth-upc.github.io/landing-page/.*

**Base de datos: Neon**

Se creó el proyecto TATA en Neon con el plan Free, en la región AWS US East 2 (Ohio), con el branch `production` y la base `tata`. La cadena de conexión se obtuvo desde *Connect*, con *connection pooling* activo y el rol `tata_owner`. La contraseña no se publica.

![Neon: resumen del proyecto TATA, branch production.](assets/deployment-evidence/neon-proyecto.png)

*Figura 3. Neon: resumen del proyecto TATA, branch `production`.*

![Neon: cadena de conexión con la contraseña oculta.](assets/deployment-evidence/neon-connect.png)

*Figura 4. Neon: cadena de conexión con la contraseña oculta.*

**Web Services: Render**

Se creó un Web Service enlazado al repositorio `vitaHealth-UPC/web-services`, rama `develop`, con entorno Docker (el `Dockerfile` está en la raíz) y plan Free. La conexión a la base de datos se configura con las variables de entorno `SPRING_DATASOURCE_URL` (`jdbc:postgresql://<host>.neon.tech:5432/tata?sslmode=require`), `SPRING_DATASOURCE_USERNAME` y `SPRING_DATASOURCE_PASSWORD`, de modo que ningún secreto se versiona. En producción las tablas se crean al arrancar con `spring.jpa.hibernate.ddl-auto=update`.

![Render: variables de entorno del servicio con los valores ocultos.](assets/deployment-evidence/render-env.png)

*Figura 5. Render: variables de entorno del servicio con los valores ocultos.*

El despliegue manual terminó con *Deploy succeeded* y el servicio quedó en estado *Live*.

![Render: despliegue exitoso y servicio en estado Live.](assets/deployment-evidence/render-deploy.png)

*Figura 6. Render: despliegue exitoso y servicio en estado Live.*

**Verificación**

`GET /health` responde `{"status":"UP"}` y Swagger UI queda disponible en la URL pública. El plan Free de Render suspende la instancia por inactividad, por lo que la primera petición puede tardar en responder.

![Verificación de GET /health en la URL pública.](assets/deployment-evidence/health.png)

*Figura 7. Verificación de `GET /health` en la URL pública.*

![Swagger UI en la URL pública del backend.](assets/deployment-evidence/swagger-desplegado.png)

*Figura 8. Swagger UI en la URL pública del backend.*

**Commits de despliegue del Sprint**

| Repository | Branch | Commit Id | Commit Message | Commit Message Body | Commited on (Date) |
| --- | --- | --- | --- | --- | --- |
| `vitaHealth-UPC/web-services` | `develop` | `67511a1` | `chore(deploy): add Docker packaging, health and DATABASE_URL mapping Prepare the Spring Boot API so Railway can build and run it.` | — | 07/10/2026 |
| `vitaHealth-UPC/web-services` | `develop` | `7582274` | `fix(deploy): use published Temurin 26 Docker base images` | — | 07/10/2026 |
| `vitaHealth-UPC/web-services` | `develop` | `aebd362` | `fix(deploy): map DATABASE_URL into Spring datasource for Neon/Render` | — | 07/10/2026 |
| `vitaHealth-UPC/landing-page` | `develop` | `01ef128` | `ci: add GitHub Pages preview from develop` | — | 02/10/2026 |


#### 4.2.1.9. Team Collaboration Insights during Sprint

Durante el Sprint 1 el equipo trabajó en cuatro repositorios de la organización `vitaHealth-UPC` (Landing Page, Web Services, aplicación Android e informe), aplicando el flujo GitFlow descrito en la sección 4.1.2. Cada User Story o Technical Story se desarrolló en su propia rama de feature, nombrada con el identificador de la historia (por ejemplo, `feature/ts-12-inventory-replenishment-api`, `feature/us-40-initial-inventory` y `feature/us-46-header-hero`), y se integró a `develop` mediante Pull Request. Los mensajes de commit siguen Conventional Commits, con el Bounded Context o la historia como scope (por ejemplo, `feat(inventory): add quantity and reorder threshold value objects` o `feat(us-19): reopen existing treatments`), lo que permite trazar cada cambio hacia la historia que lo originó.

Las cifras corresponden a la rama `develop` de cada repositorio al cierre del Sprint 1 (7 de octubre de 2026).

| Repositorio | Producto | Ramas de feature | Pull Requests integrados a `develop` | Commits en `develop` (sin merges) |
| --- | --- | --- | --- | --- |
| [landing-page](https://github.com/vitaHealth-UPC/landing-page) | Landing Page | 7 | 2 | 40 |
| [web-services](https://github.com/vitaHealth-UPC/web-services) | Web Services | 14 (+3 de corrección) | 19 | 83 |
| [mobile-android](https://github.com/vitaHealth-UPC/mobile-android) | Aplicación Android | 48 (33 con trabajo, +2 de corrección) | 14 | 93 |

**Commits por integrante (rama `develop`, sin contar merges)**

| Integrante | landing-page | web-services | mobile-android | Total |
| --- | --- | --- | --- | --- |
| Morales Venegas, David Joel | 40 | 32 | 61 | 133 |
| Velasquez Laquihuanaco, Eduardo David | 0 | 30 | 6 | 36 |
| Cabrera Novoa, Leonardo Moises | 0 | 12 | 17 | 29 |
| Diaz Yurivilca, Sofía | 0 | 3 | 9 | 12 |
| Alfaro Mallma, Alberto Joaquín | 0 | 1 | 0 | 1 |
| Joseph Salazar | 0 | 5 | 0 | 5 |

**Interpretación de los analíticos**

- **Landing Page.** El Landing Page se construyó en una sola jornada (2 de octubre), en siete ramas de feature, una por bloque de User Stories (US-46 a US-50), integradas y publicadas en GitHub Pages ese mismo día.
- **Web Services.** El backend concentra el mayor número de Pull Requests (19). David Morales lideró la arquitectura y la integración de los Bounded Contexts; Eduardo Velásquez implementó Accessibility & Preferences y las consultas de medicamentos y tratamientos; Leonardo Cabrera implementó Inventory & Replenishment (TS-12); Sofía Díaz las vistas de Adherence Analytics; y Joseph Salazar la configuración de despliegue (Docker, health check y conexión a PostgreSQL).
- **Aplicación Android.** Se crearon 48 ramas, una por User Story del backlog. 33 tienen trabajo y 15 quedaron preparadas para historias de Sprints siguientes. Las historias de inventario (US-40 a US-43) se trabajaron en una sola rama porque comparten la misma vista y el mismo módulo `:inventory`.
