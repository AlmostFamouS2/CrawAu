# CrawAu
Essa é uma ferramenta para coleta de informações web

A ideia é conseguir o maior número de informações sobre diretórios e subdomínios da aplicação sem realizar um Brute Force

A ferramenta "simula" a navegação de um usuário comum acessando a aplicação, dessa forma não chama a atenção dos mecanismos de defesa

Ela realiza uma consulta na URL passada e identifica todos os links presentes na página, após isso retorna todos os links que pertencem a esse domínio

Existe também a possibilidade de realizar uma consulta em profundidade, onde a ferramenta após descobrir os links, entra neles e realiza uma nova consulta

## Instalação
1) ``git clone https://github.com/SQU4NCH/CrawAu``
2) ``cd CrawAu``
3) ``python3 -m pip install -r requirements.txt``
4) ``python3 crawau.py --help``

## Opções

```
usage: crawau.py [-h] [-q] [-d DEEP] [--random-agent] [-o FILE_NAME] [--no-robots] [--header HEADER] target

positional arguments:
  target           Target url

options:
  -h, --help       show this help message and exit
  -q, --quiet      Suppress Output
  -d DEEP          Deeping level for crawler (default: 0)
  --random-agent   Random user agent for requests (default: CrawAu)
  -o FILE_NAME     File to save the result
  --no-robots      Not look for robots.txt (default: no)
  --header HEADER  header key:value (Ex: "Authorization: Basic YWxhZGRpbjpvcGVuc2VzYW1l")
```

## Exemplo

```
➜ python3 crawau.py squ4nch.github.io

    __________________
  <    CrawAu 0.6.0  >
    ------------------
                \   ^__^
                 \  (oo)\_______
                    (__)\       )\/\
                        ||-----||
                        ||     ||

    By: Squ4nch
    

[*] Conectando a squ4nch.github.io
[+] Status Code 200
[+] Servidor: GitHub.com
[*] Verificando robots.txt
[+] robots.txt existe
[*] Conteúdo de robots.txt:

Sitemap: https://squ4nch.github.io//sitemap.xml


[*] Extraindo links presentes na página

http://squ4nch.github.io//whoami
http://squ4nch.github.io//write%20up/Desafio-Realista-1-e-2/
http://squ4nch.github.io/#main
http://squ4nch.github.io//categories
http://squ4nch.github.io//write%20up/Desafio-Realista-7/
http://squ4nch.github.io//write%20up/Daily-Bugle/
http://squ4nch.github.io/#
http://squ4nch.github.io//page2/
http://squ4nch.github.io//page3/
http://squ4nch.github.io//opsec/Ataques-de-desanonimiza%C3%A7%C3%A3o-contra-a-rede-Tor/
http://squ4nch.github.io//write%20up/Desafio-Realista-3-e-4/
http://squ4nch.github.io/#footer
http://squ4nch.github.io/#site-nav
http://squ4nch.github.io//

[*] Encontrados mas possivelmente fora do escopo:

https://github.com/SQU4NCH
https://www.instagram.com/ltxsecurity/
https://www.linkedin.com/in/leo-teodoro/

```
