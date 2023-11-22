# Flask - Lab 01 - Introdução

Flask é um *framework web* escrito na linguagem Python. Os frameworks web são ferramentas que têm como objetivo permitir o desenvolvimento de sistemas web, tais como *websites* e *APIs* de uma forma fácil e simples. Para isso, o Flask dispõe de uma gama de funcionalidades que auxiliam em todo o processo do desenvolvimento da sua aplicação.

Neste lab inicial, você irá conhecer a documentação oficial do Flask, e desenvolver sua primeira aplicação _web_ com o uso desse framework.

## Documentação

A maioria das bibliotecas que você utilizará possui em sua documentação uma seção denominada "Quickstart" ou "Getting Started". Como o nome sugere, essa seção contém os passos mínimos necessários para a utilização da biblioteca. O Flask possui, por sua vez, essa seção em sua documentação oficial.

A documentação pode ser encontrada geralmente no site oficial da biblioteca, ou até mesmo no repositório do projeto. No caso do flask, a sua documentação está no site: <https://flask.palletsprojects.com/en/3.0.x/>.

> [!TIP]
> Para todo desenvolvedor, aprender a navegar pelas documentações e entendê-las é uma habilidade fundamental. Nelas que você encontrará as informações mais corretas e atualizadas sobre uma biblioteca, software, framework ou sistema.
> Outros recursos como tutoriais e artigos podem estar desatualizados, porém a documentação oficial sempre compreenderá as últimas informações. Além disso, ler documentações regularmente contribui muito para sua própria habilidade de escrita de docs para seus próprios projetos.


## Quickstart

A seção "Quickstart" é bastante atrativa para novos usuários das bibliotecas, pois ela geralmente oferece um caminho mais curto possível para conseguir colocar a mão na massa.

No caso do Flask, a página do Quickstart é esta: <https://flask.palletsprojects.com/en/3.0.x/quickstart/>
E logo em seu início é recomendado que vá primeiro para a página "Installation", para configurar a biblioteca em seu computador antes de iniciar.


## Installation

Nesta seção, em "Python Version", é recomendado o uso da última versão disponível do Python.

Depois, em "Virtual environments", é recomendado o uso dos ambientes virtuais, ou `venvs`.
Esses ambientes são uma forma de isolar as versões de dependências entre projetos. Dessa forma, não há conflitos de versões de bibliotecas em seu sistema.
Caso esteja iniciando um projeto, eu recomendo a utilização do `venv`. Caso esteja apenas fazendo um exemplo simples e rápido, como é o nosso caso, esta etapa pode ser pulada.

O próximo passo é a seção "Install Flask", e consiste de executar o comando:

```
pip install Flask
```

> [!IMPORTANT]
> Perceba que na documentação, cada comando inicia com um caractere `$`. Ele não deve ser incluído no comando que você irá digitar no seu terminal; ele apenas representa o prompt do seu sistema. Essa representação é muito comum em tutoriais e documentações.

Caso não haja nenhum erro, o Flask estará instalado em seu virtualenv.


## A Minimal Application

Voltando para o Quickstart, seguimos para a seção "A Minimal Application".
Nela, há um exemplo mais simples possível de uma aplicação Flask ("A Minimal Application").
Este é o exemplo:

```python
from flask import Flask

app = Flask(__name__)

@app.route("/")
def hello_world():
    return "<p>Hello, World!</p>"
```

**Agora, vamos entender o código acima e também o trecho da documentação do flask que explica esse código.**

> First we imported the Flask class. An instance of this class will be our WSGI application.
Esta parte refere-se à primeira linha do código, `from flask import Flask`.
O nome `Flask`, com F maiúsculo, é a classe Flask. A nossa aplicação será uma instância (ou objeto) dessa classe.

> Next we create an instance of this class. The first argument is the name of the application’s module or package. `__name__` is a convenient shortcut for this that is appropriate for most cases. This is needed so that Flask knows where to look for resources such as templates and static files.
Esta parte refere-se à linha `app = Flask(__name__)`.
A variável `app` recebe a instância (objeto) da classe Flask, e o parâmetro passado dentro dos parênteses é o nome da app. Por padrão, no Python, essa variável especial `__name__` contém o nome do seu módulo, nesse caso será `__main__`.

> We then use the route() decorator to tell Flask what URL should trigger our function.
O decorator `@app.route("/")` associa uma URL a uma função do Python. Nesse caso, a URL "/" refere-se ao índice do site. Por exemplo, quando você acessa o site <https://youtube.com>, sem mais nada depois do `.com`, você está acessando a rota "/" do site.
Logo abaixo do `app.route()`, há a linha `def hello_world():`, que declara a função que será executada quando a URL "/" do site for acessada.

> The function returns the message we want to display in the user’s browser. The default content type is HTML, so HTML in the string will be rendered by the browser.
Esse trecho refere-se à linha `return "<p>Hello, World!</p>"`. A função retornará o valor `"<p>Hello, World!</p>"` para o cliente que acessou o site na rota "/", e esse valor deverá ser renderizado e exibido em sua tela pelo navegador.


## Executando a app

Ainda na seção "A Minimal Application", a documentação explica como executar a aplicação:


```
flask --app hello run
```

Basta salvar seu arquivo com o nome `hello.py`.
Tente agora fazer isto em seu computador.

Caso tenha dificuldades em utilizar o comando acima, modifique seu arquivo `hello.py` e adicione no final a seguinte linha:

```python
app.run(debug=True)
```

E tente executar seu script normalmente, como você geralmente faz com qualquer outro script.


## Acessando sua primeira app

Agora, o Flask está executando em seu computador e aguardando algum cliente acessar a app.

Para acessar a app e validar se o hello world está funcionando corretamente, abra o seu navegador na URL <http://127.0.0.1:5000>. Caso a mensagem "Hello, World!" apareça em sua tela: **parabéns**, você concluiu este primeiro lab! :tada: :tada:



Mas, antes de finalizarmos, responda às seguintes perguntas:

1. O que é o Quickstart?
2. Como você alteraria o código para exibir uma mensagem diferente de "Hello, World!"? 
3. Qual a importância de uma documentação bem escrita em seus projetos?


E agora, vamos ao próximo passo de [criar uma rota dinâmica](lab02.md).

