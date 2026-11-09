# Fuentes — modelo de lenguaje para leyes rusas

Consultado el 2026-11-09. Primarias: artículos y actas académicas. Secundarias: prensa especializada, guías y reseñas; se marcan como tales cuando el dato viene de ellas.

## Primarias

1. **RusLawOD — The Russian Legislative Corpus** (arXiv:2406.04855, 2024).
   https://arxiv.org/html/2406.04855v1
   El corpus de legislación federal 1991–2023: 281.413 textos, 176.523.268 tokens; versión actualizada 1991–2025: 304.382 textos, 194.425.905 tokens. Extraído de pravo.gov.ru. ConsultantPlus y Garant como sistemas privados de pago, sin corpus descargable. CorRIDA (1.546 documentos, 1,784 millones de tokens) y CorCodex (279 documentos, 3,227 millones de tokens). MultiLegalPile (24 idiomas, 87.000 millones de palabras) y Pile of Law (10 millones de documentos, 30.000 millones de palabras). La legislación se reescribió casi por completo tras 1991.

2. **Domain adaptation of Russian ModernBERT for long legal documents** (arXiv:2610.06715, octubre 2026).
   https://arxiv.org/html/2610.06715
   RuModernBERT-ruLaw: preentrenamiento continuado sobre 304.382 documentos legislativos, 194.425.905 tokens. Evaluación en 1.031 segmentos de decisiones judiciales: la entropía cruzada de token enmascarado baja 0,10942 / 0,07052 / 0,06604 a 512 / 2.048 / 8.192 tokens. Entrada máxima 8.192 tokens. F1 de entidad 0,99852 frente a 0,99820, con el 99,95% de los segmentos de prueba compartiendo forma y clase con el entrenamiento. Los autores advierten que no aísla el contexto lejano ni establece utilidad legal práctica.

3. **TenetBench: A Clause-Anchored Russian Corpus for Evaluating Language Models against Professional Codes of Ethics** (arXiv:2610.29477, octubre 2026).
   https://arxiv.org/html/2610.29477
   3.433 peticiones en conflicto con cláusulas de quince códigos de ética profesional en ruso, con gemelas benignas. Catorce combinaciones evaluadas; once de catorce producen contenido en conflicto en la mayoría de las peticiones. GigaChat 3.1 10B-A1.8B (0,183), YandexGPT 5.1 (0,240), T-pro-it 2.1 (0,258), Claude Sonnet 5 (0,849). Validación humana: 0,995 plausibles; AC1 de Gwet de al menos 0,894.

4. **RuLegalNER: a new dataset for Russian legal named entities recognition** (Scientific and Technical Journal of Information Technologies, Mechanics and Optics, 2023, vol. 23, n.º 4, págs. 854–857).
   https://ntv.ifmo.ru/en/article/22225/RuLegalNER:_novyy_dataset_dlya_raspoznavaniya_imenovannyh_yuridicheskih_suschnostey_na_russkom_yazyke.htm
   Primer dataset de NER legal en ruso. Anotación por reglas con expertos legales de Tag-Consulting. Base RuBERT, con CRF y adaptadores.

5. **Transfer Learning for Russian Legal Text Simplification** (taller READI, ACL, 2024, págs. 59–69).
   https://preview.aclanthology.org/navbar-space/2024.readi-1.6.pdf
   Primer corpus paralelo para simplificar leyes rusas, a partir de "Rossiyskaya Gazeta Legal Papers". Enfoques T5 y GPT; métricas ROUGE, SARI y BERTScore; evaluación humana por hablantes nativos y abogados rusos. GPT rinde mejor afinado con textos copiados.

6. **Russian-Language Multimodal Dataset for Automatic Summarization of Scientific Papers** (arXiv:2405.07886, 2024).
   https://arxiv.org/html/2405.07886v1
   GigaChat procesó sin censura solo el 37% de los textos; especialmente reacio con textos legales y médicos. Solo 9 resúmenes de 60 posibles en periodismo. YandexGPT procesó más textos.

## Secundarias

7. **Russia Launches Its New AI Law** (ALLNET Law).
   https://www.allnetlaw.com/news/russia-launches-its-new-ai-law
   Ley en vigor el 1 de septiembre de 2026. Umbral de 1.000 millones de parámetros. Estatus soberano y nacional; desarrollador persona jurídica rusa; centros de datos de propiedad rusa en Rusia; conformidad con la legislación y los valores tradicionales.

8. **Russia's AI Law Puts Control Ahead of Capability** (TechPolicy Press).
   https://www.techpolicy.press/russias-ai-law-puts-control-ahead-of-capability/
   Ley firmada el 26 de julio de 2026. Desarrollo liderado por Sber, T-Bank, Yandex y MTS. Bases extranjeras, sobre todo chinas: GigaChat modelado en DeepSeek con atención estilo Qwen; YandexGPT 5 Pro con pesos de Qwen-2.5-32B; T-Pro, T-Lite y Cotype sobre generaciones de Qwen. MERA y LLM Arena como clasificaciones en ruso. El borrador integral de marzo de 2026 se abandonó en junio.

9. **Prompt of changes: Russian AI models will receive state support** (Iz.ru).
   https://iz.ru/en/node/2145495
   Apoyo estatal a desarrolladores rusos. Entrada en vigor por etapas: parte principal el 1 de septiembre de 2026; etiquetado, modelos soberanos y propiedad intelectual el 1 de marzo de 2027. Cotype Pro 3 de MWS AI como modelo nacional.

10. **Punished for a Prompt: How the State Plans to Control AI in Russia** (T-invariant, abril 2026).
    https://t-invariant.org/2026/04/punished-for-a-prompt-how-the-state-plans-to-control-ai-in-russia/
    Análisis del borrador de la ley: responsabilidad del usuario por uso "ilegítimo" (art. 10.4 del borrador); modelos extranjeros ya inaccesibles desde IPs rusas; lista de valores tradicionales del art. 4.6.

11. **Civil Code of Russia** (Wikipedia en inglés).
    https://en.wikipedia.org/wiki/Russian_Civil_Code
    Código Civil: 1.551 artículos en cuatro partes (I: 30-nov-1994; II: 26-ene-1996; III: 26-nov-2001; IV: 18-dic-2006, en vigor 1-ene-2008). Derecho de familia en código aparte. Sistema de derecho civil, heredero del derecho romano por tradición bizantina.

12. **Foreign Law: Russia** (guía de la Universidad de San Diego).
    https://lawlibguides.sandiego.edu/c.php?g=841170&p=6010291
    pravo.gov.ru como portal oficial de información legal; las leyes publicadas ahí se consideran oficiales. Garant como sistema de seguimiento de la legislación rusa.

13. **Garant system: a database of the federal and regional laws** (Nice Panorama, página descriptiva).
    https://www.nice-panorama.com/en/Economy/Garant-SK/Garant-database-of-the-federal-and-regional-laws-applicable-in-the-Russian-Federation.php
    Garant: banco de datos con más de 5,03 millones de documentos (leyes federales y regionales, comentarios, jurisprudencia, tratados). Dato de la descripción pública del sistema, no del vendedor directo.

14. **YandexGPT in 2026: A Review of Russia's AI Platform for Business** (MySummit School).
    https://mysummit.school/blog/en/yandexgpt-review-2026/
    Reseña con 42 modelos y 80 escenarios de gestión. Alice AI LLM v3 lidera el benchmark SLAVA. YandexGPT 5.1 Pro supera a la versión anterior en el 58% de los casos y a GPT-4.1 en el 56%, según Yandex, sin confirmación independiente. Alice AI v3 "no funciona" para derecho laboral (errores críticos); YandexGPT inventa estatutos al citar derecho laboral estadounidense.
