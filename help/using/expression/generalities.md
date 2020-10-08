---
title: Generalidades
description: Saiba mais sobre generalidades avançadas de expressões
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 3%

---


# Generalidades {#concept_rcy_qj5_dgb}

## Parênteses e prioridade da expressão{#section_edf_fks_bgb}

Os parênteses podem ser usados para tornar uma expressão complexa mais legível. _(&lt;expressão>)_ é o equivalente de _&lt;expressão>_. Os parênteses também podem ser usados para definir a ordem de avaliação e a associatividade.

As expressões serão avaliadas da esquerda para a direita. A associatividade nos operadores aritméticos deve ser aplicada: multiplicações e divisões têm prioridade sobre adições e subtrações. Para impor uma ordem específica, os parênteses devem ser adicionados para delimitar as operações. Por exemplo:

<!--```5 + 2 * 10 = 25, and (5 + 2) * 10 = 70```-->

| Expressão | Avaliação |
|--- |--- |
| `4 + 2 * 10` | <ul><li>&#39;*&#39; tem prioridade sobre &#39;+&#39;: 2 * 10 é avaliado → 20</li><li>4 + 20 → 24</li></ul> |
| `(4 + 2) * 10` | <ul><li>Os parênteses alteram a prioridade: (4 + 2) é avaliada → 6</li><li> 6 * 10 → 60</li></ul> |

## Diferenciação entre maiúsculas e minúsculas{#section_lrb_xh5_dgb}

Estas são as diferentes regras de diferenciação entre maiúsculas e minúsculas:

* Todos os operadores (e, ou, etc.) deve ser escrito em minúsculas. Por exemplo, _`<expression1>`e`<expression2>`_ é uma expressão válida, enquanto a expressão _`<expression1>`E não`<expression2>`_ é.
* Todos os nomes de função fazem distinção entre maiúsculas e minúsculas. Por exemplo, _inSegment()_ é válido, enquanto a função _INSEGMENT()_ não é.
* As referências de campo e os valores constantes fazem distinção entre maiúsculas e minúsculas: eles não são elementos incorporados da linguagem (ao contrário de operadores e funções), eles são criados pelo usuário final.

## Tipo de expressão retornado{#section_gyc_435_53b}

Dependendo do contexto de uso, o editor de expressões pode retornar valores diferentes.

| Uso avançado do editor de expressões | Tipo de expressão retornado esperado |
|--- |--- |
| Condição (condição da fonte de dados, condição de data) | booleano |
| Temporizador personalizado | dateTimeOnly |
| Mapeamento de parâmetros de ação | Qualquer |
