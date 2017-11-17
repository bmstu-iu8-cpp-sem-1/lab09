## Лабораторная работа 9

### Инструкция
Каждое задание 1 и 2 должны быть выполнены в файле `iu_strings.cpp`.
Остальные задания должны быть выполнены в файле `matrix.cpp`.
Прототипы функции должны быть вынесены в соответствующие `.hpp` файлы.
Все реализованные функции необходимо вызвать в фунции `main` в файле [lab09](lab09.cpp)
Все `.cpp` файлы добавить в `CMakeLists.txt`

### Задание 1
Реализуйте функцию `stringCopy`
```cpp
char* stringCopy(const char*);
```
```cpp
const char * p = "some string";
char * newString = stringCopy(p);
p[0] = 'S';
std::cout << p << std::endl; // Some string
std::cout << newString << std::endl; // some string
```

### Задание 2
Реализуйте функцию `stringConcatinate`
```cpp
char* stringConcatinate(const char*, const char*);
```
```cpp
const char * p = "Hello,";
const char * p1 = " world!";
char * newString = stringConcatinate(p, p1);
p[0] = 'S';
p1[0] = 'S';
std::cout << newString << std::endl; // Hello, world!
```

### Определим структуру матрицы
```cpp
struct Matrix
{
    float ** matrix;
    int n;
    int m;
};
```
### Задание 3
Реализуйте функцию создания двумерного массива `newMatrix`
```cpp
Matrix newMatrix(int, int);
```
```cpp
int n = 10;
int m = 10;
Matrix matrix = newMatrix(n, m); // создаем матрицу N x M
```

### Задание 4
Реализуйте функцию освобождения двумерного массива `deleteMatrix`
```cpp
void deleteMatrix(Matrix&);
```
```cpp
int n = 10;
int m = 15;
Matrix matrix = newMatrix(n, m); // создаем матрицу N x M
deleteMatrix(matrix); // освобождаем память
bool b = matrix.matrix == nullptr; // true
// matrix.n == 0
// matrix.m == 0
```

### Задание 5
Реализуйте функцию заполнения матрицы `N x M` змейкой

| 0 | 1   |  5  | 6   | ... |
|---|-----|:---:|-----|-----|
| 2 | 4   | 7   | ... | ... |
| 3 | 8   | ... | ... | ... |
| 9 | ... | ... | ... | ... |

```cpp
void snake(Matrix&);
```
```cpp
int n = 10;
int m = 15;
Matrix matrix = newMatrix(n, m);
snake(matrix);
deleteMatrix(matrix);
```

### Задание 6
Реалезуйте функцию копирования матрицы
```cpp
Matrix copy(const Matrix&);
```
```cpp
int n = 10;
int m = 10;
Matrix matrixA = newMatrix(n, m);
// ...
Matrix matrixB = copy(matrixA);
deleteMatrix(matrixA);
deleteMatrix(matrixB);
```


### Задание 7
Реализуйте функцию транспонирования матрицы
```cpp
Matrix transpose(const Matrix&);
```
```cpp
int n = 10;
int m = 10;
Matrix matrix = newMatrix(n, m);
// ...
Matrix matrixT = transpose(matrix);
deleteMatrix(matrix);
```

### Задание 8
Реализуйте функцию нахождения обратной матрицы
```cpp
Matrix inverse(const Matrix&);
```
```cpp
int n = 10;
Matrix matrix = newMatrix(n, n);
// ...
Matrix inv = inverse(matrix);
deleteMatrix(matrix);
```

### Задание 9
Реализуйте функцию нахождения определителя матрицы
```cpp
float determinant(const Matrix&);
```
```cpp
int n = 10;
int m = 10;
Matrix matrix = newMatrix(n, m);
// ...
float d = determinant(matrix);
deleteMatrix(matrix);
```


### Задание 10
Реализуйте функцию создания единичной матрицы
```cpp
Matrix ones(int n);
```
```cpp
int n = 10;
int m = 10;
Matrix matrix = ones(n);
float d = determinant(matrix);
// d == 1
deleteMatrix(matrix);
```


### Задание 11
Реализуйте функцию перемножения матриц
```cpp
Matrix operator*(const Matrix&, const Matrix&);
```
```cpp
int n = 10;
int m = 10;
int k = 10;
Matrix matrixOne = newMatrix(n, m);
Matrix matrixTwo = newMatrix(m, k);
// ...
Matrix matrixThree = matrixOne * matrixTwo;
// ...
deleteMatrix(matrixOne);
deleteMatrix(matrixTwo);
deleteMatrix(matrixThree);
```


### Задание 12
Реализуйте функцию сравнения матриц
```cpp
bool operator==(const Matrix&, const Matrix&);
```
```cpp
int n = 10;
Matrix matrixOne = newMatrix(n, m);
Matrix matrixTwo = newMatrix(n, m);
// ...
bool d = (matrixOne == matrixTwo);
deleteMatrix(matrixOne);
deleteMatrix(matrixTwo);
```
