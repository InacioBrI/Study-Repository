# Não fique perdido sobre o que é JSON, fique maluco!

## Brincadeira, nesse artigo vou te mostrar como você vai aprender o que é JSON

De uma forma que seja simples, para até mesmo para um cavalo prender o que seja, ``JSON``

``Relaxa JSON não vai te matar``

![Jason](/Images/Jason.png)

## Mas afinal de conta, o que é o bendito JSON?

JSON está ligado na area de desenvolvimento de Software,
ele é um formato simples e leve de troca de dados.

Basease em um subconjunto da linguagem JavaScript ``(JavaScript Object Notation)``, mas calma, por mais que ele carregue o nome do Javacript, ele não é puramente escrito nessa linguagem.

JSON é um formato de texto, que é completamente, 

ele é facilmente interpretado por qual quer programador por ter um padrão logico, muito simples. linguagens: 
``C, incluindo C,C++, C#,Java, Javascript, Perl, Python e muitas outras linguagem.`` 
Ou seja, é utilizado para a grande maioria das linguagem de programação.

### Para simplificar mais ainda, o JSON é:
Ele é utilizado para troca e armazenamento de dados, facil de aprender e de ser gerado.

## Te mosrtrei o que é, mas como é contruido?
Vou te explicar:

``JSON ele é composto por duas estrutura`` 

* Uma coleção de pares nome/valor. Em várias linguagens, isso é realizado como um ``objeto`` , ``registro``, ``struct``, ``dicionário``, ``tabela hash``, ``lista com chave`` ou ``array associativo``.

* Uma lista ordenada de valores. Na maioria das linguagens, isso é realizado como um array , vetor, lista ou sequência.

``Essas são estruturas de dados universais.``

## Quais são as linguagem que aceitam ou com facil integração JSON?

1. JavaScript → ``JSON.parse()`` e ``JSON.stringify()``
2. Python → ``Módulo json``
3. Java → ``Jackson`` ou ``Gson``
4. C# → ``System.Text.Json`` e ``Newtonsoft.Json``
5. PHP → ``json_encode()`` e ``json_decode()``
6. Ruby → ``Módulo json``
7. Go → ``Pacote encoding/json``
8. Swift → ``JSONSerialization``
9. Dart (Flutter) → dart:convert (``jsonDecode()`` e ``jsonEncode()``)
10. Rust → Biblioteca ``serde_json``

## Qual é o formato JSON?
**Esse é um modelo em que fizemos para meu estudo sobre JSON.**

Mas aqui podemos ver que a criação do JSON é bem simples, basicamente uma estrutura baseada em pares de Chaves-valor
``{ }`` podendo conter ``arrays``, ``numeros``, ``string`` ``booleanos`` e ``valores nulos`` 

```
{
  "project":  "Estudo",
  "studies_log": [
    {
      "start_date": "25/02/2025",
      "end_date": "04/03/2025",
      "total_points": "",
      "total_tasks": ""
    },
    {
      "start_date": "",
      "end_date": "",
      "total_points": "",
      "total_tasks": ""
    }
  ]
}
```

(``Outro exemplo``)

```

{
  "nome": "João",
  "idade": 25,
  "email": "joao@email.com",
  "casado": false,
  "filhos": ["Ana", "Pedro"],
  "endereco": {
    "rua": "Av. Paulista",
    "numero": 100,
    "cidade": "São Paulo"
  }
}

```

Aqui são as regras do JSON

✅ As chaves devem estar entre aspas (" ")

✅ Os valores podem ser:

* Strings ("texto")
* Números (25, 3.14)
* Booleanos (true, false)
* Arrays ([1, 2, 3])
* Objetos ({ "chave": "valor" })
* null (valor nulo)

❌ Sem vírgula no último item de um objeto ou array.

## Como criar um JSON na pratica?

1. Você pode escrever   um arquivo JSON (``dados.json``) e salvar o conteudo nele.

2. Criando o JSON em diferentes linguagem.

### ``Javascript``

```

const dados = {
  nome: "João",
  idade: 25
};

const jsonString = JSON.stringify(dados);  // Converte objeto para JSON (string)

console.log(jsonString);


```
### ``Python``

```

const dados = {
  nome: "João",
  idade: 25
};

const jsonString = JSON.stringify(dados);  // Converte objeto para JSON (string)

console.log(jsonString);

```

### ``JAVA``

```

import org.json.JSONObject;

public class Main {
    public static void main(String[] args) {
        JSONObject json = new JSONObject();
        json.put("nome", "João");
        json.put("idade", 25);
        
        System.out.println(json.toString());
    }
}

```

### ``PHP``
O PHP é um pouco diferente em relação as chaves, mas a estrutura, é "a mesma".

```

<?php
// Criando um array associativo (estrutura de dados em PHP)
$dados = [
    "nome" => "João",
    "idade" => 25,
    "email" => "joao@email.com",
    "casado" => false,
    "filhos" => ["Ana", "Pedro"],
    "endereco" => [
        "rua" => "Av. Paulista",
        "numero" => 100,
        "cidade" => "São Paulo"
    ]
];

// Convertendo para JSON
$json = json_encode($dados, JSON_PRETTY_PRINT | JSON_UNESCAPED_UNICODE);

// Exibindo o JSON formatado
echo $json;
?>

```


Mas por fim esse é o Json, ele recolhe dados do usuarios ou dados, deu pra perceber que ele não é um bicho de 300 cabeça é só uma, então agradeço de já a sua leitura e por favor, não enche o meu ``saco``.

![alt text](/Images/image.png)

