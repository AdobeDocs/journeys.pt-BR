---
title: Tipos de dados
description: Saiba mais sobre tipos de dados em expressões avançadas
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
workflow-type: tm+mt
source-wordcount: '675'
ht-degree: 3%

---


# Tipos de dados {#concept_gp3_rj5_dgb}

Tecnicamente, uma constante sempre contém um tipo de dados. Na expressão literal, especificamos apenas o valor. O tipo de dados pode ser inferido a partir do valor (por exemplo, string, integer, decimal etc.). Para casos específicos, como data e hora, usamos funções dedicadas para a representação.

Veja como as expressões de tipo de dados são representadas:

<table>
    <thead>
        <tr>
        <td>Tipo de dados</td>
        <td>Descrição</td>
        <td>Representação literal</td>
        <td>Exemplo</td>
        </tr>
    </thead>
    <tbody>
    <tr>
        <td>string</td>
        <td><p>Sequência comum de caracteres.</p><p>Ele não tem nenhum tamanho específico, exceto o implícito que vem do ambiente, como a quantidade de memória disponível.</p><p>Formato JSON: String</p><p>Formato de serialização: UTF-8</p></td>
        <td><p>"&lt;value&gt;"</p><p>'&lt;value&gt;'</p></td>
        <td><p><pre>"hello world"</pre></p><p><pre>'hello world'</pre></p></td>
    </tr>
    <tr>
        <td>integer</td>
        <td><p>Valor inteiro de -2^63 a 2^63-1.</p><p>Formato JSON: Número</p></td>
        <td>&lt;valor inteiro&gt;</td>
        <td><p><pre>42</pre></p></td>
    </tr>
    <tr>
        <td>decimal</td>
        <td><p>Número decimal.</p><p>Representa um valor flutuante:</p>
        <p>- maior valor positivo finito do tipo duplo, (2-2^-52)x2^1023</p>
        <p> - menor valor normal positivo do tipo duplo, 2-1022</p>
        <p> - menor valor positivo diferente de zero do tipo duplo, 2 p-1074</p><p>Formato JSON: Número</p><p>Formato de serialização: usando '.' como separador decimal.</p></td>
        <td>&lt;valor inteiro&gt;.&lt;valor inteiro&gt;</td>
        <td><p><pre>3.14</pre></p></td>
    </tr>
    <tr>
        <td>booleano</td>
        <td><p>Valor booliano escrito em minúsculas: true ou false</p><p>Formato JSON: Booleano</p></td>
        <td><p>true</p><p>false</p></td>
        <td><p><pre>true</pre></p></td>
    </tr>
    <tr>
        <td>dateTimeOnly</td>
        <td><p>Representa uma hora de data sem fuso horário, exibida como ano-mês-dia-hora-minuto-segundo-milissegundo.</p><p>Ele não armazena ou representa um fuso horário.</p><p>Em vez disso, é uma descrição da data, como usada para aniversários, combinada com a hora local, como visto em um relógio de parede.</p><p>Não pode representar um instante na linha do tempo sem informações adicionais, como deslocamento ou fuso horário.</p><p>Formato de serialização: Formato de data e hora de deslocamento estendido ISO-8601.</p><p>Usa DateTimeFormatter.</p><p>ISO_LOCAL_DATE_TIME para desserializar e serializar o valor.</p> <a href="https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html#ISO_LOCAL_DATE_TIME">Saiba mais</a>.</td>
        <td><p>toDateTimeOnly("&lt;dateTimeOnly no formato ISO-8601&gt;")</p></td>
        <td></td>
    </tr>
    <tr>
        <td>dateTime</td>
        <td><p>Constante de data e hora que também considera fuso horário.</p><p>Representa uma data e hora com um deslocamento de UTC. Ele pode ser exibido como um instantâneo no tempo com as informações adicionais do deslocamento. </p><p>É uma forma de representar um "momento" específico em um certo lugar do mundo.</p><p>Formato JSON: String.</p><p> Ele deve ser encapsulado em uma função toDateTime.</p><p>
        Formato de serialização: Formato de data e hora de deslocamento estendido ISO-8601.</p><p> Ele usa DateTimeFormatter.ISO_OFFSET_DATE_TIME para desserializar e serializar o valor.</p> <a href="https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html#ISO_OFFSET_DATE_TIME">Saiba mais</a>. 
        <p>Você também pode passar um número inteiro transmitindo um valor de época.</p> <a href="https://www.epochconverter.com/">Leia mais</a>.</p>
        <p>O fuso horário pode ser especificado por um deslocamento ou um código de fuso horário (por exemplo: Europa/Paris, Z - ou seja, UTC).</p></td>
        <td><p>toDateTime("&lt;dateTime no formato ISO-8601&gt;")</p>
        <p>toDateTime(&lt;valor inteiro de uma época em milissegundos&gt;)</p></td>
        <td><p><pre>toDateTime("1977-04-22T06:00:00Z")</pre></p><p><pre>toDateTime</pre></p><p><pre>("2011-12-03T15:15:30Z")</pre></p><p><pre>toDateTime</pre></p><p><pre>("2011-12-03T15:15:30.123Z")</pre></p><p><pre>toDateTime</pre></p><p><pre>("2011-12-03T15:15:30.123+02:00")</pre></p>
        <p><pre>toDateTime</pre></p><p><pre>("2011-12-03T15:15:30.123-00:20")</pre></p><p><pre>toDateTime(1560762190189)</pre></p></td>
    </tr>
    <tr>
        <td>duração</td>
        <td><p>Representa uma quantidade de tempo baseada em tempo, como "34,5 segundos".</p><p> Ele modela uma quantidade ou quantidade de tempo em termos de milissegundos.</p><p>As unidades temporais suportadas são: milissegundos, segundos, minutos, horas, dias em que um dia é igual a 24 horas.</p><p> Anos e meses não são suportados porque não são um tempo fixo.</p><p>Formato JSON: String. Ele deve ser encapsulado em uma função toDuration.</p><p>Formato de serialização: Para desserializar uma ID de fuso horário, ela usa a função java java.time.</p><p>Duração.análise: os formatos aceitos são baseados no formato de duração ISO-8601 PnDTnHnMn.nS com dias considerados exatamente 24 horas.</p><a href="https://docs.oracle.com/javase/8/docs/api/java/time/Duration.html#parse-java.lang.CharSequence-">Saiba mais</a>.</td>
        <td><p>toDuration("&lt;duração no formato ISO-8601&gt;")</p><p>toDuration(&lt;duração em milissegundos&gt;)</p></td>
        <td><p><pre>toDuration("PT5S") // 5 segundos</pre></p>
        <p><pre>toDuration(500) // </pre></p>
        <p><pre>500ms</pre></p>
        <p><pre>toDuration("PT20.345S") </pre></p>
        <p><pre>— analisa como "20,345 segundos"</pre></p>
        <p><pre>toDuration("PT15M") </pre></p>
        <p><pre> — analisa como "15 minutos"</pre></p>
        <p><pre>(em que um minuto é de 60 segundos)</pre></p>
        <p><pre>toDuration("PT10H") </pre></p>
        <p><pre>— analisa como "10 horas"</pre></p>
        <p><pre>(em que uma hora é de 3600 segundos)</pre></p>
        <p><pre>toDuration("P2D") </pre></p>
        <p><pre>— analisa como "2 dias"</pre></p>
        <p><pre>(se um dia for </pre></p>
        <p><pre>24 horas ou 86400 segundos)</pre></p>
        <p><pre>toDuration("P2DT3H4M") </pre></p>
        <p><pre>— analisa como</pre></p>
        <p><pre>"2 dias, 3 horas e 4 minutos"</pre></p>
        <p><pre>toDuration("P-6H3M") </pre></p>
        <p><pre>— analisa como</pre></p>
        <p><pre>"-6 horas e +3 minutos"</pre></p>
        <p><pre>toDuration("-P6H3M") </pre></p>
        <p><pre>— analisa como</pre></p>
        <p><pre>"-6 horas e -3 minutos"</pre></p>
        <p><pre>toDuration("-P-6H+3M") </pre></p>
        <p><pre>— analisa como</pre></p>
        <p><pre>"+6 horas e -3 minutos"</pre></p></td>
    </tr>
    <tr>
        <td>lista</td>
        <td>Lista separada por vírgulas de expressões usando colchetes como delimitadores. O polimorfismo não é suportado, portanto, todas as expressões contidas na lista devem ter o mesmo tipo.</td>
        <td>[&lt;expressão&gt;, &lt;expressão&gt;, ... ]</td>
        <td><p><pre>["value1","value2"]</pre></p><p><pre>[3,5]</pre></p><p><pre>[toDuration(500),toDuration(800)]</pre></p></td>
    </tr>
    </tbody>
</table>
