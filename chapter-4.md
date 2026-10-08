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

Enlace a video: Pendiente.

#### 4.2.1.7. Services Documentation Evidence for Sprint Review

Swagger UI reúne los contratos REST del backend, sus parámetros y respuestas. Las operaciones protegidas utilizan un token Bearer.

Enlace a repositorio:

https://github.com/vitaHealth-UPC/web-services

Enlace a documentación:

https://web-services-yzxl.onrender.com/swagger-ui/index.html

**Treatment Management**

| Endpoint | Acción | HTTP | Parámetros | Respuesta y significado |
| --- | --- | --- | --- | --- |
| `/api/v1/older-adults/{olderAdultId}/treatments` | Crear un tratamiento (US-14) | POST | Path: `olderAdultId`.<br>Body: `caregiverId`, `name`. | `201` `{"id":"3f6c1d0e-8a52-4f0b-9c55-2f1f4d9a7b10","olderAdultId":"00000000-0000-0000-0000-000000000001","name":"Control de presión","status":"DRAFT","medicationId":null,"dose":null,"frequency":null,"scheduledTimes":null,"instructions":null,"reminderLeadMinutes":null}`<br>Crea el tratamiento en estado `DRAFT`, sin pauta. `400` si falta un dato; 403 si el cuidador no tiene un vínculo de cuidado activo con el adulto mayor. |
| `/api/v1/older-adults/{olderAdultId}/treatments` | Listar los tratamientos de un adulto mayor (US-19) | GET | Path: `olderAdultId`.<br>Query: `caregiverId`. | `200` `[{"id":"3f6c1d0e-8a52-4f0b-9c55-2f1f4d9a7b10","olderAdultId":"00000000-0000-0000-0000-000000000001","name":"Control de presión","status":"DRAFT","medicationId":null,"dose":null,"frequency":null,"scheduledTimes":null,"instructions":null,"reminderLeadMinutes":null}]`<br>Devuelve la lista, del más antiguo al más reciente; vacía si no hay tratamientos. 403 si el cuidador no tiene un vínculo de cuidado activo con el adulto mayor. |
| `/api/v1/treatments/{treatmentId}/regimen` | Configurar dosis, frecuencia, horarios, instrucciones y recordatorio (US-15, US-16, US-17) | PUT | Path: `treatmentId`.<br>Body: `caregiverId`, `medicationId`, `dose`, `frequency`, `scheduledTimes` (al menos un horario), `instructions`, `reminderLeadMinutes` (0 a 1440). | `200` `{"id":"3f6c1d0e-8a52-4f0b-9c55-2f1f4d9a7b10","olderAdultId":"00000000-0000-0000-0000-000000000001","name":"Control de presión","status":"DRAFT","medicationId":"7a1b2c3d-1111-4222-8333-444455556666","dose":"1 comprimido","frequency":"DAILY","scheduledTimes":["08:00:00","20:00:00"],"instructions":"Con un vaso de agua","reminderLeadMinutes":10}`<br>Devuelve el tratamiento con su pauta. `400` si la pauta es inválida; `404` si no existe el tratamiento o el medicamento; `409` si el medicamento está inactivo; 403 si el cuidador no tiene un vínculo de cuidado activo con el adulto mayor. |
| `/api/v1/treatments/{treatmentId}/activation` | Activar un tratamiento (US-18) | POST | Path: `treatmentId`.<br>Query: `caregiverId`. | `200` `{"id":"3f6c1d0e-8a52-4f0b-9c55-2f1f4d9a7b10","olderAdultId":"00000000-0000-0000-0000-000000000001","name":"Control de presión","status":"ACTIVE","medicationId":"7a1b2c3d-1111-4222-8333-444455556666","dose":"1 comprimido","frequency":"DAILY","scheduledTimes":["08:00:00","20:00:00"],"instructions":"Con un vaso de agua","reminderLeadMinutes":10}`<br>El tratamiento pasa a `ACTIVE`. `409` si la pauta está incompleta o el medicamento está inactivo; `404` si no existe; 403 si el cuidador no tiene un vínculo de cuidado activo con el adulto mayor. |
| `/api/v1/treatments/{treatmentId}/pause` | Pausar un tratamiento (US-18) | POST | Path: `treatmentId`.<br>Query: `caregiverId`. | `200` `{"id":"3f6c1d0e-8a52-4f0b-9c55-2f1f4d9a7b10","olderAdultId":"00000000-0000-0000-0000-000000000001","name":"Control de presión","status":"PAUSED","medicationId":"7a1b2c3d-1111-4222-8333-444455556666","dose":"1 comprimido","frequency":"DAILY","scheduledTimes":["08:00:00","20:00:00"],"instructions":"Con un vaso de agua","reminderLeadMinutes":10}`<br>El tratamiento pasa a `PAUSED` y conserva la pauta y el historial. `409` si no estaba activo; `404` si no existe; 403 si el cuidador no tiene un vínculo de cuidado activo con el adulto mayor. |
| `/api/v1/treatments/{treatmentId}/resume` | Reanudar un tratamiento pausado | POST | Path: `treatmentId`.<br>Query: `caregiverId`. | `200` `{"id":"3f6c1d0e-8a52-4f0b-9c55-2f1f4d9a7b10","olderAdultId":"00000000-0000-0000-0000-000000000001","name":"Control de presión","status":"ACTIVE","medicationId":"7a1b2c3d-1111-4222-8333-444455556666","dose":"1 comprimido","frequency":"DAILY","scheduledTimes":["08:00:00","20:00:00"],"instructions":"Con un vaso de agua","reminderLeadMinutes":10}`<br>El tratamiento vuelve a `ACTIVE`. `409` si no estaba pausado o su medicamento está inactivo; `404` si no existe; 403 si el cuidador no tiene un vínculo de cuidado activo con el adulto mayor. |
| `/api/v1/treatments/{treatmentId}` | Consultar el detalle de un tratamiento (US-19) | GET | Path: `treatmentId`.<br>Query: `caregiverId`. | `200` `{"id":"3f6c1d0e-8a52-4f0b-9c55-2f1f4d9a7b10","olderAdultId":"00000000-0000-0000-0000-000000000001","name":"Control de presión","status":"ACTIVE","medicationId":"7a1b2c3d-1111-4222-8333-444455556666","dose":"1 comprimido","frequency":"DAILY","scheduledTimes":["08:00:00","20:00:00"],"instructions":"Con un vaso de agua","reminderLeadMinutes":10}`<br>Devuelve el tratamiento con su pauta; los campos de la pauta son `null` mientras esté incompleto. `404` si no existe; 403 si el cuidador no tiene un vínculo de cuidado activo con el adulto mayor. |
| `/api/v1/older-adults/{olderAdultId}/medications` | Registrar un medicamento (US-03) | POST | Path: `olderAdultId`.<br>Body: `caregiverId`, `name`, `presentation`. | `201` `{"id":"7a1b2c3d-1111-4222-8333-444455556666","olderAdultId":"00000000-0000-0000-0000-000000000001","name":"Losartán","presentation":"50 mg, tableta","active":true}`<br>Crea el medicamento activo del adulto mayor. `400` si falta un dato obligatorio; 403 si el cuidador no tiene un vínculo de cuidado activo con el adulto mayor. |
| `/api/v1/older-adults/{olderAdultId}/medications` | Listar los medicamentos de un adulto mayor (US-03) | GET | Path: `olderAdultId`.<br>Query: `caregiverId`. | `200` `[{"id":"7a1b2c3d-1111-4222-8333-444455556666","olderAdultId":"00000000-0000-0000-0000-000000000001","name":"Losartán","presentation":"50 mg, tableta","active":true}]`<br>Devuelve los medicamentos ordenados por nombre, incluidos los inactivos; vacía si no hay ninguno. 403 si el cuidador no tiene un vínculo de cuidado activo con el adulto mayor. |
| `/api/v1/medications/{medicationId}` | Editar un medicamento (US-04) | PUT | Path: `medicationId`.<br>Body: `caregiverId`, `name`, `presentation`. | `200` `{"id":"7a1b2c3d-1111-4222-8333-444455556666","olderAdultId":"00000000-0000-0000-0000-000000000001","name":"Losartán","presentation":"100 mg, tableta","active":true}`<br>Cambia el nombre y la presentación; los tratamientos que lo usan republican su agenda. `400` si falta un dato; `404` si no existe; `409` si está inactivo; 403 si el cuidador no tiene un vínculo de cuidado activo con el adulto mayor. |
| `/api/v1/medications/{medicationId}/deactivation` | Desactivar un medicamento (US-04) | POST | Path: `medicationId`.<br>Query: `caregiverId`. | `200` `{"id":"7a1b2c3d-1111-4222-8333-444455556666","olderAdultId":"00000000-0000-0000-0000-000000000001","name":"Losartán","presentation":"50 mg, tableta","active":false}`<br>El medicamento queda inactivo y conserva su historial; un tratamiento activo que lo use se pausa. `404` si no existe; 403 si el cuidador no tiene un vínculo de cuidado activo con el adulto mayor. |
| `/api/v1/medications/{medicationId}` | Consultar el detalle de un medicamento | GET | Path: `medicationId`.<br>Query: `caregiverId`. | `200` `{"id":"7a1b2c3d-1111-4222-8333-444455556666","olderAdultId":"00000000-0000-0000-0000-000000000001","name":"Losartán","presentation":"50 mg, tableta","active":true}`<br>Devuelve el medicamento. `404` si no existe; 403 si el cuidador no tiene un vínculo de cuidado activo con el adulto mayor. |

**Accessibility & Preferences**

| Endpoint | Acción | HTTP | Parámetros | Respuesta y significado |
| --- | --- | --- | --- | --- |
| `/api/v1/users/{userId}/preferences` | Consultar las preferencias de un usuario (US-35, US-36) | GET | Path: `userId`. | `200` `{"userId":"00000000-0000-0000-0000-000000000001","textSize":"LARGE","highContrast":false,"reducedMotion":false,"readingAssistance":false,"voiceConfirmationEnabled":true,"quietHours":{"start":"22:00:00","end":"07:00:00"},"notificationChannels":[{"type":"PUSH","enabled":true},{"type":"SMS","enabled":false},{"type":"EMAIL","enabled":false}]}`<br>Devuelve las preferencias de accesibilidad y de notificación. Un usuario que nunca guardó nada recibe los valores por defecto, que se guardan en esa primera lectura. |
| `/api/v1/users/{userId}/preferences/text-size` | Cambiar el tamaño de texto (US-35) | PUT | Path: `userId`.<br>Body: `textSize` (`SMALL`, `MEDIUM`, `LARGE` o `EXTRA_LARGE`). | `200` `{"userId":"00000000-0000-0000-0000-000000000001","textSize":"LARGE","highContrast":false,"reducedMotion":false,"readingAssistance":false,"voiceConfirmationEnabled":true,"quietHours":{"start":"22:00:00","end":"07:00:00"},"notificationChannels":[{"type":"PUSH","enabled":true},{"type":"SMS","enabled":false},{"type":"EMAIL","enabled":false}]}`<br>Devuelve las preferencias actualizadas. Cada cambio se conserva para las próximas sesiones. `400` si el tamaño no es válido. |
| `/api/v1/users/{userId}/preferences/contrast` | Activar o desactivar el contraste reforzado (US-36) | PUT | Path: `userId`.<br>Body: `enabled` (booleano). | `200` `{"userId":"00000000-0000-0000-0000-000000000001","textSize":"LARGE","highContrast":true,"reducedMotion":false,"readingAssistance":false,"voiceConfirmationEnabled":true,"quietHours":{"start":"22:00:00","end":"07:00:00"},"notificationChannels":[{"type":"PUSH","enabled":true},{"type":"SMS","enabled":false},{"type":"EMAIL","enabled":false}]}`<br>Devuelve las preferencias actualizadas. Cada cambio se conserva para las próximas sesiones. |
| `/api/v1/users/{userId}/preferences/reduced-motion` | Activar o desactivar la reducción de movimiento (US-37) | PUT | Path: `userId`.<br>Body: `enabled` (booleano). | `200` `{"userId":"00000000-0000-0000-0000-000000000001","textSize":"LARGE","highContrast":false,"reducedMotion":true,"readingAssistance":false,"voiceConfirmationEnabled":true,"quietHours":{"start":"22:00:00","end":"07:00:00"},"notificationChannels":[{"type":"PUSH","enabled":true},{"type":"SMS","enabled":false},{"type":"EMAIL","enabled":false}]}`<br>Devuelve las preferencias actualizadas. Cada cambio se conserva para las próximas sesiones. |
| `/api/v1/users/{userId}/preferences/reading-assistance` | Activar o desactivar la ayuda de lectura (US-38) | PUT | Path: `userId`.<br>Body: `enabled` (booleano). | `200` `{"userId":"00000000-0000-0000-0000-000000000001","textSize":"LARGE","highContrast":false,"reducedMotion":false,"readingAssistance":true,"voiceConfirmationEnabled":true,"quietHours":{"start":"22:00:00","end":"07:00:00"},"notificationChannels":[{"type":"PUSH","enabled":true},{"type":"SMS","enabled":false},{"type":"EMAIL","enabled":false}]}`<br>Devuelve las preferencias actualizadas. Cada cambio se conserva para las próximas sesiones. |
| `/api/v1/users/{userId}/preferences/voice-confirmation` | Activar o desactivar la confirmación por voz (US-06) | PUT | Path: `userId`.<br>Body: `enabled` (booleano). | `200` `{"userId":"00000000-0000-0000-0000-000000000001","textSize":"LARGE","highContrast":false,"reducedMotion":false,"readingAssistance":false,"voiceConfirmationEnabled":false,"quietHours":{"start":"22:00:00","end":"07:00:00"},"notificationChannels":[{"type":"PUSH","enabled":true},{"type":"SMS","enabled":false},{"type":"EMAIL","enabled":false}]}`<br>Devuelve las preferencias actualizadas. Solo guarda la preferencia; el reconocimiento de voz pertenece a Intake Execution. |
| `/api/v1/users/{userId}/notification-preferences` | Configurar el horario de silencio y los canales de notificación (US-39) | PUT | Path: `userId`.<br>Body: `quietHours` (`start` y `end`, o `null` para quitarlo), `channels` (lista de `type` y `enabled`; `PUSH`, `SMS` o `EMAIL`, sin repetir). | `200` `{"userId":"00000000-0000-0000-0000-000000000001","textSize":"LARGE","highContrast":false,"reducedMotion":false,"readingAssistance":false,"voiceConfirmationEnabled":true,"quietHours":{"start":"22:00:00","end":"07:00:00"},"notificationChannels":[{"type":"PUSH","enabled":true},{"type":"SMS","enabled":false},{"type":"EMAIL","enabled":false}]}`<br>Reemplaza ambos ajustes a la vez y devuelve las preferencias. El horario puede cruzar la medianoche. `400` si inicio y fin son iguales o se repite un canal. |

**Identity & Subscription**

| Endpoint | Acción | HTTP | Parámetros | Respuesta y significado |
| --- | --- | --- | --- | --- |
| `/api/v1/email-verification-requests` | Solicitar el código de verificación del correo | POST | Body: `email`. | `202` `{"id":"string","name":"string","email":"string","status":"string","accessToken":"string","expiresAt":"2026-10-06T08:00:00Z"}`<br>Solicita el envío del código de verificación; responde `202`. `400` si el correo falta o no es válido. No requiere token. |
| `/api/v1/accounts` | Crear una cuenta | POST | Body: `name`, `email`, `password`. | `201` `{"id":"string","name":"string","email":"string","status":"string","accessToken":"string","expiresAt":"2026-10-06T08:00:00Z"}`<br>Crea la cuenta y devuelve sus datos y el token de acceso. `400` si faltan datos. No requiere token. |
| `/api/v1/accounts/verification` | Verificar el correo con el código recibido | POST | Body: `email`, `code`. | `200` `{"id":"string","name":"string","email":"string","status":"string","accessToken":"string","expiresAt":"2026-10-06T08:00:00Z"}`<br>Valida el código y devuelve los datos de la cuenta con el token de acceso. `400` si el código es inválido. No requiere token. |
| `/api/v1/sessions` | Iniciar sesión de un cuidador o familiar | POST | Body: `email`, `password`. | `200` `{"accountId":"string","accessToken":"string","expiresAt":"2026-10-06T08:00:00Z"}`<br>Devuelve el `accessToken` y su vencimiento. `400` si faltan datos. No requiere token. |
| `/api/v1/sessions/current` | Consultar la sesión actual | GET | Ninguno. | `200` `{"subjectId":"string","role":"CAREGIVER","expiresAt":"2026-10-06T08:00:00Z","careLinkId":"string","name":"string"}`<br>Devuelve el sujeto de la sesión, su rol (`CAREGIVER` u otro), el vínculo de cuidado y el vencimiento. |
| `/api/v1/sessions` | Cerrar la sesión | DELETE | Header: `Authorization`. | `204` Sin cuerpo<br>Invalida el token enviado en `Authorization`; responde `204` sin cuerpo. |
| `/api/v1/pin-credentials` | Registrar el PIN de un adulto mayor | POST | Body: `olderAdultId`, `pin`. | `201` Sin cuerpo<br>Guarda el PIN con el que el adulto mayor iniciará sesión; responde `201` sin cuerpo. |
| `/api/v1/pin-sessions` | Iniciar sesión de un adulto mayor con PIN | POST | Body: `olderAdultId`, `pin`. | `200` `{"olderAdultId":"string","accessToken":"string","expiresAt":"2026-10-06T08:00:00Z"}`<br>Devuelve el `accessToken` de la sesión del adulto mayor y su vencimiento. `400` si faltan datos. No requiere token. |
| `/api/v1/plans` | Listar los planes disponibles | GET | Ninguno. | `200` `[{"code":"string","name":"string","monthlyPrice":1,"currency":"string","capabilities":["REMINDERS"]}]`<br>Devuelve los planes con su precio mensual, moneda y capacidades. No requiere token. |
| `/api/v1/accounts/{accountId}/subscription` | Consultar la suscripción de una cuenta (US-44) | GET | Path: `accountId`. | `200` `{"accountId":"string","plan":{"code":"string","name":"string","monthlyPrice":1,"currency":"string","capabilities":["REMINDERS"]},"status":"ACTIVE","renewsAt":"2026-10-06T08:00:00Z"}`<br>Devuelve el plan vigente, el estado de la suscripción, la fecha de renovación y las capacidades habilitadas. |
| `/api/v1/accounts/{accountId}/subscription` | Activar o cambiar el plan de una cuenta (US-45) | PUT | Path: `accountId`.<br>Body: `planCode`. | `200` `{"accountId":"string","plan":{"code":"string","name":"string","monthlyPrice":1,"currency":"string","capabilities":["REMINDERS"]},"status":"ACTIVE","renewsAt":"2026-10-06T08:00:00Z"}`<br>Aplica el plan indicado por `planCode` y devuelve la suscripción resultante. |

**Care Link**

| Endpoint | Acción | HTTP | Parámetros | Respuesta y significado |
| --- | --- | --- | --- | --- |
| `/api/v1/older-adults` | Registrar un adulto mayor | POST | Body: `caregiverId`, `fullName`, `birthDate`, `emergencyContactName`, `emergencyContactRelationship`, `emergencyContactPhone`. | `201` `{"id":"string","registeredByCaregiverId":"string","fullName":"string","birthDate":"2026-10-06","emergencyContactName":"string","emergencyContactRelationship":"string","emergencyContactPhone":"string","createdAt":"2026-10-06T08:00:00Z"}`<br>Crea el adulto mayor con su contacto de emergencia y devuelve sus datos; responde `201`. |
| `/api/v1/older-adults/{olderAdultId}` | Consultar los datos de un adulto mayor | GET | Path: `olderAdultId`. | `200` `{"id":"string","registeredByCaregiverId":"string","fullName":"string","birthDate":"2026-10-06","emergencyContactName":"string","emergencyContactRelationship":"string","emergencyContactPhone":"string","createdAt":"2026-10-06T08:00:00Z"}`<br>Devuelve los datos del adulto mayor y de su contacto de emergencia. |
| `/api/v1/care-links/linking-codes` | Generar un código de vinculación | POST | Body: `caregiverId`, `olderAdultId`. | `201` `{"id":"string","caregiverId":"string","olderAdultId":"string","status":"PENDING","linkingCode":"string","codeExpiresAt":"2026-10-06T08:00:00Z","codeUsedAt":"2026-10-06T08:00:00Z","consentGranted":true,"consentRecordedAt":"2026-10-06T08:00:00Z","confirmedAt":"2026-10-06T08:00:00Z","accessToken":"string","expiresAt":"2026-10-06T08:00:00Z"}`<br>Crea un vínculo en estado `PENDING` con un código y su vencimiento; responde `201`. |
| `/api/v1/care-links/acceptances` | Aceptar un código de vinculación | POST | Body: `caregiverId`, `code`. | `200` `{"id":"string","caregiverId":"string","olderAdultId":"string","status":"PENDING","linkingCode":"string","codeExpiresAt":"2026-10-06T08:00:00Z","codeUsedAt":"2026-10-06T08:00:00Z","consentGranted":true,"consentRecordedAt":"2026-10-06T08:00:00Z","confirmedAt":"2026-10-06T08:00:00Z","accessToken":"string","expiresAt":"2026-10-06T08:00:00Z"}`<br>Usa el código para asociar al cuidador con el vínculo y devuelve el vínculo actualizado. |
| `/api/v1/care-links/{careLinkId}/consent` | Registrar el consentimiento del adulto mayor | POST | Path: `careLinkId`.<br>Body: `accepted`. | `200` `{"id":"string","caregiverId":"string","olderAdultId":"string","status":"PENDING","linkingCode":"string","codeExpiresAt":"2026-10-06T08:00:00Z","codeUsedAt":"2026-10-06T08:00:00Z","consentGranted":true,"consentRecordedAt":"2026-10-06T08:00:00Z","confirmedAt":"2026-10-06T08:00:00Z","accessToken":"string","expiresAt":"2026-10-06T08:00:00Z"}`<br>Guarda si el adulto mayor aceptó (`accepted`) y devuelve el vínculo con la fecha del consentimiento. |
| `/api/v1/care-links` | Listar los vínculos confirmados de un cuidador | GET | Query: `caregiverId`. | `200` `[{"id":"string","olderAdultId":"string","olderAdultName":"string","confirmedAt":"2026-10-06T08:00:00Z"}]`<br>Devuelve los vínculos activos con consentimiento, del más reciente al más antiguo; vacía si no hay ninguno. |
| `/api/v1/care-links/{careLinkId}` | Consultar un vínculo de cuidado | GET | Path: `careLinkId`. | `200` `{"id":"string","caregiverId":"string","olderAdultId":"string","status":"PENDING","linkingCode":"string","codeExpiresAt":"2026-10-06T08:00:00Z","codeUsedAt":"2026-10-06T08:00:00Z","consentGranted":true,"consentRecordedAt":"2026-10-06T08:00:00Z","confirmedAt":"2026-10-06T08:00:00Z","accessToken":"string","expiresAt":"2026-10-06T08:00:00Z"}`<br>Devuelve el vínculo con su estado, código y consentimiento. |
| `/api/v1/care-links/authorization` | Verificar si un cuidador está autorizado sobre un adulto mayor | GET | Query: `caregiverId`, `olderAdultId`. | `200` `true`<br>Devuelve `true` si existe un vínculo activo entre ambos y `false` en caso contrario. |

**Intake Execution**

| Endpoint | Acción | HTTP | Parámetros | Respuesta y significado |
| --- | --- | --- | --- | --- |
| `/api/v1/older-adults/{olderAdultId}/intakes/next` | Consultar la próxima toma | GET | Path: `olderAdultId`. | `200` `{"id":"string","treatmentId":"string","medicationId":"string","olderAdultId":"string","medicationName":"string","dose":"string","instructions":"string","scheduledAt":"2026-10-06T08:00:00Z","status":"PENDING","confirmedAt":"2026-10-06T08:00:00Z","confirmationChannel":"TOUCH"}`<br>Devuelve la próxima toma programada del adulto mayor. |
| `/api/v1/older-adults/{olderAdultId}/intakes/agenda` | Consultar la agenda de tomas de un período | GET | Path: `olderAdultId`.<br>Query: `from`, `to`. | `200` `[{"id":"string","treatmentId":"string","medicationId":"string","olderAdultId":"string","medicationName":"string","dose":"string","instructions":"string","scheduledAt":"2026-10-06T08:00:00Z","status":"PENDING","confirmedAt":"2026-10-06T08:00:00Z","confirmationChannel":"TOUCH"}]`<br>Devuelve las tomas programadas entre `from` y `to`. |
| `/api/v1/intakes/{intakeId}` | Consultar una toma | GET | Path: `intakeId`. | `200` `{"id":"string","treatmentId":"string","medicationId":"string","olderAdultId":"string","medicationName":"string","dose":"string","instructions":"string","scheduledAt":"2026-10-06T08:00:00Z","status":"PENDING","confirmedAt":"2026-10-06T08:00:00Z","confirmationChannel":"TOUCH"}`<br>Devuelve el medicamento, la dosis, las instrucciones, el horario y el estado de la toma. |
| `/api/v1/intakes/{intakeId}/confirmation` | Confirmar una toma (US-05) | POST | Path: `intakeId`.<br>Body: `channel`. | `200` `{"id":"string","treatmentId":"string","medicationId":"string","olderAdultId":"string","medicationName":"string","dose":"string","instructions":"string","scheduledAt":"2026-10-06T08:00:00Z","status":"PENDING","confirmedAt":"2026-10-06T08:00:00Z","confirmationChannel":"TOUCH"}`<br>Registra la confirmación por el canal indicado (`TOUCH`) y devuelve la toma actualizada. |
| `/api/v1/intakes/{intakeId}/voice-confirmation` | Confirmar una toma por voz (US-06) | POST | Path: `intakeId`.<br>Query: `language` (opcional).<br>Body: `audio`. | `200` `{"status":"CONFIRMED","transcript":"string","confidence":1,"intake":{"id":"string","treatmentId":"string","medicationId":"string","olderAdultId":"string","medicationName":"string","dose":"string","instructions":"string","scheduledAt":"2026-10-06T08:00:00Z","status":"PENDING","confirmedAt":"2026-10-06T08:00:00Z","confirmationChannel":"TOUCH"}}`<br>Procesa el audio con el servicio de reconocimiento de voz; solo una confirmación reconocida y validada cambia el estado de la toma. |

**Family Monitoring**

| Endpoint | Acción | HTTP | Parámetros | Respuesta y significado |
| --- | --- | --- | --- | --- |
| `/api/v1/older-adults/{olderAdultId}/status` | Consultar el estado reciente de un adulto mayor (US-25) | GET | Path: `olderAdultId`.<br>Query: `caregiverId`. | `200` `{"nextIntakeAt":"2026-10-05T21:00:00Z","lastIntakeStatus":"CONFIRMED","hasOpenAlert":true,"openAlerts":[{"id":1,"intakeId":"101","medicationName":"Losartan 50 mg","scheduledAt":"2026-10-05T13:00:00Z","reason":"Intake not confirmed within the grace period","status":"OPEN","openedAt":"2026-10-05T13:30:00Z","closedAt":null}],"weeklyAdherence":{"confirmedIntakes":1,"totalIntakes":1},"lowStock":[{"medicationId":"7a1b2c3d-1111-4222-8333-444455556666","medicationName":"Losartán","remainingStock":4,"replenishmentThreshold":5,"detectedAt":"2026-10-06T12:00:00Z"}],"adherenceInsights":[{"medicationId":"7a1b2c3d-1111-4222-8333-444455556666","medicationName":"Losartán","omissionDays":3,"firstDay":"2026-10-01","lastDay":"2026-10-03","detectedAt":"2026-10-06T08:00:00Z"}]}`<br>Devuelve la próxima toma, el resultado de la última y las alertas pendientes. `404` si el adulto mayor no tiene seguimiento activo. |
| `/api/v1/older-adults/{olderAdultId}/intakes` | Consultar el historial reciente de tomas (US-26) | GET | Path: `olderAdultId`.<br>Query: `caregiverId`, `days` (opcional). | `200` `[{"intakeId":"101","medicationName":"Losartan 50 mg","scheduledAt":"2026-10-05T13:00:00Z","status":"CONFIRMED"}]`<br>Devuelve las tomas de los últimos días, de la más reciente a la más antigua; vacía si no hay registros. `400` si `days` es inválido; `404` si no hay seguimiento activo. |
| `/api/v1/older-adults/{olderAdultId}/contact-channel` | Consultar el canal de contacto de un adulto mayor (US-29) | GET | Path: `olderAdultId`.<br>Query: `caregiverId`. | `200` `{"type":"PHONE","value":"+51 999 888 777"}`<br>Devuelve el canal con el que el cuidador puede comunicarse tras una alerta. `404` si no hay seguimiento o canal. |
| `/api/v1/older-adults/{olderAdultId}/alerts/{alertId}` | Consultar el detalle de una alerta (US-27) | GET | Path: `olderAdultId`, `alertId`.<br>Query: `caregiverId`. | `200` `{"id":1,"intakeId":"101","medicationName":"Losartan 50 mg","scheduledAt":"2026-10-05T13:00:00Z","reason":"Intake not confirmed within the grace period","status":"OPEN","openedAt":"2026-10-05T13:30:00Z","closedAt":null}`<br>Devuelve el medicamento, el horario, el estado y el motivo de la alerta. `404` si no existe. |
| `/api/v1/older-adults/{olderAdultId}/alerts/{alertId}/status` | Actualizar el estado de seguimiento de una alerta (US-31) | PUT | Path: `olderAdultId`, `alertId`.<br>Query: `caregiverId`.<br>Body: `status`. | `200` `{"id":1,"intakeId":"101","medicationName":"Losartan 50 mg","scheduledAt":"2026-10-05T13:00:00Z","reason":"Intake not confirmed within the grace period","status":"OPEN","openedAt":"2026-10-05T13:30:00Z","closedAt":null}`<br>`ATTENDED` registra que el cuidador actuó; `CLOSED` la quita de las pendientes y la conserva en el historial. `400` si el estado no es válido; `404` si no existe; `409` si no puede pasar a ese estado. |
| `/api/v1/older-adults/{olderAdultId}/notes` | Listar las notas de seguimiento (US-30) | GET | Path: `olderAdultId`.<br>Query: `caregiverId`. | `200` `[{"id":1,"text":"I called her and she had already taken the pill.","recordedAt":"2026-10-05T14:10:00Z","familiarId":"1"}]`<br>Devuelve las notas registradas, de la más reciente a la más antigua; vacía si no hay. `404` si no hay seguimiento activo. |
| `/api/v1/older-adults/{olderAdultId}/notes` | Registrar una nota de seguimiento (US-30) | POST | Path: `olderAdultId`.<br>Body: `familiarId`, `text`. | `201` `{"id":1,"text":"I called her and she had already taken the pill.","recordedAt":"2026-10-05T14:10:00Z","familiarId":"1"}`<br>Guarda la nota con su fecha y su autor; responde `201`. `400` si la nota es inválida; `404` si no hay seguimiento activo. |

**Adherence Analytics**

| Endpoint | Acción | HTTP | Parámetros | Respuesta y significado |
| --- | --- | --- | --- | --- |
| `/api/v1/older-adults/{olderAdultId}/adherence/weekly` | Consultar la adherencia semanal | GET | Path: `olderAdultId`.<br>Query: `from`, `to`. | `200` `{"olderAdultId":"string","from":"2026-10-06T08:00:00Z","to":"2026-10-06T08:00:00Z","confirmedIntakes":1,"totalIntakes":1,"percentage":1,"onTimeIntakes":1,"lateIntakes":1,"omittedIntakes":1}`<br>Devuelve las tomas confirmadas, a tiempo, tardías y omitidas del período, con el porcentaje de adherencia. |
| `/api/v1/older-adults/{olderAdultId}/adherence/summary` | Consultar el resumen de adherencia | GET | Path: `olderAdultId`.<br>Query: `days` (opcional), `zone` (opcional). | `200` `{"periodDays":1,"scheduledCount":1,"adherencePercent":1,"adherenceChangePercent":1,"onTimePercent":1,"onTimeChangePercent":1,"lateCount":1,"omittedCount":1,"trend":[{"date":"2026-10-06","adherencePercent":1}],"recentIntakes":[{"scheduledAt":"2026-10-06T08:00:00Z","medicationName":"string","status":"string","minutesLate":1}],"pattern":{"timeBand":"string","omittedCount":1,"lateCount":1}}`<br>Devuelve los porcentajes de adherencia y puntualidad con el cambio frente al período anterior, la tendencia y las tomas recientes. `204` si no hay tomas definitivas; `400` si el período o la zona son inválidos. |
| `/api/v1/older-adults/{olderAdultId}/adherence/recommendations` | Consultar las recomendaciones de adherencia | GET | Path: `olderAdultId`.<br>Query: `from`, `to`, `zone` (opcional). | `200` `[{"medicationId":"string","code":"string","evidenceDays":1}]`<br>Devuelve recomendaciones por medicamento con los días de evidencia. |
| `/api/v1/older-adults/{olderAdultId}/adherence/patterns` | Consultar los patrones de omisión | GET | Path: `olderAdultId`.<br>Query: `from`, `to`, `zone` (opcional). | `200` `[{"medicationId":"string","omissionDays":1,"firstDay":"2026-10-06","lastDay":"2026-10-06"}]`<br>Devuelve, por medicamento, los días de omisión y el primer y último día. |
| `/api/v1/older-adults/{olderAdultId}/adherence/insights` | Consultar las recomendaciones de seguimiento según patrones | GET | Path: `olderAdultId`.<br>Query: `days` (opcional), `zone` (opcional). | `200` `{"periodDays":1,"pattern":{"type":"string","timeBand":"string","omittedCount":1,"lateCount":1,"fromHour":1,"toHour":1},"concentration":[[1]],"recommendations":["string"]}`<br>Devuelve el patrón detectado, la concentración por franja y las recomendaciones; solo tratan recordatorios, horarios y seguimiento, nunca la dosis. `204` si no hay evidencia suficiente; `400` si el período o la zona son inválidos. |
| `/api/v1/older-adults/{olderAdultId}/adherence/insight` | Consultar las recomendaciones de seguimiento según patrones (ruta alterna) | GET | Path: `olderAdultId`.<br>Query: `days` (opcional), `zone` (opcional). | `200` `{"periodDays":1,"pattern":{"type":"string","timeBand":"string","omittedCount":1,"lateCount":1,"fromHour":1,"toHour":1},"concentration":[[1]],"recommendations":["string"]}`<br>Misma respuesta que `/adherence/insights`. |
| `/api/v1/older-adults/{olderAdultId}/adherence/history` | Consultar el historial de tomas del período | GET | Path: `olderAdultId`.<br>Query: `from`, `to`. | `200` `[{"medicationId":"string","scheduledAt":"2026-10-06T08:00:00Z","status":"PENDING"}]`<br>Devuelve cada toma con su medicamento, horario y estado entre `from` y `to`. |
| `/api/v1/older-adults/{olderAdultId}/adherence/consolidations` | Consolidar la adherencia de un período | POST | Path: `olderAdultId`.<br>Query: `from`, `to`, `zone` (opcional). | `200` `{"id":"string","olderAdultId":"string","from":"2026-10-06T08:00:00Z","to":"2026-10-06T08:00:00Z","zone":"string","consolidatedAt":"2026-10-06T08:00:00Z","confirmedIntakes":1,"totalIntakes":1,"percentage":1,"onTimeIntakes":1,"lateIntakes":1,"omittedIntakes":1,"patterns":[{"medicationId":"string","omissionDays":1,"firstDay":"2026-10-06","lastDay":"2026-10-06"}],"minimumOmissionDays":1}`<br>Calcula y guarda una captura de la adherencia entre `from` y `to` y la devuelve. |
| `/api/v1/older-adults/{olderAdultId}/adherence/consolidations/{snapshotId}` | Consultar una consolidación de adherencia | GET | Path: `olderAdultId`, `snapshotId`. | `200` `{"id":"string","olderAdultId":"string","from":"2026-10-06T08:00:00Z","to":"2026-10-06T08:00:00Z","zone":"string","consolidatedAt":"2026-10-06T08:00:00Z","confirmedIntakes":1,"totalIntakes":1,"percentage":1,"onTimeIntakes":1,"lateIntakes":1,"omittedIntakes":1,"patterns":[{"medicationId":"string","omissionDays":1,"firstDay":"2026-10-06","lastDay":"2026-10-06"}],"minimumOmissionDays":1}`<br>Devuelve la captura guardada con sus totales y porcentajes. |

**Inventory & Replenishment**

| Endpoint | Acción | HTTP | Parámetros | Respuesta y significado |
| --- | --- | --- | --- | --- |
| `/api/v1/inventories` | Registrar el inventario inicial de un medicamento (US-40) | POST | Body: `medicationId`, `initialQuantity`, `replenishmentThreshold`. | `201` `{"id":"string","medicationId":"string","remainingStock":12,"replenishmentThreshold":5,"lowStock":true,"batches":[{"id":"string","quantity":1,"registeredAt":"2026-10-06T08:00:00Z","lot":"string"}],"createdAt":"2026-10-06T08:00:00Z","updatedAt":"2026-10-06T08:00:00Z","daysRemaining":1,"dailyConsumptionUnits":1}`<br>Crea el stock con su primer lote y el umbral de reposición; solo existe un inventario por medicamento. `400` si faltan datos o la cantidad es inválida; `404` si el medicamento no existe; `409` si está inactivo o ya tiene inventario. |
| `/api/v1/inventories/{medicationId}/replenishments` | Registrar una reposición (US-43) | POST | Path: `medicationId`.<br>Body: `quantity`, `lot`. | `201` `{"id":"string","medicationId":"string","remainingStock":12,"replenishmentThreshold":5,"lowStock":true,"batches":[{"id":"string","quantity":1,"registeredAt":"2026-10-06T08:00:00Z","lot":"string"}],"createdAt":"2026-10-06T08:00:00Z","updatedAt":"2026-10-06T08:00:00Z","daysRemaining":1,"dailyConsumptionUnits":1}`<br>Agrega un lote y aumenta el stock; devuelve el inventario actualizado. `400` si faltan datos; `404` si no hay inventario; `409` si hubo una modificación concurrente. |
| `/api/v1/inventories/{medicationId}` | Consultar el stock de un medicamento (US-41, US-42) | GET | Path: `medicationId`. | `200` `{"id":"string","medicationId":"string","remainingStock":12,"replenishmentThreshold":5,"lowStock":true,"batches":[{"id":"string","quantity":1,"registeredAt":"2026-10-06T08:00:00Z","lot":"string"}],"createdAt":"2026-10-06T08:00:00Z","updatedAt":"2026-10-06T08:00:00Z","daysRemaining":1,"dailyConsumptionUnits":1}`<br>Devuelve las unidades restantes, el umbral, el indicador de stock bajo y los lotes. `404` si no hay inventario. |

**Estado del servicio**

| Endpoint | Acción | HTTP | Parámetros | Respuesta y significado |
| --- | --- | --- | --- | --- |
| `/health` | Verificar que el servicio está activo | GET | Ninguno. | `200` `null`<br>Devuelve el estado del servicio (`UP`). No requiere token. |
| `/actuator/health` | Verificar el estado del servicio (Actuator) | GET | Ninguno. | `200` `null`<br>Devuelve el estado del servicio (`UP`). No requiere token. |

**Capturas de la documentación**

Las capturas se tomaron ejecutando el backend en un entorno local con una base de datos en memoria y datos de muestra, desde Swagger UI con la opción *Try it out*.

<p align="center">
  <img src="assets/services-documentation/00-swagger-treatments.png" alt="Operaciones de tratamientos en Swagger UI" width="960">
</p>

*Figura. Operaciones de tratamientos en Swagger UI.*


<p align="center">
  <img src="assets/services-documentation/00-swagger-medications.png" alt="Operaciones de medicamentos en Swagger UI" width="960">
</p>

*Figura. Operaciones de medicamentos en Swagger UI.*


<p align="center">
  <img src="assets/services-documentation/00-swagger-accessibility.png" alt="Operaciones de accesibilidad en Swagger UI" width="960">
</p>

*Figura. Operaciones de accesibilidad en Swagger UI.*


<p align="center">
  <img src="assets/services-documentation/00-swagger-notification-preferences.png" alt="Preferencias de notificación en Swagger UI" width="960">
</p>

*Figura. Preferencias de notificación en Swagger UI.*


<p align="center">
  <img src="assets/services-documentation/01-registrar-medicamento.png" alt="Registro de medicamento" width="960">
</p>

*Figura. Registro de medicamento.*


<p align="center">
  <img src="assets/services-documentation/02-listar-medicamentos.png" alt="Consulta de medicamentos" width="960">
</p>

*Figura. Consulta de medicamentos.*


<p align="center">
  <img src="assets/services-documentation/03-editar-medicamento.png" alt="Edición de medicamento" width="960">
</p>

*Figura. Edición de medicamento.*


<p align="center">
  <img src="assets/services-documentation/04-crear-tratamiento.png" alt="Creación de tratamiento" width="960">
</p>

*Figura. Creación de tratamiento.*


<p align="center">
  <img src="assets/services-documentation/05-configurar-pauta.png" alt="Configuración de la pauta" width="960">
</p>

*Figura. Configuración de la pauta.*


<p align="center">
  <img src="assets/services-documentation/06-activar-tratamiento.png" alt="Activación del tratamiento" width="960">
</p>

*Figura. Activación del tratamiento.*


<p align="center">
  <img src="assets/services-documentation/07-detalle-tratamiento.png" alt="Consulta del tratamiento" width="960">
</p>

*Figura. Consulta del tratamiento.*


<p align="center">
  <img src="assets/services-documentation/08-pausar-tratamiento.png" alt="Pausa del tratamiento" width="960">
</p>

*Figura. Pausa del tratamiento.*


<p align="center">
  <img src="assets/services-documentation/09-desactivar-medicamento.png" alt="Desactivación del medicamento" width="960">
</p>

*Figura. Desactivación del medicamento.*


<p align="center">
  <img src="assets/services-documentation/10-error-403-sin-vinculo.png" alt="Respuesta de acceso sin vínculo autorizado" width="960">
</p>

*Figura. Respuesta de acceso sin vínculo autorizado.*


<p align="center">
  <img src="assets/services-documentation/11-consultar-preferencias.png" alt="Consulta de preferencias" width="960">
</p>

*Figura. Consulta de preferencias.*


<p align="center">
  <img src="assets/services-documentation/12-cambiar-tamano-texto.png" alt="Ajuste del tamaño de texto" width="960">
</p>

*Figura. Ajuste del tamaño de texto.*


<p align="center">
  <img src="assets/services-documentation/13-activar-contraste.png" alt="Activación del contraste" width="960">
</p>

*Figura. Activación del contraste.*


<p align="center">
  <img src="assets/services-documentation/14-horario-silencio-y-canales.png" alt="Configuración del horario de silencio y canales" width="960">
</p>

*Figura. Configuración del horario de silencio y canales.*


Las siguientes capturas muestran los grupos de endpoints de los demás Bounded Contexts en el Swagger UI desplegado.

<p align="center">
  <img src="assets/services-documentation/swagger-identity-subscription.png" alt="Cuenta y suscripción en Swagger UI" width="960">
</p>

*Figura. Cuenta y suscripción en Swagger UI.*


<p align="center">
  <img src="assets/services-documentation/swagger-care-link.png" alt="Vinculación de cuidado en Swagger UI" width="960">
</p>

*Figura. Vinculación de cuidado en Swagger UI.*


<p align="center">
  <img src="assets/services-documentation/swagger-intake-execution.png" alt="Tomas en Swagger UI" width="960">
</p>

*Figura. Tomas en Swagger UI.*


<p align="center">
  <img src="assets/services-documentation/swagger-family-monitoring.png" alt="Seguimiento familiar en Swagger UI" width="960">
</p>

*Figura. Seguimiento familiar en Swagger UI.*


<p align="center">
  <img src="assets/services-documentation/swagger-adherence-analytics.png" alt="Adherencia en Swagger UI" width="960">
</p>

*Figura. Adherencia en Swagger UI.*


<p align="center">
  <img src="assets/services-documentation/swagger-inventory.png" alt="Inventario en Swagger UI" width="960">
</p>

*Figura. Inventario en Swagger UI.*


(FALTA: capturas de ejecución con datos de muestra de los endpoints de los demás Bounded Contexts)

**Commits de documentación del Sprint**

Commits que agregan o modifican la documentación OpenAPI de los endpoints, integrados en la rama `develop`.

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

La landing se publica en GitHub Pages y el backend en Render, con PostgreSQL en Neon. Las capturas muestran la publicación, la configuración del servicio y la documentación disponible.

| Producto | Plataforma | Versión / acceso |
| --- | --- | --- |
| Landing | GitHub Pages | Release v1.0.0 |
| Backend | Render | Release v1.0.0 y Swagger UI |
| Base de datos | Neon | PostgreSQL, conexión privada |
| Android | Emulador Android API 36 | APK y ejecución de vistas |

<p align="center">
  <img src="assets/repository-evidence/landing-deployment.png" alt="Publicación de la landing mediante GitHub Actions" width="960">
</p>

*Figura. Publicación de la landing mediante GitHub Actions.*

Enlace a despliegue de landing:

https://github.com/vitaHealth-UPC/landing-page/actions/runs/37709905361

<p align="center">
  <img src="assets/githubPageEvidence.png" alt="Configuración de GitHub Pages" width="960">
</p>

*Figura. Configuración de GitHub Pages.*

<p align="center">
  <img src="assets/landingPageEvidence.png" alt="Landing publicada" width="960">
</p>

*Figura. Landing publicada.*

<p align="center">
  <img src="assets/deployment-evidence/neon-proyecto.png" alt="Proyecto PostgreSQL en Neon" width="960">
</p>

*Figura. Proyecto PostgreSQL en Neon.*

<p align="center">
  <img src="assets/deployment-evidence/neon-connect.png" alt="Configuración de conexión a PostgreSQL" width="960">
</p>

*Figura. Configuración de conexión a PostgreSQL.*

<p align="center">
  <img src="assets/deployment-evidence/render-env.png" alt="Variables de entorno del servicio" width="960">
</p>

*Figura. Variables de entorno del servicio.*

<p align="center">
  <img src="assets/deployment-evidence/render-deploy.png" alt="Servicio publicado en Render" width="960">
</p>

*Figura. Servicio publicado en Render.*

<p align="center">
  <img src="assets/deployment-evidence/health.png" alt="Respuesta del endpoint de salud" width="960">
</p>

*Figura. Respuesta del endpoint de salud.*

<p align="center">
  <img src="assets/deployment-evidence/swagger-desplegado.png" alt="Swagger UI del backend publicado" width="960">
</p>

*Figura. Swagger UI del backend publicado.*

Enlace a landing:

https://vitahealth-upc.github.io/landing-page/

Enlace a backend:

https://web-services-yzxl.onrender.com/

Enlace a health:

https://web-services-yzxl.onrender.com/health

Enlace a Swagger UI:

https://web-services-yzxl.onrender.com/swagger-ui/index.html

Enlace a release Android:

https://github.com/vitaHealth-UPC/mobile-android/releases/tag/v1.0.0

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
