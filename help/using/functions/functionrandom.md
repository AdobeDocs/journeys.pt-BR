---
product: adobe campaign
solution: Journey Orchestration
title: random
description: Saiba mais sobre a função aleatória
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '51'
ht-degree: 5%

---


# random {#random}

Gera um número aleatório entre 0 e 1.

## Categoria

Matemática

## Sintaxe da função

`random(<parameters>)`

## Assinatura e tipo retornado

`random()`

Retorna um decimal.

## Exemplo

`#{MarltonReservation.statistics.successRatio, defaultValue : random() * 100}`

Explicação: se a taxa de sucesso não tiver valor/for nulo, o valor padrão será aplicado e será um valor aleatório entre 0 e 1 * 100 (ou seja, de 0 a 100).
