# Documentação Técnica — Servidor ctlinux01

**Sistema Operacional:** Ubuntu Server 24.04.4 LTS (Noble Numbat)
**Data de Geração:** 01/06/2026
**Finalidade:** Auditoria | Inventário de Ativos | Troubleshooting
**Classificação:** INTERNO — USO RESTRITO

---

## Sumário

1. [Informações Gerais do Servidor](#1-informações-gerais-do-servidor)
2. [Informações de Hardware do Servidor](#2-informações-de-hardware-do-servidor)
3. [Informações de Rede do Servidor](#3-informações-de-rede-do-servidor)
4. [Informações de Serviços e Processos](#4-informações-de-serviços-e-processos)
5. [Informações de Softwares e Atualizações](#5-informações-de-softwares-e-atualizações)

---

## 1. Informações Gerais do Servidor

| Categoria | Descrição | Configuração |
|-----------|-----------|--------------|
| Hostname | Nome de identificação do servidor na rede | `ctlinux01` |
| Machine ID | Identificador único permanente do sistema | `05c2865e767d44c4870777b482ba0652` |
| Boot ID | Identificador da sessão de inicialização atual | `a5a81cd031274f22b58fcf4ab580cf85` |
| Sistema Operacional | Distribuição Linux instalada | Ubuntu 24.04.4 LTS (Noble Numbat) |
| Kernel | Núcleo do sistema operacional em execução | Linux 6.8.0-107-generic #107-Ubuntu SMP PREEMPT_DYNAMIC |
| Arquitetura | Tipo de processador suportado | x86_64 (64 bits) |
| Codinome Ubuntu | Nome interno da versão do sistema | noble |
| Compilação do Kernel | Data em que o kernel foi compilado | Fri, 13 Mar 2026 19:51:50 UTC |
| Fuso Horário | Referência de tempo usada pelo sistema | UTC |
| Uptime | Tempo contínuo em funcionamento desde o último boot | 1h 58min (coletado às 23:27:55) |
| Usuários Logados | Quantidade de sessões abertas no momento da coleta | 10 usuários ativos |
| Load Average | Carga média de processamento do servidor | 0.01 (1min) · 0.00 (5min) · 0.00 (15min) |

### O que isso significa para a gestão?

Este servidor está identificado na rede como **ctlinux01** e opera com o sistema **Ubuntu Server 24.04.4 LTS**, uma versão empresarial de longo suporte (LTS — Long Term Support), o que garante atualizações de segurança até **abril de 2029**.

No momento da coleta, o servidor estava ligado há menos de 2 horas, com **10 usuários conectados simultaneamente** e carga de processamento praticamente zero — indicando que o sistema estava **ocioso e saudável** naquele instante. O fuso horário configurado como UTC é padrão para servidores de infraestrutura, facilitando a correlação de logs em ambientes distribuídos.

---

## 2. Informações de Hardware do Servidor

### 2.1 Plataforma e Virtualização

| Categoria | Descrição | Configuração |
|-----------|-----------|--------------|
| Tipo de Chassis | Formato físico ou virtual do servidor | Virtual Machine (vm) |
| Hypervisor | Plataforma de virtualização que hospeda este servidor | Oracle VirtualBox |
| Hardware Vendor | Fabricante do hardware virtual | innotek GmbH |
| Hardware Model | Modelo do hardware reportado pelo sistema | VirtualBox |
| Firmware | Versão do firmware (BIOS) da máquina virtual | VirtualBox · Data: Fri 2006-12-01 |

### 2.2 Memória RAM e Swap

| Categoria | Descrição | Configuração |
|-----------|-----------|--------------|
| RAM Total | Memória principal total disponível no servidor | 3.915 MB (~4 GB) |
| RAM Usada | Memória RAM em uso no momento da coleta | 589 MB |
| RAM Livre | Memória RAM imediatamente disponível | 2.930 MB |
| RAM Disponível | Memória real disponível considerando cache | 3.326 MB |
| Swap Total | Memória virtual em disco usada como extensão da RAM | 3.914 MB (~4 GB) |
| Swap Usada | Swap efetivamente em uso | 0 MB (não utilizada) |
| Swap Livre | Swap disponível para uso | 3.914 MB |

### 2.3 Disco e Partições

| Categoria | Descrição | Configuração |
|-----------|-----------|--------------|
| sda | Disco principal do servidor | 50 GB — Disco físico virtual |
| sda1 | Partição reservada para o bootloader do sistema | 1 MB — Partição de boot GRUB |
| sda2 | Partição que armazena os arquivos de inicialização do kernel | 2 GB — Montada em `/boot` · Uso: 200 MB · Livre: 1,6 GB |
| sda3 | Partição destinada ao volume lógico LVM | 48 GB — Grupo de volume LVM |
| ubuntu-vg/ubuntu-lv | Volume lógico principal onde o sistema operacional reside | 48 GB — Montado em `/` · Uso: 8,5 GB · Livre: 37 GB (19%) |
| sr0 | Drive de CD/DVD virtual (geralmente não utilizado em servidores) | 1.024 MB — ROM virtual |

### O que isso significa para a gestão?

Este servidor é uma **máquina virtual** rodando sobre o Oracle VirtualBox, o que significa que **não existe hardware físico dedicado** — ele compartilha recursos de um servidor físico hospedeiro. Isso é comum em ambientes de virtualização, mas implica que o desempenho pode ser afetado por outros sistemas rodando na mesma máquina física.

**Memória RAM:** O servidor possui aproximadamente **4 GB de RAM**. No momento da coleta, apenas **589 MB estavam em uso**, indicando baixa demanda. Porém, 4 GB é um volume **limitado para cargas de trabalho com múltiplos containers Docker ativos simultaneamente**. Em horários de pico ou com crescimento no uso de containers, esse recurso deve ser monitorado com atenção.

**Armazenamento:** O disco principal possui **50 GB**, dos quais **37 GB ainda estão disponíveis (81% livre)**. Não há risco imediato de esgotamento, mas o crescimento de logs e volumes Docker deve ser acompanhado periodicamente.

---

## 3. Informações de Rede do Servidor

### 3.1 Interfaces de Rede

| Categoria | Descrição | Configuração |
|-----------|-----------|--------------|
| lo | Interface de loopback — comunicação interna do próprio servidor consigo mesmo | IP: 127.0.0.1/8 · IPv6: ::1/128 · MAC: 00:00:00:00:00:00 |
| enp0s3 | Interface de rede principal — conecta o servidor à rede corporativa | IP: 10.24.82.200/24 · IPv6: fe80::a00:27ff:fe42:90a5/64 · MAC: 08:00:27:42:90:a5 |
| docker0 | Bridge de rede criada automaticamente pelo Docker para comunicação entre containers | IP: 172.17.0.1/16 · IPv6: fe80::4c15:bdff:fe3d:de85/64 · MAC: 4e:15:bd:3d:de:85 |
| veth1321de1 | Interface virtual que conecta um container ativo ao bridge Docker | Sem IP · IPv6: fe80::48c1:39ff:fef7:48f4/64 · MAC: 4a:c1:39:f7:48:f4 |

### 3.2 Tabela de Rotas

| Categoria | Descrição | Configuração |
|-----------|-----------|--------------|
| Rota Padrão (Default Gateway) | Caminho padrão para o tráfego de rede sair do servidor em direção à Internet ou outros segmentos | 10.24.82.1 via enp0s3 (proto static) |
| Rede Local Corporativa | Sub-rede interna à qual o servidor pertence | 10.24.82.0/24 via enp0s3 (proto kernel) |
| Rede Docker | Sub-rede interna usada exclusivamente para comunicação entre containers | 172.17.0.0/16 via docker0 (proto kernel) |

### 3.3 DNS e Resolução de Nomes

| Categoria | Descrição | Configuração |
|-----------|-----------|--------------|
| Modo resolv.conf | Método de configuração de DNS adotado pelo sistema | stub (gerenciado pelo systemd-resolved) |
| DNS Servidor Atual | Servidor DNS primário atualmente em uso | 8.8.4.4 (Google DNS) |
| Servidores DNS Configurados | Lista de servidores de resolução de nomes | 8.8.8.8 · 8.8.4.4 (Google DNS) |
| DNSSEC | Validação de segurança de domínios via criptografia | Não suportado / Desabilitado |
| LLMNR | Resolução de nomes local sem servidor DNS | Desabilitado |
| mDNS | Resolução de nomes em redes locais sem configuração | Desabilitado |
| DNS over TLS | Criptografia do tráfego DNS | Desabilitado |

### 3.4 Portas em Escuta

| Categoria | Descrição | Configuração |
|-----------|-----------|--------------|
| Porta 53 (127.0.0.54) | DNS stub interno do systemd-resolved | LISTEN · Local: 127.0.0.54:53 |
| Porta 22 (0.0.0.0) | Acesso remoto via SSH — permite administração segura do servidor | LISTEN · Local: 0.0.0.0:22 · Serviço: OpenBSD sshd |
| Porta 53 (127.0.0.53) | Resolvedor DNS local do sistema | LISTEN · Local: 127.0.0.53%lo:53 |
| Porta 9000 (IPv4) | Interface web do Portainer para gerenciamento visual de containers Docker | LISTEN · Local: 0.0.0.0:9000 |
| Porta 9000 (IPv6) | Interface web do Portainer acessível via IPv6 | LISTEN · Local: [::]:9000 |

### O que isso significa para a gestão?

O servidor está na rede corporativa com o endereço **10.24.82.200** e usa como saída o gateway **10.24.82.1**. Além da rede corporativa, existe uma rede interna exclusiva do Docker (**172.17.0.0/16**) para comunicação entre os containers — esse tráfego é isolado e não interfere na rede da empresa.

O DNS está configurado com os servidores do Google (8.8.8.8 e 8.8.4.4), o que é funcional, mas em ambientes corporativos é recomendável avaliar o uso de servidores DNS internos para maior controle e privacidade.

**Atenção de segurança:** A porta **22 (SSH) está aberta para qualquer endereço IP** (0.0.0.0), o que significa que o servidor aceita tentativas de acesso remoto de qualquer origem. Recomenda-se revisar com a equipe de segurança se isso é intencional ou se deve ser restrito a endereços específicos da rede interna. A porta **9000 (Portainer)** também está exposta publicamente — o acesso a essa interface deve ser protegido por autenticação forte.

---

## 4. Informações de Serviços e Processos

| Categoria | Descrição | Configuração |
|-----------|-----------|--------------|
| containerd.service | Runtime de baixo nível responsável pelo ciclo de vida dos containers — base do Docker | loaded · active · running |
| cron.service | Agendador de tarefas automáticas do sistema operacional | loaded · active · running |
| dbus.service | Barramento de mensagens do sistema para comunicação entre processos | loaded · active · running |
| docker.service | Motor principal do Docker — gerencia criação e execução de containers | loaded · active · running |
| fwupd.service | Serviço de atualização de firmware de hardware | loaded · active · running |
| getty@tty1.service | Terminal virtual local (console físico do servidor) | loaded · active · running |
| ModemManager.service | Gerenciador de modems e conexões móveis | loaded · active · running |
| multipathd.service | Controlador de múltiplos caminhos para dispositivos de armazenamento | loaded · active · running |
| polkit.service | Gerenciador de permissões e autorizações do sistema | loaded · active · running |
| portainer.service | Interface web para gerenciamento visual de containers Docker | loaded · active · running |
| rsyslog.service | Serviço de coleta e armazenamento de logs do sistema | loaded · active · running |
| ssh.service | Servidor SSH para acesso remoto seguro ao servidor | loaded · active · running |
| systemd-hostnamed.service | Serviço responsável pelo nome do host do servidor | loaded · active · running |
| systemd-journald.service | Serviço de journaling — registra eventos e logs do sistema | loaded · active · running |
| systemd-logind.service | Gerenciador de sessões e login de usuários | loaded · active · running |
| systemd-networkd.service | Serviço de configuração e gerenciamento de rede | loaded · active · running |
| systemd-resolved.service | Serviço de resolução de nomes DNS | loaded · active · running |
| systemd-timesyncd.service | Sincronização de data e hora via rede (NTP) | loaded · active · running |
| systemd-udevd.service | Gerenciador de eventos de dispositivos de hardware | loaded · active · running |
| udisks2.service | Gerenciador de discos e dispositivos de armazenamento | loaded · active · running |
| unattended-upgrades.service | Serviço de aplicação automática de atualizações de segurança | loaded · active · running |
| upower.service | Daemon de gerenciamento de energia | loaded · active · running |
| user@1001.service | Sessão de gerenciamento do usuário com UID 1001 | loaded · active · running |
| user@1002.service | Sessão de gerenciamento do usuário com UID 1002 | loaded · active · running |

**Total de serviços monitorados:** 24 | **Todos os serviços:** loaded · active · running

### O que isso significa para a gestão?

Todos os **24 serviços críticos** do servidor estão **ativos e funcionando normalmente** no momento da coleta. Não há serviços com falha ou parados.

Os serviços mais relevantes do ponto de vista do negócio são:

- **docker.service** e **containerd.service** — São o coração da operação de containers. Se pararem, todos os serviços hospedados em containers param junto.
- **portainer.service** — Ferramenta de gerenciamento visual de containers, acessível via navegador na porta 9000. Permite que a equipe técnica gerencie containers sem precisar usar linha de comando.
- **ssh.service** — Permite que administradores acessem o servidor remotamente de forma segura.
- **unattended-upgrades.service** — Aplica automaticamente atualizações de segurança, reduzindo o risco de exposição a vulnerabilidades conhecidas.

Dois usuários com sessões ativas (UID 1001 e UID 1002) estavam com sessões de sistema abertas, o que é normal em servidores com múltiplos administradores.

---

## 5. Informações de Softwares e Atualizações

### 5.1 Resumo de Atualizações

| Categoria | Descrição | Configuração |
|-----------|-----------|--------------|
| Total de Pacotes com Atualização Pendente | Quantidade de softwares instalados que possuem versão mais nova disponível | 29 pacotes |
| Repositório Principal | Fonte oficial de pacotes do Ubuntu utilizada | noble-updates (Ubuntu 24.04) |
| Repositório Docker | Fonte oficial dos pacotes do Docker CE | noble — Repositório oficial Docker |
| Docker CE — Versão Instalada | Versão atual do motor Docker em execução no servidor | 5:29.2.1-1~ubuntu.24.04~noble |
| Docker CE — Versão Disponível | Versão mais recente do Docker CE disponível para atualização | 5:29.4.0-1~ubuntu.24.04~noble |
| Docker Compose Plugin — Instalado | Versão atual da ferramenta de orquestração de múltiplos containers | 5.1.0 |
| Docker Compose Plugin — Disponível | Versão mais recente disponível para atualização | 5.1.1 |
| containerd.io — Instalado | Versão atual do runtime de containers | 2.2.1 |
| containerd.io — Disponível | Versão mais recente disponível para atualização | 2.2.2 |

### 5.2 Lista Completa de Pacotes com Atualização Pendente

| Categoria | Descrição | Configuração |
|-----------|-----------|--------------|
| binutils-common | Utilitários binários do sistema (ferramentas de compilação) | Instalado: 2.42-4ubuntu2.8 → Disponível: 2.42-4ubuntu2.10 · Repo: noble-updates |
| binutils-x86-64-linux-gnu | Utilitários binários específicos para arquitetura x86-64 | Instalado: 2.42-4ubuntu2.8 → Disponível: 2.42-4ubuntu2.10 · Repo: noble-updates |
| binutils | Pacote principal de utilitários binários | Instalado: 2.42-4ubuntu2.8 → Disponível: 2.42-4ubuntu2.10 · Repo: noble-updates |
| containerd.io | Runtime de containers — base do Docker | Instalado: 2.2.1-1~ubuntu.24.04~noble → Disponível: 2.2.2-1~ubuntu.24.04~noble · Repo: noble (Docker) |
| coreutils | Utilitários fundamentais do sistema Linux (ls, cp, mv, etc.) | Instalado: 9.4-3ubuntu6.1 → Disponível: 9.4-3ubuntu6.2 · Repo: noble-updates |
| docker-buildx-plugin | Plugin do Docker para builds avançados de imagens | Instalado: 0.31.1-1~ubuntu.24.04~noble → Disponível: 0.33.0-1~ubuntu.24.04~noble · Repo: noble (Docker) |
| docker-ce-cli | Interface de linha de comando do Docker | Instalado: 5:29.2.1-1~ubuntu.24.04~noble → Disponível: 5:29.4.0-1~ubuntu.24.04~noble · Repo: noble (Docker) |
| docker-ce-rootless-extras | Componentes para execução do Docker sem privilégios de root | Instalado: 5:29.2.1-1~ubuntu.24.04~noble → Disponível: 5:29.4.0-1~ubuntu.24.04~noble · Repo: noble (Docker) |
| docker-ce | Motor principal do Docker CE | Instalado: 5:29.2.1-1~ubuntu.24.04~noble → Disponível: 5:29.4.0-1~ubuntu.24.04~noble · Repo: noble (Docker) |
| docker-compose-plugin | Plugin para orquestração de múltiplos containers | Instalado: 5.1.0-1~ubuntu.24.04~noble → Disponível: 5.1.1-1~ubuntu.24.04~noble · Repo: noble (Docker) |
| fwupd | Serviço de atualização de firmware de hardware | Instalado: 1.9.33-0ubuntu1~24.04.1ubuntu1 → Disponível: 1.9.34-0ubuntu1~24.04.1 · Repo: noble-updates |
| libbinutils | Biblioteca de suporte para utilitários binários | Instalado: 2.42-4ubuntu2.8 → Disponível: 2.42-4ubuntu2.10 · Repo: noble-updates |
| libctf-nobfd0 | Biblioteca CTF para depuração de binários | Instalado: 2.42-4ubuntu2.8 → Disponível: 2.42-4ubuntu2.10 · Repo: noble-updates |
| libsystemd0 | Biblioteca principal do systemd — usada por todos os serviços do sistema | Instalado: 255.4-1ubuntu8.14 → Disponível: 255.4-1ubuntu8.15 · Repo: noble-updates |
| libudev1 | Biblioteca de gerenciamento de dispositivos de hardware | Instalado: 255.4-1ubuntu8.14 → Disponível: 255.4-1ubuntu8.15 · Repo: noble-updates |
| linux-base | Arquivos base de suporte ao kernel Linux | Instalado: 4.5ubuntu9+24.04.1 → Disponível: 4.5ubuntu9+24.04.2 · Repo: noble-updates |
| lshw | Ferramenta de listagem de hardware do servidor | Instalado: 02.19.git.2021.06.19.996aaad9c7-2build3 → Disponível: 02.19.git.2021.06.19.996aaad9c7-2ubuntu0.24.04.1 · Repo: noble-updates |
| netplan-generator | Gerador de configurações de rede para o netplan | Instalado: 1.1.2-8ubuntu1~24.04.1 → Disponível: 1.1.2-8ubuntu1~24.04.2 · Repo: noble-updates |
| netplan.io | Ferramenta de configuração de rede do Ubuntu | Instalado: 1.1.2-8ubuntu1~24.04.1 → Disponível: 1.1.2-8ubuntu1~24.04.2 · Repo: noble-updates |
| nftables | Framework moderno de filtragem de pacotes de rede (firewall) | Instalado: 1.0.9-1build1 → Disponível: 1.0.9-1ubuntu0.1 · Repo: noble-updates |
| python3-netplan | Bindings Python para o netplan | Instalado: 1.1.2-8ubuntu1~24.04.1 → Disponível: 1.1.2-8ubuntu1~24.04.2 · Repo: noble-updates |
| sosreport | Ferramenta de coleta de informações de diagnóstico do sistema | Instalado: 4.9.2-0ubuntu0~24.04.1 → Disponível: 4.10.2-0ubuntu0~24.04.1 · Repo: noble-updates |
| systemd-dev | Arquivos de desenvolvimento do systemd | Instalado: 255.4-1ubuntu8.14 → Disponível: 255.4-1ubuntu8.15 · Repo: noble-updates |
| systemd-resolved | Serviço de resolução de nomes DNS do systemd | Instalado: 255.4-1ubuntu8.14 → Disponível: 255.4-1ubuntu8.15 · Repo: noble-updates |
| systemd-sysv | Compatibilidade do systemd com scripts SysV init | Instalado: 255.4-1ubuntu8.14 → Disponível: 255.4-1ubuntu8.15 · Repo: noble-updates |
| systemd-timesyncd | Serviço de sincronização de horário via NTP | Instalado: 255.4-1ubuntu8.14 → Disponível: 255.4-1ubuntu8.15 · Repo: noble-updates |
| systemd | Gerenciador de serviços e inicialização do sistema | Instalado: 255.4-1ubuntu8.14 → Disponível: 255.4-1ubuntu8.15 · Repo: noble-updates |
| ubuntu-drivers-common | Ferramenta de gerenciamento de drivers de hardware | Instalado: 1:0.9.7.6ubuntu3.5 → Disponível: 1:0.9.7.6ubuntu3.6 · Repo: noble-updates |
| udev | Gerenciador de dispositivos de hardware em tempo real | Instalado: 255.4-1ubuntu8.14 → Disponível: 255.4-1ubuntu8.15 · Repo: noble-updates |

### O que isso significa para a gestão?

Existem **29 pacotes com atualizações pendentes**, distribuídos em dois grupos principais:

**Atualizações do Sistema Operacional (Ubuntu):** Pacotes como `systemd`, `linux-base`, `nftables` e `coreutils` possuem versões mais novas disponíveis. Destaque para o `systemd` — ele é o gerenciador central de todos os serviços do servidor. A atualização desse pacote exige **reinicialização do servidor** e deve ser agendada em uma **janela de manutenção planejada** para evitar indisponibilidade inesperada.

**Atualizações do Docker CE:** Os pacotes `docker-ce`, `docker-ce-cli`, `containerd.io` e `docker-compose-plugin` possuem versões mais novas. A atualização do Docker requer **restart do serviço Docker**, o que causa uma **interrupção temporária de todos os containers em execução**. Deve ser planejada com antecedência.

> **Recomendação:** Agendar uma janela de manutenção para execução do comando `sudo apt update && sudo apt upgrade -y`. Priorizar as atualizações de segurança do `systemd` e do `Docker CE`. Após a atualização do `systemd`, será necessário reiniciar o servidor. Informar previamente as equipes que utilizam os serviços hospedados neste servidor.

---

*Documento gerado em 01/06/2026 — Servidor ctlinux01 — Ubuntu Server 24.04.4 LTS*
*Classificação: INTERNO — USO RESTRITO*
