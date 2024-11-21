# :dna: Proyecto de Detección y Mutación de ADN :dna:

Este proyecto permite la simulación de la **detección de mutaciones** en una matriz de ADN y la creación de **mutantes** a través de mutaciones específicas. El programa ofrece la opción de **mutar el ADN** de diferentes maneras, como mediante **radiación** (horizontal/vertical) o **virus** (diagonal). También incluye la funcionalidad de **sanar el ADN**, generando una nueva matriz sin mutaciones.

---

## :rocket: Requisitos

- **Python 3.x**.
- No se requieren librerías externas adicionales para ejecutar este proyecto.

---

## :clipboard: Instalación

1. **Clona** este repositorio o **descarga los archivos** del proyecto.
2. Asegúrate de tener **Python 3.x** instalado en tu máquina.
3. Ejecuta el archivo `ejecutable.py` para iniciar el programa.

---

## :wrench: Uso

1. Al ejecutar el programa, el usuario deberá ingresar una **matriz de ADN de 6x6** utilizando las bases nitrogenadas válidas: A, T, C, G.
2. Una vez que la matriz esté ingresada, se presentarán las siguientes opciones:
   - **Detectar mutaciones**: El programa buscará mutaciones horizontales, verticales y diagonales en el ADN.
   - **Crear mutantes**: El usuario podrá crear mutantes aplicando mutaciones por radiación (horizontal/vertical) o virus (diagonal).
   - **Sanar ADN**: El programa generará un nuevo ADN aleatorio sin mutaciones.
   - **Ingresar una nueva matriz**: Permite al usuario ingresar una nueva matriz de ADN.
   - **Salir**: Termina la ejecución del programa.

---

## :book: Funcionalidad

### :mag_right: Clases y Métodos

#### **Clase `Detector`** :mag:
- **Función**: Detecta mutaciones en la matriz de ADN.
- **Métodos**:
  - `detectar_mutantes()`: Detecta mutaciones horizontales, verticales y diagonales.
  - Métodos internos para detectar mutaciones en direcciones específicas: `detectar_horizontal()`, `detectar_vertical()`, `detectar_diagonal()`.

#### **Clase `Mutador`** :wrench:
- **Función**: Clase base para las mutaciones de ADN.
- **Métodos**:
  - `crear_mutante()`: Método abstracto que debe ser implementado por las clases hijas para crear una mutación.

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

## :keyboard: Estructura del Proyecto

- **`clases.py`**: Contiene las clases que implementan la funcionalidad de detección y mutación de ADN.
- **`ejecutable.py`**: El archivo principal que ejecuta el programa y permite la interacción con el usuario.

---

## :camera: Ejemplo de Ejecución

1. **Ingreso de la matriz de ADN**:
   Ingrese una matriz de ADN (6 filas de 6 bases nitrogenadas, separadas por una coma y un espacio):
   
Ejemplo: AGATCA, GATTCA, CAACAT, GAGCTA, ATTGCG, CTGTTC
Matriz: AGATCA, GATTCA, CAACAT, GAGCTA, ATTGCG, CTGTTC

3. **Opciones disponibles**:
Opciones:
1. Detectar mutaciones
2. Crear mutantes
3. Sanar ADN
4. Ingresar una nueva matriz
5. Salir Seleccione una opción

3. **Detección de mutaciones**:
Resultado booleano: True
Mutaciones detectadas en las siguientes posiciones:
Fila: 0, Columna: 2, Tipo: Horizontal

4. **Creación de mutantes**:
Base nitrogenada (A/T/C/G): A
Fila inicial (0-5): 2
Columna inicial (0-5): 3
Tipo de mutación (H para Horizontal, V para Vertical, D para Diagonal): H
MATRIZ MUTADA: AGATCA GATTCA CAACAA GAGCTA ATTGCG CTGTTC

5. **Sanar ADN**:
MATRIZ SANADA: AGATCA GATTCA CAACAT GAGCTA ATTGCG CTGTTC


---

## :warning: Consideraciones

- El programa asegura que las mutaciones se realicen dentro de los límites de la matriz, y si se intenta realizar una mutación fuera de esos límites, se muestra un mensaje de error y se solicita un nuevo intento.
- La matriz debe ser de exactamente **6x6** y contener únicamente las bases nitrogenadas válidas: **A, T, C, G**.

---
