---
product: adobe campaign
title: Limitações de Journey Orchestration
description: Saiba mais sobre as limitações de Journey Orchestration
feature: Jornadas
role: Business Practitioner
level: Beginner
exl-id: 27859689-dc61-4f7a-b942-431cdf244455
source-git-commit: 784c91054e0f6b9ea12aa4b7f4079f7c2da8f949
workflow-type: tm+mt
source-wordcount: '519'
ht-degree: 2%

---

# Limitações {#limitations}

Estas são limitações relacionadas ao uso do Journey Orchestration.

## Limitações de ações gerais

* Não há limitação de envio. 
* Três tentativas são executadas sistematicamente em caso de erro. Não é possível ajustar o número de tentativas de acordo com a mensagem de erro recebida. 
* O evento integrado **Reaction** permite reagir a ações predefinidas (consulte esta [página](../building-journeys/reaction-events.md)). Se quiser reagir a uma mensagem enviada por meio de uma ação personalizada, será necessário configurar um evento dedicado. 

## Limitações das versões do Jornada {#journey-versions-limitations}

* Uma jornada que começa com uma atividade de evento em v1 não pode começar com algo diferente de um evento em outras versões. Não é possível iniciar uma jornada com um evento de **Qualificação de segmento**.
* Uma jornada que começa com uma atividade **Qualificação de segmento** em v1 deve sempre começar com uma **Qualificação de segmento** em outras versões.
* O segmento e o namespace escolhidos em **Segment qualification** (primeiro nó) não podem ser alterados em novas versões.
* A regra de reentrada deve ser a mesma em todas as versões do jornada.

## Qualificação do segmento {#segment-qualification}

* A atividade **Segment qualification** não pode ser usada juntamente com as mensagens transacionais do Adobe Campaign Standard devido a restrições de taxa de transferência. Consulte [Descrição do produto Adobe Campaign Standard](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html). 
 

## Limitações de ações personalizadas

* O URL de ação personalizada não suporta parâmetros dinâmicos. 
* Somente métodos de chamada POST e PUT são compatíveis. 
* O nome do parâmetro de consulta ou cabeçalho não deve começar com &quot;.&quot; ou &quot;$&quot;. 
* Endereços IP não são permitidos. 
* Endereços Adobe internos (.adobe.) não são permitidas.
 

## Limitações de ações do Adobe Campaign

* As mensagens transacionais do Adobe Campaign Standard têm uma escala de no máximo 50.000 mensagens por hora nos canais para uma determinada instância. Consulte [Descrição do produto Adobe Campaign Standard](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html). 
 

## Limitações de eventos

* Para eventos gerados pelo sistema, os dados de transmissão usados para iniciar uma jornada do cliente devem ser configurados no Journey Orchestration primeiro para obter uma ID de orquestração exclusiva. Essa ID de orquestração deve ser anexada à carga de transmissão que entra no Adobe Experience Platform. Essa limitação não se aplica a eventos com base em regras.
 

## Limitações das fontes de dados

* As fontes de dados externas podem ser aproveitadas em uma jornada do cliente para pesquisar dados externos em tempo real. Essas fontes devem ser utilizáveis por meio da API REST, devem ser compatíveis com JSON e podem lidar com o volume de solicitações.

## Jornadas que começam ao mesmo tempo que uma criação de perfil {#journeys-limitation-profile-creation}

Há um atraso associado à criação/atualização de perfil com base em API no Adobe Experience Platform. O Service Level Target (SLT) em termos de latência é &lt; 1 min desde a assimilação até o Perfil unificado, por 95% das solicitações, em um volume de 20 mil solicitações por segundo (RPS).

Se uma Jornada for acionada simultaneamente à criação de um perfil e verificar/recuperar imediatamente as informações do Serviço de perfil, ela pode não funcionar corretamente.

Você pode escolher uma dessas duas soluções:

* Adicione uma atividade de espera após o primeiro evento para conceder ao Adobe Experience Platform o tempo necessário para executar a assimilação no Serviço de perfil.

* Configure uma jornada que não use o perfil imediatamente. Por exemplo, se a jornada foi projetada para confirmar a criação de uma conta, o evento de experiência pode conter as informações necessárias para enviar a primeira mensagem de confirmação (nome, sobrenome, endereço de email etc.).
