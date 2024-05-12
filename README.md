# Ponderada_3_Thiago-Volcati

## Documentação Detalhada do Modelo Relacional

**Projeto:** Sistema de Feedbacks do Cesim Game
**Data:** 2024-05-12  
**Autor:** Thiago Volcati
**Objetivo:** Este documento visa fornecer uma descrição detalhada do modelo relacional utilizado no projeto de jogo interativo. O foco está em mapear as interações e feedbacks dos usuários durante as diversas fases do jogo, destacando a estrutura de dados e os relacionamentos essenciais.

### Entidades

#### **Usuário** (`Usuário`)
- **Descrição:** Armazena todas as informações pessoais e acadêmicas dos usuários participantes.
- **Atributos Principais:**
  - `id`: Identificador único do usuário (chave primária).
  - `name`: Nome completo do usuário.
  - `email`: Endereço de e-mail.
  - `senha`: Senha de acesso ao sistema.
  - `country`: País de origem.
  - `gender`: Gênero.
  - `first_language`: Primeira língua falada.
  - `status`: Status atual no sistema (ativo, inativo, ocupado, etc).
  - `University`: Instituição de ensino que frequenta.
  - `hapiness_meter`: Medidor de satisfação ou felicidade.
  - `id_team`: Identificador do time ao qual o usuário pertence.

#### **Etapas do Cesim Game**
- **Pré-Jogo** (`pré-game`)
  - **Descrição:** Registra as avaliações e escolhas feitas pelos usuários antes do início efetivo do jogo.
  - **Relacionamentos:** Recebe as avaliações iniciais de seus pontos de vista sobre seus perfis profissionais.
- **Durante o Jogo** (`during-game`)
  - **Descrição:** Captura decisões e interações entre os usuários enquanto o jogo está ativo.
  - **Relacionamentos:** Mantém registro das interações avaliativas entre os usuários, com referências cruzadas aos participantes.
- **Pós-Jogo** (`end-game`)
  - **Descrição:** Armazena os feedbacks fornecidos após a conclusão das sessões de jogo.
  - **Relacionamentos:** Conecta os feedbacks dados a quem os recebeu e a quem os enviou.

#### **Feedback**
- **Decison Making** (`feedback-decision-making`)
  - **Descrição:** Coleta feedback sobre as decisões tomadas pelos usuários durante o jogo.
  - **Relacionamentos:** Associa cada feedback ao usuário avaliado e ao avaliador.
- **Colaboração** (`feedback-colaboration`)
  - **Descrição:** Registra impressões sobre como os usuários trabalharam em conjunto durante o jogo.
  - **Relacionamentos:** Similar ao feedback de decisão, conecta o feedback à sessão colaborativa relevante.

#### **Avaliação de Pares**
- **Decisão** (`decision-making-av.pares`)
  - **Descrição:** Avaliações específicas sobre decisões tomadas pelos usuários em um contexto de pares.
  - **Relacionamentos:** Vincula a avaliação ao usuário avaliado e ao que realiza a avaliação.
- **Colaboração** (`collaboration-av.pares`)
  - **Descrição:** Focado em avaliar a eficácia da colaboração entre pares.
  - **Relacionamentos:** Registra quem colaborou com quem e quais foram os resultados.

### Relacionamentos

- **Usuários e Jogos:** Cada usuário pode participar em múltiplas sessões de pré-jogo, durante o jogo e pós-jogo.
- **Feedbacks e Avaliações:** As avaliações durante as sessões de jogo são diretamente ligadas aos feedbacks que se seguem, garantindo que toda a informação relevante seja capturada e associada corretamente aos participantes.

### Regras de Negócio

- **Integridade dos Dados:** É crucial que todas as entradas de dados sejam validadas para garantir que as relações entre as tabelas sejam mantidas sem inconsistências.
- **Confidencialidade:** Os dados dos usuários, especialmente feedbacks e avaliações, devem ser mantidos confidenciais e seguros.
- **Consistência das Informações:** As informações devem ser coerentes em todas as etapas do jogo e refletir de maneira fiel as interações ocorridas.

### Diagrama

Segue o diagrama do modelo relacional, ilustrando as entidades envolvidas e seus relacionamentos:

assets/diagrama.png

### Considerações Finais

Este modelo relacional fornece a estrutura necessária para o desenvolvimento e manutenção de um sistema de jogo interativo complexo, que depende da integridade, segurança e coerência dos dados para funcionar corretamente. As adaptações podem ser necessárias conforme o projeto evolui e novas necessidades são identificadas.

**Observações:**

- **Flexibilidade do Modelo:** O modelo pode ser ajustado conforme necessário para atender melhor às exigências do projeto.
- **Documentação Detalhada:** Recomenda-se manter uma documentação detalhada e atualizada para facilitar a compreensão e o desenvolvimento contínuo do sistema.
- **Boas Práticas:** A implementação deve seguir boas práticas de desenvolvimento de banco de dados para garantir a performance e a escalabilidade do sistema.
