---
product: adobe campaign
title: Mudar de uma jornada para outra
description: Mudar de uma jornada para outra
feature: Jornadas
role: User
level: Intermediate
exl-id: eaf2c795-0920-4b9c-9f06-801e43c1844b
source-git-commit: e1ee5a488e9eb6fd8d175a2ab8989c73289ea708
workflow-type: tm+mt
source-wordcount: '337'
ht-degree: 5%

---

# Atualizar perfil {#update-profile}

A atividade de ação **[!UICONTROL Update profile]** permite atualizar um perfil do Adobe Experience Platform existente com informações provenientes do evento, uma fonte de dados ou usando um valor específico.

## Observações importantes

* A ação **Atualizar perfil** só pode ser usada em jornadas que comecem com um evento que tenha um namespace.
* A ação atualiza apenas os campos existentes, mas não cria novos campos de perfil.
* Você não pode usar a ação **Atualizar perfil** para gerar eventos de experiência, por exemplo, uma compra.
* Assim como qualquer outra ação, você pode definir um caminho alternativo em caso de erro ou tempo limite e não pode colocar duas ações em paralelo.
* A solicitação de atualização enviada para a Platform será rápida, mas não imediata/dentro de um segundo. Em geral, levará alguns segundos, mas às vezes mais sem garantia. Como resultado, por exemplo, se uma ação estiver usando um &quot;campo 1&quot; atualizado por uma ação Atualizar perfil posicionada anteriormente, você não deve esperar que o &quot;campo 1&quot; seja atualizado na ação.
* No modo de teste, a atualização do perfil não será simulada. A atualização será executada no perfil de teste.

## Usar a atualização de perfil

1. Crie a jornada começando com um evento. Consulte esta [seção](../building-journeys/journey.md).

1. Na seção **Action** da paleta, solte a atividade **Update profile** na tela.

   ![](../assets/profileupdate0.png)

1. Selecione um schema na lista.

1. Clique em **Fields** para selecionar o campo que deseja atualizar. Somente um campo pode ser selecionado.

   ![](../assets/profileupdate2.png)

1. Selecione um conjunto de dados na lista.

   >[!NOTE]
   >
   >A ação **Atualizar perfil** atualiza os dados do perfil em tempo real, mas não atualiza os conjuntos de dados. A seleção do conjunto de dados é necessária, pois o perfil é um registro relacionado a um conjunto de dados.

1. Clique no campo **Value** para definir o valor que deseja usar:

   * Usando o editor de expressão simples, é possível selecionar um campo de uma fonte de dados ou do evento de entrada.

      ![](../assets/profileupdate4.png)

   * Se desejar definir um valor específico ou aproveitar funções avançadas, clique em **Modo avançado**.

      ![](../assets/profileupdate3.png)

O **Atualizar perfil** agora está configurado.

![](../assets/profileupdate1.png)
