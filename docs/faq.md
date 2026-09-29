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
É uma estimativa do Claude a partir do anúncio e do seu perfil. Leia sempre a vaga antes de se candidatar.
