# Árvore Binária Balanceadas e não Balanceadas

## Árvore Binária

A Árvore Binária é uma ordenação de dados com base em nós, na qual ela funciona com cada nó armazenado valores, e que no caso pode estar ligada a uma subárvore à direita ou esquerda. Lembrando-se que todos os nós da subárvore à esquerda contêm valores menores que o nó da raiz, é já a subárvore da direita contém valores maiores. Outro ponto relevante é sua hierarquia, isso porque os nós têm uma especificação conforme sua posição, no caso dos nós abaixo das raízes são identificados com filhos, e os nós que são das pontas que não tem filhos são nomeados como folhas.

Veja um exemplo de uma implementação de código do método de busca.

```sh
public int buscaBinaria(int vet, int vetor[]) {
    int quite;
    int start;
    int end;
    start = 0;
    end = vetor.length-1;
    while (start <= end) {
        quite = (start + end) / 2;
        if (vet == vetor[quite]) {
            return quite;
        }
            
        if (vet > vetor[quite]) {
            start = quite + 1;
        } else {
            end = quite - 1;
        }
    }
    return -1;
}
```

Veja um exemplo de uma implementação de código do método de inserção.

```sh
public boolean insert(int vet){
	this.pt = this.raiz;
	p = buscaBinaria(vet, vetor[]);
		
	if (p != null){
	    return false;
	} else {
	    if (pos == 0) {
		    this.raiz = p;
	    } else if (pos == 1) {
		    p.father = aux;
		    aux.esq  = p;
        }
		else if (pos == 2) {
			p.father = aux;
			aux.dir  = p; 	
		}
	}
	pos = 4;
	pt = raiz;
	return true;
}
```

## Árvore Binária Balanceada

A Árvore Balanceada tem como base as inserções e exclusões, para que as buscas tenham um uso de balanceamento, onde sua altura das subárvores direita precisam ter uma altura bem próxima das subárvores da esquerda.

Veja a imagem abaixo um exemplo de Árvore Binária Balanceada.

![Optional Text](../master/Imagens/Balanceada.png)

Veja a implementação de um código chamando o objeto no método main, e executando uma busca no vetor com seus elementos balanceados em pré-ordem. Lembrando que essa busca é referente ao método "buscaBinaria" citado acima. 

```sh
public static void main(String[] args) {
    ArvoreBinaria busca = new ArvoreBinaria();
        
    int vetor[] = {51, 16, 11, 8, 13, 22, 18, 71, 53, 66, 75};
        
    System.out.println("Posição do Elemento 11: " + busca.buscaBinaria(11, vetor));
}
```

## Árvore Binária não Balanceada

A Árvore não Balanceada é o contrário da árvore balanceada, porque ela tem suas subárvores esquerda não muito próxima da altura e nem o números de nós das subárvores da direita, isso faz com que ela seja uma árvore desbalanceada.

Veja a imagem abaixo um exemplo de Árvore Binária não Balanceada.

![Optional Text](../master/Imagens/N_Balanceada.png)

Veja a implementação de um código chamando o objeto no método main, e executando uma busca no vetor com seus elementos não balanceados em pré-ordem. Lembrando que essa busca é referente ao método "buscaBinaria" citado acima.

```sh
public static void main(String[] args) {
    ArvoreBinaria busca = new ArvoreBinaria();
        
    int vetor[] = {51, 16, 8, 13, 11, 22, 18, 75, 53, 71, 66};
        
    System.out.println("Posição do Elemento 13: " + busca.buscaBinaria(13, vetor));
    }
```

## Desempenho e Possíveis Impactos em Execução

Nestes desempenhos foi feito um comparativo, no qual vai identificar a performance de uma árvore balanceada e não balanceada em uma busca de elementos, onde foi utilizado para percorrer a forma pré-ordem.

Tabela de desempenho referente a busca de elementos

| Algoritmo | Tempo de Execução | Acessos |
| ------ | ------ | ------ |
| Árvore Binária Balanceada | 483 ms | 3 |
| Árvore Binária não Balanceada | 537 ms | 3,37 |

## Análise final

Com análise nos desempenhos levantados com base nos dois métodos, dá para observar que com a árvore binária balanceada consegue ter uma maior performance, tanto no tempo como no número de acessos para chegar nos elementos.

