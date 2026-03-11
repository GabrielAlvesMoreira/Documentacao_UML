# Documentação do Projeto: Nex_TI
## Plataforma Educacional Gamificada

O **Nex_TI** é um sistema web educacional focado na metodologia de **Estudo Ativo (Flashcards)** e **Gamificação**. Desenvolvido para tornar o aprendizado de tecnologia mais engajador, o sistema recompensa os alunos com Pontos de Experiência (XP) e Moedas Virtuais (Coins) conforme eles progridem nas disciplinas.

---

## 1. Requisitos Funcionais (RF)

- **RF01 - Autenticação e Gestão de Perfis:** O sistema deve permitir o cadastro, login e gerenciamento de dois níveis de acesso: Administrador (gestão de usuários e conteúdo) e Aluno (consumo de conteúdo e gamificação).
- **RF02 - Gestão de Estudos (Flashcards):** O sistema deve apresentar os conteúdos em formato de flashcards (frente e verso), permitindo que o aluno revele a resposta e registre seu resultado (Acerto ou Erro).
- **RF03 - Sistema de Gamificação (Core):** O sistema deve calcular e atribuir dinamicamente Pontos de Experiência (XP) e Moedas Virtuais (Coins) a cada flashcard respondido corretamente.
- **RF04 - Progressão e Nivelamento:** O sistema deve atualizar automaticamente o Rank/Nível do aluno com base no XP acumulado e realizar um teste diagnóstico no primeiro acesso para definir o nível inicial.
- **RF05 - Gestão de Conteúdo e Desbloqueio:** O sistema deve permitir o bloqueio de Fases e Módulos (ex: Fases Bônus), exigindo que o aluno utilize suas Moedas (Coins) ou atinja um nível específico para liberá-los.
- **RF06 - Relatórios de Desempenho:** O sistema deve gerar painéis de acompanhamento (Dashboards) mostrando o progresso, as estatísticas de acertos e o nível individual exclusivamente para o próprio aluno.
- **RF07 - Suporte por Agente Especialista (IA):** O sistema deve integrar uma interface de comunicação com um Agente Especialista (Inteligência Artificial) para fornecer suporte em tempo real, permitindo ao aluno tirar dúvidas e aprofundar as explicações sobre as cartas estudadas.

---

## 2. Requisitos Não Funcionais (RNF)

- **RNF01 - Arquitetura (Integração):** Em sua fase atual (MVP), o front-end e a lógica de negócio rodam em HTML/CSS/JS. A arquitetura alvo (desenvolvimento futuro) prevê a comunicação com um banco de dados (SQL Server) através de uma API RESTful em C# (.NET).
- **RNF02 - Responsividade (Mobile First):** A interface de usuário (UI) deve se adaptar perfeitamente a dispositivos móveis, tablets e desktops, garantindo a usabilidade e leitura sem quebra de layout.
- **RNF03 - Desempenho (Tempo de Resposta):** O tempo de transição ao virar uma carta (flashcard) e a computação de XP/Moedas na tela devem ocorrer em no máximo 1 segundo, garantindo a imersão no estudo.
- **RNF04 - Segurança de Dados:** Na integração futura, as senhas dos usuários deverão ser armazenadas de forma criptografada (uso de Hash), e as rotas da API protegidas por tokens de autenticação.
- **RNF05 - Usabilidade e Identidade Visual:** O sistema deve manter um padrão de Dark Mode contínuo (estética de terminal/código) e fornecer feedback visual e imediato (cores indicativas e animações) nas ações de acerto ou erro.
- **RNF06 - Disponibilidade:** O sistema web deve ser projetado para alta disponibilidade, com o front-end hospedado em serviços de nuvem estáveis (ex: GitHub Pages) para acesso contínuo dos alunos.

---

## 3. Histórias de Usuário (User Stories)

- **US01 - Diagnóstico Inicial:** Como Aluno, eu quero realizar um teste diagnóstico no meu primeiro acesso, para que o sistema defina meu nível de XP inicial de forma justa.
- **US02 - Estudo Ativo:** Como Aluno, eu quero interagir com flashcards (frente e verso) e registrar meus acertos ou erros, para que eu possa fixar o conteúdo acadêmico.
- **US03 - Gamificação e Recompensa:** Como Aluno, eu quero ganhar XP e Moedas (Coins) ao acertar os flashcards, para que eu me sinta motivado a subir de Rank.
- **US04 - Economia do Jogo:** Como Aluno, eu quero utilizar minhas Moedas acumuladas para desbloquear módulos bônus, para ter acesso a conteúdos exclusivos.
- **US05 - Gestão de Conteúdo:** Como Administrador, eu quero criar e atualizar os flashcards das disciplinas, para que a plataforma se mantenha relevante e atualizada.
- **US06 - Painel de Progresso:** Como Aluno, eu quero visualizar um painel com meu desempenho e histórico de acertos, para acompanhar minha evolução no sistema de forma autônoma.
- **US07 - Suporte Inteligente:** Como Aluno, eu quero poder consultar um Agente Especialista (IA) durante as sessões de estudo, para esclarecer dúvidas técnicas de forma imediata.

---

## 4. Arquitetura e Tecnologias

O projeto adota uma arquitetura em camadas. Atualmente, o sistema opera como um Produto Mínimo Viável (MVP) totalmente funcional no Front-end. A modelagem de software já contempla a arquitetura final robusta a ser implementada na próxima fase.

- **Front-end:** HTML5, CSS3 (Flexbox/Grid), JavaScript Vanilla.
- **Back-end (Fase Atual):** JavaScript (Responsável pela simulação da lógica de gamificação, controle de estados e persistência de dados local).
- **Back-end (Implementação Futura):** API RESTful desenvolvida em C# (.NET Core).
- **Banco de Dados (Implementação Futura):** Microsoft SQL Server.
- **ORM (Implementação Futura):** Entity Framework Core.
- **Engenharia de Software:** Modelagem UML (Casos de Uso, Diagramas de Classes e Sequência) projetada e documentada para a integração final em C#.

---

## 5. Equipe de Desenvolvimento

- 💻 **[Maycon Douglas](https://github.com/MayconDIS)** (RA: H719CD3)
  *Scrum Master | Desenvolvedor Full-Stack | Documentação UML*

- 💾 **[Rafael Mesquita](https://github.com/RFP40)** (RA: H6722I0)
  *Product Owner (PO) | Desenvolvedor Back-end | Banco de Dados | Documentação UML*

- 🎨 **[Maciel Silva](https://github.com/maciellcs)** (RA: R280985)
  *Desenvolvedor Front-end Mobile | UI Design | Documentação UML*

- 🎨 **[Gabriel Alves](https://github.com/GabrielAlvesMoreira)** (RA: H67HJ4)
  *Desenvolvedor Front-end Mobile | UI Design | Documentação UML*

---
*(Projeto acadêmico desenvolvido para a disciplina de Projeto Integrado Multidisciplinar - PIM_III).*
