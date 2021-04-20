---
product: adobe campaign
solution: Journey Orchestration
title: replace
description: Saiba mais sobre a substituição de função
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '80'
ht-degree: 8%

---


# replace {#replace}

Substitui a primeira ocorrência que corresponde à string de destino pela string de substituição na string base.

A substituição prossegue do início da string para o final, por exemplo, a substituição de &quot;aa&quot; por &quot;b&quot; na string &quot;aaa&quot; resultará em &quot;ba&quot; em vez de &quot;ab&quot;.

## Categoria

String

## Sintaxe da função

`replace(<parameters>)`

## Parâmetros

| Parâmetro | Tipo |
|-----------|--------------|
| base | string |
| público-alvo | string |
| substituição | string |

## Assinatura e tipo retornado

`replace(<base>,<target>,<replacement>)`

Retorne uma string.

## Exemplo

`replace("Hello World", "l", "x")`

Retorna &quot;Mundo Hexlo&quot;.
