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
#### 4.2.1.2. Aspect Leaders and Collaborators
#### 4.2.1.3. Sprint Backlog 1
#### 4.2.1.4. Development Evidence for Sprint Review
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
#### 4.2.1.8. Software Deployment Evidence for Sprint Review
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
