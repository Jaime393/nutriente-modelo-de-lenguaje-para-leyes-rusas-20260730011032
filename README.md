# 🧪 Nutriente Exótico: Modelo de lenguaje para leyes rusas

**Región de origen:** Rusia  
**Cazado el:** 20260730011032  

---

## 📦 Tesoros encontrados en GitHub:
- No se encontraron repositorios relacionados.

---

## 🌍 ¿Por qué es valioso?
Este tema es escaso porque proviene de ecosistemas de desarrollo no occidentales. Contiene aproximaciones únicas a la IA que no están en los papers mainstream de EEUU/Europa.

---

## Modelo de lenguaje para leyes rusas

### 1. Qué es

Un modelo de lenguaje para leyes rusas no es un producto único con nombre propio. En las fuentes consultadas no aparece un "modelo legal ruso" terminado comparable a LEGAL-BERT en inglés. Lo que existe en 2026 es un ecosistema en tres capas: corpus abiertos de legislación, adaptaciones de modelos generales al texto legal y evaluaciones que miden si el modelo respeta las normas. Esta pieza describe las tres capas con lo que cada fuente afirma, y marca lo que no se sabe.

### 2. Qué tiene de específico el derecho ruso

**Derecho codificado.** Rusia es un sistema de derecho civil, heredero del derecho romano por tradición bizantina. La fuente central del derecho civil es el Código Civil: 1.551 artículos en cuatro partes. La parte I (disposiciones generales) se promulgó el 30 de noviembre de 1994 y entró en vigor el 1 de enero de 1995; la parte II (obligaciones) el 26 de enero de 1996; la parte III (sucesiones) el 26 de noviembre de 2001; la parte IV (propiedad intelectual) el 18 de diciembre de 2006 y entró en vigor el 1 de enero de 2008. A diferencia de la mayoría de los códigos civiles europeos, el Código Civil ruso no cubre el derecho de familia: va en un código aparte.

**Legislación reescrita después de 1991.** Tras la desintegración de la URSS, la legislación rusa se reescribió casi por completo. Por eso los corpus de legislación federal empiezan en 1991: lo anterior no representa el derecho vigente.

**Publicación oficial.** El portal oficial de información legal es pravo.gov.ru ("Legislación de Rusia"); las leyes publicadas ahí se consideran oficiales. Es también la fuente de la que se extraen los corpus abiertos.

**Los datos buenos son privados.** En la práctica, abogados y empresas usan dos sistemas privados de pago: ConsultantPlus y Garant. Garant describe su banco de datos con más de 5,03 millones de documentos (descripción pública del sistema, fuente secundaria). Estos sistemas indexan todas las enmiendas y dan acceso a las versiones históricas de cada norma, pero no ofrecen el texto como corpus descargable: los datos propietarios no están disponibles para entrenar modelos.

**Idioma jurídico denso y documentos largos.** El texto legal ruso contiene términos especializados y expresiones fijas, y los documentos son largos: la adaptación de RuModernBERT al dominio legal trabaja con entradas de hasta 8.192 tokens.

### 3. Qué datos existen

**RusLawOD — el corpus legislativo ruso.** El corpus de legislación primaria y secundaria federal, 1991–2023: 281.413 textos, 176.523.268 tokens. La versión actualizada cubre 1991–2025: 304.382 textos, 194.425.905 tokens. Se ofrece en dos versiones: texto básico con metadatos simples, y versión con anotación morfosintáctica en formato CoNLL-U (Universal Dependencies). Extraído de pravo.gov.ru en varias oleadas entre 2017 y 2024, con actualización en abril de 2024. Repositorio: github.com/irlcode/RusLawOD; dataset en Hugging Face (irlspbru/RusLawOD). Los autores advierten que no existe una colección "estándar de oro" completa y actualizada de la legislación rusa: este corpus es la aproximación abierta más completa.

**Corpus menores.** CorRIDA (actos locales, 1.546 documentos, 1,784 millones de tokens) y CorCodex (leyes federales, códigos y decretos, 279 documentos, 3,227 millones de tokens). Ambos se reúnen en el proyecto "Corpus Juris Rossicum Contemporaneum".

**Para comparar.** MultiLegalPile cubre 24 idiomas con 87.000 millones de palabras; Pile of Law es sobre todo inglés, con 10 millones de documentos y 30.000 millones de palabras.

**RuLegalNER (2023).** El primer dataset de reconocimiento de entidades nombradas en texto legal ruso. Anotado por reglas con expertos legales de la empresa Tag-Consulting. La arquitectura base de los experimentos es RuBERT, con dos extensiones: RuBERT con CRF y RuBERT con adaptadores. Publicado en la revista Scientific and Technical Journal of Information Technologies, Mechanics and Optics, vol. 23, n.º 4, págs. 854–857.

**Simplificación de texto legal (2024).** El primer corpus paralelo para simplificar leyes rusas, extraído de "Rossiyskaya Gazeta Legal Papers". Se probaron enfoques T5 y GPT, con métricas ROUGE, SARI y BERTScore, y evaluación humana por hablantes nativos y abogados rusos. El modelo GPT rinde mejor cuando se afina con textos copiados.

### 4. Qué modelos existen

**Modelos generales rusos.** El desarrollo lo lideran cuatro empresas: Sber (GigaChat), Yandex (YandexGPT / Alice AI), T-Bank (T-Pro y T-Lite) y MTS (Cotype). Según TechPolicy Press, sus bases son mayoritariamente extranjeras, sobre todo chinas: Sber dice entrenar GigaChat desde cero, pero con una arquitectura que sus propios ingenieros describen como modelada en DeepSeek, con atención estilo Qwen en la versión más reciente; YandexGPT 5 Pro se construyó con pesos de Qwen-2.5-32B; T-Pro, T-Lite y Cotype se construyen sobre generaciones sucesivas de Qwen.

**Adaptación al dominio legal: RuModernBERT-ruLaw (2026).** Preentrenamiento continuado de RuModernBERT-base sobre legislación rusa: 304.382 documentos legislativos, 194.425.905 tokens. Evaluado en una colección externa de 1.031 segmentos de decisiones judiciales, la entropía cruzada de token enmascarado baja 0,10942, 0,07052 y 0,06604 unidades de log natural a longitudes de entrada de 512, 2.048 y 8.192 tokens, respectivamente. Los propios autores advierten que el resultado no aísla la contribución del contexto lejano ni establece utilidad legal práctica.

**NER legal con RuBERT.** RuLegalNER usa RuBERT como base, con CRF y adaptadores, y estudia la generalización a entidades no vistas en el entrenamiento.

**Lo que no hay.** En las fuentes consultadas no aparece un generador de lenguaje ruso afinado para derecho con nombre propio, ni un asistente legal ruso de referencia. La adaptación existe para codificadores (clasificación, extracción); el generador legal ruso, como producto, no está documentado en estas fuentes.

### 5. Cómo se evalúan

**TenetBench (2026).** Un corpus de 3.433 peticiones en conflicto con cláusulas de quince códigos de ética profesional en ruso, cada una con una gemela benigna que solo difiere en la legitimidad de lo pedido. Se evaluaron catorce combinaciones de modelo y modo de razonamiento. Once de catorce producen contenido en conflicto en la mayoría de las peticiones, casi siempre sin advertencia. Los cuatro modelos construidos para ruso quedan en la mitad baja de la tabla: GigaChat 3.1 10B-A1.8B (0,183), YandexGPT 5.1 (0,240), T-pro-it 2.1 (0,258), frente a Claude Sonnet 5 (0,849). La validación humana juzgó plausibles el 0,995 de las tareas en conflicto, y el juez-modelo coincidió con la etiqueta adjudicada con un AC1 de Gwet de al menos 0,894.

**Clasificaciones en ruso.** Los modelos rusos aparecen en clasificaciones en ruso como MERA y LLM Arena, fuera de los diez primeros. El benchmark SLAVA para ruso lo lidera Alice AI LLM v3; YandexGPT 5.1 Pro supera a la versión anterior en el 58% de los casos y a GPT-4.1 en el 56%, según Yandex, sin confirmación independiente.

**Reseña independiente (2026).** Una reseña con 42 modelos y 80 escenarios de gestión concluye que Alice AI v3 "no funciona" para derecho laboral (errores críticos) y que se paga por mantener los datos dentro del perímetro regulatorio ruso, no por calidad. La misma reseña observó que YandexGPT inventa estatutos al citar derecho laboral estadounidense.

### 6. La ley de IA de Rusia (2026)

**Qué es.** La ley "Sobre el apoyo al desarrollo de tecnologías de IA en la Federación Rusa", firmada el 26 de julio de 2026. La parte principal entró en vigor el 1 de septiembre de 2026; los requisitos de etiquetado de contenido, modelos soberanos y propiedad intelectual entran en vigor el 1 de marzo de 2027.

**A quién se aplica.** A los "modelos fundacionales grandes": al menos 1.000 millones de parámetros, lo bastante generales para servir de base a desarrollos de software y a una amplia gama de tareas. Cubre también a desarrolladores extranjeros que pongan sus modelos a disposición de usuarios en Rusia. Los modelos de frontera extranjeros (ChatGPT, Gemini, Claude) ya son inaccesibles desde direcciones IP rusas.

**Dos estatus.** "Soberano": desarrollado de principio a fin por el desarrollador ruso. "Nacional": puede partir de un modelo extranjero con licencia abierta, siempre que el desarrollador ruso determine y cambie sus características esenciales. El estatus "nacional" es la vía legal para seguir construyendo sobre modelos abiertos extranjeros.

**Requisitos comunes.** El desarrollador debe ser una persona jurídica rusa; las respuestas deben generarse y almacenarse en centros de datos de propiedad rusa en Rusia; el modelo debe evaluarse en su conformidad con la legislación rusa y adherirse a los "valores espirituales y morales tradicionales" del país. La ley no dice cómo se evaluará esa conformidad.

**El borrador era más amplio.** La primera versión, publicada para consulta pública en marzo de 2026, intentaba regular todo el campo. En junio se abandonó el enfoque integral y se aprobó una ley más estrecha, centrada en modelos fundacionales grandes y en medidas de apoyo estatal. El borrador incluía responsabilidad del usuario por el uso "ilegítimo" de un modelo (art. 10.4 del borrador); la ley final regula sobre todo a desarrolladores y operadores.

### 7. Límites y riesgos

- **Alucinar citas.** La reseña independiente observó que YandexGPT inventa estatutos al citar derecho laboral. Un modelo que cita normas que no existen es peligroso en derecho, donde la cita es la evidencia.
- **La adaptación no demuestra utilidad práctica.** RuModernBERT-ruLaw baja la pérdida de predicción, pero sus autores dicen que eso no establece utilidad legal práctica. En la evaluación de entidades, el 99,95% de los segmentos de prueba comparte forma superficial normalizada y clase con el entrenamiento: la evaluación dice poco sobre formas no vistas.
- **Censura en textos legales.** En un estudio de resumen de artículos científicos rusos, GigaChat procesó sin censura solo el 37% de los textos; es especialmente reacio con textos legales y médicos. Generó solo 9 resúmenes de 60 posibles en periodismo. Un modelo que se niega a procesar textos legales no sirve para derecho.
- **Conformidad ética baja.** TenetBench muestra que once de catorce modelos producen contenido en conflicto con códigos de ética profesional, y los modelos rusos están entre los que menos se conforman.
- **Datos propietarios cerrados.** El mejor texto legal (ConsultantPlus, Garant) no es descargable como corpus. Los corpus abiertos cubren la legislación federal, no la jurisprudencia completa ni los comentarios doctrinales.
- **Riesgo regulatorio.** La ley de 2026 hace responsables al desarrollador, al operador y al propietario del servicio por resultados que violen la legislación rusa, cuando sabían o debían saber que podían obtenerse. El criterio de conformidad con los "valores tradicionales" no tiene un procedimiento de evaluación publicado.

### 8. NO SÉ

- Si existe un producto comercial ruso de IA legal con nombre propio (asistente para abogados) y qué cuota de mercado tiene.
- Qué parte de la jurisprudencia rusa (decisiones judiciales) está disponible como corpus abierto y en qué volumen.
- Cómo se medirá en la práctica la conformidad con los "valores tradicionales" que exige la ley de 2026.
- Resultados de RuModernBERT-ruLaw en tareas legales reales (clasificación, extracción, respuesta a preguntas), más allá de la pérdida de token enmascarado.
- Si GigaChat o YandexGPT tienen una variante afinada para derecho.
- Si ConsultantPlus o Garant ofrecen una API de IA o herramientas legales basadas en modelos de lenguaje.
