---
product: adobe campaign
title: Solução de problemas
description: Saiba mais sobre solução de problemas
feature: Journeys
role: User
level: Intermediate
exl-id: c678ba01-c868-49f2-99f3-1abe0302779e
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '1038'
ht-degree: 97%

---

# Solução de problemas{#concept_nlv_bcv_2fb}

Nesta seção, você descobrirá como solucionar problemas de jornadas antes de testar ou publicar. Todos os controles enumerados a seguir podem ser efetuados quando a jornada estiver em modo de teste ou mesmo ativa. Recomenda-se que todas as verificações a seguir sejam feitas no modo de teste, para então prosseguir com a publicação. Consulte [esta página](../building-journeys/testing-the-journey.md).

## Verificação de erros antes do teste{#section_h3q_kqk_fhb}

Antes de testar e publicar sua jornada, verifique se todas as atividades estão configuradas corretamente. Não é possível executar testes ou publicações se os erros ainda forem detectados pelo sistema.

Os erros são exibidos com um símbolo de aviso na tela. Coloque o cursor no ponto de exclamação para exibir a mensagem de erro. Se você clicar na atividade, verá a linha que contém o erro com um aviso. Por exemplo, se um campo obrigatório estiver vazio, um erro será exibido.

![](../assets/journey63.png)

Por exemplo, caso duas atividades estejam desconectadas na tela, um aviso é exibido.

![](../assets/canvas-disconnected.png)

Um sinal de aviso pode ser exibido próximo aos botões **[!UICONTROL Test]** e **[!UICONTROL Publish]**. Este sinal de aviso mostra erros detectados pelo sistema e impede a ativação do modo de teste ou a publicação da jornada. Na maioria das vezes, os erros detectados pelo sistema estão vinculados aos erros visíveis nas atividades, mas às vezes estão vinculados a outros problemas. Nesse caso, você pode exibi-los e tentar identificar o problema usando a descrição do erro. Se não conseguir identificar o problema, você pode copiar os detalhes e enviá-los ao administrador ou ao suporte. Observe que os erros que bloqueiam o teste e os erros que bloqueiam a publicação são semelhantes.

O sistema detecta dois tipos de problemas: erros e avisos. Os erros bloqueiam a publicação e a ativação de teste. Os avisos indicam possíveis problemas que não estão bloqueando a ativação de teste ou a publicação. Você verá uma descrição do problema e uma ID de registro de problemas do tipo ERR_XXX_XXX. Essas informações ajudarão o suporte técnico a identificar o problema.

Duas cores diferentes podem ser exibidas no sinal próximo aos botões **[!UICONTROL Test]** e **[!UICONTROL Publish]**. Em caso de erro, o sinal é exibido em vermelho. Em caso de aviso, é exibido em laranja.

![](../assets/journey75.png)

Erros e avisos globais para a jornada aparecem primeiro na lista. Os erros e avisos relacionados a atividades específicas são listados depois, por ordem de atividade ou aparência na jornada, da esquerda para a direita. O botão **[!UICONTROL Copy details]** copia informações técnicas sobre a jornada que a equipe de suporte pode usar para a solução de problemas.

A jornada de uma pessoa para quando ocorre um erro em uma ação ou condição. O único modo de fazê-la continuar é marcando a caixa **[!UICONTROL Add an alternative path in case of a timeout or an error]**. Consulte [esta seção](../building-journeys/using-the-journey-designer.md#paths).

## Verificação do envio correto dos eventos{#section_rqz_11t_dgb}

O ponto de partida de uma jornada é sempre um evento. Você pode fazer testes usando ferramentas como o Postman.

Você pode verificar se a chamada à API enviada por meio dessas ferramentas foi corretamente enviada. Se ocorrer um erro, significa que a chamada tem um problema. Verifique novamente o payload, o cabeçalho (e principalmente a ID da organização) e o URL de destino. Você pode perguntar ao administrador qual é o URL correto para a ocorrência.

Eventos não são levados diretamente da origem ao [!DNL Journey Orchestration]. Na verdade, o [!DNL Journey Orchestration] depende das APIs de assimilação de streaming da Adobe Experience Platform. Como resultado, no caso de problemas relacionados ao evento, consulte [esta página](https://experienceleague.adobe.com/docs/experience-platform/ingestion/streaming/troubleshooting.html) para solucionar problemas de APIs de assimilação de streaming.

## Verificação da entrada de pessoas na jornada{#section_x4v_zzs_dgb}

O relatório do [!DNL Journey Orchestration] mede a entrada das pessoas em uma jornada em tempo real.

Se você enviar o evento com sucesso, mas não vir nenhuma entrada na jornada, significa que há algo de errado entre o envio do evento e a recepção do evento na jornada.

Veja alguns itens que o administrador deve verificar:

* Você tem certeza de que a jornada em que você espera o evento de entrada está no modo de teste ou ativa?
* Você salvou o evento antes de copiar o payload da pré-visualização de payload?
* O payload do evento contém uma ID do evento?
* Você digitou o URL correto?
* Você seguiu a estrutura de payload das APIs de assimilação de streaming usando a pré-visualização da estrutura de payload no painel de configuração do evento? Consulte [esta página](../event/previewing-the-payload.md).
* Você usou os pares de chave/valor corretos no cabeçalho do evento?

  ```
  X-gw-ims-org-id - your ORGID
  Content-type - application/json
  ```

## Verificação de como as pessoas navegam pela jornada{#section_l5y_yzs_dgb}

O relatório do [!DNL Journey Orchestration] mede o progresso das pessoas físicas dentro de uma jornada. É fácil identificar onde e por que uma pessoa foi parada.

Veja algumas coisas que devem ser verificadas:

* A interrupção se deve a uma condição que exclui a pessoa? Por exemplo, a condição é &quot;gênero = homem&quot; e a pessoa é uma mulher. Essa verificação pode ser feita por um usuário empresarial se a condição não for muito complexa.
* A interrupção se deve a uma chamada a uma fonte de dados que não está respondendo? Quando a jornada está em teste, essas informações podem ser vistas nos registros do modo de teste. Quando a jornada é em tempo real, um administrador pode testar chamadas diretas para a fonte de dados e verificar a resposta recebida. Um administrador também pode duplicar a jornada e testá-la.

## Verificação de mensagens enviadas com êxito{#section_qb1_yzs_dgb}

Se as pessoas físicas continuarem percorrendo o caminho certo na jornada, mas não receberem as mensagens esperadas, você pode verificar se:

* As mensagens transacionais levaram em conta corretamente a solicitação para enviar a mensagem. Um usuário comercial pode acessar a mensagem transacional que deve ser enviada e verificar se a hora da execução mais recente corresponde ao tempo de execução da sua jornada. Ele também pode verificar as chamadas/eventos de API mais recentes recebidos por mensagens transacionais.
* As mensagens transacionais enviaram a mensagem com êxito. Você pode ver o status de cada execução nos registros de envio da mensagem transacional. Se é verde, vermelho e qual o problema. Um usuário empresarial pode acessar essa tela e enviar os registros a um administrador para fazer mais investigações.

No caso de mensagem enviada através de ação personalizada, a única coisa a ser verificada durante o teste da jornada é o fato de a chamada do sistema da ação personalizada causar ou não um erro. Se a chamada para o sistema externo associada à ação personalizada não causar um erro, mas também não enviar a mensagem, algumas investigações devem ser feitas por parte do sistema externo.
