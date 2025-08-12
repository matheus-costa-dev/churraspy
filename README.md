# Churraspy ![Static Badge](https://img.shields.io/badge/Status-Concluido-green)

[![Estrelas](https://img.shields.io/github/stars/matheus-costa-dev/churraspy?style=social)](https://github.com/matheus-costa-dev/churraspy/stargazers) [![Contribuidores](https://img.shields.io/github/contributors/matheus-costa-dev/churraspy)](https://github.com/matheus-costa-dev/churraspy/graphs/contributors) [![Tamanho do Repositório](https://img.shields.io/github/repo-size/matheus-costa-dev/churraspy)](https://github.com/matheus-costa-dev/churraspy) [![Linguagens](https://img.shields.io/github/languages/top/matheus-costa-dev/churraspy)](https://github.com/matheus-costa-dev/churraspy)  
[![Último Commit](https://img.shields.io/github/last-commit/matheus-costa-dev/churraspy)](https://github.com/matheus-costa-dev/churraspy/commits/main) [![Issues](https://img.shields.io/github/issues/matheus-costa-dev/churraspy)](https://github.com/matheus-costa-dev/churraspy/issues) 
[![License](https://img.shields.io/github/license/matheus-costa-dev/churraspy)](https://github.com/matheus-costa-dev/churraspy/blob/main/LICENSE)

## Demonstração

https://github.com/user-attachments/assets/a110362d-3312-494e-8286-20487b708ab6

## Índice :pushpin:

- [Descrição](#descrição-books)
- [Funcionalidades](#funcionalidades-do-projeto-hammer)
- [Como rodar localmente](#como-rodar-localmente-desktop-computer)
    - [Preparação do ambiente](#preparação-do-ambiente-shell)
    - [Passo a passo](#passo-a-passo-walking)
- [Principais arquivos e pastas](#principais-arquivos-e-pastas-file-folder)
- [Tecnologias utilizadas](#tecnologias-utilizadas-computer)
- [Desenvolvedores](#desenvolvedores-construction_worker)
- [Ideias de novas features](#ideias-de-novas-features-sparkles)
- [Como contribuir](#como-contribuir-handshake)
- [Links](#links-globe_with_meridians)

## Descrição :books:

Aplicação feita em python que visa calcular o que será necessário para realizar um churrasco. Os dados dos alimentos e bebidas são obtidos de um webscrapping feito no site do supermercado princesa maricá e armazenados no banco de dados sqlite. O projeto está configurado e rodando no servidor do python anywhere, para acessar <a href="https://matheuspc.pythonanywhere.com/"> clique aqui </a>

## Funcionalidades do projeto :hammer:

- `Web Scrapping`: Pesquisa de preço no site do mercado
- `Armazenamento de Dados`: Armazena os preços em um banco de dados, sendo possível um histórico de preços
- `Orçamento`: Permite que o cliente selecione os itens desejados e gera um orçamento real, com base nos preços atuais

## Como rodar localmente :desktop-computer:

### Preparação do ambiente :shell:

* Se tiver o git instalado no computador: vá no terminal do seu computador e digite o comando
    ```{bash}
    git clone https://github.com/matheus-costa-dev/churraspy
    ```
* Se não tiver o git instalado: no repositorio do github https://github.com/matheus-costa-dev/churraspy clique em code e aperte em download zip, clique com o botão direito e extraia o arquivo. Assim que terminar de extrair, renomeia para churraspy

Ao final do processo entre na pasta churraspy

### Passo a passo :walking: 

* Crie um ambiente virtual com o seguinte comando
    ```{bash}
    python -m venv env
    ```
* Ative o ambiente virtual com o comando
    * Windowns: 
        ```{bash}
        env\scripts\activate
        ```
    * Linux e Mac:
      ```{bash}
      source env\bin\activate
      ```
* instale as bibliotecas necessárias
    ```{bash}
    pip install -r requirements.txt
    ```
* Execute o script app.py
    ```{bash}
    python3 app.py
    ```
    :warning:Obs: veja como ta instalado o python no seu computador, pode ser de outra forma como por exemplo <code> py app.py </code> ou <code> python app.py </code>

ele irá rodar e criar um servidor local na sua maquina, no endereço **http://127.0.0.1:5000/**
copie esse endereço e cole na url do seu navegador

## Principais arquivos e pastas :file-folder:

* requirements.txt: Arquivo que informa quais bibliotecas são necessárias pra rodar essa aplicação
* members.json: Arquivo onde as informações dos seus desenvolvedores estão armazenadas.
* app.py: é o script principal onde irá executar o servidor.
* instance: é onde fica os bancos de dados, foram feitos 2, um para armazenar os dados dos preços e outro para o que a pessoa pediu no nosso site para calcular o churrasco.
* py_scripts: Fica armazenado os codigos python.
    * calculo_churras.py: Logica do calculo que será retornado para o usuário
    * SQL.py: Armazena os dados obtidos do web_scrapping.py feito no site do supermercado princesa no banco de dados Churrasquin.db
    * SQL_session.py: Armazena os dados do pedido do que irá usar no churrasco, é inserido no banco de dados app.db
    * Utilidade.py: Script intermediário que traz os dados do script SQL e retorna em formato de dicionário
    * web_scrapping.py: Obtem os dados do supermercado princesa através de um request, é o script mais crítico devido a possível alteração constante onde os dados são armazenados no seu site
* routes: Define as rotas que o site terá
    * rotas.py: são definidos as rotas do nosso site e o que fará cada uma delas, lá atualmente tem 3 rotas index, calcular e resultado. index é a pagina inicial, o calcular é um endpoint que recebe os dados do que o usuário selecionou e redirecionar pra rota resultado
* routines: Rotinas isoladas que devem ocorrer paralelo ao site
    * atualizar_db.py: Atualiza o banco de dados dos preços dos produtos, deve ser rodado em um agendador de tarefas do windows ou crontab do linux, de forma isolada pode ser rodado manualmente.
* templates: Fica nossos codigos html de cada rota e o que terá, a base.html define o corpo do site e o index.html e resultado.html defini qual é o conteudo que o usuário terá a disposição, essas duas são extensões da base.html
* static: Fica os arquivos css, js e imagens

## Tecnologias utilizadas :computer:

<div>
    <table>
        <tr>
            <th><code><img width="50" src="https://raw.githubusercontent.com/marwin1991/profile-technology-icons/refs/heads/main/icons/python.png" alt="Python" title="Python"/></code></th>
            <th><code><img width="50" src="https://raw.githubusercontent.com/marwin1991/profile-technology-icons/refs/heads/main/icons/javascript.png" alt="JavaScript" title="JavaScript"/></code></th>
            <th><code><img width="50" src="https://raw.githubusercontent.com/marwin1991/profile-technology-icons/refs/heads/main/icons/sqlite.png" alt="SQLite" title="SQLite"/></code></th>
            <th><code><img width="50" src="https://raw.githubusercontent.com/marwin1991/profile-technology-icons/refs/heads/main/icons/html.png" alt="HTML" title="HTML"/></code></th>
            <th><code><img width="50" src="https://raw.githubusercontent.com/marwin1991/profile-technology-icons/refs/heads/main/icons/css.png" alt="CSS" title="CSS"/></code></th>
            <th><code><img width="50" src="https://raw.githubusercontent.com/marwin1991/profile-technology-icons/refs/heads/main/icons/bootstrap.png" alt="Bootstrap" title="Bootstrap"/></code></th>
            <th><code><img width="50" src="https://raw.githubusercontent.com/marwin1991/profile-technology-icons/refs/heads/main/icons/git.png" alt="Git" title="Git"/></code></th>
            <th><code><img width="50" src="https://raw.githubusercontent.com/marwin1991/profile-technology-icons/refs/heads/main/icons/github.png" alt="GitHub" title="GitHub"/></code></th>
            <th><code><img width="50" src="https://raw.githubusercontent.com/marwin1991/profile-technology-icons/refs/heads/main/icons/pandas.png" alt="Pandas" title="Pandas"/></code></th>
        </tr>
        <tr>
            <td><h5>Python</h5></td>
            <td><h5>JavaScript</h5></td>
            <td><h5>SQLite</h5></td>
            <td><h5>HTML</h5></td>
            <td><h5>CSS</h5></td>
            <td><h5>Bootstrap</h5></td>
            <td><h5>Git</h5></td>
            <td><h5>GitHub</h5></td>
            <td><h5>Pandas</h5></td>
        </tr>
    </table>
</div>

## Desenvolvedores :construction_worker:

### Back-End :wrench:

| [<img loading="lazy" src="https://avatars.githubusercontent.com/matheus-costa-dev" width=115><br><sub>Matheus Pereira Costa</sub>](https://github.com/matheus-costa-dev) | [<img loading="lazy" src="https://avatars.githubusercontent.com/rafapcdev" width=115><br><sub>Rafael Costa</sub>](https://github.com/rafapcdev) | [<img loading="lazy" src="https://avatars.githubusercontent.com/hugokoppe" width=115><br><sub>Hugo Koppe</sub>](https://github.com/hugokoppe) | [<img loading="lazy" src="https://avatars.githubusercontent.com/dvsalvaya" width=115><br><sub>Davi salvaya</sub>](https://github.com/dvsalvaya) | [<img loading="lazy" src="https://avatars.githubusercontent.com/Rodrigo-Avieira" width=115><br><sub>Rodrigo Vieira</sub>](https://github.com/Rodrigo-Avieira) | [<img loading="lazy" src="https://avatars.githubusercontent.com/carolinesvazz" width=115><br><sub>Caroline Vazz</sub>](https://github.com/carolinesvazz) |
| :---: | :---: | :---: | :---: | :---: | :---: |

### Front-End :art:

| [<img loading="lazy" src="https://avatars.githubusercontent.com/matheus-costa-dev" width=115><br><sub>Matheus Pereira Costa</sub>](https://github.com/matheus-costa-dev) | [<img loading="lazy" src="https://avatars.githubusercontent.com/Ju-Rodrigues22" width=115><br><sub>Juliana Rodrigues Ferreira</sub>](https://github.com/Ju-Rodrigues22) |
| :---: | :---: |

## Ideias de novas features :sparkles:

1. O site pode conter uma nova rota chamada histórico no qual irá demonstra através de gráfico a variação de preço dos produtos
2. Na pagina inicial do site o usuário poder selecionar a quantidade que quer de cada item ou ao menos dentro daquela seção ele considera mais importante pra comprar mais daquele produto específico do que de outro.
3. Criar um relatorio dinâmico estilo power bi so que no python, exemplo com bibliotecas Taipy 

## Como Contribuir :handshake:

Se você deseja contribuir para o projeto, siga os passos abaixo:

1. **Fork o repositório** clicando no botão "Fork" no topo da página.
2. **Crie uma branch** para sua modificação:
   ```bash
   git checkout -b feature/minha-nova-funcionalidade
   ```
3. **Realize as alterações** no código e faça o commit das mudanças:
   ```bash
   git commit -am 'Adicionando nova funcionalidade'
   ```
4. **Envie suas mudanças** para o repositório remoto:
   ```bash
   git push origin feature/minha-nova-funcionalidade
   ```
5. **Abra um Pull Request** para discutir e revisar suas alterações.

## Links :globe_with_meridians:

- [Aplicação ao vivo](https://matheuspc.pythonanywhere.com/)
- [Montar Readme.md](https://www.alura.com.br/artigos/escrever-bom-readme)
- [Gerar icones](https://marwin1991.github.io/profile-technology-icons/)


