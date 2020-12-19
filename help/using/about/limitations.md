---
product: adobe campaign
solution: Journey Orchestration
title: Limitações de Journey Orchestration
description: Saiba mais sobre limitações de Journey Orchestration
translation-type: tm+mt
source-git-commit: 6ebedad2cb8e78b4dd953bc7a2993cebbeefabcc
workflow-type: tm+mt
source-wordcount: '361'
ht-degree: 3%

---


# Limitações {#limitations}

Aqui estão limitações relacionadas ao uso do Journey Orchestration.

## Limitações de ações gerais

* Não há limite de envio. 
* Duas tentativas são executadas sistematicamente em caso de erro. Não é possível ajustar o número de tentativas de acordo com a mensagem de erro recebida. 
* O evento incorporado **Reaction** permite que você reaja às ações predefinidas (consulte esta [página](../building-journeys/reaction-events.md)). Se quiser reagir a uma mensagem enviada por meio de uma ação personalizada, é necessário configurar um evento dedicado. 
* Não há integração produzida pela Adobe Campaign Classic.

## Limitações de versões de viagem {#journey-versions-limitations}

* uma jornada que começa com uma atividade de evento na v1 não pode ser start com algo além de um evento em versões posteriores. Não é possível start de uma jornada com um evento **Qualificação de segmento**.
* uma jornada que começa com uma **Qualificação de segmento** atividade em v1 deve sempre ser start com uma **Qualificação de segmento** em versões posteriores.
* O segmento e a namespace escolhidos em **Qualificação de segmento** (primeiro nó) não podem ser alterados em novas versões.
* A regra de reentrada deve ser a mesma em todas as versões de viagem.

## Qualificação de segmento {#segment-qualification}

* A atividade **Qualificação de segmento** não pode ser usada juntamente com o Adobe Campaign Standard Transactional Messaging devido a restrições de throughput. Consulte [Descrição do produto Adobe Campaign Standard](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html). 
 

## Limitações de ações personalizadas

* O URL de ação personalizado não suporta parâmetros dinâmicos. 
* Somente métodos de chamada POST e PUT são suportados. 
* O nome do parâmetro ou cabeçalho do query não deve ser start com &quot;.&quot; ou &quot;$&quot;. 
* Endereços IP não são permitidos. 
* Endereços de Adobe internos (.adobe.) não são permitidas.
 

## Limitações de ações do Adobe Campaign

* O Adobe Campaign Standard Transactional Messaging tem uma escala máxima de 50.000 mensagens por hora em canais para uma determinada instância. Consulte [Descrição do produto Adobe Campaign Standard](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html). 
 

## Limitações de eventos

* Os dados de transmissão usados para iniciar uma jornada do cliente devem ser configurados no Journey Orchestration primeiro para obter uma ID de orquestração exclusiva. Essa ID de orquestração deve ser anexada à carga de streaming que entra no Adobe Experience Platform.
 

## Limitações das fontes de dados

* Fontes de dados externas podem ser aproveitadas em uma jornada do cliente para pesquisar dados externos em tempo real. Essas fontes devem ser utilizáveis por meio da REST API, suportar JSON e ser capazes de lidar com o volume de solicitações.