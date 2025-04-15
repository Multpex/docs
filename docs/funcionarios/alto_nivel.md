# Dynamic System Overview - Gestão de Funcionários (vx.x.x)

**Última atualização**: YYYY-MM-DD (Sprint #X)

---

## Funcionalidades Principais
1. **RF-FUN-1 Cadastro de Funcionários**
   - Campos obrigatórios: sap, email, ...
   - RNs: RN-FUN-1

2. **RF-FUN-2 Adicionar ou atualizar Perfil de Acesso de Usuário**
   - Vincula funcionário a um perfil (role)
   - RNs: RN-FUN-2 RN-FUN-3

3. **RF-FUN-3 Integração com Keycloak**
   - Chamadas automáticas à API do Keycloak durante:
     - Criação de perfil de acesso.
     - Atualização de e-mail, perfil ou status do funcionário.
   - RNs: RN-FUN-2, RN-FUN-3, RN-FUN-4

---

## Regras de Negócio Críticas
| ID       | Descrição | Aplicável a | Fonte (Sprint/Decisão) |
|----------|-----------|-------------|------------------------|
| RN-FUN-1 | Campo sap é único | RF-FUN-1 |  |
| RN-FUN-2 | Todo funcionário com perfil de acesso é um usuário do sistema, por consequência deve ter um usuário criado no **Keycloak** | RF-FUN-2 RF-FUN-3 | [ADR-FUN-1](docs/funcionarios/adr/1) |
| RN-FUN-3 | Atualizações no cadastro de funcionários (perfil, email, status) devem refletir no **Keycloak** | RF-FUN-2 RF-FUN-3 | [ADR-FUN-1](docs/funcionarios/adr/1) |
| RN-FUN-4 | Falhas na integração com Keycloak devem gerar registro em log, e deve ser possível tentar novamente a atualização | RF-FUN-3 | [ADR-FUN-1](docs/funcionarios/adr/1) |

---

## Diagrama de Contexto Atual
** @TODO **
