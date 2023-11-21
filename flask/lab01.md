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

Em seguida, há um exemplo mais simples possível de uma aplicação Flask ("A Minimal Application").
Este é o exemplo:

```python
from flask import Flask

app = Flask(__name__)

@app.route("/")
def hello_world():
    return "<p>Hello, World!</p>"
```

**Agora, tente entender o código acima e também o trecho da documentação do flask que explica esse código.**
Ainda na seção "A Minimal Application", a documentação explica que é possível executar a sua app com o comando `flask --app hello run`. Basta salvar seu arquivo com o nome `hello.py`.
Tente agora fazer isto em seu computador.

Caso tenha dificuldades em utilizar o comando acima, modifique seu arquivo `hello.py` e adicione no final a seguinte linha:

```python
app.run(debug=True)
```

E tente executar seu script normalmente, como você geralmente faz com qualquer outro script.

Para validar se conseguiu fazer o hello world funcionar, abra o seu navegador na URL <http://127.0.0.1:5000>. Caso a mensagem "Hello, World!" apareça em sua tela: **parabéns**, você concluiu este primeiro lab!

Agora, responda às seguintes perguntas:

1. O que é o Quickstart?
2. Como você alteraria o código para exibir uma mensagem diferente de "Hello, World!"? 
3. Qual a importância de uma documentação bem escrita em seus projetos?