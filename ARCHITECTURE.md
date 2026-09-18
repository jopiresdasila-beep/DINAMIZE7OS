# Arquitetura — Dinamize7OS

## Multi-tenancy
Cada registro operacional pertence a uma agência por `agency_id`. Clientes pertencem à agência e usuários de clientes são ligados por `client_members`.

## Papéis
### Agência
- owner
- admin
- manager
- designer
- social_media
- finance
- member

### Cliente
- client_admin
- client_approver
- client_viewer

## Fluxo de aprovação
1. Agência cria conteúdo.
2. Item fica em `not_requested`.
3. Agência envia para aprovação.
4. Item muda para `awaiting_client`.
5. Cliente aprova ou solicita alteração.
6. A ação é registrada em `content_approvals`.
7. Trigger sincroniza o status do conteúdo.
8. Agência recebe notificação.

## Tabelas principais
- agencies
- agency_branding
- profiles
- agency_members
- clients
- client_members
- projects
- tasks
- calendar_events
- content_schedules
- content_schedule_items
- content_approvals
- notifications
- audit_log
- services
- notes
- files
- messages

## Edge Functions
- `claim-owner`: configura o primeiro proprietário uma única vez.
- `create-user`: cria usuário de equipe ou cliente, permitido apenas para owner/admin.

## Princípios de segurança
- RLS em tabelas expostas.
- Sem `service_role` no frontend.
- Arquivos privados no Storage.
- Ações administrativas autenticadas no backend.
