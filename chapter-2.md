# Capítulo II: Requirements Development and Software Solution Design
## 2.1. Competidores

Para el análisis competitivo de Tata se identificaron tres soluciones digitales relacionadas con el cuidado remoto y la adherencia al tratamiento médico de personas mayores. Se consideraron competidores directos cuyo nucleo del producto sea el recordatorio de medicación con alertas al cuidador, así como un competidor indirecto orientado a la coordinación familiar del cuidado en general.

**Competidor 1: Medisafe** <br>
Aplicación de recordatorio de medicamentos con más de 10 millones de usuarios a nivel global. Permite programar dosis, registrar la toma y, mediante su función "Medfriend", notificar a un familiar cuando una dosis fue omitida. Cuenta con un plan gratuito limitado y un plan premium mensual/anual con reportes de adherencia ilimitados.

**Competidor 2: MyTherapy** <br>
Aplicación gratuita desarrollada por la empresa alemana smartpatient GmbH, orientada a recordatorios de medicación y diario de salud (síntomas, mediciones). No requiere suscripción de pago y opera bajo estándares de privacidad GDPR, pero su función de monitoreo remoto para un familiar es limitada frente a soluciones especializadas en cuidado a distancia.

**Competidor 3: Caring Village** <br>
Plataforma de coordinación de cuidado familiar que integra listas de tareas, calendario compartido, almacenamiento de documentos y recordatorios de medicación básicos dentro de un "círculo de cuidado" con múltiples cuidadores. Su enfoque es más amplio que la sola adherencia a medicamentos, por lo que no está optimizada para la simplicidad de uso que requiere un adulto mayor con baja alfabetización digital.

### 2.1.1. Análisis competitivo

<table>
  <tr>
    <th colspan="2" style="background-color: #f6f8fa; text-align: left;">¿Por qué llevar a cabo este análisis?</th>
    <td colspan="4">Se busca contrastar la propuesta de valor de Tata frente a soluciones existentes de recordatorio de medicación y coordinación de cuidado, identificando vacíos que Tata puede cubrir, particularmente en la combinación de accesibilidad para el adulto mayor y anticipación de olvidos mediante detección de patrones.</td>
  </tr>

  <tr align="center">
    <th width="12%">Perfil / Criterio</th>
    <th width="18%">Subcriterio</th>
    <th width="17.5%">
      <img src="./assets/Tata.png" alt="Tata Logo" width="50"><br>
      <b>Tata (VitaHealth)</b>
    </th>
    <th width="17.5%">
      <img src="./assets/Medisafe.png" alt="Medisafe Logo" width="50"><br>
      <b>Medisafe</b>
    </th>
    <th width="17.5%">
      <img src="./assets/MyTheraphy.jpg" alt="MyTherapy Logo" width="50"><br>
      <b>MyTherapy</b>
    </th>
    <th width="17.5%">
      <img src="./assets/CaringVillage.png" alt="Caring Village Logo" width="50"><br>
      <b>Caring Village</b>
    </th>
  </tr>

  <tr>
    <td colspan="2"><b>Overview — Perfil</b></td>
    <td>Aplicación móvil enfocada en la adherencia a medicamentos para adultos mayores con baja alfabetización digital, mediante confirmación por voz o un solo toque, y un panel de monitoreo en tiempo real para la familia.</td>
    <td>Aplicación de recordatorio de medicación con función de alerta al cuidador (Medfriend) ante dosis omitidas.</td>
    <td>Aplicación gratuita de recordatorio de medicación y diario de salud, sin foco específico en cuidadores remotos.</td>
    <td>Plataforma de coordinación del cuidado familiar con múltiples cuidadores, calendario y tareas compartidas.</td>
  </tr>

  <tr>
    <td colspan="2"><b>Ventaja competitiva / ¿Qué valor ofrece a los clientes?</b></td>
    <td>Interfaz ultra simplificada (voz/un toque) diseñada para adultos mayores + anticipación de olvidos mediante detección de patrones.</td>
    <td>Amplia base de usuarios y robusta base de datos sobre interacciones entre medicamentos.</td>
    <td>Gratuita sin límites, enfoque integral en salud (no solo enfocado en medicación).</td>
    <td>Coordinación entre varios cuidadores familiares, no solo un contacto de alerta.</td>
  </tr>

  <tr>
    <td rowspan="2" align="center" style="vertical-align: middle;"><b>Perfil de Marketing</b></td>
    <td><b>Mercado objetivo</b></td>
    <td>Familias limeñas con adultos mayores de 68-85 años que viven solos o con poca compañía.</td>
    <td>Usuarios individuales a nivel global con tratamientos crónicos, con opción de compartir información con un familiar.</td>
    <td>Personas que gestionan su propia medicación y buscan una alternativa gratuita.</td>
    <td>Familias con múltiples cuidadores que coordinan el cuidado integral de un adulto mayor.</td>
  </tr>
  <tr>
    <td><b>Estrategias de marketing</b></td>
    <td>Cercanía local, alianzas estratégicas con clínicas, farmacias y aseguradoras (canal B2B2C).</td>
    <td>Marketing digital masivo y posicionamiento orgánico/pagado en app stores globales.</td>
    <td>Posicionamiento por gratuidad y cumplimiento estricto de privacidad (GDPR).</td>
    <td>Posicionamiento en comunidades de cuidadores familiares (blogs, guías de soporte).</td>
  </tr>

  <tr>
    <td rowspan="3" align="center" style="vertical-align: middle;"><b>Perfil de Producto</b></td>
    <td><b>Productos & Servicios</b></td>
    <td>Aplicación móvil (adulto mayor + familiar) + reconocimiento de voz + detección de patrones de olvido.</td>
    <td>Aplicación móvil de recordatorios + seguimiento de interacciones + reportes de adherencia.</td>
    <td>Aplicación móvil de recordatorios + diario de salud + sincronización con Apple Health / Google Fit.</td>
    <td>Aplicación móvil de coordinación de cuidado + recordatorios básicos + almacenamiento de documentos.</td>
  </tr>
  <tr>
    <td><b>Precios & Costos</b></td>
    <td>Modelo freemium con suscripción mensual para el familiar (plan premium).</td>
    <td>Gratuito (limitado a 2 medicamentos) / Premium a USD 4.99 mensual o USD 39.99 anual.</td>
    <td>Gratis, sin muro de pago.</td>
    <td>Gratis.</td>
  </tr>
  <tr>
    <td><b>Canales de distribución (Web y/o Móvil)</b></td>
    <td>Aplicación móvil nativa (Android/iOS) + Sitio web (Landing Page).</td>
    <td>Aplicación móvil (iOS/Android).</td>
    <td>Aplicación móvil (iOS/Android).</td>
    <td>Aplicación móvil (iOS/Android) + versión web.</td>
  </tr>
  
  <tr>
    <td rowspan="4" align="center" style="vertical-align: middle;"><b>Análisis SWOT</b></td>
    <td><b>Fortalezas</b></td>
    <td>Interfaz diseñada específicamente para baja alfabetización digital (voz/un toque); detección de patrones de olvido como diferenciador único.</td>
    <td>Base de usuarios masiva (+10M) y robustez en el seguimiento de interacciones medicamentosas.</td>
    <td>Gratuidad total sin muro de pago; buen posicionamiento en privacidad de datos (cumplimiento GDPR).</td>
    <td>Coordinación entre múltiples cuidadores familiares, no solo un contacto único de alerta.</td>
  </tr>
  <tr>
    <td><b>Debilidades</b></td>
    <td>Startup nueva sin base de usuarios ni reconocimiento de marca; recursos limitados frente a aplicaciones consolidadas.</td>
    <td>Interfaz no optimizada para adultos mayores con baja alfabetización digital; versión gratuita limitada a 2 medicamentos.</td>
    <td>Monitoreo remoto para el familiar limitado; sin función de anticipación de olvidos.</td>
    <td>Enfoque generalista que diluye la especialización en medicación; no diseñada para uso autónomo del adulto mayor.</td>
  </tr>
  <tr>
    <td><b>Oportunidades</b></td>
    <td>Mercado peruano de salud digital para adultos mayores poco atendido; alianzas B2B2C con clínicas y aseguradoras.</td>
    <td>Expansión a mercados latinoamericanos no explotados.</td>
    <td>Ampliar funciones dirigidas al cuidador a futuro.</td>
    <td>Integrar funciones más específicas de salud y seguimiento clínico.</td>
  </tr>
  <tr>
    <td><b>Amenazas</b></td>
    <td>Aplicaciones globales gratuitas que reducen la disposición a pagar; posible entrada de competidores locales con mayor respaldo.</td>
    <td>Soluciones locales más simples y económicas orientadas específicamente al segmento de adultos mayores.</td>
    <td>Al ser gratuita, presiona a Tata a justificar claramente el valor monetario de su modelo freemium.</td>
    <td>Aplicaciones especializadas como Tata, con foco exclusivo en medicación, pueden captar al segmento que busca esa profundidad.</td>
  </tr>
</table>

### 2.1.2. Estrategias y tácticas frente a competidores

Para posicionar a **Tata** de manera sólida frente a las alternativas del mercado, se establecen estrategias específicas según el perfil de cada competidor, complementadas con una táctica transversal de adquisición local:

* **Frente a Medisafe (Diferenciación por accesibilidad extrema):** Mientras Medisafe se enfoca en el seguimiento clínico avanzado y un alto volumen de usuarios, Tata centrará su propuesta en eliminar barreras de uso. Se aplicará un testeo continuo de la interfaz de confirmación por voz y un solo toque con adultos mayores reales del segmento objetivo, evitando la sobrecarga de funciones que dificulta la adopción autónoma en plataformas complejas.

* **Frente a MyTherapy (Posicionamiento por valor agregado vs. gratuidad):** Ante la ventaja de gratuidad total de MyTherapy, Tata no competirá por precio, sino por el valor diferencial de la detección de patrones de olvido y el panel de monitoreo familiar en tiempo real. Esta propuesta se comunicará claramente en la Landing Page y la app para justificar el modelo *freemium*.

* **Frente a Caring Village (Especialización exclusiva):** Dado que Caring Village se orienta a la coordinación general del cuidado (calendario, tareas y documentos), Tata mantendrá su foco exclusivo en la adherencia a medicamentos. Esta táctica evita la dispersión funcional y atiende de forma directa el problema central identificado en la investigación.

* **Táctica transversal de adquisición (Canal B2B2C local):** Se establecerán alianzas estratégicas con clínicas geriátricas y farmacias en Lima Metropolitana para acelerar la captura de usuarios a través de un canal local que ninguno de los tres competidores internacionales aprovecha actualmente.

## 2.2. Entrevistas

### 2.2.1. Diseño de entrevistas

Para cada segmento objetivo se diseñó una guía de entrevista semiestructurada. Esta se compone de preguntas principales que abordan directamente los objetivos de la investigación y preguntas complementarias que permiten profundizar según las respuestas del entrevistado.

El diseño busca recolectar información de ambos segmentos sobre:
* **Datos demográficos y contexto:** Género, edad, distrito de residencia, estado civil, composición familiar y ocupación.
* **Perfil cualitativo:** Personalidad, habilidades, afinidad por marcas, influencias y dispositivos preferidos.
* **Comportamiento digital:** Canales digitales de interacción y uso de asistentes o comandos de voz.
* **Dominio del problema:** Objetivos, frustraciones y antecedentes o biografía relevante vinculada a la adherencia a la medicación y el cuidado remoto.

---

#### Guía de entrevista — Segmento Adulto Mayor

**Preguntas demográficas y de contexto** <br>
**1.** ¿Podría contarme un poco sobre usted: su edad, distrito donde vive y con quién vive actualmente? <br>
**2.** ¿A qué se dedicaba antes de jubilarse, y cómo describiría un día típico suyo actualmente? <br>

**Preguntas sobre el problema (medicación)** <br>
**3.** ¿Qué medicamentos toma actualmente y con qué frecuencia? <br>
**4.** ¿Cómo recuerda usted la hora en que debe tomar cada medicamento? <br>
**5.** ¿Le ha pasado alguna vez olvidarse de tomar un medicamento? ¿Qué ocurrió después? <br>
**6.** ¿Alguien de su familia le pregunta o verifica si tomó sus medicamentos? ¿Cómo lo hace (llamada, visita, mensaje)? <br>

**Preguntas sobre tecnología** <br>
**7.** ¿Qué tipo de celular usa (básico o smartphone) y qué aplicaciones usa con más frecuencia? <br>
**8.** ¿Ha usado alguna vez comandos de voz en su celular (como asistentes de voz)? ¿Cómo fue esa experiencia? <br>
**9.** ¿Qué le resulta difícil o incómodo al usar aplicaciones nuevas en su celular? <br>

**Preguntas sobre frustraciones y objetivos** <br>
**10.** ¿Qué es lo que más le preocupa en relación con su salud y su tratamiento médico? <br>
**11.** ¿Qué le gustaría que fuera más fácil en su día a día respecto al cuidado de su salud? <br>

---

#### Guía de entrevista — Segmento Familiar

**Preguntas demográficas y de contexto** <br>
**1.** ¿Podría contarme sobre usted: edad, distrito donde vive, ocupación y composición de su familia? <br>
**2.** ¿Con qué frecuencia ve o se comunica con su familiar adulto mayor? <br>

**Preguntas sobre el problema (supervisión remota)** <br>
**3.** ¿Cómo se entera usted si su familiar tomó su medicación en el horario indicado? <br>
**4.** ¿Qué hace cuando no está seguro de si la tomó (llama, envía mensaje, pide a alguien que lo visite)? <br>
**5.** ¿Cuánto tiempo diría que le toma, en promedio, hacer este tipo de seguimiento a la semana? <br>
**6.** Cuénteme sobre alguna vez en la que se enteró tarde de que su familiar no tomó su medicamento. ¿Qué pasó? <br>

**Preguntas sobre tecnología** <br>
**7.** ¿Qué aplicaciones usa habitualmente en su celular (redes sociales, mensajería, salud)? <br>
**8.** ¿Ha usado alguna aplicación para el cuidado de un familiar? ¿Cuál y qué le pareció? <br>
**9.** ¿Qué tan cómodo se siente configurando alertas o notificaciones en aplicaciones móviles? <br>

**Preguntas sobre frustraciones y objetivos** <br>
**10.** ¿Qué es lo que más le genera ansiedad o preocupación respecto al cuidado de su familiar a distancia? <br>
**11.** Si pudiera tener una herramienta ideal para este problema, ¿qué es lo primero que le gustaría que le mostrara o le avisara? <br>

### 2.2.2. Registro de entrevistas

Las entrevistas se realizaron con representantes de los dos segmentos objetivo de Tata. El propósito fue conocer cómo gestionan actualmente la medicación, qué dificultades aparecen durante este proceso y cómo intervienen los familiares cuando el seguimiento se realiza a distancia.

Para cada participante se registraron sus datos principales, una captura de la sesión, la duración de la entrevista y el enlace de acceso. Además, se elaboró un resumen descriptivo con los aspectos más relevantes obtenidos durante la conversación.

#### Segmento 1: Adultos mayores

Este segmento está conformado por adultos mayores que siguen uno o más tratamientos y gestionan directamente sus medicamentos. Las entrevistas buscan conocer sus rutinas actuales, las dificultades que experimentan para recordar o confirmar una toma y su relación con el uso de dispositivos móviles.

<table>
  <tbody>
    <tr>
      <td colspan="4" align="center"><strong>Entrevista N.° 1</strong></td>
    </tr>
    <tr>
      <td colspan="4" align="center">
        <img src="assets/segmento-1-entrevista-1-manuel-torres.png" alt="Entrevista del segmento 1, participante 1" width="900">
      </td>
    </tr>
    <tr>
      <td colspan="2" align="center"><strong>Información del entrevistado</strong></td>
      <td colspan="2" align="center"><strong>Contexto de la entrevista</strong></td>
    </tr>
    <tr>
      <td><strong>Nombre completo</strong></td>
      <td>Manuel Alberto Torres Huamaní</td>
      <td><strong>Tratamiento o medicación</strong></td>
      <td>Losartán (mañana) y amlodipino (tarde) para hipertensión; celecoxib 200mg ante dolor de columna; atorvastatina para colesterol</td>
    </tr>
    <tr>
      <td><strong>Edad</strong></td>
      <td>64 años</td>
      <td><strong>Gestión actual de las tomas</strong></td>
      <td>Sigue una rutina informal (mañana/tarde) sin recordatorio fijo; frecuentemente no recuerda si ya tomó la dosis</td>
    </tr>
    <tr>
      <td><strong>Distrito</strong></td>
      <td>San Martín de Porres</td>
      <td><strong>Apoyo familiar</strong></td>
      <td>Su único hijo (vive en Los Olivos) lo llama o envía mensajes de forma esporádica para recordarle, sin frecuencia fija</td>
    </tr>
    <tr>
      <td><strong>Ocupación o situación actual</strong></td>
      <td>Jubilado (ex mecánico y conductor); vive solo, es viudo</td>
      <td><strong>Contexto digital</strong></td>
      <td>Smartphone gama media (Honor); usa WhatsApp y Facebook; usa apps de pago de recibos (agua/luz/teléfono) pero evita apps nuevas o complejas; no usa comandos de voz pero los conoce y les tiene buena disposición</td>
    </tr>
    <tr>
      <td colspan="2"><strong>Duración:</strong> Aproximadamente 12 minutos</td>
      <td colspan="2">
        <strong>URL de grabación:</strong>
        <a href="https://example.com/segmento-1-entrevista-1">Ver video</a>
      </td>
    </tr>
    <tr>
      <td colspan="4">
        <strong>Resumen de la entrevista</strong>
        <p>Manuel Alberto Torres Huamaní es un adulto mayor de 64 años, viudo, residente en San Martín de Porres. Vive solo, ya que su único hijo reside en el distrito de Los Olivos y lo visita principalmente los fines de semana, según su disponibilidad laboral. Trabajó la mayor parte de su vida como mecánico y conductor; actualmente no realiza actividad laboral por limitaciones físicas asociadas a la edad, y su rutina diaria se centra en caminatas cortas y permanecer en casa.</p>
        <p>Es hipertenso y toma losartán en la mañana y amlodipino en la tarde; adicionalmente maneja dolor de columna con celecoxib 200mg ante episodios de dolor, y atorvastatina para el control del colesterol. No cuenta con un método fijo de recordatorio: sigue una rutina informal asociada a los momentos del día, pero reconoce olvidarse con frecuencia de si ya tomó una dosis, dándose cuenta generalmente solo cuando aparecen síntomas físicos (dolor de cabeza asociado al antihipertensivo, mareos asociados a la atorvastatina).</p>
        <p>El apoyo familiar existente es esporádico: su hijo lo llama o le escribe ocasionalmente para recordarle tomar su medicación, pero sin una frecuencia constante debido a sus propias responsabilidades laborales y familiares. Manuel expresa que, al vivir solo, no existe alguien presente que note si algo sale mal.</p>
        <p>En cuanto a tecnología, usa un smartphone gama media (Honor) y limita su uso principalmente a WhatsApp y Facebook para comunicarse con familiares y conocidos. Utiliza aplicaciones de pago de servicios (agua, luz, teléfono) por necesidad, pero evita explorar aplicaciones nuevas que perciba como complejas. No ha usado comandos de voz personalmente, pero los conoce por observar a personas más jóvenes de su entorno, y expresa una actitud favorable hacia esta forma de interacción, ya que la percibe como más práctica que escribir.</p>
        <p>Su principal preocupación de salud es sufrir un evento grave (menciona explícitamente el riesgo de un infarto) por no medicarse correctamente mientras vive solo, sin nadie que lo note a tiempo. Señala además la preocupación de convertirse en una carga para su familia. Como necesidad ideal, describe un mecanismo de aviso simple —lo compara con un timbre— que no dependa de la disponibilidad de un familiar para recordarle su medicación.</p>
      </td>
    </tr>
  </tbody>
</table>

<table>
  <tbody>
    <tr>
      <td colspan="4" align="center"><strong>Entrevista N.° 2</strong></td>
    </tr>
    <tr>
      <td colspan="4" align="center">
        <img src="assets/interviews/segmento-1-entrevista-2.png" alt="Entrevista del segmento 1, participante 2" width="900">
      </td>
    </tr>
    <tr>
      <td colspan="2" align="center"><strong>Información del entrevistado</strong></td>
      <td colspan="2" align="center"><strong>Contexto de la entrevista</strong></td>
    </tr>
    <tr>
      <td><strong>Nombre completo</strong></td>
      <td>[pendiente]</td>
      <td><strong>Tratamiento o medicación</strong></td>
      <td>[pendiente]</td>
    </tr>
    <tr>
      <td><strong>Edad</strong></td>
      <td>[pendiente]</td>
      <td><strong>Gestión actual de las tomas</strong></td>
      <td>[pendiente]</td>
    </tr>
    <tr>
      <td><strong>Distrito</strong></td>
      <td>[pendiente]</td>
      <td><strong>Apoyo familiar</strong></td>
      <td>[pendiente]</td>
    </tr>
    <tr>
      <td><strong>Ocupación o situación actual</strong></td>
      <td>[pendiente]</td>
      <td><strong>Contexto digital</strong></td>
      <td>[pendiente]</td>
    </tr>
    <tr>
      <td colspan="2"><strong>Duración:</strong> [pendiente]</td>
      <td colspan="2">
        <strong>URL de grabación:</strong>
        <a href="https://example.com/segmento-1-entrevista-2">Ver video</a>
      </td>
    </tr>
    <tr>
      <td colspan="4">
        <strong>Resumen de la entrevista</strong>
        <p>[pendiente]</p>
      </td>
    </tr>
  </tbody>
</table>

<table>
  <tbody>
    <tr>
      <td colspan="4" align="center"><strong>Entrevista N.° 3</strong></td>
    </tr>
    <tr>
      <td colspan="4" align="center">
        <img src="assets/interviews/segmento-1-entrevista-3.png" alt="Entrevista del segmento 1, participante 3" width="900">
      </td>
    </tr>
    <tr>
      <td colspan="2" align="center"><strong>Información del entrevistado</strong></td>
      <td colspan="2" align="center"><strong>Contexto de la entrevista</strong></td>
    </tr>
    <tr>
      <td><strong>Nombre completo</strong></td>
      <td>[pendiente]</td>
      <td><strong>Tratamiento o medicación</strong></td>
      <td>[pendiente]</td>
    </tr>
    <tr>
      <td><strong>Edad</strong></td>
      <td>[pendiente]</td>
      <td><strong>Gestión actual de las tomas</strong></td>
      <td>[pendiente]</td>
    </tr>
    <tr>
      <td><strong>Distrito</strong></td>
      <td>[pendiente]</td>
      <td><strong>Apoyo familiar</strong></td>
      <td>[pendiente]</td>
    </tr>
    <tr>
      <td><strong>Ocupación o situación actual</strong></td>
      <td>[pendiente]</td>
      <td><strong>Contexto digital</strong></td>
      <td>[pendiente]</td>
    </tr>
    <tr>
      <td colspan="2"><strong>Duración:</strong> [pendiente]</td>
      <td colspan="2">
        <strong>URL de grabación:</strong>
        <a href="https://example.com/segmento-1-entrevista-3">Ver video</a>
      </td>
    </tr>
    <tr>
      <td colspan="4">
        <strong>Resumen de la entrevista</strong>
        <p>[pendiente]</p>
      </td>
    </tr>
  </tbody>
</table>

#### Segmento 2: Familiares o cuidadores

Este segmento está conformado por familiares o cuidadores que realizan algún tipo de seguimiento a un adulto mayor, especialmente cuando no pueden acompañarlo presencialmente durante todo el día. Las entrevistas buscan comprender cómo obtienen información sobre la medicación, qué dificultades encuentran y qué situaciones generan mayor preocupación durante el cuidado a distancia.

<table>
  <tbody>
    <tr>
      <td colspan="4" align="center"><strong>Entrevista N.° 1</strong></td>
    </tr>
    <tr>
      <td colspan="4" align="center">
        <img src="assets/segmento-2-valeri-rojas.png" alt="Entrevista del segmento 2, participante 1" width="900">
      </td>
    </tr>
    <tr>
      <td colspan="2" align="center"><strong>Información del entrevistado</strong></td>
      <td colspan="2" align="center"><strong>Contexto de seguimiento</strong></td>
    </tr>
    <tr>
      <td><strong>Nombre completo</strong></td>
      <td>Valeri Rojas</td>
      <td><strong>Adulto mayor acompañado</strong></td>
      <td>Abuela (enfermedad: diabetes)</td>
    </tr>
    <tr>
      <td><strong>Edad</strong></td>
      <td>22 años</td>
      <td><strong>Frecuencia de contacto</strong></td>
      <td>Diaria (vive en el mismo hogar que su abuela)</td>
    </tr>
    <tr>
      <td><strong>Distrito</strong></td>
      <td>Los Olivos</td>
      <td><strong>Seguimiento actual</strong></td>
      <td>Le pregunta directamente si ya tomó sus medicamentos; si no está en casa, la llama para verificar. Dedica en promedio 10 minutos a la semana a este seguimiento.</td>
    </tr>
    <tr>
      <td><strong>Ocupación</strong></td>
      <td>Estudiante universitaria</td>
      <td><strong>Contexto digital</strong></td>
      <td>Usa habitualmente WhatsApp, Instagram y TikTok. Nunca ha usado una app específica para el cuidado de un familiar; se siente cómoda configurando alertas y notificaciones en apps móviles. Su abuela no usa WhatsApp, solo llamadas.</td>
    </tr>
    <tr>
      <td colspan="2"><strong>Duración:</strong>4:50</td>
      <td colspan="2">
        <strong>URL de grabación:</strong>
        <a href="https://upcedupe-my.sharepoint.com/:v:/g/personal/u202324623_upc_edu_pe/IQAGYnZf_FOeSpr13EuOgvBGAW-DLQJ_IvvwJbMMOnjjoEE?e=2l9JH8&nav=eyJyZWZlcnJhbEluZm8iOnsicmVmZXJyYWxBcHAiOiJTdHJlYW1XZWJBcHAiLCJyZWZlcnJhbFZpZXciOiJTaGFyZURpYWxvZy1MaW5rIiwicmVmZXJyYWxBcHBQbGF0Zm9ybSI6IldlYiIsInJlZmVycmFsTW9kZSI6InZpZXcifX0%3D">Ver video</a>
      </td>
    </tr>
    <tr>
      <td colspan="4">
        <strong>Resumen de la entrevista</strong>
        <p>
          Valeri (22 años, estudiante universitaria, distrito de Los Olivos) vive con sus padres y su abuela, quien tiene diabetes y requiere seguimiento constante de su medicación. Al vivir juntas, la ve y conversa con ella todos los días, y su método actual de seguimiento es preguntarle directamente si ya tomó sus medicamentos o, si no está en casa, llamarla para confirmarlo. Este seguimiento le toma en promedio unos 10 minutos a la semana. Relató un episodio en el que la familia asumió que su abuelita ya había tomado el medicamento y luego se dieron cuenta de que no fue así, lo que generó preocupación y llevó a reforzar las indicaciones del doctor. Su principal fuente de ansiedad es no enterarse a tiempo cuando está fuera de casa y su abuelita olvida tomar la medicación, dado que está relacionada a su condición de diabetes. En cuanto a contexto digital, usa a diario WhatsApp, Instagram y TikTok, nunca ha probado una aplicación de cuidado familiar, y se siente cómoda configurando alertas o notificaciones. Como funcionalidad ideal, mencionó que le gustaría recibir un aviso cuando su abuelita ya tomó sus medicamentos y una alerta si se olvida o se retrasa, señalando que esto sería especialmente útil porque su abuelita no usa WhatsApp, solo llamadas.
        </p>
      </td>
    </tr>
  </tbody>
</table>

<table>
  <tbody>
    <tr>
      <td colspan="4" align="center"><strong>Entrevista N.° 2: Sebastián Vásquez</strong></td>
    </tr>
    <tr>
      <td colspan="4" align="center">
        <img src="assets/segmento-2-entrevista-2-sebastian-vasquez.png" alt="Entrevista a Sebastián Vásquez" width="900">
      </td>
    </tr>
    <tr>
      <td colspan="2" align="center"><strong>Información del entrevistado</strong></td>
      <td colspan="2" align="center"><strong>Contexto de seguimiento</strong></td>
    </tr>
    <tr>
      <td><strong>Nombre completo</strong></td>
      <td>Sebastián Vásquez</td>
      <td><strong>Adulto mayor acompañado</strong></td>
      <td>Su abuelo</td>
    </tr>
    <tr>
      <td><strong>Edad</strong></td>
      <td>26 años</td>
      <td><strong>Frecuencia de contacto</strong></td>
      <td>Una visita semanal y alrededor de dos llamadas o videollamadas por semana</td>
    </tr>
    <tr>
      <td><strong>Distrito</strong></td>
      <td>Magdalena, Lima</td>
      <td><strong>Seguimiento actual</strong></td>
      <td>Pregunta directamente a su abuelo y normalmente confía en su respuesta</td>
    </tr>
    <tr>
      <td><strong>Ocupación</strong></td>
      <td>Estudiante y supervisor de un pequeño proyecto de software</td>
      <td><strong>Contexto digital</strong></td>
      <td>Utiliza smartphone, WhatsApp, Telegram, banca móvil, Yape, TikTok y llamadas telefónicas</td>
    </tr>
    <tr>
      <td colspan="2"><strong>Duración:</strong> 14:29</td>
      <td colspan="2">
        <strong>URL de grabación:</strong>
        <a href="https://drive.google.com/file/d/1vmsmti_gVNPKoTYMcTZnCLLsb_3lQmc5/view?usp=drive_link">Ver video</a>
      </td>
    </tr>
    <tr>
      <td colspan="4">
        <strong>Resumen de la entrevista</strong>
        <p>Sebastián tiene 26 años, vive en Magdalena y combina sus estudios con un trabajo que realiza desde casa. Vive solo y se encarga de acompañar a su abuelo debido a que ambos son actualmente los integrantes de su familia que se encuentran en Lima. Su abuelo sufrió una caída aproximadamente dos años atrás y quedó con molestias permanentes en la espalda, por lo que realiza ejercicios de rehabilitación y utiliza medicamentos para el dolor y vitaminas.</p>
        <p>Intenta visitarlo al menos una vez por semana y también mantiene contacto mediante llamadas o videollamadas, aunque señala que su abuelo presenta poca familiaridad con la tecnología. En relación con los medicamentos, Sebastián no dispone de un mecanismo de seguimiento constante. Normalmente pregunta si realizó la toma y debe confiar en la respuesta que recibe, incluso cuando percibe cierta duda.</p>
        <p>Durante la entrevista recordó una situación en la que su abuelo afirmó inicialmente haber tomado sus medicamentos, pero después de varias preguntas reconoció que no lo había hecho. Aunque no ocurrió una consecuencia inmediata, la situación generó preocupación dentro de la familia. Sebastián considera conveniente recibir información que reduzca esta incertidumbre y evite depender de consultas constantes para conocer si una toma fue realizada.</p>
        <p>Su preocupación por el cuidado a distancia también incluye la posibilidad de que su abuelo vuelva a sufrir un accidente cuando se encuentra solo. Al referirse a una herramienta ideal, mencionó que le resultaría útil conocer algunas actividades básicas del adulto mayor y disponer de un mecanismo sencillo de solicitud de ayuda ante una emergencia.</p>
      </td>
    </tr>
  </tbody>
</table>

<table>
  <tbody>
    <tr>
      <td colspan="4" align="center"><strong>Entrevista N.° 3</strong></td>
    </tr>
    <tr>
      <td colspan="4" align="center">
        <img src="assets/interviews/segmento-2-entrevista-3.png" alt="Entrevista del segmento 2, participante 3" width="900">
      </td>
    </tr>
    <tr>
      <td colspan="2" align="center"><strong>Información del entrevistado</strong></td>
      <td colspan="2" align="center"><strong>Contexto de seguimiento</strong></td>
    </tr>
    <tr>
      <td><strong>Nombre completo</strong></td>
      <td>[pendiente]</td>
      <td><strong>Adulto mayor acompañado</strong></td>
      <td>[pendiente]</td>
    </tr>
    <tr>
      <td><strong>Edad</strong></td>
      <td>[pendiente]</td>
      <td><strong>Frecuencia de contacto</strong></td>
      <td>[pendiente]</td>
    </tr>
    <tr>
      <td><strong>Distrito</strong></td>
      <td>[pendiente]</td>
      <td><strong>Seguimiento actual</strong></td>
      <td>[pendiente]</td>
    </tr>
    <tr>
      <td><strong>Ocupación</strong></td>
      <td>[pendiente]</td>
      <td><strong>Contexto digital</strong></td>
      <td>[pendiente]</td>
    </tr>
    <tr>
      <td colspan="2"><strong>Duración:</strong> [pendiente]</td>
      <td colspan="2">
        <strong>URL de grabación:</strong>
        <a href="https://example.com/segmento-2-entrevista-3">Ver video</a>
      </td>
    </tr>
    <tr>
      <td colspan="4">
        <strong>Resumen de la entrevista</strong>
        <p>[pendiente]</p>
      </td>
    </tr>
  </tbody>
</table>

### 2.2.3. Análisis de entrevistas

El análisis de las entrevistas se organizó por segmento objetivo. Primero se identificaron los principales hallazgos obtenidos de cada participante y luego se contrastaron sus respuestas para reconocer características comunes.

Las características fueron clasificadas como objetivas o subjetivas y su recurrencia será expresada mediante frecuencias y porcentajes. Estos resultados servirán como base para la definición y ajuste de los User Persona de Tata.

#### Segmento 1: Adultos mayores

##### Hallazgos por entrevista

<table>
  <thead>
    <tr>
      <th>Entrevista</th>
      <th>Características objetivas</th>
      <th>Características subjetivas</th>
      <th>Hallazgo principal</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Entrevista N.° 1</td>
      <td>[pendiente]</td>
      <td>[pendiente]</td>
      <td>[pendiente]</td>
    </tr>
    <tr>
      <td>Entrevista N.° 2</td>
      <td>[pendiente]</td>
      <td>[pendiente]</td>
      <td>[pendiente]</td>
    </tr>
    <tr>
      <td>Entrevista N.° 3</td>
      <td>[pendiente]</td>
      <td>[pendiente]</td>
      <td>[pendiente]</td>
    </tr>
  </tbody>
</table>

##### Características representativas del segmento

<table>
  <thead>
    <tr>
      <th>Tipo</th>
      <th>Característica</th>
      <th>Evidencia</th>
      <th>Frecuencia</th>
      <th>Porcentaje</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Objetiva</td>
      <td>[pendiente]</td>
      <td>Entrevistas [pendiente]</td>
      <td>[pendiente]</td>
      <td>[pendiente]</td>
    </tr>
    <tr>
      <td>Objetiva</td>
      <td>[pendiente]</td>
      <td>Entrevistas [pendiente]</td>
      <td>[pendiente]</td>
      <td>[pendiente]</td>
    </tr>
    <tr>
      <td>Subjetiva</td>
      <td>[pendiente]</td>
      <td>Entrevistas [pendiente]</td>
      <td>[pendiente]</td>
      <td>[pendiente]</td>
    </tr>
    <tr>
      <td>Subjetiva</td>
      <td>[pendiente]</td>
      <td>Entrevistas [pendiente]</td>
      <td>[pendiente]</td>
      <td>[pendiente]</td>
    </tr>
  </tbody>
</table>

##### Conclusión del segmento 1

[pendiente]

#### Segmento 2: Familiares o cuidadores

##### Hallazgos por entrevista

<table>
  <thead>
    <tr>
      <th>Entrevista</th>
      <th>Características objetivas</th>
      <th>Características subjetivas</th>
      <th>Hallazgo principal</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Entrevista N.° 1</td>
      <td>[pendiente]</td>
      <td>[pendiente]</td>
      <td>[pendiente]</td>
    </tr>
    <tr>
      <td>Entrevista N.° 2: Sebastián Vásquez</td>
      <td>26 años, vive en Magdalena, estudia y trabaja desde casa. Acompaña a su abuelo y mantiene contacto mediante visitas, llamadas y videollamadas.</td>
      <td>Considera poco confiable depender únicamente de la respuesta de su abuelo para comprobar una toma. Valora recibir información sin realizar verificaciones constantes.</td>
      <td>El seguimiento a distancia genera incertidumbre porque no existe un mecanismo confiable para conocer si la medicación fue cumplida.</td>
    </tr>
    <tr>
      <td>Entrevista N.° 3</td>
      <td>[pendiente]</td>
      <td>[pendiente]</td>
      <td>[pendiente]</td>
    </tr>
  </tbody>
</table>

##### Características representativas del segmento

<table>
  <thead>
    <tr>
      <th>Tipo</th>
      <th>Característica</th>
      <th>Evidencia</th>
      <th>Frecuencia</th>
      <th>Porcentaje</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Objetiva</td>
      <td>El seguimiento se realiza mediante visitas y comunicación remota</td>
      <td>Entrevista N.° 2</td>
      <td>[pendiente]</td>
      <td>[pendiente]</td>
    </tr>
    <tr>
      <td>Objetiva</td>
      <td>El familiar utiliza habitualmente aplicaciones móviles</td>
      <td>Entrevista N.° 2</td>
      <td>[pendiente]</td>
      <td>[pendiente]</td>
    </tr>
    <tr>
      <td>Subjetiva</td>
      <td>Existe incertidumbre sobre el cumplimiento de la medicación</td>
      <td>Entrevista N.° 2</td>
      <td>[pendiente]</td>
      <td>[pendiente]</td>
    </tr>
    <tr>
      <td>Subjetiva</td>
      <td>Se valora recibir información sin realizar verificaciones constantes</td>
      <td>Entrevista N.° 2</td>
      <td>[pendiente]</td>
      <td>[pendiente]</td>
    </tr>
    <tr>
      <td>Subjetiva</td>
      <td>Existe preocupación por el cuidado del adulto mayor cuando se encuentra solo</td>
      <td>Entrevista N.° 2</td>
      <td>[pendiente]</td>
      <td>[pendiente]</td>
    </tr>
  </tbody>
</table>

##### Conclusión del segmento 2

[pendiente]

## 2.3. Needfinding

A partir de la información recolectada en el proceso de entrevistas y del análisis competitivo desarrollado previamente, el equipo procedera a realizar el Needfinding, con el objetivo de construir una comprensión profunda y estructurada de los dos segmentos objetivo de Tata. Esta sección incluye la elaboración de los User Personas que representan a cada segmento, el User Task Matrix que consolida las tareas relevantes que estos realizan, los User Journey Maps en su versión As-Is, los Empathy Maps por cada arquetipo, el Big Picture EventStorming del dominio del negocio, y el glosario de Ubiquitous Language que unifica el vocabulario del equipo en torno al dominio del problema.

### 2.3.1. User Personas

**Segmento 1: Adultos mayores**
<p align="center">
  <img src="assets/User_Persona1.png" alt="user_persona_valentina" width="500"/>
</p>

**Segmento 2: Familiares o cuidadores de adultos mayores**
<p align="center">
  <img src="assets/User_Persona2.png" alt="user_persona_andrea" width="500"/>
</p>

### 2.3.2. User Task Matrix

#### Segmento 1: Adultos mayores

<div align="center"> <table> <thead> <tr> <th>Tarea</th> <th>Frecuencia</th> <th>Importancia</th> </tr> </thead> <tbody> <tr> <td>Recordar los medicamentos que debe tomar</td> <td>Often</td> <td>High</td> </tr> <tr> <td>Identificar cuándo debe tomar un medicamento</td> <td>Often</td> <td>High</td> </tr> <tr> <td>Tener sus medicamentos disponibles cuando los necesita</td> <td>Often</td> <td>High</td> </tr> <tr> <td>Tomar sus medicamentos durante una crisis de salud</td> <td>Sometimes</td> <td>High</td> </tr> <tr> <td>Tomar el medicamento indicado antes de dormir</td> <td>Often</td> <td>High</td> </tr> <tr> <td>Recordar si ya realizó una toma</td> <td>Sometimes</td> <td>High</td> </tr> <tr> <td>Consultar a sus familiares sobre aspectos relacionados con sus medicamentos</td> <td>Sometimes</td> <td>Medium</td> </tr> <tr> <td>Informar a sus familiares sobre su estado de salud</td> <td>Sometimes</td> <td>Medium</td> </tr> <tr> <td>Buscar información sobre sus problemas de salud</td> <td>Sometimes</td> <td>Medium</td> </tr> <tr> <td>Aprender a utilizar nuevas herramientas para el cuidado de su salud</td> <td>Rarely</td> <td>Medium</td> </tr> </tbody> </table> </div>

#### Segmento 2: Familiares o cuidadores de adultos mayores

<div align="center"> <table> <thead> <tr> <th>Tarea</th> <th>Frecuencia</th> <th>Importancia</th> </tr> </thead> <tbody> <tr> <td>Comunicarse con el adulto mayor para conocer su estado de salud</td> <td>Often</td> <td>High</td> </tr> <tr> <td>Preguntar al adulto mayor si tomó sus medicamentos</td> <td>Often</td> <td>High</td> </tr> <tr> <td>Recordar al adulto mayor que debe tomar sus medicamentos</td> <td>Often</td> <td>High</td> </tr> <tr> <td>Verificar que el adulto mayor haya tomado sus medicamentos</td> <td>Often</td> <td>High</td> </tr> <tr> <td>Realizar seguimiento del tratamiento del adulto mayor</td> <td>Often</td> <td>High</td> </tr> <tr> <td>Detectar cuando el adulto mayor olvida una toma</td> <td>Sometimes</td> <td>High</td> </tr> <tr> <td>Recordar periódicamente los horarios de medicación</td> <td>Often</td> <td>High</td> </tr> <tr> <td>Consultar directamente al adulto mayor cuando existe duda sobre una toma</td> <td>Sometimes</td> <td>Medium</td> </tr> <tr> <td>Dedicar tiempo diario al seguimiento de la medicación</td> <td>Often</td> <td>Medium</td> </tr> <tr> <td>Preocuparse por el cuidado general del adulto mayor cuando no está presente</td> <td>Often</td> <td>High</td> </tr> </tbody> </table> </div>

#### Análisis del User Task Matrix

Las tareas con mayor frecuencia e importancia para el segmento de adultos mayores están relacionadas con recordar y realizar correctamente sus tomas de medicamentos. Destacan recordar los medicamentos que debe tomar, identificar cuándo debe tomarlos, tenerlos disponibles y realizar las tomas correspondientes, principalmente calificadas como Often y High. La entrevista evidencia que el cumplimiento de la medicación puede estar relacionado con su bienestar, especialmente en situaciones como las crisis de migraña o la toma de medicamentos durante la noche. Asimismo, existe una necesidad de contar con herramientas sencillas que puedan ser comprendidas y utilizadas sin generar dificultades.

Para el segmento de familiares o cuidadores, las tareas de mayor frecuencia e importancia son preguntar si el adulto mayor tomó sus medicamentos, recordarle que debe tomarlos, verificar que la toma se haya realizado y realizar seguimiento del tratamiento. Estas tareas muestran que actualmente el familiar depende principalmente de la comunicación directa con el adulto mayor para conocer si cumplió con su medicación. Además, el entrevistado indicó que dedica aproximadamente 10 minutos diarios a realizar este tipo de seguimiento.

Una de las principales coincidencias entre ambos segmentos es que ambos participan en el cumplimiento y seguimiento de la medicación. El adulto mayor realiza las acciones relacionadas directamente con sus medicamentos, mientras que el familiar participa mediante recordatorios, preguntas y verificación. Por ello, una misma situación puede generar una tarea para ambos usuarios: mientras el adulto mayor necesita recordar y realizar una toma, el familiar necesita comprobar que esta se haya realizado.

La principal diferencia se encuentra en el rol que desempeña cada segmento dentro del proceso. El adulto mayor es quien ejecuta directamente la toma y necesita una forma sencilla de recordar sus medicamentos y horarios. En cambio, el familiar o cuidador cumple un rol de supervisión, dedicando tiempo a comunicarse con el adulto mayor y verificar que el tratamiento se esté siguiendo correctamente.

Finalmente, las tareas identificadas muestran que existe una necesidad de reducir la dependencia de la comunicación verbal para comprobar las tomas. Mientras que actualmente el familiar debe preguntar directamente al adulto mayor y confiar en su respuesta, el adulto mayor necesita una manera sencilla de indicar que ya realizó su toma. Esta relación entre ambos segmentos es fundamental para TATA, ya que permite plantear una solución que facilite el cumplimiento del tratamiento para el adulto mayor y, al mismo tiempo, reduzca la incertidumbre del familiar.

### 2.3.3. User Journey Mapping

#### Segmento 1: Adultos mayores

![journeymap1.png](assets/journeymap1.png)

#### Segmento 2: Familiares o cuidadores de adultos mayores

![journeymap2.png](assets/journeymap2.png)

### 2.3.4. Empathy Mapping

#### Segmento 1: Adultos mayores

![empathymap1.png](assets/empathymap1.png)

#### Segmento 2: Familiares o cuidadores de adultos mayores

![empathymap2.png](assets/empathymap2.png)

### 2.3.5. Big Picture EventStorming

El Big Picture EventStorming permitió representar de forma general cómo se desarrolla el dominio de Tata, desde el registro y la vinculación de los usuarios hasta el seguimiento de las tomas, la generación de alertas y el análisis de la adherencia. El modelo se construyó principalmente a partir de eventos de dominio expresados como hechos ya ocurridos y organizados según su secuencia dentro del negocio.

Para facilitar su lectura, el dominio se dividió en cuatro grupos principales: **Cuenta y cuidado**, **Tratamiento y toma**, **Omisión, seguimiento y analítica**, y **Continuidad y accesibilidad**. Los eventos principales se representaron mediante notas naranjas, mientras que las barras verticales identifican eventos pivote que marcan cambios relevantes dentro del flujo. También se incorporaron puntos problemáticos para mantener visibles situaciones que requieren mayor análisis o validación durante el desarrollo del proyecto.

![Big Picture EventStorming de Tata](assets/big-picture-eventstorming.png)

*Figura. Big Picture EventStorming de Tata.*

#### Cuenta y cuidado

Este flujo representa la incorporación inicial de los usuarios al ecosistema de Tata y el establecimiento de la relación de cuidado. Comienza con la creación y verificación de la cuenta del familiar o cuidador, continúa con su habilitación y la activación del plan correspondiente.

Posteriormente, se registra el perfil del adulto mayor y se genera el mecanismo de vinculación entre ambas partes. El flujo culmina cuando se registra el consentimiento y se confirma el vínculo de cuidado. Este último evento resulta importante porque permite continuar con la configuración y seguimiento del tratamiento asociado al adulto mayor.

Los eventos pivote permiten distinguir momentos relevantes dentro del proceso, como la habilitación de la cuenta y la confirmación del vínculo. Asimismo, los puntos problemáticos asociados permiten mantener visibles aspectos que todavía pueden requerir validación, como la seguridad del proceso de vinculación y el consentimiento del adulto mayor.

![Cuenta y cuidado](assets/big-picture-cuenta-cuidado.png)

*Figura. Flujo de cuenta y cuidado.*

#### Tratamiento y toma

Este grupo describe el flujo principal relacionado con la configuración del tratamiento y la ejecución cotidiana de una toma. Inicialmente se registra el tratamiento, el medicamento, la dosis, el horario y los recordatorios necesarios. Cuando la configuración se encuentra completa, el tratamiento pasa a un estado activo y Tata puede calcular las próximas tomas programadas.

Al acercarse el horario establecido, se envía el recordatorio y se abre una ventana para que el adulto mayor registre la confirmación. A partir de este punto aparecen dos resultados principales. Si la toma es confirmada, se registra el evento correspondiente y se actualiza el historial diario. Si no existe confirmación dentro del periodo esperado, el flujo continúa hacia el proceso de gestión de omisiones.

La separación entre **Tratamiento activado** y los eventos correspondientes a una toma concreta permite distinguir la configuración general del tratamiento de su ejecución diaria. De igual forma, la bifurcación entre una toma confirmada y una toma no confirmada representa uno de los principales cambios de comportamiento dentro del dominio.

![Tratamiento y toma](assets/big-picture-tratamiento-toma.png)

*Figura. Flujo de tratamiento y toma.*

#### Omisión, seguimiento y analítica

Este flujo representa lo que ocurre cuando una toma permanece sin confirmación y requiere atención adicional. Tata puede emitir un recordatorio reforzado y mantener abierta una ventana de tolerancia. Si el periodo definido finaliza sin una confirmación, la toma se registra como omitida y se genera una alerta dirigida al familiar o cuidador.

La alerta puede continuar mediante los canales configurados y, cuando corresponde, iniciar un proceso de escalamiento. Posteriormente, el familiar recibe información sobre la situación y puede realizar el seguimiento correspondiente. De esta forma, Tata no se limita a recordar una toma, sino que también permite informar al responsable del cuidado cuando se produce una situación relevante.

Los registros generados durante las tomas también alimentan el análisis de adherencia. Con el historial acumulado se pueden consolidar periodos de seguimiento, calcular indicadores e identificar patrones recurrentes, como horarios en los que aparecen retrasos u omisiones con mayor frecuencia. A partir de estos resultados, Tata puede mostrar recomendaciones orientadas a mejorar la continuidad del tratamiento.

![Omisión, seguimiento y analítica](assets/big-picture-omision-seguimiento-analitica.png)

*Figura. Flujo de omisión, seguimiento y analítica.*

#### Continuidad y accesibilidad

Este último grupo reúne dos capacidades complementarias del dominio: la accesibilidad de la experiencia y la continuidad del tratamiento.

En cuanto a la accesibilidad, el usuario puede adaptar determinados aspectos de interacción de acuerdo con sus necesidades. Entre los eventos considerados se encuentran el ajuste del tamaño del texto, la habilitación de la confirmación por voz y el almacenamiento de las preferencias de accesibilidad. Estas configuraciones buscan reducir las barreras de interacción para adultos mayores con distintos niveles de familiaridad con dispositivos móviles.

Por otro lado, el flujo de continuidad considera el seguimiento de la disponibilidad de medicamentos. Tata puede recalcular el stock restante y detectar cuándo la cantidad disponible comienza a ser insuficiente. A partir de ello se puede emitir un recordatorio de reabastecimiento e iniciar el registro de la reposición. Una vez confirmada y registrado el nuevo lote, la agenda de tomas puede actualizarse para mantener la continuidad del tratamiento.

Aunque ambos flujos responden a necesidades diferentes, se incluyen dentro de esta vista general porque complementan el objetivo principal de Tata: facilitar una gestión de la medicación que pueda mantenerse en el tiempo y que resulte accesible para el adulto mayor.

![Continuidad y accesibilidad](assets/big-picture-continuidad-accesibilidad.png)

*Figura. Flujos de continuidad y accesibilidad.*

En conjunto, el Big Picture EventStorming permitió identificar una secuencia global que parte de la incorporación y vinculación de los usuarios, continúa con la configuración y ejecución del tratamiento y se extiende hacia el manejo de omisiones, el seguimiento familiar, el análisis de la adherencia y la continuidad del tratamiento. Esta vista general sirve como base para profundizar posteriormente en los procesos del dominio mediante el EventStorming desarrollado en la sección de Strategic-Level Domain-Driven Design.

Enlace a la versión del Big Picture EventStorming: [https://miro.com/app/board/uXjVHq5Jc9w=/](https://miro.com/app/board/uXjVHq5Jc9w=/)

#### 2.3.6. Ubiquitous Language

El Ubiquitous Language se definió a partir de los conceptos identificados durante el análisis del dominio y el desarrollo del EventStorming. Su propósito es establecer un vocabulario común entre los integrantes del equipo y reducir interpretaciones diferentes sobre los elementos que forman parte de Tata. Los términos se redactan en inglés, incluyendo su equivalente en español entre paréntesis, mientras que la definición correspondiente se mantiene en español.

Debido a que un mismo término puede adquirir un significado particular según el contexto en el que se utiliza, el vocabulario se organizó de acuerdo con los Bounded Contexts identificados. Esto permite mantener definiciones precisas dentro de cada parte del dominio y facilita la posterior especificación de reglas, eventos y relaciones.

##### Identidad y suscripción

| Término | Definición |
| --- | --- |
| Account (Cuenta) | Registro de acceso de un usuario en Tata. |
| User (Usuario) | Persona autenticada que utiliza la aplicación. |
| Account status (Estado de cuenta) | Condición que indica si la cuenta se encuentra habilitada. |
| Plan (Plan) | Conjunto de funcionalidades asociado a una modalidad de uso. |
| Subscription (Suscripción) | Relación vigente entre una cuenta y un plan. |
| Consent (Consentimiento) | Autorización registrada para el uso de datos y funcionalidades relacionadas con el cuidado. |
| Verified email (Correo verificado) | Correo cuya propiedad fue confirmada por el usuario. |

##### Vínculo de cuidado

| Término | Definición |
| --- | --- |
| Older adult (Adulto mayor) | Persona cuyo tratamiento es acompañado mediante Tata. |
| Family member (Familiar) | Persona cercana que consulta y acompaña el seguimiento del adulto mayor. |
| Caregiver (Cuidador) | Usuario autorizado para supervisar información relacionada con el adulto mayor. |
| Care link (Vínculo de cuidado) | Relación autorizada entre un cuidador y un adulto mayor. |
| Linking code (Código de vinculación) | Código temporal utilizado para iniciar la asociación entre usuarios. |
| Consent (Consentimiento) | Aceptación del adulto mayor para establecer la relación de cuidado. |
| Emergency contact (Contacto de emergencia) | Información de contacto disponible para situaciones que requieren mayor atención. |

##### Gestión del tratamiento

| Término | Definición |
| --- | --- |
| Treatment (Tratamiento) | Conjunto de reglas que define cómo debe administrarse un medicamento. |
| Medication (Medicamento) | Producto asociado a una pauta de tratamiento. |
| Dose (Dosis) | Cantidad indicada para una toma. |
| Frequency (Frecuencia) | Periodicidad con la que debe realizarse una toma. |
| Intake time (Horario de toma) | Hora programada para administrar una dosis. |
| Instructions (Instrucciones) | Indicaciones asociadas a la administración del medicamento. |
| Reminder (Recordatorio) | Aviso programado relacionado con una toma futura. |
| Active treatment (Tratamiento activo) | Tratamiento completo y habilitado para generar tomas programadas. |

##### Ejecución de tomas

| Término | Definición |
| --- | --- |
| Intake (Toma) | Instancia concreta de una dosis programada. |
| Next intake (Próxima toma) | Siguiente toma pendiente según la programación vigente. |
| Scheduled intake (Toma programada) | Toma asociada a una fecha y hora determinadas. |
| Confirmation window (Ventana de confirmación) | Intervalo disponible para registrar la confirmación de una toma. |
| Confirmation (Confirmación) | Registro realizado por el usuario para indicar que completó una toma. |
| Voice confirmation (Confirmación por voz) | Confirmación registrada a partir de una frase reconocida por el sistema. |
| Tap confirmation (Confirmación por toque) | Confirmación registrada mediante una interacción táctil. |
| Daily history (Historial diario) | Registro de las tomas y sus estados correspondientes a un día. |

##### Omisión y escalamiento

| Término | Definición |
| --- | --- |
| Unconfirmed intake (Toma no confirmada) | Toma que no posee una confirmación dentro de la ventana inicial. |
| Grace period (Tolerancia) | Tiempo adicional disponible antes de considerar una omisión. |
| Pending (Pendiente) | Estado temporal previo a determinar que una toma fue omitida. |
| Omission (Omisión) | Toma que permanece sin confirmación después de finalizar el periodo permitido. |
| Alert (Alerta) | Aviso generado para comunicar una situación que requiere atención del cuidador. |
| Escalation (Escalamiento) | Incremento del nivel de atención cuando una situación continúa sin respuesta. |
| Omission case (Caso de omisión) | Seguimiento de una omisión desde su detección hasta su cierre. |

##### Seguimiento familiar

| Término | Definición |
| --- | --- |
| Family summary (Resumen familiar) | Vista consolidada del estado reciente del adulto mayor. |
| Follow-up (Seguimiento) | Conjunto de acciones realizadas por el familiar o cuidador para acompañar al adulto mayor. |
| Older adult status (Estado del adulto) | Situación reciente obtenida a partir de las tomas, confirmaciones y alertas disponibles. |
| Alert (Alerta) | Situación presentada al familiar porque requiere su atención. |
| Caregiver note (Nota del cuidador) | Registro textual asociado a una intervención o situación observada. |
| Contact (Contacto) | Canal disponible para comunicarse con el adulto mayor. |
| Intervention (Intervención) | Acción realizada por el cuidador ante un estado, alerta o necesidad de seguimiento. |

##### Accesibilidad y preferencias

| Término | Definición |
| --- | --- |
| Text size (Tamaño de texto) | Escala visual aplicada a los textos de la aplicación. |
| Contrast (Contraste) | Nivel de diferenciación visual aplicado a los elementos de la interfaz. |
| Reduced motion (Reducción de movimiento) | Preferencia que disminuye animaciones y transiciones de la aplicación. |
| Voice confirmation (Confirmación por voz) | Preferencia que habilita el uso de la voz como mecanismo de confirmación de una toma. |
| Reading assistance (Ayuda de lectura) | Soporte destinado a facilitar la comprensión del contenido presentado. |
| Quiet hours (Horario de silencio) | Intervalo en el que se restringen determinadas notificaciones no críticas. |
| Notification channel (Canal de notificación) | Medio habilitado para recibir avisos. |
| Preferences (Preferencias) | Conjunto de configuraciones asociadas a la experiencia de un usuario. |

##### Analítica de adherencia

| Término | Definición |
| --- | --- |
| Adherence (Adherencia) | Grado de cumplimiento del tratamiento durante un periodo determinado. |
| Adherence rate (Tasa de adherencia) | Porcentaje de tomas cumplidas respecto de las tomas esperadas durante un periodo. |
| Late intake (Toma tardía) | Toma confirmada después de su horario previsto, pero dentro del periodo considerado válido. |
| Omission (Omisión) | Toma que no fue confirmada dentro del periodo establecido. |
| Time pattern (Patrón horario) | Tendencia recurrente asociada a determinadas franjas de tiempo. |
| Omission risk (Riesgo de omisión) | Estimación de la posibilidad de que se produzcan futuras omisiones. |
| Insight (Insight) | Hallazgo obtenido a partir del análisis del historial de adherencia. |
| Recommendation (Recomendación) | Consejo orientativo generado a partir de los resultados del análisis. |

##### Inventario y reposición

| Término | Definición |
| --- | --- |
| Inventory (Inventario) | Cantidad disponible de un medicamento. |
| Remaining stock (Stock restante) | Número de unidades disponibles en un momento determinado. |
| Low stock (Stock bajo) | Estado alcanzado cuando las unidades disponibles llegan al umbral establecido. |
| Replenishment threshold (Umbral de reposición) | Cantidad mínima que provoca la generación de un aviso de reabastecimiento. |
| Batch (Lote) | Conjunto de unidades incorporadas al inventario durante una reposición. |
| Replenishment request (Solicitud de reposición) | Registro de la necesidad de reabastecer un medicamento. |
| Continuity (Continuidad) | Condición en la que el tratamiento puede mantenerse sin interrupciones por falta de medicamento. |
| Restocking (Reabastecimiento) | Incremento del stock disponible después de una reposición. |

Algunos términos aparecen en más de un contexto, como **Consent (Consentimiento)**, **Voice confirmation (Confirmación por voz)**, **Omission (Omisión)** y **Alert (Alerta)**. Esta repetición responde a que su significado depende de la responsabilidad del contexto. Por ejemplo, una omisión (omission) representa el estado de una toma no confirmada dentro de **Omisión y escalamiento**, mientras que en **Analítica de adherencia** se utiliza como un dato histórico para calcular indicadores y detectar patrones. Mantener estas diferencias permite utilizar el mismo vocabulario de manera consistente sin mezclar responsabilidades entre los modelos del dominio.

## 2.4. Requirements specification

Durante la etapa de investigación, el equipo pudo confirmar algo que ya se intuía desde el planteamiento inicial del proyecto: muchos adultos mayores tienen dificultades para llevar un control constante de su medicación, y sus familiares, al no vivir con ellos o no tener cómo verificarlo, terminan preocupados sin una forma real de saber si todo está bien. A partir de esos hallazgos, en esta sección se definen los requisitos de **Tata**, buscando que cada funcionalidad responda a una necesidad concreta detectada en las entrevistas y no simplemente a una idea aislada del equipo.
 
Para ordenar este trabajo, la sección se divide en cuatro partes:
 
- **To-Be Scenario Mapping**, donde se compara cómo se vive hoy el problema (As-Is) frente a cómo debería sentirse la experiencia una vez que la app esté funcionando (To-Be).
- **User Stories**, con las funcionalidades descritas desde la perspectiva de cada usuario, tanto el adulto mayor como el familiar que lo acompaña.
- **Impact Map**, que conecta el objetivo del negocio con los actores y los cambios de comportamiento que se busca lograr en ellos.
- **Product Backlog**, donde finalmente se ordenan y priorizan las historias de usuario e historias técnicas que se van a desarrollar.

### 2.4.1. User Stories

A partir de los requisitos identificados durante la investigación y el modelado del dominio, el equipo tradujo las necesidades de los segmentos objetivo en historias de usuario agrupadas en Epics. Las historias consideran las funciones destinadas al adulto mayor, al familiar o cuidador y al visitante del Landing Page.

También se incorporaron Technical Stories para las capacidades que no presentan una interacción directa con el usuario final, como servicios REST, procesamiento automático, almacenamiento local e integraciones externas. Finalmente, se definieron Spike Stories para aquellas funcionalidades que requieren reducir incertidumbre técnica antes de su implementación.

Cada User Story y Technical Story mantiene el formato Story ID, User, Priority y Epic. La descripción sigue la estructura Como, quiero, para y los criterios de aceptación utilizan Given, When y Then mediante sus equivalentes Dado, Cuando y Entonces.

#### Epics identificadas

| Epic ID | Nombre | Descripción breve |
| --- | --- | --- |
| EPIC-01 | Autenticación y Vinculación de Cuentas | Gestiona las cuentas del familiar y adulto mayor, su acceso, verificación y relación de cuidado. |
| EPIC-02 | Gestión de Medicamentos y Tratamientos | Permite registrar medicamentos y definir la pauta que determina dosis, frecuencia, horarios e instrucciones. |
| EPIC-03 | Recordatorios y Confirmación de Tomas | Gestiona la agenda de tomas, recordatorios, ventanas de confirmación y registro de cumplimiento. |
| EPIC-04 | Monitoreo, Alertas y Seguimiento Familiar | Permite al familiar conocer el estado de las tomas, recibir alertas relevantes y registrar acciones de seguimiento. |
| EPIC-05 | Analítica de Adherencia y Patrones | Consolida el historial de tomas, calcula adherencia e identifica tendencias recurrentes. |
| EPIC-06 | Accesibilidad y Preferencias | Permite adaptar la experiencia a las necesidades del usuario y configurar determinadas preferencias de interacción. |
| EPIC-07 | Inventario y Reposición | Permite controlar la disponibilidad de medicamentos y registrar su reposición. |
| EPIC-08 | Planes y Suscripción | Gestiona el plan asociado al familiar y las funcionalidades disponibles según la suscripción. |
| EPIC-09 | Landing Page y Captación | Presenta Tata, su propuesta de valor, funcionalidades, planes y medios para continuar con el producto. |

#### User Stories

<table>
<tr><th>Story ID</th><th>User</th><th>Priority</th><th>Epic</th></tr>
<tr><td>US-01</td><td>Adulto mayor</td><td>Alta</td><td>EPIC-01</td></tr>
<tr><td colspan="4"><strong>Title:</strong> Ingreso simplificado a la aplicación</td></tr>
<tr><td colspan="4"><strong>Description</strong><br>Como adulto mayor, quiero ingresar a la aplicación mediante un PIN corto, para acceder sin recordar una contraseña compleja.</td></tr>
<tr><td colspan="4"><strong>Acceptance Criteria</strong><br>
1. Dado que el adulto mayor tiene un perfil habilitado y todavía no cuenta con un PIN, cuando registra cuatro dígitos válidos, entonces el sistema guarda su credencial de acceso.<br>
2. Dado que el adulto mayor posee un PIN registrado, cuando ingresa el valor correcto, entonces el sistema inicia su sesión.<br>
3. Dado que se producen intentos incorrectos consecutivos, cuando se alcanza el límite configurado, entonces el sistema restringe temporalmente nuevos intentos.
</td></tr>
</table>

<table>
<tr><th>Story ID</th><th>User</th><th>Priority</th><th>Epic</th></tr>
<tr><td>US-02</td><td>Familiar</td><td>Alta</td><td>EPIC-01</td></tr>
<tr><td colspan="4"><strong>Title:</strong> Vinculación con la cuenta del adulto mayor</td></tr>
<tr><td colspan="4"><strong>Description</strong><br>Como familiar, quiero vincular mi cuenta con la de un adulto mayor mediante un código, para realizar su seguimiento desde mi cuenta.</td></tr>
<tr><td colspan="4"><strong>Acceptance Criteria</strong><br>
1. Dado que existe un adulto mayor registrado, cuando se solicita una vinculación, entonces el sistema genera un código temporal asociado a su perfil.<br>
2. Dado que el familiar ingresa un código vigente, cuando el adulto mayor acepta la vinculación, entonces el sistema registra la relación de cuidado.<br>
3. Dado que el código ha expirado o ya fue utilizado, cuando se intenta utilizar nuevamente, entonces el sistema rechaza la vinculación.
</td></tr>
</table>

<table>
<tr><th>Story ID</th><th>User</th><th>Priority</th><th>Epic</th></tr>
<tr><td>US-03</td><td>Familiar</td><td>Alta</td><td>EPIC-02</td></tr>
<tr><td colspan="4"><strong>Title:</strong> Registro de un nuevo medicamento</td></tr>
<tr><td colspan="4"><strong>Description</strong><br>Como familiar, quiero registrar un medicamento del adulto mayor, para incorporarlo a su tratamiento.</td></tr>
<tr><td colspan="4"><strong>Acceptance Criteria</strong><br>
1. Dado que el familiar se encuentra vinculado al adulto mayor, cuando registra los datos obligatorios de un medicamento, entonces el sistema almacena el medicamento asociado al adulto.<br>
2. Dado que falta información obligatoria, cuando el familiar intenta registrar el medicamento, entonces el sistema rechaza la operación.
</td></tr>
</table>

<table>
<tr><th>Story ID</th><th>User</th><th>Priority</th><th>Epic</th></tr>
<tr><td>US-04</td><td>Familiar</td><td>Media</td><td>EPIC-02</td></tr>
<tr><td colspan="4"><strong>Title:</strong> Edición y desactivación de un medicamento</td></tr>
<tr><td colspan="4"><strong>Description</strong><br>Como familiar, quiero modificar o desactivar un medicamento registrado, para mantener actualizado el tratamiento sin perder su historial.</td></tr>
<tr><td colspan="4"><strong>Acceptance Criteria</strong><br>
1. Dado que existe un medicamento activo, cuando el familiar modifica sus datos, entonces el sistema conserva la nueva información para las programaciones futuras.<br>
2. Dado que existe un medicamento activo, cuando el familiar lo desactiva, entonces no se generan nuevas tomas y se conserva el historial previo.
</td></tr>
</table>

<table>
<tr><th>Story ID</th><th>User</th><th>Priority</th><th>Epic</th></tr>
<tr><td>US-05</td><td>Adulto mayor</td><td>Alta</td><td>EPIC-03</td></tr>
<tr><td colspan="4"><strong>Title:</strong> Recordatorio de toma de medicamento</td></tr>
<tr><td colspan="4"><strong>Description</strong><br>Como adulto mayor, quiero recibir un recordatorio cuando corresponde una toma, para disminuir la posibilidad de olvidarla.</td></tr>
<tr><td colspan="4"><strong>Acceptance Criteria</strong><br>
1. Dado que existe una toma programada, cuando se alcanza su horario, entonces el sistema genera el recordatorio correspondiente.<br>
2. Dado que la toma ya fue confirmada antes de la ejecución del recordatorio, cuando llega el horario programado, entonces el sistema evita generar un recordatorio innecesario.
</td></tr>
</table>

<table>
<tr><th>Story ID</th><th>User</th><th>Priority</th><th>Epic</th></tr>
<tr><td>US-06</td><td>Adulto mayor</td><td>Alta</td><td>EPIC-03</td></tr>
<tr><td colspan="4"><strong>Title:</strong> Confirmación accesible de una toma</td></tr>
<tr><td colspan="4"><strong>Description</strong><br>Como adulto mayor, quiero confirmar una toma mediante una acción sencilla por toque o por voz, para registrar su realización sin escribir información.</td></tr>
<tr><td colspan="4"><strong>Acceptance Criteria</strong><br>
1. Dado que existe una toma pendiente, cuando el adulto mayor confirma mediante interacción táctil, entonces el sistema registra la toma como confirmada.<br>
2. Dado que existe una toma pendiente, cuando una confirmación de voz es reconocida y validada, entonces el sistema registra la toma como confirmada.<br>
3. Dado que la toma ya fue confirmada, cuando se intenta confirmarla nuevamente, entonces el sistema evita crear un segundo registro.
</td></tr>
</table>

<table>
<tr><th>Story ID</th><th>User</th><th>Priority</th><th>Epic</th></tr>
<tr><td>US-07</td><td>Familiar</td><td>Alta</td><td>EPIC-04</td></tr>
<tr><td colspan="4"><strong>Title:</strong> Alerta ante una toma no confirmada</td></tr>
<tr><td colspan="4"><strong>Description</strong><br>Como familiar, quiero recibir una alerta cuando una toma permanece sin confirmar o es registrada como omitida, para intervenir cuando sea necesario.</td></tr>
<tr><td colspan="4"><strong>Acceptance Criteria</strong><br>
1. Dado que una toma supera el periodo de confirmación establecido, cuando el sistema detecta la falta de respuesta, entonces genera una alerta asociada al adulto mayor.<br>
2. Dado que una toma es registrada como omitida, cuando existe un familiar vinculado con notificaciones habilitadas, entonces el sistema solicita el envío de la alerta correspondiente.
</td></tr>
</table>

<table>
<tr><th>Story ID</th><th>User</th><th>Priority</th><th>Epic</th></tr>
<tr><td>US-08</td><td>Familiar</td><td>Media</td><td>EPIC-05</td></tr>
<tr><td colspan="4"><strong>Title:</strong> Resumen semanal de adherencia</td></tr>
<tr><td colspan="4"><strong>Description</strong><br>Como familiar, quiero consultar un resumen semanal de adherencia, para comprender el nivel general de cumplimiento del tratamiento.</td></tr>
<tr><td colspan="4"><strong>Acceptance Criteria</strong><br>
1. Dado que existen tomas programadas durante el periodo, cuando el familiar consulta el resumen semanal, entonces el sistema calcula las tomas confirmadas, tardías y omitidas.<br>
2. Dado que no existen tomas durante el periodo, cuando se solicita el resumen, entonces el sistema informa que no existen datos suficientes para calcular adherencia.
</td></tr>
</table>

<table>
<tr><th>Story ID</th><th>User</th><th>Priority</th><th>Epic</th></tr>
<tr><td>US-09</td><td>Familiar</td><td>Media</td><td>EPIC-05</td></tr>
<tr><td colspan="4"><strong>Title:</strong> Alerta de patrón de olvido recurrente</td></tr>
<tr><td colspan="4"><strong>Description</strong><br>Como familiar, quiero conocer cuando se detecta un patrón recurrente de omisiones, para revisar los recordatorios y realizar un seguimiento más oportuno.</td></tr>
<tr><td colspan="4"><strong>Acceptance Criteria</strong><br>
1. Dado que el historial cumple el criterio configurado de recurrencia, cuando el sistema analiza las tomas, entonces registra un patrón asociado al horario o medicamento correspondiente.<br>
2. Dado que existe un patrón identificado, cuando el familiar consulta sus insights, entonces el sistema presenta la información que sustenta el hallazgo.
</td></tr>
</table>

<table>
<tr><th>Story ID</th><th>User</th><th>Priority</th><th>Epic</th></tr>
<tr><td>US-10</td><td>Familiar</td><td>Alta</td><td>EPIC-01</td></tr>
<tr><td colspan="4"><strong>Title:</strong> Registro de cuenta del familiar</td></tr>
<tr><td colspan="4"><strong>Description</strong><br>Como familiar, quiero crear una cuenta en Tata, para administrar el seguimiento de un adulto mayor.</td></tr>
<tr><td colspan="4"><strong>Acceptance Criteria</strong><br>
1. Dado que el familiar proporciona los datos requeridos, cuando confirma el registro, entonces el sistema crea una cuenta pendiente de verificación.<br>
2. Dado que el correo ya pertenece a una cuenta existente, cuando se intenta registrar nuevamente, entonces el sistema evita crear una cuenta duplicada.
</td></tr>
</table>

<table>
<tr><th>Story ID</th><th>User</th><th>Priority</th><th>Epic</th></tr>
<tr><td>US-11</td><td>Familiar</td><td>Alta</td><td>EPIC-01</td></tr>
<tr><td colspan="4"><strong>Title:</strong> Verificación del correo del familiar</td></tr>
<tr><td colspan="4"><strong>Description</strong><br>Como familiar, quiero verificar mi correo, para habilitar mi cuenta y continuar con el proceso de vinculación.</td></tr>
<tr><td colspan="4"><strong>Acceptance Criteria</strong><br>
1. Dado que existe una cuenta pendiente, cuando el familiar utiliza una verificación vigente, entonces el sistema registra el correo como verificado.<br>
2. Dado que la verificación ha expirado, cuando se intenta utilizar, entonces el sistema rechaza la operación y permite solicitar una nueva.
</td></tr>
</table>

<table>
<tr><th>Story ID</th><th>User</th><th>Priority</th><th>Epic</th></tr>
<tr><td>US-12</td><td>Familiar</td><td>Alta</td><td>EPIC-01</td></tr>
<tr><td colspan="4"><strong>Title:</strong> Registro del perfil del adulto mayor</td></tr>
<tr><td colspan="4"><strong>Description</strong><br>Como familiar, quiero registrar los datos básicos del adulto mayor, para preparar su perfil de cuidado dentro de Tata.</td></tr>
<tr><td colspan="4"><strong>Acceptance Criteria</strong><br>
1. Dado que el familiar posee una cuenta habilitada, cuando registra los datos requeridos del adulto mayor, entonces el sistema crea su perfil.<br>
2. Dado que se proporciona un contacto de emergencia válido, cuando se completa el perfil, entonces el sistema lo asocia al adulto mayor.
</td></tr>
</table>

<table>
<tr><th>Story ID</th><th>User</th><th>Priority</th><th>Epic</th></tr>
<tr><td>US-13</td><td>Adulto mayor</td><td>Alta</td><td>EPIC-01</td></tr>
<tr><td colspan="4"><strong>Title:</strong> Consentimiento para establecer el vínculo de cuidado</td></tr>
<tr><td colspan="4"><strong>Description</strong><br>Como adulto mayor, quiero aceptar la relación de cuidado con un familiar, para autorizar el acceso a la información necesaria para mi seguimiento.</td></tr>
<tr><td colspan="4"><strong>Acceptance Criteria</strong><br>
1. Dado que existe una solicitud de vinculación vigente, cuando el adulto mayor registra su aceptación, entonces el sistema almacena el consentimiento asociado.<br>
2. Dado que no existe consentimiento registrado, cuando el familiar intenta acceder al seguimiento del adulto, entonces el sistema mantiene restringido dicho acceso.
</td></tr>
</table>

<table>
<tr><th>Story ID</th><th>User</th><th>Priority</th><th>Epic</th></tr>
<tr><td>US-14</td><td>Familiar</td><td>Alta</td><td>EPIC-02</td></tr>
<tr><td colspan="4"><strong>Title:</strong> Creación de un tratamiento</td></tr>
<tr><td colspan="4"><strong>Description</strong><br>Como familiar, quiero crear un tratamiento para el adulto mayor, para agrupar los medicamentos y pautas que debe seguir.</td></tr>
<tr><td colspan="4"><strong>Acceptance Criteria</strong><br>
1. Dado que existe un vínculo activo, cuando el familiar crea un tratamiento, entonces el sistema lo asocia al adulto mayor.<br>
2. Dado que el tratamiento aún no contiene una pauta completa, cuando se crea, entonces permanece inactivo hasta completar su configuración.
</td></tr>
</table>

<table>
<tr><th>Story ID</th><th>User</th><th>Priority</th><th>Epic</th></tr>
<tr><td>US-15</td><td>Familiar</td><td>Alta</td><td>EPIC-02</td></tr>
<tr><td colspan="4"><strong>Title:</strong> Definición de dosis y frecuencia</td></tr>
<tr><td colspan="4"><strong>Description</strong><br>Como familiar, quiero definir la dosis y frecuencia de un medicamento, para representar correctamente su pauta de administración.</td></tr>
<tr><td colspan="4"><strong>Acceptance Criteria</strong><br>
1. Dado que existe un medicamento dentro de un tratamiento, cuando se registra una dosis y frecuencia válidas, entonces el sistema conserva la pauta.<br>
2. Dado que la información proporcionada es incompleta, cuando se intenta guardar la pauta, entonces el sistema rechaza la configuración.
</td></tr>
</table>

<table>
<tr><th>Story ID</th><th>User</th><th>Priority</th><th>Epic</th></tr>
<tr><td>US-16</td><td>Familiar</td><td>Alta</td><td>EPIC-02</td></tr>
<tr><td colspan="4"><strong>Title:</strong> Configuración de horarios e instrucciones</td></tr>
<tr><td colspan="4"><strong>Description</strong><br>Como familiar, quiero definir los horarios e instrucciones de un medicamento, para que cada toma contenga la información necesaria.</td></tr>
<tr><td colspan="4"><strong>Acceptance Criteria</strong><br>
1. Dado que existe una pauta registrada, cuando el familiar añade uno o más horarios, entonces el sistema los asocia al medicamento.<br>
2. Dado que se registran instrucciones complementarias, cuando se genera una toma, entonces estas permanecen asociadas a la programación correspondiente.
</td></tr>
</table>

<table>
<tr><th>Story ID</th><th>User</th><th>Priority</th><th>Epic</th></tr>
<tr><td>US-17</td><td>Familiar</td><td>Alta</td><td>EPIC-02</td></tr>
<tr><td colspan="4"><strong>Title:</strong> Configuración de recordatorios</td></tr>
<tr><td colspan="4"><strong>Description</strong><br>Como familiar, quiero configurar los recordatorios de un tratamiento, para establecer cómo se avisará al adulto mayor antes de una toma.</td></tr>
<tr><td colspan="4"><strong>Acceptance Criteria</strong><br>
1. Dado que existe un tratamiento configurado, cuando el familiar habilita sus recordatorios, entonces el sistema registra la configuración correspondiente.<br>
2. Dado que los recordatorios son modificados, cuando existen tomas futuras, entonces la nueva configuración se aplica a las programaciones pendientes.
</td></tr>
</table>

<table>
<tr><th>Story ID</th><th>User</th><th>Priority</th><th>Epic</th></tr>
<tr><td>US-18</td><td>Familiar</td><td>Alta</td><td>EPIC-02</td></tr>
<tr><td colspan="4"><strong>Title:</strong> Activación y pausa de un tratamiento</td></tr>
<tr><td colspan="4"><strong>Description</strong><br>Como familiar, quiero activar o pausar un tratamiento, para controlar cuándo debe generar nuevas tomas.</td></tr>
<tr><td colspan="4"><strong>Acceptance Criteria</strong><br>
1. Dado que un tratamiento contiene la información obligatoria, cuando el familiar lo activa, entonces el sistema permite generar sus tomas futuras.<br>
2. Dado que el tratamiento está activo, cuando el familiar lo pausa, entonces el sistema deja de generar nuevas tomas sin eliminar el historial existente.
</td></tr>
</table>

<table>
<tr><th>Story ID</th><th>User</th><th>Priority</th><th>Epic</th></tr>
<tr><td>US-19</td><td>Familiar</td><td>Media</td><td>EPIC-02</td></tr>
<tr><td colspan="4"><strong>Title:</strong> Consulta del detalle de un tratamiento</td></tr>
<tr><td colspan="4"><strong>Description</strong><br>Como familiar, quiero consultar la pauta completa de un tratamiento, para verificar la configuración vigente del adulto mayor.</td></tr>
<tr><td colspan="4"><strong>Acceptance Criteria</strong><br>
1. Dado que existe un tratamiento registrado, cuando el familiar consulta su detalle, entonces el sistema proporciona medicamentos, dosis, frecuencia, horarios, instrucciones y estado.<br>
2. Dado que el tratamiento no pertenece a un adulto mayor vinculado al familiar, cuando se intenta consultarlo, entonces el sistema rechaza el acceso.
</td></tr>
</table>

<table>
<tr><th>Story ID</th><th>User</th><th>Priority</th><th>Epic</th></tr>
<tr><td>US-20</td><td>Adulto mayor</td><td>Alta</td><td>EPIC-03</td></tr>
<tr><td colspan="4"><strong>Title:</strong> Consulta de la próxima toma</td></tr>
<tr><td colspan="4"><strong>Description</strong><br>Como adulto mayor, quiero conocer cuál es mi próxima toma, para saber qué medicamento debo tomar y cuándo.</td></tr>
<tr><td colspan="4"><strong>Acceptance Criteria</strong><br>
1. Dado que existen tomas futuras, cuando el adulto mayor consulta su próxima toma, entonces el sistema devuelve la más cercana según la programación.<br>
2. Dado que no existen tomas pendientes, cuando se realiza la consulta, entonces el sistema informa que no hay una próxima toma programada.
</td></tr>
</table>

<table>
<tr><th>Story ID</th><th>User</th><th>Priority</th><th>Epic</th></tr>
<tr><td>US-21</td><td>Adulto mayor</td><td>Media</td><td>EPIC-03</td></tr>
<tr><td colspan="4"><strong>Title:</strong> Consulta del detalle de una toma</td></tr>
<tr><td colspan="4"><strong>Description</strong><br>Como adulto mayor, quiero consultar los datos de una toma, para recordar la dosis y las instrucciones asociadas.</td></tr>
<tr><td colspan="4"><strong>Acceptance Criteria</strong><br>
1. Dado que existe una toma programada, cuando se consulta su detalle, entonces el sistema proporciona medicamento, dosis, horario e instrucciones disponibles.<br>
2. Dado que la toma ya posee un estado, cuando se consulta, entonces el sistema informa si está pendiente, confirmada, tardía u omitida.
</td></tr>
</table>

<table>
<tr><th>Story ID</th><th>User</th><th>Priority</th><th>Epic</th></tr>
<tr><td>US-22</td><td>Adulto mayor</td><td>Alta</td><td>EPIC-03</td></tr>
<tr><td colspan="4"><strong>Title:</strong> Recordatorio reforzado por falta de confirmación</td></tr>
<tr><td colspan="4"><strong>Description</strong><br>Como adulto mayor, quiero recibir un nuevo recordatorio cuando una toma continúa pendiente, para tener otra oportunidad de recordar la medicación.</td></tr>
<tr><td colspan="4"><strong>Acceptance Criteria</strong><br>
1. Dado que el primer recordatorio fue enviado y la toma continúa pendiente, cuando se alcanza el intervalo configurado, entonces el sistema genera un recordatorio reforzado.<br>
2. Dado que la toma ya fue confirmada, cuando llega el momento del refuerzo, entonces el sistema no genera otro recordatorio.
</td></tr>
</table>

<table>
<tr><th>Story ID</th><th>User</th><th>Priority</th><th>Epic</th></tr>
<tr><td>US-23</td><td>Adulto mayor</td><td>Alta</td><td>EPIC-03</td></tr>
<tr><td colspan="4"><strong>Title:</strong> Confirmación dentro del periodo de tolerancia</td></tr>
<tr><td colspan="4"><strong>Description</strong><br>Como adulto mayor, quiero poder confirmar una toma durante el periodo de tolerancia, para registrar correctamente una toma realizada con retraso.</td></tr>
<tr><td colspan="4"><strong>Acceptance Criteria</strong><br>
1. Dado que la hora programada ya pasó y la tolerancia continúa vigente, cuando se registra la confirmación, entonces el sistema clasifica la toma según el retraso correspondiente.<br>
2. Dado que el periodo permitido terminó y la toma fue registrada como omitida, cuando se intenta una confirmación posterior, entonces el sistema no reemplaza automáticamente la omisión.
</td></tr>
</table>

<table>
<tr><th>Story ID</th><th>User</th><th>Priority</th><th>Epic</th></tr>
<tr><td>US-24</td><td>Adulto mayor</td><td>Alta</td><td>EPIC-03</td></tr>
<tr><td colspan="4"><strong>Title:</strong> Consulta de agenda diaria de tomas</td></tr>
<tr><td colspan="4"><strong>Description</strong><br>Como adulto mayor, quiero consultar las tomas programadas para el día, para conocer mi rutina de medicación.</td></tr>
<tr><td colspan="4"><strong>Acceptance Criteria</strong><br>
1. Dado que existen tomas en la fecha consultada, cuando el adulto mayor solicita su agenda, entonces el sistema devuelve las tomas ordenadas cronológicamente.<br>
2. Dado que algunas tomas ya poseen un resultado, cuando se consulta la agenda, entonces cada toma conserva su estado correspondiente.
</td></tr>
</table>

<table>
<tr><th>Story ID</th><th>User</th><th>Priority</th><th>Epic</th></tr>
<tr><td>US-25</td><td>Familiar</td><td>Alta</td><td>EPIC-04</td></tr>
<tr><td colspan="4"><strong>Title:</strong> Consulta del estado reciente del adulto mayor</td></tr>
<tr><td colspan="4"><strong>Description</strong><br>Como familiar, quiero consultar el estado reciente de las tomas del adulto mayor, para conocer su situación sin tener que llamarlo constantemente.</td></tr>
<tr><td colspan="4"><strong>Acceptance Criteria</strong><br>
1. Dado que existe un vínculo de cuidado activo, cuando el familiar consulta el estado del adulto, entonces el sistema proporciona la próxima toma y los últimos resultados registrados.<br>
2. Dado que existe una alerta activa, cuando se consulta el estado, entonces el sistema incluye la situación pendiente de atención.
</td></tr>
</table>

<table>
<tr><th>Story ID</th><th>User</th><th>Priority</th><th>Epic</th></tr>
<tr><td>US-26</td><td>Familiar</td><td>Alta</td><td>EPIC-04</td></tr>
<tr><td colspan="4"><strong>Title:</strong> Consulta del historial reciente de tomas</td></tr>
<tr><td colspan="4"><strong>Description</strong><br>Como familiar, quiero revisar las tomas recientes del adulto mayor, para identificar confirmaciones, retrasos u omisiones.</td></tr>
<tr><td colspan="4"><strong>Acceptance Criteria</strong><br>
1. Dado que existen tomas registradas, cuando el familiar consulta el historial reciente, entonces el sistema devuelve las tomas con fecha, medicamento y estado.<br>
2. Dado que no existen registros dentro del periodo solicitado, cuando se realiza la consulta, entonces el sistema informa la ausencia de resultados.
</td></tr>
</table>

<table>
<tr><th>Story ID</th><th>User</th><th>Priority</th><th>Epic</th></tr>
<tr><td>US-27</td><td>Familiar</td><td>Alta</td><td>EPIC-04</td></tr>
<tr><td colspan="4"><strong>Title:</strong> Consulta del detalle de una alerta</td></tr>
<tr><td colspan="4"><strong>Description</strong><br>Como familiar, quiero consultar el detalle de una alerta, para comprender qué toma requiere mi atención.</td></tr>
<tr><td colspan="4"><strong>Acceptance Criteria</strong><br>
1. Dado que existe una alerta asociada a una toma, cuando el familiar consulta su detalle, entonces el sistema proporciona medicamento, horario, estado y motivo de la alerta.<br>
2. Dado que la alerta presenta acciones de seguimiento registradas, cuando se consulta nuevamente, entonces el sistema conserva la información correspondiente.
</td></tr>
</table>

<table>
<tr><th>Story ID</th><th>User</th><th>Priority</th><th>Epic</th></tr>
<tr><td>US-28</td><td>Familiar</td><td>Media</td><td>EPIC-04</td></tr>
<tr><td colspan="4"><strong>Title:</strong> Configuración de preferencias de notificación</td></tr>
<tr><td colspan="4"><strong>Description</strong><br>Como familiar, quiero seleccionar qué avisos deseo recibir, para mantener un seguimiento útil sin recibir notificaciones innecesarias.</td></tr>
<tr><td colspan="4"><strong>Acceptance Criteria</strong><br>
1. Dado que el familiar posee un vínculo activo, cuando modifica las categorías de notificación permitidas, entonces el sistema guarda sus preferencias.<br>
2. Dado que ocurre un evento no habilitado por el familiar y no corresponde a una alerta crítica, cuando se evalúa el envío, entonces el sistema respeta la preferencia configurada.
</td></tr>
</table>

<table>
<tr><th>Story ID</th><th>User</th><th>Priority</th><th>Epic</th></tr>
<tr><td>US-29</td><td>Familiar</td><td>Media</td><td>EPIC-04</td></tr>
<tr><td colspan="4"><strong>Title:</strong> Contacto con el adulto mayor ante una alerta</td></tr>
<tr><td colspan="4"><strong>Description</strong><br>Como familiar, quiero utilizar el contacto registrado del adulto mayor cuando existe una alerta, para comunicarme con él y verificar la situación.</td></tr>
<tr><td colspan="4"><strong>Acceptance Criteria</strong><br>
1. Dado que existe un contacto disponible, cuando el familiar decide comunicarse ante una alerta, entonces el sistema proporciona el canal de contacto correspondiente.<br>
2. Dado que no existe información de contacto válida, cuando se solicita la acción, entonces el sistema informa que el contacto no se encuentra disponible.
</td></tr>
</table>

<table>
<tr><th>Story ID</th><th>User</th><th>Priority</th><th>Epic</th></tr>
<tr><td>US-30</td><td>Familiar</td><td>Baja</td><td>EPIC-04</td></tr>
<tr><td colspan="4"><strong>Title:</strong> Registro de una nota de seguimiento</td></tr>
<tr><td colspan="4"><strong>Description</strong><br>Como familiar, quiero registrar una nota sobre una intervención, para conservar información relevante sobre el seguimiento realizado.</td></tr>
<tr><td colspan="4"><strong>Acceptance Criteria</strong><br>
1. Dado que existe un vínculo activo, cuando el familiar registra una nota válida, entonces el sistema la almacena con la fecha y el usuario responsable.<br>
2. Dado que existe una nota registrada, cuando se consulta el seguimiento correspondiente, entonces la nota permanece disponible.
</td></tr>
</table>

<table>
<tr><th>Story ID</th><th>User</th><th>Priority</th><th>Epic</th></tr>
<tr><td>US-31</td><td>Familiar</td><td>Media</td><td>EPIC-04</td></tr>
<tr><td colspan="4"><strong>Title:</strong> Actualización del seguimiento de una alerta</td></tr>
<tr><td colspan="4"><strong>Description</strong><br>Como familiar, quiero registrar que una alerta fue atendida, para diferenciar las situaciones resueltas de aquellas que todavía requieren intervención.</td></tr>
<tr><td colspan="4"><strong>Acceptance Criteria</strong><br>
1. Dado que existe una alerta abierta, cuando el familiar registra una intervención, entonces el sistema actualiza su seguimiento.<br>
2. Dado que la situación se considera atendida, cuando el familiar registra su cierre, entonces la alerta deja de aparecer como pendiente sin eliminar su historial.
</td></tr>
</table>

<table>
<tr><th>Story ID</th><th>User</th><th>Priority</th><th>Epic</th></tr>
<tr><td>US-32</td><td>Familiar</td><td>Media</td><td>EPIC-05</td></tr>
<tr><td colspan="4"><strong>Title:</strong> Consulta del historial de adherencia</td></tr>
<tr><td colspan="4"><strong>Description</strong><br>Como familiar, quiero consultar la adherencia de distintos periodos, para observar cómo evoluciona el cumplimiento del tratamiento.</td></tr>
<tr><td colspan="4"><strong>Acceptance Criteria</strong><br>
1. Dado que existe historial suficiente, cuando el familiar selecciona un periodo válido, entonces el sistema calcula los indicadores correspondientes.<br>
2. Dado que se consultan periodos diferentes, cuando existen registros para ambos, entonces cada resultado se calcula utilizando únicamente las tomas de su periodo.
</td></tr>
</table>

<table>
<tr><th>Story ID</th><th>User</th><th>Priority</th><th>Epic</th></tr>
<tr><td>US-33</td><td>Familiar</td><td>Media</td><td>EPIC-05</td></tr>
<tr><td colspan="4"><strong>Title:</strong> Identificación de tomas tardías y omitidas</td></tr>
<tr><td colspan="4"><strong>Description</strong><br>Como familiar, quiero distinguir las tomas tardías y omitidas dentro del historial, para comprender mejor dónde aparecen dificultades de adherencia.</td></tr>
<tr><td colspan="4"><strong>Acceptance Criteria</strong><br>
1. Dado que una toma se confirma después del horario programado pero dentro del periodo permitido, cuando se procesa su resultado, entonces el sistema la clasifica como tardía.<br>
2. Dado que una toma termina el periodo permitido sin confirmación, cuando se procesa su estado, entonces el sistema la clasifica como omitida.
</td></tr>
</table>

<table>
<tr><th>Story ID</th><th>User</th><th>Priority</th><th>Epic</th></tr>
<tr><td>US-34</td><td>Familiar</td><td>Media</td><td>EPIC-05</td></tr>
<tr><td colspan="4"><strong>Title:</strong> Recomendaciones a partir de patrones de adherencia</td></tr>
<tr><td colspan="4"><strong>Description</strong><br>Como familiar, quiero recibir recomendaciones orientativas a partir de patrones de adherencia, para mejorar la forma en que realizo el seguimiento.</td></tr>
<tr><td colspan="4"><strong>Acceptance Criteria</strong><br>
1. Dado que existe un patrón con evidencia suficiente, cuando el sistema genera una recomendación, entonces esta se relaciona con recordatorios, horarios o seguimiento y no modifica indicaciones médicas.<br>
2. Dado que no existe evidencia suficiente, cuando se ejecuta el análisis, entonces el sistema evita presentar una recomendación concluyente.
</td></tr>
</table>

<table>
<tr><th>Story ID</th><th>User</th><th>Priority</th><th>Epic</th></tr>
<tr><td>US-35</td><td>Adulto mayor</td><td>Media</td><td>EPIC-06</td></tr>
<tr><td colspan="4"><strong>Title:</strong> Ajuste del tamaño de texto</td></tr>
<tr><td colspan="4"><strong>Description</strong><br>Como adulto mayor, quiero aumentar el tamaño del texto, para leer la información con mayor facilidad.</td></tr>
<tr><td colspan="4"><strong>Acceptance Criteria</strong><br>
1. Dado que el adulto mayor modifica el tamaño de texto permitido, cuando guarda la preferencia, entonces el sistema conserva el valor seleccionado.<br>
2. Dado que existe una preferencia guardada, cuando el usuario vuelve a utilizar la aplicación, entonces el sistema aplica dicha configuración.
</td></tr>
</table>

<table>
<tr><th>Story ID</th><th>User</th><th>Priority</th><th>Epic</th></tr>
<tr><td>US-36</td><td>Adulto mayor</td><td>Media</td><td>EPIC-06</td></tr>
<tr><td colspan="4"><strong>Title:</strong> Activación de mayor contraste</td></tr>
<tr><td colspan="4"><strong>Description</strong><br>Como adulto mayor, quiero utilizar una configuración de mayor contraste, para distinguir mejor la información presentada.</td></tr>
<tr><td colspan="4"><strong>Acceptance Criteria</strong><br>
1. Dado que la configuración de contraste está disponible, cuando el adulto mayor la activa, entonces el sistema conserva la preferencia.<br>
2. Dado que la preferencia se encuentra activa, cuando el usuario inicia una nueva sesión, entonces el sistema mantiene la configuración.
</td></tr>
</table>

<table>
<tr><th>Story ID</th><th>User</th><th>Priority</th><th>Epic</th></tr>
<tr><td>US-37</td><td>Adulto mayor</td><td>Baja</td><td>EPIC-06</td></tr>
<tr><td colspan="4"><strong>Title:</strong> Reducción de movimiento</td></tr>
<tr><td colspan="4"><strong>Description</strong><br>Como adulto mayor, quiero reducir animaciones y movimientos no esenciales, para utilizar Tata con menos distracciones visuales.</td></tr>
<tr><td colspan="4"><strong>Acceptance Criteria</strong><br>
1. Dado que el usuario habilita la reducción de movimiento, cuando el sistema presenta transiciones no esenciales, entonces utiliza una alternativa reducida.<br>
2. Dado que la preferencia fue guardada, cuando el usuario vuelve a ingresar, entonces el sistema mantiene la configuración seleccionada.
</td></tr>
</table>

<table>
<tr><th>Story ID</th><th>User</th><th>Priority</th><th>Epic</th></tr>
<tr><td>US-38</td><td>Adulto mayor</td><td>Media</td><td>EPIC-06</td></tr>
<tr><td colspan="4"><strong>Title:</strong> Activación de ayuda de lectura</td></tr>
<tr><td colspan="4"><strong>Description</strong><br>Como adulto mayor, quiero disponer de ayuda para comprender la información relevante de mis tomas, para reducir dificultades de lectura.</td></tr>
<tr><td colspan="4"><strong>Acceptance Criteria</strong><br>
1. Dado que la ayuda de lectura está habilitada, cuando existe contenido compatible, entonces el sistema proporciona el apoyo correspondiente.<br>
2. Dado que la ayuda se encuentra deshabilitada, cuando se consulta la misma información, entonces el sistema mantiene el comportamiento estándar.
</td></tr>
</table>

<table>
<tr><th>Story ID</th><th>User</th><th>Priority</th><th>Epic</th></tr>
<tr><td>US-39</td><td>Familiar</td><td>Media</td><td>EPIC-06</td></tr>
<tr><td colspan="4"><strong>Title:</strong> Configuración de horario de silencio y canales</td></tr>
<tr><td colspan="4"><strong>Description</strong><br>Como familiar, quiero definir horarios de silencio y canales de aviso, para adaptar las notificaciones no críticas a mi disponibilidad.</td></tr>
<tr><td colspan="4"><strong>Acceptance Criteria</strong><br>
1. Dado que el familiar configura un horario de silencio válido, cuando se genera un aviso no crítico dentro de dicho periodo, entonces el sistema respeta la configuración.<br>
2. Dado que el familiar habilita o deshabilita un canal disponible, cuando se genera una notificación compatible, entonces el sistema utiliza únicamente los canales permitidos.
</td></tr>
</table>

<table>
<tr><th>Story ID</th><th>User</th><th>Priority</th><th>Epic</th></tr>
<tr><td>US-40</td><td>Familiar</td><td>Media</td><td>EPIC-07</td></tr>
<tr><td colspan="4"><strong>Title:</strong> Registro de inventario inicial</td></tr>
<tr><td colspan="4"><strong>Description</strong><br>Como familiar, quiero registrar la cantidad disponible de un medicamento, para comenzar a controlar su stock.</td></tr>
<tr><td colspan="4"><strong>Acceptance Criteria</strong><br>
1. Dado que existe un medicamento activo, cuando el familiar registra una cantidad inicial válida, entonces el sistema crea su inventario.<br>
2. Dado que se intenta registrar una cantidad inválida, cuando se procesa la operación, entonces el sistema rechaza el valor.
</td></tr>
</table>

<table>
<tr><th>Story ID</th><th>User</th><th>Priority</th><th>Epic</th></tr>
<tr><td>US-41</td><td>Familiar</td><td>Media</td><td>EPIC-07</td></tr>
<tr><td colspan="4"><strong>Title:</strong> Consulta de stock restante</td></tr>
<tr><td colspan="4"><strong>Description</strong><br>Como familiar, quiero conocer el stock restante de un medicamento, para estimar cuándo será necesario reponerlo.</td></tr>
<tr><td colspan="4"><strong>Acceptance Criteria</strong><br>
1. Dado que existe un inventario registrado, cuando el familiar consulta el medicamento, entonces el sistema proporciona la cantidad restante calculada.<br>
2. Dado que existe una pauta activa, cuando se consulta el stock, entonces el sistema puede estimar los días de disponibilidad a partir de la información registrada.
</td></tr>
</table>

<table>
<tr><th>Story ID</th><th>User</th><th>Priority</th><th>Epic</th></tr>
<tr><td>US-42</td><td>Familiar</td><td>Alta</td><td>EPIC-07</td></tr>
<tr><td colspan="4"><strong>Title:</strong> Aviso de stock bajo</td></tr>
<tr><td colspan="4"><strong>Description</strong><br>Como familiar, quiero recibir un aviso cuando un medicamento se aproxima al umbral de reposición, para evitar interrupciones por falta de stock.</td></tr>
<tr><td colspan="4"><strong>Acceptance Criteria</strong><br>
1. Dado que el stock alcanza o queda por debajo del umbral configurado, cuando el sistema recalcula el inventario, entonces genera un aviso de reposición.<br>
2. Dado que el stock vuelve a superar el umbral después de una reposición, cuando se recalcula el inventario, entonces el sistema deja de considerarlo bajo.
</td></tr>
</table>

<table>
<tr><th>Story ID</th><th>User</th><th>Priority</th><th>Epic</th></tr>
<tr><td>US-43</td><td>Familiar</td><td>Media</td><td>EPIC-07</td></tr>
<tr><td colspan="4"><strong>Title:</strong> Registro de reposición de medicamento</td></tr>
<tr><td colspan="4"><strong>Description</strong><br>Como familiar, quiero registrar una reposición y la cantidad incorporada, para actualizar el inventario disponible.</td></tr>
<tr><td colspan="4"><strong>Acceptance Criteria</strong><br>
1. Dado que existe un medicamento con inventario, cuando el familiar registra una reposición válida, entonces el sistema incrementa el stock disponible.<br>
2. Dado que la reposición incluye información de un nuevo lote, cuando se confirma el registro, entonces el sistema conserva dicha información junto con el movimiento.
</td></tr>
</table>

<table>
<tr><th>Story ID</th><th>User</th><th>Priority</th><th>Epic</th></tr>
<tr><td>US-44</td><td>Familiar</td><td>Baja</td><td>EPIC-08</td></tr>
<tr><td colspan="4"><strong>Title:</strong> Consulta del plan actual</td></tr>
<tr><td colspan="4"><strong>Description</strong><br>Como familiar, quiero consultar el plan asociado a mi cuenta, para conocer las funcionalidades disponibles en Tata.</td></tr>
<tr><td colspan="4"><strong>Acceptance Criteria</strong><br>
1. Dado que la cuenta posee un plan asociado, cuando el familiar consulta su suscripción, entonces el sistema proporciona el plan y su estado.<br>
2. Dado que una funcionalidad depende del plan contratado, cuando se consulta la suscripción, entonces el sistema informa si dicha capacidad se encuentra disponible.
</td></tr>
</table>

<table>
<tr><th>Story ID</th><th>User</th><th>Priority</th><th>Epic</th></tr>
<tr><td>US-45</td><td>Familiar</td><td>Media</td><td>EPIC-08</td></tr>
<tr><td colspan="4"><strong>Title:</strong> Activación o cambio de suscripción</td></tr>
<tr><td colspan="4"><strong>Description</strong><br>Como familiar, quiero seleccionar o cambiar mi plan, para utilizar la modalidad de Tata que mejor se adapte a mis necesidades.</td></tr>
<tr><td colspan="4"><strong>Acceptance Criteria</strong><br>
1. Dado que existen planes disponibles, cuando el familiar selecciona uno válido, entonces el sistema registra la suscripción asociada a su cuenta.<br>
2. Dado que la suscripción cambia de plan, cuando la operación es confirmada, entonces el sistema actualiza las capacidades asociadas.
</td></tr>
</table>

<table>
<tr><th>Story ID</th><th>User</th><th>Priority</th><th>Epic</th></tr>
<tr><td>US-46</td><td>Visitante</td><td>Alta</td><td>EPIC-09</td></tr>
<tr><td colspan="4"><strong>Title:</strong> Consulta de la propuesta de valor de Tata</td></tr>
<tr><td colspan="4"><strong>Description</strong><br>Como visitante, quiero conocer el problema que aborda Tata y sus principales beneficios, para evaluar si la solución es relevante para mi familia.</td></tr>
<tr><td colspan="4"><strong>Acceptance Criteria</strong><br>
1. Dado que el visitante accede al Landing Page, cuando se carga el contenido principal, entonces se presenta la propuesta de valor de Tata.<br>
2. Dado que el visitante revisa la información del producto, cuando continúa explorando el contenido, entonces puede reconocer a qué segmentos está dirigida la solución.
</td></tr>
</table>

<table>
<tr><th>Story ID</th><th>User</th><th>Priority</th><th>Epic</th></tr>
<tr><td>US-47</td><td>Visitante</td><td>Media</td><td>EPIC-09</td></tr>
<tr><td colspan="4"><strong>Title:</strong> Consulta de funcionalidades principales</td></tr>
<tr><td colspan="4"><strong>Description</strong><br>Como visitante, quiero conocer las principales funcionalidades de Tata, para comprender cómo facilita la adherencia y el seguimiento familiar.</td></tr>
<tr><td colspan="4"><strong>Acceptance Criteria</strong><br>
1. Dado que el visitante consulta la información del producto, cuando revisa sus funcionalidades, entonces se presentan las capacidades principales de Tata.<br>
2. Dado que existen funcionalidades destinadas a diferentes segmentos, cuando son descritas, entonces el contenido diferencia las relacionadas con el adulto mayor y el familiar.
</td></tr>
</table>

<table>
<tr><th>Story ID</th><th>User</th><th>Priority</th><th>Epic</th></tr>
<tr><td>US-48</td><td>Visitante</td><td>Media</td><td>EPIC-09</td></tr>
<tr><td colspan="4"><strong>Title:</strong> Comparación de planes disponibles</td></tr>
<tr><td colspan="4"><strong>Description</strong><br>Como visitante, quiero conocer las alternativas de suscripción de Tata, para comparar sus beneficios antes de registrarme.</td></tr>
<tr><td colspan="4"><strong>Acceptance Criteria</strong><br>
1. Dado que existen planes disponibles, cuando el visitante consulta la información comercial, entonces se muestran sus principales diferencias.<br>
2. Dado que una funcionalidad pertenece únicamente a una modalidad específica, cuando se comparan los planes, entonces dicha diferencia queda identificada.
</td></tr>
</table>

<table>
<tr><th>Story ID</th><th>User</th><th>Priority</th><th>Epic</th></tr>
<tr><td>US-49</td><td>Visitante</td><td>Alta</td><td>EPIC-09</td></tr>
<tr><td colspan="4"><strong>Title:</strong> Continuación hacia registro o contacto</td></tr>
<tr><td colspan="4"><strong>Description</strong><br>Como visitante, quiero disponer de una forma de continuar hacia el registro, descarga o contacto, para comenzar a utilizar Tata o solicitar más información.</td></tr>
<tr><td colspan="4"><strong>Acceptance Criteria</strong><br>
1. Dado que el visitante decide continuar con Tata, cuando selecciona una alternativa disponible, entonces el sistema lo dirige al destino correspondiente.<br>
2. Dado que una alternativa externa no se encuentra disponible, cuando se intenta acceder a ella, entonces el sistema evita dirigir al visitante hacia un recurso inválido.
</td></tr>
</table>

<table>
<tr><th>Story ID</th><th>User</th><th>Priority</th><th>Epic</th></tr>
<tr><td>US-50</td><td>Visitante</td><td>Alta</td><td>EPIC-09</td></tr>
<tr><td colspan="4"><strong>Title:</strong> Acceso adaptable al Landing Page</td></tr>
<tr><td colspan="4"><strong>Description</strong><br>Como visitante, quiero consultar el Landing Page desde distintos tamaños de pantalla, para acceder a la información sin perder contenido relevante.</td></tr>
<tr><td colspan="4"><strong>Acceptance Criteria</strong><br>
1. Dado que el visitante utiliza un dispositivo móvil o de escritorio, cuando accede al Landing Page, entonces el contenido permanece disponible y comprensible.<br>
2. Dado que el visitante navega mediante teclado o tecnologías de asistencia compatibles, cuando interactúa con elementos funcionales, entonces puede acceder a las acciones disponibles.
</td></tr>
</table>

#### Technical Stories

Las Technical Stories representan capacidades que soportan las funcionalidades del producto sin corresponder directamente a una interacción de los segmentos objetivo. Cuando una historia expone un servicio REST, los criterios consideran los principales escenarios de request y response.

<table>
<tr><th>Story ID</th><th>User</th><th>Priority</th><th>Epic</th></tr>
<tr><td>TS-01</td><td>Developer</td><td>Alta</td><td>EPIC-01</td></tr>
<tr><td colspan="4"><strong>Title:</strong> Servicio de autenticación mediante PIN</td></tr>
<tr><td colspan="4"><strong>Description</strong><br>Como developer, quiero implementar la validación del PIN del adulto mayor, para autenticar sus solicitudes de manera controlada.</td></tr>
<tr><td colspan="4"><strong>Acceptance Criteria</strong><br>
1. Dado un request con una credencial válida, cuando se procesa la autenticación, entonces el servicio responde 200 y genera una sesión válida.<br>
2. Dado un request con una credencial incorrecta, cuando se procesa la autenticación, entonces el servicio responde 401 y no genera una sesión.
</td></tr>
</table>

<table>
<tr><th>Story ID</th><th>User</th><th>Priority</th><th>Epic</th></tr>
<tr><td>TS-02</td><td>Developer</td><td>Alta</td><td>EPIC-01</td></tr>
<tr><td colspan="4"><strong>Title:</strong> API de vinculación de cuidado</td></tr>
<tr><td colspan="4"><strong>Description</strong><br>Como developer, quiero implementar las operaciones necesarias para crear y validar una vinculación entre familiar y adulto mayor, para mantener la relación de cuidado.</td></tr>
<tr><td colspan="4"><strong>Acceptance Criteria</strong><br>
1. Dado un código vigente y un consentimiento válido, cuando se confirma la vinculación, entonces la API persiste la relación y responde con el recurso creado.<br>
2. Dado un código inválido o expirado, cuando se solicita la vinculación, entonces la API rechaza la operación sin crear la relación.
</td></tr>
</table>

<table>
<tr><th>Story ID</th><th>User</th><th>Priority</th><th>Epic</th></tr>
<tr><td>TS-03</td><td>Developer</td><td>Alta</td><td>EPIC-02</td></tr>
<tr><td colspan="4"><strong>Title:</strong> API de medicamentos y tratamientos</td></tr>
<tr><td colspan="4"><strong>Description</strong><br>Como developer, quiero proporcionar operaciones REST para medicamentos y tratamientos, para persistir la configuración administrada desde la aplicación del familiar.</td></tr>
<tr><td colspan="4"><strong>Acceptance Criteria</strong><br>
1. Dado un request válido de creación, cuando se registra un medicamento o tratamiento, entonces la API persiste el recurso y responde 201.<br>
2. Dado un recurso existente, cuando se solicita su actualización o desactivación, entonces la API conserva el cambio y responde correctamente.<br>
3. Dado un identificador inexistente, cuando se intenta modificar el recurso, entonces la API responde 404.
</td></tr>
</table>

<table>
<tr><th>Story ID</th><th>User</th><th>Priority</th><th>Epic</th></tr>
<tr><td>TS-04</td><td>Developer</td><td>Alta</td><td>EPIC-03</td></tr>
<tr><td colspan="4"><strong>Title:</strong> API de confirmación de tomas</td></tr>
<tr><td colspan="4"><strong>Description</strong><br>Como developer, quiero implementar una operación que registre la confirmación de una toma, para actualizar su estado de forma idempotente.</td></tr>
<tr><td colspan="4"><strong>Acceptance Criteria</strong><br>
1. Dado un request válido para una toma pendiente, cuando se registra la confirmación, entonces la API actualiza su estado y responde 200.<br>
2. Dado que la toma ya posee una confirmación, cuando se recibe nuevamente la misma operación, entonces la API evita crear un registro duplicado.
</td></tr>
</table>

<table>
<tr><th>Story ID</th><th>User</th><th>Priority</th><th>Epic</th></tr>
<tr><td>TS-05</td><td>Developer</td><td>Alta</td><td>EPIC-04</td></tr>
<tr><td colspan="4"><strong>Title:</strong> Proceso automático de tomas sin confirmar</td></tr>
<tr><td colspan="4"><strong>Description</strong><br>Como developer, quiero ejecutar un proceso que evalúe las tomas pendientes, para identificar vencimientos, registrar omisiones y generar los eventos correspondientes.</td></tr>
<tr><td colspan="4"><strong>Acceptance Criteria</strong><br>
1. Dado que una toma supera el periodo permitido sin confirmación, cuando el proceso automático la evalúa, entonces actualiza su estado según las reglas vigentes.<br>
2. Dado que la misma toma ya fue procesada, cuando el proceso vuelve a ejecutarse, entonces no genera una segunda omisión ni una segunda transición equivalente.
</td></tr>
</table>

<table>
<tr><th>Story ID</th><th>User</th><th>Priority</th><th>Epic</th></tr>
<tr><td>TS-06</td><td>Developer</td><td>Alta</td><td>EPIC-04</td></tr>
<tr><td colspan="4"><strong>Title:</strong> Integración del servicio de notificaciones push</td></tr>
<tr><td colspan="4"><strong>Description</strong><br>Como developer, quiero integrar un servicio de notificaciones push, para entregar recordatorios y alertas a los dispositivos registrados.</td></tr>
<tr><td colspan="4"><strong>Acceptance Criteria</strong><br>
1. Dado que existe un dispositivo registrado y un evento notificable, cuando se solicita el envío, entonces la integración entrega la solicitud al proveedor configurado.<br>
2. Dado que el proveedor rechaza el envío o el dispositivo ya no es válido, cuando se procesa la respuesta, entonces el sistema registra el resultado sin interrumpir el proceso principal.
</td></tr>
</table>

<table>
<tr><th>Story ID</th><th>User</th><th>Priority</th><th>Epic</th></tr>
<tr><td>TS-07</td><td>Developer</td><td>Alta</td><td>EPIC-01</td></tr>
<tr><td colspan="4"><strong>Title:</strong> API de cuenta y sesión del familiar</td></tr>
<tr><td colspan="4"><strong>Description</strong><br>Como developer, quiero implementar el registro, verificación e inicio de sesión del familiar, para proporcionar acceso autenticado a sus recursos.</td></tr>
<tr><td colspan="4"><strong>Acceptance Criteria</strong><br>
1. Dado un request de registro válido, cuando se procesa, entonces la API crea la cuenta pendiente de verificación.<br>
2. Dadas credenciales válidas de una cuenta habilitada, cuando se solicita iniciar sesión, entonces la API genera una sesión válida.
</td></tr>
</table>

<table>
<tr><th>Story ID</th><th>User</th><th>Priority</th><th>Epic</th></tr>
<tr><td>TS-08</td><td>Developer</td><td>Alta</td><td>EPIC-03</td></tr>
<tr><td colspan="4"><strong>Title:</strong> Servicio de generación de agenda de tomas</td></tr>
<tr><td colspan="4"><strong>Description</strong><br>Como developer, quiero generar las tomas futuras a partir de los tratamientos activos, para mantener la agenda de medicación actualizada.</td></tr>
<tr><td colspan="4"><strong>Acceptance Criteria</strong><br>
1. Dado un tratamiento activo con una pauta válida, cuando se procesa la programación, entonces el servicio genera las tomas futuras correspondientes.<br>
2. Dado que una pauta cambia, cuando se regenera la programación, entonces se actualizan únicamente las tomas futuras que todavía no poseen un resultado definitivo.
</td></tr>
</table>

<table>
<tr><th>Story ID</th><th>User</th><th>Priority</th><th>Epic</th></tr>
<tr><td>TS-09</td><td>Developer</td><td>Alta</td><td>EPIC-04</td></tr>
<tr><td colspan="4"><strong>Title:</strong> API de resumen familiar e historial</td></tr>
<tr><td colspan="4"><strong>Description</strong><br>Como developer, quiero proporcionar el estado reciente, historial y alertas del adulto mayor, para soportar las consultas de seguimiento del familiar.</td></tr>
<tr><td colspan="4"><strong>Acceptance Criteria</strong><br>
1. Dado un vínculo activo, cuando se consulta el resumen del adulto mayor, entonces la API responde con sus datos recientes autorizados.<br>
2. Dado que el solicitante no posee un vínculo válido, cuando intenta consultar dichos datos, entonces la API rechaza el acceso.
</td></tr>
</table>

<table>
<tr><th>Story ID</th><th>User</th><th>Priority</th><th>Epic</th></tr>
<tr><td>TS-10</td><td>Developer</td><td>Media</td><td>EPIC-05</td></tr>
<tr><td colspan="4"><strong>Title:</strong> Servicio de cálculo de adherencia y detección de patrones</td></tr>
<tr><td colspan="4"><strong>Description</strong><br>Como developer, quiero analizar el historial de tomas, para calcular indicadores e identificar patrones de adherencia.</td></tr>
<tr><td colspan="4"><strong>Acceptance Criteria</strong><br>
1. Dado un periodo con tomas registradas, cuando se ejecuta el cálculo, entonces el servicio obtiene indicadores a partir de confirmaciones, retrasos y omisiones.<br>
2. Dado que el historial cumple los criterios configurados de recurrencia, cuando se procesa el análisis, entonces el servicio registra el patrón identificado.
</td></tr>
</table>

<table>
<tr><th>Story ID</th><th>User</th><th>Priority</th><th>Epic</th></tr>
<tr><td>TS-11</td><td>Developer</td><td>Alta</td><td>EPIC-03</td></tr>
<tr><td colspan="4"><strong>Title:</strong> Integración de reconocimiento de voz</td></tr>
<tr><td colspan="4"><strong>Description</strong><br>Como developer, quiero integrar el mecanismo seleccionado de reconocimiento de voz, para convertir una confirmación hablada en información utilizable por Tata.</td></tr>
<tr><td colspan="4"><strong>Acceptance Criteria</strong><br>
1. Dado un audio válido, cuando se procesa mediante la alternativa seleccionada, entonces la integración devuelve la transcripción y la información disponible sobre su reconocimiento.<br>
2. Dado que la entrada no puede reconocerse con suficiente confiabilidad, cuando finaliza el procesamiento, entonces el sistema no registra automáticamente una toma como confirmada.
</td></tr>
</table>

<table>
<tr><th>Story ID</th><th>User</th><th>Priority</th><th>Epic</th></tr>
<tr><td>TS-12</td><td>Developer</td><td>Media</td><td>EPIC-07</td></tr>
<tr><td colspan="4"><strong>Title:</strong> API de inventario y reposición</td></tr>
<tr><td colspan="4"><strong>Description</strong><br>Como developer, quiero proporcionar operaciones de inventario y reposición, para mantener el stock asociado a cada medicamento.</td></tr>
<tr><td colspan="4"><strong>Acceptance Criteria</strong><br>
1. Dado un medicamento válido, cuando se registra un inventario o una reposición, entonces la API persiste el movimiento y actualiza el stock.<br>
2. Dado que el stock alcanza el umbral configurado, cuando se recalcula la disponibilidad, entonces el servicio genera la condición de stock bajo.
</td></tr>
</table>

<table>
<tr><th>Story ID</th><th>User</th><th>Priority</th><th>Epic</th></tr>
<tr><td>TS-13</td><td>Developer</td><td>Alta</td><td>EPIC-03</td></tr>
<tr><td colspan="4"><strong>Title:</strong> Almacenamiento local y sincronización de información esencial</td></tr>
<tr><td colspan="4"><strong>Description</strong><br>Como developer, quiero conservar localmente la información necesaria para la experiencia móvil y sincronizarla cuando exista conectividad, para mantener continuidad ante interrupciones temporales de red.</td></tr>
<tr><td colspan="4"><strong>Acceptance Criteria</strong><br>
1. Dado que la aplicación pierde conectividad después de haber sincronizado información esencial, cuando el usuario consulta dichos datos, entonces la aplicación puede recuperar la información local disponible.<br>
2. Dado que existen cambios pendientes y se restablece la conectividad, cuando se ejecuta la sincronización, entonces el sistema procesa los cambios evitando duplicados.
</td></tr>
</table>

<table>
<tr><th>Story ID</th><th>User</th><th>Priority</th><th>Epic</th></tr>
<tr><td>TS-14</td><td>Developer</td><td>Media</td><td>EPIC-08</td></tr>
<tr><td colspan="4"><strong>Title:</strong> API de planes y suscripciones</td></tr>
<tr><td colspan="4"><strong>Description</strong><br>Como developer, quiero gestionar planes y suscripciones mediante el backend, para determinar las capacidades disponibles para cada cuenta.</td></tr>
<tr><td colspan="4"><strong>Acceptance Criteria</strong><br>
1. Dado que existen planes configurados, cuando se consulta el catálogo, entonces la API responde con sus características vigentes.<br>
2. Dada una cuenta con una suscripción válida, cuando se consulta su estado, entonces la API proporciona el plan y las capacidades asociadas.
</td></tr>
</table>

#### Spike Stories

##### Spike 1: Investigación de reconocimiento de voz para confirmación de tomas

**Contexto**

La confirmación mediante voz busca reducir la necesidad de interacción táctil o escritura para el adulto mayor. El equipo necesita determinar qué alternativa proporciona una integración viable y un nivel de reconocimiento suficiente en español.

**Spike Story**

Como equipo de desarrollo, quiero investigar y prototipar alternativas de reconocimiento de voz, para seleccionar una opción viable para la confirmación de tomas.

**Criterios de Aceptación**

1. Dado que existen distintas alternativas de reconocimiento de voz, cuando se investigan al menos dos opciones, entonces el equipo documenta sus ventajas, restricciones, costos y requisitos de integración.
2. Dado que se selecciona una alternativa candidata, cuando se desarrolla un prototipo, entonces este procesa distintas frases de confirmación en español.
3. Dado que se completan las pruebas, cuando el equipo analiza sus resultados, entonces registra la alternativa recomendada y sus limitaciones.

**Timebox:** 8 horas.

##### Spike 2: Investigación de detección de patrones de olvido

**Contexto**

Tata busca identificar tendencias recurrentes dentro del historial de tomas. Antes de implementar esta capacidad es necesario determinar si un enfoque estadístico basado en reglas o una técnica de clasificación sencilla resulta adecuada para el alcance del proyecto.

**Spike Story**

Como equipo de desarrollo, quiero investigar y prototipar alternativas para detectar patrones de omisión, para seleccionar un enfoque comprensible y viable para Tata.

**Criterios de Aceptación**

1. Dado que existen distintas alternativas de análisis, cuando se comparan al menos un enfoque basado en reglas y otro basado en clasificación, entonces se documentan sus diferencias y complejidad.
2. Dado un conjunto de datos de prueba con confirmaciones y omisiones, cuando se ejecuta el prototipo, entonces este identifica los patrones conocidos incluidos en los datos.
3. Dado que se obtienen resultados, cuando se finaliza el análisis, entonces el equipo registra el enfoque recomendado y sus limitaciones.

**Timebox:** 8 horas.

##### Spike 3: Investigación de recordatorios y ejecución en segundo plano

**Contexto**

Los recordatorios constituyen una capacidad central de Tata y deben continuar funcionando bajo las restricciones propias de los sistemas operativos móviles. El equipo necesita evaluar cómo manejar programaciones y notificaciones cuando la aplicación no se encuentra activa.

**Spike Story**

Como equipo de desarrollo, quiero investigar los mecanismos disponibles para programar recordatorios y ejecutar tareas necesarias en segundo plano, para seleccionar una estrategia confiable para las aplicaciones móviles de Tata.

**Criterios de Aceptación**

1. Dado que Android y la alternativa multiplataforma presentan mecanismos distintos de ejecución en segundo plano, cuando se revisa su documentación, entonces se registran restricciones y alternativas aplicables.
2. Dado que se selecciona una estrategia candidata, cuando se realiza una prueba con la aplicación cerrada, entonces el equipo documenta el comportamiento observado.
3. Dado que finalizan las pruebas, cuando se comparan los resultados, entonces se registra la estrategia recomendada para el proyecto.

**Timebox:** 8 horas.

### 2.4.2. Impact Mapping

El Impact Mapping permitió relacionar los objetivos de negocio de Tata con los cambios esperados en el comportamiento de sus segmentos objetivo. Para ello se utilizaron los User Persona definidos previamente, identificando los impactos que pueden contribuir al cumplimiento de cada objetivo, los entregables necesarios para producir dichos impactos y las User Stories relacionadas.

#### Impact Mapping: Doña Carmen Rodríguez

El primer Impact Map corresponde al segmento de adultos mayores y utiliza a Doña Carmen Rodríguez como User Persona. El objetivo se orienta a reducir las tomas que permanecen sin confirmar mediante recordatorios, consulta de la agenda, mecanismos accesibles de confirmación y configuraciones que faciliten el uso de la aplicación.

![Impact Mapping de Doña Carmen Rodríguez](assets/impact-mapping-dona-carmen-rodriguez.png)

*Figura. Impact Mapping correspondiente al User Persona Doña Carmen Rodríguez.*

El mapa muestra que el cumplimiento del objetivo no depende de una sola funcionalidad. Los recordatorios buscan disminuir los olvidos, mientras que la agenda permite anticipar las próximas tomas. La confirmación accesible facilita registrar la acción realizada y las configuraciones de accesibilidad reducen las barreras de interacción que podrían dificultar el uso autónomo de Tata.

#### Impact Mapping: Diego Dani Mendoza

El segundo Impact Map corresponde al segmento de familiares o cuidadores y utiliza a Diego Dani Mendoza como User Persona. En este caso, el objetivo se concentra en incrementar el uso del seguimiento remoto y disminuir la dependencia de verificaciones manuales constantes.

![Impact Mapping de Diego Dani Mendoza](assets/impact-mapping-diego-dani-mendoza.png)

*Figura. Impact Mapping correspondiente al User Persona Diego Dani Mendoza.*

En este mapa, los impactos se concentran en reducir la incertidumbre del familiar durante el seguimiento remoto. El resumen y el historial permiten consultar información sin depender exclusivamente de llamadas, mientras que las alertas facilitan identificar situaciones que requieren atención. La analítica complementa este seguimiento mediante la identificación de retrasos, omisiones y patrones recurrentes que pueden orientar futuras acciones.

### 2.4.3. Product Backlog

El Product Backlog de Tata organiza los requisitos funcionales y técnicos identificados para el producto. La prioridad se estableció considerando primero el valor que cada funcionalidad proporciona a los segmentos objetivo y no únicamente el orden técnico requerido para su implementación.

Las estimaciones utilizan Story Points de 1, 2, 3, 5 y 8. La columna Sprint representa una asignación inicial que podrá revisarse posteriormente durante los Sprint Planning según la capacidad del equipo, los resultados de las iteraciones previas y las dependencias encontradas durante el desarrollo.

Las historias correspondientes al Landing Page se incluyen desde el Sprint 1. Las Technical Stories y Spike Stories se mantienen dentro del mismo Product Backlog porque representan trabajo necesario para habilitar funcionalidades del producto o reducir incertidumbre técnica.

| # Orden | Story ID | Título | Epic | Story Points | Sprint |
| ---: | --- | --- | --- | ---: | --- |
| 1 | US-05 | Recordatorio de toma de medicamento | EPIC-03 | 3 | Sprint 1 |
| 2 | US-06 | Confirmación accesible de una toma | EPIC-03 | 5 | Sprint 2 |
| 3 | US-03 | Registro de un nuevo medicamento | EPIC-02 | 5 | Sprint 1 |
| 4 | US-02 | Vinculación con la cuenta del adulto mayor | EPIC-01 | 5 | Sprint 1 |
| 5 | US-07 | Alerta ante una toma no confirmada | EPIC-04 | 5 | Sprint 2 |
| 6 | US-25 | Consulta del estado reciente del adulto mayor | EPIC-04 | 3 | Sprint 2 |
| 7 | US-14 | Creación de un tratamiento | EPIC-02 | 3 | Sprint 1 |
| 8 | US-15 | Definición de dosis y frecuencia | EPIC-02 | 3 | Sprint 1 |
| 9 | US-16 | Configuración de horarios e instrucciones | EPIC-02 | 3 | Sprint 1 |
| 10 | US-17 | Configuración de recordatorios | EPIC-02 | 3 | Sprint 1 |
| 11 | US-20 | Consulta de la próxima toma | EPIC-03 | 2 | Sprint 1 |
| 12 | US-24 | Consulta de agenda diaria de tomas | EPIC-03 | 3 | Sprint 2 |
| 13 | US-26 | Consulta del historial reciente de tomas | EPIC-04 | 3 | Sprint 2 |
| 14 | US-08 | Resumen semanal de adherencia | EPIC-05 | 3 | Sprint 3 |
| 15 | US-27 | Consulta del detalle de una alerta | EPIC-04 | 2 | Sprint 2 |
| 16 | US-22 | Recordatorio reforzado por falta de confirmación | EPIC-03 | 3 | Sprint 2 |
| 17 | US-23 | Confirmación dentro del periodo de tolerancia | EPIC-03 | 3 | Sprint 2 |
| 18 | US-18 | Activación y pausa de un tratamiento | EPIC-02 | 3 | Sprint 2 |
| 19 | US-04 | Edición y desactivación de un medicamento | EPIC-02 | 3 | Sprint 2 |
| 20 | US-21 | Consulta del detalle de una toma | EPIC-03 | 2 | Sprint 2 |
| 21 | US-19 | Consulta del detalle de un tratamiento | EPIC-02 | 2 | Sprint 2 |
| 22 | US-09 | Alerta de patrón de olvido recurrente | EPIC-05 | 5 | Sprint 3 |
| 23 | US-32 | Consulta del historial de adherencia | EPIC-05 | 3 | Sprint 3 |
| 24 | US-33 | Identificación de tomas tardías y omitidas | EPIC-05 | 3 | Sprint 3 |
| 25 | US-34 | Recomendaciones a partir de patrones | EPIC-05 | 5 | Sprint 3 |
| 26 | US-29 | Contacto con el adulto mayor ante una alerta | EPIC-04 | 2 | Sprint 2 |
| 27 | US-31 | Actualización del seguimiento de una alerta | EPIC-04 | 3 | Sprint 3 |
| 28 | US-28 | Configuración de preferencias de notificación | EPIC-04 | 3 | Sprint 3 |
| 29 | US-35 | Ajuste del tamaño de texto | EPIC-06 | 2 | Sprint 2 |
| 30 | US-36 | Activación de mayor contraste | EPIC-06 | 2 | Sprint 2 |
| 31 | US-38 | Activación de ayuda de lectura | EPIC-06 | 3 | Sprint 3 |
| 32 | US-39 | Configuración de horario de silencio y canales | EPIC-06 | 3 | Sprint 3 |
| 33 | US-37 | Reducción de movimiento | EPIC-06 | 2 | Sprint 3 |
| 34 | US-42 | Aviso de stock bajo | EPIC-07 | 3 | Sprint 4 |
| 35 | US-41 | Consulta de stock restante | EPIC-07 | 2 | Sprint 4 |
| 36 | US-40 | Registro de inventario inicial | EPIC-07 | 3 | Sprint 4 |
| 37 | US-43 | Registro de reposición de medicamento | EPIC-07 | 3 | Sprint 4 |
| 38 | US-46 | Consulta de la propuesta de valor de Tata | EPIC-09 | 2 | Sprint 1 |
| 39 | US-47 | Consulta de funcionalidades principales | EPIC-09 | 2 | Sprint 1 |
| 40 | US-49 | Continuación hacia registro o contacto | EPIC-09 | 2 | Sprint 1 |
| 41 | US-50 | Acceso adaptable al Landing Page | EPIC-09 | 3 | Sprint 1 |
| 42 | US-48 | Comparación de planes disponibles | EPIC-09 | 2 | Sprint 1 |
| 43 | US-10 | Registro de cuenta del familiar | EPIC-01 | 3 | Sprint 1 |
| 44 | US-11 | Verificación del correo del familiar | EPIC-01 | 2 | Sprint 1 |
| 45 | US-01 | Ingreso simplificado a la aplicación | EPIC-01 | 3 | Sprint 1 |
| 46 | US-12 | Registro del perfil del adulto mayor | EPIC-01 | 3 | Sprint 1 |
| 47 | US-13 | Consentimiento para establecer el vínculo | EPIC-01 | 3 | Sprint 1 |
| 48 | US-44 | Consulta del plan actual | EPIC-08 | 2 | Sprint 4 |
| 49 | US-45 | Activación o cambio de suscripción | EPIC-08 | 5 | Sprint 4 |
| 50 | US-30 | Registro de una nota de seguimiento | EPIC-04 | 2 | Sprint 4 |
| 51 | TS-03 | API de medicamentos y tratamientos | EPIC-02 | 5 | Sprint 1 |
| 52 | TS-08 | Servicio de generación de agenda de tomas | EPIC-03 | 5 | Sprint 1 |
| 53 | TS-04 | API de confirmación de tomas | EPIC-03 | 5 | Sprint 2 |
| 54 | TS-02 | API de vinculación de cuidado | EPIC-01 | 5 | Sprint 1 |
| 55 | TS-09 | API de resumen familiar e historial | EPIC-04 | 5 | Sprint 2 |
| 56 | TS-05 | Proceso automático de tomas sin confirmar | EPIC-04 | 5 | Sprint 2 |
| 57 | TS-06 | Integración del servicio de notificaciones push | EPIC-04 | 5 | Sprint 2 |
| 58 | TS-11 | Integración de reconocimiento de voz | EPIC-03 | 5 | Sprint 2 |
| 59 | TS-13 | Almacenamiento local y sincronización | EPIC-03 | 8 | Sprint 2 |
| 60 | TS-10 | Servicio de cálculo de adherencia y patrones | EPIC-05 | 8 | Sprint 3 |
| 61 | TS-07 | API de cuenta y sesión del familiar | EPIC-01 | 5 | Sprint 1 |
| 62 | TS-01 | Servicio de autenticación mediante PIN | EPIC-01 | 3 | Sprint 1 |
| 63 | TS-12 | API de inventario y reposición | EPIC-07 | 5 | Sprint 4 |
| 64 | TS-14 | API de planes y suscripciones | EPIC-08 | 5 | Sprint 4 |
| 65 | SP-01 | Investigación de reconocimiento de voz | EPIC-03 | 3 | Sprint 1 |
| 66 | SP-03 | Investigación de ejecución en segundo plano | EPIC-03 | 3 | Sprint 1 |
| 67 | SP-02 | Investigación de detección de patrones de olvido | EPIC-05 | 5 | Sprint 2 |

#### Evidencia del Product Backlog

![Product Backlog de Tata](assets/product-backlog-tata.png)

*Figura. Product Backlog de Tata.*

Enlace público al Product Backlog: https://trello.com/b/wuHmMypU/apps-moviles

### 2.5. Strategic-Level Domain-Driven Design

El Strategic-Level Domain-Driven Design se utilizó para organizar el dominio de Tata a partir de las responsabilidades, reglas y conceptos identificados durante las etapas anteriores del proyecto. El objetivo de esta etapa no es definir todavía componentes físicos de software, sino establecer límites conceptuales que permitan mantener modelos coherentes y reducir el acoplamiento entre distintas áreas del dominio.

Para ello, se profundizó el EventStorming desarrollado previamente, incorporando actores, comandos, políticas, modelos de lectura, sistemas externos y agregados. A partir de estos elementos se identificaron candidatos a Bounded Context, se analizaron los mensajes relevantes que atraviesan sus límites y se documentó la responsabilidad interna de cada contexto mediante Bounded Context Canvases.

Este análisis permite pasar de una representación general del comportamiento de Tata hacia una estructura estratégica del dominio que posteriormente servirá como base para el Context Mapping y las decisiones de arquitectura de software.

### 2.5.1. EventStorming

El EventStorming se utilizó para profundizar los procesos identificados previamente en el Big Picture EventStorming. Mientras el Big Picture permitió observar de forma global qué ocurre dentro del dominio de Tata, esta etapa incorporó mayor detalle sobre las acciones que originan los eventos, las reglas que reaccionan ante ellos y los conceptos responsables de mantener el estado y las reglas del negocio.

El modelado se desarrolló de manera progresiva. Inicialmente se organizaron los eventos de dominio según su secuencia temporal y se identificaron puntos problemáticos y eventos pivote. Posteriormente se incorporaron comandos y actores para representar qué acciones originan cada cambio dentro del dominio.

A medida que el modelo fue refinado, se añadieron políticas para representar comportamientos automáticos, modelos de lectura para identificar la información requerida antes de ejecutar determinadas acciones y sistemas externos que participan en los distintos procesos. Finalmente, los comandos y eventos relacionados se organizaron alrededor de agregados, lo que permitió comenzar a reconocer responsabilidades y límites conceptuales dentro del dominio.

![EventStorming de Tata](assets/eventstorming-tata.png)

*Figura. EventStorming del dominio de Tata.*

Enlace a la versión del EventStorming: [https://miro.com/app/board/uXjVHq5Jc9w=/](https://miro.com/app/board/uXjVHq5Jc9w=/)

#### Evolución del EventStorming

La construcción progresiva del EventStorming permitió aumentar el nivel de detalle sin perder la secuencia principal del dominio. Los primeros pasos estuvieron orientados a comprender el comportamiento y sus principales problemas, mientras que las etapas posteriores incorporaron los elementos necesarios para analizar las reglas y responsabilidades involucradas.

![Evolución del EventStorming](assets/eventstorming-evolucion1.png)

*Figura. Evolución del EventStorming de Tata Pain Points.*

![Evolución del EventStorming](assets/eventstorming-evolucion2.png)

*Figura. Evolución del EventStorming de Tata Commands.*

![Evolución del EventStorming](assets/eventstorming-evolucion3.png)

*Figura. Evolución del EventStorming de Tata Aggregates.*

#### 2.5.1.1. Candidate Context Discovery

A partir del EventStorming refinado se analizaron grupos de eventos, comandos, políticas y agregados que compartían un mismo lenguaje y conjunto de responsabilidades. El propósito fue identificar áreas del dominio que requieren mantener un modelo propio y cuyos conceptos pueden evolucionar de forma relativamente independiente.

La agrupación no se realizó únicamente por proximidad dentro del tablero. Se consideraron principalmente las responsabilidades asumidas por cada conjunto de elementos, las reglas que gobiernan su comportamiento y los cambios de significado que aparecen al pasar de un proceso a otro.

Por ejemplo, **Gestión del tratamiento** administra la definición del medicamento, dosis, frecuencia y horario, mientras que **Ejecución de tomas** administra cada instancia concreta generada a partir de esa configuración. Aunque ambos contextos trabajan con información relacionada, responden a preguntas diferentes dentro del dominio y poseen ciclos de vida distintos.

![Candidate Context Discovery](assets/candidate-context-discovery.png)

*Figura. Descubrimiento de candidatos a Bounded Context.*

Enlace a la version de Eventstorming Bounded Context: [https://miro.com/app/board/uXjVHq5Jc9w=/](https://miro.com/app/board/uXjVHq5Jc9w=/)

Como resultado se identificaron los siguientes candidatos:

| Candidate Context | Responsabilidad principal |
| --- | --- |
| Identidad y suscripción | Gestionar la existencia, acceso y habilitación de los usuarios |
| Vínculo de cuidado | Administrar la relación autorizada entre familiar y adulto mayor |
| Gestión del tratamiento | Definir medicamentos, dosis, horarios e instrucciones |
| Ejecución de tomas | Gestionar cada toma programada y su confirmación |
| Omisión y escalamiento | Administrar tomas no confirmadas, alertas y escalamiento |
| Seguimiento familiar | Presentar información y registrar las intervenciones del cuidador |
| Accesibilidad y preferencias | Adaptar la interacción y las preferencias del usuario |
| Analítica de adherencia | Calcular indicadores, patrones e insights de adherencia |
| Inventario y reposición | Mantener la disponibilidad y continuidad de los medicamentos |

Estos límites se consideran candidatos dentro de esta etapa y no implican que cada contexto deba implementarse posteriormente como un microservicio independiente.

#### 2.5.1.2. Domain Message Flows Modeling

El Domain Message Flows Modeling se utilizó para representar las interacciones que ocurren entre los actores, Bounded Contexts y sistemas externos que participan en los principales procesos de Tata. A diferencia del EventStorming, donde se estudia el comportamiento interno del dominio mediante eventos, comandos y políticas, en esta etapa el interés se centra en los mensajes que atraviesan los límites previamente identificados.

El modelado se desarrolló a partir de escenarios concretos del dominio. Cada escenario representa una situación relevante de uso y muestra la secuencia de mensajes intercambiados entre sus participantes. Los mensajes se clasificaron como **Commands**, cuando solicitan la ejecución de una acción; **Events**, cuando comunican un hecho que ya ocurrió; y **Queries**, cuando un participante requiere información para continuar con una decisión o proceso.

Para mantener los diagramas legibles, cada escenario fue modelado de manera independiente. Las relaciones representan dependencias conceptuales del dominio y no establecen todavía el mecanismo técnico mediante el cual se implementará la comunicación.

##### Registro y vinculación del adulto mayor

Este escenario representa el proceso mediante el cual un familiar o cuidador ingresa a Tata y establece una relación de cuidado con un adulto mayor. El flujo comienza con la creación y verificación de la cuenta, continúa con el registro del adulto mayor y finaliza cuando la vinculación es aceptada y confirmada.

En este proceso participan principalmente **Identidad y suscripción** y **Vínculo de cuidado**. El primero administra el estado de la cuenta, mientras que el segundo mantiene la relación autorizada entre ambos usuarios. El servicio de correo interviene como sistema externo durante la verificación de la cuenta.

![Domain Message Flow - Registro y vinculación](assets/domain-message-flow-registro-vinculacion.png)

*Figura. Domain Message Flow para el registro y vinculación del adulto mayor.*

##### Configuración y activación del tratamiento

Este escenario describe la configuración inicial de un tratamiento asociado al adulto mayor. El familiar registra el medicamento y define los datos necesarios para su administración, como la dosis, frecuencia, horario e instrucciones de toma.

Antes de realizar determinadas operaciones, **Gestión del tratamiento** puede consultar a **Vínculo de cuidado** para verificar que el familiar se encuentre autorizado para administrar la información del adulto mayor. Una vez completa la configuración, la activación del tratamiento genera información necesaria para que **Ejecución de tomas** pueda comenzar a programar las tomas correspondientes.

![Domain Message Flow - Configuración del tratamiento](assets/domain-message-flow-configuracion-tratamiento.png)

*Figura. Domain Message Flow para la configuración y activación del tratamiento.*

##### Confirmación de una toma mediante un toque

Este escenario representa el camino esperado cuando el adulto mayor recibe un recordatorio y confirma correctamente una toma mediante interacción táctil.

El adulto puede consultar la próxima toma programada y posteriormente registrar su confirmación. Una vez aceptada, **Ejecución de tomas** comunica el resultado a otros contextos interesados. **Analítica de adherencia** utiliza el evento para actualizar las métricas del adulto, mientras que **Seguimiento familiar** puede utilizarlo para actualizar el estado mostrado al familiar o cuidador.

![Domain Message Flow - Confirmación por toque](assets/domain-message-flow-confirmacion-toque.png)

*Figura. Domain Message Flow para la confirmación de una toma mediante un toque.*

##### Confirmación de una toma mediante voz

Este escenario representa la alternativa accesible mediante la cual el adulto mayor puede registrar la confirmación utilizando su voz. En este flujo, **Ejecución de tomas** coordina la interacción con un servicio externo de reconocimiento de voz para procesar el audio recibido.

Si la transcripción puede ser validada, se registra la confirmación y se generan los mismos eventos de dominio empleados por el flujo táctil. De esta manera, el método utilizado para interactuar puede variar sin modificar el significado principal del evento **Toma confirmada** para los demás contextos.

![Domain Message Flow - Confirmación por voz](assets/domain-message-flow-confirmacion-voz.png)

*Figura. Domain Message Flow para la confirmación de una toma mediante voz.*

##### Toma no confirmada, omisión y escalamiento

Este escenario representa el flujo alternativo que se inicia cuando el adulto mayor no confirma una toma dentro del periodo esperado.

Al finalizar la ventana inicial, **Ejecución de tomas** comunica la ausencia de confirmación a **Omisión y escalamiento**. Este contexto administra los recordatorios reforzados y la ventana de tolerancia. Si el tiempo establecido concluye sin una respuesta, se registra la omisión y se genera una alerta.

La omisión también es comunicada a **Analítica de adherencia**, mientras que **Seguimiento familiar** recibe la información necesaria para advertir al familiar o cuidador. Los servicios externos de notificación permiten posteriormente entregar la alerta mediante los canales habilitados.

![Domain Message Flow - Omisión y escalamiento](assets/domain-message-flow-omision-escalamiento.png)

*Figura. Domain Message Flow para una toma no confirmada, omisión y escalamiento.*

##### Seguimiento familiar ante una alerta

Este escenario describe las acciones disponibles para el familiar después de recibir información sobre una situación que requiere atención. El familiar puede consultar el resumen del adulto mayor, revisar las tomas recientes y acceder a los indicadores de adherencia disponibles.

**Seguimiento familiar** reúne información proporcionada por otros contextos sin asumir sus responsabilidades internas. Cuando el familiar necesita intervenir, puede registrar una nota, iniciar una llamada o utilizar otro canal disponible para comunicarse con el adulto mayor.

![Domain Message Flow - Seguimiento familiar](assets/domain-message-flow-seguimiento-familiar.png)

*Figura. Domain Message Flow para el seguimiento familiar ante una alerta.*

##### Consolidación de adherencia y detección de patrones

Este escenario representa el procesamiento de los resultados acumulados durante la ejecución de las tomas. **Analítica de adherencia** recibe información acerca de las tomas confirmadas, tardías u omitidas y la utiliza para consolidar periodos de seguimiento.

A partir de estos registros se calculan indicadores de adherencia y se pueden identificar patrones recurrentes relacionados con determinados horarios o periodos. Los resultados relevantes son publicados para que **Seguimiento familiar** pueda mostrarlos posteriormente al cuidador sin tener que reproducir internamente la lógica analítica.

![Domain Message Flow - Analítica de adherencia](assets/domain-message-flow-analitica-adherencia.png)

*Figura. Domain Message Flow para la consolidación de adherencia y detección de patrones.*

##### Reposición y continuidad del tratamiento

Este escenario representa el seguimiento del stock disponible de un medicamento y las acciones relacionadas con su reposición. **Inventario y reposición** permite consultar las unidades restantes y detectar situaciones en las que el medicamento puede agotarse antes de las próximas tomas.

Cuando se alcanza el umbral definido, se puede generar un aviso al familiar. Después de registrar una reposición o un nuevo lote, el contexto comunica los cambios necesarios para mantener actualizada la planificación de futuras tomas y conservar la continuidad del tratamiento.

![Domain Message Flow - Reposición y continuidad](assets/domain-message-flow-reposicion-continuidad.png)

*Figura. Domain Message Flow para la reposición y continuidad del tratamiento.*

En conjunto, los escenarios permitieron identificar los principales intercambios de información entre los límites del dominio de Tata. El modelado muestra que los Bounded Contexts colaboran mediante mensajes específicos sin compartir directamente sus reglas internas. Este resultado también sirve como entrada para documentar con mayor precisión las responsabilidades, mensajes y dependencias de cada contexto mediante los Bounded Context Canvases.

Enlace a la version del Domain Message Flow: [https://miro.com/app/board/uXjVHq5Jc9w=/](https://miro.com/app/board/uXjVHq5Jc9w=/)

#### 2.5.1.3. Bounded Context Canvases

Los Bounded Context Canvases se utilizaron para documentar individualmente los contextos identificados durante el Candidate Context Discovery. Mientras el EventStorming permitió reconocer los posibles límites y el Domain Message Flows Modeling mostró las interacciones entre ellos, los canvases permitieron precisar el propósito y las responsabilidades que corresponden a cada contexto.

Cada canvas documenta su descripción, clasificación estratégica, características del modelo, decisiones de negocio y términos principales del Ubiquitous Language. Asimismo, se especifican los Commands, Events y Queries que el contexto consume o produce, además de sus principales proveedores y consumidores de información.

Esta representación permitió revisar que cada contexto mantuviera responsabilidades coherentes y que las colaboraciones necesarias pudieran realizarse mediante mensajes explícitos, evitando que diferentes áreas del dominio dependieran de los detalles internos de otras.

##### Identidad y suscripción

El Bounded Context **Identidad y suscripción** concentra las responsabilidades relacionadas con la existencia y habilitación de una cuenta dentro de Tata. Incluye la creación del usuario, la verificación de su información básica y el estado del plan asociado.

Sus reglas determinan cuándo una cuenta puede considerarse habilitada y qué información puede ser utilizada posteriormente por otros contextos. Entre los conceptos principales de su lenguaje se encuentran **Cuenta**, **Usuario**, **Plan**, **Suscripción**, **Consentimiento** y **Estado de cuenta**.

Una de sus principales salidas es el evento **Cuenta habilitada**, que permite que el contexto de Vínculo de cuidado continúe con el registro de la relación entre el familiar y el adulto mayor.

![Bounded Context Canvas - Identidad y suscripción](assets/bounded-context-canvas-identidad-suscripcion.png)

*Figura. Bounded Context Canvas de Identidad y suscripción.*

##### Vínculo de cuidado

El contexto **Vínculo de cuidado** administra la relación autorizada entre el adulto mayor y el familiar o cuidador encargado de su seguimiento.

Su modelo mantiene información relacionada con el adulto mayor, los códigos de vinculación, el consentimiento y el estado de la relación. Entre sus principales decisiones se encuentra validar que una cuenta pueda iniciar una vinculación y que el consentimiento requerido haya sido registrado antes de habilitar el seguimiento.

El evento **Vínculo de cuidado confirmado** representa uno de sus resultados más importantes, ya que permite que otros contextos reconozcan que el familiar posee una relación válida con el adulto mayor.

![Bounded Context Canvas - Vínculo de cuidado](assets/bounded-context-canvas-vinculo-cuidado.png)

*Figura. Bounded Context Canvas de Vínculo de cuidado.*

##### Gestión del tratamiento

El contexto **Gestión del tratamiento** mantiene la definición operativa del tratamiento del adulto mayor. Dentro de este límite se gestionan el medicamento, la dosis, frecuencia, horario, instrucciones y configuración de recordatorios.

Su responsabilidad termina en definir **qué tratamiento debe seguirse**. No administra cada ejecución concreta de una dosis, ya que esa responsabilidad pertenece a Ejecución de tomas.

Cuando la configuración requerida se encuentra completa, el contexto puede publicar el evento **Tratamiento activado**, que proporciona la información necesaria para generar las futuras tomas.

![Bounded Context Canvas - Gestión del tratamiento](assets/bounded-context-canvas-gestion-tratamiento.png)

*Figura. Bounded Context Canvas de Gestión del tratamiento.*

##### Ejecución de tomas

El contexto **Ejecución de tomas** administra las instancias concretas generadas a partir de un tratamiento activo. Su responsabilidad comienza cuando debe programarse una toma y continúa hasta que esta queda confirmada o se detecta que permanece sin confirmación.

Dentro de este contexto se manejan conceptos como **Toma**, **Próxima toma**, **Ventana de confirmación**, **Confirmación por toque** y **Confirmación por voz**.

También coordina servicios externos necesarios para determinadas interacciones, como el reconocimiento de voz o las notificaciones. Sus principales eventos de salida incluyen **Toma confirmada**, **Toma no confirmada** e **Historial diario actualizado**.

![Bounded Context Canvas - Ejecución de tomas](assets/bounded-context-canvas-ejecucion-tomas.png)

*Figura. Bounded Context Canvas de Ejecución de tomas.*

##### Omisión y escalamiento

El contexto **Omisión y escalamiento** administra las situaciones excepcionales originadas cuando una toma permanece sin confirmación.

Este contexto controla la ventana de tolerancia, los recordatorios reforzados, el registro de una omisión, la generación de alertas y el escalamiento cuando corresponde. De esta manera, la lógica de excepción no queda mezclada con la ejecución normal de una toma.

Entre sus eventos principales se encuentran **Toma omitida registrada**, **Alerta al cuidador generada** y **Escalamiento ejecutado**. Estos eventos pueden ser consumidos posteriormente por Analítica de adherencia y Seguimiento familiar.

![Bounded Context Canvas - Omisión y escalamiento](assets/bounded-context-canvas-omision-escalamiento.png)

*Figura. Bounded Context Canvas de Omisión y escalamiento.*

##### Seguimiento familiar

El contexto **Seguimiento familiar** representa la visión del dominio orientada al familiar o cuidador. Su responsabilidad es reunir y presentar la información necesaria para conocer el estado reciente del adulto mayor y facilitar una intervención cuando sea necesaria.

Este contexto recibe información producida por Ejecución de tomas, Omisión y escalamiento y Analítica de adherencia. A partir de ella permite construir un resumen familiar, consultar información relevante y registrar acciones como notas del cuidador.

El contexto no recalcula la adherencia ni decide cuándo una toma se convierte en una omisión; consume los resultados generados por los contextos responsables de esas reglas.

![Bounded Context Canvas - Seguimiento familiar](assets/bounded-context-canvas-seguimiento-familiar.png)

*Figura. Bounded Context Canvas de Seguimiento familiar.*

##### Accesibilidad y preferencias

El contexto **Accesibilidad y preferencias** administra las configuraciones que permiten adaptar la interacción con Tata según las necesidades de cada usuario.

Incluye elementos como el tamaño de texto, contraste reforzado, reducción de movimiento, confirmación por voz, ayuda de lectura, horario de silencio y canales de notificación.

Estas preferencias poseen un carácter transversal debido a que pueden condicionar el comportamiento de otras áreas del producto. Sin embargo, mantenerlas dentro de un modelo propio evita que cada contexto deba definir nuevamente las reglas relacionadas con la configuración personal del usuario.

![Bounded Context Canvas - Accesibilidad y preferencias](assets/bounded-context-canvas-accesibilidad-preferencias.png)

*Figura. Bounded Context Canvas de Accesibilidad y preferencias.*

##### Analítica de adherencia

El contexto **Analítica de adherencia** transforma los resultados acumulados de las tomas en información útil para comprender la evolución del tratamiento.

Su modelo maneja conceptos como **Adherencia**, **Tasa de adherencia**, **Toma tardía**, **Omisión**, **Patrón horario**, **Riesgo de omisión**, **Insight** y **Recomendación**.

El contexto recibe los registros generados durante la ejecución normal y los casos de omisión. A partir de ellos puede consolidar periodos, calcular indicadores e identificar patrones. Los resultados obtenidos se publican posteriormente para que otros contextos, especialmente Seguimiento familiar, puedan utilizarlos.

![Bounded Context Canvas - Analítica de adherencia](assets/bounded-context-canvas-analitica-adherencia.png)

*Figura. Bounded Context Canvas de Analítica de adherencia.*

##### Inventario y reposición

El contexto **Inventario y reposición** administra la disponibilidad de los medicamentos asociados a un tratamiento y las acciones necesarias para mantener su continuidad.

Su modelo contempla el stock disponible, el umbral de reposición, los lotes registrados y el proceso de reabastecimiento. Cuando detecta que las unidades restantes se acercan a un límite establecido, puede generar un aviso para el familiar.

Después de registrar una reposición, el contexto puede producir información que permita actualizar la planificación de futuras tomas. De esta manera, la disponibilidad física del medicamento se mantiene separada de las reglas propias de la configuración del tratamiento y de la ejecución diaria.

![Bounded Context Canvas - Inventario y reposición](assets/bounded-context-canvas-inventario-reposicion.png)

*Figura. Bounded Context Canvas de Inventario y reposición.*

En conjunto, los nueve Bounded Context Canvases permitieron precisar las responsabilidades y colaboraciones identificadas durante el EventStorming. El resultado proporciona una visión más estable de los límites estratégicos del dominio y sirve como base para el posterior Context Mapping, donde se analizarán las relaciones existentes entre estos contextos y la forma en que sus modelos deben colaborar.

Enlace a la version de Bounded Context Canvas: [https://miro.com/app/board/uXjVHq5Jc9w=/](https://miro.com/app/board/uXjVHq5Jc9w=/)

### 2.5.2. Context Mapping

El Context Mapping se utilizó para representar las relaciones estructurales entre los nueve Bounded Contexts identificados en el Candidate Context Discovery, a partir de la información ya documentada en el Domain Message Flows Modeling y en los Bounded Context Canvases. El objetivo de esta etapa es explicitar, para cada colaboración relevante entre contextos, qué patrón de relación de Domain-Driven Design describe mejor la forma en que ambos modelos deben coexistir.

Para construir el mapa, el equipo revisó cada mensaje identificado entre contextos y discutió preguntas exploratorias del tipo "¿qué pasaría si...?" antes de fijar el patrón definitivo. Entre las discusiones más relevantes:

- **¿Qué pasaría si moviéramos la validación del vínculo de cuidado dentro de Gestión del tratamiento?** Se descartó porque duplicaría las reglas de autorización ya definidas en Vínculo de cuidado y rompería la responsabilidad única de ese contexto. Se optó por mantener una relación **Customer/Supplier**, donde Gestión del tratamiento consulta a Vínculo de cuidado sin reimplementar su lógica.
- **¿Qué pasaría si Seguimiento familiar recalculara la adherencia o decidiera cuándo una toma se convierte en omisión?** Se descartó porque mezclaría reglas de negocio que ya pertenecen a Ejecución de tomas, Omisión y escalamiento y Analítica de adherencia. Se decidió que Seguimiento familiar se comporte como **Conformist** frente a esos tres contextos: consume sus resultados tal como se publican, sin traducirlos ni cuestionarlos.
- **¿Qué pasaría si duplicáramos las preferencias de accesibilidad dentro de cada contexto que las necesita (Ejecución de tomas, Omisión y escalamiento, Seguimiento familiar)?** Se descartó por el riesgo de que las configuraciones queden inconsistentes entre contextos. Se optó por tratar a Accesibilidad y preferencias como un **Shared Kernel** acotado, limitado a un conjunto pequeño y estable de conceptos (canal de notificación, horario de silencio, confirmación por voz) que los demás contextos referencian directamente.
- **¿Qué pasaría si Tata se acoplara directamente a los modelos de los servicios externos de reconocimiento de voz, notificaciones push y correo?** Se descartó porque un cambio en la API de cualquiera de esos proveedores impactaría directamente el modelo de dominio. Se decidió aislar cada integración mediante un **Anti-Corruption Layer**, de modo que Tata siempre trabaje con sus propios conceptos (Confirmación por voz, Alerta, Correo verificado) independientemente del contrato específico del proveedor.

El resultado de esta discusión se resume en el siguiente Context Map:

![Context Map de Tata](assets/context-map-tata.png)

*Figura. Context Map de Tata, con los patrones de relación aplicados entre Bounded Contexts.*

En conjunto, la mayoría de las colaboraciones entre contextos internos de Tata siguen relaciones de tipo **Customer/Supplier**, reflejando un flujo con dirección clara (identidad → vínculo → tratamiento → ejecución → omisión/analítica). Seguimiento familiar se mantiene deliberadamente como **Conformist** frente a los contextos que sí poseen las reglas de negocio, evitando duplicar lógica. Accesibilidad y preferencias se aísla como un **Shared Kernel** pequeño y estable para no fragmentar la configuración del usuario, mientras que toda integración con los sistemas externos de terceros (correo, reconocimiento de voz, notificaciones push) queda protegida mediante un **Anti-Corruption Layer**. Esta estructura sirve como base para las decisiones de Software Architecture que se detallan en la siguiente sección.

### 2.5.3. Software Architecture

En esta sección el equipo presenta y explica la representación de la arquitectura de software de Tata mediante **C4 Model**, utilizando **Structurizr DSL** como herramienta de Diagram-as-Code. El objetivo es mostrar, de forma progresiva y en distintos niveles de abstracción, cómo el sistema se relaciona con sus usuarios y sistemas externos (Context), cómo se descompone en aplicaciones y servicios desplegables (Container) y cómo estos se distribuyen físicamente en la infraestructura (Deployment).

Las decisiones de arquitectura reflejan directamente los resultados del Context Mapping (sección 2.5.2): los nueve Bounded Contexts candidatos se materializan como servicios backend independientes que colaboran mediante un API Gateway y un bus de mensajes, mientras que las integraciones con sistemas externos (reconocimiento de voz, notificaciones push y correo) se mantienen aisladas mediante el patrón Anti-Corruption Layer ya definido a nivel estratégico.

El archivo fuente completo en Structurizr DSL se encuentra documentado como artefacto del proyecto en el repositorio del equipo.

#### 2.5.3.1. Software Architecture Context Level Diagrams

El **Context Diagram** (C4 Nivel 1) muestra a Tata como una única caja negra, rodeada de los actores y sistemas externos con los que interactúa, sin exponer todavía su estructura interna. Este nivel permite comunicar el alcance del sistema a una audiencia no técnica.

Los actores identificados son el **Familiar/Cuidador**, quien configura tratamientos y monitorea el estado del adulto mayor; el **Adulto Mayor**, quien consulta su agenda y confirma sus tomas; y el **Visitante**, quien navega el Landing Page para conocer la propuesta de valor de Tata. Los sistemas externos considerados son el **Servicio de Notificaciones Push** (para recordatorios y alertas), el **Servicio de Reconocimiento de Voz** (para validar confirmaciones habladas) y el **Servicio de Correo** (para la verificación de cuentas).

![Context Diagram de Tata](assets/context.png)

*Figura. Software Architecture Context Level Diagram de Tata (C4 Nivel 1).*

El diagrama evidencia que, si bien Tata concentra la lógica del negocio, depende de tres integraciones externas críticas para cumplir su propuesta de valor: sin el servicio de notificaciones push no sería posible entregar recordatorios ni alertas al familiar, y sin el servicio de reconocimiento de voz no sería posible ofrecer la confirmación accesible por voz que constituye uno de los diferenciadores frente a la competencia (ver sección 2.1).

#### 2.5.3.2. Software Architecture Container Level Diagrams

El **Container Diagram** (C4 Nivel 2) descompone a Tata en las aplicaciones y servicios desplegables que lo conforman, mostrando sus responsabilidades, la tecnología elegida para cada uno y cómo se comunican entre sí. Cada Container corresponde, en su mayoría, a uno de los Bounded Contexts identificados en el Candidate Context Discovery (sección 2.5.1.1), lo que mantiene la trazabilidad entre el diseño estratégico y la arquitectura de software.

Se definieron los siguientes contenedores: **Landing Page** (sitio estático), **Mobile App** (aplicación única con vistas diferenciadas para el familiar y el adulto mayor), un **API Gateway** como punto de entrada único, nueve **servicios backend** — uno por Bounded Context —, una **base de datos** relacional compartida y un **bus de mensajes** para la comunicación asíncrona entre servicios (por ejemplo, la publicación de *Toma confirmada* o *Toma no confirmada* que consumen Omisión y escalamiento, Analítica de adherencia y Seguimiento familiar).

![Container Diagram de Tata](assets/container.png)

*Figura. Software Architecture Container Level Diagram de Tata (C4 Nivel 2).*

Como decisión de tecnología, el **API Gateway** centraliza el enrutamiento hacia los nueve servicios, evitando que la Mobile App conozca la ubicación interna de cada uno. La comunicación entre servicios ante eventos de dominio (como una toma confirmada u omitida) se realiza de forma asíncrona mediante el **bus de mensajes**, lo cual es coherente con la relación **Customer/Supplier** definida en el Context Mapping (sección 2.5.2): el servicio productor del evento no necesita conocer a sus consumidores. Se identifica **Family Monitoring Service** con acceso de solo lectura a la base de datos, reflejando su rol **Conformist** frente a los contextos que sí poseen las reglas de negocio.

#### 2.5.3.3. Software Architecture Deployment Diagrams

El **Deployment Diagram** muestra la distribución física de los contenedores sobre la infraestructura de despliegue: dónde se aloja cada aplicación, qué proveedor cloud se utiliza y cómo se relacionan los nodos de hardware/plataforma entre sí. Este nivel de detalle no requiere ser exhaustivo para un proyecto académico, pero sí debe evidenciar los entornos considerados para producción.

Para Tata se definió un entorno de **Producción** sobre **AWS**: el Landing Page se despliega en un servicio de hosting estático con CDN, la Mobile App se distribuye a través de Firebase App Distribution / las tiendas de aplicaciones hacia el dispositivo del usuario, los nueve servicios backend y el API Gateway se despliegan como pods dentro de un clúster de **Amazon EKS (Kubernetes)**, la base de datos utiliza **Amazon RDS (PostgreSQL)** y el bus de mensajes se aloja en **Amazon MQ (RabbitMQ)**.

![Deployment Diagram de Tata](assets/deployment.png)

*Figura. Software Architecture Deployment Diagram de Tata.*

Esta configuración permite que la Landing Page, al ser un sitio estático, escale de forma independiente mediante CDN sin afectar el backend. El uso de un clúster de Kubernetes para los nueve servicios facilita el escalamiento independiente de cada Bounded Context por ejemplo, ante picos de tráfico en **Intake Execution Service** durante las horas de mayor concentración de tomas programadas sin necesidad de escalar la totalidad del sistema. Asimismo, aislar la base de datos en Amazon RDS y el bus de mensajes en Amazon MQ como servicios administrados reduce la carga operativa del equipo y refuerza la separación entre la lógica de negocio y la infraestructura de persistencia y mensajería.


## 2.6. Tactical-Level Domain-Driven Design

### 2.6.1. Bounded Context: Ejecución de tomas

#### 2.6.1.1. Domain Layer

#### 2.6.1.2. Interface Layer

#### 2.6.1.3. Application Layer

#### 2.6.1.4. Infrastructure Layer

#### 2.6.1.5. Bounded Context Software Architecture Component Level Diagrams

#### 2.6.1.6. Bounded Context Software Architecture Code Level Diagrams

##### 2.6.1.6.1. Bounded Context Domain Layer Class Diagrams

##### 2.6.1.6.2. Bounded Context Database Design Diagram


### 2.6.2. Bounded Context: Analítica de adherencia

#### 2.6.2.1. Domain Layer

#### 2.6.2.2. Interface Layer

#### 2.6.2.3. Application Layer

#### 2.6.2.4. Infrastructure Layer

#### 2.6.2.5. Bounded Context Software Architecture Component Level Diagrams

#### 2.6.2.6. Bounded Context Software Architecture Code Level Diagrams

##### 2.6.2.6.1. Bounded Context Domain Layer Class Diagrams

##### 2.6.2.6.2. Bounded Context Database Design Diagram


### 2.6.3. Bounded Context: Identidad y suscripción

#### 2.6.3.1. Domain Layer

#### 2.6.3.2. Interface Layer

#### 2.6.3.3. Application Layer

#### 2.6.3.4. Infrastructure Layer

#### 2.6.3.5. Bounded Context Software Architecture Component Level Diagrams

#### 2.6.3.6. Bounded Context Software Architecture Code Level Diagrams

##### 2.6.3.6.1. Bounded Context Domain Layer Class Diagrams

##### 2.6.3.6.2. Bounded Context Database Design Diagram


### 2.6.4. Bounded Context: Vínculo de cuidado

#### 2.6.4.1. Domain Layer

#### 2.6.4.2. Interface Layer

#### 2.6.4.3. Application Layer

#### 2.6.4.4. Infrastructure Layer

#### 2.6.4.5. Bounded Context Software Architecture Component Level Diagrams

#### 2.6.4.6. Bounded Context Software Architecture Code Level Diagrams

##### 2.6.4.6.1. Bounded Context Domain Layer Class Diagrams

##### 2.6.4.6.2. Bounded Context Database Design Diagram


### 2.6.5. Bounded Context: Gestión del tratamiento

#### 2.6.5.1. Domain Layer

#### 2.6.5.2. Interface Layer

#### 2.6.5.3. Application Layer

#### 2.6.5.4. Infrastructure Layer

#### 2.6.5.5. Bounded Context Software Architecture Component Level Diagrams

#### 2.6.5.6. Bounded Context Software Architecture Code Level Diagrams

##### 2.6.5.6.1. Bounded Context Domain Layer Class Diagrams

##### 2.6.5.6.2. Bounded Context Database Design Diagram


### 2.6.6. Bounded Context: Inventario y reposición

#### 2.6.6.1. Domain Layer

#### 2.6.6.2. Interface Layer

#### 2.6.6.3. Application Layer

#### 2.6.6.4. Infrastructure Layer

#### 2.6.6.5. Bounded Context Software Architecture Component Level Diagrams

#### 2.6.6.6. Bounded Context Software Architecture Code Level Diagrams

##### 2.6.6.6.1. Bounded Context Domain Layer Class Diagrams

##### 2.6.6.6.2. Bounded Context Database Design Diagram


### 2.6.7. Bounded Context: Seguimiento familiar

#### 2.6.7.1. Domain Layer

#### 2.6.7.2. Interface Layer

#### 2.6.7.3. Application Layer

#### 2.6.7.4. Infrastructure Layer

#### 2.6.7.5. Bounded Context Software Architecture Component Level Diagrams

#### 2.6.7.6. Bounded Context Software Architecture Code Level Diagrams

##### 2.6.7.6.1. Bounded Context Domain Layer Class Diagrams

##### 2.6.7.6.2. Bounded Context Database Design Diagram


### 2.6.8. Bounded Context: Accesibilidad y preferencias

#### 2.6.8.1. Domain Layer

#### 2.6.8.2. Interface Layer

#### 2.6.8.3. Application Layer

#### 2.6.8.4. Infrastructure Layer

#### 2.6.8.5. Bounded Context Software Architecture Component Level Diagrams

#### 2.6.8.6. Bounded Context Software Architecture Code Level Diagrams

##### 2.6.8.6.1. Bounded Context Domain Layer Class Diagrams

##### 2.6.8.6.2. Bounded Context Database Design Diagram


### 2.6.9. Bounded Context: Omisión y escalamiento

#### 2.6.9.1. Domain Layer

#### 2.6.9.2. Interface Layer

#### 2.6.9.3. Application Layer

#### 2.6.9.4. Infrastructure Layer

#### 2.6.9.5. Bounded Context Software Architecture Component Level Diagrams

#### 2.6.9.6. Bounded Context Software Architecture Code Level Diagrams

##### 2.6.9.6.1. Bounded Context Domain Layer Class Diagrams

##### 2.6.9.6.2. Bounded Context Database Design Diagram
