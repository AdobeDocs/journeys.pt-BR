---
product: adobe campaign
solution: Journey Orchestration
title: Sobre eventos
description: Saiba mais sobre eventos
translation-type: tm+mt
source-git-commit: c66c09441f69e7026c60c37f87972e1e4ac9f7f8
workflow-type: tm+mt
source-wordcount: '385'
ht-degree: 54%

---


# Princípio geral {#concept_gfj_fqt_52b}

>[!CONTEXTUALHELP]
>id="jo_events"
>title="Sobre eventos"
>abstract="Um evento está vinculado a uma pessoa. Relaciona-se com o comportamento de uma pessoa (por exemplo, uma pessoa comprou um produto, visitou uma loja, saiu de um site, etc.) ou com algo que acontece ligado a uma pessoa (por exemplo, uma pessoa atingiu 10.000 pontos no programa de fidelidade). É o que o [!DNL Journey Orchestration] escutará nas jornadas para orquestrar as melhores ações futuras."

Um evento está vinculado a uma pessoa. Relaciona-se com o comportamento de uma pessoa (por exemplo, uma pessoa comprou um produto, visitou uma loja, saiu de um site, etc.) ou com algo que acontece ligado a uma pessoa (por exemplo, uma pessoa atingiu 10.000 pontos no programa de fidelidade). É o que o [!DNL Journey Orchestration] escutará nas jornadas para orquestrar as melhores ações futuras.

Essa configuração é **obrigatória**, pois o [!DNL Journey Orchestration] foi projetado para acompanhar eventos e sempre ser executado por um **usuário técnico**.

A configuração do evento permite definir as informações que o [!DNL Journey Orchestration] receberá como eventos. Você pode usar vários eventos (em diferentes etapas de uma jornada) e várias jornadas podem usar o mesmo evento.

Se você editar um evento usado em um rascunho ou em uma jornada ao vivo, será possível apenas alterar o nome, a descrição ou adicionar campos de carga útil. Limitamos rigorosamente a edição de rascunho ou jornadas ao vivo para evitar a quebra de jornadas.

Você pode definir dois tipos de eventos:

* **Eventos baseados** em regras: esse tipo de evento não gera uma eventID. Usando o editor de expressões simples, basta definir uma regra que será usada pelo sistema para identificar os eventos relevantes que acionarão suas viagens. Essa regra pode se basear em qualquer campo disponível na carga do evento, por exemplo, o local do perfil ou o número de itens adicionados ao carrinho do perfil.

   >[!CAUTION]
   >
   >Uma regra de limite é definida para eventos baseados em regras. Limita o número de eventos qualificados que uma jornada pode processar a 400 mil por minuto. Entre em contato com seu ponto de contato do programa Alpha para obter mais informações. Além dessa regra de limite, um limite de 5000 eventos por segundos é definido no nível da jornada.

* **Eventos gerados** pelo sistema: esses eventos exigem uma eventID. Esse campo eventID é gerado automaticamente ao criar o evento. O sistema que envia o evento não deve gerar uma ID; ele deve passar pela que está disponível na pré-visualização de carga.

Para saber como criar um evento, consulte esta [página](../event/about-creating.md).

