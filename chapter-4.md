# Capítulo IV: Product Implementation & Validation

## 4. Product Implementation & Validation

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
 
#### Repositorios
 
| Producto | Repositorio | Contenido |
|---|---|---|
| Landing Page | https://github.com/vitaHealth-UPC/landing-page | Sitio estático (HTML5, CSS3, JavaScript), publicado en GitHub Pages |
| Web Services | https://github.com/vitaHealth-UPC/web-services | Proyecto del backend (RESTful API), pruebas unitarias y pruebas de integración/aceptación (archivos `.feature`) |
| Mobile Application | https://github.com/vitaHealth-UPC/mobile-android | App Tata en Kotlin (Android) |
| Frontend Web Application | `https://github.com/<org>/<web-app>` | Aplicación web (si aplica a su alcance) |
 
#### GitFlow Workflow
 
Se trabaja con dos ramas de vida larga y tres tipos de ramas de apoyo.
 
##### Ramas permanentes
 
- **`main`**: contiene únicamente código estable y listo para producción. Cada merge a `main` corresponde a un release y se etiqueta con su versión.
- **`develop`**: rama de integración. Recibe todas las features terminadas y es la base de los release branches.
##### Ramas de apoyo
 
###### Feature branches
 
- Se crean desde `develop` y se fusionan de vuelta a `develop` mediante Pull Request.
- Convención: `feature/<descripcion-corta-en-kebab-case>`
- Ejemplos: `feature/medication-reminders`, `feature/user-login`, `feature/caregiver-linking`
- Se eliminan después del merge.
###### Release branches
 
- Se crean desde `develop` cuando el conjunto de features del sprint está completo. Solo admiten correcciones menores, ajustes de versión y documentación.
- Convención: `release/<MAJOR.MINOR.PATCH>`, por ejemplo `release/1.0.0`
- Se fusionan a `main` (con tag `vX.Y.Z`) y de vuelta a `develop`.
###### Hotfix branches
 
- Se crean desde `main` para corregir errores críticos detectados en producción.
- Convención: `hotfix/<MAJOR.MINOR.PATCH>` con el siguiente PATCH, por ejemplo `hotfix/1.0.1`
- Se fusionan a `main` (con nuevo tag) y a `develop`.
##### Reglas de colaboración
 
- No se hace push directo a `main` ni a `develop`; todo cambio entra por Pull Request con al menos una revisión de otro integrante.
- Las ramas de feature se actualizan desde `develop` antes de abrir el PR para minimizar conflictos.
#### Semantic Versioning 2.0.0
 
Los releases siguen el formato `MAJOR.MINOR.PATCH`:
 
- **MAJOR**: cambios incompatibles con versiones anteriores (por ejemplo, cambios que rompen la API).
- **MINOR**: nueva funcionalidad compatible hacia atrás.
- **PATCH**: corrección de errores compatible hacia atrás.
Los tags se nombran `v1.0.0`, `v1.1.0`, `v1.1.1`. Las versiones previas a producción pueden usar sufijos como `v0.1.0` o `v1.0.0-beta.1`.
 
#### Conventional Commits
 
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
#### Evidencia de commits
 
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
