# Prompt para criar o portal

O portal é um artifact do Claude com banco de dados. O arquivo [`portal/job-hunter-template.html`](../portal/job-hunter-template.html) já vem pronto; só o bloco `CONFIG` no topo precisa ser preenchido.

**Como usar**

1. No app desktop do Claude, abra o Cowork e comece uma tarefa nova.
2. Anexe `job-hunter-template.html` e o seu currículo em PDF.
3. Cole a mensagem abaixo, trocando o que está entre chaves.
4. Abra o portal que o Claude publicar e **copie o link** (`claude.ai/artifact/...`). Ele vai no prompt da tarefa agendada.

---

```text
Publique o arquivo job-hunter-template.html anexado como um artifact chamado "Job Hunter", com a capability de banco de dados (db).
Antes de publicar, preencha o bloco CONFIG no topo do arquivo:
- resumo: "{{RESUMO_PORTAL}}"
- areas: ["{{AREA_1}}", "{{AREA_2}}", "{{AREA_3}}"]
- lugares: {{CIDADE_CENTRAL}} no centro e as cidades da região metropolitana dela, com direção em graus (0 = norte) e distância de 0 a 1 aproximadas da realidade. Se eu aceito uma cidade mais distante ({{CIDADE_DISTANTE}}), use-a em "distante" com o rótulo de distância em km.
Não altere nada fora do bloco CONFIG. Depois de publicar, me mande o link do artifact.
```

O portal abre vazio e se enche na primeira varredura da tarefa agendada.
