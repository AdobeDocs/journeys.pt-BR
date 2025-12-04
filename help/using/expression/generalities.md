---
product: adobe campaign
title: Generalidades
description: Saiba mais sobre generalidades de expressão avançadas
feature: Journeys
role: Developer
level: Experienced
exl-id: ba474219-7c9e-4f93-8e9c-16c317131614
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '269'
ht-degree: 19%

---

# Generalidades {#concept_rcy_qj5_dgb}


>[!CAUTION]
>
>**Está procurando pelo Adobe Journey Optimizer**? Clique [aqui](https://experienceleague.adobe.com/pt-br/docs/journey-optimizer/using/ajo-home){target="_blank"} para acessar a documentação do Journey Optimizer.
>
>
>_Essa documentação refere-se ao material herdado do Journey Orchestration, que foi substituído pelo Journey Optimizer. Entre em contato com a equipe de contas em caso de dúvidas sobre como acessar o Journey Orchestration ou o Journey Optimizer._


## Parênteses e prioridade da expressão{#section_edf_fks_bgb}

É possível usar parênteses para tornar uma expressão complexa mais legível. _(&lt;expressão>)_ é o equivalente a _&lt;expressão>_. Também é possível usar parênteses para definir a ordem de avaliação e a associatividade.

As expressões serão avaliadas da esquerda para a direita. A associatividade em operadores aritméticos deve ser aplicada: multiplicações e divisões têm prioridade sobre adições e subtrações. Para impor uma ordem específica, é necessário adicionar parênteses para delimitar as operações. Por exemplo:

<!--```5 + 2 * 10 = 25, and (5 + 2) * 10 = 70```-->

| Expressão | Avaliação |
|--- |--- |
| `4 + 2 * 10` | <ul><li>&#39;*&#39; tem prioridade sobre &#39;+&#39;: 2 * 10 é avaliado → 20</li><li>4 + 20 → 24</li></ul> |
| `(4 + 2) * 10` | <ul><li>Os parênteses alteram a prioridade: (4 + 2) é avaliado → 6</li><li> 6 * 10 → 60</li></ul> |

## Diferenciação de maiúsculas e minúsculas{#section_lrb_xh5_dgb}

Estas são as diferentes regras de diferenciação entre maiúsculas e minúsculas:

* Todos os operadores (and, or, etc.) devem ser escritos em minúsculas. Por exemplo, _`<expression1>`e`<expression2>`_ é uma expressão válida, enquanto a expressão _`<expression1>`E`<expression2>`_ não é.
* Todos os nomes de função fazem distinção entre maiúsculas e minúsculas. Por exemplo, _inSegment()_ é válido, enquanto a função _INSEGMENT()_ não é.
* Referências de campo e valores constantes fazem distinção entre maiúsculas e minúsculas: eles não são elementos integrados da linguagem (em vez de operadores e funções), eles são criados pelo usuário final.

## Tipo de expressão retornada{#section_gyc_435_53b}

Dependendo do contexto de uso, o editor de expressão pode retornar valores diferentes.

| Uso do editor de expressão avançado | Tipo de expressão retornada esperado |
|--- |--- |
| Condição (condição da fonte de dados, condição de data) | booleano |
| Temporizador personalizado | dateTimeOnly |
| Mapeamento de parâmetros de ação | Qualquer uma |
