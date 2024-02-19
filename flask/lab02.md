# Flask - Lab 02 - Rotas Dinâmicas

No lab anterior, nós conhecemos o Flask e sua documentação, e fizemos o exemplo inicial mais básico possível.
(Caso você tenha pulado, o link é este: [primeiro lab](lab01.md))

Desta vez, iremos entender mais a fundo o que são as **rotas** do Flask, para quê servem e como funcionam.
Primeiro de tudo, vamos relembrar o que são as URLs.


## URLs

Em sua definição mais simples, uma URL é a representação de um recurso da web.

São exemplos de URLs:
- `https://en.wikipedia.org/wiki/Linux`
- `https://github.com/junegunn/fzf`
- `https://info.cern.ch/hypertext/WWW/TheProject.html`

### Partes da URL

A URL pode ser dividida em três partes: `protocol`, `host` e `path`.
```
    https://example.com/over/there
    \___/   \_________/\_________/
      |          |          |   
   protocol    host       path
```

Por exemplo, considerando a seguinte URL:
```
https://github.com/python/cpython
```

- O `protocol` é "https"
- O `host` é "github.com"
- O `path` é "/python/cpython"

Essa divisão pode ser melhor visualizada abaixo:

```
    https://github.com/python/cpython
    \___/   \________/\_____________/
      |          |           |   
   protocol    host        path
```

Algumas regras para as URLs:
- O `path` não é obrigatório. `https://twitter.com` e `https://google.com` são URLs válidas que não possuem `path`. Nesse caso, considera-se que o `path` seja igual a raiz, representada por uma barra (`/`).
- Os `protocolos` que iremos utilizar serão o `http` e `https`. O `https` é a versão segura (criptografada) do `http`. Para fins de desenvolvimento e testes, não há problema em utilizarmos o `http`, que é muito mais simples do que o `https`.
- A ordem `protocol`, `host`, `path` deve sempre ser respeitada, ou seja, não pode haver um `path` antes do `host`.


## URL do Flask

Quando nós executamos a nossa app hello world no Lab 01, a mensagem exibida pelo Flask foi algo como:
```
 * Serving Flask app 'hello'
 * Debug mode: off
WARNING: This is a development server. Do not use it in a production deployment. Use a production WSGI server instead.
 * Running on http://127.0.0.1:5000
```

Nós utilizamos a URL `http://127.0.0.1:5000` para acessar a app. Essa URL pode ser dividida da seguinte forma:
```
    http://127.0.0.1:5000
    \__/   \____________/
     |           |
  protocol  host + port
```
Nesse caso, não temos somente o `host`, mas sim a combinação `host:port`.

O `host` é o endereço IP `127.0.0.1`. Esse endereço em específico é chamado de `localhost`, e representa o seu próprio computador.
(O `localhost` é análogo ao pronome pessoal "eu", que sempre refere-se à própria pessoa.)

A `port` é um número inteiro entre 0 e 65535.
Esse número representa um serviço.
Por exemplo, a porta padrão do protocolo HTTP é a 80, enquanto a do protocolo SMTP, utilizado no envio de e-mails, é a 25. O protocolo SSH, por sua vez, utiliza a porta 22.
Ou seja, cada protocolo de rede possui uma porta específica, registrada no órgão IANA. (a lista completa está disponível [neste link](https://www.iana.org/assignments/service-names-port-numbers/service-names-port-numbers.xhtml).)

> [!TIP]
> Sempre que uma URL é acessada sem que uma `port` seja informada, o `protocol` determinará qual `port` será acessada.
Por exemplo, acessar a URL `http://httpforever.com` é equivalente a acessar `http://httpforever.com:80`. A porta utilizada será a 80, que é a porta padrão do protocolo HTTP.
Do mesmo modo, acessar a URL `https://twitter.com` é equivalente a acessar `https://twitter.com:443` (a porta padrão do protocolo HTTPS é a 443).

Então, quando acessamos a URL da nossa aplicação Flask (`http://127.0.0.1:5000`) em nosso navegador, estamos dizendo ao navegador que:

- Utilize o protocolo HTTP
- Para acessar o computador com endereço IP `127.0.0.1` (que nesse caso refere-se ao seu próprio computador)
- Ao invés de utilizar a porta padrão (80), utilize a porta `5000`


## Rotas

Agora que aprendemos melhor como as URLs funcionam, vamos aplicar esse conhecimento no desenvolvimento web com o Flask.
Um dos elementos mais importantes de uma aplicação Flask são as suas rotas.
A rota é uma função associada a um `path`.
Por exemplo, no Quickstart, temos a função `hello_world`:
```python
@app.route("/")
def hello_world():
    return "<p>Hello, World!</p>"
```

O decorator `app.route()` denota qual o path associado à função `hello_world`.
Isso significa que quando o cliente acessar a URL `http://127.0.0.1:5000/`, a função que será executada será a `hello_world.`

Do mesmo modo, podemos definir uma nova rota assim:
```python
@app.route("/teste")
def testando():
    return "<p>Testando - 1, 2, 3...</p>"
```
Dessa vez, quando o cliente acessar a URL `http://127.0.0.1:5000/teste`, a função que será executada será a `testando`.


## Conclusão

Neste segundo Lab sobre Flask, nós aprendemos um pouco mais sobre as URLs e nos aprofundamos nas rotas do Flask.


1. Separe corretamente as seguintes URLs em partes (`protocol`, `host` e `path`):
    - `https://docs.python.org/3/whatsnew/3.12.html`
    - `https://en.wikipedia.org/wiki/Linux`
    - `https://www.google.com/search`
    - `http://127.0.0.1:5000/testando`
    - `http://192.168.0.1/`
2. Crie uma rota `/seu_nome`, mas substitua "seu_nome" pelo seu primeiro nome. Na função da rota, retorne uma breve página de introdução sobre quem é você (nome, idade, profissão, hobbies).


E agora, vamos ao próximo passo de [criar uma rota dinâmica](lab02.md).

---

## Leia Mais

- <https://developer.mozilla.org/en-US/docs/Learn/Common_questions/Web_mechanics/What_is_a_URL>
- Este Lab tem como referência a [RFC 3986](https://datatracker.ietf.org/doc/html/rfc3986). As RFCs são documentos da IETF (Internet Engineering Task Force) que definem padrões sobre como a Internet deve funcionar.
