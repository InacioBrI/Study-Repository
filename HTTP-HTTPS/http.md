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



#### 3. Corpo/Mensagem

### http//

Em navegadores da internet como Chrome e Safari, um endereço Web é prefixado por ``http://``. Este prefixo instrui o navegador da Web a comunicar pelo protocolo HTTP, um exemplo:

```

http://google.com

```

## Etapas que acontecem com o HTTP

### 1. Etapa - Navegação e inicio

O usuario deve-se diriger para endeteço IP da Web em um navegador ou clicar em um link simple email ou de comunicação. A URL também tem dominio. O navegador localiza o endereço da Web com uma  pesquisa de DNS ``(Sistema  de nomes de Dominio)`` e em seguida, envia a solicitação para o endereço 

### 2. Etapa - ``cliente``envia uma mensagem de solicitação HTTP ao servidor 

``cliente``TTP, por exemplo, o navegador, constroi uma mensagem de solicitação que é direicionada para o servidor Web do Google. A primeira linha de mensagem de solicitação HTTP identidica a pagina raiz do site ou seja da o famoso ``GET``

### 3. Etapa - O servidor Web do Google envia a respota HTTP de volta para cliente

Assim que o servidor da Web do Google recebe a solicitação, uma mensagem de respota criada e retornada para o ``cliente`` 
A primeira linha da mensagem inclui o codigo de resposta "200" OK para indicar que o servidor Web pode responder à solicitação com exito.

### Quais codigo podem aparecer na resposta:

* 404 - Não Encontrado
* 503 - Servidor Indisponivel