# Pasos para Configurar un Entorno de Programación en C en Otra Computadora

### Requisitos Previos
Antes de comenzar, asegúrate de tener:
- Acceso a la computadora donde realizarás la configuración.
- Una conexión a internet para descargar herramientas necesarias.


### 1. **Instalar un Compilador de C**
1. Descarga un compilador como TDM-GCC (https://jmeubank.github.io/tdm-gcc/)
2. Durante la instalación:
   - Selecciona una instalación mínima (base).
   - Asegúrate de que el compilador se agregue automáticamente a la variable de entorno "PATH".

### 2. **Instalar Visual Studio Code (VS Code)**
1. Descarga Visual Studio Code desde su [sitio oficial](https://code.visualstudio.com/).
2. Instala VS Code siguiendo las instrucciones del instalador.
3. Durante la instalación:
   - Marca la opción para agregar VS Code al menú contextual del explorador.
   - Habilita la opción de agregarlo al (PATH).



### 3. **Instalar Extensiones en VS Code**
1. Abre VS Code y ve a la pestaña de extensiones (ícono de cuadrados en la barra lateral izquierda o presiona "Ctrl+Shift+X").
2. Busca e instala las siguientes extensiones:
   - **C/C++ (Microsoft)**: Para soporte del lenguaje.
   - **Code Runner** (opcional): Para ejecutar código rápidamente.


### 4. **Configurar Archivos en VS Code**
1. Abre cualquier archivo ".c" en VS Code.
2. VS Code te pedirá que configures un entorno para depuración. Selecciona "C/C++".
3. Se generará un archivo "launch.json". Asegúrate de que tenga esta estructura básica:

   #### json
   {
       "version": "0.2.0",
       "configurations": [
           {
               "name": "C/C++ Runner: Debug Session",
               "type": "cppdbg",
               "request": "launch",
               "program": "${fileDirname}\\${fileBasenameNoExtension}.exe",
               "args": [],
               "stopAtEntry": false,
               "cwd": "${fileDirname}",
               "environment": [],
               "externalConsole": true,
               "MIMode": "gdb",
               "miDebuggerPath": "C:\\TDM-GCC-64\\bin\\gdb.exe",
               "setupCommands": [
{
"description": "Enable pretty-printing for gdb",
"text": "-enable-pretty-printing",
"ignoreFailures": true
                   }
               ]
           }
       ]
   }


4. Asegúrate de cambiar "miDebuggerPath" a la ruta donde instalaste "gdb".


### 5. **Probar el Entorno**
1. Crea un archivo ".c" en cualquier carpeta, por ejemplo:
   #### c
   #include <stdio.h>
   int main() {
       printf("Hola, mundo!\n");
       return 0;
   }
   
2. Compila desde la terminal en VS Code:
   #### bash
   gcc -o programa.exe programa.c
   
3. Ejecuta el programa:
   #### bash
   ./programa.exe

### 6. **Configurar Antivirus (si es necesario)**
Si el antivirus bloquea la ejecución:
1. Agrega las carpetas donde trabajas (por ejemplo, "C:\Users\Usuario\Tu_carpeta" o "D:\Tu_carpeta\C") como excepciones en tu antivirus.
2. Si el problema persiste, agrega el archivo del compilador "gcc.exe" y el ejecutable del programa (".exe") a la lista de permitidos.



### 7. **Probar en Diferentes Unidades**
- Asegúrate de que las carpetas de trabajo (en unidades diferentes, como C o D) tengan permisos adecuados para lectura/escritura.
- Prueba nuevamente compilar y ejecutar desde esas ubicaciones.



### ¡Listo!
Tu entorno debería estar completamente configurado para programar en C en otra computadora.
 
 
