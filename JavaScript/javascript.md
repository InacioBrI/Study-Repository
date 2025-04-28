# Aprenda JavaScript de uma vez por toda!

![BannerJs](image-1.png)

#### aqui irei te ensinar do zero até o avançado sobre JavaScript, e que você consiga fazer sozinho suas proprias funções.

# 🧠 Módulo 1 Fundamentos do JavaScript
### 1. O que é JavaScript?
* Javascript é uma linguagem de programação interpretada de alto nivel.
* Criada em 1955 por Brendan Eich em apenas `` 10 dias``, **loucura né**
* Inicialmente era usada para fazer apenas paginas Web interativas, mas hoje em dia é usada para até fazer ``Servidores``,``Desktop``,``Mobile``,``Lot``,``Inteligencia Artificial``

## Quer saber uma curiosidade?
``Roda no navegador por meio de um "motor" (engine).``

* ``Chrome`` → ``V8 Engine``

* ``Firefox`` → ``SpiderMonkey``

* ``Safari`` → ``JavaScriptCore``

## Mas como o JavaScript é interpretado?

* Não compila o código antes de rodar (como ``C++`` ou ``Java``). O navegador lê linha por linha do seu código, interpreta e executa, os motores modernos fazem JIT Compilation (Just-In-Time) para melhorar a performance.

## Trindade da Web:
##### ``HTML: estrutura`` (o corpo da página)

##### ``CSS: estilo`` (como ela é apresentada)

##### ``JavaScript:`` comportamento (o cérebro da página)

# 🛠️ Módulo 2 - Tipos de dados e Operadores. 
``Objetivo: Entender como o JavaScript armazena e manipula as informações.``

### Tipos Primitivos

### String → texto ("Olá")

```
const nomeCliente = "Gabriel";
console.log(`Bem-vindo de volta, ${nomeCliente}!`);
```
``Usada para exibir mensagens, capturar inputs, nomes de usuários...``

### Number → números (10, 3.14)

```
const precoProduto = 249.99;
const desconto = 20;
const precoFinal = precoProduto - desconto;
console.log(`Preço com desconto: R$${precoFinal}`);
```
``Usado para valores de pagamento, idades, contadores, métricas...``

### Boolean → verdadeiro/falso (true, false)

```
const isAutenticado = true;

if (isAutenticado) {
  console.log("Redirecionar para o painel do usuário.");
} else {
  console.log("Redirecionar para login.");
}
```
``Controle de fluxo (usuário autenticado? pagamento aprovado? etc)``

### Null → vazio (null)

```
let fotoPerfil = null;
// Se o usuário não enviar uma foto, usar imagem padrão
console.log(fotoPerfil ?? "imagem_padrao.png");
```
``Dado que foi intencionalmente definido como “sem valor”.``

### Undefined → não definido

```
function exibeMensagem(mensagem) {
  console.log(mensagem);
}

exibeMensagem(); // undefined
```
``Variável declarada mas ainda não atribuída, ou ausência de parâmetro.``

### Symbol → identificador único

```
const ROLE_ADMIN = Symbol("admin");
const ROLE_USER = Symbol("user");

const usuario = {
  nome: "Lívia",
  tipo: ROLE_ADMIN
};

console.log(usuario.tipo);
```
``Numa empresa: Sistema de permissões em plataformas corporativas.``

### BigInt → números inteiros enormes

```
const numeroGigante = 12345678901234567890123456789012n;
console.log(numeroGigante);
```

## Tipos de Referência:

### Object → estrutura chave-valor

```
const produto = {
  id: 1,
  nome: "Notebook Gamer",
  preco: 6599.90,
  emEstoque: true
};

console.log(produto);
```
``Numa empresa: Cadastro de produtos em marketplace tipo Amazon.``

### Array → lista ordenada

```
    const pedidos = [
  { id: 1, produto: "Mouse", quantidade: 2 },
  { id: 2, produto: "Teclado", quantidade: 1 },
];

console.log(pedidos);
```
``Numa empresa: Lista de pedidos no carrinho de compras de um cliente.``

### Function → blocos de código reutilizáveis

```
function calcularTotal(preco, quantidade) {
  return preco * quantidade;
}

console.log(calcularTotal(299.99, 3));
```

# 📚 Modulo 3 - Variavel, Constantes e Escopos.
``Objetivo: Aprender a guardar informações e contolar onde elas vivem.``

``Var``, ``Let`` e ``const``

``var`` → Antigo, escopo de função, sofre hoisting (sobe pro topo).

``let`` → Moderno, escopo de bloco.

``const`` → Moderno, escopo de bloco e não pode reatribuir valor.

Exemplo: 

```
{
  let a = 2;
  const b = 3;
  var c = 4;
}
console.log(c); // OK
console.log(a); // ERRO
```

## Hoisting

### ``JavaScript move declarações para o topo do código antes de executar.``

### ``var`` é "içado", mas ``let`` e ``const`` não!

## Vou dar exemplos de como eles são usados dentro de uma empresa.

### var → (antigo, escopo de função, sofre hoisting)

```
function exemploVar() {
  var mensagem = "Olá com var";
  console.log(mensagem);
}
exemploVar();
```
``Numa empresa: Código legado, sistemas antigos ainda têm muito var (principalmente antes de 2015).``

### let → (moderno, escopo de bloco)

```
function exemploLet() {
  let contador = 0;
  if (true) {
    let contador = 5; // Essa variável só existe aqui dentro
    console.log("Dentro do if:", contador); 
  }
  console.log("Fora do if:", contador);
}
exemploLet();
```
``Numa empresa: Usar let para variáveis que precisam mudar dentro de blocos separados (ex: laços, condições).``

### const → (moderno, escopo de bloco, valor constante)

```
function exemploConst() {
  const taxa = 0.15;
  console.log(`Taxa de juros: ${taxa * 100}%`);
}
exemploConst();
```
``Numa empresa: Constantes usadas para valores que não mudam, tipo taxa de impostos, chave de API, configurações fixas.``

## Exemplo mais prático e real de empresa usando var, let e const juntos:

```
function checkoutCarrinho(produtos) {
  const taxaEntrega = 15.99;
  let total = 0;

  for (var i = 0; i < produtos.length; i++) {
    total += produtos[i].preco * produtos[i].quantidade;
  }

  total += taxaEntrega;
  return total;
}

const carrinho = [
  { nome: "Teclado", preco: 199.90, quantidade: 1 },
  { nome: "Mouse", preco: 99.90, quantidade: 2 }
];

console.log(`Valor final: R$${checkoutCarrinho(carrinho)}`);
```
``Numa empresa: Função de checkout de compras, somando produtos e entrega.``

## Agora, sobre ESCOPO:

### Escopo de Função
#### Variáveis declaradas dentro de uma função só existem dentro dela.

```
function criarUsuario() {
  let nome = "Lucas";
  console.log(nome);
}
criarUsuario();
// console.log(nome); // ERRO: nome is not defined
```
💡``Numa empresa: Dados temporários usados só dentro de processos internos (não vazam para fora).``

### 🔹Escopo de Bloco (if, for, etc)
``let`` e ``const`` respeitam blocos ``{}``, ``var`` não respeita!

```
{
  let produto = "Notebook";
  const preco = 4500;
  console.log(produto, preco);
}
// console.log(produto); // ERRO
```
💡``Numa empresa: Protege variáveis locais para não ter conflito de nomes em diferentes partes do sistema.``

## 🔹 Hoisting → "içamento"
Só ``var`` sofre hoisting completo, ``let``/``const`` não!

```
console.log(nome); // undefined (por causa do hoisting)
var nome = "Carlos";
```

```
// console.log(preco); // ERRO (não sofre hoisting)
let preco = 300;
```

Numa empresa: Bugs bizarros em sistemas antigos que misturavam ``var``, ``let`` e ``const`` → virou uma bagunça, por isso se recomenda usar let/const SEMPRE hoje.

## 🛠️ Um exemplo realzão de escopo em função de grande sistema:

```
function processarPedido(pedido) {
  if (!pedido) {
    const erro = "Pedido inválido.";
    return erro;
  }

  let status = "Em processamento";

  if (pedido.valor > 1000) {
    let status = "Pedido de alto valor";
    console.log(status); // "Pedido de alto valor"
  }

  console.log(status); // "Em processamento"
}

const pedidoCliente = { id: 123, valor: 1500 };
processarPedido(pedidoCliente);
```

💡``Numa empresa: Funções grandes que precisam tratar vários cenários sem deixar as variáveis "vazarem" para onde não devem.``

# 📈 Resumo Visual
![palavraChave](/JavaScript/resumo3.png)

# 📚 MÓDULO 4 — Controle de Fluxo em JavaScript

### Controle de fluxo = ``dizer ao código "o que fazer em cada situação".``
**Tipo: "se isso acontecer → faça isso, se não → faça aquilo".**

###  🔹 1. if / else → Condicional padrão

```
const saldo = 500;

if (saldo >= 100) {
  console.log("Compra aprovada!");
} else {
  console.log("Saldo insuficiente.");
}
```
💡``Numa empresa: Aprovar pagamento se o cliente tiver saldo.``

### 🔹 2. else if → Várias condições diferentes

```
const nota = 75;

if (nota >= 90) {
  console.log("Aprovado com excelência!");
} else if (nota >= 60) {
  console.log("Aprovado.");
} else {
  console.log("Reprovado.");
}
```
💡``Numa empresa: Avaliação de desempenho de funcionários (tipo metas atingidas).``

### 🔹 3. switch → Muitas opções fixas

```
const metodoPagamento = "credito";

switch (metodoPagamento) {
  case "debito":
    console.log("Pagamento com débito.");
    break;
  case "credito":
    console.log("Pagamento com crédito.");
    break;
  case "pix":
    console.log("Pagamento com Pix.");
    break;
  default:
    console.log("Método de pagamento inválido.");
}
```
💡``Numa empresa: Processar diferentes formas de pagamento no checkout.``

### 🔹 4. for → Repetição com contador

```
for (let i = 1; i <= 5; i++) {
  console.log(`Pedido número ${i}`);
}
```
💡``Numa empresa: Gerar número de pedidos, imprimir etiquetas, fazer listagens.``

### 🔹 5. while → Repetição enquanto uma condição for verdadeira

```
let tentativas = 0;

while (tentativas < 3) {
  console.log(`Tentativa ${tentativas + 1}`);
  tentativas++;
}
```
💡``Numa empresa: Tentativas de login antes de bloquear usuário.``

### 🔹 6. do...while → Executa pelo menos uma vez

```
let senhaCorreta = false;
let tentativasSenha = 0;

do {
  console.log("Tentando validar senha...");
  tentativasSenha++;
} while (!senhaCorreta && tentativasSenha < 3);
```
💡 ``Numa empresa: Garantir que uma verificação de segurança execute pelo menos uma vez.``

### 🔹 7. break → Interromper um loop


```
for (let i = 0; i < 10; i++) {
  if (i === 5) {
    break;
  }
  console.log(i);
}
```
💡 ``Numa empresa: Parar um processo ao atingir um limite (ex: estoque mínimo).``

### 🔹 8. continue → Pula para a próxima repetição

```
for (let i = 0; i <= 5; i++) {
  if (i === 3) {
    continue;
  }
  console.log(i);
}
```

💡 ``Numa empresa: Ignorar produtos indisponíveis em uma lista de pedidos.``

🎯 Exemplo Realzão usando tudo junto:

```
function processarPedidos(pedidos) {
  for (let i = 0; i < pedidos.length; i++) {
    const pedido = pedidos[i];

    if (!pedido.disponivel) {
      console.log(`Pedido ${pedido.id} indisponível, pulando...`);
      continue;
    }

    if (pedido.valor > 1000) {
      console.log(`Pedido ${pedido.id} é de alto valor!`);
    } else {
      console.log(`Processando pedido ${pedido.id} normalmente.`);
    }

    if (i >= 10) {
      console.log("Limite máximo de pedidos processados.");
      break;
    }
  }
}

const listaPedidos = [
  { id: 1, valor: 250, disponivel: true },
  { id: 2, valor: 1200, disponivel: true },
  { id: 3, valor: 400, disponivel: false },
  { id: 4, valor: 100, disponivel: true },
];

processarPedidos(listaPedidos);
```

💡 ``Numa empresa: Esse tipo de fluxo seria usado pra processar filas de pedidos num sistema de vendas ou logística.``

# Modulo 5 - Funções em JavaScript
**Objetivo**: Modularizar (separar) e reutilizar código em várias partes do programa.

### 🧩 Tipos de Funções

### 🔹 1. Funções Declarativas → ``function nome()``

```
function saudacao() {
  console.log("Olá, seja bem-vindo!");
}

saudacao();
```
💡 ``Numa empresa: Usar funções para mensagens padrão no app, como "Boas-vindas" ou "Senha inválida".``

### 🔹 2. Expressões de Função → Armazena função numa variável

```
const somar = function (a, b) {
  return a + b;
};

console.log(somar(5, 3)); // 8
```
💡 ``Numa empresa: Guardar funções em variáveis pra depois passar elas como parâmetros (muito usado em eventos ou filtros).``
 
### 🔹 3. Arrow Functions → Função moderna (mais curta)

```
const multiplicar = (a, b) => a * b;

console.log(multiplicar(4, 5)); // 20
```
💡 ``Numa empresa: Usada direto em APIs, sistemas em React, manipulação rápida de listas (arrays).``

# 🧠 Conceitos Importantes

### 🔸 ``Parameters x Arguments``

* **Parameters = nomes definidos na criação da função.**

* **Arguments = valores passados quando a função é chamada.**

```
function apresentar(nome) { // parâmetro: nome
  console.log(`Olá, ${nome}!`);
}

apresentar("Lucas"); // argumento: "Lucas"
```
💡 ``Numa empresa: Cadastro de novos usuários enviando nome, email, senha via função.``

---

### 🔸 Escopo de Função
``Cada função cria o seu próprio "mundinho" de variáveis.``

```
function testeEscopo() {
  const segredo = "1234";
  console.log(segredo); // OK: dentro da função
}

testeEscopo();
// console.log(segredo); // Erro: fora da função
```
💡 ``Numa empresa: Manter dados sensíveis escondidos (ex: tokens de sessão, validações internas).``

---

### 🔸 Closure (Fechamento de Escopo)
``Função lembra do lugar onde foi criada, mesmo depois de ser chamada fora dele.``

```
function criarContador() {
  let contador = 0;

  return function() {
    contador++;
    console.log(contador);
  };
}

const contador1 = criarContador();
contador1(); // 1
contador1(); // 2
contador1(); // 3
```
💡 ``Numa empresa: Gerenciar estado interno sem deixar exposto (ex: contador de visitas, tempo de sessão do usuário).``

---

## 🎯 Exemplo Real com Tudo Junto:
```
function criarSistemaDeLogin(usuarioCorreto, senhaCorreta) {
  return function(usuario, senha) {
    if (usuario === usuarioCorreto && senha === senhaCorreta) {
      return "Login realizado com sucesso!";
    } else {
      return "Usuário ou senha incorretos.";
    }
  };
}

const login = criarSistemaDeLogin("admin", "1234");

console.log(login("admin", "1234")); // Login realizado com sucesso!
console.log(login("admin", "0000")); // Usuário ou senha incorretos.
```
💡 ``Numa empresa: Sistema de autenticação, mantendo a senha protegida dentro da função inicial.```

# Resumo Modulo 5

![alt text](/JavaScript/resumoModulo5.png)

### ⚡Observação importante:

#### 🔸 ``Arrow Functions`` NÃO têm seu próprio this → Isso muda como você usa dentro de classes ou objetos!

#### 🔸``losures`` são MUITO usadas para criar funções "privadas" no JavaScript moderno.

# 🗄️ Modulo 6 - Objetos Arrays
**Objetivo**: Trabalhar com grupos de dados de forma organizada.

### 📦 Objetos → "pacote" com chave e valor (estrutura de dados)

### 🔹``Criando um Objeto:``
```
const usuario = {
  nome: "Lucas",
  idade: 25,
  email: "lucas@email.com"
};

console.log(usuario.nome); // Lucas
console.log(usuario["email"]); // lucas@email.com
```
💡 ``Numa empresa: Representar usuários, produtos, pedidos... Cada objeto representa uma entidade do sistema.``

### 🔹 Adicionando / alterando propriedades

```
usuario.telefone = "1199999-9999"; // adicionar
usuario.idade = 26; // alterar

console.log(usuario);
```
💡 ``Numa empresa: Atualizar dados do cliente, como endereço ou telefone.``

---

### 🔹 Removendo propriedades

```
delete usuario.email;

console.log(usuario);
```
💡 ``Numa empresa: Remover dados sensíveis quando não são mais necessários (por segurança ou privacidade).``

### 🔹 Métodos dentro de objetos
Funções que vivem dentro do objeto → chamadas de métodos.

```
const carro = {
  modelo: "Fusca",
  ligar: function() {
    console.log("Carro ligado!");
  }
};

carro.ligar();
```
💡 ``Numa empresa: Métodos para ações que pertencem ao objeto (ex: enviarEmail(), confirmarPagamento()).``

## 📋 Arrays → Lista ordenada de dados (índices)

### 🔹 Criando um array

```
const frutas = ["Maçã", "Banana", "Laranja"];

console.log(frutas[0]); // Maçã
console.log(frutas.length); // 3
```
💡 Numa empresa: Listas de produtos, clientes, pedidos, etc.

### 🔹 Adicionando e removendo no array

```
frutas.push("Manga"); // adicionar no final
frutas.pop(); // remover do final

frutas.unshift("Morango"); // adicionar no início
frutas.shift(); // remover do início

console.log(frutas);
```
💡 Numa empresa: Carrinho de compras (adicionar/remover itens).

### 🔹 Percorrendo arrays (for/forEach)

```
frutas.forEach(function(fruta, indice) {
  console.log(`${indice + 1}: ${fruta}`);
});
```
💡 Numa empresa: Mostrar lista de produtos para o cliente.

### 🔹 Outras operações úteis
```
const numeros = [1, 2, 3, 4, 5];

const dobrados = numeros.map(numero => numero * 2);
console.log(dobrados); // [2, 4, 6, 8, 10]

const pares = numeros.filter(numero => numero % 2 === 0);
console.log(pares); // [2, 4]

const somaTotal = numeros.reduce((acumulador, numero) => acumulador + numero, 0);
console.log(somaTotal); // 15
```
💡 Numa empresa:
* ``map``: gerar preço  com desconto
* ``Filter``: mostrar apenas produtos disponivel
* ``reduce``: Calcular o total da compra

## 🎯 Exemplo Real de Objeto + Array Juntos:

```
const clientes = [
  { nome: "Lucas", saldo: 500 },
  { nome: "Ana", saldo: 1200 },
  { nome: "Carlos", saldo: 300 }
];

clientes.forEach(cliente => {
  if (cliente.saldo >= 1000) {
    console.log(`${cliente.nome} é cliente VIP!`);
  } else {
    console.log(`${cliente.nome} é cliente comum.`);
  }
});
```
💡 Numa empresa: Sistema que diferencia cliente VIP de cliente comum baseado em saldo.

## Resumo do Modulo 6:

![modulo6](/JavaScript/resumoModulo6.png)