---
product: adobe campaign
title: random
description: Saiba mais sobre a função aleatória
feature: Jornadas
role: Data Engineer
level: Experienced
exl-id: c47dc5f0-ea69-4814-863b-e0e483ba7770
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '52'
ht-degree: 7%

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

Explicação: se a taxa de sucesso não tiver valor/for nulo, o valor padrão será aplicado e será uma figura aleatória entre 0 e 1 * 100 (o que significa 0 a 100).
