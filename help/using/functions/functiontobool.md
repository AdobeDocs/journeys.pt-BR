---
product: adobe campaign
title: toBool
description: Saiba mais sobre a função toBool
feature: Journeys
role: Developer
level: Experienced
exl-id: 490144c2-1ecd-4772-ab15-e23b1b7d8f0c
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '75'
ht-degree: 12%

---

# toBool {#toBool}

Converte um valor de argumento em um valor booleano, dependendo de seu tipo.

* Da string: tente converter o valor da string como booleano, de &quot;true&quot; se o valor da string for &quot;true&quot;, caso contrário, false
* Do numérico: verdadeiro se o valor numérico não for igual a 0, caso contrário, falso

## Categoria

Conversão

## Sintaxe da função

`toBool(<parameter>)`

## Parâmetros

* decimal
* booleano
* sequência de caracteres
* inteiro

## Assinaturas e tipos retornados

`toBool(<decimal>)`

`toBool(<boolean>)`

`toBool(<string>)`

`toBool(<integer>)`

Retornar um booleano.

## Exemplos

`toBool("true")`

`toBool(1)`

Retorna verdadeiro.

`toBool("this is not a boolean")`

Retorna falso.
