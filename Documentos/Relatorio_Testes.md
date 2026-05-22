# Relatório de Testes 

## 1. Visão Geral do Sistema e Escopo

O projeto **NaSalinha** é composto por três módulos principais de funcionalidades:
1. **Módulo de Autenticação e Acesso (JWT):** Controla o registro de usuários, fluxo de ativação por e-mail, restrição de acessos e controle de permissões baseado em funções.
2. **Módulo de Check-in:** Gerencia o registro de atividades por meio do envio de imagens associadas a temporadas ativas, tratando regras de concorrência temporal e integridade de arquivos.
3. **Módulo de Pontuação e Ranking:** Regula a concessão automática de pontos baseada em check-ins válidos, estornos de pontuação e exibição do ranking ordenado.

---

## 2. Requisitos vs. Casos de Teste

| Código Requisito | Descrição do Requisito | IDs dos Casos de Teste Associados |
| :--- | :--- | :--- |
| **RF-01** | Cadastro e Verificação (Nome, E-mail, Senha, Código de ativação e Status Pendente) |`C-1`, `C-2`, `C-7`, `C-8`, `R-1`, `R-2`, `R-4`, `Bug-2`, `Bug-3`, `Bug-4`, `Bug-9` |
| **RF-02** | Restrição de Login para contas não confirmadas por e-mail | `C-12` |
| **RF-03** | Controle de Níveis  | `C-9`, `Bug-8` |
| **RF-04** | Registro de Check-in | `C-3`, `C-4`, `C-5`, `C-11`, `Bug-6`, `Bug-7` |
| **RF-05** | Fluxo de Status do Check-in  | `Bug-5` |
| **RF-06** | Restrição de Propriedade | `C-10`, `R-3` |
| **RF-07** | Atribuição de Pontos e atualização automática do ranking | `C-6` |
| **RF-08** | Consistência de Saldo (Subtração automática ao remover check-in) | `Bug-1` |
| **RF-09** | Regras de Ranking | `Bug-7` |

---

## 3. Visão geral dos Testes

| Casos Planejados | Casos Testados | Pass | Fail | Taxa de sucesso |
| :--- | :--- | :--- | :--- | :--- |
| 25 | 21 | 12 | 9 | 60% |

---

## 4. Distribuição de gravidade

| Crítico | Maiores | Baixo | Total |
| :--- | :--- | :--- | :--- |
| 2 | 7 | 0 | 9 |

## 5. Teste de Regressão
A fim de exemplificar os testes de regressão, foi simulada a correção do bug em que o usuário conseguia criar uma conta com o cargo de "administrador".
Após a correção validou-se se:
1. O usuário conseguiria criar uma conta com o cargo "administrador" através da API. (Esperado: Bloqueado)
2. Os usuários ainda conseguem criar contas com outros cargos. (Esperado: Sucesso)
3. É possível ainda fazer login em uma conta "administrador". (Esperado: Sucesso)
4. O "administrador" manteve seu acesso completo ao CRUD do sistema. (Esperado: Sucesso)

## 6. Considerações Finais

O Sistema apresenta falhas críticas que compromentem a segurança dos usuários e a integridade das própias informações cadastradas. Desse modo, é necessário um trabalho de correção e reteste para garantir uma melhor usuabilidade e confiabilidade do site.
Sendo assim, é altamente recomendável que não seja disponibilizado ao público geral no estado atual.
