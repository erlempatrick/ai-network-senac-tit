# Consolidação de Serviços Ubuntu

## Serviços Ativos Associados às Portas

| Serviço | Processo | Porta(s) | Protocolo | Status |
|---|---|---|---|---|
| SSH | sshd / systemd | 22 | TCP | Ativo |
| Node Exporter | node_exporter | 9100 | TCP | Ativo |
| Prometheus | prometheus | 9091 | TCP | Ativo |
| Apache Tomcat 11 | java (tomcat11) | 8080 | TCP | Ativo |
| MySQL Community Server | mysqld | 3306, 33060 | TCP | Ativo |
| Grafana | grafana | 3000 | TCP | Ativo |
| Systemd Resolved | systemd-resolved | 53 | TCP/UDP | Ativo |
| Apache HTTP Server | apache2 | 80, 8888 | TCP | Ativo |
| Systemd Networkd | systemd-networkd | 68 | UDP | Ativo |

---

## Serviços Ativos Sem Associação de Porta

| Serviço Ativo | Unidade (systemd) | Porta Associada | Observação |
|---|---|---|---|
| Cron | cron.service | Não | Agendamento de tarefas |
| D-Bus | dbus.service | Não | Barramento de comunicação do sistema |
| Getty | getty@tty1.service | Não | Terminal local |
| Modem Manager | ModemManager.service | Não | Gerenciamento de modem |
| Multipath Device Controller | multipathd.service | Não | Gerenciamento de multipath |
| Polkit | polkit.service | Não | Controle de autorização |
| Rsyslog | rsyslog.service | Não | Serviço de logs |
| Systemd Journald | systemd-journald.service | Não | Coleta de logs do sistema |
| Systemd Logind | systemd-logind.service | Não | Gerenciamento de sessões |
| Systemd Timesyncd | systemd-timesyncd.service | Não | Sincronização de horário |
| Systemd Udevd | systemd-udevd.service | Não | Gerenciamento de dispositivos |
| Udisks2 | udisks2.service | Não | Gerenciamento de discos |
| Unattended Upgrades | unattended-upgrades.service | Não | Atualizações automáticas |
| UPower | upower.service | Não | Gerenciamento de energia |
| User Manager UID 1000 | user@1000.service | Não | Sessão do usuário |

---

## Sugestões de Hardening e Otimização

| Serviço | Situação Identificada | Sugestões de Hardening | Sugestões de Otimização |
|---|---|---|---|
| OpenSSH Server | Porta 22 exposta e sessões SSH ativas | Alterar porta padrão, desabilitar login root (`PermitRootLogin no`), forçar autenticação por chave SSH, habilitar Fail2ban, limitar usuários via `AllowUsers`, desativar protocolos e algoritmos legados | Ajustar `ClientAliveInterval`, limitar tentativas (`MaxAuthTries`), habilitar compressão apenas quando necessário |
| Apache2 Server | Portas 80 e 8888 expostas | Habilitar HTTPS/TLS 1.2+, remover módulos desnecessários, ocultar banner (`ServerTokens Prod`), habilitar ModSecurity e Fail2ban, configurar headers HTTP seguros | Habilitar KeepAlive otimizado, compressão GZIP/Brotli, cache HTTP, MPM Event, ajuste de `MaxRequestWorkers` |
| Apache Tomcat Server | Porta 8080 exposta | Remover aplicações padrão (`docs`, `examples`, `manager`), usar proxy reverso Apache/Nginx, habilitar TLS, restringir acesso ao Manager, executar com usuário sem privilégios | Ajustar heap JVM (`-Xms/-Xmx`), configurar pool de threads, habilitar compressão HTTP, revisar GC da JVM |
| MySQL Server | Portas 3306 e 33060 abertas | Restringir bind para rede interna, remover usuários anônimos, aplicar política forte de senha, desabilitar acesso root remoto, habilitar TLS entre clientes | Ajustar `innodb_buffer_pool_size`, índices otimizados, tuning de cache e conexões, habilitar slow query log |
| Grafana Server | Porta 3000 exposta | Alterar credenciais padrão, integrar LDAP/OAuth, habilitar HTTPS, restringir acesso externo, desabilitar signup público | Configurar retenção de dashboards/logs, otimizar datasource queries, habilitar cache |
| Prometheus Server | Porta 9091 exposta | Restringir acesso via firewall/reverse proxy, autenticação externa, limitar targets monitorados, segmentar rede de monitoração | Ajustar retenção (`--storage.tsdb.retention.time`), reduzir scrape interval desnecessário, otimizar cardinalidade de métricas |
| Node Exporter | Porta 9100 ativa | Restringir acesso somente ao Prometheus, bind em localhost/rede privada, firewall específico para coleta | Desabilitar collectors não utilizados, reduzir consumo de CPU e I/O do exporter |
| GLPI Help Desk | Não identificado diretamente, provável hospedagem Apache/MySQL | Implementar HTTPS obrigatório, MFA para administradores, restringir plugins não oficiais, backups frequentes, WAF no Apache | Ajustar cache PHP OPcache, otimizar consultas MySQL, separar banco em servidor dedicado |
| Wordpress CMS | Não identificado diretamente, provável hospedagem Apache/MySQL | Atualizar plugins/temas, remover plugins inativos, habilitar WAF, MFA, desabilitar XML-RPC se não utilizado, limitar `/wp-admin` | Habilitar cache (Redis/Varnish), CDN, OPcache, compressão GZIP, otimização de banco e imagens |

---

## Recomendações Gerais de Infraestrutura

| Categoria | Recomendações Gerais de Infraestrutura |
|---|---|
| Firewall | Restringir portas expostas apenas às redes necessárias utilizando `ufw`, `iptables` ou firewall externo |
| Monitoramento | Configurar alertas no Prometheus/Grafana para CPU, memória, disco, falhas de autenticação e indisponibilidade |
| Logs | Centralizar logs com `rsyslog`, Elastic Stack ou Loki |
| Atualizações | Habilitar política controlada de patching e revisão periódica de CVEs |
| Segmentação | Separar serviços críticos em VLANs/sub-redes distintas |
| Backup | Aplicar estratégia 3-2-1 com testes periódicos de restauração |
| TLS/Certificados | Padronizar uso de TLS com certificados válidos e renovação automática |
| Controle de Acesso | Implementar MFA e RBAC para serviços administrativos |
| Auditoria | Habilitar auditoria de acessos SSH, Apache, MySQL e aplicações web |
| Containers/Isolamento | Avaliar isolamento via Docker/Podman ou VMs dedicadas para serviços críticos |
