---
product: adobe campaign
title: Tipos de dados
description: Saiba mais sobre tipos de dados em expressões avançadas
feature: Jornadas
role: Data Engineer
level: Experienced
exl-id: 343f61b8-2315-4971-8b2b-6aa815bd9ced
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '559'
ht-degree: 5%

---

# Tipos de dados {#concept_gp3_rj5_dgb}

Tecnicamente, uma constante sempre contém um tipo de dados. Na expressão literal, especificamos apenas o valor . O tipo de dados pode ser inferido a partir do valor (por exemplo, string, número inteiro, decimal, etc.). Para casos específicos, como a data e hora, usamos funções dedicadas para a representação.

As seções abaixo fornecem informações sobre as diferentes expressões de tipo de dados e como elas são representadas.

## string {#string}

**Descrição**

Sequência comum de caracteres. Ele não tem nenhum tamanho específico, exceto o implícito que vem do ambiente, como a quantidade de memória disponível.

Formato JSON: String

Formato de serialização: UTF-8

**Representação literal**

```
"<value>"
```

```
'<value>'
```

**Exemplo**

```
"hello world"
```

```
'hello world'
```

## integer {#integer}

**Descrição**

Valor inteiro de -2^63 para 2^63-1.

Formato JSON: Número

**Representação literal**

```
<integer value>
```

**Exemplo**

```
42
```

## decimal {#decimal}

**Descrição**

Número decimal. Ele representa um valor flutuante:

* maior valor finito positivo do tipo duplo, (2-2^-52)x2^1023
* menor valor normal positivo do tipo duplo, 2-1022
* menor valor positivo diferente de zero do tipo double, 2 p-1074

Formato JSON: Número

Formato de serialização: usando &#39;.&#39; como separador decimal.

**Representação literal**

```
<integer value>.<integer value>
```

**Exemplo**

```
3.14
```

## booleano {#boolean}

**Descrição**

Valor booleano gravado em minúsculas: verdadeiro ou falso

Formato JSON: Booleano

**Representação literal**

```
true
```

```
false
```

**Exemplo**

```
true
```

## dateTimeOnly {#date-time-only}

**Descrição**

Representa uma data/hora sem fuso horário, exibida como ano-mês-dia-hora-minuto-segundo-milissegundo.

Ele não armazena ou representa um fuso horário. Em vez disso, é uma descrição da data, como usada para aniversários, combinada com a hora local, como visto em um relógio de parede.

Ele não pode representar um instante na linha do tempo sem informações adicionais, como um deslocamento ou um fuso horário.

Formato de serialização: Formato de data e hora de deslocamento estendido ISO-8601.

Ele usa DateTimeFormatter ISO_LOCAL_DATE_TIME para desserializar e serializar o valor. [Saiba mais](https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html#ISO_LOCAL_DATE_TIME&quot;)

**Representação literal**

```
toDateTimeOnly("<dateTimeOnly in ISO-8601 format>")  
```

## dateTime {#date-time}

**Descrição**

Constante de data e hora que também considera fuso horário. Representa uma data e hora com um deslocamento de UTC.

Ele pode ser exibido como um instantâneo no tempo com as informações adicionais do deslocamento. É uma forma de representar um &quot;momento&quot; específico em um certo lugar do mundo.

Formato JSON: Sequência de caracteres.

Ele deve ser encapsulado em uma função toDateTime .

Formato de serialização: Formato de data e hora de deslocamento estendido ISO-8601.

Ele usa DateTimeFormatter ISO_OFFSET_DATE_TIME para desserializar e serializar o valor. [Saiba mais](https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html#ISO_OFFSET_DATE_TIME)

Você também pode passar um número inteiro passando por um valor de época. [Leia mais](https://www.epochconverter.com)

O fuso horário pode ser especificado por um deslocamento ou um código de fuso horário (por exemplo: Europa/Paris, Z - ou seja, UTC).

**Representação literal**

```
toDateTime("<dateTime in ISO-8601 format>")
```

```
toDateTime(<integer value of an epoch in milliseconds>)
```

**Exemplo**

```
toDateTime("1977-04-22T06:00:00Z")
```

```
toDateTime("2011-12-03T15:15:30Z")
```

```
toDateTime("2011-12-03T15:15:30.123Z")
```

```
toDateTime("2011-12-03T15:15:30.123+02:00")
```

```
toDateTime("2011-12-03T15:15:30.123-00:20")
```

```
toDateTime(1560762190189)
```

## duration {#duration}

**Descrição**

Representa uma quantidade de tempo baseada em tempo, como &quot;34,5 segundos&quot;. Ele modela uma quantidade ou quantidade de tempo em termos de milissegundos.

As unidades temporais suportadas são: milissegundos, segundos, minutos, horas, dias em que um dia é igual a 24 horas. Anos e meses não são suportados, pois não são um período fixo.

Formato JSON: Sequência de caracteres.

Ele deve ser encapsulado em uma função toDuration .

Formato de serialização: Para desserializar uma ID de fuso horário, ela usa a função java java.time.

Duração.análise: os formatos aceitos são baseados no formato ISO-8601 duration PnDTnHnMn.nS com dias considerados exatamente 24 horas. [Saiba mais](https://docs.oracle.com/javase/8/docs/api/java/time/Duration.html#parse-java.lang.CharSequence-)

**Representação literal**

```
toDuration("<duration in ISO-8601 format>")
```

```
toDuration(<duration in milliseconds>)
```

**Exemplo**

```
toDuration("PT5S") -- parses as 5 seconds
```

```
toDuration(500) -- parses as 500ms
```

```
toDuration("PT20.345S") -- parses as "20.345 seconds"
```

```
toDuration("PT15M") -- parses as "15 minutes" (where a minute is 60 seconds)
```

```
toDuration("PT10H")  -- parses as "10 hours" (where an hour is 3600 seconds)
```

```
toDuration("P2D") -- parses as "2 days" (where a day is 24 hours or 86400 seconds)
```

```
toDuration("P2DT3H4M") -- parses as "2 days, 3 hours and 4 minutes"
```

```
toDuration("P-6H3M") -- parses as "-6 hours and +3 minutes"
```

```
toDuration("-P6H3M") -- parses as "-6 hours and -3 minutes"
```

```
toDuration("-P-6H+3M") -- parses as "+6 hours and -3 minutes"
```

## listar {#list}

**Descrição**

Lista de expressões separada por vírgulas usando colchetes como delimitadores.

O polimorfismo não é suportado, portanto, todas as expressões contidas na lista devem ter o mesmo tipo.

**Representação literal**

```
[<expression>, <expression>, ... ]
```

**Exemplo**

```
["value1","value2"]
```

```
[3,5]
```

```
[toDuration(500),toDuration(800)]
```
