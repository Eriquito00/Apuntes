<%*
const fileName = await tp.system.prompt("Ingresa el nombre de la imagen:");
if (fileName) {
    const newPath = "TuCarpetaDeImágenes/" + fileName + ".png"; // Cambia la extensión si es necesario
    tp.file.move(newPath);
}
%>
