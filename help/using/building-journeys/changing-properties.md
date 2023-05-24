---
product: adobe campaign
title: Alterar propriedades
description: Saiba como alterar propriedades
feature: Journeys
role: User
level: Intermediate
exl-id: 06d26078-b9b8-4dc4-918d-0f2426d00f54
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '543'
ht-degree: 1%

---

# Alterar propriedades {#concept_prq_wqt_52b}

Clique no ícone de lápis, na parte superior direita, para acessar as propriedades da jornada.

É possível alterar o nome da jornada, adicionar uma descrição, permitir a reentrada, escolher datas de início e término e definir um **[!UICONTROL Timeout and error]** duração se você for administrador.

Para jornadas ao vivo, essa tela exibe a data da publicação e o nome do usuário que publicou a jornada.

A variável **Copiar detalhes técnicos** O permite copiar informações técnicas sobre a jornada que a equipe de suporte pode usar para a solução de problemas. As seguintes informações são copiadas: JourneyVersion UID, OrgID, orgName, sandboxName, lastDeployedBy, lastDeployedAt.

![](../assets/journey32.png)

## Entrada{#entrance}

Por padrão, novas jornadas permitem a reentrada. Você pode desmarcar a opção para jornadas &quot;one shot&quot;, por exemplo, se quiser oferecer um presente único quando uma pessoa entrar em uma loja. Nesse caso, você não deseja que o cliente entre novamente na jornada e receba a oferta novamente.

Quando uma jornada &quot;termina&quot;, ela terá o status **[!UICONTROL Closed (no entrance)]**. A jornada deixará de permitir que novos indivíduos entrem na jornada. As pessoas que já estão na jornada terminarão a jornada normalmente.

Após o tempo limite global padrão de 30 dias, a jornada será alternada para a variável **Concluído** status. Consulte esta [seção](#global_timeout).

## Tempo limite e erro em atividades de jornada {#timeout_and_error}

Ao editar uma atividade de ação ou condição, é possível definir um caminho alternativo em caso de erro ou tempo limite. Se o processamento da atividade que interroga um sistema de terceiros exceder a duração do tempo limite definida nas propriedades da jornada (**[!UICONTROL Timeout and  error]** ), o segundo caminho será escolhido para executar uma possível ação de fallback.

Os valores autorizados estão entre 1 e 30 segundos.

Recomendamos que você defina um período muito curto **[!UICONTROL Timeout and error]** valor se a jornada for sensível ao tempo (por exemplo: reagir ao local em tempo real de uma pessoa) porque você não pode atrasar a ação por mais de alguns segundos. Se a jornada for menos sensível ao tempo, você poderá usar um valor mais longo para dar mais tempo ao sistema chamado para enviar uma resposta válida.

[!DNL Journey Orchestration] também usa um tempo limite global. Consulte a [próxima seção](#global_timeout).

## Tempo limite de jornada global {#global_timeout}

Além do [timeout](#timeout_and_error) usado em atividades de jornada, também há um tempo limite de jornada global que não é exibido na interface e não pode ser alterado. Esse tempo limite interromperá o progresso das pessoas físicas na jornada 30 dias após a sua entrada. Isso significa que a jornada de um indivíduo não pode durar mais de 30 dias. Após o período de tempo limite de 30 dias, os dados do indivíduo são excluídos. As pessoas que ainda fluem na jornada no final do período de tempo limite serão interrompidas e serão consideradas como erros no relatório.

>[!NOTE]
>
>[!DNL Journey Orchestration] O não reage diretamente a solicitações de recusa, acesso ou exclusão de privacidade. No entanto, o tempo limite global garante que os indivíduos nunca fiquem mais de 30 dias em qualquer jornada.

Devido ao tempo limite de jornada de 30 dias, quando a reentrada da jornada não é permitida, não podemos garantir que o bloqueio de reentrada funcionará por mais de 30 dias. Na verdade, à medida que removemos todas as informações sobre as pessoas que entraram na jornada 30 dias depois de entrarem, não podemos saber a pessoa inserida anteriormente, há mais de 30 dias.

## Fuso horário e fuso horário do perfil {#timezone}

Os fusos horários são definidos no nível da jornada.

Você pode inserir um fuso horário fixo ou usar perfis do Adobe Experience Platform para definir o fuso horário de jornada.

Para obter mais informações sobre o gerenciamento de fuso horário, consulte [esta página](../building-journeys/timezone-management.md).
