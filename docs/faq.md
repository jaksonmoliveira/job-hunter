# Dúvidas frequentes

**O Job Hunter pega todas as vagas do LinkedIn?**
Não. Ele só vê as vagas que chegam nos seus alertas por e-mail, porque o LinkedIn bloqueia leitura automática. Quanto melhores os alertas, mais vagas entram.

**E a InHire e outros portais?**
Entram por busca na web, que acha menos coisa que a Gupy. Vale como complemento, não como fonte principal.

**Quanto isso consome do meu plano?**
Cada varredura é uma sessão do Claude com dezenas de buscas. Se o limite de uso apertar, rode só 3 vezes por semana ou corte a lista de termos pela metade.

**Uso Outlook, iCloud ou outro e-mail, não Gmail.**
A caixa dos alertas e o remetente do resumo são configuráveis no topo do prompt da tarefa (`CAIXA_ALERTAS` e `REMETENTE`). Gmail, Outlook/Microsoft 365 e Hostinger são lidos direto pelos conectores. iCloud, Yahoo e outros provedores sem conector funcionam encaminhando os alertas do LinkedIn para um Gmail. Detalhes em [`variaveis.md`](variaveis.md#qual-valor-usar-em-caixa_alertas).

**O conector da minha caixa caiu. A tarefa para?**
Não. Ela segue com Gupy e busca web e avisa no rodapé do e-mail que o LinkedIn ficou de fora naquele dia.

**Moro fora de São Paulo.**
Tudo se adapta: as cidades aceitas ficam no prompt, e o mapa "Constelação de locais" usa o bloco `CONFIG` do portal. A instalação rápida monta esse bloco para a sua cidade.

**Posso mudar as áreas depois?**
Pode, mas troque os nomes nos dois lugares: no prompt da tarefa e no `CONFIG` do portal. As vagas antigas continuam com o nome antigo da área.

**Por que só 3 áreas?**
O painel usa uma cor por área, e três é o máximo em que as cores continuam fáceis de distinguir, inclusive para quem tem daltonismo.

**Meus dados ficam públicos?**
Não. O portal e a tarefa são privados da sua conta. O modelo deste repositório não tem dado de ninguém.

**A nota de aderência é exata?**
É uma regra fixa de palavras-chave aplicada ao título e ao resumo do anúncio, calculada por um script que o próprio Claude roda. Ela é consistente (a mesma vaga sempre tira a mesma nota), mas não lê nas entrelinhas. Leia sempre a vaga antes de se candidatar e, se as notas estiverem altas ou baixas demais, ajuste as listas `PALAVRAS_*` ([`variaveis.md`](variaveis.md#palavras-da-nota-de-aderência)).

**Como sei se uma fonte parou de funcionar?**
O rodapé do e-mail traz o funil de cada fonte (lidas, na janela, pré-filtro, mantidas). A tarefa também confere se a vaga mais recente da Gupy é de ontem ou de hoje; se não for, tenta de novo e marca a execução como "alerta".

**Por que a mesma vaga descartada não volta?**
Toda vaga avaliada fica na coleção `vistas` do portal, com a decisão e o motivo. A tarefa pula o que já está lá.
