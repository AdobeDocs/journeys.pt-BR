---
product: adobe campaign
title: Mudar de uma jornada para outra
description: Mudar de uma jornada para outra
feature: Journeys
role: User
level: Intermediate
exl-id: 520376aa-2cb5-46d6-8f21-3e03544f5da1
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '791'
ht-degree: 4%

---

# Mudar de uma jornada para outra {#jump}

O **[!UICONTROL Jump]** A atividade de ação permite enviar indivíduos de uma jornada para outra. Esse recurso permite:

* simplificar o design de jornadas muito complexas dividindo-as em várias
* criar jornadas com base em padrões de jornada comuns e reutilizáveis

Na jornada de origem, basta adicionar um **[!UICONTROL Jump]** e selecione uma jornada do target. Quando o indivíduo entra no **[!UICONTROL Jump]** , um evento interno é enviado para o primeiro evento da jornada de destino. Se a variável **[!UICONTROL Jump]** Se a ação for bem sucedida, o indivíduo continuará a progredir na jornada. O comportamento é semelhante a outras ações.

Na jornada do target, o primeiro evento acionado internamente pela variável **[!UICONTROL Jump]** A atividade fará com que o fluxo individual na jornada.

>[!NOTE]
>
>Consulte também o vídeo tutorial [here](https://experienceleague.adobe.com/docs/journey-orchestration-learn/tutorials/building-a-journey/jumping-to-another-journey.html?lang=pt-BR)

## Vida útil

Digamos que você adicionou um **[!UICONTROL Jump]** atividade em uma jornada A para uma jornada B. A Jornada A é a variável **jornada de origem** e jornada B, a **jornada do target**.
Estas são as diferentes etapas do processo de execução:

**Jornada A** é acionado de um evento externo:

1. A jornada A recebe um evento externo relacionado a um indivíduo.
1. O indivíduo alcança o **[!UICONTROL Jump]** etapa.
1. O indivíduo é empurrado para a Jornada B e avança para as próximas etapas na Jornada A, após a **[!UICONTROL Jump]** etapa.

Na jornada B, o primeiro evento é acionado internamente, por meio da variável **[!UICONTROL Jump]** atividade da jornada A:

1. A jornada B recebeu um evento interno da Jornada A.
1. O indivíduo começa a fluir na Jornada B.

>[!NOTE]
>
>A jornada B também pode ser acionada por meio de um evento externo.

## Práticas recomendadas e limitações

### Criação

* O **[!UICONTROL Jump]** A atividade só está disponível em jornadas que usam um namespace.
* Você só pode ir para uma jornada que usa o mesmo namespace que a jornada de origem.
* Não é possível pular para uma jornada que começa com uma **Qualificação do segmento** evento.
* Não é possível ter um **[!UICONTROL Jump]** e uma **Qualificação do segmento** na mesma jornada.
* É possível incluir quantas **[!UICONTROL Jump]** atividades conforme necessário em uma jornada. Depois de um **[!UICONTROL Jump]**, é possível adicionar qualquer atividade necessária.
* Você pode ter quantos níveis de salto forem necessários. Por exemplo, a Jornada A vai para a jornada B, que vai para a jornada C e assim por diante.
* A jornada de destino também pode incluir quantas **[!UICONTROL Jump]** conforme necessário.
* Os padrões de loop não são suportados. Não há como vincular duas ou mais jornadas que criariam um loop infinito. O **[!UICONTROL Jump]** a tela de configuração de atividade impede que você faça isso.

### Execução

* Quando a variável **[!UICONTROL Jump]** for executada, a versão mais recente da jornada de destino será acionada.
* Como de costume, um indivíduo único só pode estar presente uma vez em uma mesma jornada. Como resultado, se o indivíduo enviado da jornada de origem já estiver na jornada de destino, o indivíduo não entrará na jornada de destino. Nenhum erro será relatado na variável **[!UICONTROL Jump]** atividade porque esse é um comportamento normal.

## Configuração da atividade Jump

1. Crie seu **jornada de origem**.

   ![](../assets/jump1.png)

1. Em qualquer etapa da jornada, adicione um **[!UICONTROL Jump]** da **[!UICONTROL ACTIONS]** categoria . Adicione um rótulo e uma descrição.

   ![](../assets/jump2.png)

1. Clique dentro do **Jornada do Target** campo.
A lista exibe todas as versões de jornada que são rascunho, ativo ou em modo de teste. Jornadas que usam um namespace diferente ou que começam com um **Qualificação do segmento** não estão disponíveis. Jornadas do Target que criariam um padrão de loop também são filtradas.

   ![](../assets/jump3.png)

   >[!NOTE]
   >
   >Você pode clicar no botão **Abrir jornada de destino** no lado direito, para abrir a jornada de destino em uma nova guia.

1. Selecione a jornada de destino para a qual você deseja ir.
O **Primeiro evento** O campo é preenchido com o nome do primeiro evento da jornada de destino. Se a jornada de destino incluir vários eventos, a variável **[!UICONTROL Jump]** é permitido somente no primeiro evento.

   ![](../assets/jump4.png)

1. O **Parâmetros de ação** exibe todos os campos do evento de destino. Da mesma forma que para outros tipos de ações, mapeie cada campo com campos do evento de origem ou fonte de dados. Essas informações serão passadas para a jornada de destino no tempo de execução.
1. Adicione as próximas atividades para finalizar a jornada de origem.

   ![](../assets/jump5.png)


   >[!NOTE]
   >
   >A identidade do indivíduo é mapeada automaticamente. Essas informações não estão visíveis na interface.

Seu **[!UICONTROL Jump]** está configurada. Assim que sua jornada estiver no modo de teste ou estiver no modo de teste, os indivíduos que atingem o **[!UICONTROL Jump]** será enviado do para a jornada de destino.

Quando uma **[!UICONTROL Jump]** está configurada em uma jornada, uma **[!UICONTROL Jump]** o ícone de entrada é adicionado automaticamente no início da jornada de destino. Isso ajuda a identificar que a jornada pode ser acionada externamente, mas também internamente, a partir de uma **[!UICONTROL Jump]** atividade .

![](../assets/jump7.png)

## Solução de problemas

Quando a jornada é publicada ou no modo de teste, os erros acontecerão se:
* a jornada de destino não existe mais
* a jornada do target é rascunho, fechada ou interrompida
* se o primeiro evento da jornada de destino tiver sido alterado e o mapeamento estiver quebrado

![](../assets/jump6.png)
