# Variáveis para preencher

Os exemplos vêm da configuração original do Job Hunter (profissional de operações de energia em São Paulo). Troque pelos seus.

| Variável | Onde entra | O que colocar | Exemplo |
| --- | --- | --- | --- |
| `{{NOME}}` | Tarefa | Seu nome | Maria Souza |
| `{{EMAIL_DESTINO}}` | Tarefa | E-mail que recebe o resumo | maria@email.com |
| `{{CAIXA_ALERTAS}}` | Tarefa | Onde chegam os alertas do LinkedIn: `gmail`, `outlook`, `hostinger` ou `nenhuma` (veja a tabela abaixo) | gmail |
| `{{EMAIL_ALERTAS}}` | Tarefa | Endereço que recebe os alertas do LinkedIn | maria@email.com |
| `{{REMETENTE}}` | Tarefa | Conector que envia o resumo: `gmail`, `outlook` ou `hostinger` | gmail |
| `{{URL_PORTAL}}` | Tarefa | Link do portal criado | claude.ai/artifact/... |
| `{{LINKEDIN_URL}}` | Tarefa | Link do seu perfil | linkedin.com/in/mariasouza |
| `{{PERFIL_RESUMIDO}}` | Tarefa | 5 a 8 linhas: cargo atual, anteriores com escopo e números, domínio técnico, formação | Coordenadora de Operações de Energia desde 2026; antes Especialista de Faturamento (500 MWac, 100 mil UCs)... |
| `{{NIVEIS_ACEITOS}}` | Tarefa | Níveis que você aceita | Analista Sênior, Especialista, Supervisor, Coordenador |
| `{{NIVEIS_EXCLUIDOS}}` | Tarefa | Níveis a descartar | Júnior, Pleno, Estágio, Gerente, Diretor |
| `{{DIAS_MAX}}` | Tarefa | Idade máxima da vaga, em dias | 60 |
| `{{CIDADE_CENTRAL}}` | Tarefa e portal | Cidade onde você mora | São Paulo |
| `{{CIDADES_ACEITAS}}` | Tarefa | Cidades aceitas para presencial ou híbrido | São Paulo, região metropolitana (Guarulhos, Osasco, Barueri...) ou Campinas |
| `{{CIDADE_DISTANTE}}` | Portal | Uma cidade mais distante que você aceita (opcional) | Campinas (≈ 95 km) |
| `{{REGRA_REMOTO}}` | Tarefa | Onde vale remoto | qualquer lugar do Brasil |
| `{{AREA_1}}` a `{{AREA_3}}` | Tarefa e portal | Nomes curtos das 3 áreas, **iguais nos dois lugares** | Energia · Operações & Billing · Processos & Automação |
| `{{DESCRICAO_AREA_1}}` a `{{DESCRICAO_AREA_3}}` | Tarefa | O que conta como cada área | GD, geração solar, faturamento de energia, Mercado Livre, CCEE |
| `{{AREAS_EXCLUIDAS}}` | Tarefa | O que nunca interessa | TI/desenvolvimento, vendas pura, jurídico, varejo de loja |
| `{{SETOR_PRINCIPAL}}` | Tarefa | Seu setor | energia / GD / Mercado Livre |
| `{{CARGO_ALVO}}` | Tarefa | Cargo principal para buscas na web | coordenador de operações |
| `{{TERMOS_DE_BUSCA}}` | Tarefa | 20 a 30 termos para a Gupy, separados por ponto e vírgula. Inclua termos amplos (ex.: "faturamento", "energia") além dos cargos | coordenador de operações; faturamento; billing; geração distribuída; energia; CCEE |
| `{{DIA_VARREDURA_COMPLETA}}` | Tarefa | Dia da semana em que a tarefa revarre a janela inteira (nos outros dias busca só desde a última execução) | segunda-feira |
| `{{FUSO_HORARIO}}` | Tarefa | Fuso no formato IANA | America/Sao_Paulo |
| `{{DIAS_E_HORARIO}}` | Pedido da tarefa | Quando a tarefa roda | de segunda a sexta às 8h |
| `{{RESUMO_PORTAL}}` | Portal | Frase do topo do portal | Vagas de Analista Sênior a Coordenador em energia, billing e processos. SP, Grande SP, Campinas ou remoto. |

## Palavras da nota de aderência

A nota é calculada por um script Python dentro do prompt, sempre com as mesmas regras. Cada variável abaixo é uma **lista Python** de palavras em minúsculas e **sem acento** (o script remove os acentos dos anúncios antes de comparar).

| Variável | Pontos | O que colocar | Exemplo |
| --- | --- | --- | --- |
| `{{PALAVRAS_FUNCAO_TITULO}}` | +40 | Funções que você já exerceu, como aparecem em títulos de vaga | `["faturamento","billing","garantia de receita","coordenador de operacoes","geracao distribuida"]` |
| `{{PALAVRAS_FUNCAO_PARCIAL}}` | +20 | Palavras de título que indicam função parecida | `["operacoes","processos","backoffice"]` |
| `{{PALAVRAS_FUNCAO_DESCRICAO}}` | +25 | Atividades suas que aparecem na descrição (precisa de 2 ou mais) | `["faturamento","titularidade","cadastro","medicao","sla","backlog"]` |
| `{{PALAVRAS_SETOR}}` | +25 | Seu setor | `["energia","eletrica","solar","mercado livre","ccee","distribuidora"]` |
| `{{PALAVRAS_SETOR_AFIM}}` | +10 | Setores vizinhos | `["gas","saneamento","utilities","telecom"]` |
| `{{PALAVRAS_NIVEL_ALTO}}` | +15 | Níveis mais altos que você aceita | `["coordenador","coordenadora","supervisor","especialista","lider","lead"]` |
| `{{PALAVRAS_NIVEL_SENIOR}}` | +10 | Marcas de sênior | `["senior","sr","iii"]` |
| `{{PALAVRAS_NIVEL_EXCLUIDO}}` | zera | Níveis que você não quer (ignorado se o título também tiver um nível alto, como "Coordenador/Gerente") | `["junior","jr","pleno","pl","assistente","estagio","trainee","gerente","diretor"]` |
| `{{PALAVRAS_COMPETENCIAS}}` | +10 | Competências que valorizam a vaga | `["automacao","ia","dados","bi","processos","sql","crm"]` |

Os outros +10 vêm do local: vaga em `{{CIDADE_CENTRAL}}`, híbrida ou remota. A nota vai até 100 e só entram vagas com 50 ou mais.

## Qual valor usar em `CAIXA_ALERTAS`

| Seu e-mail | Valor | O que precisa |
| --- | --- | --- |
| Gmail | `gmail` | Conector **Gmail** ativo no Claude |
| Outlook / Microsoft 365 | `outlook` | Conector **Microsoft 365** ativo no Claude. Ele é pensado para contas de trabalho ou escola; se a sua conta pessoal (@outlook.com, @hotmail.com) não conectar, use o encaminhamento abaixo |
| Domínio próprio na Hostinger | `hostinger` | Conector **Hostinger Mail** ativo no Claude |
| iCloud, Yahoo, UOL, Terra ou outro sem conector | `gmail` | Crie no seu provedor uma regra que encaminhe automaticamente os e-mails de `@linkedin.com` para um Gmail conectado. Outra saída: trocar o e-mail principal da conta do LinkedIn para esse Gmail |
| Não quer usar o LinkedIn | `nenhuma` | Nada |

O conector escolhido precisa estar ligado também nas configurações da tarefa agendada, não só na sua conta.

## O bloco CONFIG do portal

```js
const CONFIG = {
  resumo: "Vagas de Analista Sênior a Coordenador em energia, billing e processos.",
  areas: ["Energia", "Operações & Billing", "Processos & Automação"],
  lugares: {
    // "nome sem acento": [direção em graus (0 = norte, 90 = leste), distância 0 a 1, "Nome exibido"]
    "sao paulo": [0, 0, "São Paulo"],
    "guarulhos": [45, .42, "Guarulhos"],
    "barueri": [282, .5, "Barueri"],
    "santo andre": [135, .42, "Santo André"],
    "campinas": [318, 1, "Campinas"]
  },
  distante: "campinas",
  distanteRotulo: "≈ 95 km"
};
```

Cidades que não estão em `lugares` aparecem junto da cidade central.
