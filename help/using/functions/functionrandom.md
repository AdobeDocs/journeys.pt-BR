---
product: adobe campaign
solution: Journey Orchestration
title: random
description: Saiba mais sobre a função aleatória
feature: Jornada
role: Engenheiro de dados
level: Experienciado
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '55'
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

Explicação: se a taxa de sucesso não tiver valor/for nulo, o valor padrão será aplicado e será uma figura aleatória entre 0 e 1 * 100 (o que significa 0 a 100).
