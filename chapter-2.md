# Capítulo II: Requirements Development and Software Solution Design
## 2.1. Competidores

### 2.1.1. Análisis competitivo

### 2.1.2. Estrategias y tácticas frente a competidores

## 2.2. Entrevistas

### 2.2.1. Diseño de entrevistas

### 2.2.2. Registro de entrevistas

### 2.2.3. Análisis de entrevistas

## 2.3. Needfinding

### 2.3.1. User Personas

### 2.3.2. User Task Matrix

### 2.3.3. User Journey Mapping

### 2.3.4. Empathy Mapping

### 2.3.5. Big Picture EventStorming

### 2.3.6. Ubiquitous Language

## 2.4. Requirements specification

Durante la etapa de investigación, el equipo pudo confirmar algo que ya se intuía desde el planteamiento inicial del proyecto: muchos adultos mayores tienen dificultades para llevar un control constante de su medicación, y sus familiares, al no vivir con ellos o no tener cómo verificarlo, terminan preocupados sin una forma real de saber si todo está bien. A partir de esos hallazgos, en esta sección se definen los requisitos de **Tata**, buscando que cada funcionalidad responda a una necesidad concreta detectada en las entrevistas y no simplemente a una idea aislada del equipo.
 
Para ordenar este trabajo, la sección se divide en cuatro partes:
 
- **To-Be Scenario Mapping**, donde se compara cómo se vive hoy el problema (As-Is) frente a cómo debería sentirse la experiencia una vez que la app esté funcionando (To-Be).
- **User Stories**, con las funcionalidades descritas desde la perspectiva de cada usuario, tanto el adulto mayor como el familiar que lo acompaña.
- **Impact Map**, que conecta el objetivo del negocio con los actores y los cambios de comportamiento que se busca lograr en ellos.
- **Product Backlog**, donde finalmente se ordenan y priorizan las historias de usuario e historias técnicas que se van a desarrollar.

### 2.4.1. User Stories

A partir de los requisitos identificados en la investigación, el equipo tradujo cada necesidad detectada en historias de usuario, agrupadas en epics según el módulo al que pertenecen. Además de las historias orientadas al adulto mayor y al familiar, se incluyen historias técnicas para aquellas funcionalidades que no tienen una interacción directa con el usuario final (como los endpoints del backend), y dos spike stories para investigar la viabilidad de los componentes que requieren aprendizaje autónomo antes de comenzar su implementación.

Cada historia de usuario sigue el formato Story ID / User / Priority / Epic, con su Title, Description y Acceptance Criteria redactados bajo la estructura Given-When-Then, en tiempo presente y tercera persona, evitando hacer referencia a elementos específicos de interfaz.


**Epics identificadas**

| Epic ID | Nombre | Descripción breve |
|---|---|---|
| EPIC-01 | Autenticación y Vinculación de Cuentas | Acceso simplificado del adulto mayor y vinculación con la cuenta del familiar |
| EPIC-02 | Gestión de Medicamentos | Registro, edición y eliminación de medicamentos por parte del familiar |
| EPIC-03 | Confirmación de Toma de Medicamento | Recordatorio y confirmación de la toma desde la app del adulto mayor |
| EPIC-04 | Monitoreo y Notificaciones | Visibilidad del familiar sobre el estado de las tomas y la adherencia |
| EPIC-05 | Detección de Patrones de Olvido (IA) | Análisis de historial para anticipar olvidos recurrentes |
 
---

**User Stories**

<table>
<tr><th>Story ID</th><th>User</th><th>Priority</th><th>Epic</th></tr>
<tr><td>US-01</td><td>Adulto mayor</td><td>Alta</td><td>EPIC-01</td></tr>
<tr><td colspan="4"><strong>Title:</strong> Ingreso simplificado a la aplicación</td></tr>
<tr><td colspan="4"><strong>Description</strong><br>Como adulto mayor, quiero ingresar a la aplicación con un PIN corto y sencillo, para no tener que recordar contraseñas complicadas.</td></tr>
<tr><td colspan="4"><strong>Acceptance Criteria</strong><br>
1. Dado que el adulto mayor abre la aplicación por primera vez, cuando ingresa un PIN de cuatro dígitos, entonces el sistema registra dicho PIN como su credencial de acceso.<br>
2. Dado que el adulto mayor ya tiene un PIN registrado, cuando lo ingresa correctamente, entonces el sistema le da acceso a la pantalla principal.<br>
3. Dado que el adulto mayor ingresa un PIN incorrecto, cuando lo intenta tres veces seguidas, entonces el sistema bloquea temporalmente el acceso y sugiere contactar a su familiar.
</td></tr>
</table>
<table>
<tr><th>Story ID</th><th>User</th><th>Priority</th><th>Epic</th></tr>
<tr><td>US-02</td><td>Familiar</td><td>Alta</td><td>EPIC-01</td></tr>
<tr><td colspan="4"><strong>Title:</strong> Vinculación con la cuenta del adulto mayor</td></tr>
<tr><td colspan="4"><strong>Description</strong><br>Como familiar, quiero vincular mi cuenta con la de mi adulto mayor mediante un código, para poder monitorear su tratamiento desde mi propia aplicación.</td></tr>
<tr><td colspan="4"><strong>Acceptance Criteria</strong><br>
1. Dado que el adulto mayor tiene una cuenta creada, cuando el sistema genera un código de vinculación para esa cuenta, entonces dicho código queda disponible para ser compartido.<br>
2. Dado que el familiar cuenta con el código de vinculación, cuando lo ingresa en su aplicación, entonces el sistema asocia ambas cuentas.<br>
3. Dado que dos familiares distintos ingresan el mismo código de vinculación, cuando ambos lo registran, entonces el sistema permite que ambos queden vinculados al mismo adulto mayor.
</td></tr>
</table>
<table>
<tr><th>Story ID</th><th>User</th><th>Priority</th><th>Epic</th></tr>
<tr><td>US-03</td><td>Familiar</td><td>Alta</td><td>EPIC-02</td></tr>
<tr><td colspan="4"><strong>Title:</strong> Registro de un nuevo medicamento</td></tr>
<tr><td colspan="4"><strong>Description</strong><br>Como familiar, quiero registrar un medicamento con su dosis, horario y días de la semana, para que el sistema le recuerde a mi adulto mayor cuándo debe tomarlo.</td></tr>
<tr><td colspan="4"><strong>Acceptance Criteria</strong><br>
1. Dado que el familiar completa el nombre, la dosis y al menos un horario del medicamento, cuando confirma el registro, entonces el sistema guarda el medicamento como activo para el adulto mayor vinculado.<br>
2. Dado que el familiar no completa el nombre del medicamento, cuando intenta confirmar el registro, entonces el sistema rechaza la operación y no crea el medicamento.<br>
3. Dado que un medicamento fue registrado con éxito, cuando llega la fecha y hora programada, entonces el sistema genera una toma pendiente asociada a ese medicamento.
</td></tr>
</table>
<table>
<tr><th>Story ID</th><th>User</th><th>Priority</th><th>Epic</th></tr>
<tr><td>US-04</td><td>Familiar</td><td>Media</td><td>EPIC-02</td></tr>
<tr><td colspan="4"><strong>Title:</strong> Edición y eliminación de un medicamento</td></tr>
<tr><td colspan="4"><strong>Description</strong><br>Como familiar, quiero editar o eliminar un medicamento ya registrado, para mantener actualizado el tratamiento cuando cambie una indicación médica.</td></tr>
<tr><td colspan="4"><strong>Acceptance Criteria</strong><br>
1. Dado que existe un medicamento registrado, cuando el familiar modifica su horario o dosis, entonces el sistema actualiza la información y aplica el cambio a las próximas tomas programadas.<br>
2. Dado que existe un medicamento registrado, cuando el familiar lo elimina, entonces el sistema deja de generar nuevas tomas para dicho medicamento, conservando el historial previo.
</td></tr>
</table>
<table>
<tr><th>Story ID</th><th>User</th><th>Priority</th><th>Epic</th></tr>
<tr><td>US-05</td><td>Adulto mayor</td><td>Alta</td><td>EPIC-03</td></tr>
<tr><td colspan="4"><strong>Title:</strong> Recordatorio de toma de medicamento</td></tr>
<tr><td colspan="4"><strong>Description</strong><br>Como adulto mayor, quiero recibir un recordatorio a la hora indicada de mi medicamento, para no olvidarme de tomarlo.</td></tr>
<tr><td colspan="4"><strong>Acceptance Criteria</strong><br>
1. Dado que existe una toma programada para la hora actual, cuando dicha hora se cumple, entonces el sistema envía un recordatorio al adulto mayor.<br>
2. Dado que un recordatorio fue enviado, cuando el adulto mayor no confirma la toma dentro del tiempo de tolerancia configurado, entonces el sistema envía un segundo recordatorio.
</td></tr>
</table>
<table>
<tr><th>Story ID</th><th>User</th><th>Priority</th><th>Epic</th></tr>
<tr><td>US-06</td><td>Adulto mayor</td><td>Alta</td><td>EPIC-03</td></tr>
<tr><td colspan="4"><strong>Title:</strong> Confirmación de toma por voz o por selección</td></tr>
<tr><td colspan="4"><strong>Description</strong><br>Como adulto mayor, quiero confirmar que tomé mi medicamento con una sola acción, ya sea hablando o seleccionando una opción, para no tener que escribir nada.</td></tr>
<tr><td colspan="4"><strong>Acceptance Criteria</strong><br>
1. Dado que existe una toma pendiente, cuando el adulto mayor confirma la toma mediante voz, entonces el sistema reconoce la confirmación y cambia el estado de la toma a confirmada.<br>
2. Dado que existe una toma pendiente, cuando el adulto mayor selecciona la confirmación sin usar voz, entonces el sistema cambia el estado de la toma a confirmada.<br>
3. Dado que una toma ya fue confirmada, cuando el adulto mayor intenta confirmarla nuevamente, entonces el sistema no genera un registro duplicado.
</td></tr>
</table>
<table>
<tr><th>Story ID</th><th>User</th><th>Priority</th><th>Epic</th></tr>
<tr><td>US-07</td><td>Familiar</td><td>Alta</td><td>EPIC-04</td></tr>
<tr><td colspan="4"><strong>Title:</strong> Notificación del estado de una toma</td></tr>
<tr><td colspan="4"><strong>Description</strong><br>Como familiar, quiero recibir una notificación cuando una toma es confirmada o queda sin confirmar, para estar al tanto sin necesidad de llamar constantemente.</td></tr>
<tr><td colspan="4"><strong>Acceptance Criteria</strong><br>
1. Dado que el adulto mayor confirma una toma, cuando el sistema registra dicha confirmación, entonces envía una notificación al familiar vinculado.<br>
2. Dado que una toma supera el tiempo de tolerancia sin ser confirmada, cuando el sistema la marca como omitida, entonces envía una notificación al familiar vinculado.
</td></tr>
</table>
<table>
<tr><th>Story ID</th><th>User</th><th>Priority</th><th>Epic</th></tr>
<tr><td>US-08</td><td>Familiar</td><td>Media</td><td>EPIC-04</td></tr>
<tr><td colspan="4"><strong>Title:</strong> Resumen de adherencia al tratamiento</td></tr>
<tr><td colspan="4"><strong>Description</strong><br>Como familiar, quiero ver un resumen del cumplimiento de los medicamentos durante la semana, para entender cómo ha ido el tratamiento en general.</td></tr>
<tr><td colspan="4"><strong>Acceptance Criteria</strong><br>
1. Dado que existen tomas registradas durante los últimos siete días, cuando el familiar consulta el resumen semanal, entonces el sistema muestra el porcentaje de tomas confirmadas frente al total programado.<br>
2. Dado que no existen tomas registradas en el periodo consultado, cuando el familiar accede al resumen, entonces el sistema indica que no hay información disponible para ese periodo.
</td></tr>
</table>
<table>
<tr><th>Story ID</th><th>User</th><th>Priority</th><th>Epic</th></tr>
<tr><td>US-09</td><td>Familiar</td><td>Media</td><td>EPIC-05</td></tr>
<tr><td colspan="4"><strong>Title:</strong> Alerta de patrón de olvido recurrente</td></tr>
<tr><td colspan="4"><strong>Description</strong><br>Como familiar, quiero recibir una alerta cuando el sistema detecta que una toma se olvida de forma repetida en un horario específico, para poder ajustar el tratamiento junto al médico o modificar el recordatorio.</td></tr>
<tr><td colspan="4"><strong>Acceptance Criteria</strong><br>
1. Dado que un medicamento acumula tres o más tomas omitidas en el mismo horario dentro de las últimas cuatro semanas, cuando el sistema evalúa el historial, entonces genera una alerta de patrón para el familiar.<br>
2. Dado que una alerta de patrón fue generada, cuando el familiar la revisa, entonces el sistema le permite acceder directamente a la edición del medicamento asociado.
</td></tr>
</table>

---

**Technical Stories**

<table>
<tr><th>Story ID</th><th>User</th><th>Priority</th><th>Epic</th></tr>
<tr><td>TS-01</td><td>Developer</td><td>Alta</td><td>EPIC-01</td></tr>
<tr><td colspan="4"><strong>Title:</strong> Endpoint de autenticación por PIN</td></tr>
<tr><td colspan="4"><strong>Description</strong><br>Como developer, quiero implementar el endpoint que valida el PIN del adulto mayor, para que la aplicación pueda autenticar sus solicitudes.</td></tr>
<tr><td colspan="4"><strong>Acceptance Criteria</strong><br>
1. Dado un request con un PIN válido registrado, cuando se envía al endpoint de autenticación, entonces el response devuelve un token de sesión con código 200.<br>
2. Dado un request con un PIN inválido, cuando se envía al endpoint de autenticación, entonces el response devuelve un código 401 sin generar token.
</td></tr>
</table>
<table>
<tr><th>Story ID</th><th>User</th><th>Priority</th><th>Epic</th></tr>
<tr><td>TS-02</td><td>Developer</td><td>Alta</td><td>EPIC-01</td></tr>
<tr><td colspan="4"><strong>Title:</strong> Endpoint de vinculación familiar-paciente</td></tr>
<tr><td colspan="4"><strong>Description</strong><br>Como developer, quiero implementar el endpoint que asocia la cuenta de un familiar con la de un adulto mayor mediante un código, para reflejar esa relación en el sistema.</td></tr>
<tr><td colspan="4"><strong>Acceptance Criteria</strong><br>
1. Dado un request con un código de vinculación existente y vigente, cuando se envía al endpoint de vinculación, entonces el response crea la relación familiar-paciente y devuelve código 201.<br>
2. Dado un request con un código de vinculación expirado o inexistente, cuando se envía al endpoint de vinculación, entonces el response devuelve código 404 sin crear ninguna relación.
</td></tr>
</table>
<table>
<tr><th>Story ID</th><th>User</th><th>Priority</th><th>Epic</th></tr>
<tr><td>TS-03</td><td>Developer</td><td>Alta</td><td>EPIC-02</td></tr>
<tr><td colspan="4"><strong>Title:</strong> Endpoints CRUD de medicamentos</td></tr>
<tr><td colspan="4"><strong>Description</strong><br>Como developer, quiero exponer los endpoints para crear, actualizar, eliminar y listar medicamentos, para que la aplicación del familiar pueda gestionar el tratamiento del adulto mayor.</td></tr>
<tr><td colspan="4"><strong>Acceptance Criteria</strong><br>
1. Dado un request con los datos obligatorios de un medicamento, cuando se envía al endpoint de creación, entonces el response registra el medicamento y devuelve código 201.<br>
2. Dado un request de actualización sobre un medicamento existente, cuando se envía al endpoint correspondiente, entonces el response refleja los cambios y devuelve código 200.<br>
3. Dado un request de eliminación sobre un medicamento existente, cuando se envía al endpoint correspondiente, entonces el response marca el medicamento como inactivo y devuelve código 200.
</td></tr>
</table>
<table>
<tr><th>Story ID</th><th>User</th><th>Priority</th><th>Epic</th></tr>
<tr><td>TS-04</td><td>Developer</td><td>Alta</td><td>EPIC-03</td></tr>
<tr><td colspan="4"><strong>Title:</strong> Endpoint de confirmación de toma</td></tr>
<tr><td colspan="4"><strong>Description</strong><br>Como developer, quiero implementar el endpoint que registra la confirmación de una toma, para actualizar su estado en la base de datos.</td></tr>
<tr><td colspan="4"><strong>Acceptance Criteria</strong><br>
1. Dado un request de confirmación sobre una toma en estado pendiente, cuando se envía al endpoint correspondiente, entonces el response cambia el estado a confirmada y devuelve código 200.<br>
2. Dado un request de confirmación sobre una toma ya confirmada previamente, cuando se envía al endpoint correspondiente, entonces el response devuelve código 409 sin duplicar el registro.
</td></tr>
</table>
<table>
<tr><th>Story ID</th><th>User</th><th>Priority</th><th>Epic</th></tr>
<tr><td>TS-05</td><td>Developer</td><td>Media</td><td>EPIC-04</td></tr>
<tr><td colspan="4"><strong>Title:</strong> Proceso automático de tomas vencidas</td></tr>
<tr><td colspan="4"><strong>Description</strong><br>Como developer, quiero implementar un proceso que revise periódicamente las tomas pendientes vencidas, para marcarlas como omitidas y disparar la notificación correspondiente.</td></tr>
<tr><td colspan="4"><strong>Acceptance Criteria</strong><br>
1. Dado que una toma pendiente supera el tiempo de tolerancia configurado, cuando el proceso automático se ejecuta, entonces cambia el estado de la toma a omitida.<br>
2. Dado que una toma fue marcada como omitida, cuando el proceso automático finaliza, entonces se genera una solicitud de notificación hacia el servicio de mensajería.
</td></tr>
</table>
<table>
<tr><th>Story ID</th><th>User</th><th>Priority</th><th>Epic</th></tr>
<tr><td>TS-06</td><td>Developer</td><td>Media</td><td>EPIC-04</td></tr>
<tr><td colspan="4"><strong>Title:</strong> Endpoint de envío de notificaciones push</td></tr>
<tr><td colspan="4"><strong>Description</strong><br>Como developer, quiero exponer el endpoint que dispara una notificación push al familiar, para informarle sobre el estado de una toma.</td></tr>
<tr><td colspan="4"><strong>Acceptance Criteria</strong><br>
1. Dado un request con el identificador de una toma y el familiar destinatario, cuando se envía al endpoint de notificaciones, entonces el response confirma el envío y devuelve código 200.<br>
2. Dado un request con un familiar destinatario sin dispositivo registrado, cuando se envía al endpoint de notificaciones, entonces el response devuelve código 404 sin intentar el envío.
</td></tr>
</table>

---

**Spike Stories**

***Spike 1: Investigar la Integración de Reconocimiento de Voz (Speech-to-Text) para la Confirmación de Tomas***
 
**Contexto**
La aplicación del adulto mayor requiere una forma de confirmar la toma de medicamentos sin depender exclusivamente de la lectura o escritura, dado que parte del público objetivo tiene dificultad para interactuar con interfaces convencionales. El equipo evalúa incorporar un SDK de reconocimiento de voz (por ejemplo, el Speech Recognition nativo de Android/iOS, o un servicio externo como Google Speech-to-Text) dentro de la aplicación móvil, considerando que este componente no ha sido trabajado previamente en el curso.
 
**Spike Story**
Como equipo de desarrollo, quiero investigar y prototipar la integración de un servicio de reconocimiento de voz en la aplicación del adulto mayor, para entender su precisión, facilidad de integración y esfuerzo necesario antes de implementarlo como funcionalidad definitiva.
 
**Criterios de Aceptación**
 
1. Dado que el equipo necesita conocer las opciones disponibles, cuando revisa la documentación de al menos dos alternativas de reconocimiento de voz (SDK nativo vs. servicio externo), entonces documenta ventajas, limitaciones y costos de cada una en un informe.
2. Dado que se eligió una alternativa preliminar, cuando el equipo construye un prototipo mínimo que reconoce la frase "ya tomé mi pastilla" en español, entonces el prototipo queda registrado en una rama del repositorio.
3. Dado que el prototipo está construido, cuando se realizan pruebas con distintas formas de pronunciar la frase, entonces el equipo documenta el porcentaje de reconocimiento correcto obtenido.
4. Dado que las pruebas fueron realizadas, cuando el equipo evalúa los resultados, entonces documenta una recomendación final sobre si la alternativa evaluada es viable para el proyecto.
**Definition of Done (DoD)**
- El código del prototipo está registrado en una rama del repositorio.
- El informe con hallazgos, precisión obtenida y recomendación final es compartido con el equipo.
- Los hallazgos se utilizan para crear o ajustar la historia de usuario US-06 en el backlog.
- El spike está limitado a 8 horas y se completa dentro del sprint correspondiente.

---
 
***Spike 2: Investigar un Modelo Simple de Detección de Patrones de Olvido***
 
**Contexto**
Como parte del feature de aprendizaje autónomo del proyecto, el equipo busca incorporar un mecanismo que analice el historial de tomas y detecte patrones recurrentes de olvido (por ejemplo, un horario donde el adulto mayor suele omitir la toma con frecuencia). Este análisis no corresponde a un tema cubierto directamente en el curso, por lo que se requiere investigar una aproximación simple antes de integrarla al backend.
 
**Spike Story**
Como equipo de desarrollo, quiero investigar y prototipar una forma simple de detectar patrones de olvido a partir del historial de tomas, para determinar qué enfoque (reglas estadísticas o un modelo de clasificación básico) es viable de implementar dentro del alcance del proyecto.
 
**Criterios de Aceptación**
 
1. Dado que el equipo necesita comparar alternativas, cuando investiga un enfoque basado en reglas estadísticas simples y un enfoque basado en un modelo de clasificación básico (por ejemplo, con una librería ligera de machine learning), entonces documenta las diferencias, complejidad de implementación y precisión esperada de cada uno.
2. Dado que se seleccionó un enfoque preliminar, cuando el equipo construye un prototipo que procesa un set de datos de prueba con tomas confirmadas y omitidas, entonces el prototipo identifica al menos un patrón esperado dentro de los datos de prueba.
3. Dado que el prototipo genera resultados, cuando el equipo revisa la salida obtenida, entonces documenta si el resultado es lo suficientemente claro como para mostrarse directamente al familiar.
**Definition of Done (DoD)**
- El código del prototipo está registrado en una rama del repositorio.
- El informe con el enfoque recomendado y sus limitaciones es compartido con el equipo.
- Los hallazgos se utilizan para crear o ajustar la historia de usuario US-09 en el backlog.
- El spike está limitado a 8 horas y se completa dentro del sprint correspondiente.

### 2.4.2. Impact Mapping

### 2.4.3. Product Backlog

## 2.5. Strategic-Level Domain-Driven Design

### 2.5.1. EventStorming

#### 2.5.1.1. Candidate Context Discovery

#### 2.5.1.2. Domain Message Flows Modeling

#### 2.5.1.3. Bounded Context Canvases

### 2.5.2. Context Mapping

### 2.5.3. Software Architecture

#### 2.5.3.1. Software Architecture Context Level Diagrams

#### 2.5.3.2. Software Architecture Container Level Diagrams

#### 2.5.3.3. Software Architecture Deployment Diagrams

## 2.6. Tactical-Level Domain-Driven Design

### 2.6.x. Bounded Context: <Bounded Context Name>

#### 2.6.x.1. Domain Layer

#### 2.6.x.2. Interface Layer

#### 2.6.x.3. Application Layer

#### 2.6.x.4 Infrastructure Layer

#### 2.6.x.5. Bounded Context Software Architecture Component Level Diagrams

#### 2.6.x.6. Bounded Context Software Architecture Code Level Diagrams

##### 2.6.x.6.1. Bounded Context Domain Layer Class Diagrams

##### 2.6.x.6.2. Bounded Context Database Design Diagram
