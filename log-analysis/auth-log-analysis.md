# Auth Log Analysis - Linux

## Cenário 1: Privilege Escalation
**Objetivo:** Simular elevação de privilégio via sudo  
**Comando executado:**
```bash```
sudo /opt/splunk/bin/splunk start

Evento registrado no Splunk:

session opened for user root

COMMAND=/opt/splunk/bin/splunk start
Interpretação:

Usuário pedrosilva abriu sessão root.

Demonstra elevação de privilégio.

#Cenário 2: Failed Login

Objetivo: Simular falha de autenticação
Comando executado:
sudo -k
sudo ls

Evento registrado no Splunk:

authentication failure
Interpretação:

Mostra falha de autenticação.

Útil para detectar brute force ou erro de digitação.

#Cenário 3: Sessões de root

Objetivo: Monitorar sessões de root
Query Splunk usada:
source="/var/log/auth.log" "session opened"
Evento registrado:

Todas as sessões abertas por root no período.
Interpretação:

Permite monitorar atividades privilegiadas
