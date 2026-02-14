# Endpoints Especiais / Autenticação e Usuário - ZeladorX API

Esta seção documenta os **endpoints transversais** da API ZeladorX que não fazem parte de macro serviços específicos (ex: jardinagem, limpeza predial, agendamentos). Eles lidam principalmente com:

- Autenticação e gerenciamento de sessão
- Perfil do usuário
- Troca de senha (usuário logado)
- Recuperação / reset de senha (esquecida)
- Outras operações de segurança e configuração básica

**Base URL:** `https://api.zeladorx.com/v1` (ou `/v2` dependendo da versão)

**Autenticação geral:**  
A maioria dos endpoints requer **Bearer Token** (JWT) no header:  
`Authorization: Bearer <seu-token>`

Endpoints de login/recuperação **não** requerem autenticação prévia.

## 1. Autenticação Básica

### POST /auth/login  
Efetua login do usuário (síndico, zelador, administrador, etc.)

**Body (JSON):**
```json
{
  "email": "usuario@condominio.com",
  "password": "SenhaForte123!"
}
