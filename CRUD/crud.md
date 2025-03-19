# É CRUD não GRUDE

![alt text](/Images/CRUD.png)

## Afinal, o que é um CRUD?

CRUD nada mais é do que um acrônomo para ``CREATE``, ``READ``, ``UPDATE``, ``DELETE`` que representão as quatros operações basicas de um sistema de gestão de ``dados``. Essas operações são essenciais para qualquer aplicação que manipule informação armazenadas em banco de dados.

``E para você que não sabe o que é a porra de um ACRÔNOMO, É A JUNÇÃO DAS INICIAIS DAS PALAVRAS``

## Bom, mas para que serve o CRUD?

CRUD é um conceito fundamental no desenvolvimento de qualquer software, que necessite armazenar e gerenciar dados, ele é para garantir que os dados sejam:

* ``Criados``<br>
* ``Lidos``<br>
* ``Atualizados``<br>
e
* ``Deletados``<br>

sendo isso feitas de forma organizada e eficiente.

## Funcionalidades do CRUD

1. ``Criar (CREATE)``
Essa operação permite inserir de novos registros no banco de dados, como SQL, isso pode ser feito com o comando ``INSERT``:

```

INSERT INTO usuarios (nome, email) VALUES ('João Silva', 'joao@email.com');

```

2. ``Read (Ler)``
A leitura dos dados permite recuperar informações armazenadas. Em SQL, utilizamos o comando ``SELECT``:
```

SELECT * FROM usuarios;

```

3. ``Update (Atualizar)``
A operação de atualização permite modificar dados existentes. O comando SQL correspondente é ``UPDATE:``
```

UPDATE usuarios SET email = 'joaosilva@email.com' WHERE nome = 'João Silva';

```

4. ``Delete (Excluir)``
A exclusão remove registros do banco de dados. Em SQL, usamos o comando ``DELETE``:
```

DELETE FROM usuarios WHERE nome = 'João Silva';

```

## Como podemos utilizar o CRUD em uma aplicação Web?<br>
CRUD pode ser implementado em diversas tecnologias. Um exemplo em PHP com MySQL seria:

## Criando um CRUD em PHP<br>
*``Conexão com o banco de dados``*

```

<?php
$servername = "localhost";
$username = "root";
$password = "";
$dbname = "meubanco";

$conn = new mysqli($servername, $username, $password, $dbname);

if ($conn->connect_error) {
    die("Conexão falhou: " . $conn->connect_error);
}
?>

```

### **Criando um novo usuário** ``(Create)``

```

<?php
$sql = "INSERT INTO usuarios (nome, email) VALUES ('João Silva', 'joao@email.com')";
if ($conn->query($sql) === TRUE) {
    echo "Usuário criado com sucesso";
} else {
    echo "Erro: " . $conn->error;
}
$conn->close();
?>

```

### **Listando usuarios** ``(READ)``

```

<?php
$sql = "SELECT * FROM usuarios";
$result = $conn->query($sql);
if ($result->num_rows > 0) {
    while($row = $result->fetch_assoc()) {
        echo "ID: " . $row["id"]. " - Nome: " . $row["nome"]. " - Email: " . $row["email"]. "<br>";
    }
} else {
    echo "Nenhum usuário encontrado";
}
$conn->close();
?>

```

### **Atualizando um usuário** ``(Update)``

```

<?php
$sql = "UPDATE usuarios SET email='joaosilva@email.com' WHERE nome='João Silva'";
if ($conn->query($sql) === TRUE) {
    echo "Usuário atualizado com sucesso";
} else {
    echo "Erro ao atualizar: " . $conn->error;
}
$conn->close();
?>

```

### **Excluindo um usuário** ``(Delete)``

```

<?php
$sql = "DELETE FROM usuarios WHERE nome='João Silva'";
if ($conn->query($sql) === TRUE) {
    echo "Usuário deletado com sucesso";
} else {
    echo "Erro ao deletar: " . $conn->error;
}
$conn->close();
?>

```

## Irei fazer com JavaScript

```

const express = require('express');
const app = express();
app.use(express.json());

let usuarios = [];

// Create
app.post('/usuarios', (req, res) => {
    const usuario = req.body;
    usuarios.push(usuario);
    res.status(201).send('Usuário criado');
});

// Read
app.get('/usuarios', (req, res) => {
    res.json(usuarios);
});

// Update
app.put('/usuarios/:id', (req, res) => {
    const { id } = req.params;
    usuarios[id] = req.body;
    res.send('Usuário atualizado');
});

// Delete
app.delete('/usuarios/:id', (req, res) => {
    const { id } = req.params;
    usuarios.splice(id, 1);
    res.send('Usuário deletado');
});

app.listen(3000, () => console.log('Servidor rodando na porta 3000'));

```

**Conclusão**

``CRUD`` é um conceito essencial para o ``desenvolvimento de aplicações que manipulam dados``. Com a compreensão desses quatro processos, é possível **construir sistemas robustos** e **funcionais**, garantindo que os dados sejam gerenciados de forma eficaz. A implementação pode ser feita em diversas linguagens e tecnologias, tornando-o um padrão fundamental na programação.

E assim finalizamos o artigo sobre CRUD espero que tenha botado nessa sua cabeça.

![alt text](/Images/CavaloCRUD.png)