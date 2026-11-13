## Aula 01 - Arquitetura Cliente-Servidor

### Introdução
Cliente-servidor usa 3 componentes básicos pra compartilhar recursos de computação
 - cliente: normalmente um computador padrão
 - servidor: normalmente um computador poderoso
 - rede: conecta os clientes aos servidores

Divisão de responsabilidades
 - cliente: interface com o usuário e lógica básica do aplicativo
 - servidor: gerencia o acesso a tudo q envolve o banco de dados e as "regras" ou "lógica" do negócio

Exemplo real
 - cliente → manda um pedido SQL pro servidor → recebe os resultados
 - cliente cuida da GUI, lógica da aplicação e parte da lógica dos negócios
 - servidor cuida do acesso ao banco de dados, lógica dos negócios e gerenciamento da rede


### Papel do cliente
 - gerenciamento de apresentação: interação com o usuário (interface), entrada e consulta de dados
 - lógica do aplicativo: funcionamento do aplicativo, partes simples da lógica do negócio
 - aplicativos de produtividade pessoal: processador de texto, planilha, navegador web, cliente de e-mail etc


### Papel do servidor
 - atendimento a usuários: comunicação e autenticação de usuários, atender as solicitações dos clientes
 - gerenciador de banco de dados: acesso e organização, seleção e atualização de registros/dados
 - execução de regras do negócio
   - procedimentos armazenados no banco de dados
   - procedimentos armazenados em componentes
   - processamento de transações
   - conjuntos de operações relacionadas aos processos de negócio


### Papel da rede
 - infraestrutura pros aplicativos cliente/servidor
 - leva as solicitações do cliente pro servidor
 - transporta os dados resultantes do servidor pro cliente

Padrões mais usados
 - Ethernet (transporte físico)
 - TCP/IP (transporte lógico)
 - HTTP (transporte na internet)


### Processamento cliente-servidor
Processo de software = programa de computador sendo executado numa CPU
 - "processo", "tarefa" e "serviço" podem ser considerados sinônimos
 - processos concorrentes trocam mensagens entre si, prestando serviços uns aos outros pra atender o usuário
 - a "tecnologia" cliente/servidor é composta por vários desses processos


### Como é atualmente
Sistemas distribuídos
 - processos executando de forma concorrente, espalhados em vários pontos da rede
 - comunicação entre processos
 - otimização de hardware
 - reutilização de software
 - software em camadas
 - dados distribuídos
 - mais flexibilidade pra atender os usuários

Peer-to-peer (P2P)
 - não é hierárquico
 - todos os processos são "clones" rodando em todas as máquinas e prestando serviços uns aos outros
 - não existem processos servidores
 - cada processo pode ser cliente e servidor ao mesmo tempo

Cliente-servidor
 - processos distintos: o processo cliente é diferente do processo servidor
 - cliente é sempre cliente, servidor é sempre servidor
 - cada processo fica na plataforma mais conveniente
 - ex: navegador (no cliente) e aplicação web (no servidor)

Um sistema cliente/servidor inclui
 - hardware: servidores, estações de trabalho, rede
 - software
   - sistemas operacionais (clientes e servidores)
   - processos clientes (aplicativos do usuário)
   - processos servidores (banco, web, regras etc)
   - processos de comunicação (entre os dois)


### Características do cliente
 - ATIVO!
 - inicia e termina as conversas com os servidores, pedindo serviços
 - normalmente não se comunica com outros clientes
 - o slide diz q "normalmente não é responsável pela entrada e saída de dados e comunicação com o usuário" (mas isso contradiz o resto da aula, onde a interface com o usuário é papel do cliente)
 - torna a rede transparente pro usuário

### Características do servidor
 - REATIVO
 - execução contínua
 - recebe e responde solicitações dos clientes e de outros servidores
 - presta serviços distribuídos
 - atende vários clientes ou outros servidores ao mesmo tempo


### Estrutura típica de um aplicativo
3 camadas: Interface do Usuário → Regras de Negócio → Banco de Dados

Interface do usuário (camada de apresentação)
 - coleta e apresenta os dados pro usuário
 - inclui: entrada de dados, apresentação de dados, formatações, validações básicas, metáforas visuais, fluxo de formulários/páginas (navegação), lógica de aplicação

Regras de negócio
 - regras do mundo real q precisam ser identificadas pra garantir a coerência das informações
 - dependem só do mundo real: regras burocráticas, políticas, legais, comerciais etc q regem a organização e q devem estar refletidas nos sistemas de informação

Camada de dados
 - armazenamento persistente dos dados
 - inclui: atualização e recuperação de dados, gerenciamento de concorrência, gerenciamento da distribuição dos dados, recuperação de falhas
 - recursos: banco de dados, documentos eletrônicos, imagens, sons etc


### Processos do cliente
 - interface
 - validações básicas
 - lógica local (personalização)
 - fluxo de utilização (sequência de formulários ou páginas)

### Processos do servidor
 - gerenciamento de recursos compartilhados: banco de dados, imagens, documentos
 - lógica corporativa: política de acesso, autenticação de usuários
 - regras de negócio: decisões, cálculos, registro de operações


## Aula 02 - Conceitos gerais, HTTP e HTTPS

### Conceitos gerais
Servidor
 - um programa em execução (processo)
 - num computador ligado em rede
 - q aceita pedidos de programas rodando em outros computadores
 - pra fazer um serviço e responder apropriadamente

Cliente
 - processos q fazem pedidos a processos servidores
 - pedidos vão em mensagens de requisição do cliente pro servidor; as respostas voltam do servidor pro cliente
 - quando o cliente pede uma operação, dizemos q ele requisita uma operação no servidor

Requisição remota = uma interação completa entre cliente e servidor
 - clientes são ativos, servidores são reativos
 - ex: clientes mandam invocações pro servidor e recebem resultados; o servidor tb pode invocar outro servidor (aí ele faz papel de cliente)


### Características do servidor web
Normalmente a resposta é em HTML
 - log com as informações detalhadas das requisições e respostas
 - autenticação de usuários pra conteúdos específicos
 - conteúdo estático: imagens, páginas HTML ou XML
 - conteúdo dinâmico, usando interfaces adequadas (JSP, PHP, Ruby)


### Acesso
DNS (Domain Name System): mapeia nomes de domínio da internet pra endereços de rede (IP)
 - ex: https://g1.globo.com/ → IP 186.192.81.31
 - curiosidade: pra descobrir o IP de um site, abre o terminal e digita `ping` + o site (ex: `ping g1.globo.com`)

O navegador se comunica com um servidor web pra pedir páginas web
 - World Wide Web: sistema pra publicar e acessar recursos e serviços pela internet

URL (Uniform Resource Locator)
 - endereço de rede q aponta pra algum recurso num servidor (endereço completo de um recurso na internet)
 - formato: `<scheme>://<host>/<path>`

URN (Uniform Resource Name)
 - identifica um recurso na web por um nome único e persistente
 - ex: `urn:lex:br:federal:lei:2008-06-19;11705`
 - é raro usar esse termo

URI (Uniform Resource Identifier)
 - cadeia compacta de caracteres pra identificar ou nomear um recurso ou serviço na web
 - é o conceito geral, q engloba URL e URN

Diferença
 - URL é um tipo de URI
 - toda URL é uma URI
 - mas nem toda URI é uma URL


### HTTP
HTTP (HyperText Transfer Protocol)
 - protocolo da camada de aplicação → relativamente fácil de manipular nas aplicações
 - define como navegadores e outros clientes interagem com os servidores web

É do tipo requisição-resposta
 - cliente manda uma mensagem de requisição pro servidor com a URL do recurso
 - servidor procura o caminho e manda uma mensagem de resposta
   - deu certo → manda o conteúdo do arquivo
   - deu errado → erro (ex: 404)

Formato da requisição
```
<método> <URL> HTTP/<versão>
<cabeçalhos - um em cada linha>
<corpo da requisição>
```

Exemplo
```
GET /restaurante/clientes HTTP/1.1
Host: www.nomedaempresa.com.br
Accept: text/html
Accept-language: pt-br
```
 - método GET pra pedir o conteúdo da URL /restaurante/clientes
 - do host www.nomedaempresa.com.br (o host, servidor q fornece os dados, vai num cabeçalho à parte)
 - versão 1.1 do HTTP
 - mais dois cabeçalhos: Accept e Accept-language

Formato da resposta
```
HTTP/<versão> <código de status> <descrição do código>
<cabeçalhos>
<resposta>
```

Exemplo
```
HTTP/1.1 200 OK
Content-Type: text/html
Content-Length: 245

<clientes>
  <cliente id="1">
    <nome>Alexandre</nome>
    <dataNascimento>2012-12-01</dataNascimento>
  </cliente>
  <cliente id="2">
    <nome>Paulo</nome>
    <dataNascimento>2012-11-01</dataNascimento>
  </cliente>
</clientes>
```
 - versão 1.1, código 200, descrição OK
 - cabeçalhos: Content-Type e Content-Length
 - depois vem a resposta (o conteúdo)


### Códigos de status
 - 1XX → informativos
 - 2XX → requisição bem-sucedida
 - 3XX → redirecionamento
 - 4XX → erro na requisição do cliente
 - 5XX → erro no servidor
 - todos: https://developer.mozilla.org/pt-BR/docs/Web/HTTP/Status

Principais códigos de erro
 - 403 Forbidden → o cliente não tem direito de acessar o recurso, então o servidor se recusa a responder
 - 404 Not Found → o servidor não encontrou o recurso pedido
 - 500 Internal Server Error → o servidor encontrou uma situação q não sabe lidar
 - 503 Service Unavailable → o servidor não está pronto pra atender a solicitação


### HTTPS
HTTPS (HyperText Transfer Protocol Secure) = "Protocolo de Transferência de Hipertexto Seguro"
 - não é uma variação do HTTP, é o HTTP com uma camada extra (por isso fica na mesma categoria do HTTP)
 - essa camada permite transmitir os dados por uma conexão criptografada e verificar a autenticidade do servidor e do cliente por certificados digitais
 - a URL começa com `https://`

Uso
 - muito usado em pagamentos e transações sensíveis em sistemas corporativos
 - ideia principal: criar um canal seguro sobre uma rede insegura
 - dá uma proteção razoável contra quem faz escuta ilegal

Funcionamento
 1. cliente: "sua conexão é segura?"
 2. servidor: "sim, estou mandando o certificado"
 3. cliente: "ótimo, pronto pra estabelecer uma conexão segura"
 4. servidor: "vou criptografar o caminho e liberar quando estiver seguro"