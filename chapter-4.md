# Capítulo IV: Product Implementation & Validation

## 4.1. Software Configuration Management

### 4.1.1. Software Development Environment Configuration

El equipo utiliza herramientas de planificación, diseño, desarrollo y despliegue para la landing, los servicios web y la aplicación Android.

| Actividad | Herramientas | Uso |
| --- | --- | --- |
| Planificación | Trello y GitHub | Historias, tareas y control de versiones |
| Diseño | Figma, UXPressia y Miro | Interfaces y artefactos de diseño |
| Landing | WebStorm, HTML, CSS y JavaScript | Desarrollo del sitio responsive |
| Servicios web | IntelliJ IDEA, Java, Spring Boot y Maven | API REST y pruebas |
| Android | Android Studio, Kotlin, Compose y Gradle | Aplicación nativa y pruebas |
| Persistencia | PostgreSQL y Room | Datos del servicio y almacenamiento local |
| Integración y despliegue | GitHub Actions, Render, Neon y GitHub Pages | Compilación, pruebas y publicación |

Enlace a tablero:

https://trello.com/b/wuHmMypU/apps-moviles

Enlace a Figma:

https://www.figma.com/design/jCppvxtSpLpHOrC3ZWUIVC/VitaHealth

Enlace a Android Studio:

https://developer.android.com/studio

Enlace a Spring Boot:

https://spring.io/projects/spring-boot

### 4.1.2. Source Code Management

El equipo trabaja con GitFlow. Las historias se desarrollan en ramas feature, se revisan mediante Pull Requests y se integran en develop; las versiones estables se publican desde main con una etiqueta de release.

| Rama | Uso |
| --- | --- |
| main | Versiones estables |
| develop | Integración del trabajo |
| feature/ | Desarrollo de historias |
| fix/ | Correcciones |
| release/ | Preparación de versiones |
| hotfix/ | Correcciones de una versión publicada |

Los commits utilizan Conventional Commits, con tipo, alcance y descripción. Las releases siguen Semantic Versioning; v1.0.0 identifica la versión publicada de los productos.

**Landing Page**

<p align="center">
  <img src="assets/repository-evidence/landing-repository.png" alt="Repositorio de Landing Page en GitHub" width="960">
</p>

*Figura. Repositorio de Landing Page en GitHub.*

Enlace a repositorio:

https://github.com/vitaHealth-UPC/landing-page/tree/develop

**Web Services**

<p align="center">
  <img src="assets/repository-evidence/backend-repository.png" alt="Repositorio de Web Services en GitHub" width="960">
</p>

*Figura. Repositorio de Web Services en GitHub.*

Enlace a repositorio:

https://github.com/vitaHealth-UPC/web-services/tree/develop

**Aplicación Android**

<p align="center">
  <img src="assets/repository-evidence/android-repository.png" alt="Repositorio de Aplicación Android en GitHub" width="960">
</p>

*Figura. Repositorio de Aplicación Android en GitHub.*

Enlace a repositorio:

https://github.com/vitaHealth-UPC/mobile-android/tree/develop

### 4.1.3. Source Code Style Guide & Conventions

El código utiliza nombres en inglés y conceptos del dominio. Los textos de la interfaz se mantienen en recursos; el español es el idioma inicial y la función de idioma habilita la variante EN.

| Tecnología | Convenciones |
| --- | --- |
| HTML | Elementos semánticos, etiquetas y atributos en minúsculas |
| CSS | Clases descriptivas, variables de diseño y reglas responsive |
| JavaScript | lowerCamelCase, funciones breves y textos de interfaz separados |
| Java | Clases en PascalCase, métodos en lowerCamelCase y paquetes por bounded context y capa |
| Kotlin | Composables en PascalCase, estado en ViewModels y módulos por bounded context |
| SQL | Nombres consistentes y relaciones definidas mediante claves |
| Pruebas | Nombres que describen el comportamiento y resultado esperado |
| Git | Commits con tipo y alcance; Pull Requests con descripción y validación |

### 4.1.4. Software Deployment Configuration

GitHub Actions publica la landing en GitHub Pages. Render construye el backend desde su Dockerfile y utiliza PostgreSQL en Neon; Android recibe la URL del servicio mediante TATA_API_BASE_URL.

| Producto | Configuración |
| --- | --- |
| Landing | Workflow .github/workflows/pages.yml y publicación en GitHub Pages |
| Backend | Dockerfile, perfil prod, PORT y variables de conexión a PostgreSQL |
| Base de datos | Conexión administrada con credenciales en el entorno del servicio |
| Android | Compilación de APK con Gradle y API_BASE_URL en BuildConfig |

```powershell
.\gradlew.bat :app:assembleDebug -PTATA_API_BASE_URL=https://web-services-yzxl.onrender.com/
```

<p align="center">
  <img src="assets/software-architecture-deployment-diagram.svg" alt="Diagrama de despliegue de Tata" width="960">
</p>

*Figura. Diagrama de despliegue de Tata.*

Enlace a landing:

https://vitahealth-upc.github.io/landing-page/

Enlace a Swagger UI:

https://web-services-yzxl.onrender.com/swagger-ui/index.html

## 4.2. Landing Page & Mobile Application Implementation

### 4.2.1. Sprint 1

#### 4.2.1.1. Sprint Planning 1

Sprint 1 reúne el acceso y la vinculación familiar, la configuración del tratamiento, la próxima toma y la landing. El alcance comprende 25 historias y 81 Story Points.

| Campo | Detalle |
| --- | --- |
| **Sprint #** | Sprint 1 |
| **Sprint Planning Background** | |
| Date | 2026-09-28 (fecha propuesta para el cronograma del Sprint 1) |
| Time | 19:00, hora de Perú (horario propuesto) |
| Location | Reunión virtual (modalidad propuesta) |
| Prepared By | Diaz Yurivilca, Sofia |
| Attendees (to the meeting) | Quispe Pérez, Eder Edu / Diaz Yurivilca, Sofia / Morales Venegas, David Joel / Cabrera Novoa, Leonardo Moises / Alfaro Mallma, Joaquín Alberto / Velasquez Laquihuanaco, Eduardo David |
| **Sprint 0 Review Summary** | |
| Review | El antecedente del Sprint 1 comprende la definición del producto, requisitos y diseño de la solución. |
| Retrospective Summary | El equipo organiza el trabajo por historias y bounded contexts, con revisión de cambios mediante Pull Requests. |
| **Sprint Goal & User Stories** | |
| Sprint 1 Goal | Nuestro foco es ofrecer al familiar un recorrido desde conocer Tata hasta configurar el cuidado del adulto mayor. Esto facilita el acceso al producto y la organización de su medicación. El cumplimiento se evalúa mediante registro, vínculo con consentimiento, tratamiento y consulta de la próxima toma. |
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

La matriz distribuye el liderazgo y la colaboración en los aspectos del Sprint 1. L identifica al líder y C al colaborador.

| Integrante | GitHub Username | Landing y UI | Backend | Pruebas | Reporte | Integración y release |
| --- | --- | --- | --- | --- | --- | --- |
| Morales Venegas, David Joel | David-std2 | L | C | C | C | C |
| Velasquez Laquihuanaco, Eduardo David | lalo-dev8 | C | L | C | C | C |
| Cabrera Novoa, Leonardo Moises | u202415820 | C | C | C | C | C |
| Diaz Yurivilca, Sofía | u20241a195-cmd | C | C | L | C | C |
| Alfaro Mallma, Alberto Joaquín | elprrr / elperro123xd | C | C | C | L | C |
| Quispe Pérez, Eder Edu | DuDu-0912 | C | C | C | C | L |

#### 4.2.1.3. Sprint Backlog 1

El Sprint Backlog organiza las 25 historias de Sprint 1 en tareas de implementación y revisión. Las estimaciones expresan horas de trabajo para cada tarea.

<p align="center">
  <img src="assets/repository-evidence/sprint1-board.png" alt="Tablero de Trello con las historias de Sprint 1" width="960">
</p>

*Figura. Tablero de Trello con las historias de Sprint 1.*

Enlace a tablero:

https://trello.com/b/wuHmMypU/apps-moviles

| Historia | Título | Task ID | Tarea | Estimación (horas) | Responsable | Estado |
| --- | --- | --- | --- | --- | --- | --- |
| US-05 | Recordatorio de toma de medicamento | S1-T01 | Implementar vista, validaciones y consumo de API | 6 | David Morales | To-review |
| US-03 | Registro de un nuevo medicamento | S1-T02 | Implementar vista, validaciones y consumo de API | 10 | David Morales | To-review |
| US-02 | Vinculación con la cuenta del adulto mayor | S1-T03 | Implementar vista, validaciones y consumo de API | 10 | David Morales | To-review |
| US-14 | Creación de un tratamiento | S1-T04 | Implementar vista, validaciones y consumo de API | 6 | David Morales | To-review |
| US-15 | Definición de dosis y frecuencia | S1-T05 | Implementar vista, validaciones y consumo de API | 6 | David Morales | To-review |
| US-16 | Configuración de horarios e instrucciones | S1-T06 | Implementar vista, validaciones y consumo de API | 6 | David Morales | To-review |
| US-17 | Configuración de recordatorios | S1-T07 | Implementar vista, validaciones y consumo de API | 6 | David Morales | To-review |
| US-20 | Consulta de la próxima toma | S1-T08 | Implementar vista, validaciones y consumo de API | 4 | David Morales | To-review |
| US-46 | Consulta de la propuesta de valor de Tata | S1-T09 | Implementar sección, adaptación responsive e idioma | 4 | David Morales | Done |
| US-47 | Consulta de funcionalidades principales | S1-T10 | Implementar sección, adaptación responsive e idioma | 4 | David Morales | Done |
| US-49 | Continuación hacia registro o contacto | S1-T11 | Implementar sección, adaptación responsive e idioma | 4 | David Morales | Done |
| US-50 | Acceso adaptable al Landing Page | S1-T12 | Implementar sección, adaptación responsive e idioma | 6 | David Morales | Done |
| US-48 | Comparación de planes disponibles | S1-T13 | Implementar sección, adaptación responsive e idioma | 4 | David Morales | Done |
| US-10 | Registro de cuenta del familiar | S1-T14 | Implementar vista, validaciones y consumo de API | 6 | David Morales | To-review |
| US-11 | Verificación del correo del familiar | S1-T15 | Implementar vista, validaciones y consumo de API | 4 | David Morales | To-review |
| US-01 | Ingreso simplificado a la aplicación | S1-T16 | Implementar vista, validaciones y consumo de API | 6 | David Morales | To-review |
| US-12 | Registro del perfil del adulto mayor | S1-T17 | Implementar vista, validaciones y consumo de API | 6 | David Morales | To-review |
| US-13 | Consentimiento para establecer el vínculo | S1-T18 | Implementar vista, validaciones y consumo de API | 6 | David Morales | To-review |
| TS-03 | API de medicamentos y tratamientos | S1-T19 | Implementar contrato y pruebas del servicio | 10 | Eduardo Velasquez | Done |
| TS-08 | Servicio de generación de agenda de tomas | S1-T20 | Implementar contrato y pruebas del servicio | 10 | Eduardo Velasquez | Done |
| TS-02 | API de vinculación de cuidado | S1-T21 | Implementar contrato y pruebas del servicio | 10 | Eduardo Velasquez | Done |
| TS-07 | API de cuenta y sesión del familiar | S1-T22 | Implementar contrato y pruebas del servicio | 10 | Eduardo Velasquez | Done |
| TS-01 | Servicio de autenticación mediante PIN | S1-T23 | Implementar contrato y pruebas del servicio | 6 | Eduardo Velasquez | Done |
| SP-01 | Investigación de reconocimiento de voz | S1-T24 | Revisar APIs Android y documentar el enfoque | 6 | Leonardo Cabrera | To-review |
| SP-03 | Investigación de ejecución en segundo plano | S1-T25 | Revisar APIs Android y documentar el enfoque | 6 | Leonardo Cabrera | To-review |

#### 4.2.1.4. Development Evidence for Sprint Review

La landing, el backend y Android se desarrollan en sus repositorios y se integran mediante Pull Requests. Los commits muestran la implementación y los ajustes de las historias.

| Repository | Branch | Commit Id | Commit Message | Commit Message Body | Committed on (Date) |
| --- | --- | --- | --- | --- | --- |
| `vitaHealth-UPC/landing-page` | `feature/pricing-support` | `f1c6d8e` | `feat: localize pricing and support` | - | 02/10/2026 |
| `vitaHealth-UPC/landing-page` | `develop` | `82d1449` | `feat: implement pricing and support` | * feat: add Figma assets for pricing and support | 02/10/2026 |
| `vitaHealth-UPC/landing-page` | `feature/cta-footer` | `f3fda48` | `feat: add Figma assets for CTA and footer` | - | 02/10/2026 |
| `vitaHealth-UPC/landing-page` | `develop` | `b43b5b3` | `feat: implement pricing and support` | * feat: add Figma assets for pricing and support | 02/10/2026 |
| `vitaHealth-UPC/landing-page` | `develop` | `8121db2` | `feat: align English and mobile landing variants with Figma` | * feat: add English and mobile Figma assets | 02/10/2026 |
| `vitaHealth-UPC/web-services` | `develop` | `e4b7f33` | `feat: list medications and treatments, expose medication lookup and document with OpenAPI` | - | 06/10/2026 |
| `vitaHealth-UPC/web-services` | `develop` | `a20c0ba` | `feat: respect the voice confirmation preference when confirming by voice` | - | 06/10/2026 |
| `vitaHealth-UPC/web-services` | `develop` | `8604122` | `feat: publish adherence patterns and consolidate weekly on a schedule` | - | 06/10/2026 |
| `vitaHealth-UPC/web-services` | `develop` | `e8b4039` | `feat: show low stock and adherence insights in the older adult status` | - | 06/10/2026 |
| `vitaHealth-UPC/web-services` | `feature/ts-10-adherence-frontend-views` | `f362d4c` | `feat(analytics): add adherence summary and insights views for the family app` | - | 06/10/2026 |
| `vitaHealth-UPC/mobile-android` | `feature/ts-10-adherence-entry-point` | `84c8ee7` | `feat(analytics): show recent intakes classified as on time, late or omitted` | - | 06/10/2026 |
| `vitaHealth-UPC/mobile-android` | `feature/ts-10-adherence-entry-point` | `73ea0e4` | `feat(analytics): show detected omission pattern card linked to recommendations` | - | 06/10/2026 |
| `vitaHealth-UPC/mobile-android` | `feature/ts-10-adherence-entry-point` | `22b494f` | `feat(analytics): connect the adherence screens to the backend endpoints` | - | 06/10/2026 |
| `vitaHealth-UPC/mobile-android` | `feature/ts-10-adherence-entry-point` | `b3a71dc` | `feat(app): open the adherence history from the family summary` | - | 07/10/2026 |
| `vitaHealth-UPC/mobile-android` | `feature/ts-10-adherence-entry-point` | `ec5b326` | `feat(analytics): show the caregiver tab bar in the adherence screens` | - | 07/10/2026 |

<p align="center">
  <img src="assets/repository-evidence/landing-commits.png" alt="Historial de commits de landing-page" width="960">
</p>

*Figura. Historial de commits de landing-page.*

Enlace a commits:

https://github.com/vitaHealth-UPC/landing-page/commits/develop/

<p align="center">
  <img src="assets/repository-evidence/backend-commits.png" alt="Historial de commits de web-services" width="960">
</p>

*Figura. Historial de commits de web-services.*

Enlace a commits:

https://github.com/vitaHealth-UPC/web-services/commits/develop/

<p align="center">
  <img src="assets/repository-evidence/android-commits.png" alt="Historial de commits de mobile-android" width="960">
</p>

*Figura. Historial de commits de mobile-android.*

Enlace a commits:

https://github.com/vitaHealth-UPC/mobile-android/commits/develop/

#### 4.2.1.5. Testing Suite Evidence for Sprint Review

El backend utiliza JUnit y pruebas de integración con Spring Boot y MockMvc. Android incorpora pruebas unitarias y pruebas instrumentadas de Compose; la ejecución visual en el emulador registra 21 pruebas, sin fallos ni errores.

| Prueba | Historias | Comportamiento |
| --- | --- | --- |
| AccountTest y PinCredentialTest | US-01, US-10, US-11 | Cuenta, credenciales y PIN |
| CareLinkTest | US-02, US-13 | Solicitud y consentimiento del vínculo |
| TreatmentTest y TreatmentAuthorizationTest | US-14 a US-19 | Pauta, activación, pausa y autorización |
| GenerateIntakesCommandHandlerTest | TS-08, US-20 | Generación de tomas programadas |
| IntakeAgendaIntegrationTest | US-24 | Orden, rango temporal y aislamiento por adulto mayor |
| IntakeConfirmationIntegrationTest | US-06 | Confirmación de tomas y resultados de la API |
| InventoryControllerTest e IntakeInventoryIntegrationTest | US-40 a US-43 | Stock y reposición |
| ExistingScreensVisualAuditTest | Vistas Android | Estados, idioma, navegación y capturas de componentes |

Enlace a pruebas del backend:

https://github.com/vitaHealth-UPC/web-services/tree/develop/src/test

Enlace a pruebas Android:

https://github.com/vitaHealth-UPC/mobile-android/tree/develop/app/src

Enlace a pruebas instrumentadas:

https://github.com/vitaHealth-UPC/mobile-android/blob/develop/app/src/androidTest/kotlin/com/vitahealth/tata/ExistingScreensVisualAuditTest.kt

**Prueba de tratamiento**

```java
@Test
void incompleteTreatmentCannotActivate() {
    var treatment = Treatment.create("adult-1", "Control de presión",
        Instant.parse("2026-10-05T12:00:00Z"));
    assertEquals(TreatmentStatus.DRAFT, treatment.status());
    assertThrows(IllegalStateException.class, treatment::activate);
}
```

Enlace a TreatmentTest:

https://github.com/vitaHealth-UPC/web-services/blob/develop/src/test/java/com/tata/treatmentmanagement/domain/model/aggregates/TreatmentTest.java

| Repositorio | Commit | Avance en pruebas | Fecha |
| --- | --- | --- | --- |
| web-services | 7618f5e | Sesiones, consentimiento y autorización | 07/10/2026 |
| mobile-android | 686eebb | Inicio de sesión e idioma en pruebas instrumentadas | 07/10/2026 |

<p align="center">
  <img src="assets/repository-evidence/backend-ci.png" alt="Backend CI con ejecución exitosa" width="960">
</p>

*Figura. Backend CI con ejecución exitosa.*

Enlace a ejecución:

https://github.com/vitaHealth-UPC/web-services/actions/runs/37647569632

<p align="center">
  <img src="assets/repository-evidence/android-ci.png" alt="Android CI con ejecución exitosa" width="960">
</p>

*Figura. Android CI con ejecución exitosa.*

Enlace a ejecución:

https://github.com/vitaHealth-UPC/mobile-android/actions/runs/37727256292

#### 4.2.1.6. Execution Evidence for Sprint Review

La landing presenta la propuesta, funcionalidades, planes y contacto. Android reúne las vistas de acceso, tratamiento y seguimiento; las siguientes capturas muestran su ejecución en el emulador con datos de prueba.

Enlace a landing:

https://vitahealth-upc.github.io/landing-page/

<p align="center">
  <img src="assets/execution-evidence/landing-hero.png" alt="Encabezado y propuesta de valor" width="960">
</p>

*Figura. Encabezado y propuesta de valor.*

<p align="center">
  <img src="assets/execution-evidence/landing-value-features.png" alt="Funcionalidades de Tata" width="960">
</p>

*Figura. Funcionalidades de Tata.*

<p align="center">
  <img src="assets/execution-evidence/landing-app-how.png" alt="Presentación de la aplicación y pasos de uso" width="960">
</p>

*Figura. Presentación de la aplicación y pasos de uso.*

<p align="center">
  <img src="assets/execution-evidence/landing-testimonial-about.png" alt="Testimonio e historia del producto" width="960">
</p>

*Figura. Testimonio e historia del producto.*

<p align="center">
  <img src="assets/execution-evidence/landing-plans-faq.png" alt="Planes y soporte" width="960">
</p>

*Figura. Planes y soporte.*

<p align="center">
  <img src="assets/execution-evidence/landing-cta-footer.png" alt="Contacto y pie de página" width="960">
</p>

*Figura. Contacto y pie de página.*

<p align="center">
  <img src="assets/execution-evidence/landing-mobile.png" alt="Landing en formato móvil" width="480">
</p>

*Figura. Landing en formato móvil.*

<p align="center">
  <img src="assets/execution-evidence/android-access.png" alt="Acceso, registro y vinculación en Android" width="960">
</p>

*Figura. Acceso, registro y vinculación en Android.*

<p align="center">
  <img src="assets/execution-evidence/android-treatment.png" alt="Medicamento, tratamiento e inventario en Android" width="960">
</p>

*Figura. Medicamento, tratamiento e inventario en Android.*

<p align="center">
  <img src="assets/execution-evidence/android-followup.png" alt="Resumen familiar, adherencia y notificaciones en Android" width="960">
</p>

*Figura. Resumen familiar, adherencia y notificaciones en Android.*

**Video de ejecución**

<p align="center">
  <a href="https://upcedupe-my.sharepoint.com/:v:/g/personal/u202415820_upc_edu_pe/IQCB84CBuGz_T5NngWc1a80SAdKHBcArMUcdP7DEkmu17-M?nav=eyJyZWZlcnJhbEluZm8iOnsicmVmZXJyYWxBcHAiOiJPbmVEcml2ZUZvckJ1c2luZXNzIiwicmVmZXJyYWxBcHBQbGF0Zm9ybSI6IldlYiIsInJlZmVycmFsTW9kZSI6InZpZXciLCJyZWZlcnJhbFZpZXciOiJNeUZpbGVzTGlua0NvcHkifX0&e=N23NX3">
    <img src="assets/execution-evidence/video-ejecucion.png" alt="Video de ejecución del Sprint 1" width="720">
  </a>
</p>

*Figura. Video de ejecución del Sprint 1: recorrido por el Landing Page desplegado y las vistas de la aplicación Android conectadas al backend en Render.*

Enlace a video: [Video de ejecución del Sprint 1](https://upcedupe-my.sharepoint.com/:v:/g/personal/u202415820_upc_edu_pe/IQCB84CBuGz_T5NngWc1a80SAdKHBcArMUcdP7DEkmu17-M?nav=eyJyZWZlcnJhbEluZm8iOnsicmVmZXJyYWxBcHAiOiJPbmVEcml2ZUZvckJ1c2luZXNzIiwicmVmZXJyYWxBcHBQbGF0Zm9ybSI6IldlYiIsInJlZmVycmFsTW9kZSI6InZpZXciLCJyZWZlcnJhbFZpZXciOiJNeUZpbGVzTGlua0NvcHkifX0&e=N23NX3) (duración: 5:25).

#### 4.2.1.7. Services Documentation Evidence for Sprint Review

En este Sprint documentamos el backend con OpenAPI y lo publicamos junto con los Web Services en Swagger UI. En total son 64 operaciones: 62 de los Bounded Contexts Identity & Subscription, Care Link, Treatment Management, Intake Execution, Family Monitoring, Adherence Analytics, Inventory & Replenishment y Accessibility & Preferences, y 2 de estado del servicio. Omission & Escalation no tiene endpoints REST, así que no aparece. Algunos endpoints pertenecen a historias que el Product Backlog asigna a sprints posteriores, pero ya estaban implementados al cerrar el Sprint 1 y por eso se documentaron aquí. Todas las llamadas llevan el encabezado `Authorization: Bearer <token>`, menos las que la tabla marca como públicas; sin el token responden `401 AUTHENTICATION_REQUIRED`. Los ejemplos de respuesta de la tabla son respuestas reales del backend desplegado, que obtuvimos con la cuenta de demostración. Tres ejemplos los armamos con la misma estructura de la respuesta real, porque no se pueden ejecutar con esa cuenta: la verificación del correo (necesita el código que todavía no se envía), la confirmación por voz (necesita el proveedor de voz) y el cambio de plan. Los endpoints de adherencia devuelven listas vacías o `204` porque la cuenta demo aún no tiene tomas pasadas.

Repositorio de Web Services: https://github.com/vitaHealth-UPC/web-services

Documentación desplegada: https://web-services-yzxl.onrender.com/swagger-ui/index.html

**Treatment Management**

| Endpoint | Acción | Verbo HTTP | Sintaxis de llamada | Parámetros | Ejemplo de response | Explicación del response | Documentación |
| --- | --- | --- | --- | --- | --- | --- | --- |
| `/api/v1/older-adults/{olderAdultId}/treatments` | Crear un tratamiento (US-14) | POST | `POST /api/v1/older-adults/{olderAdultId}/treatments` | Path: `olderAdultId`.<br>Body: `caregiverId`, `name`. | `201` `{"id":"3f6c1d0e-8a52-4f0b-9c55-2f1f4d9a7b10","olderAdultId":"00000000-0000-0000-0000-000000000001","name":"Control de presión","status":"DRAFT","medicationId":null,"dose":null,"frequency":null,"scheduledTimes":null,"instructions":null,"reminderLeadMinutes":null}` | Crea el tratamiento en estado `DRAFT`, sin pauta. `400` si falta un dato; 403 si el cuidador no tiene un vínculo de cuidado activo con el adulto mayor. | https://web-services-yzxl.onrender.com/swagger-ui/index.html · Treatments |
| `/api/v1/older-adults/{olderAdultId}/treatments` | Listar los tratamientos de un adulto mayor (US-19) | GET | `GET /api/v1/older-adults/{olderAdultId}/treatments?caregiverId={caregiverId}` | Path: `olderAdultId`.<br>Query: `caregiverId`. | `200` `[{"id":"3f6c1d0e-8a52-4f0b-9c55-2f1f4d9a7b10","olderAdultId":"00000000-0000-0000-0000-000000000001","name":"Control de presión","status":"DRAFT","medicationId":null,"dose":null,"frequency":null,"scheduledTimes":null,"instructions":null,"reminderLeadMinutes":null}]` | Devuelve la lista, del más antiguo al más reciente; vacía si no hay tratamientos. 403 si el cuidador no tiene un vínculo de cuidado activo con el adulto mayor. | https://web-services-yzxl.onrender.com/swagger-ui/index.html · Treatments |
| `/api/v1/treatments/{treatmentId}/regimen` | Configurar dosis, frecuencia, horarios, instrucciones y recordatorio (US-15, US-16, US-17) | PUT | `PUT /api/v1/treatments/{treatmentId}/regimen` | Path: `treatmentId`.<br>Body: `caregiverId`, `medicationId`, `dose`, `frequency`, `scheduledTimes` (al menos un horario), `instructions`, `reminderLeadMinutes` (0 a 1440). | `200` `{"id":"3f6c1d0e-8a52-4f0b-9c55-2f1f4d9a7b10","olderAdultId":"00000000-0000-0000-0000-000000000001","name":"Control de presión","status":"DRAFT","medicationId":"7a1b2c3d-1111-4222-8333-444455556666","dose":"1 comprimido","frequency":"DAILY","scheduledTimes":["08:00:00","20:00:00"],"instructions":"Con un vaso de agua","reminderLeadMinutes":10}` | Devuelve el tratamiento con su pauta. `400` si la pauta es inválida; `404` si no existe el tratamiento o el medicamento; `409` si el medicamento está inactivo; 403 si el cuidador no tiene un vínculo de cuidado activo con el adulto mayor. | https://web-services-yzxl.onrender.com/swagger-ui/index.html · Treatments |
| `/api/v1/treatments/{treatmentId}/activation` | Activar un tratamiento (US-18) | POST | `POST /api/v1/treatments/{treatmentId}/activation?caregiverId={caregiverId}` | Path: `treatmentId`.<br>Query: `caregiverId`. | `200` `{"id":"3f6c1d0e-8a52-4f0b-9c55-2f1f4d9a7b10","olderAdultId":"00000000-0000-0000-0000-000000000001","name":"Control de presión","status":"ACTIVE","medicationId":"7a1b2c3d-1111-4222-8333-444455556666","dose":"1 comprimido","frequency":"DAILY","scheduledTimes":["08:00:00","20:00:00"],"instructions":"Con un vaso de agua","reminderLeadMinutes":10}` | El tratamiento pasa a `ACTIVE`. `409` si la pauta está incompleta o el medicamento está inactivo; `404` si no existe; 403 si el cuidador no tiene un vínculo de cuidado activo con el adulto mayor. | https://web-services-yzxl.onrender.com/swagger-ui/index.html · Treatments |
| `/api/v1/treatments/{treatmentId}/pause` | Pausar un tratamiento (US-18) | POST | `POST /api/v1/treatments/{treatmentId}/pause?caregiverId={caregiverId}` | Path: `treatmentId`.<br>Query: `caregiverId`. | `200` `{"id":"3f6c1d0e-8a52-4f0b-9c55-2f1f4d9a7b10","olderAdultId":"00000000-0000-0000-0000-000000000001","name":"Control de presión","status":"PAUSED","medicationId":"7a1b2c3d-1111-4222-8333-444455556666","dose":"1 comprimido","frequency":"DAILY","scheduledTimes":["08:00:00","20:00:00"],"instructions":"Con un vaso de agua","reminderLeadMinutes":10}` | El tratamiento pasa a `PAUSED` y conserva la pauta y el historial. `409` si no estaba activo; `404` si no existe; 403 si el cuidador no tiene un vínculo de cuidado activo con el adulto mayor. | https://web-services-yzxl.onrender.com/swagger-ui/index.html · Treatments |
| `/api/v1/treatments/{treatmentId}/resume` | Reanudar un tratamiento pausado | POST | `POST /api/v1/treatments/{treatmentId}/resume?caregiverId={caregiverId}` | Path: `treatmentId`.<br>Query: `caregiverId`. | `200` `{"id":"3f6c1d0e-8a52-4f0b-9c55-2f1f4d9a7b10","olderAdultId":"00000000-0000-0000-0000-000000000001","name":"Control de presión","status":"ACTIVE","medicationId":"7a1b2c3d-1111-4222-8333-444455556666","dose":"1 comprimido","frequency":"DAILY","scheduledTimes":["08:00:00","20:00:00"],"instructions":"Con un vaso de agua","reminderLeadMinutes":10}` | El tratamiento vuelve a `ACTIVE`. `409` si no estaba pausado o su medicamento está inactivo; `404` si no existe; 403 si el cuidador no tiene un vínculo de cuidado activo con el adulto mayor. | https://web-services-yzxl.onrender.com/swagger-ui/index.html · Treatments |
| `/api/v1/treatments/{treatmentId}` | Consultar el detalle de un tratamiento (US-19) | GET | `GET /api/v1/treatments/{treatmentId}?caregiverId={caregiverId}` | Path: `treatmentId`.<br>Query: `caregiverId`. | `200` `{"id":"3f6c1d0e-8a52-4f0b-9c55-2f1f4d9a7b10","olderAdultId":"00000000-0000-0000-0000-000000000001","name":"Control de presión","status":"ACTIVE","medicationId":"7a1b2c3d-1111-4222-8333-444455556666","dose":"1 comprimido","frequency":"DAILY","scheduledTimes":["08:00:00","20:00:00"],"instructions":"Con un vaso de agua","reminderLeadMinutes":10}` | Devuelve el tratamiento con su pauta; los campos de la pauta son `null` mientras esté incompleto. `404` si no existe; 403 si el cuidador no tiene un vínculo de cuidado activo con el adulto mayor. | https://web-services-yzxl.onrender.com/swagger-ui/index.html · Treatments |
| `/api/v1/older-adults/{olderAdultId}/medications` | Registrar un medicamento (US-03) | POST | `POST /api/v1/older-adults/{olderAdultId}/medications` | Path: `olderAdultId`.<br>Body: `caregiverId`, `name`, `presentation`. | `201` `{"id":"7a1b2c3d-1111-4222-8333-444455556666","olderAdultId":"00000000-0000-0000-0000-000000000001","name":"Losartán","presentation":"50 mg, tableta","active":true}` | Crea el medicamento activo del adulto mayor. `400` si falta un dato obligatorio; 403 si el cuidador no tiene un vínculo de cuidado activo con el adulto mayor. | https://web-services-yzxl.onrender.com/swagger-ui/index.html · Medications |
| `/api/v1/older-adults/{olderAdultId}/medications` | Listar los medicamentos de un adulto mayor (US-03) | GET | `GET /api/v1/older-adults/{olderAdultId}/medications?caregiverId={caregiverId}` | Path: `olderAdultId`.<br>Query: `caregiverId`. | `200` `[{"id":"7a1b2c3d-1111-4222-8333-444455556666","olderAdultId":"00000000-0000-0000-0000-000000000001","name":"Losartán","presentation":"50 mg, tableta","active":true}]` | Devuelve los medicamentos ordenados por nombre, incluidos los inactivos; vacía si no hay ninguno. 403 si el cuidador no tiene un vínculo de cuidado activo con el adulto mayor. | https://web-services-yzxl.onrender.com/swagger-ui/index.html · Medications |
| `/api/v1/medications/{medicationId}` | Editar un medicamento (US-04) | PUT | `PUT /api/v1/medications/{medicationId}` | Path: `medicationId`.<br>Body: `caregiverId`, `name`, `presentation`. | `200` `{"id":"7a1b2c3d-1111-4222-8333-444455556666","olderAdultId":"00000000-0000-0000-0000-000000000001","name":"Losartán","presentation":"100 mg, tableta","active":true}` | Cambia el nombre y la presentación; los tratamientos que lo usan republican su agenda. `400` si falta un dato; `404` si no existe; `409` si está inactivo; 403 si el cuidador no tiene un vínculo de cuidado activo con el adulto mayor. | https://web-services-yzxl.onrender.com/swagger-ui/index.html · Medications |
| `/api/v1/medications/{medicationId}/deactivation` | Desactivar un medicamento (US-04) | POST | `POST /api/v1/medications/{medicationId}/deactivation?caregiverId={caregiverId}` | Path: `medicationId`.<br>Query: `caregiverId`. | `200` `{"id":"7a1b2c3d-1111-4222-8333-444455556666","olderAdultId":"00000000-0000-0000-0000-000000000001","name":"Losartán","presentation":"50 mg, tableta","active":false}` | El medicamento queda inactivo y conserva su historial; un tratamiento activo que lo use se pausa. `404` si no existe; 403 si el cuidador no tiene un vínculo de cuidado activo con el adulto mayor. | https://web-services-yzxl.onrender.com/swagger-ui/index.html · Medications |
| `/api/v1/medications/{medicationId}` | Consultar el detalle de un medicamento | GET | `GET /api/v1/medications/{medicationId}?caregiverId={caregiverId}` | Path: `medicationId`.<br>Query: `caregiverId`. | `200` `{"id":"7a1b2c3d-1111-4222-8333-444455556666","olderAdultId":"00000000-0000-0000-0000-000000000001","name":"Losartán","presentation":"50 mg, tableta","active":true}` | Devuelve el medicamento. `404` si no existe; 403 si el cuidador no tiene un vínculo de cuidado activo con el adulto mayor. | https://web-services-yzxl.onrender.com/swagger-ui/index.html · Medications |

**Accessibility & Preferences**

| Endpoint | Acción | Verbo HTTP | Sintaxis de llamada | Parámetros | Ejemplo de response | Explicación del response | Documentación |
| --- | --- | --- | --- | --- | --- | --- | --- |
| `/api/v1/users/{userId}/preferences` | Consultar las preferencias de un usuario (US-35, US-36) | GET | `GET /api/v1/users/{userId}/preferences` | Path: `userId`. | `200` `{"userId":"00000000-0000-0000-0000-000000000001","textSize":"LARGE","highContrast":false,"reducedMotion":false,"readingAssistance":false,"voiceConfirmationEnabled":true,"quietHours":{"start":"22:00:00","end":"07:00:00"},"notificationChannels":[{"type":"PUSH","enabled":true},{"type":"SMS","enabled":false},{"type":"EMAIL","enabled":false}]}` | Devuelve las preferencias de accesibilidad y de notificación. Un usuario que nunca guardó nada recibe los valores por defecto, que se guardan en esa primera lectura. | https://web-services-yzxl.onrender.com/swagger-ui/index.html · Accessibility |
| `/api/v1/users/{userId}/preferences/text-size` | Cambiar el tamaño de texto (US-35) | PUT | `PUT /api/v1/users/{userId}/preferences/text-size` | Path: `userId`.<br>Body: `textSize` (`SMALL`, `MEDIUM`, `LARGE` o `EXTRA_LARGE`). | `200` `{"userId":"00000000-0000-0000-0000-000000000001","textSize":"LARGE","highContrast":false,"reducedMotion":false,"readingAssistance":false,"voiceConfirmationEnabled":true,"quietHours":{"start":"22:00:00","end":"07:00:00"},"notificationChannels":[{"type":"PUSH","enabled":true},{"type":"SMS","enabled":false},{"type":"EMAIL","enabled":false}]}` | Devuelve las preferencias actualizadas. Cada cambio se conserva para las próximas sesiones. `400` si el tamaño no es válido. | https://web-services-yzxl.onrender.com/swagger-ui/index.html · Accessibility |
| `/api/v1/users/{userId}/preferences/contrast` | Activar o desactivar el contraste reforzado (US-36) | PUT | `PUT /api/v1/users/{userId}/preferences/contrast` | Path: `userId`.<br>Body: `enabled` (booleano). | `200` `{"userId":"00000000-0000-0000-0000-000000000001","textSize":"LARGE","highContrast":true,"reducedMotion":false,"readingAssistance":false,"voiceConfirmationEnabled":true,"quietHours":{"start":"22:00:00","end":"07:00:00"},"notificationChannels":[{"type":"PUSH","enabled":true},{"type":"SMS","enabled":false},{"type":"EMAIL","enabled":false}]}` | Devuelve las preferencias actualizadas. Cada cambio se conserva para las próximas sesiones. | https://web-services-yzxl.onrender.com/swagger-ui/index.html · Accessibility |
| `/api/v1/users/{userId}/preferences/reduced-motion` | Activar o desactivar la reducción de movimiento (US-37) | PUT | `PUT /api/v1/users/{userId}/preferences/reduced-motion` | Path: `userId`.<br>Body: `enabled` (booleano). | `200` `{"userId":"00000000-0000-0000-0000-000000000001","textSize":"LARGE","highContrast":false,"reducedMotion":true,"readingAssistance":false,"voiceConfirmationEnabled":true,"quietHours":{"start":"22:00:00","end":"07:00:00"},"notificationChannels":[{"type":"PUSH","enabled":true},{"type":"SMS","enabled":false},{"type":"EMAIL","enabled":false}]}` | Devuelve las preferencias actualizadas. Cada cambio se conserva para las próximas sesiones. | https://web-services-yzxl.onrender.com/swagger-ui/index.html · Accessibility |
| `/api/v1/users/{userId}/preferences/reading-assistance` | Activar o desactivar la ayuda de lectura (US-38) | PUT | `PUT /api/v1/users/{userId}/preferences/reading-assistance` | Path: `userId`.<br>Body: `enabled` (booleano). | `200` `{"userId":"00000000-0000-0000-0000-000000000001","textSize":"LARGE","highContrast":false,"reducedMotion":false,"readingAssistance":true,"voiceConfirmationEnabled":true,"quietHours":{"start":"22:00:00","end":"07:00:00"},"notificationChannels":[{"type":"PUSH","enabled":true},{"type":"SMS","enabled":false},{"type":"EMAIL","enabled":false}]}` | Devuelve las preferencias actualizadas. Cada cambio se conserva para las próximas sesiones. | https://web-services-yzxl.onrender.com/swagger-ui/index.html · Accessibility |
| `/api/v1/users/{userId}/preferences/voice-confirmation` | Activar o desactivar la confirmación por voz (US-06) | PUT | `PUT /api/v1/users/{userId}/preferences/voice-confirmation` | Path: `userId`.<br>Body: `enabled` (booleano). | `200` `{"userId":"00000000-0000-0000-0000-000000000001","textSize":"LARGE","highContrast":false,"reducedMotion":false,"readingAssistance":false,"voiceConfirmationEnabled":false,"quietHours":{"start":"22:00:00","end":"07:00:00"},"notificationChannels":[{"type":"PUSH","enabled":true},{"type":"SMS","enabled":false},{"type":"EMAIL","enabled":false}]}` | Devuelve las preferencias actualizadas. Solo guarda la preferencia; el reconocimiento de voz pertenece a Intake Execution. | https://web-services-yzxl.onrender.com/swagger-ui/index.html · Accessibility |
| `/api/v1/users/{userId}/notification-preferences` | Configurar el horario de silencio y los canales de notificación (US-39) | PUT | `PUT /api/v1/users/{userId}/notification-preferences` | Path: `userId`.<br>Body: `quietHours` (`start` y `end`, o `null` para quitarlo), `channels` (lista de `type` y `enabled`; `PUSH`, `SMS` o `EMAIL`, sin repetir). | `200` `{"userId":"00000000-0000-0000-0000-000000000001","textSize":"LARGE","highContrast":false,"reducedMotion":false,"readingAssistance":false,"voiceConfirmationEnabled":true,"quietHours":{"start":"22:00:00","end":"07:00:00"},"notificationChannels":[{"type":"PUSH","enabled":true},{"type":"SMS","enabled":false},{"type":"EMAIL","enabled":false}]}` | Reemplaza ambos ajustes a la vez y devuelve las preferencias. El horario puede cruzar la medianoche. `400` si inicio y fin son iguales o se repite un canal. | https://web-services-yzxl.onrender.com/swagger-ui/index.html · Notification Preferences |

**Identity & Subscription**

| Endpoint | Acción | Verbo HTTP | Sintaxis de llamada | Parámetros | Ejemplo de response | Explicación del response | Documentación |
| --- | --- | --- | --- | --- | --- | --- | --- |
| `/api/v1/email-verification-requests` | Solicitar el código de verificación del correo | POST | `POST /api/v1/email-verification-requests` | Body: `email`. | `202` `{"id":"171efb94-a7d9-48b6-b968-73f09cdc7e31","name":"Ana Torres","email":"ana.torres.docs@tata.app","status":"PENDING_VERIFICATION","accessToken":null,"expiresAt":null}` | Solicita el envío del código de verificación; responde `202`. `400` si el correo falta o no es válido. No requiere token. | https://web-services-yzxl.onrender.com/swagger-ui/index.html · email-verification-requests-controller |
| `/api/v1/accounts` | Crear una cuenta | POST | `POST /api/v1/accounts` | Body: `name`, `email`, `password`. | `201` `{"id":"171efb94-a7d9-48b6-b968-73f09cdc7e31","name":"Ana Torres","email":"ana.torres.docs@tata.app","status":"PENDING_VERIFICATION","accessToken":null,"expiresAt":null}` | Crea la cuenta y devuelve sus datos y el token de acceso. `400` si faltan datos. No requiere token. | https://web-services-yzxl.onrender.com/swagger-ui/index.html · accounts-controller |
| `/api/v1/accounts/verification` | Verificar el correo con el código recibido | POST | `POST /api/v1/accounts/verification` | Body: `email`, `code`. | `200` `{"id":"171efb94-a7d9-48b6-b968-73f09cdc7e31","name":"Ana Torres","email":"ana.torres.docs@tata.app","status":"ACTIVE","accessToken":"0a1b2c3d-...","expiresAt":"2026-10-10T11:20:00Z"}` | Valida el código y devuelve los datos de la cuenta con el token de acceso. `401` si el código es inválido. No requiere token. | https://web-services-yzxl.onrender.com/swagger-ui/index.html · accounts-controller |
| `/api/v1/sessions` | Iniciar sesión de un cuidador o familiar | POST | `POST /api/v1/sessions` | Body: `email`, `password`. | `200` `{"accountId":"d3a10000-0000-4000-8000-000000000001","accessToken":"b646cff2-...","expiresAt":"2026-10-10T11:14:56.502817859Z"}` | Devuelve el `accessToken` y su vencimiento. `400` si faltan datos. No requiere token. | https://web-services-yzxl.onrender.com/swagger-ui/index.html · sessions-controller |
| `/api/v1/sessions/current` | Consultar la sesión actual | GET | `GET /api/v1/sessions/current` | Ninguno. | `200` `{"subjectId":"d3a10000-0000-4000-8000-000000000001","role":"CAREGIVER","expiresAt":"2026-10-10T11:14:56.502818Z","careLinkId":null,"name":"d3a10000-0000-4000-8000-000000000001"}` | Devuelve el sujeto de la sesión, su rol (`CAREGIVER` u otro), el vínculo de cuidado y el vencimiento. | https://web-services-yzxl.onrender.com/swagger-ui/index.html · session-lifecycle-controller |
| `/api/v1/sessions` | Cerrar la sesión | DELETE | `DELETE /api/v1/sessions` | Header: `Authorization`. | `204` Sin cuerpo | Invalida el token enviado en `Authorization`; responde `204` sin cuerpo. | https://web-services-yzxl.onrender.com/swagger-ui/index.html · session-lifecycle-controller |
| `/api/v1/pin-credentials` | Registrar el PIN de un adulto mayor | POST | `POST /api/v1/pin-credentials` | Body: `olderAdultId`, `pin`. | `201` Sin cuerpo | Guarda el PIN con el que el adulto mayor iniciará sesión; responde `201` sin cuerpo. | https://web-services-yzxl.onrender.com/swagger-ui/index.html · pin-credentials-controller |
| `/api/v1/pin-sessions` | Iniciar sesión de un adulto mayor con PIN | POST | `POST /api/v1/pin-sessions` | Body: `olderAdultId`, `pin`. | `200` `{"olderAdultId":"d3a10000-0000-4000-8000-000000000002","accessToken":"fb448982-...","expiresAt":"2026-10-10T11:15:00.089889817Z"}` | Devuelve el `accessToken` de la sesión del adulto mayor y su vencimiento. `400` si faltan datos. No requiere token. | https://web-services-yzxl.onrender.com/swagger-ui/index.html · pin-sessions-controller |
| `/api/v1/plans` | Listar los planes disponibles | GET | `GET /api/v1/plans` | Ninguno. | `200` `[{"code":"ESSENTIAL","name":"Esencial","monthlyPrice":9.90,"currency":"PEN","capabilities":["AGENDA","REMINDERS","INTAKE_CONFIRMATION"]},{"code":"FAMILY","name":"Familiar","monthlyPrice":19.90,"currency":"PEN","capabilities":["ADHERENCE_INSIGHTS","AGENDA","FAMILY_MONITORING","INTAKE_CONFIRMATION","REMINDERS","FAMILY_ALERTS"]}]` | Devuelve los planes con su precio mensual, moneda y capacidades. No requiere token. | https://web-services-yzxl.onrender.com/swagger-ui/index.html · Plans and subscriptions |
| `/api/v1/accounts/{accountId}/subscription` | Consultar la suscripción de una cuenta (US-44) | GET | `GET /api/v1/accounts/{accountId}/subscription` | Path: `accountId`. | `200` `{"accountId":"d3a10000-0000-4000-8000-000000000001","plan":{"code":"ESSENTIAL","name":"Esencial","monthlyPrice":9.90,"currency":"PEN","capabilities":["AGENDA","REMINDERS","INTAKE_CONFIRMATION"]},"status":"ACTIVE","renewsAt":null}` | Devuelve el plan vigente, el estado de la suscripción, la fecha de renovación y las capacidades habilitadas. | https://web-services-yzxl.onrender.com/swagger-ui/index.html · Plans and subscriptions |
| `/api/v1/accounts/{accountId}/subscription` | Activar o cambiar el plan de una cuenta (US-45) | PUT | `PUT /api/v1/accounts/{accountId}/subscription` | Path: `accountId`.<br>Body: `planCode`. | `200` `{"accountId":"d3a10000-0000-4000-8000-000000000001","plan":{"code":"FAMILY","name":"Familiar","monthlyPrice":19.90,"currency":"PEN","capabilities":["ADHERENCE_INSIGHTS","AGENDA","FAMILY_MONITORING","INTAKE_CONFIRMATION","REMINDERS","FAMILY_ALERTS"]},"status":"ACTIVE","renewsAt":"2026-11-09T12:00:00Z"}` | Aplica el plan indicado por `planCode` y devuelve la suscripción resultante. | https://web-services-yzxl.onrender.com/swagger-ui/index.html · Plans and subscriptions |

**Care Link**

| Endpoint | Acción | Verbo HTTP | Sintaxis de llamada | Parámetros | Ejemplo de response | Explicación del response | Documentación |
| --- | --- | --- | --- | --- | --- | --- | --- |
| `/api/v1/older-adults` | Registrar un adulto mayor | POST | `POST /api/v1/older-adults` | Body: `caregiverId`, `fullName`, `birthDate`, `emergencyContactName`, `emergencyContactRelationship`, `emergencyContactPhone`. | `201` `{"id":"b4dcad92-3ce9-41b4-a184-980fb819ea4e","registeredByCaregiverId":"d3a10000-0000-4000-8000-000000000001","fullName":"Carlos Mendoza","birthDate":"1950-03-02","emergencyContactName":"Lucía Mendoza","emergencyContactRelationship":"Hija","emergencyContactPhone":"+51 999 111 222","createdAt":"2026-10-09T23:15:42.388079448Z"}` | Crea el adulto mayor con su contacto de emergencia y devuelve sus datos; responde `201`. | https://web-services-yzxl.onrender.com/swagger-ui/index.html · older-adults-controller |
| `/api/v1/older-adults/{olderAdultId}` | Consultar los datos de un adulto mayor | GET | `GET /api/v1/older-adults/{olderAdultId}` | Path: `olderAdultId`. | `200` `{"id":"d3a10000-0000-4000-8000-000000000002","registeredByCaregiverId":"d3a10000-0000-4000-8000-000000000001","fullName":"Rosa Vargas","birthDate":"1948-05-12","emergencyContactName":"Diego Vargas","emergencyContactRelationship":"Son","emergencyContactPhone":"999888777","createdAt":"2026-10-09T11:23:14.137645Z"}` | Devuelve los datos del adulto mayor y de su contacto de emergencia. | https://web-services-yzxl.onrender.com/swagger-ui/index.html · older-adults-controller |
| `/api/v1/care-links/linking-codes` | Generar un código de vinculación | POST | `POST /api/v1/care-links/linking-codes` | Body: `caregiverId`, `olderAdultId`. | `201` `{"id":"73e804c9-7a0a-47a0-8f3f-c440c790c2e7","caregiverId":"d3a10000-0000-4000-8000-000000000001","olderAdultId":"b4dcad92-3ce9-41b4-a184-980fb819ea4e","status":"PENDING","linkingCode":"TATA-9620","codeExpiresAt":"2026-10-09T23:30:43.475096019Z","codeUsedAt":null,"consentGranted":false,"consentRecordedAt":null,"confirmedAt":null,"accessToken":null,"expiresAt":null}` | Crea un vínculo en estado `PENDING` con un código y su vencimiento; responde `201`. | https://web-services-yzxl.onrender.com/swagger-ui/index.html · care-links-controller |
| `/api/v1/care-links/acceptances` | Aceptar un código de vinculación | POST | `POST /api/v1/care-links/acceptances` | Body: `caregiverId`, `code`. | `200` `{"id":"73e804c9-7a0a-47a0-8f3f-c440c790c2e7","caregiverId":"d3a10000-0000-4000-8000-000000000001","olderAdultId":"b4dcad92-3ce9-41b4-a184-980fb819ea4e","status":"AWAITING_CONSENT","linkingCode":"TATA-9620","codeExpiresAt":"2026-10-09T23:30:43.475096Z","codeUsedAt":"2026-10-09T23:15:44.113778030Z","consentGranted":false,"consentRecordedAt":null,"confirmedAt":null,"accessToken":"1f760672-...","expiresAt":"2026-10-09T23:30:44.114526343Z"}` | Usa el código para asociar al cuidador con el vínculo y devuelve el vínculo actualizado. | https://web-services-yzxl.onrender.com/swagger-ui/index.html · care-links-controller |
| `/api/v1/care-links/{careLinkId}/consent` | Registrar el consentimiento del adulto mayor | POST | `POST /api/v1/care-links/{careLinkId}/consent` | Path: `careLinkId`.<br>Body: `accepted`. | `200` `{"id":"73e804c9-7a0a-47a0-8f3f-c440c790c2e7","caregiverId":"d3a10000-0000-4000-8000-000000000001","olderAdultId":"b4dcad92-3ce9-41b4-a184-980fb819ea4e","status":"CONFIRMED","linkingCode":"TATA-9620","codeExpiresAt":"2026-10-09T23:30:43.475096Z","codeUsedAt":"2026-10-09T23:15:44.113778Z","consentGranted":true,"consentRecordedAt":"2026-10-09T23:15:45.096617372Z","confirmedAt":"2026-10-09T23:15:45.096651403Z","accessToken":"caf137bd-...","expiresAt":"2026-10-10T11:15:45.454296317Z"}` | Guarda si el adulto mayor aceptó (`accepted`) y devuelve el vínculo con la fecha del consentimiento. | https://web-services-yzxl.onrender.com/swagger-ui/index.html · care-links-controller |
| `/api/v1/care-links` | Listar los vínculos confirmados de un cuidador | GET | `GET /api/v1/care-links?caregiverId={caregiverId}` | Query: `caregiverId`. | `200` `[{"id":"d3a10000-0000-4000-8000-000000000003","olderAdultId":"d3a10000-0000-4000-8000-000000000002","olderAdultName":"Rosa Vargas","confirmedAt":"2026-10-09T11:23:14.137645Z"}]` | Devuelve los vínculos activos con consentimiento, del más reciente al más antiguo; vacía si no hay ninguno. | https://web-services-yzxl.onrender.com/swagger-ui/index.html · care-links-controller |
| `/api/v1/care-links/{careLinkId}` | Consultar un vínculo de cuidado | GET | `GET /api/v1/care-links/{careLinkId}` | Path: `careLinkId`. | `200` `{"id":"73e804c9-7a0a-47a0-8f3f-c440c790c2e7","caregiverId":"d3a10000-0000-4000-8000-000000000001","olderAdultId":"b4dcad92-3ce9-41b4-a184-980fb819ea4e","status":"CONFIRMED","linkingCode":"TATA-9620","codeExpiresAt":"2026-10-09T23:30:43.475096Z","codeUsedAt":"2026-10-09T23:15:44.113778Z","consentGranted":true,"consentRecordedAt":"2026-10-09T23:15:45.096617Z","confirmedAt":"2026-10-09T23:15:45.096651Z","accessToken":null,"expiresAt":null}` | Devuelve el vínculo con su estado, código y consentimiento. | https://web-services-yzxl.onrender.com/swagger-ui/index.html · care-links-controller |
| `/api/v1/care-links/authorization` | Verificar si un cuidador está autorizado sobre un adulto mayor | GET | `GET /api/v1/care-links/authorization?caregiverId={caregiverId}&olderAdultId={olderAdultId}` | Query: `caregiverId`, `olderAdultId`. | `200` `true` | Devuelve `true` si existe un vínculo activo entre ambos y `false` en caso contrario. | https://web-services-yzxl.onrender.com/swagger-ui/index.html · care-links-controller |

**Intake Execution**

| Endpoint | Acción | Verbo HTTP | Sintaxis de llamada | Parámetros | Ejemplo de response | Explicación del response | Documentación |
| --- | --- | --- | --- | --- | --- | --- | --- |
| `/api/v1/older-adults/{olderAdultId}/intakes/next` | Consultar la próxima toma | GET | `GET /api/v1/older-adults/{olderAdultId}/intakes/next` | Path: `olderAdultId`. | `200` `{"id":"ed24bf3d-af04-4866-9d1a-49450670cb91","treatmentId":"a8809b8e-fafe-4d25-83d7-cc9529dc988e","medicationId":"f66da084-42d4-4faa-ba33-996027441d07","olderAdultId":"d3a10000-0000-4000-8000-000000000002","medicationName":"Losartán","dose":"1 comprimido","instructions":"Con un vaso de agua","scheduledAt":"2026-10-10T08:00:00Z","status":"PENDING","confirmedAt":null,"confirmationChannel":null,"alreadyConfirmed":false}` | Devuelve la próxima toma programada del adulto mayor. | https://web-services-yzxl.onrender.com/swagger-ui/index.html · intakes-controller |
| `/api/v1/older-adults/{olderAdultId}/intakes/agenda` | Consultar la agenda de tomas de un período | GET | `GET /api/v1/older-adults/{olderAdultId}/intakes/agenda?from={from}&to={to}` | Path: `olderAdultId`.<br>Query: `from`, `to`. | `200` `[{"id":"ed24bf3d-af04-4866-9d1a-49450670cb91","treatmentId":"a8809b8e-fafe-4d25-83d7-cc9529dc988e","medicationId":"f66da084-42d4-4faa-ba33-996027441d07","olderAdultId":"d3a10000-0000-4000-8000-000000000002","medicationName":"Losartán","dose":"1 comprimido","instructions":"Con un vaso de agua","scheduledAt":"2026-10-10T08:00:00Z","status":"PENDING","confirmedAt":null,"confirmationChannel":null,"alreadyConfirmed":false},{"id":"59ac9071-9827-4f35-9796-bcd17fcf38ec","treatmentId":"a8809b8e-fafe-4d25-83d7-cc9529dc988e","medicationId":"f66da084-42d4-4faa-ba33-996027441d07","olderAdultId":"d3a10000-0000-4000-8000-000000000002","medicationName":"Losartán","dose":"1 comprimido","instructions":"Con un vaso de agua","scheduledAt":"2026-10-10T20:00:00Z","status":"PENDING","confirmedAt":null,"confirmationChannel":null,"alreadyConfirmed":false},{"id":"09a16e35-2de1-4df0-92b9-7dabeaf96dfe","treatmentId":"a8809b8e-fafe-4d25-83d7-cc9529dc988e","medicationId":"f66da084-42d4-4faa-ba33-996027441d07","olderAdultId":"d3a10000-0000-4000-8000-000000000002","medicationName":"Losartán","dose":"1 comprimido","instructions":"Con un vaso de agua","scheduledAt":"2026-10-11T08:00:00Z","status":"PENDING","confirmedAt":null,"confirmationChannel":null,"alreadyConfirmed":false},{"id":"76ed82b9-29d5-434e-bb8b-7cc9f053ae65","treatmentId":"a8809b8e-fafe-4d25-83d7-cc9529dc988e","medicationId":"f66da084-42d4-4faa-ba33-996027441d07","olderAdultId":"d3a10000-0000-4000-8000-000000000002","medicationName":"Losartán","dose":"1 comprimido","instructions":"Con un vaso de agua","scheduledAt":"2026-10-11T20:00:00Z","status":"PENDING","confirmedAt":null,"confirmationChannel":null,"alreadyConfirmed":false}]` | Devuelve las tomas programadas entre `from` y `to`. | https://web-services-yzxl.onrender.com/swagger-ui/index.html · intakes-controller |
| `/api/v1/intakes/{intakeId}` | Consultar una toma | GET | `GET /api/v1/intakes/{intakeId}` | Path: `intakeId`. | `200` `{"id":"ed24bf3d-af04-4866-9d1a-49450670cb91","treatmentId":"a8809b8e-fafe-4d25-83d7-cc9529dc988e","medicationId":"f66da084-42d4-4faa-ba33-996027441d07","olderAdultId":"d3a10000-0000-4000-8000-000000000002","medicationName":"Losartán","dose":"1 comprimido","instructions":"Con un vaso de agua","scheduledAt":"2026-10-10T08:00:00Z","status":"PENDING","confirmedAt":null,"confirmationChannel":null,"alreadyConfirmed":false}` | Devuelve el medicamento, la dosis, las instrucciones, el horario y el estado de la toma. | https://web-services-yzxl.onrender.com/swagger-ui/index.html · intakes-controller |
| `/api/v1/intakes/{intakeId}/confirmation` | Confirmar una toma (US-05) | POST | `POST /api/v1/intakes/{intakeId}/confirmation` | Path: `intakeId`.<br>Body: `channel`. | `200` `{"id":"ed24bf3d-af04-4866-9d1a-49450670cb91","treatmentId":"a8809b8e-fafe-4d25-83d7-cc9529dc988e","medicationId":"f66da084-42d4-4faa-ba33-996027441d07","olderAdultId":"d3a10000-0000-4000-8000-000000000002","medicationName":"Losartán","dose":"1 comprimido","instructions":"Con un vaso de agua","scheduledAt":"2026-10-10T08:00:00Z","status":"CONFIRMED","confirmedAt":"2026-10-09T23:15:06.388841Z","confirmationChannel":"TOUCH","alreadyConfirmed":false}` | Registra la confirmación por el canal indicado (`TOUCH`) y devuelve la toma actualizada. | https://web-services-yzxl.onrender.com/swagger-ui/index.html · intakes-controller |
| `/api/v1/intakes/{intakeId}/voice-confirmation` | Confirmar una toma por voz (US-06) | POST | `POST /api/v1/intakes/{intakeId}/voice-confirmation?language={language}` | Path: `intakeId`.<br>Query: `language` (opcional).<br>Body: `audio`. | `200` `{"status":"CONFIRMED","transcript":"ya tomé mi pastilla","confidence":0.93,"intake":{"id":"ed24bf3d-af04-4866-9d1a-49450670cb91","treatmentId":"a8809b8e-fafe-4d25-83d7-cc9529dc988e","medicationId":"f66da084-42d4-4faa-ba33-996027441d07","olderAdultId":"d3a10000-0000-4000-8000-000000000002","medicationName":"Losartán","dose":"1 comprimido","instructions":"Con un vaso de agua","scheduledAt":"2026-10-10T08:00:00Z","status":"CONFIRMED","confirmedAt":"2026-10-09T23:15:06.388841Z","confirmationChannel":"TOUCH","alreadyConfirmed":false}}` | Procesa el audio con el servicio de reconocimiento de voz; solo una confirmación reconocida y validada cambia el estado de la toma. | https://web-services-yzxl.onrender.com/swagger-ui/index.html · intakes-controller |

**Family Monitoring**

| Endpoint | Acción | Verbo HTTP | Sintaxis de llamada | Parámetros | Ejemplo de response | Explicación del response | Documentación |
| --- | --- | --- | --- | --- | --- | --- | --- |
| `/api/v1/older-adults/{olderAdultId}/status` | Consultar el estado reciente de un adulto mayor (US-25) | GET | `GET /api/v1/older-adults/{olderAdultId}/status?caregiverId={caregiverId}` | Path: `olderAdultId`.<br>Query: `caregiverId`. | `200` `{"nextIntakeAt":"2026-10-05T21:00:00Z","lastIntakeStatus":"CONFIRMED","hasOpenAlert":true,"openAlerts":[{"id":1,"intakeId":"101","medicationName":"Losartan 50 mg","scheduledAt":"2026-10-05T13:00:00Z","reason":"Intake not confirmed within the grace period","status":"OPEN","openedAt":"2026-10-05T13:30:00Z","closedAt":null}],"weeklyAdherence":{"confirmedIntakes":1,"totalIntakes":1},"lowStock":[{"medicationId":"7a1b2c3d-1111-4222-8333-444455556666","medicationName":"Losartán","remainingStock":4,"replenishmentThreshold":5,"detectedAt":"2026-10-06T12:00:00Z"}],"adherenceInsights":[{"medicationId":"7a1b2c3d-1111-4222-8333-444455556666","medicationName":"Losartán","omissionDays":3,"firstDay":"2026-10-01","lastDay":"2026-10-03","detectedAt":"2026-10-06T08:00:00Z"}]}` | Devuelve la próxima toma, el resultado de la última y las alertas pendientes. `404` si el adulto mayor no tiene seguimiento activo. | https://web-services-yzxl.onrender.com/swagger-ui/index.html · Family Monitoring |
| `/api/v1/older-adults/{olderAdultId}/intakes` | Consultar el historial reciente de tomas (US-26) | GET | `GET /api/v1/older-adults/{olderAdultId}/intakes?caregiverId={caregiverId}&days={days}` | Path: `olderAdultId`.<br>Query: `caregiverId`, `days` (opcional). | `200` `[{"intakeId":"101","medicationName":"Losartan 50 mg","scheduledAt":"2026-10-05T13:00:00Z","status":"CONFIRMED"}]` | Devuelve las tomas de los últimos días, de la más reciente a la más antigua; vacía si no hay registros. `400` si `days` es inválido; `404` si no hay seguimiento activo. | https://web-services-yzxl.onrender.com/swagger-ui/index.html · Family Monitoring |
| `/api/v1/older-adults/{olderAdultId}/contact-channel` | Consultar el canal de contacto de un adulto mayor (US-29) | GET | `GET /api/v1/older-adults/{olderAdultId}/contact-channel?caregiverId={caregiverId}` | Path: `olderAdultId`.<br>Query: `caregiverId`. | `200` `{"type":"PHONE","value":"+51 999 888 777"}` | Devuelve el canal con el que el cuidador puede comunicarse tras una alerta. `404` si no hay seguimiento o canal. | https://web-services-yzxl.onrender.com/swagger-ui/index.html · Family Monitoring |
| `/api/v1/older-adults/{olderAdultId}/alerts/{alertId}` | Consultar el detalle de una alerta (US-27) | GET | `GET /api/v1/older-adults/{olderAdultId}/alerts/{alertId}?caregiverId={caregiverId}` | Path: `olderAdultId`, `alertId`.<br>Query: `caregiverId`. | `200` `{"id":1,"intakeId":"101","medicationName":"Losartan 50 mg","scheduledAt":"2026-10-05T13:00:00Z","reason":"Intake not confirmed within the grace period","status":"OPEN","openedAt":"2026-10-05T13:30:00Z","closedAt":null}` | Devuelve el medicamento, el horario, el estado y el motivo de la alerta. `404` si no existe. | https://web-services-yzxl.onrender.com/swagger-ui/index.html · Alerts |
| `/api/v1/older-adults/{olderAdultId}/alerts/{alertId}/status` | Actualizar el estado de seguimiento de una alerta (US-31) | PUT | `PUT /api/v1/older-adults/{olderAdultId}/alerts/{alertId}/status?caregiverId={caregiverId}` | Path: `olderAdultId`, `alertId`.<br>Query: `caregiverId`.<br>Body: `status`. | `200` `{"id":1,"intakeId":"101","medicationName":"Losartan 50 mg","scheduledAt":"2026-10-05T13:00:00Z","reason":"Intake not confirmed within the grace period","status":"OPEN","openedAt":"2026-10-05T13:30:00Z","closedAt":null}` | `ATTENDED` registra que el cuidador actuó; `CLOSED` la quita de las pendientes y la conserva en el historial. `400` si el estado no es válido; `404` si no existe; `409` si no puede pasar a ese estado. | https://web-services-yzxl.onrender.com/swagger-ui/index.html · Alerts |
| `/api/v1/older-adults/{olderAdultId}/notes` | Listar las notas de seguimiento (US-30) | GET | `GET /api/v1/older-adults/{olderAdultId}/notes?caregiverId={caregiverId}` | Path: `olderAdultId`.<br>Query: `caregiverId`. | `200` `[{"id":1,"text":"I called her and she had already taken the pill.","recordedAt":"2026-10-05T14:10:00Z","familiarId":"1"}]` | Devuelve las notas registradas, de la más reciente a la más antigua; vacía si no hay. `404` si no hay seguimiento activo. | https://web-services-yzxl.onrender.com/swagger-ui/index.html · Caregiver Notes |
| `/api/v1/older-adults/{olderAdultId}/notes` | Registrar una nota de seguimiento (US-30) | POST | `POST /api/v1/older-adults/{olderAdultId}/notes` | Path: `olderAdultId`.<br>Body: `familiarId`, `text`. | `201` `{"id":1,"text":"I called her and she had already taken the pill.","recordedAt":"2026-10-05T14:10:00Z","familiarId":"1"}` | Guarda la nota con su fecha y su autor; responde `201`. `400` si la nota es inválida; `404` si no hay seguimiento activo. | https://web-services-yzxl.onrender.com/swagger-ui/index.html · Caregiver Notes |

**Adherence Analytics**

| Endpoint | Acción | Verbo HTTP | Sintaxis de llamada | Parámetros | Ejemplo de response | Explicación del response | Documentación |
| --- | --- | --- | --- | --- | --- | --- | --- |
| `/api/v1/older-adults/{olderAdultId}/adherence/weekly` | Consultar la adherencia semanal | GET | `GET /api/v1/older-adults/{olderAdultId}/adherence/weekly?from={from}&to={to}` | Path: `olderAdultId`.<br>Query: `from`, `to`. | `200` `{"olderAdultId":"d3a10000-0000-4000-8000-000000000002","from":"2026-10-03T00:00:00Z","to":"2026-10-10T00:00:00Z","confirmedIntakes":0,"totalIntakes":0,"percentage":0.0,"onTimeIntakes":0,"lateIntakes":0,"omittedIntakes":0}` | Devuelve las tomas confirmadas, a tiempo, tardías y omitidas del período, con el porcentaje de adherencia. | https://web-services-yzxl.onrender.com/swagger-ui/index.html · adherence-controller |
| `/api/v1/older-adults/{olderAdultId}/adherence/summary` | Consultar el resumen de adherencia | GET | `GET /api/v1/older-adults/{olderAdultId}/adherence/summary?days={days}&zone={zone}` | Path: `olderAdultId`.<br>Query: `days` (opcional), `zone` (opcional). | `204` Sin cuerpo | Devuelve los porcentajes de adherencia y puntualidad con el cambio frente al período anterior, la tendencia y las tomas recientes. `204` si no hay tomas definitivas; `400` si el período o la zona son inválidos. | https://web-services-yzxl.onrender.com/swagger-ui/index.html · Adherence Analytics |
| `/api/v1/older-adults/{olderAdultId}/adherence/recommendations` | Consultar las recomendaciones de adherencia | GET | `GET /api/v1/older-adults/{olderAdultId}/adherence/recommendations?from={from}&to={to}&zone={zone}` | Path: `olderAdultId`.<br>Query: `from`, `to`, `zone` (opcional). | `200` `[]` | Devuelve recomendaciones por medicamento con los días de evidencia; la lista va vacía si el período no tiene omisiones. | https://web-services-yzxl.onrender.com/swagger-ui/index.html · adherence-controller |
| `/api/v1/older-adults/{olderAdultId}/adherence/patterns` | Consultar los patrones de omisión | GET | `GET /api/v1/older-adults/{olderAdultId}/adherence/patterns?from={from}&to={to}&zone={zone}` | Path: `olderAdultId`.<br>Query: `from`, `to`, `zone` (opcional). | `200` `[]` | Devuelve, por medicamento, los días de omisión y el primer y último día; la lista va vacía si no hay patrones. | https://web-services-yzxl.onrender.com/swagger-ui/index.html · adherence-controller |
| `/api/v1/older-adults/{olderAdultId}/adherence/insights` | Consultar las recomendaciones de seguimiento según patrones | GET | `GET /api/v1/older-adults/{olderAdultId}/adherence/insights?days={days}&zone={zone}` | Path: `olderAdultId`.<br>Query: `days` (opcional), `zone` (opcional). | `204` Sin cuerpo | Devuelve el patrón detectado, la concentración por franja y las recomendaciones; solo tratan recordatorios, horarios y seguimiento, nunca la dosis. `204` si no hay evidencia suficiente; `400` si el período o la zona son inválidos. | https://web-services-yzxl.onrender.com/swagger-ui/index.html · Adherence Analytics |
| `/api/v1/older-adults/{olderAdultId}/adherence/insight` | Consultar las recomendaciones de seguimiento según patrones (ruta alterna) | GET | `GET /api/v1/older-adults/{olderAdultId}/adherence/insight?days={days}&zone={zone}` | Path: `olderAdultId`.<br>Query: `days` (opcional), `zone` (opcional). | `204` Sin cuerpo | Misma respuesta que `/adherence/insights`. | https://web-services-yzxl.onrender.com/swagger-ui/index.html · Adherence Analytics |
| `/api/v1/older-adults/{olderAdultId}/adherence/history` | Consultar el historial de tomas del período | GET | `GET /api/v1/older-adults/{olderAdultId}/adherence/history?from={from}&to={to}` | Path: `olderAdultId`.<br>Query: `from`, `to`. | `200` `[]` | Devuelve cada toma con su medicamento, horario y estado entre `from` y `to`; la lista va vacía si todavía no hay tomas en el período. | https://web-services-yzxl.onrender.com/swagger-ui/index.html · adherence-controller |
| `/api/v1/older-adults/{olderAdultId}/adherence/consolidations` | Consolidar la adherencia de un período | POST | `POST /api/v1/older-adults/{olderAdultId}/adherence/consolidations?from={from}&to={to}&zone={zone}` | Path: `olderAdultId`.<br>Query: `from`, `to`, `zone` (opcional). | `200` `{"id":"969c2d55-5383-3507-8e83-5093803bd0be","olderAdultId":"d3a10000-0000-4000-8000-000000000002","from":"2026-10-03T00:00:00Z","to":"2026-10-10T00:00:00Z","zone":"Z","consolidatedAt":"2026-10-09T23:15:18.371490Z","confirmedIntakes":0,"totalIntakes":0,"percentage":0.0,"onTimeIntakes":0,"lateIntakes":0,"omittedIntakes":0,"patterns":[],"minimumOmissionDays":3}` | Calcula y guarda una captura de la adherencia entre `from` y `to` y la devuelve. | https://web-services-yzxl.onrender.com/swagger-ui/index.html · adherence-controller |
| `/api/v1/older-adults/{olderAdultId}/adherence/consolidations/{snapshotId}` | Consultar una consolidación de adherencia | GET | `GET /api/v1/older-adults/{olderAdultId}/adherence/consolidations/{snapshotId}` | Path: `olderAdultId`, `snapshotId`. | `200` `{"id":"969c2d55-5383-3507-8e83-5093803bd0be","olderAdultId":"d3a10000-0000-4000-8000-000000000002","from":"2026-10-03T00:00:00Z","to":"2026-10-10T00:00:00Z","zone":"Z","consolidatedAt":"2026-10-09T23:15:18.371490Z","confirmedIntakes":0,"totalIntakes":0,"percentage":0.0,"onTimeIntakes":0,"lateIntakes":0,"omittedIntakes":0,"patterns":[],"minimumOmissionDays":3}` | Devuelve la captura guardada con sus totales y porcentajes. | https://web-services-yzxl.onrender.com/swagger-ui/index.html · adherence-controller |

**Inventory & Replenishment**

| Endpoint | Acción | Verbo HTTP | Sintaxis de llamada | Parámetros | Ejemplo de response | Explicación del response | Documentación |
| --- | --- | --- | --- | --- | --- | --- | --- |
| `/api/v1/inventories` | Registrar el inventario inicial de un medicamento (US-40) | POST | `POST /api/v1/inventories` | Body: `medicationId`, `initialQuantity`, `replenishmentThreshold`. | `201` `{"id":"d58ca5d0-ea63-499a-947b-4cd872537e11","medicationId":"f66da084-42d4-4faa-ba33-996027441d07","remainingStock":30,"replenishmentThreshold":5,"lowStock":false,"batches":[{"id":"117270be-c2c4-4a1e-ac18-1e62eb5bf84f","quantity":30,"registeredAt":"2026-10-09T23:15:07.775052975Z","lot":null}],"createdAt":"2026-10-09T23:15:07.775052975Z","updatedAt":"2026-10-09T23:15:07.775052975Z","daysRemaining":15,"dailyConsumptionUnits":2}` | Crea el stock con su primer lote y el umbral de reposición; solo existe un inventario por medicamento. `400` si faltan datos o la cantidad es inválida; `404` si el medicamento no existe; `409` si está inactivo o ya tiene inventario. | https://web-services-yzxl.onrender.com/swagger-ui/index.html · Inventory |
| `/api/v1/inventories/{medicationId}/replenishments` | Registrar una reposición (US-43) | POST | `POST /api/v1/inventories/{medicationId}/replenishments` | Path: `medicationId`.<br>Body: `quantity`, `lot`. | `201` `{"id":"d58ca5d0-ea63-499a-947b-4cd872537e11","medicationId":"f66da084-42d4-4faa-ba33-996027441d07","remainingStock":40,"replenishmentThreshold":5,"lowStock":false,"batches":[{"id":"117270be-c2c4-4a1e-ac18-1e62eb5bf84f","quantity":30,"registeredAt":"2026-10-09T23:15:07.775053Z","lot":null},{"id":"b4bbf371-bd2f-4df9-9e27-a429938eec8f","quantity":10,"registeredAt":"2026-10-09T23:15:09.889009393Z","lot":"L-2026-10"}],"createdAt":"2026-10-09T23:15:07.775053Z","updatedAt":"2026-10-09T23:15:09.889009393Z","daysRemaining":20,"dailyConsumptionUnits":2}` | Agrega un lote y aumenta el stock; devuelve el inventario actualizado. `400` si faltan datos; `404` si no hay inventario; `409` si hubo una modificación concurrente. | https://web-services-yzxl.onrender.com/swagger-ui/index.html · Inventory |
| `/api/v1/inventories/{medicationId}` | Consultar el stock de un medicamento (US-41, US-42) | GET | `GET /api/v1/inventories/{medicationId}` | Path: `medicationId`. | `200` `{"id":"d58ca5d0-ea63-499a-947b-4cd872537e11","medicationId":"f66da084-42d4-4faa-ba33-996027441d07","remainingStock":40,"replenishmentThreshold":5,"lowStock":false,"batches":[{"id":"117270be-c2c4-4a1e-ac18-1e62eb5bf84f","quantity":30,"registeredAt":"2026-10-09T23:15:07.775053Z","lot":null},{"id":"b4bbf371-bd2f-4df9-9e27-a429938eec8f","quantity":10,"registeredAt":"2026-10-09T23:15:09.889009Z","lot":"L-2026-10"}],"createdAt":"2026-10-09T23:15:07.775053Z","updatedAt":"2026-10-09T23:15:09.889009Z","daysRemaining":20,"dailyConsumptionUnits":2}` | Devuelve las unidades restantes, el umbral, el indicador de stock bajo y los lotes. `404` si no hay inventario. | https://web-services-yzxl.onrender.com/swagger-ui/index.html · Inventory |

**Estado del servicio**

| Endpoint | Acción | Verbo HTTP | Sintaxis de llamada | Parámetros | Ejemplo de response | Explicación del response | Documentación |
| --- | --- | --- | --- | --- | --- | --- | --- |
| `/health` | Verificar que el servicio está activo | GET | `GET /health` | Ninguno. | `200` `{"status":"UP"}` | Devuelve el estado del servicio (`UP`). No requiere token. | https://web-services-yzxl.onrender.com/swagger-ui/index.html · health-controller |
| `/actuator/health` | Verificar el estado del servicio (Actuator) | GET | `GET /actuator/health` | Ninguno. | `200` `{"status":"UP"}` | Devuelve el estado del servicio (`UP`). No requiere token. | https://web-services-yzxl.onrender.com/swagger-ui/index.html · health-controller |

**Capturas de la documentación**

Las primeras capturas las tomamos con el backend corriendo en local, con una base de datos en memoria y datos de muestra, usando la opción *Try it out* de Swagger UI.

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

Las capturas siguientes son del Swagger UI desplegado en Render y muestran los grupos de endpoints de los demás Bounded Contexts.

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
 

**Commits de documentación del Sprint**

Estos son los commits de `develop` que agregan o cambian la documentación OpenAPI de los endpoints.

| Repository | Branch | Commit Id | Commit Message | Commit Message Body | Commited on (Date) |
| --- | --- | --- | --- | --- | --- |
| `vitaHealth-UPC/web-services` | `develop` | `f0cbd66` | `feat(family-monitoring): add REST controllers with OpenAPI documentation` | - | 06/10/2026 |
| `vitaHealth-UPC/web-services` | `develop` | `6bdc2cc` | `feat(inventory): expose inventory REST API` | - InventoryController under /api/v1/inventories documented with OpenAPI<br>- Register initial inventory (US-40), get remaining stock (US-41, US-42) and register replenishment (US-43)<br>- Request/response resources and InventoryResourceAssembler<br>- InventoryExceptionHandler with stable error codes and localized messages | 06/10/2026 |
| `vitaHealth-UPC/web-services` | `develop` | `6f19a6d` | `feat(monitoring): expose real intake history and status endpoints` | - | 06/10/2026 |
| `vitaHealth-UPC/web-services` | `develop` | `a75faae` | `feat(subscription): implement TS-14 plans and subscriptions API` | - | 06/10/2026 |
| `vitaHealth-UPC/web-services` | `develop` | `c4fbb3a` | `feat(voice): implement TS-11 speech-to-text confirmation flow` | Integrate configurable speech-to-text confirmation, validate recognized intent and confidence, preserve intake idempotency, and keep provider failures non-mutating. | 06/10/2026 |
| `vitaHealth-UPC/web-services` | `develop` | `b171f31` | `feat: add accessibility and notification preferences endpoints` | - | 06/10/2026 |
| `vitaHealth-UPC/web-services` | `develop` | `e4b7f33` | `feat: list medications and treatments, expose medication lookup and document with OpenAPI` | - | 06/10/2026 |
| `vitaHealth-UPC/web-services` | `develop` | `f362d4c` | `feat(analytics): add adherence summary and insights views for the family app` | - | 06/10/2026 |
| `vitaHealth-UPC/web-services` | `develop` | `c084872` | `docs(adherence): group view endpoints under Adherence Analytics in Swagger and describe parameters` | - | 06/10/2026 |

#### 4.2.1.8. Software Deployment Evidence for Sprint Review

En este Sprint desplegamos el Landing Page en GitHub Pages y los Web Services en Render, con la base de datos PostgreSQL en Neon. También distribuimos la aplicación Android con Firebase App Distribution. Los pasos de configuración están en la sección 4.1.4.

| Producto | Plataforma | Estado en el Sprint 1 | URL |
| --- | --- | --- | --- |
| Landing Page | GitHub Pages (GitHub Actions) | Desplegado | https://vitahealth-upc.github.io/landing-page/ |
| Web Services | Render (Web Service con Docker, plan Free; rama `develop`) | Desplegado | https://web-services-yzxl.onrender.com |
| Base de datos | Neon (PostgreSQL 16, proyecto TATA, branch `production`, base `tata`) | Desplegada | (conexión privada) |
| Aplicación Android | Firebase App Distribution (proyecto `tata-vitahealth`, app `com.vitahealth.tata`) | Distribuida (versión 0.1.0, APK debug) | Invitación por correo a los testers |

**Landing Page: GitHub Pages**

El repositorio `landing-page` tiene el workflow `.github/workflows/pages.yml` (*Deploy landing page to GitHub Pages*), que se ejecuta con cada push a `develop` o `main` y también se puede lanzar a mano. Hace el checkout, configura Pages, sube el sitio estático y lo publica con `actions/deploy-pages`. En *Settings > Pages* la fuente es *GitHub Actions* y dejamos activa la opción *Enforce HTTPS*.

![GitHub Pages del repositorio landing-page: sitio publicado con GitHub Actions como fuente y HTTPS forzado.](assets/githubPageEvidence.png)

*Figura 1. GitHub Pages del repositorio `landing-page`: sitio publicado con GitHub Actions como fuente y HTTPS forzado.*

![Landing Page publicada en https://vitahealth-upc.github.io/landing-page/.](assets/landingPageEvidence.png)

*Figura 2. Landing Page publicada en https://vitahealth-upc.github.io/landing-page/.*

**Base de datos: Neon**

En Neon creamos el proyecto TATA con el plan Free, en la región AWS US East 2 (Ohio), con el branch `production` y la base `tata`. La cadena de conexión la copiamos desde *Connect*, con *connection pooling* activo y el rol `tata_owner`. La contraseña no se muestra en las capturas.

![Neon: resumen del proyecto TATA, branch production.](assets/deployment-evidence/neon-proyecto.png)

*Figura 3. Neon: resumen del proyecto TATA, branch `production`.*

![Neon: cadena de conexión con la contraseña oculta.](assets/deployment-evidence/neon-connect.png)

*Figura 4. Neon: cadena de conexión con la contraseña oculta.*

**Web Services: Render**

En Render creamos un Web Service enlazado al repositorio `vitaHealth-UPC/web-services`, rama `develop`, con entorno Docker (el `Dockerfile` está en la raíz) y plan Free. La conexión a la base de datos va en las variables de entorno `SPRING_DATASOURCE_URL` (`jdbc:postgresql://<host>.neon.tech:5432/tata?sslmode=require`), `SPRING_DATASOURCE_USERNAME` y `SPRING_DATASOURCE_PASSWORD`, así que ningún secreto queda en el repositorio. En producción las tablas se crean al arrancar con `spring.jpa.hibernate.ddl-auto=update`. Después agregamos la variable `TATA_DEMO_SEED=true`, que crea una cuenta de demostración al arrancar, porque el envío del código de verificación por correo todavía no está integrado.

![Render: variables de entorno del servicio con los valores ocultos.](assets/deployment-evidence/render-env.png)

*Figura 5. Render: variables de entorno del servicio con los valores ocultos.*

Lanzamos el primer despliegue a mano; terminó con *Deploy succeeded* y el servicio quedó en estado *Live*.

![Render: despliegue exitoso y servicio en estado Live.](assets/deployment-evidence/render-deploy.png)

*Figura 6. Render: despliegue exitoso y servicio en estado Live.*

**Verificación**

`GET /health` responde `{"status":"UP"}` y Swagger UI abre en la URL pública. Como el plan Free de Render suspende la instancia cuando no recibe tráfico, la primera petición después de un rato puede tardar en responder.

![Verificación de GET /health en la URL pública.](assets/deployment-evidence/health.png)

*Figura 7. Verificación de `GET /health` en la URL pública.*

![Swagger UI en la URL pública del backend.](assets/deployment-evidence/swagger-desplegado.png)

*Figura 8. Swagger UI en la URL pública del backend.*

**Aplicación Android: Firebase App Distribution**

Para distribuir la aplicación Android creamos el proyecto `tata-vitahealth` en Firebase, con el plan Spark, y registramos la app `Tata` con el identificador `com.vitahealth.tata`.

![Firebase: resumen del proyecto tata-vitahealth con la app Tata registrada.](assets/deployment-evidence/FirebaseDeployment1.png)

*Figura 9. Firebase: resumen del proyecto `tata-vitahealth` con la app Tata registrada.*

Generamos el APK con `./gradlew :app:assembleDebug`, que apunta por defecto al backend desplegado en Render, y lo subimos a App Distribution. Firebase confirmó la carga de `app-debug.apk` y creó la versión 0.1.0 (1). Para este Sprint usamos el APK de debug; la versión firmada de release queda pendiente.

![Firebase: se subió app-debug.apk correctamente y se crea la versión 0.1.0.](assets/deployment-evidence/FirebaseDeployment2.png)

*Figura 10. Firebase App Distribution: carga correcta de `app-debug.apk`.*

Después invitamos a un verificador y escribimos las notas de la versión ("Segundo Hito App Moviles"). El panel de versiones muestra la 0.1.0 con 1 invitado, 1 invitación aceptada y 1 descarga.

![Firebase: versión 0.1.0 con 1 invitado, 1 aceptada y 1 descargada.](assets/deployment-evidence/FirebaseDeployment.png)

*Figura 11. Firebase App Distribution: versión 0.1.0 distribuida a un verificador.*

El verificador recibió un correo con la invitación a probar Tata (`com.vitahealth.tata`), desde el que acepta la invitación con su cuenta de Google, habilita la instalación desde orígenes desconocidos y descarga la app con Firebase App Distribution.

![Correo de invitación de Firebase App Distribution para probar Tata.](assets/deployment-evidence/pruebaFirebase.jpeg)

*Figura 12. Correo de invitación de Firebase App Distribution para probar Tata.*

**Commits de despliegue del Sprint**

| Repository | Branch | Commit Id | Commit Message | Commit Message Body | Commited on (Date) |
| --- | --- | --- | --- | --- | --- |
| `vitaHealth-UPC/web-services` | `develop` | `67511a1` | `chore(deploy): add Docker packaging, health and DATABASE_URL mapping Prepare the Spring Boot API so Railway can build and run it.` | - | 07/10/2026 |
| `vitaHealth-UPC/web-services` | `develop` | `7582274` | `fix(deploy): use published Temurin 26 Docker base images` | - | 07/10/2026 |
| `vitaHealth-UPC/web-services` | `develop` | `aebd362` | `fix(deploy): map DATABASE_URL into Spring datasource for Neon/Render` | - | 07/10/2026 |
| `vitaHealth-UPC/landing-page` | `develop` | `01ef128` | `ci: add GitHub Pages preview from develop` | - | 02/10/2026 |
| `vitaHealth-UPC/web-services` | `develop` | `a941b15` | `feat: add demo account seeders enabled by TATA_DEMO_SEED` | - | 09/10/2026 |
| `vitaHealth-UPC/web-services` | `develop` | `d9d2518` | `fix: create the demo caregiver by id and use a free default email` | - | 09/10/2026 |


#### 4.2.1.9. Team Collaboration Insights during Sprint

<p align="center">
  <img src="assets/repository-evidence/android-collaboration.png" alt="Contribuciones de Android en GitHub" width="960">
</p>

*Figura. Contribuciones en main del repositorio Android, sin commits de merge.*

<p align="center">
  <img src="assets/repository-evidence/backend-collaboration.png" alt="Contribuciones del backend en GitHub" width="960">
</p>

*Figura. Contribuciones en main del backend, sin commits de merge.*

El equipo distribuye el trabajo por historias y bounded contexts. Los Pull Requests reúnen implementación, revisión e integración; los historiales muestran la participación de los integrantes en los productos.

| Producto | Colaboración |
| --- | --- |
| Landing | Propuesta de valor, funcionalidades, planes y adaptación responsive |
| Backend | Cuenta, vínculo, tratamiento, tomas, seguimiento y servicios de apoyo |
| Android | Vistas, contratos de API, navegación y validación visual |
| Reporte | Diseño, evidencias del Sprint y documentación del producto |

Enlace a colaboración de landing-page:

https://github.com/vitaHealth-UPC/landing-page/graphs/contributors

Enlace a colaboración de web-services:

https://github.com/vitaHealth-UPC/web-services/graphs/contributors

Enlace a colaboración de mobile-android:

https://github.com/vitaHealth-UPC/mobile-android/graphs/contributors

Enlace a colaboración de project-report:

https://github.com/vitaHealth-UPC/project-report/graphs/contributors

### 4.2.2. Sprint 2

Sprint 2 reúne la confirmación de las tomas, las alertas y el seguimiento familiar, la gestión de tratamientos y medicamentos, los ajustes de accesibilidad y los procesos de soporte: tomas sin confirmar, notificaciones push, reconocimiento de voz y almacenamiento local. El alcance comprende 22 elementos del Product Backlog (15 historias de usuario, 6 Technical Stories y 1 Spike Story) y 81 Story Points. En este Sprint el trabajo se avanza en tres productos: los Web Services, la aplicación Android y la migración a Flutter. El Landing Page no cambia, porque ya se completó y desplegó en el Sprint 1.

#### 4.2.2.1. Sprint Planning 2

**Sprint Planning Background**

| Campo | Detalle |
| --- | --- |
| Sprint # | Sprint 2 |
| Date | |
| Time | |
| Location | |
| Prepared By | |
| Attendees (to the planning meeting) | |

**Sprint 1 Review Summary**



**Sprint 1 Retrospective Summary**



**Sprint Goal & User Stories**

| Campo | Detalle |
| --- | --- |
| Sprint 2 Goal | |
| Sprint 2 Velocity | |
| Sum of Story Points | |


#### 4.2.2.2. Aspect Leaders and Collaborators

<!-- Incorporar la matriz LACX con los aspectos, líderes y colaboradores del Sprint 2. -->


#### 4.2.2.3. Sprint Backlog 2

**Sprint Board**

<!-- Incorporar captura del tablero y su enlace público. -->

**Sprint Backlog**

| Historia | Título | Task ID | Tarea | Estimación (horas) | Responsable | Estado |
| --- | --- | --- | --- | --- | --- | --- |


#### 4.2.2.4. Development Evidence for Sprint Review

Durante el Sprint 2 la implementación avanzó en tres productos. En los Web Services completamos el procesamiento de tomas no confirmadas (TS-05) y la integración de notificaciones (TS-06), con la persistencia de la política de notificación, los contactos de emergencia y la preferencia de llamada. Después consolidamos la arquitectura por Bounded Context, los contratos verificados y la seguridad en el release `v1.1.0`, integrado a `main`. En la aplicación Android implementamos las preferencias de notificación de US-39, con editores nativos para la política y los contactos alineados con Figma, y alineamos la arquitectura antes de los releases `v1.1.x`. También iniciamos la aplicación multiplataforma en Flutter con el mismo backend: acceso, registro y recuperación de cuenta, vínculo y consentimiento, acceso del adulto mayor con PIN, inicio con la próxima toma y el progreso del día, agenda semanal, detalle de toma y confirmación por toque (US-01, US-02, US-06, US-10, US-11, US-12, US-13, US-20, US-21 y US-24).

El Landing Page no recibió cambios de código en este Sprint, porque su alcance se completó y desplegó en el Sprint 1. Los commits con el mensaje `fix: minor changes` de las ramas `fix/backend-architecture` y `fix/android-architecture` agrupan la reorganización por Bounded Context previa a los releases. En Flutter, el trabajo se integra temporalmente en la rama compartida `temp` y se distribuirá en ramas `feature/us-xx` por historia antes de integrarse a `develop`. Los commits de pruebas se detallan en la sección 4.2.2.5 y los de documentación no se incluyen en esta tabla.

| Repository | Branch | Commit Id | Commit Message | Commit Message Body | Committed on (Date) |
| --- | --- | --- | --- | --- | --- |
| `vitaHealth-UPC/web-services` | `feature/ts-05-unconfirmed-intake-processing` | [`4bc1c69`](https://github.com/vitaHealth-UPC/web-services/commit/4bc1c69) | `fix(ts-05): ignore delayed unconfirmed events after intake confirmation` | - | 10/10/2026 |
| `vitaHealth-UPC/web-services` | `feature/ts-05-unconfirmed-intake-processing` | [`8c128e8`](https://github.com/vitaHealth-UPC/web-services/commit/8c128e8) | `fix(ts-05): lock scheduler candidates before reporting unresolved intakes` | - | 11/10/2026 |
| `vitaHealth-UPC/web-services` | `feature/ts-06-push-notification-integration` | [`95d5638`](https://github.com/vitaHealth-UPC/web-services/commit/95d5638) | `feat(ts-06): persist the call notification channel preference` | - | 11/10/2026 |
| `vitaHealth-UPC/web-services` | `feature/ts-06-push-notification-integration` | [`8a4b0b7`](https://github.com/vitaHealth-UPC/web-services/commit/8a4b0b7) | `feat(ts-06): persist notification policy and emergency contacts` | - | 11/10/2026 |
| `vitaHealth-UPC/web-services` | `feature/ts-06-push-notification-integration` | [`2de88ed`](https://github.com/vitaHealth-UPC/web-services/commit/2de88ed) | `fix(ts-06): serialize notification effects and escalation decisions` | - | 11/10/2026 |
| `vitaHealth-UPC/web-services` | `fix/backend-architecture` | [`0e24649`](https://github.com/vitaHealth-UPC/web-services/commit/0e24649) | `fix: minor changes` | - | 22/10/2026 |
| `vitaHealth-UPC/web-services` | `fix/backend-architecture` | [`e3fab7e`](https://github.com/vitaHealth-UPC/web-services/commit/e3fab7e) | `release: consolidate verified APMO backend contracts and security` | Includes dark theme persistence, alert timeline, medication reactivation, treatment consistency, adherence context, API contract integration and regression coverage. | 22/10/2026 |
| `vitaHealth-UPC/web-services` | `fix/backend-architecture` | [`56e9b76`](https://github.com/vitaHealth-UPC/web-services/commit/56e9b76) | `fix: minor changes` | - | 27/10/2026 |
| `vitaHealth-UPC/mobile-android` | `feature/us-39-quiet-hours-channels` | [`08ace9f`](https://github.com/vitaHealth-UPC/mobile-android/commit/08ace9f) | `fix(us-39): render original Figma notification icons and proportional header` | - | 10/10/2026 |
| `vitaHealth-UPC/mobile-android` | `feature/us-39-quiet-hours-channels` | [`9e764f5`](https://github.com/vitaHealth-UPC/mobile-android/commit/9e764f5) | `feat(us-39): align notification editors and preserve call preferences` | - | 11/10/2026 |
| `vitaHealth-UPC/mobile-android` | `feature/us-39-quiet-hours-channels` | [`aead8dd`](https://github.com/vitaHealth-UPC/mobile-android/commit/aead8dd) | `feat(us-39): integrate native notification policy and contact editors` | - | 11/10/2026 |
| `vitaHealth-UPC/mobile-android` | `fix/android-architecture` | [`828c0ac`](https://github.com/vitaHealth-UPC/mobile-android/commit/828c0ac) | `fix: minor changes` | - | 26/10/2026 |
| `vitaHealth-UPC/mobile-android` | `fix/android-architecture` | [`34fdef9`](https://github.com/vitaHealth-UPC/mobile-android/commit/34fdef9) | `fix: minor changes` | - | 27/10/2026 |
| `vitaHealth-UPC/mobile-android` | `fix/android-architecture` | [`0e29678`](https://github.com/vitaHealth-UPC/mobile-android/commit/0e29678) | `fix: minor changes` | - | 27/10/2026 |
| `vitaHealth-UPC/mobile-android` | `fix/android-architecture` | [`d9c6c70`](https://github.com/vitaHealth-UPC/mobile-android/commit/d9c6c70) | `fix: minor changes` | - | 27/10/2026 |
| `vitaHealth-UPC/mobile-cross-platform` | `main` | [`ed44709`](https://github.com/vitaHealth-UPC/mobile-cross-platform/commit/ed44709) | `chore: initialize Flutter scaffold` | - | 27/10/2026 |
| `vitaHealth-UPC/mobile-cross-platform` | `temp` | [`ce70f0d`](https://github.com/vitaHealth-UPC/mobile-cross-platform/commit/ce70f0d) | `feat: share Flutter identity and care-link checkpoint` | - | 02/11/2026 |
| `vitaHealth-UPC/mobile-cross-platform` | `temp` | [`bfe62b9`](https://github.com/vitaHealth-UPC/mobile-cross-platform/commit/bfe62b9) | `feat: add adult PIN access and next-dose home` | - | 03/11/2026 |
| `vitaHealth-UPC/mobile-cross-platform` | `temp` | [`aec8faf`](https://github.com/vitaHealth-UPC/mobile-cross-platform/commit/aec8faf) | `chore: allow local backend verification in debug builds` | - | 03/11/2026 |
| `vitaHealth-UPC/mobile-cross-platform` | `temp` | [`4ff897a`](https://github.com/vitaHealth-UPC/mobile-cross-platform/commit/4ff897a) | `feat: add weekly intake agenda and touch confirmation` | - | 03/11/2026 |
| `vitaHealth-UPC/mobile-cross-platform` | `temp` | [`e425705`](https://github.com/vitaHealth-UPC/mobile-cross-platform/commit/e425705) | `chore: extend local probe with intake confirmation` | - | 03/11/2026 |

Enlaces a commits:

https://github.com/vitaHealth-UPC/web-services/commits/develop/

https://github.com/vitaHealth-UPC/mobile-android/commits/develop/

https://github.com/vitaHealth-UPC/mobile-cross-platform/commits/temp/


#### 4.2.2.5. Testing Suite Evidence for Sprint Review

**Unit Tests**

<!-- Incorporar las pruebas y las clases/comportamientos que verifican. -->

**Integration & Acceptance Tests**

<!-- Incorporar pruebas de integración/BDD, archivos .feature y evidencias. -->

**Testing Commits**

| Repository | Branch | Commit Id | Commit Message | Commit Message Body | Committed on (Date) |
| --- | --- | --- | --- | --- | --- |


#### 4.2.2.6. Execution Evidence for Sprint Review

**Landing Page**



**Web Services**



**Mobile Applications**



**Execution Video**



#### 4.2.2.7. Services Documentation Evidence for Sprint Review

En este Sprint ampliamos la documentación OpenAPI del backend con las operaciones nuevas: pasamos de 64 a 81 operaciones, es decir, 17 nuevas. Esta sección documenta solo esas 17; las 64 anteriores siguen en la sección 4.2.1.7. Las nuevas pertenecen a los Bounded Contexts Identity & Subscription (inicio de sesión social, recuperación de contraseña y dispositivos push), Care Link (edición del adulto mayor, contacto de emergencia y retiro del consentimiento), Treatment Management (reactivación de medicamentos y medicamentos del adulto mayor), Family Monitoring (línea de tiempo de alertas y notas de rutina), Adherence Analytics (resumen por tratamiento) y Accessibility & Preferences (tema oscuro y política de notificación). Todas las llamadas llevan el encabezado `Authorization: Bearer <token>`, menos las que la tabla marca como públicas; sin el token responden `401 AUTHENTICATION_REQUIRED`. Los ejemplos de respuesta son respuestas reales del backend: las obtuvimos ejecutando la versión actual de `develop` en una base de datos local con la cuenta de demostración (cuidadora y adulto mayor con PIN). Tres ejemplos los armamos con la misma estructura de la respuesta real, porque no se pueden ejecutar con la cuenta demo: el inicio de sesión social (necesita un token válido de Firebase), el restablecimiento de contraseña (necesita el código que llega por correo) y la línea de tiempo de una alerta (la cuenta demo no tiene alertas). El resumen de adherencia por tratamiento devuelve `204` porque la cuenta demo aún no tiene tomas pasadas.

Repositorio de Web Services: https://github.com/vitaHealth-UPC/web-services

Documentación desplegada: https://web-services-yzxl.onrender.com/swagger-ui/index.html

**Identity & Subscription**

| Endpoint | Acción | Verbo HTTP | Sintaxis de llamada | Parámetros | Ejemplo de response | Explicación del response | Documentación |
| --- | --- | --- | --- | --- | --- | --- | --- |
| `/api/v1/social-sessions` | Iniciar sesión con una cuenta social (Google), verificando el token de Firebase | POST | `POST /api/v1/social-sessions` | Body: `firebaseIdToken` (token de identidad que entrega Firebase Authentication). | `200` `{"accountId":"d3a10000-0000-4000-8000-000000000001","accessToken":"<jwt>","expiresAt":"2026-11-11T18:06:22Z"}` | Endpoint público. Verifica la firma del token con Firebase y devuelve una sesión de cuidador igual a la del inicio de sesión con contraseña. `400` si falta el token; `503 SOCIAL_PROVIDER_UNAVAILABLE` si el proveedor no está configurado o no responde (respuesta real al probar con un token de prueba). El ejemplo `200` lo armamos con la estructura real, porque requiere un token válido de Firebase. | https://web-services-yzxl.onrender.com/swagger-ui/index.html · Identity & Subscription |
| `/api/v1/me/social-identities` | Vincular una cuenta social a la cuenta del cuidador autenticado | PUT | `PUT /api/v1/me/social-identities` | Body: `firebaseIdToken`. | `204` Sin cuerpo | Asocia la identidad de Firebase a la cuenta de la sesión; después el cuidador puede entrar con `POST /api/v1/social-sessions`. Solo acepta sesiones de cuidador. `503 SOCIAL_PROVIDER_UNAVAILABLE` si el proveedor no está disponible (respuesta real al probar con un token de prueba). El `204` es la respuesta de éxito definida en el controlador. | https://web-services-yzxl.onrender.com/swagger-ui/index.html · Identity & Subscription |
| `/api/v1/password-recovery-requests` | Solicitar la recuperación de la contraseña | POST | `POST /api/v1/password-recovery-requests` | Body: `email`. | `202` Sin cuerpo | Endpoint público. Responde `202` exista o no la cuenta, para no revelar qué correos están registrados; si existe, genera un código de recuperación de un solo uso. `400` si el correo no tiene formato válido. | https://web-services-yzxl.onrender.com/swagger-ui/index.html · Identity & Subscription |
| `/api/v1/password-recoveries` | Restablecer la contraseña con el código de recuperación | POST | `POST /api/v1/password-recoveries` | Body: `email`, `code`, `newPassword` (hasta 72 caracteres). | `204` Sin cuerpo | Endpoint público. Cambia la contraseña y consume el código. `400 INVALID_RECOVERY_CODE` si el código es incorrecto, venció o ya se usó (respuesta real: `{"detail":"The recovery code is invalid or is no longer available.","instance":"/api/v1/password-recoveries","status":400,"title":"INVALID_RECOVERY_CODE"}`). El ejemplo `204` lo armamos con la respuesta de éxito del controlador, porque el código real llega por correo. | https://web-services-yzxl.onrender.com/swagger-ui/index.html · Identity & Subscription |
| `/api/v1/push-devices/{installationId}` | Registrar o rotar el token FCM del dispositivo | PUT | `PUT /api/v1/push-devices/{installationId}` | Path: `installationId` (UUID que crea la instalación).<br>Body: `token` (token FCM actual). | `200` `{"installationId":"6d3f1c52-9a7e-4b1d-8f20-3c5e7a91b4d6","updatedAt":"2026-11-11T06:06:23.060719Z"}` | La propiedad se deriva de la sesión; el token del dispositivo no se devuelve. Repetir el mismo token conserva `updatedAt`. `409` si el token ya pertenece a otra instalación; `401` sin sesión válida. | https://web-services-yzxl.onrender.com/swagger-ui/index.html · Identity & Subscription |
| `/api/v1/push-devices/{installationId}` | Eliminar el registro del dispositivo | DELETE | `DELETE /api/v1/push-devices/{installationId}` | Path: `installationId`. | `204` Sin cuerpo | Quita el dispositivo de la sesión que lo registró; repetir la llamada también responde `204`. `403` si lo intenta otra sesión. | https://web-services-yzxl.onrender.com/swagger-ui/index.html · Identity & Subscription |

**Care Link**

| Endpoint | Acción | Verbo HTTP | Sintaxis de llamada | Parámetros | Ejemplo de response | Explicación del response | Documentación |
| --- | --- | --- | --- | --- | --- | --- | --- |
| `/api/v1/older-adults/{olderAdultId}` | Editar el nombre y la fecha de nacimiento del adulto mayor | PUT | `PUT /api/v1/older-adults/{olderAdultId}` | Path: `olderAdultId`.<br>Body: `fullName`, `birthDate` (`AAAA-MM-DD`). | `200` `{"id":"d3a10000-0000-4000-8000-000000000002","registeredByCaregiverId":"d3a10000-0000-4000-8000-000000000001","fullName":"Rosa Vargas Quispe","birthDate":"1948-05-12","emergencyContactName":"Diego Vargas","emergencyContactRelationship":"Son","emergencyContactPhone":"999888777","createdAt":"2026-11-11T06:06:16.200916Z"}` | Devuelve el perfil actualizado. `400` si falta el nombre o la fecha. | https://web-services-yzxl.onrender.com/swagger-ui/index.html · older-adults-controller |
| `/api/v1/older-adults/{olderAdultId}/emergency-contact` | Actualizar el contacto de emergencia del adulto mayor | PUT | `PUT /api/v1/older-adults/{olderAdultId}/emergency-contact` | Path: `olderAdultId`.<br>Body: `fullName`, `relationship`, `phone`. | `200` `{"id":"d3a10000-0000-4000-8000-000000000002","registeredByCaregiverId":"d3a10000-0000-4000-8000-000000000001","fullName":"Rosa Vargas Quispe","birthDate":"1948-05-12","emergencyContactName":"Diego Vargas","emergencyContactRelationship":"Hijo","emergencyContactPhone":"999888777","createdAt":"2026-11-11T06:06:16.200916Z"}` | Devuelve el perfil con el contacto nuevo. Guardar un contacto no concede acceso de cuidado. `400` si falta algún dato. | https://web-services-yzxl.onrender.com/swagger-ui/index.html · older-adults-controller |
| `/api/v1/care-links/{careLinkId}/consent` | Retirar el consentimiento de un vínculo de cuidado | DELETE | `DELETE /api/v1/care-links/{careLinkId}/consent` | Path: `careLinkId`. | `204` Sin cuerpo | Lo ejecuta el adulto mayor con su propia sesión: el actor sale de la credencial, no del cuerpo. El vínculo deja de estar activo y se revocan las credenciales ligadas a él. | https://web-services-yzxl.onrender.com/swagger-ui/index.html · care-links-controller |

**Treatment Management**

| Endpoint | Acción | Verbo HTTP | Sintaxis de llamada | Parámetros | Ejemplo de response | Explicación del response | Documentación |
| --- | --- | --- | --- | --- | --- | --- | --- |
| `/api/v1/medications/{medicationId}/reactivation` | Reactivar un medicamento (US-04) | POST | `POST /api/v1/medications/{medicationId}/reactivation?caregiverId={caregiverId}` | Path: `medicationId`.<br>Query: `caregiverId`. | `200` `{"id":"8f6e4da9-ea94-4690-a8c4-36818c596079","olderAdultId":"d3a10000-0000-4000-8000-000000000002","name":"Losartán","presentation":"50 mg, tableta","active":true}` | El medicamento vuelve a `active: true`. No reanuda los tratamientos que se pausaron al desactivarlo: hay que reanudarlos con `POST /api/v1/treatments/{treatmentId}/resume`. 403 si el cuidador no tiene un vínculo de cuidado activo con el adulto mayor. | https://web-services-yzxl.onrender.com/swagger-ui/index.html · Medications |
| `/api/v1/me/medications` | Consultar mis medicamentos con sus tratamientos (adulto mayor) | GET | `GET /api/v1/me/medications` | Sin parámetros: el adulto mayor sale de la sesión con PIN. | `200` `[{"medication":{"id":"8f6e4da9-ea94-4690-a8c4-36818c596079","olderAdultId":"d3a10000-0000-4000-8000-000000000002","name":"Losartán","presentation":"50 mg, tableta","active":true},"treatments":[]}]` | Devuelve cada medicamento con la lista de sus tratamientos (`treatments` vacía si todavía no tiene). Ningún parámetro permite elegir a otro adulto mayor. `401` sin sesión. | https://web-services-yzxl.onrender.com/swagger-ui/index.html · Medications |

**Family Monitoring**

| Endpoint | Acción | Verbo HTTP | Sintaxis de llamada | Parámetros | Ejemplo de response | Explicación del response | Documentación |
| --- | --- | --- | --- | --- | --- | --- | --- |
| `/api/v1/older-adults/{olderAdultId}/alerts/{alertId}/timeline` | Consultar la línea de tiempo registrada de una alerta (US-27) | GET | `GET /api/v1/older-adults/{olderAdultId}/alerts/{alertId}/timeline?caregiverId={caregiverId}` | Path: `olderAdultId`, `alertId` (numérico).<br>Query: `caregiverId`. | `200` `[{"type":"INTAKE_SCHEDULED","occurredAt":"2026-11-11T13:00:00Z"},{"type":"ALERT_GENERATED","occurredAt":"2026-11-11T13:20:00Z"}]` | Devuelve solo los instantes que quedaron guardados: `INTAKE_SCHEDULED`, `ALERT_GENERATED` y, si se cerró, `ALERT_CLOSED`; no estima si la notificación llegó. El ejemplo `200` lo armamos con la estructura real, porque la cuenta demo no tiene alertas. Con un `alertId` que no existe responde `404 NOT_FOUND` (respuesta real) y sin sesión `401 AUTHENTICATION_REQUIRED`; 403 si el cuidador no tiene un vínculo de cuidado activo con el adulto mayor. | https://web-services-yzxl.onrender.com/swagger-ui/index.html · Alerts |
| `/api/v1/me/notes` | Agregar una nota de rutina privada (adulto mayor) | POST | `POST /api/v1/me/notes` | Body: `title` (hasta 100), `text` (hasta 1000), `category` (`MEDICATION` o `ROUTINE`). | `201` `{"id":1,"title":"Control de presión","text":"Medir la presión antes del desayuno","category":"ROUTINE","recordedAt":"2026-11-11T06:06:23.293304Z"}` | Guarda la nota a nombre del adulto mayor de la sesión. Son notas distintas de las de seguimiento del cuidador. `400` si falta un dato o la categoría no es válida. | https://web-services-yzxl.onrender.com/swagger-ui/index.html · Personal Notes |
| `/api/v1/me/notes` | Listar mis notas de rutina | GET | `GET /api/v1/me/notes` | Sin parámetros. | `200` `[{"id":1,"title":"Control de presión","text":"Medir la presión antes del desayuno","category":"ROUTINE","recordedAt":"2026-11-11T06:06:23.293304Z"}]` | Devuelve las notas del adulto mayor autenticado; lista vacía si no tiene. | https://web-services-yzxl.onrender.com/swagger-ui/index.html · Personal Notes |

**Adherence Analytics**

| Endpoint | Acción | Verbo HTTP | Sintaxis de llamada | Parámetros | Ejemplo de response | Explicación del response | Documentación |
| --- | --- | --- | --- | --- | --- | --- | --- |
| `/api/v1/older-adults/{olderAdultId}/adherence/treatments/{treatmentId}/summary` | Consultar el resumen de adherencia de un tratamiento | GET | `GET /api/v1/older-adults/{olderAdultId}/adherence/treatments/{treatmentId}/summary?days={days}&zone={zone}` | Path: `olderAdultId`, `treatmentId`.<br>Query: `days` (opcional, 7 por defecto), `zone` (opcional, `America/Lima` por defecto). | `204` Sin cuerpo | Devuelve el mismo resumen de `/adherence/summary` (porcentajes, tendencia, tomas recientes y patrón), pero solo con las tomas de ese tratamiento. `204` si todavía no hay tomas definitivas, como en la cuenta demo; `400` si el período o la zona son inválidos. | https://web-services-yzxl.onrender.com/swagger-ui/index.html · Adherence Analytics |

**Accessibility & Preferences**

| Endpoint | Acción | Verbo HTTP | Sintaxis de llamada | Parámetros | Ejemplo de response | Explicación del response | Documentación |
| --- | --- | --- | --- | --- | --- | --- | --- |
| `/api/v1/users/{userId}/preferences/dark-theme` | Activar o desactivar el tema oscuro | PUT | `PUT /api/v1/users/{userId}/preferences/dark-theme` | Path: `userId`.<br>Body: `enabled` (booleano). | `200` `{"userId":"d3a10000-0000-4000-8000-000000000002","textSize":"MEDIUM","highContrast":false,"reducedMotion":false,"readingAssistance":false,"voiceConfirmationEnabled":true,"quietHours":null,"notificationChannels":[{"type":"PUSH","enabled":true},{"type":"SMS","enabled":false},{"type":"EMAIL","enabled":false},{"type":"CALL","enabled":false}],"notificationPolicy":{"reminderMinutes":10,"pendingAlertMinutes":20,"omittedAlertMinutes":120,"escalationMinutes":180,"dailySummaryTime":"20:00:00"},"emergencyContacts":[],"darkTheme":true}` | Devuelve las preferencias completas, ahora con `darkTheme`, la política de notificación y los contactos de emergencia. El cambio se conserva para las próximas sesiones. | https://web-services-yzxl.onrender.com/swagger-ui/index.html · Accessibility |
| `/api/v1/users/{userId}/notification-preferences/policy` | Reemplazar los tiempos de aviso y los contactos de emergencia (US-39) | PUT | `PUT /api/v1/users/{userId}/notification-preferences/policy` | Path: `userId`.<br>Body: `policy` (`reminderMinutes`, `pendingAlertMinutes`, `omittedAlertMinutes`, `escalationMinutes`, enteros desde 1; `dailySummaryTime` opcional, `HH:mm`) y `contacts` (lista de `name` y `phone`). | `200` `{"userId":"d3a10000-0000-4000-8000-000000000002","textSize":"MEDIUM","highContrast":false,"reducedMotion":false,"readingAssistance":false,"voiceConfirmationEnabled":true,"quietHours":null,"notificationChannels":[{"type":"PUSH","enabled":true},{"type":"SMS","enabled":false},{"type":"EMAIL","enabled":false},{"type":"CALL","enabled":false}],"notificationPolicy":{"reminderMinutes":10,"pendingAlertMinutes":20,"omittedAlertMinutes":120,"escalationMinutes":180,"dailySummaryTime":"20:00:00"},"emergencyContacts":[{"name":"Diego Vargas","phone":"999888777"}],"darkTheme":true}` | Guarda la política sin tocar las horas de silencio, los canales ni la dosis. Los retrasos deben crecer del recordatorio a la escalación y se miden desde la toma programada; un `dailySummaryTime` nulo desactiva el resumen. `400` si los tiempos o los contactos no son válidos. | https://web-services-yzxl.onrender.com/swagger-ui/index.html · Notification Preferences |

**Capturas de la documentación**

![Swagger UI: operaciones nuevas de Identity & Subscription.](assets/services-documentation/s2-swagger-identity-subscription.png)

*Figura 25. Swagger UI: operaciones nuevas de Identity & Subscription (sesión social, recuperación de contraseña y dispositivos push).*

![Swagger UI: operaciones nuevas de Care Link.](assets/services-documentation/s2-swagger-care-link.png)

*Figura 26. Swagger UI: operaciones nuevas de Care Link.*

![Swagger UI: operaciones nuevas de Treatment Management.](assets/services-documentation/s2-swagger-medications.png)

*Figura 27. Swagger UI: operaciones nuevas de Medications (reactivación y `/me/medications`).*

![Swagger UI: operaciones nuevas de Family Monitoring.](assets/services-documentation/s2-swagger-family-monitoring.png)

*Figura 28. Swagger UI: operaciones nuevas de Family Monitoring (línea de tiempo y notas de rutina).*

![Swagger UI: operaciones nuevas de Adherence Analytics y Accessibility.](assets/services-documentation/s2-swagger-analytics-accessibility.png)

*Figura 29. Swagger UI: resumen de adherencia por tratamiento, tema oscuro y política de notificación.*

**Commits de documentación del Sprint**

Estos son los commits de `develop` que agregan o cambian las operaciones documentadas con OpenAPI en este Sprint.

| Repository | Branch | Commit Id | Commit Message | Commit Message Body | Commited on (Date) |
| --- | --- | --- | --- | --- | --- |
| `vitaHealth-UPC/web-services` | `feature/ts-06-push-notification-integration` | [`8a4b0b7`](https://github.com/vitaHealth-UPC/web-services/commit/8a4b0b7) | `feat(ts-06): persist notification policy and emergency contacts` | - | 11/10/2026 |
| `vitaHealth-UPC/web-services` | `fix/backend-architecture` | [`e3fab7e`](https://github.com/vitaHealth-UPC/web-services/commit/e3fab7e) | `release: consolidate verified APMO backend contracts and security` | Includes dark theme persistence, alert timeline, medication reactivation, treatment consistency, adherence context, API contract integration and regression coverage. | 22/10/2026 |
| `vitaHealth-UPC/web-services` | `fix/backend-architecture` | [`0e24649`](https://github.com/vitaHealth-UPC/web-services/commit/0e24649) | `fix: minor changes` | Agrega los controladores de dispositivos push y de notas personales. | 22/10/2026 |
| `vitaHealth-UPC/web-services` | `fix/backend-architecture` | [`56e9b76`](https://github.com/vitaHealth-UPC/web-services/commit/56e9b76) | `fix: minor changes` | Agrega los controladores de sesión social y de recuperación de contraseña. | 27/10/2026 |


#### 4.2.2.8. Software Deployment Evidence for Sprint Review

En este Sprint no cambió la infraestructura: seguimos con GitHub Pages para el Landing Page, Render para los Web Services y Neon para la base de datos PostgreSQL, que configuramos en la sección 4.1.4 y desplegamos en el Sprint 1. Lo nuevo es que pasamos el backend a la rama `main` (release `v2.0.0`) y lo redesplegamos en Render con las 17 operaciones nuevas (sección 4.2.2.7) y las variables de entorno que esa versión exige. La aplicación Android no tuvo una distribución nueva en este Sprint, y la migración a Flutter todavía no se distribuye: por ahora se compila y se prueba con GitHub Actions.

| Producto | Plataforma | Configuración / evidencia | URL |
| --- | --- | --- | --- |
| Landing Page | GitHub Pages (GitHub Actions) | Sin cambios: sigue publicado desde el Sprint 1. | https://vitahealth-upc.github.io/landing-page/ |
| Web Services | Render (Web Service con Docker, plan Free; rama `main`) | Redespliegue del release `v2.0.0` (commit `9f6fd73`, 81 operaciones) con las variables de entorno nuevas. | https://web-services-yzxl.onrender.com |
| Base de datos | Neon (PostgreSQL, proyecto TATA, branch `production`, base `tata`) | Sin cambios de infraestructura. Las tablas y columnas nuevas se crean al arrancar con `spring.jpa.hibernate.ddl-auto=update`. | (conexión privada) |
| Aplicación Android | Firebase App Distribution (proyecto `tata-vitahealth`, app `com.vitahealth.tata`) | Sin nueva distribución en este Sprint: sigue la versión 0.1.0 del Sprint 1. | Invitación por correo a los testers |
| Aplicación Flutter | GitHub Actions (`flutter-ci.yml`) | Compilación y pruebas en CI; todavía sin distribución. | https://github.com/vitaHealth-UPC/mobile-cross-platform |

**Web Services: redespliegue en Render**

El backend desplegado en el Sprint 1 tenía 64 operaciones. Para publicar las 81 de este Sprint, integramos el trabajo a `main` (commit `9f6fd73`, etiqueta `v2.0.0`, 11 de noviembre de 2026) y el servicio de Render pasó a desplegar esa rama. Render construye la imagen Docker del repositorio `vitaHealth-UPC/web-services`: el `Dockerfile` compila con Maven y Temurin 26 y ejecuta el JAR con el perfil `prod`. Además de las variables del Sprint 1 (`SPRING_DATASOURCE_URL`, `SPRING_DATASOURCE_USERNAME`, `SPRING_DATASOURCE_PASSWORD` y `TATA_DEMO_SEED`), esta versión exige estas, que se cargan solo como variables de entorno de Render y no quedan en el repositorio:

| Variable | Para qué sirve |
| --- | --- |
| `TATA_JWT_SECRET_BASE64` | Clave de 32 bytes en Base64 con la que se firman las sesiones. Sin ella el backend no arranca; si cambia, las sesiones anteriores dejan de valer. |
| `TATA_EMAIL_ENCRYPTION_ACTIVE_KEY_ID` y `TATA_EMAIL_ENCRYPTION_KEYS_<ID>` | Identificador de la clave activa y clave AES de 32 bytes en Base64 con la que se cifra la solicitud de verificación del correo. El arranque rechaza una clave ausente o inválida. |
| `TATA_FIREBASE_PROJECT_ID` | Proyecto de Firebase (`tata-vitahealth`) contra el que se verifica el token del inicio de sesión social. Sin él, `POST /api/v1/social-sessions` responde `503 SOCIAL_PROVIDER_UNAVAILABLE`. |
| `TATA_GOOGLE_SPEECH_ENABLED` | Activa el reconocimiento de voz de Google Cloud en la confirmación por voz (valor por defecto `false`). |
| `TATA_RESEND_API_KEY` y `TATA_RESEND_SENDER` | Credenciales del proveedor de correo Resend para enviar los códigos de verificación y de recuperación. |

Al guardar las variables nuevas, Render lanzó el despliegue (*Trigger: Environment updated by you*) sobre el commit `9f6fd73`. Terminó con *Deploy succeeded* en 23 segundos, el 12 de noviembre de 2026 a las 12:35 a. m. (GMT-5), y el servicio quedó en estado *Live* en https://web-services-yzxl.onrender.com. Al arrancar, Hibernate agrega a Neon las tablas y columnas nuevas (dispositivos push, notas de rutina, tema oscuro y política de notificación), sin borrar los datos existentes. Como el plan Free suspende la instancia cuando no recibe tráfico, la primera petición después de un rato puede tardar en responder.

![Render: despliegue exitoso del commit 9f6fd73 y servicio en estado Live.](assets/redeploy.jpeg)

*Figura 13. Render: despliegue exitoso del commit `9f6fd73` (release `v2.0.0`) y servicio en estado Live.*

**Commits de despliegue del Sprint**

Estos son los commits que cambian lo que se construye y se despliega en este Sprint: el release del backend que se publica en Render y el flujo de integración continua de la aplicación Flutter.

| Repository | Branch | Commit Id | Commit Message | Commit Message Body | Commited on (Date) |
| --- | --- | --- | --- | --- | --- |
| `vitaHealth-UPC/web-services` | `main` | [`9f6fd73`](https://github.com/vitaHealth-UPC/web-services/commit/9f6fd73) | `merge: minor changes` | Integra el backend del Sprint 2 a `main` (etiqueta `v2.0.0`), la rama que despliega Render. | 11/11/2026 |
| `vitaHealth-UPC/mobile-cross-platform` | `main` | [`ed44709`](https://github.com/vitaHealth-UPC/mobile-cross-platform/commit/ed44709) | `chore: initialize Flutter scaffold` | Incluye el flujo `flutter-ci.yml`. | 27/10/2026 |


#### 4.2.2.9. Team Collaboration Insights during Sprint

**Collaboration Evidence**

<!-- Incorporar capturas y enlaces a las contribuciones de los repositorios. -->

**Collaboration Analysis**

## 4.3. Validation Interviews

En esta sección registramos las entrevistas de validación del producto. A diferencia de las entrevistas de needfinding del Capítulo II, en estas sesiones los participantes de cada segmento objetivo interactúan con el Landing Page desplegado y con las aplicaciones implementadas. Así podemos contrastar las Hypothesis Statements con el comportamiento real de los usuarios. La sección incluye el diseño de las entrevistas, su registro y la evaluación según heurísticas.

### 4.3.1. Diseño de Entrevistas

Las sesiones de validación de este Sprint buscan comprobar si las funcionalidades core de Tata permiten que cada segmento cumpla su objetivo sin ayuda. Según lo definido en el Lean UX Problem Statement, Tata tiene éxito cuando los adultos mayores confirman sus medicamentos con poca o ninguna asistencia, y cuando los familiares aumentan su confianza en el seguimiento del tratamiento.

**Objetivos de validación**

| Hypothesis Statement relacionada | Qué observaremos en la sesión | Segmento |
| --- | --- | --- |
| Los adultos mayores de 68 a 85 años con baja alfabetización digital logran confirmar sus tomas sin fricción ni ayuda de terceros, con una interfaz de confirmación por voz o un solo toque. | Si el participante encuentra su próxima toma, la confirma con un toque y entiende el resultado sin intervención del moderador. | Adultos mayores |
| Los adultos mayores logran registrar sus confirmaciones sin interactuar con pantallas complejas. | Si el acceso con PIN, el inicio y la agenda se comprenden a la primera lectura, y cuántas veces el participante duda o pide ayuda. | Adultos mayores |
| Los familiares de 35 a 55 años obtienen tranquilidad al recibir información inmediata sobre la toma de medicación. | Si el participante configura el cuidado de su familiar y encuentra el estado de las tomas, las alertas y su detalle. | Familiares o cuidadores |
| El Landing Page comunica la propuesta de valor y conduce al registro. | Si el participante explica con sus palabras qué hace Tata, distingue los planes y llega al registro o al contacto. | Ambos segmentos |

**Participantes**

| Segmento | Cantidad | Criterios de selección |
| --- | --- | --- |
| Adultos mayores | De 3 a 5 entrevistas | Personas de 68 a 85 años que residen en Lima Metropolitana, toman al menos un medicamento de forma regular y usan un smartphone, aunque sea de forma básica. |
| Familiares o cuidadores | De 3 a 5 entrevistas | Personas de 35 a 55 años que residen en Lima Metropolitana, acompañan o supervisan a distancia el tratamiento de un adulto mayor y usan aplicaciones móviles a diario. |

Siempre que sea posible, entrevistamos a participantes que no formaron parte del needfinding, para que el conocimiento previo del producto no influya en los resultados.

**Elementos incluidos en la sesión**

| Elemento | Versión utilizada | Adultos mayores | Familiares o cuidadores |
| --- | --- | --- | --- |
| Landing Page | Desplegado en https://vitahealth-upc.github.io/landing-page/ | Propuesta de valor y funcionalidades | Propuesta de valor, funcionalidades, planes, registro y contacto |
| Aplicación Android nativa | Distribuida con Firebase App Distribution | Flujos del adulto mayor | Flujos del familiar o cuidador |
| Aplicación multiplataforma (Flutter) | Build instalado en un teléfono físico del equipo | Flujos del adulto mayor implementados en el Sprint | Registro, verificación y vínculo |
| Web Services | Desplegados en https://web-services-yzxl.onrender.com/ con cuentas y tratamientos de prueba creados para cada sesión | Datos de la próxima toma, agenda y confirmación | Datos de vínculo, tratamientos, resumen y alertas |

Usamos cuentas de prueba para que ningún participante registre sus datos de salud reales. Para los flujos que existen en ambas aplicaciones, alternamos la aplicación entre participantes, de modo que las dos versiones se validen sin duplicar tareas en una misma sesión.

**Estructura de la sesión**

| Bloque | Duración aproximada | Actividad |
| --- | --- | --- |
| 1. Bienvenida y consentimiento | 2 minutos | Explicamos el objetivo, aclaramos que evaluamos el producto y no a la persona, y pedimos permiso para grabar. |
| 2. Contexto | 3 minutos | Confirmamos los datos del participante: nombres, edad y distrito, y su relación con la medicación. |
| 3. Landing Page | 3 a 5 minutos | El participante explora la página y responde preguntas de comprensión. |
| 4. Tareas en las aplicaciones | 10 a 15 minutos | El participante realiza las tareas en voz alta (think aloud) mientras observamos sin intervenir, salvo que lo pida. |
| 5. Cierre | 3 a 5 minutos | Preguntas de cierre y calificación de facilidad de cada tarea en una escala del 1 al 7. |

En cada sesión participan un moderador, que guía las tareas, y un observador, que registra los tiempos, errores, dudas y pedidos de ayuda que alimentan la evaluación según heurísticas de la sección 4.3.3.

**User flows a validar con adultos mayores**

| Tarea | Instrucción para el participante | User flow | User Stories | Aplicación | Criterio de éxito observable |
| --- | --- | --- | --- | --- | --- |
| L1 | "Revise esta página y cuénteme para qué cree que sirve Tata." | WF16 | US-46, US-47 | Landing Page | Describe con sus palabras que Tata ayuda a recordar y confirmar medicamentos. |
| A1 | "Ingrese a la aplicación con su PIN y dígame cuál es su próxima toma." | WF01 | US-01, US-20 | Android nativa / Flutter | Ingresa y menciona el medicamento y la hora sin ayuda. |
| A2 | "Ya tomó su medicamento. Regístrelo en la aplicación." | WF02 | US-06 | Android nativa / Flutter | Confirma la toma con un toque e identifica el mensaje de confirmación. |
| A3 | "Revise qué medicamentos le tocan en la semana y cuáles ya tomó." | WF03-WF04 | US-21, US-24 | Android nativa / Flutter | Cambia de día en la agenda y distingue una toma confirmada de una pendiente. |
| A4 | "Haga que las letras de la aplicación se vean más grandes." | WF05 | US-35, US-36 | Android nativa | Encuentra la opción de accesibilidad y aplica el cambio. |
| A5 | "Confirme su siguiente toma hablándole al celular." | WF02 (voz) | US-06 | Android nativa | Completa la confirmación por voz o reintenta tras un aviso de voz no reconocida. |

**User flows a validar con familiares o cuidadores**

| Tarea | Instrucción para el participante | User flow | User Stories | Aplicación | Criterio de éxito observable |
| --- | --- | --- | --- | --- | --- |
| L1 | "Revise esta página, compare los planes y continúe hacia el registro." | WF16 | US-46, US-47, US-48, US-49 | Landing Page | Explica la propuesta de valor, distingue los planes y llega al registro o al contacto. |
| C1 | "Cree su cuenta y verifique su correo." | WF06 | US-10, US-11 | Android nativa / Flutter | Completa el registro y la verificación, y corrige los datos inválidos si aparecen. |
| C2 | "Registre a su familiar y compártale la invitación para vincularse." | WF06 | US-12, US-02, US-13 | Android nativa / Flutter | Registra el perfil y genera la invitación. El vínculo queda activo cuando el adulto da su consentimiento. |
| C3 | "Registre el medicamento de su familiar y configure el tratamiento." | WF07 | US-03, US-14, US-15, US-16, US-17 | Android nativa | Define el medicamento, la dosis, la frecuencia, el horario y el recordatorio, y activa el tratamiento. |
| C4 | "Revise cómo va su familiar hoy y atienda la alerta pendiente." | WF08-WF10 | US-25, US-27, US-07 | Android nativa | Encuentra el resumen, abre la alerta y entiende qué toma no se confirmó. |
| C5 | "Revise el historial reciente de tomas de su familiar." | WF08 | US-26 | Android nativa | Identifica las tomas confirmadas, tardías y omitidas. |

**Fuera del alcance de esta validación**

No validamos en este Sprint los flujos de inventario y reposición (US-40 a US-43), plan y suscripción (US-44 y US-45), ni la confirmación por voz en la aplicación Flutter. Estos flujos corresponden a Sprints posteriores o aún no están implementados en la versión multiplataforma.

**Preguntas de cierre**

*Adultos mayores*<br>
**1.** ¿Qué fue lo más fácil y lo más difícil de lo que hizo hoy? <br>
**2.** ¿Hubo algún texto, botón o ícono que no entendió o que le costó leer? <br>
**3.** ¿Preferiría confirmar sus tomas tocando la pantalla o hablándole al celular? ¿Por qué? <br>
**4.** ¿Cree que podría usar la aplicación todos los días sin ayuda de un familiar? <br>
**5.** ¿Qué le cambiaría a la aplicación para que le resulte más cómoda? <br>

*Familiares o cuidadores*<br>
**1.** ¿Qué tan seguro se sentiría de que su familiar tomó su medicamento con la información que vio hoy? <br>
**2.** ¿Qué información le faltó en el resumen o en las alertas para decidir qué hacer? <br>
**3.** ¿Le resultó claro cómo vincular a su familiar y por qué se le pide su consentimiento? <br>
**4.** ¿Con qué frecuencia revisaría la aplicación y por qué medio le gustaría recibir los avisos? <br>
**5.** Después de ver el Landing Page y la aplicación, ¿pagaría un plan como el que se ofrece? ¿Qué lo convencería? <br>

**Registro de resultados**

Para cada tarea registramos si se completó sin ayuda, con ayuda o no se completó, el tiempo empleado, los errores y dudas observados, y la calificación de facilidad del participante. Estos datos se presentan por entrevista en la sección 4.3.2 y sirven de evidencia para la evaluación según heurísticas de usabilidad, arquitectura de información e inclusive design de la sección 4.3.3.

### 4.3.2. Registro de Entrevistas

### 4.3.3. Evaluaciones según heurísticas
