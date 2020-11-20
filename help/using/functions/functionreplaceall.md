---
product: adobe campaign
solution: Journey Orchestration
title: replaceAll
description: Saiba mais sobre a função replaceAll
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '75'
ht-degree: 8%

---


# replaceAll {#replaceAll}

Substitui todas as ocorrências que correspondem à string de público alvo pela string de substituição na string base.

A substituição prossegue do início da string até o final, por exemplo, substituir &quot;aa&quot; por &quot;b&quot; na string &quot;aaa&quot; resultará em &quot;ba&quot; em vez de &quot;ab&quot;.

## Categoria

String

## Sintaxe da função

`replaceAll(<parameters>)`

## Parâmetros

| Parâmetro | Tipo |
|-----------|--------------|
| base | string |
| público-alvo | string |
| substituição | string |

## Assinatura e tipo retornado

`replaceAll(<baseString>,<sourceString>,<replacementString>)`

Retorna uma string.

## Exemplo

`replaceAll("Hello World", "l", "x")`

Retorna &quot;Hexxo Worxd&quot;.
