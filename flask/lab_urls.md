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

A URL é dividida em 5 partes:
- `scheme`
- `authority`
- `path`
- `query`
- `fragment`

Essas partes são organizadas da seguinte forma:
```
    foo://example.com:8042/over/there?name=ferret#nose
    \_/   \______________/\_________/ \_________/ \__/
     |           |            |            |        |
  scheme     authority       path        query   fragment
```

Por exemplo, na seguinte URL:
```
https://www.youtube.com/watch?v=dQw4w9WgXcQ
```

- O `scheme` é "https"
- O `authority` é "www.youtube.com"
- O `path` é "/watch"
- A `query` é "v=dQw4w9WgXcQ".

Essa divisão pode ser melhor visualizada abaixo:

```
    https://www.youtube.com/watch?v=dQw4w9WgXcQ
    \___/   \_____________/\____/ \___________/
      |           |           |         |
    scheme    authority     path      query
```

Algumas regras para as URLs:
- O `path`, a `query` e o `fragment` não são obrigatórios. Por exemplo, `https://twitter.com` é uma URL válida que não possui path, query nem fragment.
- O `scheme` mais comum é o `https`, a versão segura do protocolo HTTP, que desde o início da web até os dias de hoje é o principal protocolo da web. Porém, há uma lista completa de todos os schemes oficiais [aqui](https://www.iana.org/assignments/uri-schemes/uri-schemes.xhtml).
- O `path` sempre inicia em uma barra (`/`), e a uma `query` sempre inicia em uma interrogação (`?`). Da mesma forma, o `fragment` sempre inicia em uma _hashtag_ (`#`).
- A ordem `scheme`, `authority`, `path`, `query`, `fragment` deve sempre ser respeitada, ou seja, não pode haver uma `query` antes do `path`.


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
   scheme    authority
```

O `scheme` nesse caso representa o protocolo HTTP, o `authority` representa o servidor acessado, e tanto o `path` quanto a `query` e o `fragment` são vazios.

O `authority` por sua vez também é separado em duas partes: `host` e `porta`.

Nesse caso, o `host` é o endereço IP 127.0.0.1. Esse endereço em específico é chamado de `localhost`, e representa o seu próprio computador.
Na linguística, o `localhost` é análogo ao pronome pessoal "eu", que sempre refere-se à própria pessoa.

A `porta` é um número inteiro que vai de 0 até 65535 e representa um serviço. Por exemplo, a porta padrão do protocolo HTTP é a 80, já a do protocolo SMTP, utilizado no envio de e-mails, é a 25. Por sua vez, o protocolo FTP, de transferência de arquivos, utiliza as portas 20 e 21. Cada protocolo de rede possui uma porta específica, registrada na IANA, e a lista completa está disponível [neste link](https://www.iana.org/assignments/service-names-port-numbers/service-names-port-numbers.xhtml).

> [!TIP]
> Sempre que uma URL é acessada sem que uma `porta` seja informada, o `scheme` determinará qual `porta` será acessada.
Por exemplo, acessar a URL `http://httpforever.com` é equivalente a acessar `http://httpforever.com:80`. A porta utilizada será a 80, porta padrão do protocolo HTTP.
Do mesmo modo, acessar a URL `https://twitter.com` é equivalente a acessar `https://twitter.com:443` (a porta padrão do protocolo HTTPS é a 443).

Então, quando acessamos a URL da nossa aplicação Flask (`http://127.0.0.1:5000`) em nosso navegador, estamos dizendo ao navegador que:

- Utilize o protocolo HTTP
- Para acessar o computador com endereço IP `127.0.0.1` (que nesse caso refere-se ao seu próprio computador)
- Ao invés de utilizar a porta padrão (80), utilize a porta `5000`


## Rotas

Agora que aprendemos melhor como as URLs
https://flask.palletsprojects.com/en/3.0.x/api/#flask.Flask.route

----------------------------------------------------

## Conclusão

Neste segundo Lab sobre Flask, nós aprendemos um pouco mais sobre as URLs e nos aprofundamos nas rotas do Flask.
Também aprendemos a criar nossas próprias rotas, e a utilizar as `queries` das URLs para enviar valores ao Flask.



1. Separe corretamente as seguintes URLs em partes:
    - `https://docs.python.org/3/whatsnew/3.12.html`
    - `https://en.wikipedia.org/wiki/Linux#Hardware_support`
    - `https://www.google.com/search?q=ubuntu`
2. Como você alteraria o código para exibir uma mensagem diferente de "Hello, World!"? 
3. Qual a importância de uma documentação bem escrita em seus projetos?


E agora, vamos ao próximo passo de [criar uma rota dinâmica](lab02.md).

---

## Leia Mais

- <https://developer.mozilla.org/en-US/docs/Learn/Common_questions/Web_mechanics/What_is_a_URL>
- Este Lab tem como referência a [RFC 3986](https://datatracker.ietf.org/doc/html/rfc3986). As RFCs são documentos da IETF (Internet Engineering Task Force) que definem padrões sobre como a Internet deve funcionar.
