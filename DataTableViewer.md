
```dataview
table 
without id
semana.nombre as "Semana", dia.nombre as "Día", actividad.actividad as "Actividad", actividad.horaInicio as "Hora Inicio", actividad.horaFin as "Hora Fin"
from "config/schemas/WeekPlanerYAML.md"
flatten schema as semanas
flatten semanas.semana as semana
flatten semana.dias as dia
flatten dia.actividades as actividad

```
