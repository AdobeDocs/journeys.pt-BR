---
product: adobe campaign
title: Atualizar perfil
description: Atualizar perfil
feature: Journeys
role: User
level: Intermediate
exl-id: eaf2c795-0920-4b9c-9f06-801e43c1844b
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '390'
ht-degree: 3%

---

# Atualizar perfil {#update-profile}


>[!CAUTION]
>
>**Procurando Adobe Journey Optimizer**? Clique [aqui](https://experienceleague.adobe.com/pt-br/docs/journey-optimizer/using/ajo-home){target="_blank"} para obter a documentação do Journey Optimizer.
>
>
>_Esta documentação se refere ao material herdado do Journey Orchestration que foi substituído pelo Journey Optimizer. Entre em contato com a equipe de conta em caso de dúvidas sobre o acesso ao Journey Orchestration ou Journey Optimizer._


A atividade de ação **[!UICONTROL Update profile]** permite atualizar um perfil do Adobe Experience Platform existente com informações provenientes do evento, de uma fonte de dados ou usando um valor específico.

## Observações importantes

* A ação **Atualizar perfil** só pode ser usada em jornadas que comecem com um evento que tenha um namespace.
* A ação atualiza apenas os campos existentes, não cria novos campos de perfil.
* Você não pode usar a ação **Atualizar perfil** para gerar eventos de experiência, por exemplo, uma compra.
* Como qualquer outra ação, é possível definir um caminho alternativo em caso de erro ou tempo limite, e não é possível colocar duas ações em paralelo.
* A solicitação de atualização enviada para a Platform será rápida, mas não imediata/em um segundo. Normalmente, levará alguns segundos, mas às vezes mais, sem garantia. Como resultado, por exemplo, se uma ação estiver usando o &quot;campo 1&quot; atualizado por uma ação Atualizar perfil posicionada anteriormente, não é de esperar que o &quot;campo 1&quot; seja atualizado na ação.
* No modo de teste, a atualização do perfil não será simulada. A atualização será executada no perfil de teste.
* A atividade **Atualizar perfil** não oferece suporte a campos XDM definidos como uma enumeração.

## Uso da atualização de perfil

1. Projete sua jornada iniciando com um evento. Consulte esta [seção](../building-journeys/journey.md).

1. Na seção **Ação** da paleta, solte a atividade **Atualizar perfil** na tela.

   ![](../assets/profileupdate0.png)

1. Selecione um esquema na lista.

1. Clique em **Campos** para selecionar o campo que deseja atualizar. Somente um campo pode ser selecionado.

   ![](../assets/profileupdate2.png)

1. Selecione um conjunto de dados na lista.

   >[!NOTE]
   >
   >A ação **Atualizar perfil** atualiza os dados do perfil em tempo real, mas não atualiza os conjuntos de dados. A seleção do conjunto de dados é necessária, pois o perfil é um registro relacionado a um conjunto de dados.

1. Clique no campo **Value** para definir o valor que você deseja usar:

   * Usando o editor de expressões simples, é possível selecionar um campo de uma fonte de dados ou do evento de entrada.

     ![](../assets/profileupdate4.png)

   * Para definir um valor específico ou aproveitar funções avançadas, clique em **Modo avançado**.

     ![](../assets/profileupdate3.png)

O **Perfil de atualização** está configurado agora.

![](../assets/profileupdate1.png)
