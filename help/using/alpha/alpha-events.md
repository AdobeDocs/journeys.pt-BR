---
title: eventos baseados em regras
description: Saiba mais sobre eventos baseados em regras.
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: f146a22cec5ffbbc61b51f8fc3c875078b2ee6bf
workflow-type: tm+mt
source-wordcount: '380'
ht-degree: 6%

---


# eventos baseados em regras{#simplified-events}

Simplificamos a forma como você configura os eventos de experiência. Estamos introduzindo um novo método que não requer o uso de uma eventID. Ao configurar seu evento no Journey Orchestration, agora é possível definir um evento baseado em regras.

Esse novo tipo de evento não gera uma eventID. Usando o editor de expressões simples, agora você simplesmente define uma regra que será usada pelo sistema para identificar os eventos relevantes que acionarão suas viagens. Essa regra pode se basear em qualquer campo disponível na carga do evento, por exemplo, o local do perfil ou o número de itens adicionados ao carrinho do perfil.

Esse novo método é transparente para os usuários. A única alteração é um novo campo na tela de definição do evento.

1. No menu esquerdo, clique no ícone **Admin** e, em seguida, clique em **Eventos**. A lista dos eventos é exibida.

   ![](../assets/alpha-event1.png)

1. Click **Add** to create a new event. O painel de configuração do evento é aberto no lado direito da tela.

   ![](../assets/alpha-event2.png)

1. Digite o nome do seu evento. Você também pode adicionar uma descrição.

   ![](../assets/alpha-event3.png)

1. No campo novo tipo **de ID de** Evento, selecione **Baseado** em regra.

   ![](../assets/alpha-event4.png)

   >[!NOTE]
   >
   >O tipo Gerado **** pelo Sistema é o método existente que requer uma eventID. Consulte [esta seção](../event/about-events.md).

1. Defina os **Schemas** e os **campos** de carga. Consulte [esta seção](../event/defining-the-payload-fields.md).

   ![](../assets/alpha-event5.png)

   >[!NOTE]
   >
   >Quando você seleciona o tipo **Gerado pelo** sistema, somente os schemas com a combinação do tipo eventID estão disponíveis. Quando você seleciona o tipo **Baseado** em regras, todos os schemas de Evento da experiência estão disponíveis.

1. Clique dentro do campo de condição **da ID do** Evento. Usando o editor de expressões simples, defina a condição que será usada pelo sistema para identificar os eventos que acionarão sua jornada.

   ![](../assets/alpha-event6.png)

   Em nosso exemplo, escrevemos uma condição baseada na cidade do perfil. Isso significa que, sempre que o sistema receber um evento que corresponda a essa condição (campo **Cidade** e valor **Paris** ), ele o transmitirá ao Journey Orchestration.

1. Defina a **Namespace** e a **Chave**. Consulte [Seleção da namespace](../event/selecting-the-namespace.md) e [Definição da chave](../event/defining-the-event-key.md)do evento.

   ![](../assets/alpha-event7.png)

As outras etapas para a configuração do evento e criação da jornada permanecem inalteradas.

O evento agora está configurado e pronto para ser lançado em uma jornada como qualquer outro evento. Toda vez que um evento que corresponde à regra é enviado ao sistema, ele é passado para a Journey Orchestration para acionar suas viagens.

