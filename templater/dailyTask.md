<%*
// Definir la ruta del archivo .md
const filePath = "config/schemas/WeekPlanerYAML.md";

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

const weekName = (moment().week() % 2 === 1) ? "Semana A" : "Semana B";

moment.locale('es');
var dayName = moment().format('dddd');
dayName = dayName.charAt(0).toUpperCase() + dayName.slice(1);

console.log(dayName);


// Recorremos cada línea para extraer la información
var bandera = false;
var banderaDia = false;
lines.forEach(line => {
    line = line.trim();
    if (line.startsWith('nombre: "Semana')){
	    bandera = line.includes(weekName);
    }
    
    if(bandera){
	    // Detectar semana
	    if (line.startsWith('nombre: "Semana')) {
	        currentWeek = line.replace('nombre:', '').trim().replace(/"/g, '');
	        output += `## ${currentWeek}\n\n`;
	    }

		if(line.startsWith('- nombre: "')){
		   banderaDia = line.includes(dayName);
		   console.log(banderaDia);
		}

		if(banderaDia){
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
		}
    }
});

// Mostrar el resultado para verificar que las tareas se están generando correctamente
console.log(output);

tR += output;
%>
