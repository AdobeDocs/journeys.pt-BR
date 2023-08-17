---
product: adobe campaign
solution: Journey Orchestration
title: Integração com sistemas externos
description: Conheça as práticas recomendadas ao integrar sistemas externos
feature: Journeys
role: User
level: Beginner
exl-id: e39218bd-fa6e-443f-9843-92b7a07070fa
source-git-commit: a9a129b1949d64c4a412d3ea4002b32e3563ea96
workflow-type: tm+mt
source-wordcount: '1014'
ht-degree: 6%

---

# Integração com sistemas externos {#external-systems}

Esta página apresenta as diferentes medidas de proteção fornecidas pelo Journey Orchestration ao integrar um sistema externo, bem como as práticas recomendadas: como otimizar a proteção do sistema externo usando a API de limite, como configurar o tempo limite da jornada e como as tentativas funcionam.

O Journey Orchestration permite configurar conexões com sistemas externos por meio de fontes de dados personalizadas e ações personalizadas. Isso permite, por exemplo, enriquecer suas jornadas com dados provenientes de um sistema de reservas externo ou enviar mensagens usando um sistema de terceiros, como Epsilon ou Facebook.

Ao integrar um sistema externo, você pode encontrar vários problemas, o sistema pode ficar lento, pode parar de responder ou pode não ser capaz de lidar com um grande volume. O Journey Orchestration oferece várias medidas de proteção para proteger seu sistema contra sobrecarga.

Todos os sistemas externos são diferentes em termos de desempenho. Você precisa adaptar a configuração aos seus casos de uso.

Quando o Journey Orchestration executa uma chamada para uma API externa, as medidas de proteção técnica são executadas da seguinte maneira:

1. As regras de limitação são aplicadas: se a taxa máxima for atingida, as chamadas restantes serão descartadas.

2. Timeout and retry: se a regra de limitação for atendida, o Journey Orchestration tentará executar a chamada até que o final da duração do tempo limite seja atingido.

## Limite{#capping}

A API de limite integrada oferece uma proteção técnica de upstream que ajuda a proteger seu sistema externo.

Para fontes de dados externas, o número máximo de chamadas por segundo é definido como 15. Se o número de chamadas exceder 15 por segundo, as chamadas restantes serão descartadas. É possível aumentar esse limite para fontes de dados externas privadas. Entre em contato com o Adobe para incluir o endpoint no incluo na lista de permissões. Isso não é possível para fontes de dados externas públicas.

Para ações personalizadas, é necessário avaliar a capacidade de sua API externa. Por exemplo, se o Journey Optimizer enviar 1000 chamadas por segundo e seu sistema suportar apenas 100 chamadas por segundo, será necessário definir uma regra de limitação para que seu sistema não fique saturado.

As regras de limite são definidas no nível da sandbox para um endpoint específico (o URL chamado). No tempo de execução, o Journey Orchestration verifica se há uma regra de limitação definida e aplica a taxa definida durante as chamadas para esse endpoint. Se o número de chamadas exceder a taxa definida, as chamadas restantes serão descartadas e contadas como erros no relatório.

Uma regra de limitação é específica para um endpoint, mas global para todas as jornadas de uma sandbox. Isso significa que os slots de limite são compartilhados entre todas as jornadas de uma sandbox.

Por exemplo, digamos que você tenha definido uma regra de limitação de 100 chamadas por segundo para o sistema externo. Seu sistema é chamado por uma ação personalizada em 10 jornadas diferentes. Se uma jornada receber 200 chamadas por segundo, ela usará os 100 slots disponíveis e descartará os 100 slots restantes. Como a taxa máxima foi excedida, não restará nenhum slot para as outras 9 jornadas. Essa granularidade ajuda a proteger o sistema externo contra sobrecarga e falhas.

Para saber mais sobre a API de limitação e como configurar regras de limitação, consulte [esta página](../api/capping.md).

## Tempo limite e tentativas{#timeout}

Se a regra de limite for atendida, a regra de tempo limite será aplicada.

Em cada jornada, é possível definir uma duração de tempo limite. Isso permite definir uma duração máxima ao chamar um sistema externo. A duração do tempo limite é configurada nas propriedades de uma jornada. Consulte [esta página](../building-journeys/changing-properties.md#timeout_and_error).

Esse tempo limite é global para todas as chamadas externas (chamadas de API externas em ações personalizadas e fontes de dados personalizadas). Por padrão, é definido como 5 segundos.

Durante o tempo limite definido, o Journey Orchestration tenta chamar o sistema externo. Após a primeira chamada, um máximo de três tentativas pode ser executado até que a duração do tempo limite seja atingida. O número de tentativas não pode ser alterado.

Cada tentativa usa um slot. Se você tiver um limite de 100 chamadas por segundo e cada uma das chamadas exigir duas tentativas, a taxa cai para 30 chamadas por segundo (cada chamada usa 3 slots: a primeira chamada e duas tentativas).

O valor de duração do tempo limite depende do caso de uso. Se você quiser enviar a mensagem rapidamente, por exemplo, quando o cliente entrar na loja, não desejará configurar um tempo limite longo. Além disso, quanto maior for o tempo limite, mais itens serão colocados na fila. Isso pode afetar muito o desempenho. Se o Journey Orchestration executar 1000 chamadas por segundo, manter 5 ou 15 segundos de dados pode sobrecarregar rapidamente o sistema.

Vamos ver um exemplo para um tempo limite de 5 segundos.

* A primeira chamada dura menos de 5 segundos: a chamada é bem-sucedida, não há nova tentativa.
* A primeira chamada dura mais de 5 segundos: a chamada é cancelada e não há nenhuma tentativa. É contado como um erro de tempo limite no relatório.
* A primeira chamada falha após 2 segundos (o sistema externo retorna um erro): restam 3 segundos para tentativas, se os slots de limite estiverem disponíveis.
   * Se uma das três tentativas for bem-sucedida antes do final dos 5 segundos, a chamada será executada e não haverá erro.
   * Se o fim da duração do tempo limite for atingido durante as tentativas, a chamada será cancelada e contada como um erro de tempo limite no relatório.

## Perguntas frequentes{#faq}

**Como posso configurar uma regra de limitação? Há uma regra de limitação padrão?**

Por padrão, não há regra de limitação. As regras de limitação são definidas no nível da sandbox para um endpoint específico (o URL chamado), usando a API de limitação. Consulte [nesta seção](../about/external-systems.md#capping) e [esta página](../api/capping.md).

**Quantas tentativas são executadas? Posso alterar o número de tentativas ou definir um período mínimo de espera entre tentativas?**

Para uma determinada chamada, um máximo de três tentativas pode ser executado após a primeira chamada, até que a duração do tempo limite seja atingida. O número de tentativas e o tempo entre cada nova tentativa não podem ser alterados. Consulte [esta seção](../about/external-systems.md#timeout).

**Onde posso configurar o tempo limite? Há um valor máximo?**

Em cada jornada, é possível definir uma duração de tempo limite. A duração do tempo limite é configurada nas propriedades de uma jornada. A duração do tempo limite deve estar entre 1 segundo e 30 segundos. Consulte [nesta seção](../about/external-systems.md#timeout) e [esta página](../building-journeys/changing-properties.md#timeout_and_error).
