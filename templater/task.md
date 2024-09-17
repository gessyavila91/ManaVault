<%*
// Ruta del archivo YAML que contiene las actividades
const filePath = "Blueprint/horarios.dm";
const pathTFile = app.vault.getAbstractFileByPath(filePath); 

var file = app.workspace.getLeaf(false).openFile(pathTFile);

let output = "goals";

tR += file;
%>

