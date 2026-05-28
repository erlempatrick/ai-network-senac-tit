# 📘 Documentação Técnica de Rede — Estação Windows

## 🖥️ 1. Informações Gerais do Equipamento

### 🔹 Identificação do Host

| Campo | Informação |
|---|---|
| 🖥️ Nome do Host | `TIT0728106W11-1` |
| 🌐 Domínio / DNS Primário | `senacsp.edu.br` |
| 🔀 Tipo de Nó | Híbrido |
| 🚫 Roteamento IP | Não habilitado |
| 🚫 Proxy WINS | Não habilitado |

### 📌 Subcategoria — Observações Gerais

| Item | Status |
|---|---|
| ✅ Equipamento integrado ao domínio institucional | Sim |
| ✅ Comunicação com DNS corporativo | Funcionando |
| ✅ Rede operacional | Sim |

### 📝 Resumo Simplificado
O computador está conectado corretamente à rede da instituição e consegue acessar a internet normalmente.

---

# 🌐 2. Adaptadores de Rede

## 🔹 Adaptador Principal — Rede Corporativa

| Campo | Informação |
|---|---|
| 🔌 Adaptador | Intel(R) Ethernet Connection (17) I219-LM |
| 🧾 MAC Address | `D8-43-AE-E1-78-50` |
| 🌍 IPv4 | `10.24.82.33` |
| 🧱 Máscara de Rede | `255.255.255.0` |
| 🚪 Gateway | `10.24.82.1` |
| 📡 DHCP | Habilitado |
| 🧠 DNS Primário | `10.24.40.190` |
| 🧠 DNS Secundário | `10.1.1.195` |
| 🧠 DNS Terciário | `10.1.1.242` |
| 🔁 NetBIOS | Habilitado |

---

### 📌 Subcategoria — Configuração DHCP

| Campo | Informação |
|---|---|
| 📅 Concessão Obtida | 26/05/2026 13:37 |
| ⏰ Expiração | 27/05/2026 02:57 |
| 🖧 Servidor DHCP | `10.24.40.190` |

### 📌 Subcategoria — Status Operacional

| Item | Resultado |
|---|---|
| ✅ Adaptador ativo | Sim |
| ✅ Comunicação com gateway | Sim |
| ✅ Recebimento automático de IP | Sim |
| ✅ DNS configurado | Sim |

### 📝 Resumo Simplificado
A placa de rede principal está funcionando corretamente, recebendo configurações automáticas da rede e acessando a internet sem problemas.

---

## 🔹 Adaptador Virtual — VirtualBox

| Campo | Informação |
|---|---|
| 🔌 Adaptador | VirtualBox Host-Only Ethernet Adapter |
| 🧾 MAC Address | `0A-00-27-00-00-08` |
| 🌍 IPv4 | `192.168.56.1` |
| 🧱 Máscara de Rede | `255.255.255.0` |
| 📡 DHCP | Não habilitado |
| 🚪 Gateway | Não configurado |

### 📌 Subcategoria — Finalidade

| Item | Informação |
|---|---|
| 🖥️ Tipo | Adaptador Virtual |
| ⚙️ Uso comum | Máquinas Virtuais |
| 🌐 Acesso Internet | Não |

### 📝 Resumo Simplificado
Existe uma rede virtual instalada para uso de máquinas virtuais no computador. Ela não interfere na internet principal.

---

# 🧭 3. Interfaces de Rede Detectadas

| ID | Interface | Tipo |
|---|---|---|
| 8 | VirtualBox Host-Only Ethernet Adapter | Virtual |
| 12 | Intel(R) Ethernet Connection (17) I219-LM | Física |
| 1 | Software Loopback Interface 1 | Sistema |

### 📌 Subcategoria — Classificação

| Tipo | Quantidade |
|---|---|
| 🖥️ Física | 1 |
| 🧪 Virtual | 1 |
| ⚙️ Sistema | 1 |

### 📝 Resumo Simplificado
O computador possui uma placa de rede física, uma interface virtual e uma interface interna do próprio sistema operacional.

---

# 🛣️ 4. Tabela de Rotas IPv4

## 🔹 Rota Padrão

| Destino | Gateway | Interface |
|---|---|---|
| `0.0.0.0` | `10.24.82.1` | `10.24.82.33` |

### 📌 Subcategoria — Redes Locais

| Rede | Máscara | Interface |
|---|---|---|
| `10.24.82.0` | `255.255.255.0` | Rede Corporativa |
| `192.168.56.0` | `255.255.255.0` | Rede VirtualBox |

### 📌 Subcategoria — Rotas Persistentes

| Status | Informação |
|---|---|
| 🚫 Rotas Persistentes | Nenhuma configurada |

### 📝 Resumo Simplificado
O computador possui rotas corretas para acessar tanto a rede interna quanto a internet.

---

# 🌍 5. Tabela de Rotas IPv6

| Tipo | Status |
|---|---|
| 🌐 IPv6 Link-Local | Ativo |
| 🔁 Rotas IPv6 | Configuradas |
| 📌 Rotas Persistentes | Nenhuma |

### 📌 Subcategoria — Interfaces IPv6

| Interface | Endereço |
|---|---|
| Rede Física | `fe80::1abc:8d7f:9202:d0b0` |
| Rede Virtual | `fe80::711a:95b2:d95f:882b` |

### 📝 Resumo Simplificado
O protocolo IPv6 está ativo no computador e funcionando apenas para comunicação local da rede.

---

# 🧠 6. Servidores DNS

| Tipo | Endereço |
|---|---|
| 🧠 DNS Principal | `10.24.40.190` |
| 🧠 DNS Secundário | `10.1.1.195` |
| 🧠 DNS Terciário | `10.1.1.242` |

---

### 📌 Subcategoria — Testes DNS

| Consulta | Resultado |
|---|---|
| `dns.google` | Resolvido |
| `google.com` | Resolvido |
| 🌐 Resolução IPv4 | Funcionando |
| 🌐 Resolução IPv6 | Funcionando |

### 📝 Resumo Simplificado
O sistema consegue localizar sites e serviços corretamente através dos servidores DNS da rede.

---

# 📶 7. Testes de Conectividade

## 🔹 Ping para DNS Google — 8.8.8.8

| Métrica | Resultado |
|---|---|
| 📤 Pacotes Enviados | 4 |
| 📥 Pacotes Recebidos | 4 |
| ❌ Perda | 0% |
| ⚡ Latência Média | 4ms |

---

## 🔹 Ping para Google.com

| Métrica | Resultado |
|---|---|
| 📤 Pacotes Enviados | 4 |
| 📥 Pacotes Recebidos | 4 |
| ❌ Perda | 0% |
| ⚡ Latência Média | 3ms |

### 📌 Subcategoria — Avaliação da Rede

| Item | Resultado |
|---|---|
| 🌐 Acesso Internet | OK |
| ⚡ Latência | Baixa |
| 📡 Comunicação Externa | Estável |
| 🚫 Perda de Pacotes | Não identificada |

### 📝 Resumo Simplificado
A conexão com a internet está rápida, estável e sem falhas aparentes.

---

# 🔒 8. Diagnóstico Geral da Rede

| Verificação | Status |
|---|---|
| ✅ IP Obtido Corretamente | OK |
| ✅ Gateway Respondendo | OK |
| ✅ DNS Funcionando | OK |
| ✅ Comunicação Internet | OK |
| ✅ Rede Corporativa Ativa | OK |
| ✅ Adaptador Principal Operacional | OK |
| ⚠️ Adaptador Virtual Presente | Normal |

---

# 📋 9. Conclusão Técnica

| Item Avaliado | Resultado |
|---|---|
| 🖥️ Configuração da Máquina | Correta |
| 🌐 Comunicação com Rede | Estável |
| 📡 Acesso à Internet | Funcional |
| 🧠 Resolução DNS | Operacional |
| 🔐 Estrutura de Rede | Sem inconsistências aparentes |

### 📝 Resumo Simplificado Final
O computador está configurado corretamente, conectado à rede da instituição e acessando a internet normalmente. Não foram encontrados problemas relevantes na comunicação da rede.
