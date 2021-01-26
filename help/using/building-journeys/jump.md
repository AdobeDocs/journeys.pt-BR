---
product: adobe campaign
solution: Journey Orchestration
title: Mudar de uma jornada para outra
description: Mudar de uma jornada para outra
translation-type: tm+mt
source-git-commit: 9d8c3a2cf79f2b861aad61089a263a6a33a747b4
workflow-type: tm+mt
source-wordcount: '791'
ht-degree: 3%

---


# Mudar de uma jornada para outra {#jump}

A atividade de ação **[!UICONTROL Jump]** permite que você empurre indivíduos de uma jornada para outra. Este recurso permite:

* simplifique o design de jornadas muito complexas dividindo-as em várias
* criar jornadas com base em padrões de jornada comuns e reutilizáveis

Na jornada da origem, basta adicionar uma atividade **[!UICONTROL Jump]** e selecionar uma jornada de público alvo. Quando o indivíduo entra na etapa **[!UICONTROL Jump]**, um evento interno é enviado para o primeiro evento da jornada do público alvo. Se a ação **[!UICONTROL Jump]** for bem-sucedida, o indivíduo continuará a progredir na jornada. O comportamento é semelhante a outras ações.

Na jornada do público alvo, o primeiro evento acionado internamente pela atividade **[!UICONTROL Jump]** fará com que o fluxo individual na jornada.

>[!NOTE]
>
>Consulte também o vídeo tutorial [here](https://experienceleague.adobe.com/docs/journey-orchestration-learn/tutorials/building-a-journey/jumping-to-another-journey.html)

## Ciclo

Digamos que você tenha adicionado uma atividade **[!UICONTROL Jump]** em uma jornada A à jornada B. A jornada A é a **jornada de origem** e a jornada B, a jornada **público alvo**.
Estas são as diferentes etapas do processo de execução:

**Jornada** acionada a partir de um evento externo:

1. A jornada A recebe um evento externo relacionado a um indivíduo.
1. O indivíduo atinge a etapa **[!UICONTROL Jump]**.
1. O indivíduo é empurrado para a Jornada B e avança para as próximas etapas na Jornada A, após a etapa **[!UICONTROL Jump]**.

Na jornada B, o primeiro evento é acionado internamente, por meio da atividade **[!UICONTROL Jump]** da jornada A:

1. A jornada B recebeu um evento interno da Jornada A.
1. Os start individuais que fluem na Jornada B.

>[!NOTE]
>
>A jornada B também pode ser acionada por meio de um evento externo.

## Práticas recomendadas e limitações

### Criação

* A atividade **[!UICONTROL Jump]** só está disponível no jornada que usa uma namespace.
* Você só pode pular para uma jornada que use a mesma namespace que a jornada da origem.
* Não é possível pular para uma jornada que start com um evento **Qualificação de segmento**.
* Não é possível ter uma atividade **[!UICONTROL Jump]** e um evento **Qualificação de segmento** na mesma jornada.
* Você pode incluir quantas atividades **[!UICONTROL Jump]** forem necessárias em uma jornada. Depois de um **[!UICONTROL Jump]**, você pode adicionar qualquer atividade necessária.
* Você pode ter quantos níveis de salto forem necessários. Por exemplo, a Jornada A vai para a jornada B, que vai para a jornada C e assim por diante.
* A jornada do público alvo também pode incluir quantas atividades **[!UICONTROL Jump]** forem necessárias.
* Os padrões de loop não são suportados. Não há como vincular duas ou mais jornadas que criariam um ciclo infinito. A tela de configuração da atividade **[!UICONTROL Jump]** impede que você faça isso.

### Execução

* Quando a atividade **[!UICONTROL Jump]** é executada, a versão mais recente da jornada do público alvo é acionada.
* Como de costume, um indivíduo único só pode estar presente uma vez na mesma jornada. Como resultado, se o indivíduo empurrado da jornada da origem já estiver na jornada da público alvo, ele não entrará na jornada da público alvo. Nenhum erro será relatado na atividade **[!UICONTROL Jump]** porque esse comportamento é normal.

## Configuração da atividade de salto

1. Projete sua jornada **origem**.

   ![](../assets/jump1.png)

1. Em qualquer etapa da jornada, adicione uma atividade **[!UICONTROL Jump]** da categoria **[!UICONTROL ACTIONS]**. Adicione um rótulo e uma descrição.

   ![](../assets/jump2.png)

1. Clique dentro do campo **jornada do Público alvo**.
A lista exibe todas as versões de jornada que estão em modo de rascunho, ao vivo ou de teste. Jornadas que usam uma namespace diferente ou esse start com um evento **Qualificação de segmento** não estão disponíveis. Jornadas de público alvo que criariam um padrão de loop também são filtradas.

   ![](../assets/jump3.png)

   >[!NOTE]
   >
   >Você pode clicar no ícone **Abrir jornada do público alvo**, no lado direito, para abrir a jornada do público alvo em uma nova guia.

1. Selecione a jornada do público alvo para a qual você deseja pular.
O campo **Primeiro evento** é pré-preenchido com o nome do primeiro evento do jornada do público alvo. Se sua jornada de público alvo incluir vários eventos, o **[!UICONTROL Jump]** só será permitido no primeiro evento.

   ![](../assets/jump4.png)

1. A seção **Parâmetros de ação** exibe todos os campos do evento do público alvo. Da mesma forma que para outros tipos de ações, mapeie cada campo com campos do evento de origem ou fonte de dados. Essas informações serão passadas para a jornada do público alvo no tempo de execução.
1. Adicione as próximas atividades para concluir a jornada da origem.

   ![](../assets/jump5.png)


   >[!NOTE]
   >
   >A identidade do indivíduo é automaticamente mapeada. Essas informações não estão visíveis na interface.

Sua atividade **[!UICONTROL Jump]** está configurada. Assim que sua jornada estiver ativa ou no modo de teste, os indivíduos que atingirem a etapa **[!UICONTROL Jump]** serão encaminhados de para a jornada do público alvo.

Quando uma atividade **[!UICONTROL Jump]** é configurada em uma jornada, um ícone de entrada **[!UICONTROL Jump]** é adicionado automaticamente no início da jornada do público alvo. Isso ajuda a identificar que a jornada pode ser acionada externamente, mas também internamente, a partir de uma atividade **[!UICONTROL Jump]**.

![](../assets/jump7.png)

## Solução de problemas

Quando a jornada é publicada ou no modo de teste, os erros ocorrerão se:
* a jornada do público alvo não existe mais
* a jornada do público alvo está em rascunho, fechada ou parada
* se o primeiro evento da jornada do público alvo tiver sido alterado e o mapeamento estiver quebrado

![](../assets/jump6.png)
