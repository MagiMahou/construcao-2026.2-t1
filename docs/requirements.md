## **Documento de Requisitos**

**Histórico de Revisão**

|Data|Versão|Descrição|Autor|
| - | - | - | - |
|01/09/2026|0.1|Versão inicial preenchida com os requisitos do MoveUni|Gabriel Mendonça, Timóteo Stifft e Rafael Sasso|

## **1. Introdução**

### **1.1 Propósito**
Este documento tem como objetivo especificar os requisitos funcionais e não funcionais do sistema **MoveUni**, servindo como referência para desenvolvimento, validação e futuras evoluções da solução.

### **1.2 Escopo**
O MoveUni é um aplicativo fictício voltado para estudantes universitários que desejam encontrar colegas para praticar esportes, registrar disponibilidade, organizar partidas e entrar em eventos já existentes. O sistema busca reduzir a organização manual em grupos de mensagens e facilitar encontros esportivos por nível e horário.

### **1.3 Definições, Acrônimos e Abreviações**

|Termo|Definição|
| - | - |
|Matchmaking|Processo de agrupar usuários com disponibilidade, esporte e nível compatíveis|
|RN|Requisito de Negócio|
|RF|Requisito Funcional|
|RNF|Requisito Não Funcional|
|Usuário|Estudante cadastrado no MoveUni|
|Evento|Partida, treino ou grupo esportivo criado no sistema|

### **1.4 Referências**
- README.md do repositório `MagiMahou/construcao-2026.2-t1`
- `docs/architecture.md`
- `docs/index.md`
- `docs/visual_id.md`
- Contribuições da equipe e entendimento do domínio do projeto MoveUni

## **2. Descrição Geral**

### **2.1 Perspectiva do Produto**
O MoveUni é um sistema novo, criado para fins acadêmicos, que não substitui uma solução existente. A proposta é centralizar a organização de atividades esportivas entre estudantes, combinando agenda, nível de habilidade e agrupamento automático.

### **2.2 Funções do Produto**
Em alto nível, o sistema deve:
- permitir cadastro e autenticação de usuários;
- registrar esportes praticados e nível de habilidade;
- permitir informar disponibilidade por dia e horário;
- sugerir e montar grupos/partidas automaticamente;
- fechar eventos quando atingir a quantidade mínima de participantes;
- exibir calendário de eventos;
- permitir entrada em eventos já criados, se houver vagas;
- notificar usuários sobre confirmações e alterações relevantes.

### **2.3 Características dos Usuários**

Os usuários do MoveUni são estudantes universitários com familiaridade básica com aplicativos de celular, sem necessidade de conhecimento técnico avançado. Foram identificadas três personas principais:

**Persona 1 — O Calouro Casual**
Lucas Andrade, 19 anos, estudante do 1º semestre. Não tem grupo fixo para praticar esporte e tem disponibilidade irregular entre aulas. Busca encontrar pessoas de nível parecido para jogar sem precisar organizar tudo manualmente em grupos de WhatsApp.

**Persona 2 — A Atleta Competitiva**
Marina Costa, 22 anos, estudante do 6º semestre e atleta de vôlei. Quer jogos de nível avançado e se frustra com partidas "misturadas" onde a diferença de nível atrapalha. Precisa saber o nível médio da partida antes de entrar.

**Persona 3 — O Organizador de Corrida**
Rafael Souza, 24 anos, mestrando, corre diariamente. Hoje depende de divulgar manualmente o horário em vários canais. Quer marcar um evento no calendário e deixar que outros estudantes se incluam diretamente, sem precisar de novo convite.

### **2.4 Restrições**
- A solução deve ser mobile-first.
- A autenticação deve usar e-mail institucional e senha criptografada.
- A aplicação deve funcionar em navegadores modernos em Android e iOS.
- O tempo de resposta do agrupamento automático deve ser curto o suficiente para uso em tempo real.
- O sistema será tratado como fictício e acadêmico, portanto pode assumir um escopo enxuto e evolutivo.

### **2.5 Suposições e Dependências**
- Assume-se que os estudantes possuem acesso à internet e a um e-mail institucional válido.
- Assume-se que os dados de nível e disponibilidade são informados corretamente pelo usuário.
- O sistema depende de um banco de dados relacional para persistência dos dados.
- O envio de notificações pode depender de serviços externos, caso seja implementado futuramente.
- O calendário do sistema pode ser integrado a notificações internas sem depender de integrações complexas.

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
| RF11 | O sistema deve permitir que o usuário visualize e edite seu perfil esportivo e sua disponibilidade. | Média |
| RF12 | O sistema deve permitir filtrar eventos por esporte, nível e faixa de horário. | Média |

> **Prioridade:** Alta, Média ou Baixa, definida por impacto na proposta central do produto (fechar partidas/grupos automaticamente por disponibilidade e nível). Requisitos essenciais ao fluxo principal são Alta; ajustes de experiência e filtros são Média.

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
| RNF07 | Manutenibilidade | O código deve ser organizado em camadas para facilitar alterações futuras nas regras de negócio. | Alta |
| RNF08 | Confiabilidade | As ações críticas, como fechamento de partidas e confirmação de participação, devem ser persistidas de forma consistente. | Alta |

## **5. Regras de Negócio**

| ID | Descrição |
| -- | --------- |
| RN01 | O usuário deve informar pelo menos um esporte praticado para ativar o perfil de participação. |
| RN02 | A marcação de disponibilidade deve considerar apenas horários futuros ou ainda válidos. |
| RN03 | Uma partida só pode ser fechada quando atingir a quantidade mínima de participantes definida para o esporte ou tipo de evento. |
| RN04 | Quando houver conflito entre duas atividades no mesmo horário, deve prevalecer a com maior número de interessados. |
| RN05 | Caso não seja possível formar grupos homogêneos por nível, o sistema deve exibir o nível médio da partida. |
| RN06 | Um usuário só pode participar de um evento se houver vagas disponíveis. |
| RN07 | Eventos fechados não podem receber novos participantes, exceto se reabertos por um organizador. |
| RN08 | O calendário do usuário deve exibir apenas eventos nos quais ele está participando, organizando ou foi convidado. |

## **6. Protótipos**

Atualmente só é possivel visualizar as telas proposta para o aplicativo, que foi desenvolvida na ferramenta Figma.
