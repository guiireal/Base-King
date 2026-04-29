# King Base - WhatsApp Baileys

O **King Base** é uma base organizada e modular para bots de WhatsApp, desenvolvida utilizando a biblioteca **Baileys**. Esta base foi projetada para ser fácil de configurar, com carregamento automático de comandos e funções de envio simplificadas.

## Funcionalidades:

- **Conexão via Pairing Code**: Conecte seu bot sem precisar escanear QR Code, apenas usando o número de telefone.
- **Carregamento Automático**: Comandos organizados em pastas e subpastas são detectados automaticamente.
- **Funções de Envio Customizadas**: Funções como `kingmsg`, `kingaudio`, `kingmenu` e `kingfile` para facilitar o desenvolvimento.
- **Configuração TOML**: Gerencie prefixo, nome do bot e outras definições em um arquivo `.toml` limpo.
- **Reação Automática**: Reage quando um comando inexistente é solicitado.
- **Auto-Nome**: Atualiza o nome do perfil do WhatsApp automaticamente ao conectar.

## Estrutura do Projeto:

```text
KingBot/
├── king.sh                
├── package.json            
├── settings/
│   └── configure.toml      
└── src/
    ├── authkeys/           
    ├── commands/           
    │   └── utilitarios/
    │       └── menu.js
    ├── connection/
    │   └── king-cn.js      
    └── functions/
        ├── loadcmds.js     
        └── senders.js
```

## Instalação e Uso:

1. **Requisitos**: Certifique-se de ter o [Node.js](https://nodejs.org/) instalado.
2. **Iniciar**: No terminal, execute o script de inicialização:
   ```bash
   sh king.sh
   ```
3. **Conectar**:
   - O bot solicitará o número do WhatsApp (ex: `5511999999999`).
   - Um código de 8 dígitos será exibido no terminal.
   - No seu WhatsApp, vá em **Aparelhos Conectados > Conectar com número de telefone** e insira o código.

## Configuração:

Edite o arquivo `settings/configure.toml` para personalizar seu bot:

```toml
prefixo = "!"
nome_bot = "King Base"
```

## Criando Novos Comandos:

Para criar um comando, basta adicionar um arquivo `.js` na pasta `src/commands/`. Exemplo:

```javascript
module.exports = {
    name: "exemplo",
    async execute(client, msg, args, king, config) {
        await king.kingmsg("Este é um comando de exemplo!");
    }
};
```

---
Desenvolvido com foco em organização e performance.
