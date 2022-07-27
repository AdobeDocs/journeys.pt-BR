---
product: adobe campaign
title: Gerenciamento de fuso horário
description: Saiba mais sobre o gerenciamento de fuso horário
feature: Journeys
role: User
level: Intermediate
exl-id: c0e67849-caa0-4045-94ed-38e483054e1d
source-git-commit: 77fcc4ba02a855d4d584627625a08abb4af0da2f
workflow-type: tm+mt
source-wordcount: '277'
ht-degree: 2%

---

# Gerenciamento de fuso horário {#timezone_management}

Você pode definir um fuso horário na variável [propriedades](../building-journeys/changing-properties.md) da sua jornada.

Para acessar Propriedades, clique no ícone de lápis na parte superior direita da tela.

Esse fuso horário será usado para cada atividade da jornada que contém um elemento de hora, como:

* [Condição de tempo](../building-journeys/condition-activity.md#time_condition)
* [Condição de data](../building-journeys/condition-activity.md#date_condition)
* [Aguardar personalizado](../building-journeys/wait-activity.md#custom)

Você pode selecionar um fuso horário ou optar por usar o fuso horário definido no perfil do usuário.

>[!NOTE]
>
>O fuso horário do perfil funciona com a variável **timeZone** existente na variável **Detalhes da Preferência** grupo de campos.

## Definição de fuso horário fixo {#fixed-timezone}

O fuso horário também pode ser corrigido. Limpe o fuso horário predefinido e escolha um na lista suspensa. Se você usar um fuso horário fixo, será o mesmo para todos os indivíduos que inseriram a jornada.

Para fazer isso, em **[!UICONTROL Properties]**, selecione um fuso horário.

![](../assets/journey72.png)

## Uso de perfis para definir o fuso horário da jornada {#timezone-from-profiles}

Se o evento de entrada da jornada tiver um namespace, o que significa que a jornada pode acessar o serviço de Perfil do cliente em tempo real do Adobe Experience Platform, você pode usar o fuso horário definido no nível do perfil. Para fazer isso, em **Propriedades**, verificar **Usar o fuso horário do perfil em esperas e condições**. Essa opção não está marcada por padrão.

Se um fuso horário tiver sido definido para um perfil, ele será recuperado e usado pela jornada. Caso contrário, o fuso horário usado será o definido no campo de fuso horário.

![](../assets/journey73.png)

## Uso de fusos horários em expressões {#timezone-in-expressions}

As datas de início e término de uma jornada não podem ser vinculadas a um fuso horário específico. Eles são associados automaticamente ao fuso horário da instância.
