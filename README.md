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

### Creando la función zeroes (nxn)

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

### Creando la función zeroes (nx1)

```cpp
//La funcion crea una matriz cuadrada nx1 llena de ceros
//La funcion recibe: Un vector columna y la dimension del vector
void zeroes(Vector &v,int n){
    //Se itera n veces
    for(int i=0;i<n;i++){
        //En cada iteracion se agrega un cero al vector
        v.push_back(0.0);
    }
}

```
### Creando la función copyMatrix

```cpp
//La funcion copiara el contenido de la primera matriz en la segunda, respetando las posiiones.
//La funcion recibe: Una matriz y una matriz que sera la copia de la primera.

void copyMatrix(Matrix A, Matrix &copy){
    //Se inicializa la copia con ceroes
    //asegurandose de sus dimensiones
    zeroes(copy,A.size());
    //Se recorre la matriz original
    for(int i=0;i<A.size();i++)
        for(int j=0;j<A.at(0).size();j++)
            //Se coloca la celda actual de la matriz original
            //en la misma posicion dentro de la copia
            copy.at(i).at(j) = A.at(i).at(j);
}

```


<hr>
<p align="center">Para servirles, <strong>Equipo de Instructores</strong> </p>

