---
title: 'Fontes de dados externas '
description: 'Saiba como configurar fontes de dados externas '
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a0db4d65218861b71d35f83ccf2d15e25a1597e8

---



# Fontes de dados externas {#concept_t2s_kqt_52b}

Fontes de dados externas permitem que você defina uma conexão com sistemas de terceiros, por exemplo, se você estiver usando um sistema de reserva de hotel para verificar se a pessoa registrou um quarto. Ao contrário da fonte de dados integrada da plataforma Experience, você pode criar quantas fontes de dados externas forem necessárias.

As APIs REST que usam POST ou GET e devolvem JSON são suportadas. A chave da API, os modos de autenticação básicos e personalizados são suportados.

Vejamos o exemplo de um serviço de API meteorológica que eu quero usar para personalizar os comportamentos da minha jornada de acordo com os dados do tempo real.

Estes são dois exemplos da chamada de API:

* _https://api.adobeweather.org/weather?city=London,uk&amp;appid=1234_
* _https://api.adobeweather.org/weather?lat=35&amp;lon=139&amp;appid=1234_

A chamada é composta de um URL principal (_https://api.adobeweather.org/weather_), dois conjuntos de parâmetros (&quot;cidade&quot; para a cidade e &quot;lat/long&quot; para a latitude e a longitude) e a chave da API (appid).

Estas são as principais etapas para criar e configurar uma nova fonte de dados externa:

1. Na lista de fontes de dados, clique em **[!UICONTROL Add]** para criar uma nova fonte de dados externa.

   ![](../assets/journey25.png)

   Isso abre o painel de configuração da fonte de dados no lado direito da tela.

   ![](../assets/journey26.png)

1. Insira um nome para a sua fonte de dados.

   >[!NOTE]
   >
   >Não use espaços ou caracteres especiais. Não use mais de 30 caracteres.

1. Adicione uma descrição à sua fonte de dados. Esta etapa é opcional.
1. Adicione o URL do serviço externo. Em nosso exemplo: _https://api.adobeweather.org/weather_.

   >[!CAUTION]
   >
   >Recomendamos o uso do HTTPS por motivos de segurança. Observe também que não permitimos o uso de endereços da Adobe que não estão disponíveis publicamente e o uso de endereços IP.

   ![](../assets/journey27.png)

1. Configure a autenticação dependendo da configuração do serviço externo: **[!UICONTROL No authentication]**, **[!UICONTROL Basic]**, **[!UICONTROL Custom]** ou **[!UICONTROL API key]**. Para obter mais informações sobre o modo de autenticação personalizado, consulte [](../datasource/external-data-sources.md#section_wjp_nl5_nhb). Em nosso exemplo, escolhemos:


   * **[!UICONTROL Type]**: &quot;Chave da API&quot;
   * **[!UICONTROL Value]**: &quot;1234&quot; (este é o valor da nossa chave de API)
   * **[!UICONTROL Name]**: &quot;appid&quot; (este é o nome do parâmetro da chave da API)
   * **[!UICONTROL Location]**: &quot;Parâmetro de consulta&quot; (a chave da API está localizada no URL)
   ![](../assets/journey28.png)

1. Adicione um novo grupo de campos para cada conjunto de parâmetros da API clicando em **[!UICONTROL Add a New Field Group]**. Não use espaços ou caracteres especiais no nome do grupo de campos. Em nosso exemplo, precisamos criar dois grupos de campo, um para cada conjunto de parâmetros (cidade e long/lat).

Para o conjunto de parâmetros &quot;long/lat&quot;, criamos um grupo de campos com as seguintes informações:

* **[!UICONTROL Used in]**: exibe o número de viagens que usam um grupo de campos. Você pode clicar no **[!UICONTROL View journeys]** ícone para exibir a lista de viagens usando esse grupo de campos.
* **[!UICONTROL Method]**: selecione o método POST ou GET. No nosso caso, selecionamos o método GET.
* **[!UICONTROL Cache duration]**: no nosso caso, queremos que o tempo seja armazenado em cache por 10 minutos.
* **[!UICONTROL Response Payload]**: clique dentro do **[!UICONTROL Payload]** campo e cole um exemplo da carga retornada pela chamada. Para nosso exemplo, usamos uma carga encontrada em um site da API do tempo. Verifique se os tipos de campo estão corretos. Cada vez que a API é chamada, o sistema recuperará todos os campos incluídos no exemplo de carga. Observe que você pode clicar em **[!UICONTROL Paste a new payload]** se desejar alterar a carga transmitida no momento.
* **[!UICONTROL Dynamic Values]**: insira os diferentes parâmetros separados por vírgula, &quot;long,lat&quot; no nosso exemplo. Como os valores dos parâmetros dependem do contexto de execução, eles serão definidos nas viagens. Consulte [](../expression/expressionadvanced.md).
* **[!UICONTROL Sent Payload]**: este campo não aparece no nosso exemplo. Ela só estará disponível se você selecionar o método POST. Cole a carga que será enviada para o sistema de terceiros.

No caso de uma chamada GET que exija parâmetros, você informa os parâmetros no **[!UICONTROL Parameters]** campo e eles são adicionados automaticamente no final da chamada. No caso de uma chamada POST, é necessário:

* lista os parâmetros a serem transmitidos no momento da chamada no **[!UICONTROL Parameter]** campo (no exemplo abaixo: &quot;identificador&quot;).
* especifique-os também com a mesma sintaxe no corpo da carga enviada. Para fazer isso, é necessário adicionar: &quot;param&quot;: &quot;nome do parâmetro&quot; (no exemplo abaixo: &quot;identificador&quot;). Siga a sintaxe abaixo:

   ```
   {"id":{"param":"identifier"}}
   ```

![](../assets/journey29.png)

Clique em **[!UICONTROL Save]**.

A fonte de dados agora está configurada e pronta para ser usada em suas viagens, por exemplo em suas condições ou para personalizar um email. Se a temperatura estiver acima de 30°C, você pode decidir enviar uma comunicação específica.

## Modo de autenticação personalizado{#section_wjp_nl5_nhb}

Esse modo de autenticação é usado para autenticação complexa, frequentemente usada para chamar protocolos de empacotamento de API como OAuth2, para recuperar um token de acesso a ser inserido na solicitação HTTP real para a ação.

Ao configurar a autenticação personalizada, você pode clicar no botão abaixo para verificar se a carga de autenticação personalizada está configurada corretamente.

![](../assets/journey29-bis.png)

Se o teste for bem-sucedido, o botão fica verde.

![](../assets/journey29-ter.png)

Com essa autenticação, a execução da ação é um processo de duas etapas:

1. Chame o terminal para gerar o token de acesso.
1. Chame a REST API injetando da maneira correta o token de acesso.

Esta autenticação tem duas partes.

A definição do ponto de extremidade a ser chamado para gerar o token de acesso:

* terminal: URL a ser usado para gerar o ponto de extremidade
* método da solicitação HTTP no terminal (GET ou POST)
* cabeçalhos: pares de chave/valor a serem inseridos como cabeçalhos nesta chamada, se necessário
* corpo: descreve o corpo da chamada se o método for POST. Apoiamos uma estrutura de corpo limitada, definida em bodyParams (pares de chaves/valores). O bodyType descreve o formato e a codificação do corpo na chamada:
   * &#39;form&#39;: o que significa que o tipo de conteúdo será application/x-www-form-urlencoded (charset UTF-8) e os pares key/value serão serializados como estão: key1=value1&amp;key2=value2&amp;...
   * &#39;json&#39;: o que significa que o tipo de conteúdo será application/json (charset UTF-8) e que os pares de valores principais serão serializados como um objeto json como está: _{ &quot;key1&quot;: &quot;value1&quot;, &quot;key2&quot;: &quot;value2&quot;, ...}_

A definição da forma como o token de acesso deve ser inserido na solicitação HTTP da ação:

* licenseType: define como o token de acesso gerado deve ser inserido na chamada HTTP para a ação. Os valores possíveis são:

   * portador: indica que o token de acesso deve ser inserido no cabeçalho de Autorização, como: _Autorização: Portador &lt;token de acesso>_
   * cabeçalho: indica que o token de acesso deve ser inserido como um cabeçalho, o nome do cabeçalho definido pela propriedade tokenTarget. Por exemplo, se o tokenTarget for myHeader, o token de acesso será inserido como um cabeçalho como: _myHeader: &lt;token de acesso>_
   * queryParam: indica que o token de acesso deve ser inserido como um queryParam, o nome do parâmetro de consulta definido pela propriedade tokenTarget. Por exemplo, se o tokenTarget for myQueryParam, o URL da chamada de ação será: _&lt;url>?myQueryParam=&lt;token de acesso>_

* tokenInResponse: indica como extrair o token de acesso da chamada de autenticação. Essa propriedade pode ser:
   * &#39;response&#39;: indica que a resposta HTTP é o token de acesso
   * um seletor em um json (supondo que a resposta seja um json, não oferecemos suporte a outros formatos, como XML). O formato desse seletor é _json://&lt;caminho para a propriedade do token de acesso>_. Por exemplo, se a resposta da chamada for: _{ &quot;access_token&quot;: &quot;theToken&quot;, &quot;timestamp&quot;: 12323445656 }_, o tokenInResponse será: _json: //access_token_

O formato desta autenticação é:

```
{
    "type": "customAuthorization",
    "authorizationType": "<value in 'bearer', 'header' or 'queryParam'>",
    (optional, mandatory if authorizationType is 'header' or 'queryParam') "tokenTarget": "<name of the header or queryParam if the authorizationType is 'header' or 'queryParam'>",
    "endpoint": "<URL of the authentication endpoint>",
    "method": "<HTTP method to call the authentication endpoint, in 'GET' or 'POST'>",
    (optional) "headers": {
        "<header name>": "<header value>",
        ...
    },
    (optional, mandatory if method is 'POST') "body": {
        "bodyType": "<'form'or 'json'>,
        "bodyParams": {
            "param1": value1,
            ...

        }
    },
    "tokenInResponse": "<'response' or json selector in format 'json://<field path to access token>'"
}
```
