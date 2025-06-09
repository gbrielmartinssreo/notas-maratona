## *Extras importantes

### Auto
A palavra-chave `auto` em C++ permite ao compilador fazer uma inferência de tipo, isto é, detectar automaticamente o tipo de uma variável.

É bem útil quando o tipo da variável é complicado de se escraver.

```C++
#include <iostream>

int main(void){
    auto x = 3;

    std::cout << x+3;

    return 0;
}
```

### Bib algorithm
> A `<algorithm>` é uma biblioteca padrão da STL que contém diversas funções para manipular intervalos de dados (como arrays, vector, list, etc.). Ela oferece operações como busca, ordenação, contagem, substituição, permutação, entre outras.

| Função              | Descrição                                                                                          |
| ------------------- | -------------------------------------------------------------------------------------------------- |
| `adjacent_find()`   | Encontra um par de elementos consecutivos com o mesmo valor em um intervalo de dados               |
| `all_of()`          | Verifica se **todos** os elementos de um intervalo satisfazem uma condição                         |
| `any_of()`          | Verifica se **pelo menos um** elemento do intervalo satisfaz uma condição                          |
| `binary_search()`   | Busca eficiente para verificar se um valor existe em um intervalo ordenado                         |
| `copy()`            | Copia os valores de um intervalo para outro intervalo                                              |
| `count()`           | Conta quantas vezes um determinado valor aparece no intervalo                                      |
| `count_if()`        | Conta quantos elementos satisfazem uma condição                                                    |
| `fill()`            | Preenche todos os elementos de um intervalo com um valor                                           |
| `find()`            | Encontra o primeiro elemento com um valor específico                                               |
| `find_first_of()`   | Encontra o primeiro elemento que corresponde a um de vários valores especificados                  |
| `find_if()`         | Encontra o primeiro elemento que satisfaz uma condição                                             |
| `find_if_not()`     | Encontra o primeiro elemento que **não** satisfaz uma condição                                     |
| `for_each()`        | Executa uma função para cada elemento do intervalo                                                 |
| `includes()`        | Verifica se todos os elementos de um intervalo ordenado estão contidos em outro intervalo ordenado |
| `is_permutation()`  | Verifica se um intervalo é uma permutação de outro                                                 |
| `is_sorted()`       | Verifica se os elementos do intervalo estão ordenados                                              |
| `is_sorted_until()` | Retorna o ponto em que os elementos deixam de estar ordenados                                      |
| `lower_bound()`     | Encontra o primeiro elemento **maior ou igual** a um valor em um intervalo ordenado                |
| `max_element()`     | Retorna o elemento com o **maior valor** no intervalo                                              |
| `merge()`           | Combina os valores de dois intervalos ordenados em um novo intervalo também ordenado               |
| `min_element()`     | Retorna o elemento com o **menor valor** no intervalo                                              |
| `none_of()`         | Verifica se **nenhum** dos elementos satisfaz uma condição                                         |
| `random_shuffle()`  | Embaralha aleatoriamente os elementos do intervalo (⚠️ obsoleto desde C++14)                       |
| `replace()`         | Substitui todas as ocorrências de um valor por outro                                               |
| `replace_copy()`    | Cria uma cópia do intervalo, substituindo todas as ocorrências de um valor por outro               |
| `replace_copy_if()` | Cria uma cópia do intervalo, substituindo os valores que satisfazem uma condição                   |
| `replace_if()`      | Substitui os elementos que satisfazem uma condição por outro valor                                 |
| `reverse()`         | Inverte a ordem dos elementos do intervalo original                                                |
| `reverse_copy()`    | Cria uma cópia do intervalo com a ordem dos elementos invertida                                    |
| `search()`          | Busca uma **sequência de valores** dentro de um intervalo                                          |
| `sort()`            | Ordena os elementos do intervalo em **ordem crescente**                                            |
| `swap()`            | Troca os valores entre **duas variáveis**                                                          |
| `swap_ranges()`     | Troca os valores de dois intervalos de **mesmo tamanho**                                           |
| `upper_bound()`     | Encontra o primeiro elemento **estritamente maior** que um valor em um intervalo ordenado          |


# Listas

Na biblioteca padrão do C++, uma `list` representa uma lista duplamente ligada e, quando adicionamos nosso primeiro elemento o sistema coloca ele em algum lugar da memória.

Cada elemento da lista é associado com um nodo e, diferente do que acontece em um vetor, nós podemos adicionar elementos na frente ou atrás da lista.
![alt text](image-6.png)

## Quando usar
Use `std::list` quando você precisa fazer MUITAS inserções ou remoções no meio da estrutura, e:
- Você já tem um iterador pro local onde vai inserir/remover (ou pode obter de forma eficiente);
- Você não precisa acessar elementos por índice (list[3] não funciona).

```C++
#include <iostream>
#include <list>
#include <algorithm>

int main(void){

    std::list<int> l ={1,2,4,5};

    auto it = std::find(l.begin(),l.end(),4);
    l.insert(it,3);

    for(auto x:l){
        std::cout << x;
    }

    return 0;
}
```

1. Declare com `std::list<Tipo> nome;`.
2. Use `push_back()` e `push_front()` para inserir no fim/início.
3. Use `pop_back()` e `pop_front()` para remover do fim/início.
4. Use `insert()` e `erase()` com iteradores para inserir/remover no meio.
5. Itere com 
    
    ```C++
    for (auto x : minhaLista)
        std::cout << x << " ";
    ```
6. Acesse informações com `size()`, `empty()`, `front()`, `back()`.

 # Set

- Conjunto ordenado e sem duplicatas.

- Internamente é uma árvore binária balanceada (Red-Black Tree).

- As operações de inserção, remoção e busca têm custo O(log n).

- Os elementos sempre aparecem em ordem crescente.

```C++
std::set<int> s;
s.insert(3);
s.insert(1);
s.insert(2);

// Saída: 1 2 3
for (auto x : s)
    std::cout << x << " ";
```

### Quando usar:

Quando você precisa de ordenação automática.

# Unordered_set

- Conjunto não ordenado e sem duplicatas.

- Internamente é implementado com uma tabela hash.

- Operações de inserção, remoção e busca têm custo O(1) em média.

- A ordem dos elementos é imprevisível.

```C++
std::unordered_set<int> us;
us.insert(3);
us.insert(1);
us.insert(2);

// Ordem indefinida (ex: 2 1 3)
for (auto x : us)
    std::cout << x << " ";
```
### Quando usar:

Quando você só precisa saber se um elemento existe, sem se importar com a ordem.

Para performance máxima em grandes volumes de dados.

