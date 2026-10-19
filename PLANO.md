# PLANO — inemaSEO 4 · Nas IAs: AEO, GEO e sites usados por agentes (v7.2)

Curso 4 de 6 da Formação inemaSEO. Público: dono de site ou profissional que quer ser encontrado e citado pelas IAs. Pré-requisito sugerido: cursos 1–3 (fundação, conteúdo, medição).

Fontes (não alteradas): `wifi/longrun/2026-10-19-formacao-inemaseo-v72/TENDENCIAS-SEO-GEO-2026-10.md` (régua de 2026), `~/projetos/aiv2026` (playbook-aeo-geo.md, case-inema/), `~/projetos/aiv/diagnostico/` (bateria-v1.md, baseline-2026-07.md — só leitura; a rodada de julho usou API e não é repetida), `~/projetos/webmcp-readiness/lib/audit-rules.mjs`, `~/projetos/inemaseo-sistemas` (bing-ia, botlog, agente-ready: READMEs e exemplos de 19/10/2026), especificação WebMCP do W3C CG (16/10/2026), web.dev "Build agent-friendly websites".

## As 8 aulas

| # | slug | aula | objetivo (≤ 160) | diagrama | prática ("pronto quando") | fonte |
|---|---|---|---|---|---|---|
| 1 | `aeo-geo-sem-mito` | AEO e GEO sem mito | separar o que Google, Bing e as IAs dizem oficialmente do que é moda e escolher onde gastar o seu tempo | fundamento (SEO bem feito) → conteúdo não-commodity → medir em outro painel; ao lado, a caixa "moda" | 1) tabela "promessa → fonte oficial → veredito" com 5 itens que você ouviu; 2) 3 trechos do seu site que só você poderia escrever | TENDENCIAS §1.4, §4.1, §5, "o que muda" 14 |
| 2 | `paineis-oficiais` | Painéis oficiais de IA | abrir o relatório de IA do Search Console e o AI Performance do Bing e anotar o que cada um mede e o que não mede | Search Console (impressões) · Bing AI Performance (citações, grounding queries) · Topics Portfolio · GA4 (visita) → planilha do mês | 1) linha de base com as impressões de IA do GSC e as citações do Bing (ou "sem dado ainda"); 2) 5 grounding queries anotadas com a página citada | TENDENCIAS §1.3, §2.1, §3; bing-ia README |
| 3 | `bateria-de-perguntas` | Medir citação sem API | montar uma bateria de 20 perguntas congeladas e rodar à mão em 4 assistentes, com planilha datada | perguntas neutras → congelar v1 → rodar à mão (3×) → planilha → % de aparição e fontes citadas | 1) bateria v1 com 20 perguntas (16 neutras + 4 de marca) salva com data; 2) primeira rodada em 4 assistentes registrada na planilha | bateria-v1.md; baseline-2026-07.md (§2.8); playbook F0; TENDENCIAS §3 |
| 4 | `colisao-de-nome` | Colisão de nome e entidade | diagnosticar colisão de nome e bio desatualizada nas IAs e montar o catálogo de fichas que corrige a entidade | pergunta de marca → resposta errada → página de desambiguação + sameAs + fichas → remedir | 1) respostas de "o que é [marca]" e "quem é [fundador]" em 3 assistentes, com o erro anotado; 2) 5 fichas do catálogo com fonte e data | baseline §2.8; playbook F1; o-que-foi-feito-aiv (54 fichas) |
| 5 | `bing-e-robos-no-log` | Bing e robôs no log | conferir o site no Bing com IndexNow e ler no log quais robôs de IA visitam de verdade, por finalidade | Bing duas vezes (Copilot oficial + estudo Seer) · log → botlog → busca / ação do usuário / treino / falsos | 1) sitemap no Bing + IndexNow com resposta 200/202; 2) botlog rodado no log do seu site (ou no exemplo) com a contagem por finalidade | TENDENCIAS §2.1, §2.2, §4.4; botlog README e exemplos |
| 6 | `rubrica-readiness` | Rubrica de prontidão e as ressalvas | rodar uma nota de prontidão para IA, ler os critérios que mais pesam e saber o que a nota não prova | site → critérios com peso → nota → corrigir o que pesa → ressalvas | 1) agente-ready (ou WebMCP Readiness) rodado no seu site, nota e 3 falhas anotadas; 2) uma falha corrigida e a nota de novo | audit-rules.mjs; agente-ready README; notas de 19/10 (93/72/69/54); REVISAO §3.5 |
| 7 | `webmcp-preparacao` | Do encontrado ao usado: WebMCP | registrar uma ferramenta somente leitura com document.modelContext.registerTool() numa página de teste, como preparação | SEO encontra → agente usa → registerTool (nome, descrição, schema, execute) → feature detection + cancelar → Permissions-Policy | 1) página de teste com uma ferramenta somente leitura e fallback manual; 2) decisão escrita: onde o seu site ganharia uma ferramenta e onde não | spec W3C CG 16/10/2026; agente-ready (critério WebMCP); Formação WebMCP |
| 8 | `comercio-e-loop` | Comércio por agente e o loop mensal | deixar formulários e páginas de produto legíveis para agentes e montar o loop mensal de medição nas IAs | HTML semântico + rótulos → Merchant Center/Perfil da Empresa → loop mensal (painéis, bateria, log, nota) | 1) 1 formulário com rótulos e autocomplete conferido; 2) loop mensal agendado (gerador) com a 1ª data | web.dev agent UX; TENDENCIAS §1.4, §4.6; playbook F4; agente-ready (formulários) |

Aula 8 fecha com `mapa` (4 degraus: separar, medir, corrigir a entidade, preparar para agentes) + `gerador` (as 8 aulas).

## Simconversa da aula 1 — "me vende um llms.txt que me põe no ChatGPT"

Personagem: dona de uma loja de móveis planejados, site pequeno; recebeu oferta de "pacote GEO" com llms.txt. Ficção rotulada; o que ensina vem de TENDENCIAS §1.4, §4.1, §2.1, §3.

| fala | cliente | opções (nota → destino) |
|---|---|---|
| `abre` | "me vende um llms.txt que me põe no ChatGPT?" | vender e garantir (0 → `fim-promessa`) · explicar o que o arquivo é e perguntar o que ela quer (2 → `objetivo`) · "llms.txt é golpe" (1 → `golpe`) |
| `golpe` (desvio) | "então o que faço?" | voltar ao objetivo (1 → `objetivo`) · "não dá para fazer nada com IA" (0 → `fim-nada`) |
| `objetivo` | quer que, quando perguntam "móveis planejados em [cidade]", a loja apareça | olhar a fundação e o conteúdo próprio (2 → `medir`) · comprar pacote de 200 artigos (0 → `fim-spam`) · schema "para IA" (1 → `medir`) |
| `medir` | "e como eu sei se apareço?" | painéis oficiais + bateria mensal à mão (2 → `preco`) · "a ferramenta X dá a nota oficial" (0 → `fim-nota`) |
| `preco` | "então o llms.txt fica fora?" | opcional, barato, sem promessa (2 → `fim-bom`) · cobrar como entrega principal (0 → `fim-promessa`) |

Somas: direto 2+2+2+2 = 8; desvio 1+1+2+2+2 = 8 (não passa). Máximo = 8.

## Convenções (do piloto)
- `icone` "lupa"; `sub` "Formação inemaSEO · curso 4 de 6"; `volta` área inemaSEO; `lado_card` → curso 5 `formacao-inemaseo-agentes-v72`; `inicio.kicker` "Formação inemaSEO · curso 4 de 6 · 8 aulas".
- Aula: diagrama → passos → codigo (com saída) → [simconversa] → pratica (e1/e2) → quiz (4) → resumo (com "Régua de 2026") → links.
- Números do INEMA só da lista "Casos reais" do BRIEF + as notas do agente-ready de 19/10 (autorizadas). Exemplo do bing-ia é FICTÍCIO (selo simulação). Saída do botlog do exemplo real fica em `saida` com data.
- WebMCP: só `document.modelContext`. Nunca escrever o nome antigo por extenso no conteúdo (o checador da formação procura a string); diz-se "os cursos WebMCP antigos usam o nome anterior, no objeto navigator".

## Decisões tomadas sozinho
- Capa sem texto (como o piloto), foto da dona de padaria lendo o celular; 10/10 imagens pelo Codex na 1ª tentativa, sem reserva flux.
- Ferramentas do inemaseo-sistemas aparecem com um comando + saída + link e "detalhe no curso 7" (bing-ia na aula 2, botlog na 5, agente-ready na 6 e 7), sem tutorial de opções.
- bing-ia: saída com selo "simulação" e aviso de que o exemplo do repositório é fictício e as colunas do export são palpite.
- botlog: saída real do exemplo de desenho.inema.pro (rodado localmente em 19/10/2026, sem rede) só dentro de `saida`; a amostra montada descrita como montada.
- Notas do agente-ready de 19/10 (93/72/69/54) e o detalhe WebMCP do inema.club (1 registerTool, tools=(self)) só dentro de `saida` com data.
- Baseline de julho: só 0/48, 0/4, 52, 4/4 e 54 fichas; concorrentes citados e contagens de entidades do baseline ficaram fora. Diz que a rodada usou API e que o curso faz à mão.
- "Quem é Nei Maldaner?" com bio antiga entra como achado qualitativo (sem número), fonte baseline-2026-07.md.
- WebMCP: exemplo de ferramenta somente leitura escrito a partir da IDL da especificação de 16/10/2026 (name, title, description, inputSchema, execute, annotations.readOnlyHint; options.signal). O nome antigo nunca aparece por extenso.
- WebMCP Readiness descrito pelo audit-rules.mjs (WebMCP 30 / SEO 30 / GEO 20 / AEO 20; informativo 0,7) e pela ressalva de REVISAO §3.5.
- Protocolos de comércio por agente: só UCP citado (menção do Google); ACP fica fora por fontes conflitantes.

## Resultado (19/10/2026)
- PT: `validar.py` OK; `--links` 27 externos, único falho = curso 5 (irmão ainda não publicado); `conferir-tela.cjs` 9 páginas × 2 larguras OK, simconversa percorrida (máx. 8).
- Checagens da formação: skool/rank #1/humaniz = 0; nome antigo da API = vazio; llms.txt só como opcional/opção errada; FAQPage só com "rich result acabou (07/05/2026)".
