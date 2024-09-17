<%*
// Definir la ruta del archivo .md
const filePath = "Blueprint/BP - Day Planner.md";

// Leer el archivo .md como texto plano
let fileContent = await app.vault.adapter.read(filePath);

// Remover las líneas iniciales y finales que contienen "---"
fileContent = fileContent.replace(/---/g, '').trim();

// Dividimos el contenido del archivo en líneas
const lines = fileContent.split('\n');

// Variables para almacenar el resultado final
let output = "";
let currentWeek = "";
let currentDay = "";

// Variables temporales para almacenar actividades
let currentActivity = "";
let currentStartTime = "";
let currentEndTime = "";

// Recorremos cada línea para extraer la información
lines.forEach(line => {
    line = line.trim();
    
    // Detectar semana
    if (line.startsWith('nombre: "Semana')) {
        currentWeek = line.replace('nombre:', '').trim().replace(/"/g, '');
        output += `## ${currentWeek}\n\n`;
    }

    // Detectar día
    if (line.startsWith('- nombre: "')) {
        currentDay = line.replace('nombre:', '').trim().replace(/"/g, '');
        output += `### ${currentDay}\n\n`;
    }

    // Detectar actividad
    if (line.startsWith('- actividad:')) {
        currentActivity = line.replace('actividad:', '').trim().replace(/"/g, '');
    }

    // Detectar hora de inicio
    if (line.startsWith('horaInicio:')) {
        currentStartTime = line.replace('horaInicio:', '').trim().replace(/"/g, '');
    }

    // Detectar hora de fin
    if (line.startsWith('horaFin:')) {
        currentEndTime = line.replace('horaFin:', '').trim().replace(/"/g, '');
        output += `- [ ] ${currentActivity} (${currentStartTime} - ${currentEndTime})\n`;
    }
});

// Mostrar el resultado para verificar que las tareas se están generando correctamente
console.log(output);

tR += output;
%>
