---
title: replace
description: Saiba mais sobre a substituição de função
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: d6360d616199d597255610959432c7b93fd4e25c
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
