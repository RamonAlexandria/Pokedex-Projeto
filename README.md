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

