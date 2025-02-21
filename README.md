# Algoritmo de Pesquisa Binária

### O algoritmo de pesquisa binária é uma técnica eficiente para encontrar um item em uma lista ordenada. Ao invés de percorrer todos os elementos da lista de forma sequencial (como no caso da pesquisa linear), ele utiliza o princípio de "dividir para conquistar" para reduzir significativamente o número de comparações necessárias.
  
  ![code](https://github.com/user-attachments/assets/5c43d964-da94-4174-a392-915261c03e38)
  ----------


### O algoritmo divide a lista ao meio repetidamente, comparando o valor buscado com o elemento do meio e ajustando os limites da busca (baixo e alto) até encontrar o item ou determinar que ele não está presente na lista.

![print_code](https://github.com/user-attachments/assets/37365a16-997a-47ed-abdb-439afa19482c)

-------

Implementação
A seguir, temos a implementação de um algoritmo de pesquisa binária em Python:

python
Copiar
def pesquisa_binaria(lista, item):
    baixo = 0
    alto = len(lista) - 1

    while baixo <= alto:
        meio = int((baixo + alto) / 2)
        chute = lista[meio]

        if chute == item:
            return meio
        if chute > item:
            alto = meio - 1
        else:
            baixo = meio + 1
    return None  

minha_lista = [1, 3, 5, 7, 9]
print(pesquisa_binaria(minha_lista, 9))
Explicação do Código
Inicialização dos índices:

baixo é o índice inicial da lista, definido como 0.
alto é o índice final da lista, definido como o comprimento da lista menos um (len(lista) - 1).
Laço de repetição (while):

O laço continua enquanto baixo for menor ou igual a alto. Isso significa que ainda há elementos a serem analisados entre esses dois índices.
Cálculo do meio:

A variável meio é calculada como a média entre os índices baixo e alto. O meio representa o ponto central da sublista que estamos analisando.
Comparações:

Se o valor no índice meio for igual ao item buscado, o índice meio é retornado, indicando a posição do item na lista.
Se o valor no índice meio for maior que o item, significa que o item está na metade inferior da lista, então o índice alto é ajustado para meio - 1.
Se o valor no índice meio for menor que o item, o item está na metade superior, então o índice baixo é ajustado para meio + 1.
Retorno final:

Se o laço terminar sem encontrar o item, a função retorna None, indicando que o item não está presente na lista.
Exemplo de Execução
Com a lista [1, 3, 5, 7, 9] e o item 9, o algoritmo encontra o item na última posição e retorna o índice 4, pois 9 está localizado no índice 4 da lista.

minha_lista = [1, 3, 5, 7, 9]
print(pesquisa_binaria(minha_lista, 9))  # Saída: 4
O que aprendi no livro Entendendo Algoritmos (Jeffrey Leek, 2017)
O livro Entendendo Algoritmos descreve de forma clara e acessível como funcionam os principais algoritmos usados na ciência da computação. No capítulo sobre pesquisa binária, aprendemos que:

**Eficiência**: A pesquisa binária é muito mais eficiente que a pesquisa linear, especialmente quando lidamos com grandes volumes de dados. Enquanto a pesquisa linear pode precisar de até n comparações, a pesquisa binária reduz o número de comparações para log₂(n), o que a torna uma escolha ideal quando a lista está ordenada.

**Complexidade Temporal**: O algoritmo de pesquisa binária tem complexidade de tempo O(log n), o que significa que ele é muito mais rápido em listas grandes em comparação com a pesquisa linear, que tem complexidade O(n).

**Pré-condições**: A principal condição para a aplicação da pesquisa binária é que a lista esteja ordenada. Caso contrário, o algoritmo não funcionará corretamente.

**Aplicações**: A pesquisa binária é amplamente utilizada em diversos problemas computacionais, como busca de elementos em grandes bancos de dados, tabelas de pesquisa e até mesmo na implementação de algoritmos de busca em jogos e inteligência artificial.


A **pesquisa binária** é uma técnica fundamental em ciência da computação e, quando aplicada corretamente, pode melhorar significativamente a eficiência de programas que necessitam buscar informações em listas ordenadas. Ela é uma ótima demonstração de como a divisão de problemas e o uso de técnicas de otimização podem transformar soluções simples em soluções mais poderosas e eficientes.
