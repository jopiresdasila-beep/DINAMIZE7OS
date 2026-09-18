# Dinamize7OS

SaaS white-label para operação de agências, separado do Dinamize OS original.

## Stack
- Frontend estático responsivo
- Supabase Auth + Postgres + Storage + Edge Functions
- Vercel
- GitHub

## Módulos atuais
- Login e primeiro administrador
- Área da agência
- Portal do cliente
- Clientes
- Agenda / reuniões
- Cronograma de conteúdos
- Aprovação ou solicitação de alteração pelo cliente
- Equipe e acessos
- Serviços, notas, arquivos, mensagens, notificações e auditoria no backend

## Segurança
O projeto usa uma chave **publishable** do Supabase no navegador, que é pública por definição. Nenhuma secret key ou service role deve ser versionada aqui. As tabelas expostas têm Row Level Security (RLS).

## Backend
Projeto Supabase: `gugjzwdgmledwrgxznhb`

## Deploy
Projeto Vercel: `dinamize7os`
