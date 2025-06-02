# Introdução ao básico de C++

> C++ é uma linguagem compilada. Para um programa rodar, o código fonte tem que ser processado por um compilador, produzir arquivos objeto, os quais são combinados por um linker em um programa executável.

## Biblioteca padrão
A biblioteca padrão que já vem no C++ é muito robusta e já contém bibliotecas para realizar operações de:
- Entrada e saída: `<iostream>, <fstream>,<iomanip`;
- Manipulação de strings: `<string>, <cstring>, <sstram>`;
- Utilitários: `<utility>, <tuple>, <optional>, <variant>`;
- Tempo e data: `<chrono>, <ctime>`;
- Manipulação de arquivos e sistema: `<filesystem>, <cstdio>`.
- Multithreading: `<thread>, <mutex>, <future>`.


## STL
Dentro da biblioteca padrão do C++ temos a STL (Standard Template Library), que é um subconjunto que armazena um conjunto de modelos de classes e funções para implementação de estruturas de dados comuns, como listas, pilhas, matrizes, etc.
É basicamente um conjunto de templates prontos (containers, algoritmos, etc.).

[Para mais detalhes sobre STL clica aqui](https://www.geeksforgeeks.org/the-c-standard-template-library-stl/)


## Includes

Como já vimos em **Algoritmos e estrutura de dados I** Os componentes não estão "ligados" ao programa automaticamente, eles fazem parte das bibliotecas externas da linguagem C++ e precisam ser explicitamente incluídos para que o compilador saiba que você quer usá-los.

# Entrada e saída de dados

Dentro do `<iostream>`, estão definidos fluxos padrão que são usados para entrada e saída de dados. Esses fluxos são representados por objetos das classes `std::ostream` e `std::istream`.

Fluxos definidos no `<iostream>`

### `std::cout`

- Classe: `std::ostream`;
- Função: fluxo de saída;
- Usado para: escrever dados na tela;
- Operador: `<<`.

```C++
std::cout << "Olá, Mundo!";
```

### `std::cin`

- Classe: `std::istream`;
- Função: fluxo de entrada;
- Usado para: Ler dados que o usuário digita no teclado;
- Operador: `>>`.

```C++
int idade;
std::cout << "Digite sua idade: ";
std::cin >> idade;  // Lê o valor digitado pelo usuário
```

### Observações
> Estruturas de repetição, escolha, funções e tipos de dados se mantém os mesmos da linguagem C.

