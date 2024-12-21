# Aplicações de Programação Funcional: Map, Filter e Reduce

## Descrição do Projeto
Este projeto demonstra o uso de conceitos da programação funcional aplicados a um problema prático de gerenciamento de produtos em uma loja. Utilizando as funções **map**, **filter** e **reduce**, apresentamos soluções eficientes e concisas para tarefas comuns de manipulação de listas.

## Estrutura do Problema
Trabalhamos com uma lista de produtos, onde cada produto é representado como um dicionário contendo as seguintes informações:
- **nome**: Nome do produto
- **categoria**: Categoria do produto (ex.: Vestuário, Calçados)
- **quantidade**: Quantidade em estoque
- **preco**: Preço unitário do produto

### Objetivos:
1. **Map**: Aumentar os preços dos produtos em 10% e criar uma nova lista contendo os nomes e preços ajustados.
2. **Filter**: Filtrar os produtos que possuem menos de 5 unidades em estoque.
3. **Reduce**: Calcular o preço total de todos os produtos pertencentes à categoria "Vestuário".

## Tecnologias Utilizadas
- **Python 3**
- Módulo `functools` para a função `reduce`

## Código
O código está organizado em três seções principais, cada uma demonstrando um dos conceitos funcionais:

### 1. Map
Utilizado para aplicar um aumento de 10% nos preços dos produtos e gerar uma nova lista com nomes e preços ajustados.
```python
produtos_com_aumento = list(map(lambda p: {"nome": p["nome"], "preco_ajustado": p["preco"] * 1.1}, produtos))
print(produtos_com_aumento)
```

### 2. Filter
Filtra os produtos cujo estoque é inferior a 5 unidades.
```python
produtos_baixo_estoque = list(filter(lambda p: p["quantidade"] < 5, produtos))
print(produtos_baixo_estoque)
```

### 3. Reduce
Calcula o preço total de todos os produtos da categoria "Vestuário".
```python
vestuario_total = reduce(
    lambda total, p: total + p["preco"] * p["quantidade"],
    filter(lambda p: p["categoria"] == "Vestuario", produtos),
    0,
)
print(vestuario_total)
```

## Comentários sobre a Implementação
1. **Solução Imperativa**: Exigiria o uso de loops explícitos para iterar sobre as listas, resultando em maior complexidade e código verboso.
2. **Solução Funcional**: Com o uso de `map`, `filter` e `reduce`, o código se torna mais legível, conciso e focado na lógica do problema.
3. **Vantagens**:
   - Reduz a quantidade de código boilerplate.
   - Melhor legibilidade e manutenção.
   - Maior alinhamento com paradigmas declarativos, focando no *o que fazer* ao invés do *como fazer*.
