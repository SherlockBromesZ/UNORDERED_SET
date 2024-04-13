# Desvendando o Mistério do `unordered_set` em C++: Velocidade e Eficiência

Imagine que você precisa guardar um monte de números e depois verificar se outros números estão nessa coleção. Você poderia usar um array, mas e se você precisar buscar um número específico? Aí a coisa fica lenta, né? 🐢

**É aí que entra o `unordered_set`!** 💪 Ele é uma estrutura de dados que armazena elementos únicos e permite buscar e inserir elementos com uma velocidade incrível. ⚡

## O Segredo da Velocidade: Hashing

O `unordered_set` usa uma técnica chamada hashing para organizar os elementos. Basicamente, ele transforma cada elemento em um índice único que aponta para a sua posição na memória. É como se cada número tivesse um endereço exclusivo dentro do `unordered_set`. 🗺️

Isso significa que, quando você busca um número, o `unordered_set` não precisa percorrer todos os elementos para encontrá-lo. Ele simplesmente calcula o índice do número e vai direto ao ponto! 🎯

## Comparação com o `set`

O `set` também armazena elementos únicos, mas ele os mantém em uma ordem específica (geralmente crescente). Isso significa que ele precisa fazer um trabalho extra para manter essa ordem, o que o torna um pouco mais lento que o `unordered_set` para operações de busca e inserção. 🐌

## Exemplo: Números Proibidos

Vamos usar o problema dos "Números Proibidos" para ilustrar a vantagem do `unordered_set`:

**Problema:** Dado um conjunto de números proibidos, verificar se outros números pertencem a esse conjunto.

**Solução com `unordered_set`:**

```cpp
#include<bits/stdc++.h>
using namespace std;

int main() {
    ios_base::sync_with_stdio(false);
    cin.tie(NULL);
    
    unordered_set<int> numsProibidos;
    
    int n; cin >> n;
    int numero;
    
    for(int i = 0; i < n; i++) {
        cin >> numero;
        numsProibidos.insert(numero); // Insere o número no unordered_set
    }
    
    while(cin >> numero) {
        if(numsProibidos.count(numero)) { // Verifica se o número está no unordered_set
            cout << "SIM" << endl;
        } else {
            cout << "NAO" << endl;
        }
    }
    return 0;
}
```
*Use code with caution.*

**Explicação:**

- Criamos um `unordered_set` chamado `numsProibidos` para armazenar os números proibidos.
- Lemos a quantidade de números proibidos e inserimos cada um deles no `unordered_set`.
- Lemos outros números e verificamos se eles estão presentes no `unordered_set` usando o método `count()`.
- Se o número estiver presente, imprimimos "SIM", caso contrário, imprimimos "NAO".

## Conclusão

O `unordered_set` é uma ferramenta poderosa para quem precisa de velocidade e eficiência em operações de busca e inserção de elementos únicos. Se a ordem dos elementos não for importante, ele é a escolha perfeita para o seu código! 🔥
