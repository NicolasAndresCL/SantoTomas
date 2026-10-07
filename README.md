# Diseño de Software · IEI-050

[![CI](https://github.com/nicolascanoleal/DisenoSoftware/actions/workflows/ci.yml/badge.svg)](https://github.com/nicolascanoleal/DisenoSoftware/actions/workflows/ci.yml)

Repositorio de documentación, planificación y código de proyectos para la asignatura **Diseño de Software** (código IEI-050) impartida en la Universidad Santo Tomás (Chile).

**Docente**: Giovanni Cáceres R. (gcaceres6@santotomas.cl)  
**Alumno responsable**: Nicolás Andrés Cano Leal — Rol: Líder / Gestor de Proyecto  
**Tamaño del equipo**: 5 integrantes

---

## Estructura de la asignatura

| Unidad | Contenido | Evaluación |
|--------|-----------|-----------|
| **I** | Proceso de desarrollo de software | Prueba escrita: 30% |
| **II** | Diseño de objetos y clases | Portafolio: 35% |
| **III** | Diseño del comportamiento | Portafolio: 35% |

**Esquema de evaluación semestral**:
- Proceso de cátedra: **70%**
  - Unidad I: prueba escrita (30%)
  - Unidad II: portafolio (35%)
  - Unidad III: portafolio (35%)
- Examen final: **30%**

**Laboratorio**: 5 estudios de caso (EC1 a EC5), **20% cada uno** (100% total)

---

## Herramientas del curso

| Herramienta | Uso |
|-------------|-----|
| **StarUML** | Diagramas UML |
| **Microsoft Visio** | Diagramación y documentación |
| **BlueJ** | Implementación de clases y pruebas |

---

## Trabajos en curso

### 1. Caso de cátedra: Reservas médicas
**Archivo**: `caso-reservas-medicas-modelo-ciclo-vida.md`  
**Fecha**: 13 de agosto de 2026

Informe de fundamentación para debate académico sobre la selección del modelo de ciclo de vida más adecuado para un sistema de gestión de reservas médicas en contexto de cambios frecuentes de requisitos (observación de prototipos iniciales). 

**Propuesta**: Modelo iterativo-incremental implementado mediante Scrum con técnica de prototipado de interfaz.

**Contenido**: 13 secciones más anexo comparativo (cascada vs. iterativo-incremental vs. ágil).

### 2. Caso de laboratorio: SIGET (EC1)
**Archivo**: `Plan de Proyecto - Sistema de Gestion de Tareas (IEI-050).docx`

Plan de proyecto para el **Estudio de Caso 1**, correspondiente a un sistema de gestión de tareas para empresa. Incluye 9 secciones: introducción, objetivos y alcance, plan de proyecto, lista de tareas (EDT de 39 tareas en 6 fases), recursos requeridos, cronograma con carta Gantt, roles y responsabilidades (matriz RACI), gestión de riesgos (9 riesgos identificados) y justificación.

**Metodología**: Iterativo-incremental con Scrum  
**Duración**: 10 semanas (5 sprints de 2 semanas c/u)  
**Período**: 17 de agosto al 23 de octubre de 2026

---

### 3. Sistema de Arriendo de Vehículos
**Carpeta**: `SistemaArriendoVehiculos/`
**Fecha**: 20 de agosto de 2026

Aplicación funcional que cubre el ciclo completo del negocio de arriendo: registro de usuarios,
catálogo de vehículos, reservas, pagos y devoluciones. Dos procesos separados: una API REST en
Django + Django REST Framework sobre SQLite, y una interfaz web construida con NiceGUI que la
consume por HTTP.

Las reglas de negocio —disponibilidad del vehículo, traslape de reservas, licencia de conducir
vigente, transiciones de estado de la reserva— viven en una capa de servicios que lanza
excepciones de dominio, y un único manejador las traduce a códigos HTTP con un contrato de error
uniforme. Incluye 128 pruebas con 96 % de cobertura y pipeline de integración continua.

Ingreso por defecto: `admin@estacionamiento.cl` / `1234`. El detalle completo —arquitectura,
máquina de estados de la reserva, endpoints y puesta en marcha— está en
[`SistemaArriendoVehiculos/README.md`](SistemaArriendoVehiculos/README.md).

Desde el 20 de agosto de 2026 el sistema se desarrolla en su **propio repositorio**,
[NicolasAndresCL/SistemaArriendoVehiculos](https://github.com/NicolasAndresCL/SistemaArriendoVehiculos),
donde viven su integración continua, la contenerización (Docker y Compose), los manifiestos
de Kubernetes, la infraestructura en Terraform y el pipeline de Jenkins. La copia de esta
carpeta corresponde al estado del 20 de agosto.

---

### 4. Actividad 1.6: Simulación de Estudio de Caso 1
**Archivo**: `Actividad 1.6 - Simulacion Estudio de Caso 1 (IEI-050).docx`
**Fecha**: 27 de agosto de 2026

Planificación iterativa de un sistema ficticio de carga de notas para una institución
educativa, resuelta con el **Proceso Unificado**. Cubre el caso (problema, alcance, actores y
nueve casos de uso identificados), la justificación del marco de proceso, las tres iteraciones
con su riesgo, artefactos UML y criterio de aceptación, la asignación de roles por iteración y
el tratamiento del feedback como cambio de alcance.

**Equipo**: cuatro integrantes, distinto del equipo del EC1 (SIGET).
**Fuente**: `generar-actividad-1-6.py` regenera el `.docx` completo; el documento no se edita
a mano.

---

### 5. Modelo de clases UML: academia de estudiantes
**Archivo**: `Modelo UML - Academia de Estudiantes (IEI-050).pdf`
**Fecha**: 24 de septiembre de 2026

Ejercicio de clase (Unidad II) sobre los cuatro tipos de relación entre clases. A partir de un
enunciado de cinco oraciones —academia, estudiantes, talleres e inscripciones, sede e
instrumentos, plan de práctica y pasos, Persona como supertipo— identifica una **asociación**
(Academia–Estudiante e Inscripcion como clase que resuelve el muchos a muchos con Taller), una
**agregación** (Sede–Instrumento: el instrumento se traslada y sobrevive a la sede), una
**composición** (PlanPractica–Paso: el paso no existe fuera del plan) y una **herencia**
(Estudiante e Instructor desde Persona abstracta). Tres páginas: tabla de identificación con
multiplicidad y justificación, diagrama de clases vectorial y decisiones de diseño con su
traducción a Java.

**Fuente**: `generar-modelo-academia.py` dibuja el diagrama con reportlab y regenera el PDF; el
enunciado original es la fotografía `img1.jpeg` de la lámina proyectada en clase (no
versionada: su texto está transcrito íntegro en la sección 1 del PDF).

**Defensa**: `defensa-modelo-uml-academia.md` (y su PDF) prepara la defensa oral de este modelo
y de la corrección hecha al diagrama de otro grupo.

---

### 6. Prueba de relaciones entre clases UML
**Archivo**: `Prueba de Diseno de Software - Relaciones UML (IEI-050).docx`
**Fecha**: 7 de octubre de 2026

Evaluación de 75 minutos y 60 puntos, dirigida a estudiantes de segundo semestre de Ingeniería en Informática. Comprueba la diferencia entre clases y objetos, lectura de multiplicidades, asociación, agregación, composición, herencia y elaboración de un diagrama aplicado al contexto de cursos universitarios. Incluye pauta docente y criterios de corrección. El contenido sintetiza la secuencia de publicaciones de LONKODEV del 7 de octubre y se alinea con el modelo de clases UML de la academia preparado en la Unidad II.

## Productos exigidos en el laboratorio (lámina 43)

El profesor exige estos 6 productos entregables para cada estudio de caso:

Estado según la auditoría del 17 de agosto de 2026 (ver `auditoria-plan-vs-pauta.md`). Todos
están redactados en el `.docx`; dos quedaron marcados como parciales por defectos verificados,
no por ausencia de contenido.

| Producto | Sección | Estado | Observación |
|----------|---------|--------|-------------|
| Plan de proyecto | 3 | Cubierto | — |
| Lista de tareas (EDT) | 4 | Cubierto | Ninguna tarea nombra un diagrama UML como producto |
| Recursos requeridos | 5 | **Parcial** | No incluye StarUML ni Visio, herramientas oficiales del curso |
| Cronograma o Gantt | 6 | **Parcial** | Ruta crítica inconsistente con la tabla de dependencias; hitos H2 y H3 inalcanzables |
| Roles y responsabilidades | 7 | Cubierto | Los entregables del Diseñador no incluyen diagramas UML |
| Breve justificación | 9 | Cubierto | Extensa frente al mandato "breve" de la lámina 43 |

---

## Estructura del repositorio

### Documentación de cátedra
- **`caso-reservas-medicas-modelo-ciclo-vida.md`**  
  Análisis y justificación de la selección de modelo de ciclo de vida para el caso de cátedra. Redacción académica formal con argumentos técnicos y anexo comparativo.

### Documentación de laboratorio
- **`Plan de Proyecto - Sistema de Gestion de Tareas (IEI-050).docx`**  
  Plan completo del EC1 (SIGET). Contiene los 6 productos exigidos en formato Word con carta Gantt y matriz RACI integradas.

- **`Actividad 1.6 - Simulacion Estudio de Caso 1 (IEI-050).docx`**  
  Entregable de la Actividad 1.6: planificación de tres iteraciones de un sistema de carga de
  notas con el Proceso Unificado. Seis páginas, doce tablas. **No se edita a mano**: se
  regenera con `generar-actividad-1-6.py`.

- **`Laboratorio_Estudio_de_Caso_1 (1).docx`**  
  Versión previa de ese entregable, conservada como plantilla de estilos del generador (de ahí
  salen la paleta, los márgenes y los estilos de párrafo). Si se borra, el script deja de
  funcionar.

### Trabajo de auditoría y preparación

- **`auditoria-plan-vs-pauta.md`**  
  Auditoría del plan SIGET contra las 45 láminas del docente. Incluye tabla de trazabilidad de
  los 6 productos, desalineaciones ordenadas por gravedad con el texto de corrección redactado
  para pegar en el `.docx`, recálculo de la ruta crítica por CPM y verificación del calendario
  y del presupuesto.

- **`guion-exposicion-ec1.md`** y **`Guion de exposicion EC1.pdf`**  
  Guion de la presentación del EC1: reparto por integrante con tiempos, texto a decir tramo por
  tramo, reglas de derivación ante repreguntas, banco de 20 preguntas con respuesta y versión
  comprimida para 5 minutos. El PDF (14 páginas, A4) es la versión para imprimir o repartir al
  equipo; el `.md` es la fuente que se edita.

- **`guiones-por-integrante/`**  
  El guion partido en un cuadernillo por persona, en Markdown y en PDF. Cada uno lleva su orden
  de intervención en el encabezado de todas las páginas y es autosuficiente: solo el tramo que
  esa persona expone, sus cifras, su regla de derivación ante repreguntas, las siete preguntas
  que cualquiera del equipo debe saber responder, qué no decir y su checklist.

  | Archivo | Orden | Quién | Contenido |
  |---|---|---|---|
  | `1 - Nicolas Cano - Lider.pdf` | 1 y 6 | Nicolás Cano | Apertura y cierre, más las 13 preguntas difíciles y la corrección previa de la ruta crítica (7 págs.) |
  | `2 - Tais Montesinos - Analista.pdf` | 2 | Tais Montesinos | Problema, alcance y las 39 tareas (3 págs.) |
  | `3 - Disenador.pdf` | 3 | *por definir* | Recursos, presupuesto y herramientas (3 págs.) |
  | `4 - Joaquin Argandona - Desarrollador.pdf` | 4 | Joaquín Argandoña | Cronograma, sprints y Gantt (3 págs.) |
  | `5 - Martin Rojas - Tester.pdf` | 5 | Martin Rojas | Roles, RACI y criterios de éxito (3 págs.) |

  El cuadernillo de Nicolás es el único que incluye el banco completo de preguntas difíciles;
  los de los compañeros llevan solo las siete comunes, deliberadamente.

- **`defensa-modelo-uml-academia.md`** y **`Defensa - Modelo UML Academia (IEI-050).pdf`**
  Defensa oral del modelo UML de la academia (Nicolás Cano y Tais) y de la corrección entregada
  al diagrama de Marcela Ponce y Romina Rozas: tabla frase-decisión-prueba, las cuatro
  observaciones con su porqué, nueve preguntas difíciles con respuesta (incluidos los puntos
  débiles del propio modelo) y un guion de un minuto. El PDF (4 páginas, A4) se regenera con
  `md-a-pdf.py`; el `.md` es la fuente.

- **`md-a-pdf.py`**  
  Convierte cualquier Markdown de este repositorio a PDF A4 con encabezado, pie y numeración.
  Requiere el entorno `env\` (PyMuPDF y mistune). Uso:

  ```bash
  python md-a-pdf.py <origen.md> <destino.pdf> "<título del encabezado>"
  ```

  Es necesario regenerar el PDF del guion cada vez que se edite el `.md` —por ejemplo, al
  reemplazar los marcadores `[Integrante 2]` … `[Integrante 5]` por los nombres reales.

- **`generar-actividad-1-6.py`**  
  Genera el `.docx` de la Actividad 1.6 a partir del contenido escrito en el propio script,
  usando `Laboratorio_Estudio_de_Caso_1 (1).docx` como plantilla de estilos. El documento
  tiene una sola fuente: se edita el script y se regenera, nunca al revés. Requiere el entorno
  `env\` (python-docx). Uso:

  ```bash
  ./env/Scripts/python.exe generar-actividad-1-6.py
  ```

- **`generar-modelo-academia.py`**  
  Genera `Modelo UML - Academia de Estudiantes (IEI-050).pdf`: el diagrama de clases se dibuja
  en vectores (cajas, rombos, triángulo de herencia y multiplicidades con coordenadas
  explícitas), no como imagen exportada. Requiere el entorno `env\` con reportlab
  (`pip install reportlab`). Uso:

  ```bash
  ./env/Scripts/python.exe generar-modelo-academia.py
  ```

### Código

- **`SistemaArriendoVehiculos/`**
  Sistema de arriendo de vehículos: backend Django + DRF (`backend/`) e interfaz NiceGUI
  (`frontend/`) sobre SQLite. Trae su propio `README.md`, entorno virtual `.venv/` y suite de
  pruebas. La base de datos `db.sqlite3` y el entorno no se versionan: se regeneran con
  `migrate` y `seed_demo`.

- **`.github/`**
  Integración continua y plantillas del repositorio. El workflow `ci.yml` corre en cascada
  lint → tests con umbral de cobertura → arranque real del sistema completo → verificación de
  hardening de producción (`check --deploy`). Incluye Dependabot y plantillas de issue y de
  pull request.

### Material de referencia (no editable)
- **`Clase_1_Diseno_Software.pdf`**  
  Presentación del profesor correspondiente a la Clase 1 (45 láminas). Abarca introducción a la asignatura, estructura de unidades, sistemas de evaluación y definiciones clave del proceso de desarrollo de software.

- **`env/`** (Carpeta)  
  Entorno virtual de Python con dependencias de utilidad (PyMuPDF). Ignorada en versionado. Utilizado para extracción de texto del material PDF.

- **`WhatsApp Unknown 2026-08-13 at 2.32.13 PM/` y `WhatsApp Unknown 2026-08-13 at 2.32.13 PM.zip`**  
  Material redundante: fotografías de las láminas 41, 42 y 43 de la presentación. Ya incluidas en el PDF principal. Ignoradas en versionado.

### Otros archivos
- **`.gitignore`**  
  Configuración de exclusiones: entornos virtuales, documentación no versionada, temporales de Office, material redundante.

- **`CLAUDE.md`**  
  Guía interna para asistentes de IA que trabajen en este repositorio. Incluye contexto académico, convenciones de escritura, precisión terminológica y herramientas de extracción de texto. No versionado.

- **`pendientes.md`**  
  Trabajo abierto, ordenado por prioridad, con la acción concreta de cada punto. No versionado.

- **`memory.md`**  
  Bitácora personal de hitos técnicos para portafolio y entrevistas. No versionado.

- **`README.md`** (este archivo)  
  Documentación pública del proyecto.

---

## Notas operacionales

- La ruta de trabajo del semestre sigue la secuencia: Requerimientos → Proceso → Objetos → Clases → UML → Código → Pruebas.
- Todo material entregable se redacta en español con tildes y en tono académico formal.
- El docente (marca "LONKODEV") valora la justificación y precisión conceptual por sobre la extensión.
- La implementación de los entregables de cátedra se realiza en BlueJ (Java, orientación a objetos) y la diagramación en StarUML o Visio.
- `SistemaArriendoVehiculos/` es la excepción deliberada a lo anterior: usa Python (Django, DRF y NiceGUI) por decisión explícita, no por desalineación con el curso.
