
![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/bz1kjbrlttuif4vvlcxc.png)

O que é ``GIT`` e suas principais funcionalidades.

## O que é o GIT?

Git é basicamente um sistema que registra o historico de alteração feita no seu projeto. que certamente facilita o acompanhamento e a recupera modificações.

Um famoso Controle de versão **``VCS``**

## Para que Serve o Git?

Para entender melhor o Git, vamos pensar na seguinte situação:

Você está em um empresa com diversas pessoas desenvolvendo o mesmo projeto, e você precisa gerenciar, ``imagina o trabalho que daria, gerenciar cada pessoa que contribui no codigo``?

E ai, acha que conseguiria? Sem ter o controle de um gerenciamento na suas mãos?

E é nessa que entra o ``Git``.

## Git Não é GitHub!

Muitas pessoas que entraram no mundo da programação, viu o GIT e o GitHub, e acharam que é a mesma coisa, de primeira vista, admito pode parecer, mas não.

São ferramentas ``totalmente diferente``, mas trabalhando juntos fazem um ótimo desenvolvimento e uma total diferença no seu projeto, tanto na questão de ``eficiencia`` quanto na ``velocidade``.


![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/rroicej4pb00ox3tq7i0.png)

## Para que serve o GIT?

Vamos fazer um suposição, digamos que você está gerenciando uma equipe de desenvolvimento, e você precisa ver o codigo de um dos seus colaboradores, mas calma, só isso não basta, precisamos mais do que isso.

Precisamos manter o ``historico`` dos nossos arquivos e das nossas modificações.

 Até porque estamos falando de um projeto em **grupo** sendo assim, ele é modificado, constantemente, em um unico movimento que é o **``Commit``** que em tradução literal, significa "**Compromisso**" ou "**Comprometer-se**" às alterações em um ``repositorio``.  

 Desta forma, podemos voltar atrás e **``recuperar o estado do sitema``**: como ele era antes, para comparar mudanças ou até mesmo para identificar ``bugs`` e ``estudar otimizações``.

## Como funciona o GIT e quais são as vantagens?

Como o Git guarda todas as informações?

todos os arquivos, assim como historicos, ficam em um **``repositorio``** e existe varios sistemas que gerenciam repositorios assim, como CVS(Sistema de Versões Concorrentes) e SVN (Subversion do Apache).

O Git é uma alternativa com um funcionamento mais interessante ainda: ele é **distribuido** e todo mundo tem uma cópia inteira do repositorio, não apenas o "Servidor principal".

E uma das vantagens de disso é que cada pessoa pode desenvolver offline, realizando seus Commits e outras operações sem depender de uma conexão contante com o servidor principal.

Mas o que é a ferramenta Git exatamente?

>_
>
> **Assim como já havia falado o Git é um sistema de controle de versão distribuido e amplamente adotado.**
>
> O Git nasceu e foi tomando espaço dos outros sistemas de controle.
>
>_

## Como instalar o Git?

Para utilizar o Git, você pode seguir esse passo a passo de como fazer o download e instalar, para cada sistema operacional:

``Windows:``

``Acesse o site oficial do Git em`` "https://git-scm.com/download/win".

Clique no link para download do Git para Windows.
Após o download, execute o instalador.

Siga as instruções do instalador, aceitando as configurações padrão, se não for um usuário avançado.
Conclua a instalação.

``Linux:``

No Linux, você pode instalar o Git usando o gerenciador de pacotes da sua distribuição. Por exemplo, no Ubuntu, use o comando sudo apt-get install git.

Se estiver usando outra distribuição, substitua o comando de acordo.
macOS:

``No macOS``

O Git pode ser instalado de várias maneiras, incluindo o uso do Xcode Command Line Tools, que geralmente já está instalado no sistema.

Abra o Terminal e digite git --version para verificar se o Git está disponível. Se não estiver, o sistema solicitará a instalação.
Siga as instruções para instalar o Git. Com esses passos simples, você pode instalar o Git no seu sistema operacional e começar a usar essa poderosa ferramenta de controle de versão.

## Qual linguagem é do Git?

Uma pergunta, que todo mundo que já desenvolveu, se questiona é:
"Do que é feito o Git".

Inicialmente, como o Git foi contruido com o ``**Linux**`` em mente como plataforma, o git foi desenvolvido pelo ``Shell Script``, que apesar de funcionar como o esperado, amarrava a ferramenta a sistema ``**Linux**``, que tinha os utilitarios necessarios para interpretar o Shwll Script.

Com a popularidade da ferramenta, outros sistemas buscaram dar suporte a ela, através da emulação de um sistema ``**Linux**``, que ficava responsável por executar o Git.

No entanto, o uso da emulação de um sistema ``**Linux**`` tinha impacto na performance da ferramenta nos sistemas operacionais que usavam essa estratégia.

Tendo isso em mente, muitos ``comandos do Git``, inicialmente escritos em Shell Script, foram reescritos na ``linguagem C``, que resultou em ganho de performance em plataformas que não usam o **Shell Script como linguagem de linha de comando oficial**, como é o caso do **Windows**.

## Conceitos fundamentais do Git

### Repositórios, commits e árvores (Trees)

Um **``repositório``** é como uma pasta ou diretório que contém todos os arquivos e o histórico de um projeto.

Já o **``Commmit``**, como havia dito, sua tradução literal é de "Compromisso", que seria uma ação em que você faz uma alteração no projeto, se compromete a salva suas alterações no historico do projeto.

Sendo assim, cada `Commit` é uma entrada no historico que contem informações sobre as alterações feitas.

**``Árvores``**, por ultimo, representando a estrutura do diretório e arquivos em um Commit especifico, que tem como função registrar a organização do projeto ao longo do historico de desenvolvimento.

## Ramificação ``(Branches)`` e Fusões ``(Merges)``

As ``“ramificações”`` ou ``branches`` permitem que você crie **linhas separadas** **de desenvolvimento** para trabalhar em recursos ou correções **sem afetar a linha principal do projeto**.

Cada **branch** é uma ``ramificação`` independente do código-fonte, possibilitando que você **isole** e **desenvolva** **novas funcionalidades**, refatore o código ou faça correções e testes em paralelo, sem interferir no código existente na ``branch principal``, que geralmente é nomeada como ``"main"``.

Em um **projeto com branches diferentes**, a ``fusão``, ou ``merge``, permite combinar as alterações dessas branches de volta à linha principal, quando as alterações estão prontas.


## Versões

## Principais comandos do GIT?

### **Buscar ajuda sobre comandos git**
Ele mostra uma lista de comandos do git
```
git help
```
e se caso você queira mostrar sobre algum git especifico basta apenas você fazer isso:
```
git help commit
```

### **Criar novo repositorio**
```
git init
```

### **Adicionar arquivo/diretório**
Adicionar todos os arquivos/diretório
```
git add .
```

### **Comitar um Arquivo/diretório**
Você vai commitar todas as alteraçõesw
```
git commit -m ""
```

### **Remover diretorio**
```
git rm -r diretorio 
```

### **Clonar um repositorio**
```
git clone git@github.com:leocomelli/curso-git.git
```
Obs: git@github.com:leocomelli/curso-git.git - 
``é onde fica o repositorio que você quer colocar``

### **Atualizar os arquivos no branch atual**
Ele atualiza a sua branch para a versão mais recente do codigo.
```
git pull
```

### **Buscar as alterações, mas não aplica-las no branch atual**
Busca todas as alterações que ainda não foram colocadas na sua branch 
```
git fetch
```

### Enviar Para o Repositório 
```
git push
```

# agora pare de choramingar.
![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/vk8gizng4rq6utze23wa.png)
