---
product: adobe campaign
solution: Journey Orchestration
title: toDuration
description: Saiba mais sobre a função toDuration
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 2%

---


# toDuration {#toDuration}

Converte um valor de argumento em uma duração. Para obter mais informações sobre tipos de dados, consulte [esta página](../expression/data-types.md).

## Categoria

Conversão

## Sintaxe da função

`toDuration(<parameter>)`

## Parâmetros

| Parâmetro | Descrição |
|--- |--- |
| string | formatos baseados no formato ISO-8601 duration PnDTnHnMn.nS com dias considerados exatamente 24 horas |
| integer | número de milissegundos |

Se expressão da string: Os formatos aceites são baseados no formato ISO-8601 duration PnDTnHnMn.sS com dias considerados exatamente 24 horas.

A string começa com um sinal opcional, denotado pelo símbolo negativo ou positivo ASCII. Se for negativo, todo o período é negado. A letra ASCII &quot;P&quot; é a próxima em maiúscula ou minúscula. Em seguida, há quatro seções, cada uma com um número e um sufixo. As seções têm sufixos no ASCII de &quot;D&quot;, &quot;H&quot;, &quot;M&quot; e &quot;S&quot; para dias, horas, minutos e segundos, aceitos em letras maiúsculas ou minúsculas. Os sufixos devem ocorrer em ordem. A letra ASCII &quot;T&quot; deve ocorrer antes da primeira ocorrência, se houver, de uma hora, minuto ou segunda seção. Pelo menos uma das quatro seções deve estar presente e, se &quot;T&quot; estiver presente, deve haver pelo menos uma seção após o &quot;T&quot;. A parte do número de cada seção deve consistir em um ou mais dígitos ASCII. O número pode ser pré-fixado pelo símbolo negativo ou positivo ASCII. O número de dias, horas e minutos deve ser analisado. O número de segundos deve ser analisado junto com a fração opcional. O ponto decimal pode ser um ponto ou uma vírgula. A parte fracional pode ter de zero a 9 dígitos.

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
