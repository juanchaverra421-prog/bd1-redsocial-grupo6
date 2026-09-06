# Red Social Pascualina — Base de Datos

Diseño de la base de datos que soportará una red social para la comunidad de la
Institución Universitaria Pascual Bravo.

**Asignatura:** Bases de Datos
**Docente:** Juan Camilo Palacio Alcaraz
**Institución:** Institución Universitaria Pascual Bravo — Medellín, Colombia

## Integrantes del equipo

| Integrante | Usuario de GitHub |
|---|---|
| Juan Pablo Chaverra Betancur | `@pendiente` |
| María Lucía Cantillo Castro | `@pendiente` |

## Descripción del caso

Las plataformas institucionales existentes son formales y no favorecen la
conexión casual entre estudiantes. Este proyecto diseña la base de datos de una
red social donde la comunidad educativa pueda:

- **Crear perfiles** con su área de estudio, intereses y habilidades.
- **Conectar con compañeros** de intereses afines o de cursos avanzados que
  ofrezcan mentoría.
- **Publicar actualizaciones**: preguntas sobre tareas, recursos, noticias del
  sector o memes de la vida universitaria.
- **Crear y unirse a grupos**: estudio por materia, equipos de hackatón o clubes
  de interés.
- **Programar eventos**: reuniones de estudio, talleres y actividades sociales.

## Estado del proyecto

| Tarea | Entregable | Estado |
|---|---|---|
| Tarea 1 | Modelo conceptual (MER) | Completada |

## Estructura del repositorio

```
.
├── README.md
└── tarea1/
    ├── informe/
    │   ├── Tarea1_Informe_ModeloConceptual_RedSocialPascualina.pdf
    │   └── diagramas/
    │       ├── diagrama_mer_global.png       # vista integrada, alta resolución
    │       ├── vista1_perfil.png             # perfil, jerarquía y comunidad
    │       ├── vista2_contenido.png          # contenido e interacción
    │       ├── vista3_grupos.png             # grupos, eventos y comunicación
    │       ├── eer_usuario.png               # especialización de USUARIO
    │       └── atributos_*.png               # atributos por entidad
    └── video/
        └── README.md                          # enlace a YouTube
```

## Tarea 1 — Modelo conceptual

### Resumen del modelo

- **15 tipos de entidad**: 11 fuertes, 3 subclases y 3 débiles.
- **21 tipos de relación**, todas de grado 2.
- **1 jerarquía de especialización** (disyunta y total) sobre `USUARIO`.

| Categoría | Elementos |
|---|---|
| Entidades fuertes | `USUARIO`, `PROGRAMA_ACADEMICO`, `ASIGNATURA`, `INTERES`, `HABILIDAD`, `PUBLICACION`, `GRUPO`, `EVENTO`, `MENSAJE` |
| Subclases de `USUARIO` | `ESTUDIANTE`, `DOCENTE`, `EGRESADO` |
| Entidades débiles | `COMENTARIO` y `ADJUNTO` (de `PUBLICACION`), `NOTIFICACION` (de `USUARIO`) |
| Relaciones recursivas | `SIGUE` (seguidor/seguido), `MENTORIA` (mentor/aprendiz), `RESPONDE_A` |
| Relaciones identificadoras | `CONTIENE`, `ADJUNTA`, `GENERA` |

### Notación

Se emplea la **notación de Chen** descrita por Elmasri y Navathe en el Capítulo 3
de *Fundamentos de Sistemas de Bases de Datos* (5.ª ed.), complementada con los
constructores de especialización del modelo EER del Capítulo 4.

| Símbolo | Significado |
|---|---|
| Rectángulo | Tipo de entidad |
| Rectángulo de doble línea | Tipo de entidad débil |
| Rombo | Tipo de relación |
| Rombo de doble línea | Relación identificadora |
| Elipse | Atributo |
| Elipse con texto subrayado | Atributo clave |
| Elipse de doble línea | Atributo multivaluado |
| Elipse punteada | Atributo derivado |
| Línea simple | Participación parcial |
| Línea doble | Participación total |
| Círculo con `d` | Especialización disyunta |

Las cardinalidades se expresan en las dos notaciones del texto guía: la razón
(`1:1`, `1:N`, `M:N`) y el par `(mín, máx)` de la Sección 3.7.4.

### Contenido del informe

1. Introducción
2. Descripción del caso y alcance — incluye 12 reglas de negocio numeradas
3. Metodología aplicada
4. Análisis de necesidades — 14 requisitos de datos
5. Mapa de conceptos y criterios de clasificación
6. Identificación de entidades y justificación
7. Identificación de atributos y justificación
8. Relaciones, cardinalidades y restricciones de participación
9. Jerarquía: especialización de `USUARIO`
10. Diagrama Entidad-Relación
11. Verificación del modelo frente a los requisitos
12. Conclusiones individuales
13. Referencias

## Referencias

- Elmasri, R. y Navathe, S. B. (2007). *Fundamentos de Sistemas de Bases de
  Datos* (5.ª ed.). Pearson Addison Wesley.
- *Representar para construir* — recurso educativo de la Unidad.
