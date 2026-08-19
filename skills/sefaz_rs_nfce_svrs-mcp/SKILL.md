---
name: sefaz_rs_nfce_svrs-mcp
description: Skill da REST API do SEFAZ RS: NFC-e (SVRS) na MCP.AI: 1 endpoint em /api/sefaz_rs_nfce_svrs. SEFAZ RS: NFC-e (SVRS), consulta em fonte oficial. Hospedado pela plataforma, sem credenciais da plataforma, pague por consulta com crédito pré-pago. Autentique com workspace API key (sk_live) gerada em app.mcp.ai/settings/api-keys. Use quando o usuário pedir algo coberto pelos endpoints.
---

# SEFAZ RS: NFC-e (SVRS) — REST API skill

Você tem acesso à **SEFAZ RS: NFC-e (SVRS)** REST API na MCP.AI.

> SEFAZ RS: NFC-e (SVRS), consulta em fonte oficial. Hospedado pela plataforma, sem credenciais da plataforma, pague por consulta com crédito pré-pago.

## Base URL

```
https://api.mcp.ai/api/sefaz_rs_nfce_svrs
```

Todo endpoint é um **POST** na Base URL + o path abaixo. Os parâmetros vão no corpo JSON.

## Autenticação

Inclua em toda request:

```
Authorization: Bearer sk_live_...
Content-Type: application/json
```

> Gere sua chave em **https://app.mcp.ai/settings/api-keys** (workspace API key `sk_live_…`, não expira, revogável). Uma única chave serve pra todos os seus MCPs.

## Formato de resposta

```json
{ "ok": true, "tool": "<tool_id>", "result": <payload> }
```

## Exemplo cURL

```bash
curl -X POST https://api.mcp.ai/api/sefaz_rs_nfce_svrs/consultar \
  -H "Authorization: Bearer sk_live_..." \
  -H "Content-Type: application/json" \
  -d '{"nfce":"..."}'
```

## Reportar problemas

Se um endpoint retornar erro, vazio ou dado inesperado, reporte (não desista calado): **POST /api/sefaz_rs_nfce_svrs/report** com `{ "message": "...", "context"?: "...", "conversation"?: [...] }`. Isso notifica o time da MCP.AI.

## Endpoints (1)

#### `sefaz_rs_nfce_svrs_consultar`

SEFAZ RS: NFC-e (SVRS), consulta em fonte oficial. _(POST /api/sefaz_rs_nfce_svrs/consultar)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `nfce` | string | Sim | Parâmetro de consulta "nfce". |
| `login_cpf` | string | Não | Parâmetro de consulta "login_cpf". |
| `login_senha` | string | Não | Parâmetro de consulta "login_senha". |
| `pkcs12_cert` | string | Não | Parâmetro de consulta "pkcs12_cert". |
| `pkcs12_pass` | string | Não | Parâmetro de consulta "pkcs12_pass". |

---

Este MCP também funciona via **conexão MCP** (Claude / Cursor) em `https://api.mcp.ai/p_sefaz_rs_nfce_svrs` — veja o [README](../../README.md). A skill acima é pra consumir a **REST API** direto (agente próprio / código).
