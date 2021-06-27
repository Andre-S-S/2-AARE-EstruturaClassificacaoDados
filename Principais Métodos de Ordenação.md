# Principais Métodos de Ordenação 
## Bubble Sort

O Bubble Sort é um método de ordenação que funciona da seguinte maneira, ele percorre muitas vezes em um vetor de um forma sequencial do início ao fim, onde cada etapa compara a ordem dos elemento dois a dois onde sua troca ocorre quando o elemento de maior valor fique à direita do outro, isso ocorrendo durante a passagem completa pelo vetor, assim fazendo com que o maior valor fique na última posição do vetor, esse processo repete até que o vetor fique com uma sequência ordenada.

Veja o exemplo abaixo de um implementação de código do método de ordenação Bubble Sort.
```dart
public void bubbleSort(int vetor[]) {
    int interaction; 
    int position; 
    int swap;
         
    for (interaction = 0; interaction < vetor.length - 1; interaction++) {
        for (position = 0; position < vetor.length - interaction - 1; position++) {
            if (vetor[position] > vetor[position + 1]) {
                swap = vetor[position];
                vetor[position] = vetor[position + 1];
                vetor[position + 1] = swap;
            }
        }
        for (int i = 0; i < vetor.length; i++) {
            System.out.print(vetor[i] + " ");
        }
        System.out.println(" ");
    }
}
```

## Selection Sort

O Selection Sort tem como funcionalidade fazer com que um vetor fique ordenada de forma bem simples, isso porque a sua sequência de ordenação acontece sempre que menor valor passa para a primeira posição do vetor, após ocorrer a troca ele percorrer de volta e faz o mesmo processo, só que desta vez com o segundo menor valor jogando para a segunda posição, e assim repetindo este processo até que o vetor fique totalmente ordenado.

Veja o exemplo abaixo de um implementação de código do método de ordenação Selection Sort.

```dart
public void selectionSort(int vetor[]) {
    int interaction;
    int position;
    int swap;
    int startPosition;
    int endPosition;
        
    for (interaction = 0; interaction <  vetor.length - 1; interaction++) {
        startPosition = interaction;
        endPosition = interaction + 1;  
        for (position = startPosition + 1; position < vetor.length; position++) {
            if (vetor[position] < vetor[endPosition]) {
                endPosition = position;
            }
        } 
        if (vetor[endPosition] < vetor[startPosition]) {
            swap = vetor[startPosition];
            vetor[startPosition] = vetor[endPosition];
            vetor[endPosition] = swap;
        }
        for (int i = 0; i < vetor.length; i++) {
            System.out.print(vetor[i] + " ");
        }
        System.out.println(" ");
    }    
}
```

## Insertion Sort

O Insertion Sort funciona em uma lista e percorre da esquerda para a direita, na qual ele encontra seu maior valor e vai o passando para direita assim que vai encontrando uma valor menor a sua direita, sendo assim ele vai e pega seus elementos de menor valor da direita faz uma comparação e posicioná de forma ordenada para a esquerda da lista.

Veja o exemplo abaixo de um implementação de código do método de ordenação Insertion Sort.

```dart
public void insertionSort(int vetor[]) {
    int interaction;
    int position;
    int swap;
        
    for (interaction = 1; interaction < vetor.length; interaction++) {
        position = vetor[interaction];
        for (swap = interaction - 1; (swap >= 0) && vetor[swap] > position; swap--) {
            vetor[swap + 1] = vetor[swap];
        }
        vetor[swap + 1] = position;
        for (int i = 0; i < vetor.length; i++) {
            System.out.print(vetor[i] + " ");
        }
        System.out.println(" ");
    }
}
```

## Quick Sort

O Quick Sort é um algoritmo de ordenação que funciona em uma lista, onde sua principal referência é um elemento que se chama de pivô, no qual ele organiza a lista, onde todos os valores que estejam a frente dele sejam menores que ele, e no caso dos valores que estejam depois dele sejam maiores que ele. Assim que vai ocorrendo esse processo o valor que no caso é o pivô já fica posicionado no final da lista. No caso como ele é separado em dois grupos, ele precisa fazer esse processo até que a lista fique totalmente ordenada.

Veja o exemplo abaixo de um implementação de código do método de ordenação Quick Sort, onde ele conta com outro método divisor para dividir os elementos da lista.

```dart
public int division(int vetor[], int start, int end) {
    int reference;  
    int up;
    int down;
    int swap;
        
    reference = vetor[start];
    down = start;
    up = end;
        
    while (down < up) {
        while (vetor[down] <= reference && down < end) {
            down++;
        }
        while (vetor[up] > reference) {
            up--;
        }  
        if (down < up) {
            swap = vetor[down];
            vetor[down] = vetor[up];
            vetor[up] = swap;
        }
    }
    vetor[start] = vetor[up];
    vetor[up] = reference;
    return up;
}

public void quickSort(int vetor[], int start, int end) {
    int pivo; 
        
    if (start > end) {
        return;
    }
        
    pivo = division(vetor ,start, end);
    quickSort(vetor, start, pivo - 1);
    quickSort(vetor, pivo + 1, end);
       
    for (int i = 0; i < vetor.length; i++) {
        System.out.print(vetor[i] + " ");
    }
    System.out.println(" ");
}
```

## Comparativo de Performance e Execução

Aqui foi feito um comparativo dos métodos de ordenação, na qual eles mostram qual é a performance de cada um deles, com quantidades de números diferentes de cada execução do mesmo. Lembrando-se que todos os comparativos foram feitos em ordem crescente.

### Comparativo 1

Vetor de 10 elementos.

| Algoritmo | Tempo de Execução |
| ------ | ------ |
| Bubble Sort | 156 ms |
| Selection Sort | 148 ms |
| Insertion Sort | 142 ms |
| Quick Sort | 147 ms |

### Comparativo 2

Vetor de 50 elementos.

| Algoritmo | Tempo de Execução |
| ------ | ------ |
| Bubble Sort | 248 ms |
| Selection Sort | 232 ms |
| Insertion Sort | 209 ms |
| Quick Sort | 212 ms |

### Comparativo 3

Vetor de 100 elementos.

| Algoritmo | Tempo de Execução |
| ------ | ------ |
| Bubble Sort | 299 ms |
| Selection Sort | 291 ms |
| Insertion Sort | 234 ms |
| Quick Sort | 246 ms |

## Análise final

Com a observação levantada por meio de comparações de execução e performance, dá pra ver nitidamente que o método de ordenação que deve um bom desempenho baseado com o número de elementos dentro de um vetor, foi o Insertion Sort, porque ele obteve um melhor tempo e performance independentemente do número de elementos dentro de um vetor.