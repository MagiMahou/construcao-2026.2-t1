## **Documento de Requisitos**

**Histórico de Revisão**

|Data|Versão|Descrição|Autor|
| - | - | - | - |
|[dd/mm/aaaa]|0.1|Versão inicial|[Nome do autor]|

## **1. Introdução**

### **1.1 Propósito**
[Explique o objetivo deste documento: especificar os requisitos funcionais e não funcionais do sistema [Nome do Projeto], servindo de referência para o desenvolvimento e a validação da solução.]

### **1.2 Escopo**
[Descreva, em poucas frases, o que o sistema [Nome do Projeto] faz, qual problema resolve e para quem é destinado.]

### **1.3 Definições, Acrônimos e Abreviações**

|Termo|Definição|
| - | - |
|[Termo/Sigla]|[Definição]|

### **1.4 Referências**
[Liste os documentos e fontes utilizados na elicitação dos requisitos — ex.: entrevistas com stakeholders, documento de arquitetura, normas aplicáveis.]

## **2. Descrição Geral**

### **2.1 Perspectiva do Produto**
[Descreva se o sistema é novo, se substitui outro ou se integra a sistemas já existentes.]

### **2.2 Funções do Produto**
[Resuma, em alto nível, as principais funcionalidades do sistema.]

### **2.3 Características dos Usuários**

Os usuários do MoveUni são estudantes universitários com familiaridade básica com aplicativos de celular, sem necessidade de conhecimento técnico avançado. Foram identificadas três personas principais:

**Persona 1 — O Calouro Casual**
Lucas Andrade, 19 anos, estudante do 1º semestre. Não tem grupo fixo para praticar esporte e tem disponibilidade irregular entre aulas. Busca encontrar pessoas de nível parecido para jogar sem precisar organizar tudo manualmente em grupos de WhatsApp.

**Persona 2 — A Atleta Competitiva**
Marina Costa, 22 anos, estudante do 6º semestre e atleta de vôlei. Quer jogos de nível avançado e se frustra com partidas "misturadas" onde a diferença de nível atrapalha. Precisa saber o nível médio da partida antes de entrar.

**Persona 3 — O Organizador de Corrida**
Rafael Souza, 24 anos, mestrando, corre diariamente. Hoje depende de divulgar manualmente o horário em vários canais. Quer marcar um evento no calendário e deixar que outros estudantes se incluam diretamente, sem precisar de novo convite.

### **2.4 Restrições**
[Liste restrições técnicas, legais, de negócio ou de prazo que limitam as soluções possíveis.]

### **2.5 Suposições e Dependências**
[Liste suposições feitas durante a elicitação dos requisitos e dependências externas do projeto.]

## **3. Requisitos Funcionais**

Requisitos funcionais descrevem **o que o sistema deve fazer**.

| ID | Descrição | Prioridade |
| -- | --------- | :--------: |
| RF01 | O sistema deve permitir que o usuário se cadastre e crie um perfil informando os esportes que pratica. | Alta |
| RF02 | O sistema deve permitir que o usuário marque sua disponibilidade de dias e horários. | Alta |
| RF03 | O sistema deve agrupar automaticamente os usuários disponíveis no mesmo esporte e horário para formar times/grupos. | Alta |
| RF04 | O sistema deve fechar automaticamente uma partida/grupo quando o número mínimo de participantes necessário for atingido (ex.: 2 times completos para um jogo, ou grupo mínimo para uma corrida). | Alta |
| RF05 | Caso existam duas ou mais atividades possíveis no mesmo horário, o sistema deve priorizar a atividade com o maior número de interessados. | Média |
| RF06 | O sistema deve permitir que o usuário informe seu nível de habilidade (iniciante, intermediário, avançado) para cada esporte praticado. | Alta |
| RF07 | O sistema deve tentar formar partidas com usuários de nível semelhante; quando isso não for possível, deve exibir o nível médio da partida a todos os participantes. | Alta |
| RF08 | O sistema deve exibir um calendário com os eventos/partidas já marcados. | Alta |
| RF09 | O sistema deve permitir que um usuário se inclua em um evento já existente que ainda tenha vagas disponíveis. | Alta |
| RF10 | O sistema deve notificar o usuário quando uma partida ou grupo for fechado/confirmado. | Média |

> **Prioridade:** Alta, Média ou Baixa, definida por impacto na proposta central do produto (fechar partidas/grupos automaticamente por disponibilidade e nível) — requisitos essenciais ao fluxo de matchmaking são Alta; ajustes de experiência (notificações, priorização) são Média.

## **4. Requisitos Não Funcionais**

Requisitos não funcionais descrevem **qualidades e restrições técnicas** do sistema.

| ID | Categoria | Descrição | Prioridade |
| -- | --------- | --------- | :--------: |
| RNF01 | Desempenho | O sistema deve calcular e sugerir o agrupamento de disponibilidades em até 3 segundos após a marcação do usuário. | Alta |
| RNF02 | Segurança | O sistema deve autenticar os usuários por e-mail institucional e senha, com armazenamento de senha criptografado. | Alta |
| RNF03 | Usabilidade | O sistema deve ser mobile-first, permitindo marcar disponibilidade em no máximo 3 toques a partir da tela inicial. | Alta |
| RNF04 | Disponibilidade | O sistema deve estar disponível 99% do tempo, considerando uso concentrado em horários de intervalo entre aulas. | Média |
| RNF05 | Compatibilidade | O sistema deve ser acessível via navegador em dispositivos Android e iOS, sem exigir instalação de aplicativo nativo. | Média |
| RNF06 | Escalabilidade | O sistema deve suportar o crescimento do número de usuários simultâneos sem degradar o tempo de resposta do matchmaking. | Baixa |

## **5. Regras de Negócio**

[Liste as regras de negócio que restringem ou orientam o comportamento do sistema, independentemente de um requisito funcional específico.]

| ID | Descrição |
| -- | --------- |
| RN01 | [Descrição da regra de negócio] |

## **6. Protótipos**

[Insira aqui links ou imagens dos protótipos/wireframes que ilustram os requisitos funcionais.]
