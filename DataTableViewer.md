
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



## Semana B

### -  Miércoles

- [ ] -  ⌨️ Mecanografia (08:30 - 09:15)
- [ ] -  🎥 Video Programacion (09:15 - 09:30)
- [ ] -  💻 Programacion (09:30 - 13:30)
- [ ] -  📘 Ingles (13:30 - 16:00)
- [ ] -  🎨 Pintar miniaturas (16:00 - 20:00)

