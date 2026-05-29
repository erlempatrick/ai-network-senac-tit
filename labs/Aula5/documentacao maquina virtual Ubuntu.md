# Análise da Máquina Ubuntu

## Informações Gerais da Máquina

| Item | Informação |
|---|---|
| Hostname | `wslinux01` |
| Sistema Operacional | Ubuntu 24.04.4 LTS |
| Codename | noble |
| Interface de Rede | `enp0s3` |
| IP Principal | `10.24.82.214` |
| IP Secundário (DHCP) | `10.24.82.47` |
| Gateway | `10.24.82.1` |
| DNS Configurados | `8.8.8.8`, `8.8.4.4`, `10.24.40.190`, `10.1.1.195`, `10.1.1.242` |

---

# Estrutura de Rede Identificada

## Interface de Rede

A máquina possui uma interface ativa:

| Interface | Status | Tipo |
|---|---|---|
| `enp0s3` | Ativa | Rede física |

Também existe a interface local:

| Interface | Função |
|---|---|
| `lo` | Comunicação interna da máquina |

---

# Configuração IP

Foi identificado:

- Um IP fixo:
  - `10.24.82.214`

- Um IP dinâmico DHCP:
  - `10.24.82.47`

Isso indica que a máquina está utilizando simultaneamente:
- configuração estática
- configuração dinâmica DHCP

---

# Serviços Identificados em Execução

## Serviços Web e Monitoramento

| Serviço | Porta |
|---|---|
| SSH | 22 |
| Apache | 80 |
| Apache Alternativo | 8888 |
| Tomcat | 8080 |
| MySQL | 3306 |
| MySQL X Protocol | 33060 |
| Grafana | 3000 |
| Prometheus | 9091 |
| Node Exporter | 9100 |

---

# Observações Relevantes

## SSH Ativo

O serviço SSH está ativo na porta 22, permitindo acesso remoto.

## Banco de Dados

O serviço MySQL está operante nas portas:
- 3306
- 33060

## Serviços Web

Foram encontrados:
- Apache
- Tomcat

Isso indica que a máquina provavelmente hospeda aplicações web.

## Monitoramento

Existem ferramentas de monitoramento instaladas:
- Prometheus
- Grafana
- Node Exporter

---

# Sessão Recomendada — Segurança

## Verificar usuários logados

```bash
who
```

## Verificar tentativas de acesso SSH

```bash
sudo journalctl -u ssh
```

## Verificar portas abertas

```bash
sudo ss -tulnp
```

---

# Sessão Recomendada — Hardware

## Informações do Processador

```bash
lscpu
```

## Informações da Memória RAM

```bash
free -h
```

## Informações do Disco

```bash
lsblk
```

## Espaço em Disco

```bash
df -h
```

---

# Sessão Recomendada — Rede

## Ver IP da máquina

```bash
ip addr
```

## Ver rotas da rede

```bash
ip route
```

## Ver DNS configurado

```bash
resolvectl status
```

## Ver placas de rede disponíveis

```bash
ip link show
```

## Verificar se IP é DHCP ou Estático

```bash
cat /etc/netplan/*.yaml
```

---

# Sessão Recomendada — Serviços

## Ver todos os serviços ativos

```bash
systemctl list-units --type=service --state=running
```

## Ver todos os serviços instalados

```bash
service --status-all
```

## Ver processos ativos

```bash
ps aux
```

---

# Sessão Recomendada — Atualizações do Sistema

## Atualizar lista de pacotes

```bash
sudo apt update
```

## Ver atualizações disponíveis

```bash
apt list --upgradable
```

## Aplicar atualizações

```bash
sudo apt upgrade
```

## Atualização completa do sistema

```bash
sudo apt full-upgrade
```

---

# Tabela Geral de Comandos Úteis

| Comando | Função |
|---|---|
| `lsb_release -a` | Exibe versão do Ubuntu |
| `hostname` | Mostra nome da máquina |
| `ip addr` | Mostra IPs e interfaces |
| `ip route` | Mostra rotas da rede |
| `ip link show` | Lista placas de rede |
| `resolvectl status` | Mostra DNS configurado |
| `lscpu` | Informações do processador |
| `free -h` | Informações da memória RAM |
| `lsblk` | Lista discos e partições |
| `df -h` | Mostra uso do disco |
| `ps aux` | Lista processos ativos |
| `top` | Monitoramento em tempo real |
| `htop` | Monitoramento avançado |
| `systemctl list-units --type=service --state=running` | Lista serviços em execução |
| `service --status-all` | Lista serviços instalados |
| `ss -tulnp` | Lista portas abertas |
| `who` | Usuários logados |
| `journalctl -u ssh` | Logs do SSH |
| `sudo apt update` | Atualiza lista de pacotes |
| `apt list --upgradable` | Lista atualizações disponíveis |
| `sudo apt upgrade` | Instala atualizações |
| `sudo apt full-upgrade` | Atualização completa do sistema |
| `uname -a` | Informações do kernel |
| `uptime` | Tempo ligado da máquina |
| `neofetch` | Resumo geral da máquina |
| `sudo fdisk -l` | Informações detalhadas de discos |
| `sudo dmidecode` | Informações detalhadas do hardware |
| `netstat -tulnp` | Ver conexões e portas |
| `ping 8.8.8.8` | Teste de conectividade |
| `curl ifconfig.me` | Ver IP público |
| `history` | Histórico de comandos |
| `last` | Histórico de logins |
| `dmesg` | Logs do sistema e hardware |
