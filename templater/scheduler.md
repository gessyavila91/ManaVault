<%*
// Determina si es Semana A o B
const tableTitle = (moment().week() % 2 === 1) ? "# Semana A" : "# Semana B";
// Busca la tabla en el archivo
const tableStart = tp.file.content.indexOf(tableTitle);
if (tableStart === -1) {
    tR += `No se encontró la tabla para ${tableTitle}\n`;
} else {
    const tableEnd = tp.file.content.indexOf('# fin', tableStart);
    const tableRows = tp.file.content.slice(tableStart, tableEnd).trim().split('\n').slice(4); // Ignora encabezados
    const daysOfWeek = ['Lunes', 'Martes', 'Miércoles', 'Jueves', 'Viernes', 'Sábado', 'Domingo'];

    // Genera la lista de tareas por día
    daysOfWeek.forEach((day, dayIndex) => {
        tR += `### ${day}\n\n`;
        tableRows.forEach(row => {
            let columns = row.split('|').map(col => col.trim()).filter(col => col);
            const time = columns[0];
            const activity = columns[dayIndex + 1]; // La actividad correspondiente al día
            if (activity) tR += `- [ ] ${time} ${activity}\n`;
        });
        tR += "\n"; // Espacio entre días
    });
}
%>
