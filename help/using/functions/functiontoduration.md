---
title: toDuration
description: Saiba mais sobre a função toDuration
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
source-wordcount: '277'
ht-degree: 1%

---


# toDuration {#toDuration}

Converte um valor de argumento em uma duração. For more information on data types, refer to [](../expression/data-types.md).

## Categoria

Conversão

## Sintaxe da função

`toDuration(<parameter>)`

## Parâmetros

| Parâmetro | Descrição |
|--- |--- |
| string | formatos baseados no formato de duração ISO-8601 PnDTnHnMn.nS com dias considerados exatamente 24 horas |
| integer | número de milissegundos |

Se a expressão da string: os formatos aceitos são baseados no formato de duração ISO-8601 PnDTnHnMn.nS com dias considerados exatamente 24 horas.

A string start com um sinal opcional, denotado pelo símbolo negativo ou positivo ASCII. Se negativo, todo o período é negado. A letra ASCII &quot;P&quot; é a seguinte em maiúsculas ou minúsculas. Em seguida, há quatro seções, cada uma delas com um número e um sufixo. As seções têm sufixos no ASCII de &quot;D&quot;, &quot;H&quot;, &quot;M&quot; e &quot;S&quot; para dias, horas, minutos e segundos, aceitos em maiúsculas ou minúsculas. Os sufixos devem ocorrer em ordem. A letra &quot;T&quot; do ASCII deve ocorrer antes da primeira ocorrência, se houver, de uma hora, minuto ou segunda seção. Deve estar presente pelo menos uma das quatro seções e, se &quot;T&quot; estiver presente, deve existir pelo menos uma seção após &quot;T&quot;. A parte numérica de cada seção deve consistir em um ou mais dígitos ASCII. O número pode ser prefixado pelo símbolo negativo ou positivo ASCII. O número de dias, horas e minutos deve ser analisado. O número de segundos deve ser analisado junto com a fração opcional. O ponto decimal pode ser um ponto ou uma vírgula. A parte fracional pode ter de zero a 9 dígitos.

## Assinaturas e tipo retornado

`toDuration(<string>)`

`toDuration(<integer>)`

Retorna uma duração.

## Exemplos

`toDuration("PT10H")`

Retorna a duração de 10 horas.

`toDuration("PT4S")`

Retorna a duração de 4s.

`toDuration(4000)`

Retorna a duração de 4s.
