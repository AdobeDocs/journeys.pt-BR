---
product: adobe campaign
solution: Journey Orchestration
title: Limitações do Journey Orchestration
description: Saiba mais sobre as limitações do Journey Orchestration
translation-type: tm+mt
source-git-commit: a0b6f54e37abded690dc200bc3a901a8e0f04f79
workflow-type: tm+mt
source-wordcount: '527'
ht-degree: 2%

---


# Limitações {#limitations}

Estas são as limitações relacionadas ao uso do Journey Orchestration.

## Limitações de ações gerais

* Não há limitação de envio. 
* Duas tentativas são executadas sistematicamente em caso de erro. Não é possível ajustar o número de tentativas de acordo com a mensagem de erro recebida. 
* O evento integrado **Reaction** permite reagir a ações predefinidas (consulte esta [página](../building-journeys/reaction-events.md)). Se quiser reagir a uma mensagem enviada por meio de uma ação personalizada, será necessário configurar um evento dedicado. 
* Não há integração produzida no Adobe Campaign Classic.

## Limitações das versões de jornada {#journey-versions-limitations}

* uma jornada que começa com uma atividade de evento na v1 não pode começar com algo diferente de um evento em outras versões. Não é possível iniciar uma jornada com um evento de **Qualificação de segmento**.
* uma jornada que começa com uma atividade **Segment Qualification** em v1 deve sempre começar com uma **Segment Qualification** em outras versões.
* O segmento e o namespace escolhidos em **Segment qualification** (primeiro nó) não podem ser alterados em novas versões.
* A regra de reentrada deve ser a mesma em todas as versões da jornada.

## Qualificação do segmento {#segment-qualification}

* A atividade **Segment qualification** não pode ser usada juntamente com as mensagens transacionais do Adobe Campaign Standard devido a restrições de taxa de transferência. Consulte [Descrição de produto do Adobe Campaign Standard](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html). 
 

## Limitações de ações personalizadas

* O URL de ação personalizada não suporta parâmetros dinâmicos. 
* Somente métodos de chamada POST e PUT são compatíveis. 
* O nome do parâmetro de consulta ou cabeçalho não deve começar com &quot;.&quot; ou &quot;$&quot;. 
* Endereços IP não são permitidos. 
* Endereços internos da Adobe (.adobe.) não são permitidas.
 

## Limitações das ações do Adobe Campaign

* As mensagens transacionais do Adobe Campaign Standard têm uma escala de no máximo 50.000 mensagens por hora nos canais para uma determinada instância. Consulte [Descrição de produto do Adobe Campaign Standard](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html). 
 

## Limitações de eventos

* Para eventos gerados pelo sistema, os dados de transmissão usados para iniciar uma jornada do cliente devem ser configurados no Gerenciamento de jornada do cliente primeiro para obter uma ID de orquestração exclusiva. Essa ID de orquestração deve ser anexada à carga de transmissão que entra na Adobe Experience Platform. Essa limitação não se aplica a eventos com base em regras.
 

## Limitações das fontes de dados

* As fontes de dados externas podem ser aproveitadas em uma jornada do cliente para pesquisar dados externos em tempo real. Essas fontes devem ser utilizáveis por meio da API REST, devem ser compatíveis com JSON e podem lidar com o volume de solicitações.

## Jornadas que começam ao mesmo tempo que uma criação de perfil {#journeys-limitation-profile-creation}

Há um atraso associado à criação/atualização de perfil com base em API na Adobe Experience Platform. O Service Level Target (SLT) em termos de latência é &lt; 1 min desde a assimilação até o Perfil unificado, por 95% das solicitações, em um volume de 20 mil solicitações por segundo (RPS).

Se uma jornada for acionada simultaneamente à criação de um perfil e verificar/recuperar imediatamente as informações do Serviço de perfil, ela pode não funcionar corretamente.

Você pode escolher uma dessas duas soluções:

* Adicione uma atividade de espera após o primeiro evento para conceder à Adobe Experience Platform o tempo necessário para executar a assimilação no Serviço de perfil.

* Configure uma jornada que não use o perfil imediatamente. Por exemplo, se a jornada for projetada para confirmar a criação de uma conta, o evento de experiência poderá conter as informações necessárias para enviar a primeira mensagem de confirmação (nome, sobrenome, endereço de email etc.).