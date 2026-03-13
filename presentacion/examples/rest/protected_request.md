### Request (Headers)

POST /v1/calculadora/suma HTTP/1.1
Host: api.ejemplo.com
Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IlB1YmxvIiwiaWF0IjoxNTE2MjM5MDIyfQ.SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV_adQssw5c
Content-Type: application/json

### Request (Body)

```json
{
  "numero_a": 50,
  "numero_b": 25,
  "seguridad": {
    "transaccion_id": "TX-9901",
    "hash_verificacion": "8f686725-d41c-463d-8153-f36894c2e684",
    "dato_cifrado": "U2FsdGVkX1+92Vp6Wk8vM1p3eXQy..."
  }
}
```

---

### Response (Error 401)

HTTP/1.1 401 Unauthorized
Content-Type: application/json

```json
{
  "error": {
    "tipo": "Autenticacion",
    "codigo": 401,
    "mensaje": "Token invalido o expirado",
    "timestamp": "2026-03-13T14:15:00Z"
  }
}
```

---

### Response (Success 200)

HTTP/1.1 200 OK
Content-Type: application/json

```json
{
  "resultado": 75,
  "status": "success",
  "id_confirmacion": "CONF-12345"
}
```
