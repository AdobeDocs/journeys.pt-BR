---
product: adobe campaign
solution: Journey Orchestration
title: Gerenciamento de fuso horário
description: Saiba mais sobre o gerenciamento de fuso horário
feature: Journeys
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '265'
ht-degree: 2%

---



# Gerenciamento de fuso horário {#timezone_management}

Você pode definir um fuso horário nas [propriedades](../building-journeys/changing-properties.md) da sua jornada.

Para acessar Propriedades, clique no ícone de lápis na parte superior direita da tela.

Esse fuso horário será usado para cada atividade da jornada que contém um elemento de hora, como:

* [Condição de tempo](../building-journeys/condition-activity.md#time_condition)
* [Condição de data](../building-journeys/condition-activity.md#date_condition)
* [Aguardar personalizado](../building-journeys/wait-activity.md#custom)
* [Data de espera fixa](../building-journeys/wait-activity.md#fixed_date)

Você pode selecionar um fuso horário ou optar por usar o fuso horário definido no perfil do usuário.

## Definição de um fuso horário fixo {#fixed-timezone}

O fuso horário também pode ser corrigido. Limpe o fuso horário predefinido e escolha um na lista suspensa. Se você usar um fuso horário fixo, será o mesmo para todos os indivíduos que inseriram a jornada.

Para fazer isso, em **[!UICONTROL Properties]**, selecione um fuso horário.

![](../assets/journey73.png)

## Uso de perfis para definir o fuso horário da jornada {#timezone-from-profiles}

Se o evento de entrada da jornada tiver um namespace, o que significa que a jornada pode acessar o serviço de Perfil do cliente em tempo real da Adobe Experience Platform, o fuso horário será predefinido com o especificado no perfil do indivíduo que flui na jornada.

Se um fuso horário for definido no perfil do Adobe Experience Platform, ele poderá ser recuperado na jornada.

Se o perfil do indivíduo não contiver um fuso horário, o fuso horário recuperado será aquele definido no campo timezone.

Para fazer isso, em **[!UICONTROL Properties]**, marque **[!UICONTROL Use Profile timezone in timers and conditions]**.

![](../assets/journey72.png)

## Uso de fusos horários em expressões {#timezone-in-expressions}

As datas de início e término de uma jornada não podem ser vinculadas a um fuso horário específico. Eles são associados automaticamente ao fuso horário da instância.
