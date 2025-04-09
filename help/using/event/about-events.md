---
product: adobe campaign
title: Sobre eventos
description: Saiba mais sobre eventos
feature: Journeys
role: User
level: Intermediate
exl-id: 2115ab1d-1084-4429-8315-0357c8525c47
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '446'
ht-degree: 90%

---

# Princípio geral {#concept_gfj_fqt_52b}


>[!CAUTION]
>
>**Procurando Adobe Journey Optimizer**? Clique [aqui](https://experienceleague.adobe.com/pt-br/docs/journey-optimizer/using/ajo-home){target="_blank"} para obter a documentação do Journey Optimizer.
>
>
>_Esta documentação se refere ao material herdado do Journey Orchestration que foi substituído pelo Journey Optimizer. Entre em contato com a equipe de conta em caso de dúvidas sobre o acesso ao Journey Orchestration ou Journey Optimizer._



>[!CONTEXTUALHELP]
>id="jo_events"
>title="Sobre eventos"
>abstract="Um evento está vinculado a uma pessoa. Relaciona-se com o comportamento de uma pessoa ou com algo que acontece ligado a uma pessoa. É o que o [!DNL Journey Orchestration] considera nas jornadas para orquestrar as melhores ações futuras."

Um evento está vinculado a uma pessoa. Ele se refere ao comportamento de uma pessoa (por exemplo, uma pessoa comprou um produto, visitou uma loja, saiu de um site etc.) ou a um acontecimento relacionado a uma pessoa (por exemplo, uma pessoa acumulou 10 mil pontos de fidelidade). É o que o [!DNL Journey Orchestration] considera nas jornadas para orquestrar as melhores ações futuras.

Essa configuração é **obrigatória**, pois o [!DNL Journey Orchestration] foi projetado para acompanhar eventos e sempre ser executado por um **usuário técnico**.

A configuração do evento permite definir as informações que o [!DNL Journey Orchestration] receberá como eventos. Você pode usar vários eventos (em diferentes etapas de uma jornada) e várias jornadas podem usar o mesmo evento.

Se você editar um evento usado em um rascunho ou em uma jornada ao vivo, será possível apenas alterar o nome, a descrição ou adicionar campos de carga útil. Limitamos rigorosamente a edição de rascunho ou jornadas ao vivo para evitar a quebra de jornadas.

Você pode definir dois tipos de eventos:

* **Eventos baseados em regras**: esse tipo de evento não gera uma eventID. Usando o editor de expressões simples, basta definir uma regra que será usada pelo sistema para identificar os eventos relevantes que acionarão suas jornadas. Essa regra pode ser baseada em qualquer campo disponível na carga do evento, por exemplo, o local do perfil ou o número de itens adicionados ao carrinho do perfil.

  >[!CAUTION]
  >
  >Uma regra de limite é definida para eventos baseados em regras. Limita o número de eventos qualificados que uma jornada pode processar para 5000 por segundo em uma determinada organização (ORG). Corresponde aos SLAs do Journey Orchestration. Consulte esta [página](https://helpx.adobe.com/br/legal/product-descriptions/journey-orchestration.html).

* **Eventos gerados pelo sistema**: esses eventos exigem uma eventID. Esse campo eventID é gerado automaticamente ao criar o evento. O sistema que envia o evento não deve gerar uma ID, mas sim passar a disponível na pré-visualização de carga.

O Journey Orchestration exige que os eventos sejam transmitidos ou armazenados em lote na Adobe Experience Platform. Esses dados não precisam necessariamente acessar o Perfil em tempo real. Se você quiser usar os eventos para segmentação ou pesquisa em uma jornada separada, recomendamos ativar o conjunto de dados para perfil.

Para saber como criar um evento, consulte esta [página](../event/about-creating.md).
