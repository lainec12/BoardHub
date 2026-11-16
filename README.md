# BoardHub 💜

Projeto independente com seis jogos multiplayer: Jogo da Velha, Damas Brasileiras/Inglesas, Ludo Clássico/Power, UNO, Batalha Naval e Xadrez. Lobby roxo/lilás, salas, convites, chat e perfil Google único.

## Código completo

O código está em **BoardHub-source.zip**, incluindo cliente, servidor, documentação, lockfile e testes. Os diretórios ainda não estão extraídos na árvore deste repositório. O GitHub Actions extrai o pacote somente no ambiente temporário para testar, sem escrever no repositório.

Para executar:

```bash
git clone https://github.com/lainec12/BoardHub.git
cd BoardHub
unzip -o BoardHub-source.zip
npm ci
npm test
npm start
```

No Windows, extraia o ZIP com o Explorador de Arquivos antes dos comandos npm. Requer Node.js 24+. Abra http://localhost:3000.

## Jogos e login

Velha, Damas, Batalha Naval e Xadrez são para dois jogadores. Ludo e UNO aceitam de dois a quatro. Modo contra computador ainda não está implementado.

O login Google está preparado, mas exige suas credenciais no servidor e callback cadastrado no Google Cloud. Sem configuração funciona em desenvolvimento por apelido. Perfil e sessão são persistidos em SQLite, com sessão de até 30 dias. Não envie segredos ao GitHub. Instruções completas estão em docs/LOGIN-GOOGLE.md dentro do pacote.

## Hospedagem

O repositório público disponibiliza o código; os jogos ainda não têm URL de produção. GitHub Pages sozinho não executa o servidor multiplayer. Para Render/Railway, use o conteúdo extraído do ZIP, Node 24, build npm ci, start npm start e disco persistente para SQLite. O pacote inclui docs/DEPLOY.md. Domínio e login Google precisam ser configurados na hospedagem.

69 testes passaram localmente; o workflow deste repositório também executa a suíte. Conferência visual e auditoria formal de acessibilidade permanecem pendentes. Salas ativas ficam em memória e terminam com reinício do servidor; perfis, sessões e placares ficam no SQLite. Regras casuais e limitações estão documentadas por jogo.
