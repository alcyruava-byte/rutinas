---
name: plan-semanal
description: Genera el plan semanal de entrenamiento de un cliente de AlcyFiT como Excel y PDF, según objetivos (uno o varios), días disponibles (2 a 6) y nivel (1 a 5). Úsala siempre que el usuario pida una rutina, un plan semanal, un plan de ejercicios o un programa para un cliente o paciente, aunque no diga "skill" ni "Excel". También cuando mencione bajar de peso, ganar masa muscular, mejorar glucosa, triglicéridos, colesterol, presión o estrés con ejercicio, o rutinas para condiciones especiales (embarazo, adultos mayores, menores, lesiones, discapacidad). Invocación: /plan-semanal
---

# Plan semanal de clientes (AlcyFiT)

Convierte los datos de un cliente en un plan semanal ordenado, descargable en Excel y PDF, listo para compartir.

## 1. Datos a recopilar

**Cada rutina nueva empieza con preguntas, aunque el cliente ya exista.** Haz las preguntas en UN solo mensaje breve. Nunca asumas datos faltantes: si falta algo, pregunta.

1. **Nombre del cliente** (o iniciales).
2. **Objetivos** (uno o varios):
   - Bajar de peso
   - Reducir niveles (glucosa, triglicéridos, colesterol, presión, tiroides, estrés, etc.). Pedir cuál(es).
   - Sentirse bien y activo
   - Renovar energía y fuerza
   - Aumentar el nivel de actividad física
   - Aumentar de peso y crear masa muscular
   - Esparcimiento (recreación)
3. **Días disponibles por semana**: mínimo 2, máximo 6. Siempre queda al menos 1 día de descanso. Si piden 7, explica que se dejará 1 de descanso (6 de entrenamiento).
4. **Nivel**:
   - **1**: pacientes con enfermedades o condiciones especiales (menores de edad, algunos adultos mayores, embarazadas, personas con lesiones o discapacidad)
   - **2**: principiante
   - **3**: intermedio
   - **4**: avanzado
   - **5**: atleta de alto rendimiento o en preparación para pruebas especiales (instituciones, competencias)
5. **Equipo disponible** (casa, gimnasio, bandas, mancuernas). No asumas equipo: si no lo dicen, pregunta.
6. **Si es nivel 1 o hay condición médica**: diagnóstico, lesiones, medicación relevante, restricciones y si tiene autorización de su médico.

## 2. Reglas de armado

### Distribución según días

| Días | Estructura sugerida |
|---|---|
| 2 | Cuerpo completo A / Cuerpo completo B |
| 3 | Cuerpo completo A / B / C (o empuje, tracción, pierna) |
| 4 | Tren superior / Tren inferior, dos veces |
| 5 | Empuje / Tracción / Pierna / Superior / Inferior + movilidad |
| 6 | Empuje / Tracción / Pierna, dos veces |

Los días de descanso se reparten sin dejar dos días intensos del mismo grupo muscular seguidos. El descanso puede incluir caminata suave o movilidad (marcarlo como "Descanso activo opcional").

### Series y repeticiones por nivel

| Nivel | Series | Repeticiones | Descanso entre series | Intensidad |
|---|---|---|---|---|
| 1 | 1 a 2 | 10 a 15 | 60 a 90 s | Muy baja a baja, ejercicios simples y de bajo impacto |
| 2 | 2 a 3 | 10 a 15 | 60 a 90 s | Baja a moderada |
| 3 | 3 a 4 | 8 a 12 | 60 a 90 s | Moderada |
| 4 | 4 a 5 | 6 a 12 | 60 a 120 s | Moderada a alta |
| 5 | 4 a 6 | 3 a 12 según fase | 90 a 180 s | Alta, con periodización por fase y prueba objetivo |

### Ajuste por objetivo (se pueden combinar)

- **Bajar de peso**: circuitos y cuerpo completo, 1 a 2 sesiones de cardio de intensidad moderada, fuerza para conservar masa muscular.
- **Reducir niveles (glucosa, lípidos, presión, tiroides, estrés)**: aeróbico moderado constante más fuerza ligera a moderada. Presión alta: evitar maniobras de Valsalva y esfuerzos máximos. Estrés: incluir movilidad, respiración y descanso activo. Detalles específicos se toman de la búsqueda (sección 4).
- **Sentirse bien y activo / Aumentar actividad física**: variedad, progresión gradual, sesiones cortas y sostenibles.
- **Renovar energía y fuerza**: fuerza básica con cargas progresivas, descansos completos, sin llegar al fallo.
- **Aumentar de peso y masa muscular**: hipertrofia (volumen alto, 8 a 12 reps), ejercicios compuestos primero, cardio mínimo.
- **Esparcimiento**: actividades lúdicas, deportes recreativos, caminatas, baile, ejercicios en grupo, baja presión de rendimiento.

Con varios objetivos, prioriza el primero que indique el cliente y menciona cómo se integraron los demás.

### Nivel 1 (seguridad primero)

- Si hay enfermedad, embarazo, lesión, discapacidad o es menor de edad, **sugerir valoración y autorización médica** antes de iniciar. Anotarlo en el plan.
- Menores: juego y técnica, sin cargas máximas. Embarazadas: evitar ejercicios boca arriba prolongados, riesgo de caída y impacto alto, según trimestre. Adultos mayores: equilibrio, fuerza funcional, silla de apoyo. Lesiones y discapacidad: adaptar a la zona y capacidad disponible.
- Detener el ejercicio ante dolor, mareo, falta de aire inusual o dolor en el pecho, e incluir esta advertencia en el plan.
- No diagnosticar ni modificar tratamientos. El plan complementa la indicación médica.
- **Nivel 1 o condición médica: siempre requiere revisión y aprobación manual del usuario antes de entregar o enviar**, y la advertencia de consultar al médico debe quedar escrita en la hoja "Resumen".

## 3. Contenido del plan (Excel)

Generar **solo el Excel** con openpyxl (no usar otras herramientas para el armado). Estructura:

**Hoja "Resumen"**: nombre del cliente, fecha, objetivos, nivel, días por semana, equipo, observaciones, advertencias de seguridad, advertencia de consultar al médico (cuando aplique), marca AlcyFiT.

**Una hoja por día de entrenamiento** (o una sola hoja con bloques por día, lo que quede más legible), con estas columnas:

| Día | Grupo muscular | Ejercicio | Series | Repeticiones | Descanso | Notas / técnica |
|---|---|---|---|---|---|---|

- Ejercicios agrupados por grupo muscular, ordenados de compuestos a aislados.
- Incluir calentamiento (5 a 10 min) y enfriamiento / estiramiento al inicio y al final de cada día.
- Los días de descanso aparecen en el plan, marcados como "Descanso".
- Formato: encabezados con color de marca, bordes finos, columnas con ancho ajustado, texto con ajuste de línea, fila de encabezado fija, listo para imprimir (orientación horizontal, ajustar a una página de ancho).

**Rutas de salida**: `./salidas/excel/plan_<cliente>_<AAAA-MM-DD>.xlsx`. Nunca guardar en otra ruta.

## 4. Búsqueda con Brave (conector)

Cuando el cliente tenga **condición especial, nivel 1 o un objetivo clínico (glucosa, presión, lípidos, tiroides, embarazo, lesión, discapacidad)**, buscar formatos y pautas antes de armar el plan.

- Usar el conector de **Brave Search** (herramienta de búsqueda web de Brave) si está conectado. Si no está disponible, usar la búsqueda web disponible y avisarlo.
- Consultas sugeridas, cortas y específicas: `ejercicio diabetes tipo 2 guía rutina`, `exercise hypertension guidelines ACSM`, `ejercicio embarazo recomendaciones ACOG`, `rutina adultos mayores equilibrio fuerza`, `exercise hypothyroidism program`.
- Priorizar fuentes confiables: ACSM, OMS, ACOG, guías de sociedades médicas, universidades, ministerios de salud. Evitar blogs comerciales y foros.
- Usar los resultados solo para **adaptar estructura, intensidad y precauciones**. No copiar textos ni tablas completas de una fuente. Resumir con palabras propias.
- Incluir en la hoja "Resumen" una línea **"Fuentes consultadas"** con título y enlace.

## 5. Flujo de entrega (Claude Code)

Este flujo es obligatorio en cada rutina nueva, aunque sea el mismo cliente:

1. **Preguntas**: completar los datos de la sección 1 en un solo mensaje y esperar respuesta.
2. **Excel**: generar solo el Excel con openpyxl en `./salidas/excel/` (sección 3).
3. **Aprobación 1**: mostrar al usuario un resumen del Excel (objetivos, nivel, días, ejercicios por día, advertencias) y preguntar: **"¿Apruebas para convertir a PDF?"**. Nivel 1 o condición médica: pedir además revisión manual explícita.
4. **PDF**: solo con aprobación explícita, convertir con:
   ```
   soffice --headless --convert-to pdf --outdir ./salidas/pdf <archivo.xlsx>
   ```
   El PDF queda en `./salidas/pdf/` con el mismo nombre base.
5. **Verificación**: revisar que el PDF no corte columnas ni deje páginas vacías. Si hay problemas, corregir el Excel y volver al punto 3.
6. **Cierre**: informar las rutas de ambos archivos y, si aplica, la advertencia de nivel 1 o condición médica.

Nunca enviar correos desde esta skill. El envío pertenece a un flujo aparte con autorización explícita.

## 6. Nivel 2 (pendiente)

Se completará después: conectores de Gmail (solo lectura) y ajustes de búsqueda.

## 7. Nivel 3 (pendiente)

Se completará después: envío de correo con autorización explícita y subagente orquestador.

## Principios

- Plan simple, claro y realista. Mejor menos ejercicios bien ejecutados.
- Nunca prometer resultados médicos ni sustituir al médico.
- Adaptar siempre al nivel real del cliente, no al deseado.
- Nunca asumir datos faltantes.
