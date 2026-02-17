# Ludus AI - Assistente Inteligente

## Sobre o Projeto

**Ludus AI** é um assistente de inteligência artificial desenvolvido por **PF** como projeto de exemplo para a plataforma **Astral AI**. Este projeto demonstra como integrar modelos de linguagem avançados em uma aplicação web moderna, servindo como referência de código para desenvolvedores que desejam utilizar a API da Astral AI.

O assistente foi criado para auxiliar usuários com suporte técnico, programação e tecnologia em geral, fazendo parte do ecossistema **Ludus Launcher** (anteriormente SubGames).

## Características

- **IA Avançada**: Utiliza modelos de linguagem via Astral AI (GPT-4 Fast)
- **Chat Interativo**: Interface moderna e responsiva estilo ChatGPT
- **Multilíngue**: Suporte para Português (BR/PT) e Inglês
- **Integração Discord**: Link direto para o servidor da comunidade Ludus
- **Responsivo**: Funciona perfeitamente em desktop e mobile
- **Tempo Real**: Respostas rápidas e contextualizadas

## Recursos Principais

- **Histórico de Conversação**: Mantém contexto durante a sessão
- **Formatação Markdown**: Suporte para código, links, listas e formatação rica
- **Exemplos Rápidos**: Cards clicáveis com perguntas prontas
- **Botão Limpar**: Reinicia a conversa a qualmomento
- **Indicador Online**: Status visual da conexão com a API
- **Auto-resize**: Textarea que se ajusta automaticamente ao conteúdo

## Estrutura de Arquivos

```
ludus-ai/
├── index.html              # Página principal
├── css/
│   └── visual_site.css     # Estilos do chat
├── js/
│   └── sistema.js          # Lógica do chat e integração com API
└── img/
    └── logo.png            # Logo do Ludus Launcher
```

## Tecnologias Utilizadas

- **HTML5**: Estrutura semântica
- **CSS3**: Estilização moderna com animações
- **JavaScript (Vanilla)**: Lógica sem frameworks
- **Astral AI API**: Infraestrutura de IA
- **GPT-4 Fast**: Modelo de linguagem

## Configuração

### Pré-requisitos

- Navegador moderno (Chrome, Firefox, Safari, Edge)
- Servidor local (opcional, mas recomendado para evitar CORS)

### Instalação

1. Clone ou baixe o repositório
2. Adicione sua logo em `img/logo.png`
3. Execute com servidor local:

```bash
# Python 3
python -m http.server 8000

# Node.js (http-server)
npx http-server -p 8000
```

4. Acesse `http://localhost:8000`

### Configuração da API

O projeto já vem configurado com a API da Astral AI. As configurações estão em `js/sistema.js`:

```javascript
const CONFIG = {
    API_ENDPOINT: 'https://api.astralai.pro/v1/chat',
    MODEL: 'openai-fast',
    MAX_TOKENS: 4096,
    TEMPERATURE: 0.7
};
```

## Como Usar

1. **Iniciar Conversa**: Digite sua mensagem na caixa de texto
2. **Enviar**: Pressione `Enter` ou clique no botão de envio
3. **Exemplos Rápidos**: Clique em um dos cards de exemplo
4. **Limpar Chat**: Use o botão "Limpar" no topo
5. **Discord**: Clique no card "Ludus Launcher" para acessar o servidor

## Personalização

### Cores

Edite as variáveis de cor em `css/visual_site.css`:

```css
background: #000;           /* Fundo principal */
border: 1px solid #333;     /* Bordas */
color: #fff;                /* Texto principal */
```

### Sistema Message

Personalize a personalidade da IA em `js/sistema.js`:

```javascript
SYSTEM_MESSAGE: `Você é Ludus_AI, um assistente...`
```

## Exemplo de Integração com Astral AI

Este projeto serve como exemplo completo de integração com a API da Astral AI:

```javascript
const response = await fetch(CONFIG.API_ENDPOINT, {
    method: 'POST',
    headers: {
        'Content-Type': 'application/json',
        'Authorization': `Bearer ${CONFIG.API_KEY}`
    },
    body: JSON.stringify({
        model: CONFIG.MODEL,
        messages: [
            { role: 'system', content: CONFIG.SYSTEM_MESSAGE },
            ...conversationHistory
        ],
        temperature: CONFIG.TEMPERATURE,
        max_tokens: CONFIG.MAX_TOKENS,
        stream: false
    })
});
```

## Links Importantes

- **Site Ludus Launcher**: https://sub-games.netlify.app/
- **Discord Ludus**: https://discord.gg/b2eaKnny2E
- **Discord Astral**: https://discord.gg/px5MJpdcn5
- **Astral AI**: https://astralai.pro/

## Tratamento de Erros

O sistema inclui tratamento para:

- Erro de conexão (CORS/Network)
- Erro de autenticação (API Key inválida)
- Limite de requisições (Rate Limit)
- Resposta inválida da API

## Segurança

- A API Key está codificada em Base64 (não é 100% segura)
- **Recomendação**: Para produção, use um backend intermediário
- Não exponha a API Key diretamente no frontend

## Responsividade

O design é totalmente responsivo com breakpoints:

- **Desktop**: Largura máxima de 800px para conteúdo
- **Tablet**: Ajustes em grid e padding
- **Mobile**: Layout single-column, botões maiores

## Projeto de Exemplo

Este é um **projeto de exemplo oficial** criado especialmente para demonstrar as capacidades da **Astral AI**. O código pode ser usado como base para desenvolver suas próprias aplicações com IA, servindo como referência de boas práticas de integração e desenvolvimento frontend.

## Contribuindo

Criado e mantido por **PF** - Desenvolvedor Português

Para sugestões ou problemas, entre no Discord da comunidade.

## Licença

Este projeto faz parte do ecossistema Ludus Launcher e serve como exemplo de código para a plataforma Astral AI.

---

**Desenvolvido por PF** | Powered by Astral AI

---

Este código é fornecido apenas como **exemplo**.  
Você pode utilizá-lo em projetos próprios, **desde que faça modificações significativas**.

Caso o uso seja praticamente um *copy-paste* — alterando apenas nomes ou detalhes mínimos — **é obrigatório creditar o desenvolvedor original**.
