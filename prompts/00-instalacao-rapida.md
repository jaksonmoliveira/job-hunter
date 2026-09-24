# Instalação rápida em um único prompt

O Claude faz tudo numa conversa: lê seu currículo, pergunta o que falta, cria o portal, faz a primeira varredura e agenda a tarefa. Antes, faça a preparação do currículo e dos alertas do LinkedIn ([`docs/curriculo-e-linkedin.md`](../docs/curriculo-e-linkedin.md)).

**Como usar**

1. Numa tarefa nova do Cowork, anexe:
   - seu **currículo em PDF**;
   - [`portal/job-hunter-template.html`](../portal/job-hunter-template.html);
   - [`prompts/02-tarefa-agendada.md`](02-tarefa-agendada.md).
2. Cole a mensagem abaixo, preenchendo só as quatro primeiras linhas.
3. Responda às perguntas do Claude e aprove os cartões que aparecerem (portal, e-mail e tarefa agendada).

---

```text
Meu nome: {{NOME}}
Meu LinkedIn: {{LINKEDIN_URL}}
E-mail para receber o resumo: {{EMAIL_DESTINO}}
Cidade onde moro: {{CIDADE_CENTRAL}}

Quero instalar o Job Hunter, um caçador de vagas diário. Anexei meu currículo em PDF, o arquivo job-hunter-template.html (o portal) e o prompt modelo da tarefa agendada, com variáveis entre {{chaves}}. Faça nesta ordem:

1. Leia meu currículo e escreva um PERFIL_RESUMIDO de 5 a 8 linhas: cargo atual, cargos anteriores com escopo e números, domínio técnico e formação. Liste também as funções que já exerci, meu setor principal e minhas competências-chave.
2. Com base no currículo, proponha e me pergunte de uma vez só (com opções de múltipla escolha): níveis de cargo aceitos, cidades aceitas para presencial e híbrido, regra para remoto, as 3 áreas prioritárias com descrição, áreas a excluir, idade máxima das vagas em dias (padrão 60) e dias e horário da varredura.
3. Preencha o bloco CONFIG do job-hunter-template.html (resumo, as 3 áreas com os mesmos nomes do prompt, a minha cidade no centro e as cidades da região com direção e distância aproximadas) e publique como artifact "Job Hunter" com a capability db. Não altere nada fora do CONFIG.
4. Preencha TODAS as variáveis do prompt modelo com minhas respostas, o perfil e o link do portal. Me mostre o prompt final antes de seguir.
5. Faça a primeira varredura seguindo o prompt final: grave as vagas no portal e me envie o primeiro e-mail.
6. Crie a tarefa agendada "Job Hunter — vagas diárias" com o prompt final, nos dias e horário que escolhi, no meu fuso horário.
```

Ao final você terá o portal com as primeiras vagas, um e-mail na caixa de entrada e a tarefa marcada para o próximo dia útil.
