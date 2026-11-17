Pokédex - Consumo de API com JavaScript

Uma aplicação web interativa que simula uma Pokédex clássica, permitindo pesquisar e navegar entre diferentes Pokémon em tempo real. O foco principal deste projeto é a prática de consumo de APIs RESTful utilizando JavaScript moderno, manipulação dinâmica do DOM e estruturação semântica.

🎯 Objetivo do Projeto

Desenvolver uma interface funcional integrada à PokéAPI, aplicando conceitos fundamentais do desenvolvimento Front-end:

Requisições HTTP assíncronas com a Fetch API (async / await).

Tratamento de respostas e conversão de dados no formato JSON.

Validação de status HTTP e tratamento de erros (exibição de feedback para buscas inválidas ou em carregamento).

Atualização dinâmica de elementos na tela (DOM) sem recarregamento da página.

⚙️ Como Funciona o Consumo da API

Toda a lógica de comunicação com a API está concentrada no arquivo JavaScript/script.js e dividida em duas funções principais:

1. Busca de Dados (fetchPokemon)

Realiza uma requisição GET para o endpoint https://pokeapi.co/api/v2/pokemon/{pokemon} passando o nome ou o ID do Pokémon.

Verifica se o status da resposta é 200 (sucesso).

Converte o corpo da resposta para um objeto JavaScript através de APIResponse.json().

2. Renderização na Interface (renderPokemon)

Gerencia o estado visual da aplicação antes, durante e após a requisição:

Estado de Carregamento: Exibe "Loading..." enquanto aguarda a resolução da Promise.

Sucesso: Extrai o nome (data.name), o número identificador (data.id) e o sprite animado da 5ª geração (sprites.versions['generation-v']['black-white'].animated.front_default) para exibir na tela da Pokédex.

Erro (Status diferente de 200): Oculta a imagem e exibe "Not found :c" caso o Pokémon pesquisado não exista.

3. Navegação e Eventos

Formulário de Busca: Captura o evento submit, previne o comportamento padrão da página (event.preventDefault()) e normaliza a entrada do usuário com .toLowerCase().

Botões Prev e Next: Controlam a variável de estado searchPokemon para navegar sequencialmente pelos IDs dos Pokémon (com trava para não buscar IDs menores que 1).

🛠️ Tecnologias Utilizadas

HTML5: Estruturação semântica utilizando tags como <main>, <form> e <section>.

CSS3: Estilização responsiva, posicionamento absoluto sobre a imagem base da Pokédex, tipografia customizada (Oxanium) e efeitos de profundidade nos botões.

JavaScript (ES6+): Fetch API, funções assíncronas (async/await), manipulação do DOM e gerenciamento de eventos.

PokéAPI: API pública utilizada como fonte de dados e sprites.

📂 Estrutura de Pastas

Pokedex-Projeto/
├── estilo/
│   └── style.css       # Folha de estilos e responsividade
├── imagens/
│   ├── favicon.png     # Ícone da aba do navegador
│   └── pokedex.png     # Imagem base da interface da Pokédex
├── JavaScript/
│   └── script.js       # Lógica de consumo da PokéAPI e eventos
├── .gitattributes      # Configurações de atributos do Git
├── index.html          # Estrutura HTML principal
└── README.md           # Documentação do projeto


🚀 Como Executar o Projeto

Clone este repositório ou baixe os arquivos para o seu computador:

git clone https://github.com/seu-usuario/Pokedex-Projeto.git


Acesse a pasta do projeto:

cd Pokedex-Projeto


Abra o arquivo index.html diretamente no seu navegador de preferência (ou utilize a extensão Live Server no VS Code).

Nota: É necessário estar conectado à internet para que as requisições à PokéAPI e o carregamento da fonte Oxanium funcionem corretamente.



Desenvolvido por: *Ramon Alexandria* 💻