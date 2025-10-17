# NLW Prompts Manager

Este repositório contém a aplicação "NLW Prompts Manager", desenvolvida durante o evento Rocketseat NLW Pocket Full Stack. A aplicação é uma página web simples para gerenciar prompts (exemplos, ideias ou modelos de texto) com funcionalidades básicas de criação, edição e cópia.

## Descrição

A aplicação foi construída como parte do evento Rocketseat NLW Pocket Full Stack e serve como projeto de aprendizado para manipulação do DOM, armazenamento local e interação com o usuário através de formulários e botões. É uma aplicação front-end leve que não depende de backend para funcionamento — todos os dados são armazenados localmente (localStorage).

## Funcionalidades

- Criar novos prompts via formulário.
- Editar prompts existentes.
- Copiar o conteúdo do prompt para a área de transferência.
- Persistência simples utilizando localStorage (os prompts sobrevivem a reloads do navegador no mesmo dispositivo/usuário).
- Interface responsiva e focada em usabilidade (HTML/CSS/JS puro).

## Tecnologias e bibliotecas

- HTML
- CSS
- JavaScript (ES6+)
- Nenhuma biblioteca externa é necessária — a aplicação utiliza apenas APIs nativas do navegador (DOM, Clipboard, localStorage).

Se desejar evoluir a aplicação, recomendo considerar:
- Um framework front-end (React, Vue ou Svelte) para melhor estrutura e reatividade.
- Um backend (Node/Express, Fastify, ou similar) com um banco de dados (SQLite, PostgreSQL) para persistência remota.
- Autenticação (Auth0, NextAuth, Firebase Auth) para múltiplos usuários.

## Estrutura de arquivos e pastas

A estrutura atual do projeto é simples e intencionalmente enxuta:

```
nlw-prompt-manager/
├── index.html       # Página principal da aplicação
├── script.js        # Lógica JavaScript (criação, edição, cópia, persistência)
├── style.css        # Estilos da interface
└── assets/          # Imagens, ícones e outros recursos estáticos
```

Descrição dos arquivos principais:

- `index.html`: marca a estrutura da página, inclui os campos de formulário, botões de ação e a lista onde os prompts são exibidos.
- `script.js`: contém as funções para adicionar, editar, remover e copiar prompts, além da lógica de armazenamento no localStorage.
- `style.css`: regras visuais e layout responsivo.
- `assets/`: crie ou coloque aqui imagens, logos ou ícones usados pela interface.

## Como usar

1. Abra o arquivo `index.html` no seu navegador (arraste o arquivo para uma janela do navegador ou use um servidor HTTP estático).
2. Preencha o formulário para criar um novo prompt. Clique em salvar/adicionar.
3. Os prompts adicionados aparecerão em uma lista abaixo do formulário.
4. Use os botões de editar para alterar um prompt existente e o botão de copiar para enviar o conteúdo para a área de transferência.
5. Os prompts são armazenados no `localStorage` do navegador — para limpar, remova manualmente via ferramentas de desenvolvedor ou pelo próprio UI caso exista uma opção de excluir.

Executando via servidor (opcional):

Se preferir servir os arquivos via um servidor local (recomendado para evitar problemas de CORS com APIs do navegador ao usar alguns recursos), rode um servidor estático. Exemplo com o Node.js com o pacote `serve` (instale globalmente se necessário):

```bash
npm install -g serve
serve -s . -l 8000
```

## Contrato da aplicação (entrada / saída)

- Entrada: texto do prompt fornecido pelo usuário via formulário.
- Saída: prompt salvo exibido na lista; ação de cópia que envia o texto para a área de transferência.
- Erros: validações simples (ex.: não permitir prompt vazio). As falhas de escrita no localStorage são raras — quando ocorrem, o app deve alertar o usuário.

## Casos de borda e considerações

- Prompts vazios: impedir criação ou editar para vazio.
- Espaço de armazenamento do localStorage: localStorage tem limites; para muitos prompts ou textos muito grandes, considerar armazenamento remoto.
- Compatibilidade de clipboard: a API de clipboard funciona na maioria dos navegadores modernos; fallback pode ser necessário para navegadores antigos.
- Multiusuário: sem backend, os dados ficam restritos ao navegador/dispositivo.

## Testes e validação

Como é uma aplicação simples sem dependências, testes manuais são suficientes para o momento:

- Teste de criação: adicionar um prompt e verificar se aparece na lista.
- Teste de persistência: recarregar a página e confirmar que o prompt continua presente.
- Teste de edição: editar um prompt e confirmar a alteração.
- Teste de cópia: clicar em copiar e colar o conteúdo em outro lugar para confirmar.

## Possíveis melhorias futuras

- Adicionar funcionalidades de organização (tags, categorias).
- Busca e filtragem de prompts.
- Suporte a usuários e sincronização via backend.
- Exportar/importar prompts (JSON, CSV).
- Melhorar a UI/UX: animações, confirmação de ações e logs de atividade.

## Licença

Este projeto é fornecido como exemplo de aprendizado e pode ser usado livremente. Se você pretende usar em produção, escolha uma licença apropriada e atualize este documento.

## Agradecimentos

A aplicação foi desenvolvida durante o evento Rocketseat NLW Pocket Full Stack. Obrigado à Rocketseat e à comunidade por fornecer conteúdo e desafios que ajudam no aprendizado.
