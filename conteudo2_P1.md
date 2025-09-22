Guia de estudos – Prova de integração e entrega contínua

**1\. Fundamentos de CI/CD e Cultura DevOps**

**Integração Contínua (CI)** é a prática de mesclar o código de vários desenvolvedores a um repositório compartilhado de forma frequente, geralmente várias vezes ao dia. Cada integração dispara um processo automatizado de compilação (build) e execução de testes para detectar problemas o mais cedo possível.

**Entrega Contínua (CD)** é uma extensão da CI que garante que o software, após passar por todos os testes, esteja sempre em um estado pronto para ser implantado em produção. O processo de implantação é automatizado para minimizar erros humanos.

**Cultura DevOps** é a base para o sucesso de CI/CD. Ela promove a colaboração e comunicação entre as equipes de desenvolvimento (Dev) e operações (Ops) para otimizar todo o ciclo de vida do desenvolvimento de software, com foco na entrega contínua de valor ao cliente.

- **Benefícios do CI/CD:**
  - Entregas mais rápidas e frequentes.
  - Redução de erros e retrabalho, com identificação precoce de bugs.
  - Maior eficiência para os desenvolvedores, com menos tarefas manuais.
  - Feedback constante sobre a qualidade do código.
- **Desafios Comuns:**
  - **Mudança cultural** na equipe para adotar práticas ágeis e colaborativas.
  - **Complexidade da infraestrutura** para configurar e manter os ambientes.
  - **Gerenciamento de configuração** para garantir que todas as mudanças sejam versionadas.

**2\. Gerenciamento de Configuração e Controle de Versão com Git**

**Gerenciamento de Configuração (GC)** é a disciplina que controla e documenta todas as mudanças em um projeto, garantindo um ambiente estável e rastreável. O

**Controle de Versão (CV)**, uma parte crucial do GC, foca em rastrear as mudanças nos arquivos ao longo do tempo.

O **Git** é o sistema de controle de versão distribuído que serve como base para todo o processo de CI/CD.

**Sistemas de Controle de Versão:**

- **Local:** O desenvolvedor controla as versões manualmente em seu próprio computador. Simples, mas ineficaz para equipes.
- **Centralizado:** Um servidor central armazena o código. Melhora a coordenação, mas pode ser um ponto de falha.
- **Distribuído (Git):** Cada desenvolvedor possui uma cópia completa do repositório, permitindo trabalho offline e maior flexibilidade para mesclar alterações.

**Comandos Essenciais do Git**

| Comando | Função |
| --- | --- |
| git init | Cria um novo repositório Git em um diretório. |
| git clone &lt;url&gt; | Cria uma cópia local de um repositório remoto existente. |
| git add &lt;arquivo&gt; | Adiciona alterações de um arquivo à área de preparação (stage) para o próximo commit. |
| git commit -m "msg" | Salva as alterações preparadas no histórico local com uma mensagem descritiva. |
| git push | Envia os commits locais para o repositório remoto. |
| git pull | Busca as alterações do repositório remoto e as mescla na sua branch local. |
| git status | Mostra o estado atual dos arquivos (modificados, preparados, etc.). |
| git log | Exibe o histórico de commits. |
| git mv &lt;antigo&gt; &lt;novo&gt; | Renomeia ou move um arquivo, mantendo seu histórico de alterações. |
| git merge &lt;branch&gt; | Mescla as alterações de uma branch em outra. |


**Boas Práticas com Git**

- **Branches:** Crie branches separadas para novas funcionalidades ou correções. Isso isola o trabalho e evita instabilidade na branch principal (main).
- **Pull Requests (PRs):** Antes de mesclar uma branch, crie um Pull Request. Isso permite que outros membros da equipe revisem o código, façam sugestões e aprovem as alterações.
- **Arquivo .gitignore:** Use este arquivo para listar arquivos e diretórios que o Git deve ignorar (ex: dependências, logs, arquivos de configuração local).
- **Versionamento Semântico:** Adote um padrão para os números de versão, geralmente no formato MAJOR.MINOR.PATCH (x.y.z).
  - **MAJOR (x):** Para mudanças que quebram a compatibilidade (incompatible API changes).
  - **MINOR (y):** Para adicionar novas funcionalidades de forma retrocompatível.
  - **PATCH (z):** Para correções de bugs retrocompatíveis.

**3\. Testes Automatizados e Qualidade de Código**

Testes automatizados são a espinha dorsal da CI. Eles rodam a cada integração para garantir que novas alterações não quebrem o que já existe.

**Tipos de Testes**

| Tipo | Objetivo |
| --- | --- |
| **Testes Unitários** | Verificam as menores partes do código (funções, métodos) de forma isolada. |
| **Testes de Integração** | Testam a interação e a comunicação entre diferentes módulos ou componentes do sistema. |
| **Testes de Aceitação** | Verificam se o software atende aos requisitos do cliente e funciona como esperado do ponto de vista do usuário. |


**Métricas de Qualidade:**

- **Cobertura de código:** Percentual do código que é coberto pelos testes.
- **Taxa de sucesso dos testes:** Quantidade de testes que passaram.

**Ferramentas de Teste por Linguagem**

- **Python:** unittest, pytest, nose2.
- **JavaScript:** Mocha, Jest, Jasmine, Cypress.
- **Java:** JUnit, TestNG, Mockito, Selenium.
- **C#:** NUnit, xUnit.net, Moq.
- **Ruby:** RSpec, MiniTest, Capybara.

**4\. Docker: Empacotamento com Contêineres**

**Docker** é uma plataforma que usa contêineres para empacotar uma aplicação com todas as suas dependências (código, bibliotecas, etc.), garantindo que ela funcione de forma consistente em qualquer ambiente.

**Contêineres vs. Máquinas Virtuais (VMs):**

- **VMs** virtualizam o hardware, cada uma com seu próprio sistema operacional completo, o que as torna pesadas.
- **Contêineres** virtualizam o sistema operacional, compartilhando o mesmo kernel do host. São mais leves, rápidos e eficientes em recursos.

**Conceitos Fundamentais do Docker**

- **Imagem:** Um template somente leitura, construído em camadas, que contém as instruções para criar um contêiner (ex: um S.O., o código da aplicação, e dependências).
- **Contêiner:** Uma instância executável de uma imagem. É um ambiente isolado onde a aplicação roda.
- **Dockerfile:** Um arquivo de texto com comandos para construir uma imagem Docker personalizada.
- **Volumes:** Usados para persistir dados gerados por contêineres. Os volumes são armazenados no host e sobrevivem mesmo se o contêiner for removido, sendo essenciais para bancos de dados.
- **Docker Hub:** Um registro público (repositório) de imagens Docker.

**Comandos Essenciais do Docker**

| Comando | Função |
| --- | --- |
| docker pull &lt;imagem&gt; | Baixa uma imagem do Docker Hub. |
| docker images | Lista as imagens salvas localmente. |
| docker run &lt;imagem&gt; | Cria e inicia um contêiner a partir de uma imagem. |
| docker ps | Lista os contêineres em execução. |
| docker stop &lt;id/nome&gt; | Para um contêiner em execução. |
| docker rm &lt;id/nome&gt; | Remove um contêiner parado. |
| docker rmi &lt;imagem&gt; | Remove uma imagem. |
| docker build -t &lt;nome&gt; . | Constrói uma imagem a partir de um Dockerfile no diretório atual. |
| docker push &lt;usuario/imagem&gt; | Envia uma imagem para o Docker Hub. |
| docker-compose up | Inicia uma aplicação multi-contêiner definida em um arquivo docker-compose.yml. |


**Orquestração de Contêineres**

Enquanto o Docker gerencia contêineres individuais, orquestradores como o

**Kubernetes** são usados para gerenciar aplicações complexas com múltiplos contêineres em produção, automatizando a implantação, o escalonamento e o balanceamento de carga.

**5\. Exemplo Prático: API Node.js com Testes e GitHub Actions**

Este exemplo une os conceitos: código no Git, testes automatizados e um pipeline de CI com GitHub Actions.

**1\. A Aplicação:** Uma API RESTful para contatos usando Node.js, Express e MongoDB. \* **Estrutura:** \* app.js: Arquivo principal que configura o servidor Express e a conexão com o banco. \* models/contato.js: Define o schema do Mongoose para os dados do contato. \* routes/contatoRoutes.js: Define as rotas da API (GET, POST, PUT, DELETE).

**2\. Os Testes:** Usando Jest e Supertest para testar os endpoints da API. \* Um arquivo test/app.test.js é criado para: \* Verificar se a rota GET /contatos retorna uma lista (status 200). \* Verificar se POST /contatos cria um novo contato com dados válidos (status 201). \* Verificar se POST /contatos retorna um erro com dados inválidos (status 400).

**3\. O Pipeline de CI (GitHub Actions):** \* Um arquivo de workflow é criado em .github/workflows/test.yml. \* **Gatilho (trigger):** O pipeline é acionado a cada push na branch main. \* **Passos (steps):** 1. actions/checkout@v2: Baixa o código do repositório. 2. actions/setup-node@v2: Configura o ambiente Node.js. 3. run: npm install: Instala as dependências do projeto. 4. run: npm test: Executa os testes automatizados. \* Se qualquer passo falhar (especialmente o de testes), o pipeline falha, e o desenvolvedor é notificado de que a integração quebrou.
