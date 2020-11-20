---
product: adobe campaign
solution: Journey Orchestration
title: Limitações de Journey Orchestration
description: Saiba mais sobre limitações de Journey Orchestration
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 2%

---


# Limitações {#limitations}

Aqui estão limitações relacionadas ao uso do Journey Orchestration.

## Limitações de ações gerais

* Não há limite de envio. 
* Duas tentativas são executadas sistematicamente em caso de erro. Não é possível ajustar o número de tentativas de acordo com a mensagem de erro recebida. 
* O evento integrado de **reação** permite que você reaja a ações inovadoras (consulte esta [página](../building-journeys/reaction-events.md)). Se quiser reagir a uma mensagem enviada por meio de uma ação personalizada, é necessário configurar um evento dedicado. 
* Não há integração produzida pela Adobe Campaign Classic.
 
## Limitações de ações personalizadas

* O URL de ação personalizado não suporta parâmetros dinâmicos. 
* Somente métodos de chamada POST e PUT são suportados. 
* O nome do parâmetro ou cabeçalho do query não deve ser start com &quot;.&quot; ou &quot;$&quot;. 
* Endereços IP não são permitidos. 
* Endereços de Adobe internos (.adobe.) não são permitidas.
 

## Limitações de ações do Adobe Campaign

* O Adobe Campaign Standard Transactional Messaging tem uma escala máxima de 50.000 mensagens por hora em canais para uma determinada instância. Consulte Descrição [do produto](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html)Adobe Campaign Standard. 
* A atividade de qualificação **do** segmento não deve ser usada juntamente com o Adobe Campaign Standard Transactional Messaging devido a restrições de throughput.
 
## Limitações de eventos

* Os dados de transmissão usados para iniciar uma jornada do cliente devem ser configurados no Journey Orchestration primeiro para obter uma ID de orquestração exclusiva. Essa ID de orquestração deve ser anexada à carga de streaming que entra no Adobe Experience Platform.
 

## Limitações das fontes de dados

* Fontes de dados externas podem ser aproveitadas em uma jornada do cliente para pesquisar dados externos em tempo real. Essas fontes devem ser utilizáveis por meio da REST API, suportar JSON e ser capazes de lidar com o volume de solicitações.