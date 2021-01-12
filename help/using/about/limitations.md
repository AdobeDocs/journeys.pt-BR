---
product: adobe campaign
solution: Journey Orchestration
title: Limitações de Journey Orchestration
description: Saiba mais sobre limitações de Journey Orchestration
translation-type: tm+mt
source-git-commit: f562d4a967e6551d3b8a1bc4dbddbf01da9b3e70
workflow-type: tm+mt
source-wordcount: '515'
ht-degree: 2%

---


# Limitações {#limitations}

Aqui estão limitações relacionadas ao uso do Journey Orchestration.

## Limitações de ações gerais

* Não há limite de envio. 
* Duas tentativas são executadas sistematicamente em caso de erro. Não é possível ajustar o número de tentativas de acordo com a mensagem de erro recebida. 
* O evento incorporado **Reaction** permite que você reaja às ações predefinidas (consulte esta [página](../building-journeys/reaction-events.md)). Se quiser reagir a uma mensagem enviada por meio de uma ação personalizada, é necessário configurar um evento dedicado. 
* Não há integração produzida pela Adobe Campaign Classic.

## Limitações de versões jornadas {#journey-versions-limitations}

* uma jornada que começa com uma atividade de evento na v1 não pode ser start com outra coisa além de um evento em versões posteriores. Não é possível start de uma jornada com um evento **Qualificação de segmento**.
* uma jornada que comece com uma atividade **Qualificação de segmento** no v1 deve sempre ter um start com uma **Qualificação de segmento** em versões posteriores.
* O segmento e a namespace escolhidos em **Qualificação de segmento** (primeiro nó) não podem ser alterados em novas versões.
* A regra de reentrada deve ser a mesma em todas as versões de jornada.

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

## Jornadas que começam ao mesmo tempo que uma criação de perfil {#journeys-limitation-profile-creation}

Há um atraso associado à criação/atualização de perfis com base em API no Adobe Experience Platform. O Público alvo de nível de serviço (SLT) em termos de latência é &lt; 1 min desde a ingestão até o Perfil unificado por 95% das solicitações, em um volume de 20 mil solicitações por segundo (RPS).

Se uma Jornada for disparada simultaneamente para uma criação de perfil e verificar/recuperar imediatamente as informações do Serviço de Perfil, talvez não funcione corretamente.

É possível escolher uma destas duas soluções:

* Adicione uma atividade de espera após o primeiro evento para conceder à Adobe Experience Platform o tempo necessário para executar a ingestão ao Serviço de Perfil.

* Configure uma jornada que não aproveite imediatamente o perfil. Por exemplo, se a jornada for projetada para confirmar a criação de uma conta, o evento da experiência poderá conter as informações necessárias para enviar a primeira mensagem de confirmação (nome, sobrenome, endereço de email etc).