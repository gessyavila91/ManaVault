
```dataview
table semana.nombre as "Semana", dia.nombre as "Día", actividad.actividad as "Actividad", actividad.horaInicio as "Hora Inicio", actividad.horaFin as "Hora Fin"
from "Blueprint/horarios.md"
flatten schema as semanas
flatten semanas.semana as semana
flatten semana.dias as dia
flatten dia.actividades as actividad

```


<% tp.user.task("/Blueprint/horarios.dm") %>


[object Promise]

