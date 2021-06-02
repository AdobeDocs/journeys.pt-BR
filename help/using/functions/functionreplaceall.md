---
product: adobe campaign
title: replaceAll
description: Saiba mais sobre a função replaceAll
feature: Jornadas
role: Data Engineer
level: Experienced
exl-id: d60059e5-6bf8-4a57-88a4-5323d5f0fa0b
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '76'
ht-degree: 10%

---

# replaceAll {#replaceAll}

Substitui todas as ocorrências que correspondem à string de destino pela string de substituição na string base.

A substituição prossegue do início da string para o final, por exemplo, a substituição de &quot;aa&quot; por &quot;b&quot; na string &quot;aaa&quot; resultará em &quot;ba&quot; em vez de &quot;ab&quot;.

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
