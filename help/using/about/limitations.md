---
product: adobe campaign
title: Limitações do Journey Orchestration
description: Saiba mais sobre as limitações do Journey Orchestration
feature: Journeys
role: User
level: Beginner
exl-id: fef039ae-c04d-4198-a082-4be27710255f
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '609'
ht-degree: 42%

---

# Limitações {#limitations}


>[!CAUTION]
>
>**Procurando Adobe Journey Optimizer**? Clique [aqui](https://experienceleague.adobe.com/pt-br/docs/journey-optimizer/using/ajo-home){target="_blank"} para obter a documentação do Journey Optimizer.
>
>
>_Esta documentação se refere ao material herdado do Journey Orchestration que foi substituído pelo Journey Optimizer. Entre em contato com a equipe de conta em caso de dúvidas sobre o acesso ao Journey Orchestration ou Journey Optimizer._



Estas são as limitações relacionadas ao uso do Journey Orchestration.

## Medidas de proteção gerais da jornada {#journeys-guardrails-journeys}

* O limite de número de atividades em uma jornada é de 50. O número de atividades é exibido na seção superior esquerda da tela da jornada.
* O limite de número de **jornadas ativas** em uma organização é de 100 por sandbox. Quando esse limite for atingido, não será mais possível publicar uma nova jornada.

## Limitações gerais de ações

* Três tentativas são executadas sistematicamente em caso de erro. Não é possível ajustar o número de tentativas de acordo com a mensagem de erro recebida. 
* O evento **Reação** interno permite que você reaja a ações predefinidas (consulte esta [página](../building-journeys/reaction-events.md)). Se quiser reagir a uma mensagem enviada por meio de uma ação personalizada, será necessário configurar um evento dedicado. 

## Limitações de versões do Jornada {#journey-versions-limitations}

* Uma jornada que começa com uma atividade de evento em v1 não pode começar com algo diferente de um evento em outras versões. Não é possível iniciar uma jornada com um evento de **Qualificação do segmento**.
* Uma jornada que começa com uma atividade de **Qualificação de segmento** em v1 deve sempre começar com uma **Qualificação de segmento** em outras versões.
* O segmento e o namespace escolhidos em **Qualificação de segmento** (primeiro nó) não podem ser alterados em novas versões.
* A regra de reentrada precisa ser a mesma em todas as versões da jornada.

## Qualificação do segmento {#segment-qualification}

* A atividade de **Qualificação de segmento** não pode ser usada em conjunto com o Adobe Campaign Standard Transactional Messaging devido a restrições de taxa de transferência. Consulte a [Descrição do produto Adobe Campaign Standard](https://helpx.adobe.com/br/legal/product-descriptions/campaign-standard.html). 
 

## Limitações de ações personalizadas

* O URL de ação personalizada não aceita parâmetros dinâmicos. 
* Somente os métodos de chamada POST e PUT são compatíveis. 
* O nome do parâmetro de consulta ou cabeçalho não deve começar com “.” ou &quot;$&quot;. 
* Endereços IP não são permitidos. 
* Endereços Adobe internos (.adobe.) não são permitidos.
 

## Limitações de ações do Adobe Campaign

* As mensagens transacionais do Adobe Campaign Standard têm uma escala de no máximo 50.000 mensagens por hora entre canais para uma determinada instância. Consulte a [Descrição do produto Adobe Campaign Standard](https://helpx.adobe.com/br/legal/product-descriptions/campaign-standard.html). 
 

## Limitações de eventos

* Para eventos gerados pelo sistema, os dados de transmissão usados para iniciar uma jornada do cliente devem ser configurados no Journey Orchestration primeiro para obter uma ID de orquestração exclusiva. Essa ID de orquestração deve ser anexada ao conteúdo de transmissão que entra no Adobe Experience Platform. Essa limitação não se aplica a eventos com base em regras.
 

## Limitações das fontes de dados

* As fontes de dados externas podem ser aproveitadas em uma jornada do cliente para pesquisar dados externos em tempo real. Essas fontes devem ser utilizáveis por meio da API REST, devem ser compatíveis com JSON e poder lidar com o volume de solicitações.

## Jornadas que começam ao mesmo tempo que a criação de um perfil {#journeys-limitation-profile-creation}

Há um atraso associado à criação/atualização de perfil com base em API na Adobe Experience Platform. O Service Level Target (SLT) em termos de latência é &lt; 1 min desde a ingestão até o Perfil unificado, por 95% das solicitações, em um volume de 20 mil solicitações por segundo (RPS).

Se uma Jornada for acionada simultaneamente à criação de um perfil e verificar/recuperar imediatamente as informações do Serviço de perfil, ela pode não funcionar corretamente.

Você pode escolher uma dessas duas soluções:

* Adicione uma atividade de espera depois do primeiro evento para conceder à Adobe Experience Platform o tempo necessário para executar a ingestão no Serviço de Perfil.

* Configure uma jornada que não use o perfil imediatamente. Por exemplo, se a jornada for projetada para confirmar a criação de uma conta, o evento da experiência pode conter informações necessárias para enviar a primeira mensagem de confirmação (nome, sobrenome, endereço de email etc).
