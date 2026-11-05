<h1 align="center">Wendson Kauã</h1>

<p align="center">
  <b>Desenvolvedor backend</b> · Java e Spring Boot, Python e Django<br>
  Estagiário de TI na área de Dados do <b>TJDFT</b> · Fundador da <b>77xp</b> · Brasília, DF
</p>

<p align="center">
  <a href="https://www.linkedin.com/in/wendson-kaua/"><img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn"></a>
  <a href="mailto:wendesonkaua11@gmail.com"><img src="https://img.shields.io/badge/E--mail-EA4335?style=for-the-badge&logo=gmail&logoColor=white" alt="E-mail"></a>
  <a href="https://inkstudiobr.com.br"><img src="https://img.shields.io/badge/Ink_Studio_no_ar-1a1612?style=for-the-badge&logo=googlechrome&logoColor=e7a72c" alt="Ink Studio no ar"></a>
</p>

---

## Sobre mim

Trabalho com backend em **Java e Spring Boot** e em **Python e Django**. No TJDFT, lido com dados
institucionais em **Oracle Database** num ambiente de produção, e automatizo o que antes era
conferência manual.

Vim da infraestrutura (redes, manutenção e segurança no técnico), e por isso penso em falha,
migração e operação antes de pensar em funcionalidade. O que mais gosto de garantir: a regra
importante fica no banco, e não só na tela, e o erro aparece no teste antes de chegar ao usuário.

Hoje mantenho plataformas próprias no ar, do levantamento de requisitos ao deploy, e procuro
minha primeira posição efetiva como desenvolvedor **backend, de dados ou de infraestrutura**.

<p>
  <img src="https://skillicons.dev/icons?i=java,spring,python,django,postgres,docker,githubactions,linux,react,ts" alt="Java, Spring, Python, Django, PostgreSQL, Docker, GitHub Actions, Linux, React e TypeScript" />
</p>

Também no dia a dia: **Oracle Database e PL/SQL**, Flyway, JUnit, Testcontainers, ArchUnit, pytest,
n8n e integração com LLM. Deploy em Render, Neon, Supabase e Vercel, com os erros no Sentry.

---

## Projetos em destaque

### Ink Studio

<a href="https://inkstudiobr.com.br"><img src="assets/projetos/ink.jpg" width="100%" alt="Ink Studio: a agenda da semana em grade e o controle de estoque, no modo escuro"></a>

SaaS para estúdios de tatuagem, **em produção e com assinatura paga**. O estúdio cuida do pedido
ao pós-tatuagem: orçamento com o mapa do corpo, agenda, sinal por Pix, ficha e termo digitais,
registro sanitário, caixa e estoque.

- **Multi-tenant:** cada estúdio no próprio endereço, todo dado preso ao estúdio, e um teste que tenta abrir cada página com os registros de outro estúdio.
- **Regras no banco:** o PostgreSQL impede dois horários sobrepostos na agenda, e o estoque trava a linha para a quantidade nunca ficar negativa.
- **Pagamento:** Pix pelo Mercado Pago, com o aviso conferido por assinatura HMAC e processado sem duplicar.
- **Números:** 21 módulos, 121 migrações, mais de 5 mil testes e 14 decisões de arquitetura registradas.

`Python 3.13` `Django 6` `PostgreSQL` `Mercado Pago` `Render` `GitHub Actions` `Sentry`

[**Ver no ar →**](https://inkstudiobr.com.br) &nbsp;·&nbsp; código privado (produto comercial)

<br>

### Cátedra

<a href="https://www.aprovacaopassoapasso.com.br"><img src="assets/projetos/catedra.jpg" width="100%" alt="Cátedra: a página de venda da Aprovação Passo a Passo, que roda sobre a plataforma"></a>

Plataforma de cursos online, **no ar como Aprovação Passo a Passo**, para concursos bancários. Da
vitrine ao certificado: venda, área do aluno, correção de redação e painel do professor, sobre a
mesma API.

- **Acesso só com pagamento confirmado:** o webhook não é a fonte de verdade. A plataforma pergunta ao provedor se o pedido foi pago, confere o valor e só então libera. O estorno revoga o acesso sozinho.
- **Arquitetura modular:** 18 módulos com fronteiras verificadas pelo ArchUnit a cada build, e 37 migrações versionadas no Flyway.
- **Segurança e LGPD:** JWT com refresh rotativo que derruba a sessão quando o token é reusado, senhas em Argon2id, e-mail no padrão outbox e aceite de termos comprovável.
- **Testes:** mais de 400, entre unitários, integração com Testcontainers e testes de arquitetura.

`Java 21` `Spring Boot 3.5` `PostgreSQL 17` `Flyway` `React 19` `TypeScript`

[**Ver no ar →**](https://www.aprovacaopassoapasso.com.br) &nbsp;·&nbsp; código privado (projeto de cliente)

<br>

### 77xp OS

<a href="https://77-tech.vercel.app"><img src="assets/projetos/os.jpg" width="100%" alt="77xp OS: o funil de leads em colunas, com os parados há mais de 5 dias marcados"></a>

O sistema que opera a 77xp: leads, reuniões, orçamento, propostas e cobrança. O cliente abre a
proposta por um link público, sem conta, e o site da 77xp manda cada lead direto para o funil.

- **Isolamento pelo banco:** toda tabela tem Row Level Security, e a aplicação conecta com um papel que não consegue contornar. Uma consulta que esqueça o filtro não vaza dado: não devolve nada.
- **Auditoria só de inserção:** `UPDATE` e `DELETE` revogados no próprio banco.
- **Testes:** mais de 800, entre a API (rodando contra PostgreSQL de verdade), o painel e o site.

`Java 21` `Spring Boot` `PostgreSQL 17` `React 19` `Next.js` `Tailwind`

[**Ver o site →**](https://77-tech.vercel.app) &nbsp;·&nbsp; código privado

<br>

### Agenda por WhatsApp com IA

<a href="https://github.com/kauaxp77/Automacao_n8n"><img src="assets/projetos/agenda.jpg" width="100%" alt="Agenda por WhatsApp: a mensagem encaminhada vira evento no Google Agenda"></a>

Automação para uma assessoria de licitações. O pedido de serviço encaminhado ao WhatsApp do
robô vira evento no Google Agenda, com resposta na mesma conversa, alarmes no celular e
lembretes por e-mail para a equipe.

- **A IA lê, o código confere:** o modelo extrai os dados num JSON de esquema estrito, e regras fixas e testadas conferem a data. Dia da semana que não bate, data no passado ou "amanhã" numa mensagem encaminhada fazem o evento nascer em vermelho, para alguém conferir.
- **Falha que avisa:** áudio, pedido sem data, IA fora do ar ou mensagem que a Meta não entregou viram aviso na hora, com o texto original.
- **47 testes** da lógica, fora do n8n, e infraestrutura de **R$ 0 por mês** nos planos gratuitos.

`n8n` `JavaScript` `Groq` `WhatsApp Cloud API` `Google Agenda` `Supabase` `Docker`

[**Código (cliente) →**](https://github.com/kauaxp77/naty-agenda) &nbsp;·&nbsp; [**Versão para replicar →**](https://github.com/kauaxp77/Automacao_n8n) &nbsp;·&nbsp; [Carrossel em PDF](https://github.com/kauaxp77/Automacao_n8n/blob/main/docs/divulgacao/linkedin/carrossel-agenda-whatsapp.pdf)

---

## Outros projetos

| Projeto | O que é | Stack |
|:---|:---|:---|
| **[Extrator auditável](https://github.com/kauaxp77/AutomatizacaoDeDados)** | Extração de dados de sistemas legados com validação por backtest. No caso real: 97,6% de acurácia contra 84 registros preenchidos à mão | `Python` `Playwright` |
| **[Simulados SEDES-DF](https://github.com/kauaxp77/simulados-sedes-df)** · [no ar](https://simulados-sedes-df.vercel.app) | Simulados para concurso, com papéis e validação nas regras do Firestore e auditoria por triggers | `Firebase` `Cloud Functions` `JavaScript` |
| **[Carlos Rosa](https://github.com/kauaxp77/Carlos-Rosa)** | Site de fotógrafo com CMS próprio, agendamento e auditoria | `Java 21` `Spring Boot` `MySQL` |
| **[MedClin](https://github.com/kauaxp77/Medclin)** | Gestão de clínica com três perfis de acesso, relatórios em PDF e painel com gráficos | `PHP` `MySQL` `Chart.js` |
| **[HireNow](https://github.com/kauaxp77/Hirenow-Job)** | Portal de vagas com área da empresa, candidaturas e conversa com o candidato | `PHP` `MySQL` |
| **[Agendamento de Salas](https://github.com/kauaxp77/Agendamento-de-Salas)** | Reserva de salas do SENAI | `PHP` `MySQL` `Bootstrap` |
| **[Calculadora de orçamentos](https://github.com/kauaxp77/calculadora-orcamentos)** · [no ar](https://calculadora-or-amentos-bay.vercel.app) | Monta o orçamento de um projeto, gera o PDF com assinatura e envia pelo WhatsApp | `JavaScript` `Firebase` |
| **[ASSED Goiás](https://github.com/kauaxp77/ASSEDGOIAS)** · [no ar](https://assedgoias.vercel.app) | Protótipo de front-end: site institucional, área do associado e painel | `React` `TypeScript` `Vite` |
| **[Requinte Coffee](https://github.com/kauaxp77/Requinte_coffee)** · [no ar](https://requinte-coffee.vercel.app) | Página de venda de um buffet de café | `Next.js` `TypeScript` `Tailwind` |
| **[Sistema de Patrimônio](https://github.com/kauaxp77/Sistema_Patrimonio)** | Telas de gestão de unidades, setores e relatórios patrimoniais | `HTML` `SCSS` `JavaScript` |

---

## Formação

| Curso | Instituição | |
|:---|:---|:---|
| **Análise e Desenvolvimento de Sistemas** | Centro Universitário Projeção | 4º semestre · conclusão em jul/2027 · CRA 7,88 |
| **Técnico em Informática** | Escola Técnica de Ceilândia | concluído em 2024 |

**Certificações:** Oracle APEX Foundations (Oracle) · MongoDB Overview (MongoDB) · Power BI (Hashtag Treinamentos)
