# :dna: **Proyecto de Detección y Mutación de ADN** :dna:

Este proyecto simula la **detección de mutaciones** en una matriz de ADN y la creación de **mutantes** a través de mutaciones específicas. El programa permite mutar el ADN con **radiación** (horizontal/vertical) o **virus** (diagonal) y también incluye una funcionalidad para **sanar el ADN**, generando una nueva matriz sin mutaciones.

---

## :clipboard: **Integrantes**
- Lucas Pujada
- Lautaro Montecchiani
- Bruno Rivera
- Delfina Mampel
  
---

## :rocket: **Requisitos**

- **Python 3.x**.
- No se requieren librerías externas adicionales para ejecutar este proyecto.

---

## :clipboard: **Instalación**

1. **Clona** este repositorio o **descarga los archivos** del proyecto.
   ### **Clonar el Repositorio**:

Si tienes **Git** instalado en tu máquina, puedes clonar el repositorio utilizando el siguiente comando:

```bash
git clone https://github.com/tu-usuario/tu-repositorio.git
```
Este comando descargará una copia completa del repositorio en tu máquina local. Asegúrate de reemplazar tu-usuario y tu-repositorio con tu nombre de usuario de GitHub y el nombre de tu repositorio.

- Abre tu terminal (en Windows, puedes usar Git Bash o CMD).

- Navega al directorio donde deseas clonar el repositorio.

- Ejecuta el comando de clonación.

- Una vez clonado, navega al directorio del proyecto con:

```bash
cd tu-repositorio
```

 ### **Descargar el Repositorio Manualmente**:
Si no tienes Git instalado, también puedes descargar el repositorio como un archivo comprimido (ZIP) y extraerlo en tu máquina.

- Ve a la página de tu repositorio en GitHub.

- Haz clic en el botón verde que dice "Code".

- En el menú desplegable, haz clic en "Download ZIP".
- Extrae el archivo comprimido en el directorio de tu elección.
- Asegúrate de tener Python 3.x instalado en tu máquina y luego ejecuta el archivo ejecutable.py.

2. Asegúrate de tener **Python 3.x** instalado en tu máquina.
3. Ejecuta el archivo `ejecutable.py` para iniciar el programa.

---

## :wrench: **Uso**

1. Al ejecutar el programa, se te pedirá ingresar una **matriz de ADN de 6x6** utilizando las bases nitrogenadas válidas: **A, T, C, G**.
2. Una vez que la matriz esté ingresada, el programa te mostrará las siguientes opciones. A continuación se explica qué hace cada opción:

---

## :book: **Explicación del Menú**

### **1. Detectar mutaciones**

- Esta opción permite al programa **buscar mutaciones** dentro de la matriz de ADN. Se realizarán las siguientes comprobaciones:
  - **Horizontal**: Verifica si existen secuencias consecutivas de 4 bases nitrogenadas iguales en las filas.
  - **Vertical**: Realiza lo mismo pero en las columnas de la matriz.
  - **Diagonal**: Busca secuencias de bases iguales a lo largo de las diagonales.
  
  Si se encuentran mutaciones en la matriz, se devolverá un mensaje indicando cuántas mutaciones fueron detectadas y en qué posiciones (fila, columna y tipo de mutación). Si no se encuentran mutaciones, el programa indicará que no hubo mutaciones.

### **2. Crear mutantes**

- En esta opción, el programa permite aplicar mutaciones a la matriz de ADN:
  - **Tipo de mutación**: Se elige entre:
    - **Radiación (H/V)**:
      - **Horizontal (H)**: La mutación se aplica horizontalmente, es decir, en una fila, comenzando desde una columna específica.
      - **Vertical (V)**: La mutación se aplica verticalmente, es decir, en una columna, comenzando desde una fila específica.
    - **Virus (D)**:
      - **Diagonal (D)**: La mutación se aplica a lo largo de una diagonal, comenzando desde una posición específica de la matriz.
  - **Base nitrogenada**: Se debe elegir la base nitrogenada que se repetirá en la mutación. Solo se permiten las bases: **A**, **T**, **C**, **G**.
  - **Posición inicial**: Se solicita la posición (fila y columna) desde donde comenzará la mutación.

  Una vez completados estos datos, el programa aplicará la mutación y mostrará la **matriz mutada**.

### **3. Sanar ADN**

- Esta opción genera una nueva **matriz de ADN sin mutaciones**. El programa:
  - Verifica si la matriz de ADN contiene alguna mutación.
  - Si detecta mutaciones, genera una nueva matriz de ADN aleatoria que no tenga mutaciones, usando bases nitrogenadas aleatorias **A, T, C, G**.
  - Si no se encuentran mutaciones, el programa mostrará la matriz original, ya que no es necesario sanarla.

### **4. Ingresar una nueva matriz**

- Permite al usuario **ingresar una nueva matriz de ADN**. El formato requerido es:
  - 6 filas con 6 bases nitrogenadas cada una, separadas por una coma y un espacio.
  - Las bases nitrogenadas deben ser A, T, C o G.

  El programa validará que la matriz tenga el formato correcto y solo acepte las bases válidas.

### **5. Salir**

- Termina la ejecución del programa. El programa mostrará un mensaje de despedida y finalizará su ejecución.

---

## :book: **Funcionalidad**

### :mag_right: **Clases y Métodos**

#### **Clase `Detector`** :mag:
- **Función**: Detecta mutaciones en la matriz de ADN.
- **Métodos**:
  - `detectar_mutantes()`: Detecta mutaciones horizontales, verticales y diagonales.
  - Métodos internos: 
    - `detectar_horizontal()`
    - `detectar_vertical()`
    - `detectar_diagonal()`

#### **Clase `Mutador`** :wrench:
- **Función**: Clase base para la creación de mutaciones de ADN.
- **Métodos**:
  - `crear_mutante()`: Método abstracto para ser implementado por las clases hijas.

#### **Clase `Radiacion`** :sunny:
- **Función**: Realiza mutaciones de tipo radiación (horizontal o vertical).
- **Métodos**:
  - `crear_mutante()`: Aplica mutaciones horizontales o verticales en la matriz.

#### **Clase `Virus`** :microbe:
- **Función**: Realiza mutaciones de tipo virus (diagonal).
- **Métodos**:
  - `crear_mutante()`: Aplica mutaciones diagonales en la matriz.

#### **Clase `Sanador`** :heart:
- **Función**: Sana mutaciones en la matriz de ADN generando una nueva matriz sin mutaciones.
- **Métodos**:
  - `sanar_mutantes()`: Genera una nueva matriz de ADN sin mutaciones.

---

## :keyboard: **Estructura del Proyecto**

- **`clases.py`**: Contiene las clases que implementan la funcionalidad de detección y mutación de ADN.
- **`ejecutable.py`**: El archivo principal que ejecuta el programa y permite la interacción con el usuario.

---

## :camera: **Ejemplo de Ejecución**

### 1. **Ingreso de la matriz de ADN**:

```bash
Ingrese una matriz de ADN (6 filas de 6 bases nitrogenadas, separadas por una coma y un espacio):
Ejemplo: AGATCA, GATTCA, CAACAT, GAGCTA, ATTGCG, CTGTTC
Matriz: AGATCA, GATTCA, CAACAT, GAGCTA, ATTGCG, CTGTTC
```

### 2. **Opciones disponibles**:
Opciones:
```bash
1. Detectar mutaciones
2. Crear mutantes
3. Sanar ADN
4. Ingresar una nueva matriz
5. Salir
Seleccione una opción: 1
```

### 3. **Detección de mutaciones**:
```bash
Resultado booleano: True
Mutaciones detectadas en las siguientes posiciones:
- Fila: 0, Columna: 2, Tipo: Horizontal
```
### 4. **Creación de mutantes**:
```bash
Base nitrogenada (A/T/C/G): A
Fila inicial (0-5): 2
Columna inicial (0-5): 3
Tipo de mutación (H para Horizontal, V para Vertical, D para Diagonal): H
MATRIZ MUTADA:
AGATCA
GATTCA
CAACAA
GAGCTA
ATTGCG
CTGTTC
```

### 5. Sanar ADN:
```bash
MATRIZ SANADA:
AGATCA
GATTCA
CAACAT
GAGCTA
ATTGCG
CTGTTC
```

---

## :warning: Consideraciones



- El programa asegura que las mutaciones se realicen dentro de los límites de la matriz, y si se intenta realizar una mutación fuera de esos límites, se muestra un mensaje de error y se solicita un nuevo intento.
- La matriz debe ser de exactamente **6x6** y contener únicamente las bases nitrogenadas válidas: **A, T, C, G**.

---
