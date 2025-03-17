# Protocolo HTTP

![alt text](/Images/http.png)

## O que é um protocolo HTTP?

Da sigla ``Hypertext transfer protocol`` <br>
**Protocolo de transferencia de hipertexto**

O HTTP é um ``protocolo de camada de aplicação``, sendo assim ele é implementado nos sofware responsavel por essa comunicação, como nos ``Navegadores`` e ``Servidores WEB``


## HTTP não está sozinho!

o http sempre vai estrar trabalhando com mais dois protocolos, sendo eles:

**TCP** ``Transmission Control Protocol`` <br>
Responsavel pela transferencia das informações

**IP** ``Protocolo IP`` <br>
Um pacote IP contém os endereços IP da origem e do destino. 

## Request e Response (Pedido e Resposta)

Basicamente quando você abre um navegador pra acessar alguma coisa, vai estar ``requisitando`` informações do servidor, que assim ao receber esse pedido fara o serviços internos e devolvera uma ``resposta`` e por muitas muitas vezes essas respostas vai vir em ``HTML`` e ``CSS`` que ira ser interpretada no navegador o conteudo buscado.


## Request 
### O Resquest é formado por três fatores
Que cada uma é formada por algumas informações.

#### 1. Linha de Pedido
1. ``IDENTIFICADOR DE METODO``<br>
Basicamente é o tipo de ação que você vai esperar do servidor, existem 8 tipo, mas sendo os mais famosos o ``GET`` o ``POST`` e o ``DELETE``

2. ``URI DO RECURSO``<br>
Sendo ele o endereço, no qual será enviado o pedido, um exemplo: /index.php

3. ``VERSÃO DO PROTOCOLO``<br>
Atualmente contendo quatro versôes, sendo elas:<br>
* ``HTTP 0.9``<br>
* ``HTTP 1.0``<br>
* ``HTTP 1.1``<br>
* ``HTTP 2``<br>

#### 2. Cabeçalho
O cabeçalho é o local para se passar informações adicionais sobre a ``requisição`` e o ``servidor``, ele pode responder de modo diferente dependendo dos campos e valores contido nele. <br>

**Sendo ele dividido em três grupos**
1. ``CABEÇALHO GERAL`` 
2. ``CABEÇALHO DE REQUISIÇÃO`` 
3. ``CABEÇALHO DE ENTIDADE`` 

#### Campos:
A quantidade de campos que tem é muito grande, mas vou colocar aqui, os mais usado:

* ``DATE`` - Informa da data do envio da requisição
* ``CACHE-CONTROL`` - Envia diretivos para o mecanismo de Cache
* ``TRANSFER-ENCODING`` - Especidica a forma de decodificar o corpo da requisição
* ``COOKIE`` - Envia informações sobre os Cookies
* ``Accept`` - Especifica a preferencia de resposta
* ``User-Agent`` - Envia informações sobre o client

#### 3. Corpo/Mensagem
O corpo nada mais é do que os dados da sua requisição.<br>
``Exemplo:`` em um envio de formulario HTML, ficaria no corpo as informações desse formulario.

Exemplo:
![alt text](/Images/PostHTTP.png)


## Mas afinal qual, qual request pode nos retornar?