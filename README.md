# Sistema de Evacuación de Edificios (RutasEvacuacion)

## Integrantes

- **Oscar Antonio Solarte**
- **Andrés Uriel Sandoval**
- **Samuel Eduardo Muñoz**

## Descripción del taller

Proyecto desarrollado en **Java** que simula la evacuación de personas dentro de un edificio, aplicando estructuras de datos y algoritmos de búsqueda de rutas implementados desde cero.

El edificio (habitaciones, pasillos, escaleras y salidas de emergencia) se representa mediante un **grafo ponderado**. El sistema permite bloquear conexiones para simular obstáculos, calcular rutas alternativas hacia las salidas disponibles, simular la evacuación por turnos y **exportar el plan de evacuación a un archivo `.txt`**.

### Estructuras de datos implementadas

| Estructura | Uso en el proyecto |
|---|---|
| Lista enlazada | Administra los ocupantes del edificio |
| Cola | Organiza a las personas durante la evacuación |
| Pila | Almacena las instrucciones de las rutas |
| Tabla hash | Registra y busca personas por su identificador |
| Árbol binario | Organiza las zonas según su nivel de riesgo |
| Grafo | Representa la estructura física del edificio |

### Algoritmos implementados

- **BFS (Breadth-First Search):** recorre los nodos del edificio.
- **Dijkstra:** calcula las rutas de menor costo hacia las salidas disponibles.

### Funcionalidades

- Registro de habitaciones, pasillos, escaleras y salidas.
- Conexión entre ubicaciones mediante pesos.
- Bloqueo de conexiones y búsqueda de rutas alternativas.
- Registro y consulta de ocupantes.
- Organización de zonas por nivel de riesgo.
- Simulación de evacuación por turnos.
- Consulta del estado final de los ocupantes.
- Exportación del plan de evacuación a `plan_evacuacion.txt`.

## Estructura del proyecto

```
RutasEvacuacion/
├── src/
│   ├── app/
│   │   └── Main.java                  # Punto de entrada del programa
│   ├── algoritmos/
│   │   ├── BFS.java
│   │   └── Dijkstra.java
│   ├── estructuras/
│   │   ├── ArbolBinario.java
│   │   ├── NodoArbol.java
│   │   ├── Cola.java
│   │   ├── Pila.java
│   │   ├── ListaEnlazada.java
│   │   ├── NodoLista.java
│   │   ├── TablaHash.java
│   │   ├── Grafo.java
│   │   └── Arista.java
│   ├── modelo/
│   │   ├── Edificio.java
│   │   ├── NodoGrafo.java
│   │   ├── Arista.java
│   │   ├── Persona.java
│   │   └── Zona.java
│   ├── servicios/
│   │   ├── EvacuacionService.java
│   │   ├── GestionOcupantes.java
│   │   ├── GestionRiesgos.java
│   │   └── ExportadorPlan.java
│   └── simulacion/
│       └── Simulador.java
├── nbproject/                         # Configuración de NetBeans
├── build.xml
├── manifest.mf
└── README.md
```

## Requisitos

- **JDK 17 o superior** (el proyecto de NetBeans está configurado con JDK 25).
- Opcional: NetBeans o VS Code con la extensión *Extension Pack for Java*.

## Instrucciones para ejecutar el programa

### 1. Clonar el repositorio

```bash
git clone https://github.com/samueleduardo1061-cpu/RutasEvacuacion.git
cd RutasEvacuacion
```

### 2. Ejecutar

**Opción A: desde la terminal**

Linux / macOS:

```bash
mkdir -p out
javac -encoding UTF-8 -d out $(find src -name "*.java")
java -cp out app.Main
```

Windows (PowerShell):

```powershell
mkdir out
javac -encoding UTF-8 -d out (Get-ChildItem -Path src -Recurse -Filter *.java).FullName
java -cp out app.Main
```

**Opción B: desde NetBeans**

1. Abrir el proyecto con `File > Open Project`.
2. Clic derecho sobre el proyecto y seleccionar `Run` (la clase principal es `app.Main`).

**Opción C: desde VS Code**

1. Abrir la carpeta del proyecto.
2. Abrir `src/app/Main.java` y pulsar `Run` sobre el método `main`.

### 3.Lo qué se observa al ejecutar

El programa corre de forma automática (no pide datos por teclado) y muestra en consola:

1. El edificio registrado con sus conexiones (incluida una conexión bloqueada).
2. El recorrido BFS desde la habitación H101.
3. Las zonas de riesgo ordenadas por nivel.
4. Los ocupantes registrados en la tabla hash.
5. La exportación del plan de evacuación.
6. La simulación de la evacuación por turnos y el estado final de los ocupantes.

El plan de evacuación se guarda en el archivo **`plan_evacuacion.txt`**, dentro de la carpeta desde la que se ejecuta el programa.

## Tecnologías

- Java
- NetBeans / VS Code
- Git y GitHub

