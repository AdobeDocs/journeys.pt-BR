---
product: adobe campaign
title: Gerenciamento de fuso horário
description: Saiba mais sobre o gerenciamento de fuso horário
feature: Journeys
role: User
level: Intermediate
exl-id: c0e67849-caa0-4045-94ed-38e483054e1d
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '321'
ht-degree: 8%

---

# Gerenciamento de fuso horário {#timezone_management}


>[!CAUTION]
>
>**Procurando Adobe Journey Optimizer**? Clique [aqui](https://experienceleague.adobe.com/pt-br/docs/journey-optimizer/using/ajo-home){target="_blank"} para obter a documentação do Journey Optimizer.
>
>
>_Esta documentação se refere ao material herdado do Journey Orchestration que foi substituído pelo Journey Optimizer. Entre em contato com a equipe de conta em caso de dúvidas sobre o acesso ao Journey Orchestration ou Journey Optimizer._



Você pode definir um fuso horário nas [propriedades](../building-journeys/changing-properties.md) da jornada.

Para acessar as Propriedades, clique no ícone de lápis na parte superior direita da tela.

Esse fuso horário será usado para cada atividade da jornada que contém um elemento de tempo, como:

* [Condição de tempo](../building-journeys/condition-activity.md#time_condition)
* [Condição de data](../building-journeys/condition-activity.md#date_condition)
* [Espera personalizada](../building-journeys/wait-activity.md#custom)

Você pode selecionar um fuso horário ou optar por usar o fuso horário definido no perfil do usuário.

>[!NOTE]
>
>O fuso horário do perfil funciona com o campo **timeZone** existente no grupo de campos **Detalhes da Preferência**.

## Definição de um fuso horário fixo {#fixed-timezone}

O fuso horário também pode ser corrigido. Limpe o fuso horário predefinido e escolha um na lista suspensa. Se você usar um fuso horário fixo, ele será o mesmo para todos os indivíduos que entram na jornada.

Para fazer isso, em **[!UICONTROL Properties]**, selecione um fuso horário.

![](../assets/journey72.png)

## Uso de perfis para definir o fuso horário da jornada {#timezone-from-profiles}

Se o evento de entrada da jornada tiver um namespace, o que significa que a jornada pode acessar o serviço de Perfil do cliente em tempo real do Adobe Experience Platform, você pode usar o fuso horário definido no nível do perfil. Para fazer isso, em **Propriedades**, marque **Usar fuso horário do perfil em esperas e condições**. Essa opção não está marcada por padrão.

Se um fuso horário tiver sido definido para um perfil, ele será recuperado e usado pela jornada. Caso contrário, o fuso horário usado será aquele definido no campo timezone.

![](../assets/journey73.png)

## Uso de fusos horários em expressões {#timezone-in-expressions}

As datas de início e término de uma jornada não podem ser vinculadas a um fuso horário específico. Eles são associados automaticamente ao fuso horário da instância.
