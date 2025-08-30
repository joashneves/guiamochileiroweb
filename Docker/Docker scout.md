
# O que é ?
O Docker scout é um serviço para o docker que consistem em segurança, sua funcionalidade se concentra em analisar imagens e encontrar brechas de seguranças

# Analisar todas as vulnerabilidades
Buscar por todas as vulnerabilidades com:

```bash
docker scout cves "Docker"
```

# Filtrar por severidade alta ou crítica
 Filtrar com `--only-severity critical,high`, para que apareçam somente as vulnerabilidades classificadas como “Critical” e “High” ficando com linha de execução:
```bash
docker scout cves --only-severity critical,high "Docker"
```

# Refs
[Docker Scout | Docker Docs](https://docs.docker.com/scout/)

[Docker Security - OWASP Cheat Sheet Series](https://cheatsheetseries.owasp.org/cheatsheets/Docker_Security_Cheat_Sheet.html)
[Segurança do Docker - Série de folhas de dicas do OWASP](https://cheatsheetseries-owasp-org.translate.goog/cheatsheets/Docker_Security_Cheat_Sheet.html?_x_tr_sl=en&_x_tr_tl=pt&_x_tr_hl=pt-BR&_x_tr_pto=wapp)