# Relatório de Testes 

## 1. Visão Geral do Sistema e Escopo

O projeto **NaSalinha** é composto por três módulos principais de funcionalidades:
1. **Módulo de Autenticação e Acesso (JWT):** Controla o registro de usuários, fluxo de ativação por e-mail, restrição de acessos e controle de permissões baseado em funções (RBAC) com foco no perfil `ADMINISTRADOR`.
2. **Módulo de Check-in (Mídia):** Gerencia o registro diário de atividades por meio do envio de imagens associadas a temporadas ativas, tratando regras de concorrência temporal e integridade de arquivos.
3. **Módulo de Pontuação e Ranking:** Regula a concessão automática de pontos baseada em check-ins válidos, estornos de pontuação e exibição do ranking ordenado.

---

## 2. Requisitos vs. Casos de Teste

| Código Requisito | Descrição do Requisito | IDs dos Casos de Teste Associados |
| :--- | :--- | :--- |
| **RF-01** | Cadastro e Verificação (Nome, E-mail, Senha, Código de ativação e Status Pendente) | `#3`, `#4`, `#6`, `#7`, `#10`, `#17`, `#18`, `#23`, `#24`, `#26` |
| **RF-02** | Restrição de Login para contas não confirmadas por e-mail | `#22` |
| **RF-03** | Controle de Níveis  | `#12`, `#19` |
| **RF-04** | Registro de Check-in | `#8`, `#9`, `#13`, `#14`, `#15`, `#21` |
| **RF-05** | Fluxo de Status do Check-in  | `#11` |
| **RF-06** | Restrição de Propriedade | `#20`, `#25` |
| **RF-07** | Atribuição de Pontos e atualização automática do ranking | `#16` |
| **RF-08** | Consistência de Saldo (Subtração automática ao remover check-in) | `#1` |
| **RF-09** | Regras de Ranking | Mapeado em conjunto com as validações de intervalo do `#14` |

---

## 3. Visão geral dos Testes

| Casos Planejados | Casos Testados | Pass | Fail |
| :--- | :--- | :--- | :--- |
| 24 | 20 | 12 | 8 |

---

## 4. Distribuição de gravidade

| Crítico | Alto | Médio | Baixo |
| :--- | :--- | :--- | :--- |
| 2 | 1 | 5 | 0 | 

## 5. Teste de Regressão
Afim de exemplificar os testes de regressão, foi simulado a correção do bug em que o usuário conseguia criar uma conta com o cargo de "adiministrador".
Assim, foi "testado" :
1. Se o usuário conseguiria criar uma conta com o cargo "administrador" através da Api.
2. Se os usuários ainda conseguem criar contas com outros cargos.
3. Se o é possível ainda fazer login em uma conta "administrador"
4. Se o "administrador" manteve seu acesso completo ao CRUD do sistema.

## 6. Considerações Finais

O Sistema apresenta falhas que compromentem a segunrança dos usuários e das própias informações do sistema, necessitando assim, de mais trabalho para garantir uma melhor usuabilidade e confiabilidade nesse.







    * Não há cenários explícitos para validar o comportamento do servidor quanto à exclusão de arquivos temporários (**RNF-02**), o que pode ser mitigado por testes automatizados de infraestrutura ou testes unitários na service de mídia.
Relatorio_de_Testes_NaSalinha.md
Exibindo Relatorio_de_Testes_NaSalinha.md.
