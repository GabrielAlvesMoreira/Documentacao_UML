# Documentação do Projeto: Nex_TI
## Plataforma Educacional Gamificada e Inclusiva

O **Nex_TI** é um sistema web educacional focado nas metodologias de **Estudo Ativo**, **Repetição Espaçada (Spaced Repetition System - SRS)** e **Gamificação**. Desenvolvido para tornar o aprendizado de tecnologia mais engajador e eficiente, o sistema adapta-se ao ritmo de memória do aluno e o recompensa com Pontos de Experiência (XP) e Moedas Virtuais (Coins) conforme ele progride nas disciplinas.

---

## 1. Requisitos Funcionais (RF)

- **RF01 - Gestão de Autenticação e Perfis:** O sistema deve permitir o cadastro de novos usuários e realizar o controle de sessão (login), gerenciando os acessos entre o perfil "Aluno" e "Administrador" (incluindo permissões de God Mode).
- **RF02 - Motor de Repetição Espaçada (Algoritmo SM-2):** O sistema deve implementar o algoritmo SM-2 (base do Anki) para calcular automaticamente o intervalo de dias para a próxima revisão de cada conteúdo, otimizando a curva de esquecimento do aluno.
- **RF03 - Interface de Estudo Ativo (Flashcards):** O sistema deve apresentar os conteúdos em formato de cartões interativos de frente e verso, disponibilizando botões de feedback (De novo, Difícil, Bom, Fácil) para alimentar o algoritmo de memória.
- **RF04 - Criação de Flashcards Personalizados:** O sistema deve permitir que os alunos criem e salvem seus próprios flashcards na plataforma, integrando-os ao seu deck local de estudos.
- **RF05 - Módulo Preparatório ENADE:** O sistema deve fornecer fases dedicadas à resolução de questões de múltipla escolha focadas no ENADE, validando as respostas em tempo real.
- **RF06 - Sistema de Gamificação (XP e Ranks):** O sistema deve aplicar um teste de nivelamento inicial e, a cada conclusão de rotina de estudos, recompensar o aluno com Pontos de Experiência (XP), atualizando seu Rank acadêmico automaticamente.
- **RF07 - Economia Virtual e Desbloqueios:** O sistema deve conceder Moedas Virtuais (Coins) como recompensa por acertos, permitindo que o aluno utilize esse saldo financeiro virtual para desbloquear Módulos e Fases Bônus.
- **RF08 - Dashboard e Acompanhamento de Desempenho:** O sistema deve gerar um painel (modal de estatísticas) para que o aluno visualize de forma consolidada o seu nível atual, total de moedas e a quantidade de cartas ativas em seu deck.
- **RF09 - Suporte de Agente Especialista e Tutor (Implementação Futura):** O sistema prevê uma interface de chat contextual para sanar dúvidas técnicas em tempo real com uma Inteligência Artificial (Atendimento Nível 1) e o escalonamento via tickets para um Tutor humano (Atendimento Nível 2). **Nota:** Esta funcionalidade encontra-se no roadmap do projeto e será implementada futuramente.

---

## 2. Requisitos Não Funcionais (RNF)

- **RNF01 - Arquitetura e Hospedagem (MVP):** O sistema deve operar de forma *serverless* em sua fase inicial (MVP), hospedado em um ambiente de alta disponibilidade como o GitHub Pages.
- **RNF02 - Persistência de Dados no Cliente:** O sistema deve garantir a gravação e a recuperação imediata do estado da aplicação (progresso, economia, histórico do Anki e configurações) utilizando a API de `localStorage` do navegador.
- **RNF03 - Responsividade (Mobile First):** O layout deve ser construído sob a premissa de "Mobile First", utilizando CSS Flexbox e Media Queries para garantir a perfeita adaptação e usabilidade em smartphones, tablets e monitores *ultrawide*.
- **RNF04 - Acessibilidade Universal (WCAG):** A plataforma deve integrar um widget de acessibilidade que permita o redimensionamento responsivo das fontes (Zoom A+/A-) e um "Modo de Alto Contraste" para auxiliar usuários com baixa visão ou astigmatismo.
- **RNF05 - Desempenho e Velocidade de Resposta:** A aplicação deve garantir fluidez extrema durante o estudo, limitando a no máximo 1 segundo o tempo de transição e renderização ao virar um flashcard ou processar uma resposta do ENADE.
- **RNF06 - Identidade Visual e Micro-interações:** A interface de usuário (UI) deve seguir o padrão estético *Dark Mode* cibernético, emitindo feedbacks visuais imediatos (como chuva de estrelas, partículas e mudança de cores nos botões) para reforçar o engajamento no jogo.
- **RNF07 - Escalabilidade e Segurança Futura:** O código-fonte do front-end deve ser projetado de forma modular, preparando o terreno para a futura integração com uma API RESTful em Node.js, banco de dados e proteção de requisições HTTP via JWT.

---

## 3. Histórias de Usuário (User Stories)

**Visão do Aluno e Visitante (Front-office)**
- **US01 - Acesso e Cadastro:** Como Visitante, eu quero poder criar uma conta nova diretamente pela tela de login, para ingressar rapidamente na plataforma como Aluno.
- **US02 - Repetição Espaçada:** Como Aluno, eu quero interagir com flashcards que memorizam meu nível de dificuldade, para que o sistema me mostre as cartas difíceis com mais frequência e otimize meu tempo de estudo.
- **US03 - Flashcards Personalizados:** Como Aluno, eu quero poder criar minhas próprias cartas de estudo, para focar nas disciplinas em que tenho mais dificuldade e organizar meus resumos.
- **US04 - Acessibilidade Visual:** Como Aluno com dificuldade de leitura, eu quero poder aumentar o texto da plataforma e ativar um modo de alto contraste, para estudar com conforto visual e autonomia.
- **US05 - Jornada Gamificada:** Como Aluno, eu quero realizar um teste de nivelamento inicial, ganhar XP/Moedas ao concluir rotinas e usar meu saldo para comprar conhecimentos extras (Bônus), para manter meu engajamento no jogo.
- **US06 - Preparação Acadêmica:** Como Aluno concluinte, eu quero acessar um módulo exclusivo de simulado ENADE com questões de múltipla escolha, para testar meus conhecimentos antes da prova oficial.
- **US07 - Acompanhamento Pessoal:** Como Aluno, eu quero visualizar um dashboard com meu desempenho, rank e histórico de XP/Coins, para acompanhar minha evolução acadêmica de forma autônoma.
- **US08 - Suporte Integrado (Futuro):** Como Aluno, eu quero poder acionar um Agente Especialista (IA) durante os estudos ou abrir um ticket para o Tutor, para destravar meu aprendizado quando tiver dúvidas muito complexas.

**Visão do Tutor e Administrador (Back-office)**
- **US09 - Gestão de Acessos:** Como Administrador de TI, eu quero gerenciar os perfis de usuários (Alunos e Tutores) e seus níveis de permissão, para manter a segurança, a organização e a hierarquia da plataforma.
- **US10 - Criação de Conteúdo:** Como Tutor, eu quero criar, editar e excluir flashcards globais no banco de dados, para manter o material didático das trilhas de estudo sempre atualizado e preciso.
- **US11 - Acompanhamento Pedagógico:** Como Tutor, eu quero visualizar um painel analítico com o desempenho de XP e o engajamento da turma, para identificar alunos inativos ou com dificuldades e realizar intervenções proativas.
- **US12 - Atendimento de Dúvidas (Nível 2):** Como Tutor, eu quero receber no meu painel os tickets de dúvidas escalonados pelos alunos, para fornecer suporte humano e especializado em questões que a máquina não conseguiu resolver.

**Visão do Sistema / IA (Motor de Processamento)**
- **US13 - Processamento de Contexto (IA):** Como Agente Especialista (IA), eu quero receber via API a dúvida digitada pelo aluno junto com o texto oculto do flashcard que ele está estudando, para conseguir gerar uma resposta altamente contextualizada e precisa (Suporte de Nível 1).

---

## 4. Arquitetura e Tecnologias

O projeto adota uma arquitetura modular focada em escalabilidade. Atualmente, o sistema opera como um Produto Mínimo Viável (MVP) com a lógica de negócios e persistência rodando inteiramente no lado do cliente, servindo como uma prova de conceito avançada.

- **Front-end UI/UX:** HTML5 Semântico, CSS3 (Flexbox/Grid, Variáveis CSS, Animações Keyframes), JavaScript Vanilla.
- **Lógica de Negócios (Fase Atual):** JavaScript ES6+ (Responsável pelo motor SM-2 do Anki, controle de estado do DOM, gamificação e matemática de e-commerce).
- **Armazenamento (Fase Atual):** Arquivo estático `data.js` estruturado para alimentar o conteúdo do sistema, trabalhando em conjunto com a Web Storage API (`localStorage`) para salvar o progresso individual de cada usuário.
- **Back-end e BD (Implementação Futura):** API RESTful desenvolvida em Node.js com integração a um Banco de Dados estruturado. Também contempla a integração com APIs externas de Inteligência Artificial (LLM) para alimentar o módulo futuro do Agente Especialista.
- **Engenharia de Software:** Modelagem UML projetada e documentada para a integração final baseada no padrão MVC.

---

## 5. Conformidade e Padrões de Qualidade e Segurança

Para assegurar a excelência técnica, a confiabilidade e a maturidade do projeto, o desenvolvimento do **Nex_TI** foi guiado e fundamentado nas melhores práticas e normas nacionais e internacionais de engenharia de software:

- **ISO/IEC 27000 (Segurança da Informação):** O sistema aplica princípios de confidencialidade e integridade. Na arquitetura MVP atual, os dados são estritamente isolados no dispositivo do usuário via Web Storage, evitando exposição externa. Para o roadmap de integração com o Back-end, a arquitetura já prevê a criptografia de senhas (funções de Hash), comunicação segura via protocolo HTTPS, autenticação baseada em tokens (JWT) e adequação aos princípios de privacidade *by design* exigidos pela LGPD.
- **ISO/IEC 25010 (Qualidade de Produto de Software):** A plataforma atende aos atributos fundamentais de qualidade do modelo, com forte ênfase em **Usabilidade** (design intuitivo, recursos de acessibilidade embutidos e prevenção de erros), **Eficiência de Desempenho** (respostas sub-segundo do algoritmo de renderização dos flashcards) e **Portabilidade** (design web multiplataforma, operando em qualquer navegador moderno).
- **MPS.BR (Melhoria de Processo do Software Brasileiro):** A equipe adotou práticas de desenvolvimento ágil aderentes aos níveis iniciais do MPS.BR (focados na gestão de projetos e requisitos). Isso inclui o levantamento estruturado de necessidades (via User Stories e Backlog), a adoção de cerimônias do *Scrum* para alinhamento tático da equipe, a documentação formal em UML e o rígido Controle de Versão do código-fonte através do Git/GitHub, garantindo a rastreabilidade das entregas.

---

## 6. Equipe de Desenvolvimento

- 💻 **[Maycon Douglas](https://github.com/MayconDIS)** (RA: H719CD3)
  *Scrum Master | Desenvolvedor Full-Stack | Documentação UML*

- 💾 **[Rafael Mesquita](https://github.com/RFP40)** (RA: H6722I0)
  *Product Owner (PO) | Desenvolvedor Back-end | Banco de Dados | Documentação UML*

- 🎨 **[Maciel Silva](https://github.com/maciellcs)** (RA: R280985)
  *Desenvolvedor Front-end Mobile | UI Design | Documentação UML*

- 🎨 **[Gabriel Alves](https://github.com/GabrielAlvesMoreira)** (RA: H67HJ4)
  *Desenvolvedor Front-end Mobile | UI Design | Documentação UML*

---
> *Projeto acadêmico desenvolvido para a disciplina de Projeto Integrado Multidisciplinar - PIM_III.*
