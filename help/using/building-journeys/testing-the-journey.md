---
product: adobe campaign
title: Testar a jornada
description: Saiba mais sobre o teste do jornada
feature: Journeys
role: User
level: Intermediate
exl-id: be413905-0631-4229-a954-80a92651206d
source-git-commit: 052ecdeb0813dcc2c4c870e8ec6b12676fbf60f1
workflow-type: tm+mt
source-wordcount: '1576'
ht-degree: 7%

---

# Testar a jornada{#testing_the_journey}

Antes de poder testar sua jornada, você deve resolver todos os erros, se houver. Consulte [esta seção](../about/troubleshooting.md#section_h3q_kqk_fhb).

É possível testar sua jornada antes de sua publicação, usando perfis de teste. Isso permite analisar como as pessoas fluem na jornada e solucionam problemas antes da publicação.

Somente perfis de teste podem entrar em uma jornada no modo de teste. Você pode criar um novo perfil de teste ou transformar um perfil existente em um perfil de teste. Consulte esta [seção](../building-journeys/creating-test-profiles.md).

Para usar o modo de teste, siga estas etapas:

1. Antes de testar a jornada, verifique se ela é válida e se não há erros. Você não poderá iniciar um teste de uma jornada com erros. Consulte [esta seção](../about/troubleshooting.md#section_h3q_kqk_fhb). Um símbolo de aviso é exibido quando há erros.

1. Para ativar o modo de teste, clique no link **[!UICONTROL Test]** switch, localizado no canto superior direito.

   ![](../assets/journeytest1.png)

1. Use o **[!UICONTROL Wait time]** no canto inferior esquerdo, para definir o tempo que cada atividade de espera e timeout de evento durarão no modo de teste. O tempo padrão é de 10 segundos para esperas e tempos limite de evento. Isso garantirá que você obtenha os resultados do teste rapidamente. Esse parâmetro só aparecerá se você tiver ignorado uma ou mais atividades de espera na jornada.

   ![](../assets/journeytest_wait.png)

   >[!NOTE]
   >
   >Quando um evento de reação com um tempo limite é usado em uma jornada, o valor padrão e mínimo do tempo de espera é de 40 segundos. Consulte [esta seção](../building-journeys/reaction-events.md).

1. Clique em **[!UICONTROL Trigger an event]** para configurar e enviar eventos à jornada.

   ![](../assets/journeyuctest1.png)

1. Configure os diferentes campos esperados. No **Identificador de perfil** insira o valor do campo usado para identificar o perfil de teste. Pode ser o endereço de email, por exemplo. Envie eventos relacionados a perfis de teste. Consulte [Disparando eventos](#firing_events).

   ![](../assets/journeyuctest1-bis.png)

1. Depois que os eventos forem recebidos, clique no link **[!UICONTROL Show log]** botão para ver o resultado do teste e verificá-los. Consulte [Visualização dos logs](#viewing_logs).

   ![](../assets/journeyuctest2.png)

1. Se houver algum erro, desative o modo de teste, modifique sua jornada e teste novamente. Quando o teste for conclusivo, você pode publicar sua jornada. Consulte [esta página](../building-journeys/publishing-the-journey.md).

## Observações importantes {#important_notes}

* Uma interface é fornecida para acionar eventos para a jornada testada, mas os eventos também podem ser enviados por sistemas de terceiros, como o Postman.
* Somente indivíduos sinalizados como &quot;perfis de teste&quot; no Serviço de perfil do cliente em tempo real poderão entrar na jornada testada. Consulte esta [seção](../building-journeys/creating-test-profiles.md).
* O modo de teste só está disponível em jornadas de rascunho que usam um namespace. O modo de teste precisa verificar se uma pessoa que entra na jornada é um perfil de teste ou não e, portanto, deve ser capaz de acessar o Adobe Experience Platform.
* O número máximo de perfis de teste que podem inserir uma jornada durante uma sessão de teste é 100.
* Quando você desativa o modo de teste, ele esvazia as jornadas de todas as pessoas que entraram anteriormente ou que estão atualmente nele. Também apaga os relatórios.
* Você pode ativar/desativar o modo de teste quantas vezes forem necessárias.
* Não é possível modificar a jornada quando o modo de teste está ativado. Quando estiver no modo de teste, você poderá publicar a jornada diretamente; não é necessário desativar o modo de teste antes de.
* Ao atingir uma divisão, a ramificação superior é sempre escolhida. É possível reorganizar a posição das ramificações de divisão se quiser que o teste escolha um caminho diferente.
* Para otimizar o desempenho e evitar o uso de recursos obsoletos, todas as jornadas no modo de teste que não forem acionadas por uma semana retornarão para o status Rascunho.

## Transformar um perfil em um perfil de teste{#turning-profile-into-test}

Você pode transformar um perfil existente em um perfil de teste. No Adobe Experience Platform, você pode atualizar atributos de perfis por meio de chamadas de API, mas não pode ser executado por meio da interface.

A maneira mais fácil de fazer isso é usando um **Atualizar perfil** atividade de ação e alterar o campo booleano do perfil de teste de falso para verdadeiro. Consulte [esta seção](../building-journeys/update-profiles.md#using-the-test-mode).

## Criação de um perfil de teste{#create-test-profile}

Se quiser criar um novo perfil de teste, o procedimento será o mesmo de criar um perfil no Adobe Experience Platform. Ele é executado por meio de chamadas de API. Consulte esta [página](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=pt-BR)

Você deve usar um esquema de Perfil que contenha a combinação &quot;detalhes do teste de perfil&quot;. O sinalizador testProfile faz parte deste mixin.

Ao criar um perfil, passe o valor: testProfile = true.

Observe que você também pode atualizar um perfil existente para alterar seu sinalizador testProfile para &quot;true&quot;.

Este é um exemplo de uma chamada de API para criar um perfil de teste:

```
curl -X POST \
'https://dcs.adobedc.net/collection/xxxxxxxxxxxxxx' \
-H 'Cache-Control: no-cache' \
-H 'Content-Type: application/json' \
-H 'Postman-Token: xxxxx' \
-H 'cache-control: no-cache' \
-H 'x-api-key: xxxxx' \
-H 'x-gw-ims-org-id: xxxxx' \
-d '{
"header": {
"msgType": "xdmEntityCreate",
"msgId": "xxxxx",
"msgVersion": "xxxxx",
"xactionid":"xxxxx",
"datasetId": "xxxxx",
"imsOrgId": "xxxxx",
"source": {
"name": "Postman"
},
"schemaRef": {
"id": "https://example.adobe.com/mobile/schemas/xxxxx",
"contentType": "application/vnd.adobe.xed-full+json;version=1"
}
},
"body": {
"xdmMeta": {
"schemaRef": {
"contentType": "application/vnd.adobe.xed-full+json;version=1"
}
},
"xdmEntity": {
"_id": "xxxxx",
"_mobile":{
"ECID": "xxxxx"
},
"testProfile":true
}
}
}'
```

## Disparando eventos {#firing_events}

A variável **[!UICONTROL Trigger an event]** permite configurar um evento que fará com que uma pessoa entre na jornada.

>[!NOTE]
>
>Quando você aciona um evento no modo de teste, um evento real é gerado, o que significa que ele também atingirá outras jornadas que ouvem esse evento.

Como pré-requisito, você deve saber quais perfis são sinalizados como perfis de teste no Adobe Experience Platform. Na verdade, o modo de teste permite apenas esses perfis na jornada e o evento deve conter uma ID. A ID esperada depende da configuração do evento. Pode ser uma ECID ou um endereço de email, por exemplo. O valor dessa chave precisa ser adicionado na variável **Identificador de perfil** campo.

>[!NOTE]
>
>Uma lista suspensa é exibida para campos que esperam uma enumeração. Basta selecionar um dos valores disponíveis.

Se a jornada contiver vários eventos, use a lista suspensa para selecionar um evento. Em seguida, para cada evento, configure os campos transmitidos e a execução do envio do evento. A interface ajuda você a passar as informações corretas na carga do evento e garantir que o tipo de informação esteja correto. O modo de teste salva os últimos parâmetros usados em uma sessão de teste para uso posterior.

![](../assets/journeytest4.png)

A interface permite transmitir parâmetros de evento simples. Se quiser passar coleções ou outros objetos avançados no evento, clique em **[!UICONTROL Code View]** para ver todo o código da carga útil e modificá-lo. Por exemplo, você pode copiar e colar informações de evento preparadas por um usuário técnico.

![](../assets/journeytest5.png)

Um usuário técnico também pode usar essa interface para compor cargas de evento e acionar eventos sem precisar usar uma ferramenta de terceiros.

Ao clicar no link **[!UICONTROL Send]** botão, o teste é iniciado. A progressão do indivíduo na jornada é representada por um fluxo visual. O caminho torna-se progressivamente verde à medida que o indivíduo se move pela jornada. Se ocorrer um erro, um símbolo de aviso será exibido na etapa correspondente. Você pode colocar o cursor nele para exibir mais informações sobre o erro e acessar detalhes completos (quando disponíveis).

![](../assets/journeytest6.png)

Quando você seleciona um perfil de teste diferente na tela de configuração do evento e executa o teste novamente, o fluxo visual é limpo e mostra o caminho do novo indivíduo.

Ao abrir uma jornada no teste, o caminho exibido corresponde ao último teste executado.

O fluxo visual funciona independentemente de o evento ser acionado por meio da interface ou externamente (usando o Postman, por exemplo).

## Modo de teste para jornadas baseadas em regras {#test-rule-based}

O modo de teste também está disponível para jornadas que usam um evento com base em regras. Para obter mais informações sobre eventos baseados em regras, consulte [esta página](../event/about-events.md).

Ao acionar um evento, a variável **Configuração do evento** permite definir os parâmetros de evento que serão aprovados no teste. Você pode visualizar a condição da ID de evento clicando no ícone de dica de ferramenta no canto superior direito. Uma dica de ferramenta também está disponível ao lado de cada campo que faz parte da avaliação da regra.

![](../assets/alpha-event8.png)

Para obter mais informações sobre como usar o modo de teste, consulte [esta página](../building-journeys/testing-the-journey.md).

## Visualização dos logs {#viewing_logs}

A variável **[!UICONTROL Show log]** permite visualizar os resultados do teste. Esta página exibe as informações atuais da jornada no formato JSON. Um botão permite copiar nós inteiros. É necessário atualizar manualmente a página para atualizar os resultados do teste da jornada.

![](../assets/journeytest3.png)

>[!NOTE]
>
>Nos logs de teste, em caso de erro ao chamar um sistema de terceiros (fonte de dados ou ação), o código de erro e a resposta do erro são exibidos.

O número de indivíduos (tecnicamente chamados de instâncias) atualmente dentro da jornada é exibido. Estas são informações úteis exibidas para cada indivíduo:

* _ID_: a ID interna do indivíduo na jornada. Ele pode ser usado para fins de depuração.
* _currentstep_: a etapa em que o indivíduo está na jornada. Recomendamos adicionar rótulos às suas atividades para identificá-las mais facilmente.
* _currentstep_ >: o status da jornada do indivíduo (em execução, concluída, com erro ou tempo limite). Veja mais informações abaixo.
* _currentstep_ > _extraInfo_: descrição do erro e outras informações contextuais.
* _currentstep_ > _fetchErrors_: informações sobre erros de busca de dados que ocorreram durante essa etapa.
* _externalKeys_: o valor da fórmula principal definida no evento.
* _enrichedData_: os dados que a jornada jornada recuperou se ela usar fontes de dados.
* _transitionHistory_: a lista de etapas seguidas pelo indivíduo. Para eventos, a carga é exibida.
* _actionExecutionErrors_ : informações sobre os erros que ocorreram.

Estes são os diferentes status da jornada de um indivíduo:

* _Executando_: o indivíduo está atualmente na jornada.
* _Concluído_: o indivíduo está no final da jornada.
* _Erro_: o indivíduo é interrompido na jornada devido a um erro.
* _Tempo esgotado_: o indivíduo é interrompido na jornada devido a uma etapa que demorou muito.

Quando um evento é acionado usando o modo de teste, um conjunto de dados é gerado automaticamente com o nome da origem.

Quando um evento é acionado usando o modo de teste, um conjunto de dados é gerado automaticamente com o nome da origem.

O modo de teste cria automaticamente um Evento de experiência e o envia para a Adobe Experience Platform. O nome da origem deste evento de experiência é &quot;Journey Orchestration Eventos de teste&quot;.
