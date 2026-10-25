# Propuesta de investigación | Aprendizaje cooperativo adaptativo bajo restricciones de cómputo

**Versión:** 0.1 — 24 de octubre de 2026  
**Estado:** protocolo preliminar abierto a revisión por pares; sin experimentos ejecutados, sin validación de originalidad y sin aval institucional declarado.  
**Disciplina:** inteligencia artificial, aprendizaje multiagente, aprendizaje continuo, optimización bajo restricciones, teoría de juegos e inteligencia colectiva.

## Título tentativo

**Apoyo mutuo adaptativo entre agentes de IA: eficiencia computacional, transferencia de capacidades y preservación del aprendizaje bajo escasez de recursos.**

**Keywords (EN):** cooperative multi-agent learning; compute-efficient AI; adaptive peer teaching; continual learning; constrained meta-learning; collective intelligence; resource allocation; mutual aid; federated learning; AI for Latin America.

**Palabras clave (ES):** aprendizaje cooperativo; sistemas multiagente; apoyo mutuo; aprendizaje continuo; eficiencia computacional; distribución de recursos; metaaprendizaje; investigación abierta; inteligencia artificial latinoamericana.

## Resumen

Se propone investigar si una comunidad de agentes de aprendizaje heterogéneos, sometida a un límite estricto de recursos computacionales, puede mejorar el desempeño colectivo a través de una política que aprenda a distribuir dinámicamente enseñanza entre pares, recuperación de capacidades, entrenamiento individual, colaboración y conservación de recursos. La variable principal será el resultado verificable sobre tareas reservadas en relación con el costo total, incluyendo entrenamiento, inferencia, coordinación y comunicación. Se estudiará, además, la retención de capacidades previamente adquiridas por cada agente ante cambios sucesivos de tareas. La propuesta se contrastará con aprendizaje individual, técnicas de entrenamiento poblacional, enseñanza fija y políticas simplificadas. El marco filosófico se inspira en el apoyo mutuo de Kropotkin y la gestión de recursos compartidos de Ostrom, sin asumir que esos enfoques validan la hipótesis informática. El protocolo busca colaboración y revisión crítica, especialmente en instituciones con restricciones de infraestructura.

## Problema y justificación

Muchas mejoras en aprendizaje automático requieren aumentos de cómputo o datos. Existen técnicas para reducir costos —optimización de hiperparámetros, ajuste eficiente de parámetros y modelos especializados— y trabajos que aprenden a distribuir la enseñanza entre agentes. Sin embargo, vale la pena estudiar de manera integrada **cuándo la asistencia adaptativa mejora el aprendizaje futuro sin ocultar sus costos y sus efectos sobre agentes menos capaces**.

El desafío es especialmente relevante en laboratorios con hardware limitado, nodos heterogéneos, presupuesto restringido y conectividad imperfecta. Esa motivación regional no presupone que el método supere necesariamente a la infraestructura concentrada.

## Pregunta central

¿Puede una política adaptativa de apoyo entre agentes lograr mayor calidad colectiva por unidad de cómputo que las políticas no cooperativas, de selección por desempeño y de cooperación fija, al mismo tiempo que conserva capacidades previamente adquiridas?

### Preguntas específicas

1. ¿Cuáles son los beneficios y costos de enseñar a un agente con menor desempeño actual?
2. ¿Cuándo conviene enseñar, entrenar localmente, recuperar conocimiento o simplemente no actuar?
3. ¿Puede el mecanismo reducir el olvido catastrófico ante sucesivos cambios de tareas?
4. ¿Qué sucede cuando el costo de comunicación es alto?
5. ¿Cómo influyen la complementariedad de especialidades y la heterogeneidad de hardware?

## Hipótesis contrastables

- **H1:** la ayuda adaptativa mejora el número de problemas reservados resueltos correctamente por unidad de costo total frente al mejor control comparable.
- **H2:** la política cooperativa con restricción de retención reduce la máxima pérdida individual de habilidades anteriores respecto de una asignación basada únicamente en rendimiento.
- **H3:** la ventaja potencial aumenta cuando el aprendizaje transmitido es reutilizable y las especialidades son complementarias.
- **H4:** cuando el costo de interacción supera cierto umbral, la cooperación deja de ser más eficiente.

Todas pueden ser refutadas; no constituyen resultados.

## Método propuesto

**Primera etapa (bajo costo):** simulación reproducible en CPU con cuatro agentes heterogéneos y secuencias de tareas de dificultad controlada. Se medirán costos reales del controlador y de la comunicación, no solo el costo de los modelos base. Las condiciones experimentales usarán idénticas semillas, presupuestos y conjuntos de tareas.

**Comparadores:** aprendizaje independiente; Population Based Training; enseñanza entre pares mediante política fija; controlador adaptativo sin preservación; mecanismo completo de apoyo mutuo adaptativo. Incorporar referencias adicionales si la revisión identifica controles superiores.

**Variable primaria:** resultados correctos en evaluación reservada / costo computacional total normalizado, junto con calidad absoluta a presupuesto fijo.

**Variables secundarias:** retención de habilidades anteriores por agente; rendimiento mínimo individual; memoria máxima; energía si hay medición fiable; tiempo de ejecución; proporción de decisiones de enseñanza efectivamente reutilizadas.

**Análisis:** pilotos separados de confirmación; al menos diez semillas en la etapa confirmatoria si el diseño y el costo lo permiten; intervalos de confianza, tamaños de efecto, curvas calidad/costo, fallos y resultados negativos. Los umbrales y el tamaño final de muestra deberán preregistrarse tras el piloto metodológico.

**Segunda etapa condicional:** modelos abiertos pequeños y aprendizaje mediante memoria/LoRA, únicamente si la simulación muestra ventajas repetibles.

**Tercera etapa condicional:** nodos heterogéneos distribuidos, simulando primero conectividad y costos antes de usar infraestructura real.

## Criterios para descartar o reformular

Se rechaza una supuesta ventaja si desaparece al igualar costos, si surge por filtración de casos de evaluación, si el controlador cuesta más de lo que ahorra o si los agentes pierden capacidades sin que eso se informe. Un resultado negativo también deberá documentarse.

El objetivo de ahorro de 20% a igual calidad es **un umbral propuesto**, no una estimación científica ni una promesa de desempeño.

## Originalidad y antecedentes

La originalidad **no** consiste en inventar cooperación entre agentes, metaaprendizaje ni enseñanza entre pares. Debe contrastarse con **PBT** (Jaderberg et al., 2017), **LeCTR** (Omidshafiei et al., 2019), **MH-MARL** (Qiu et al., 2023), **TPGO** (He et al., 2026), **Meta-Team** (Hao et al., 2026), **MEAL** (Tomilin et al., ICML 2026) y trabajos de equidad bajo presupuesto.

La contribución candidata es una política unificada de inversión en apoyo, reparación y entrenamiento que pueda evaluarse bajo presupuesto integral y retención individual, con condiciones claras de cuándo cooperación sí y no conviene. La novedad seguirá **sin validar** hasta una revisión bibliográfica sistemática.

Ver [bibliografía anotada y enlaces](RELATED_WORK.md).

## Consideraciones éticas y sociales

La selección natural es un mecanismo descriptivo, no una moral social. El valor de las personas no depende de su utilidad económica o cognitiva. Las «pérdidas de capacidades» aquí medidas corresponden a agentes computacionales y no son equivalentes a sufrimiento humano. No atribuimos afiliación a universidades o comunidades que todavía no aceptaron participar. La investigación aspira a ampliar autonomía tecnológica sin prometer por sí sola justicia distributiva.

## Aportes que solicitamos a la comunidad universitaria

Se invita a especialistas en IA, matemática aplicada, ingeniería de sistemas, teoría de juegos, sistemas complejos, psicología del aprendizaje, filosofía de la tecnología y ciencia abierta a:

1. Señalar antecedentes que acoten o descarten nuestra pretendida novedad.
2. Auditar las hipótesis, la metodología y la contabilización de recursos.
3. Recomendar tareas controladas y comparadores reproducibles.
4. Participar en la definición del preregistro y revisión de resultados.
5. Estudiar gobernanza, potencial de beneficio regional y riesgos.

**No se solicita adhesión a una conclusión prefijada.** Las contribuciones críticas y los resultados negativos serán bienvenidos.

## Enlaces de trabajo

- [Repositorio público y resumen en inglés](../README.md)
- [Resumen en español](../README.es.md)
- [Protocolo formal (inglés)](RESEARCH_PROTOCOL.md)
- [Antecedentes con bibliografía](RELATED_WORK.md)
- [Plantilla de preregistro](PREREGISTRATION.md)
- [Convocatoria bilingüe](COLLABORATE.md)

**Contacto académico inicial:** abrir un Issue de investigación en el repositorio público. No se publican correos personales sin autorización.
