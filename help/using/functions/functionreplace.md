---
product: adobe campaign
solution: Journey Orchestration
title: replace
description: Saiba mais sobre a substituição de função
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '76'
ht-degree: 7%

---


# replace {#replace}

Substitui a primeira ocorrência que corresponde à string do público alvo pela string de substituição na string base.

A substituição prossegue do início da string até o final, por exemplo, substituir &quot;aa&quot; por &quot;b&quot; na string &quot;aaa&quot; resultará em &quot;ba&quot; em vez de &quot;ab&quot;.

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

Retorna uma string.

## Exemplo

`replace("Hello World", "l", "x")`

Retorna &quot;Hexlo World&quot;.
