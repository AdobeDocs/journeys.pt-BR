---
title: toInteger
description: Saiba mais sobre a função toInteger
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
source-wordcount: '70'
ht-degree: 7%

---


# toInteger {#toInteger}

Converte um valor de argumento em um número inteiro.

## Categoria

Conversão

## Sintaxe da função

`toInteger(<parameter>)`

## Parâmetros

| Parâmetro | Descrição |
|--- |--- |
| string | converte o valor da string como um número inteiro |
| dateTime | converte a data como o número de milissegundos (milissegundos) |
| decimal | converte em número inteiro removendo a parte decimal (por exemplo: 1,5 passa a ser 1) |
| booleano | converte o valor booliano como 1 se for verdadeiro, 0 se for falso |

## Assinaturas e tipo retornado

`toInteger(<dateTime>)`

`toInteger(<decimal>)`

`toInteger(<integer>)`

`toInteger(<string>)`

`toInteger(<boolean>)`

Retorna um número inteiro.

## Exemplos

`toInteger(4)`

Retorna 4.
