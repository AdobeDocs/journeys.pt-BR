---
product: adobe campaign
solution: Journey Orchestration
title: Adicionar uma condição
description: Saiba como adicionar uma condição
feature: Journeys
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '209'
ht-degree: 4%

---



# Adicionar uma condição {#concept_rbg_gqt_52b}

Para eventos gerados pelo sistema, é possível definir uma condição de evento que permita que o sistema filtre o processamento de eventos. Se a condição for verdadeira, o evento será processado. Se a condição não for verdadeira, o evento será ignorado.

A condição nos eventos só pode ser baseada nos dados transmitidos no payload do evento. A condição definida no nível do evento não pode ser alterada na tela por um profissional de marketing. O objetivo é proteger essa condição quando esse evento for usado. Por exemplo, se você nunca quiser que profissionais de marketing usem eventos de abandono de carrinho se o valor do carrinho for muito pequeno, poderá criar uma condição no campo de evento &quot;valor do carrinho&quot; e impor um valor acima de 100 dólares.

Você pode usar o editor de expressão simples ou o editor de expressão avançado para configurar condições em eventos. Consulte [esta página](../expression/expressionadvanced.md).

Por exemplo, é possível definir uma condição para processar apenas os eventos de um tipo de evento específico e ignorar os outros tipos. Ou se o evento for um abandono de carrinho e a carga incluir o campo de valor do carrinho, você poderá definir uma condição de evento para processar os eventos somente se o valor do carrinho for maior que 100 dólares.

![](../assets/journey78.png)
