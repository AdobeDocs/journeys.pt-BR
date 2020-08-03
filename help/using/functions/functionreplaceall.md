---
title: replaceAll
description: Saiba mais sobre a função replaceAll
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
source-git-commit: 939cde1f30a946ba4c20984dd72dcd1526d6e608
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
