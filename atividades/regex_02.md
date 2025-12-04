# 📝 **Logs do Sistema de Monitoramento da Capsule Corp**

Use TODO o conteúdo abaixo como base para as perguntas.

```text
2025-03-12 14:22:10 INFO  [capsulecorp.local] User goku.ssj logged in from 192.168.0.42
2025-03-12 14:22:11 INFO  [capsulecorp.local] Request GET /scouter/status HTTP/1.1 200 OK
2025-03-12 14:22:12 WARN  [capsulecorp.local] High power level detected: 53000 (source: Scouter)
2025-03-12 14:22:14 ERROR [capsulecorp.local] Failed to load module "SuperSaiyan.dll": code 0xA13F

2025-03-12 15:01:55 INFO  [training.room] User vegeta accessed training module: gravity=150g
2025-03-12 15:02:10 INFO  [training.room] User trunks.future uploaded file battle_report_01.txt (size: 12MB)
2025-03-12 15:02:44 ERROR [training.room] Unauthorized access attempt detected from IP 10.0.0.88
2025-03-12 15:03:01 WARN  [training.room] Power reading unstable: 18.3k → 21.6k

2025-03-12 16:40:33 INFO  [email.server] Sent message to "guerreiro.z@capsulecorp.com"
2025-03-12 16:40:33 INFO  [email.server] Message ID <msg-9912@capsulecorp.com> delivered
2025-03-12 16:41:02 ERROR [email.server] Connection timeout for smtp.capsulecorp.com port 587

2025-03-12 17:10:22 INFO  [security.core] Login failure for user raditz from IP 172.16.0.77
2025-03-12 17:10:25 INFO  [security.core] Login success for user raditz after 3 attempts
2025-03-12 17:10:40 CRITICAL [security.core] ALERT! Unauthorized Ki spike detected: 98,000 → 120,000

2025-03-12 18:30:02 INFO  [system.kernel] Process "hyper_saiyan_mode" exited with code 0
2025-03-12 18:30:05 WARN  [system.kernel] Memory usage at 92%
2025-03-12 18:30:10 ERROR [system.kernel] Kernel panic: module "god_ki_driver" failed to initialize
```

---

# 🔍 **PERGUNTAS DE REGEX SOBRE OS LOGS**

As perguntas agora são **técnicas**, com foco em padrões reais de logs.

---

## 1. **Extrair todos os endereços IP presentes no log.**

Metacaracteres sugeridos: `\d`, `+`, `{n,m}`, `(...)`, `.`

---

## 2. **Encontrar todas as linhas que registram falha (ERROR ou CRITICAL).**

Metacaracteres sugeridos: `^`, `(...)`, `|`, `\b`

---

## 3. **Capturar apenas os nomes de usuário presentes nos logs (ex.: goku.ssj, vegeta, trunks.future).**

Metacaracteres sugeridos: `\w`, `.`, `+`, `\b`

---

## 4. **Encontrar todas as linhas que contêm emails.**

Metacaracteres sugeridos: `\w`, `.`, `+`, `@`, `\b`

---

## 5. **Capturar o domínio de email da Capsule Corp (capsulecorp.com).**

Metacaracteres sugeridos: `\w`, `+`, `.`, `{n,m}`

---

## 6. **Extrair as datas no formato YYYY-MM-DD.**

Metacaracteres sugeridos: `\d`, `{n}`

---

## 7. **Extrair os horários (HH:MM:SS).**

Metacaracteres sugeridos: `\d`, `{n}`

---

## 8. **Capturar o nome do host (ex.: capsulecorp.local, training.room, email.server).**

Metacaracteres sugeridos: `\w`, `.`, `+`

---

## 9. **Capturar a rota HTTP (ex.: /scouter/status).**

Metacaracteres sugeridos: `/`, `\w`, `+`

---

## 10. **Encontrar todos os códigos HTTP (200, 404, etc).**

Metacaracteres sugeridos: `\b`, `\d`, `{3}`

---

## 11. **Extrair apenas os arquivos mencionados (.dll, .txt, executáveis).**

Metacaracteres sugeridos: `.`, `\w`, `+`

---

## 12. **Encontrar logs onde ocorreu tentativa de acesso não autorizado.**

Palavras-chave: `Unauthorized`, `Login failure`

Sugestão: usar `(...) | (...)`.

---

## 13. **Capturar valores de leitura de energia "numéricos + k" (ex.: 18.3k, 21.6k).**

Metacaracteres sugeridos: `\d`, `.`, `+`

---

## 14. **Capturar transições de Ki (ex.: 98,000 → 120,000).**

Metacaracteres sugeridos: `\d`, `,`, `+`, `(...)`, `\1` *(para validar padrões iguais, se desejar).*

---

## 15. **Capturar mensagens de kernel (linhas que contêm a string `"system.kernel"`).**

Metacaracteres sugeridos: `\b`, `.`, `*`

---

## 16. **Extrair IDs de mensagem como `<msg-9912@capsulecorp.com>`.**

Metacaracteres sugeridos: `<`, `>`, `.`, `\w`, `+`

---

## 17. **Extrair nomes de processos (ex.: "hyper_saiyan_mode").**

Metacaracteres sugeridos: `"`, `\w`, `_`, `+`

---

## 18. **Encontrar valores percentuais (ex.: 92%).**

Metacaracteres sugeridos: `\d`, `+`, `%`

---

## 19. **Identificar logs que retornaram código hexadecimal de erro (ex.: 0xA13F).**

Metacaracteres sugeridos: `0x`, `[A-Fa-f0-9]`, `+`

---

## 20. **Capturar a frase final do log: `"Treino concluído OK"`**

Metacaracteres sugeridos: `"`, `\b`, `$`

