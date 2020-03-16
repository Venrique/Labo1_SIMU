# Laboratorio 1
Técnicas de Simulación en Computadoras: Primera práctica de laboratorio 

## Contenido
En esta práctica trabajaremos con los siguientes temas:

- Vectores
- Matrices
- Matriz como Pseudocódigo
- Operaciones de Vectores y Matrices

## Math_tools.h

Se define un arreglo de números reales como un Vector

```cpp
typedef vector<float> Vector;
```

Se define un vector de Vectores como una matriz

```cpp
typedef vector<Vector> Matrix;
```

### Creando la función zeroes

```cpp
//La funcion crea una matriz cuadrada nxn llena de ceros
void zeroes(Matrix &M,int n){
    //Se crean n filas
    for(int i=0;i<n;i++){
        //Se crea una fila de n ceros
        vector<float> row(n,0.0);
        //Se ingresa la fila en la matriz
        M.push_back(row);
    }
}
```

<hr>
<p align="center">Para servirles, <strong>Equipo de Instructores</strong> </p>

