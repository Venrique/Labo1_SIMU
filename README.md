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

### Creando la funcion productMatrixVector

```cpp
//La funcion asume que las dimensiones de la matriz y los vectores son las adecuadas para que la multiplicacion sea posible.
//La funcion recibe: Una matriz, Un vector, Un vector y un vector para la respuesta.
void productMatrixVector(Matrix A, Vector v, Vector &R){
    //Se itera una cantidad de veces igual al numero de filas de la matriz
    for(int f=0;f<A.size();f++){
        //Se inicia un acumulador
        float cell = 0.0;
        //Se calcula el valor de la celda de acuerdo a la formulacion
        for(int c=0;c<v.size();c++){
            cell += A.at(f).at(c)*v.at(c);
        }
        //Se coloca el valor calculado en su celda correspondiente en la respuesta
        R.at(f) += cell;
    }
}

```

### Creando la funcion productRealMatrix

```cpp
//La funcion multiplica cada uno de los elementos de la matriz por el escalar, ubicando los resultados en la matriz de respuesta.
//La funcion recibe: Un escalar(Valor Real), una matriz y una matriz para la respuesta.
void productRealMatrix(float real,Matrix M,Matrix &R){
    //Se prepara la matriz de respuesta con las mismas dimensiones de la
    //matriz
    zeroes(R,M.size());
    //Se recorre la matriz original
    for(int i=0;i<M.size();i++)
        for(int j=0;j<M.at(0).size();j++)
            //La celda actual se multiplica por el real, y se almacena
            //el resultado en la matriz de respuesta
            R.at(i).at(j) = real*M.at(i).at(j);
}

```

### Creando la funcion productRealMatrix

```cpp
//La funcion elimina en la matriz la fila i, y la columna j
//La funcion recibe: Una matriz, un indice de fila i y un indice de fila j.
void getMinor(Matrix &M,int i, int j){
    //Se elimina la fila i
    M.erase(M.begin()+i); //Uso de begin para obtener un iterator a la posicion de interes
    //Se recorren las filas restantes
    for(int i=0;i<M.size();i++)
        //En cada fila se elimina la columna j
        M.at(i).erase(M.at(i).begin()+j);
}

```

<hr>
<p align="center">Para servirles, <strong>Equipo de Instructores</strong> </p>

