# Guia de Importação da Máquina Virtual Ubuntu Server 22.04.4 LTS no Oracle VirtualBox 7.2

## Objetivo

Importar a imagem virtual `UbuntuServer-OnPremises.ova` no Oracle VirtualBox 7.2, configurar a rede em modo **Bridge (Ponte)** utilizando a rede cabeada do laboratório e iniciar a máquina virtual para acesso remoto via SSH.

---

# 🖥️ Informações do Ambiente do Laboratório

| Item | Informação |
|---|---|
| Sistema Operacional | Microsoft Windows 11 |
| Virtualizador | Oracle VirtualBox 7.2 |
| Máquina Virtual | Ubuntu Server 22.04.4 LTS |
| Arquivo da VM | `UbuntuServer-OnPremises.ova` |
| Local do Arquivo | Pasta `Downloads` |
| Rede do Laboratório | `10.24.82.0/24` |
| Processador | Intel Core I7-14700K |
| Memória RAM | 32GB |
| Armazenamento | SSD 1TB |

---

# 📥 Etapa 01 — Abrir o Oracle VirtualBox

1. Clique no botão **Iniciar** do Windows.
2. Pesquise por:

   ```text
   VirtualBox
   ```

3. Clique em:

   ```text
   Oracle VirtualBox
   ```

4. Aguarde a abertura do programa.

---

# 📦 Etapa 02 — Importar a Máquina Virtual (.OVA)

1. No menu superior clique em:

   ```text
   Arquivo → Importar Appliance
   ```

2. Clique no ícone da pasta 📁.

3. Navegue até:

   ```text
   Downloads
   ```

4. Selecione o arquivo:

   ```text
   UbuntuServer-OnPremises.ova
   ```

5. Clique em:

   ```text
   Próximo
   ```

---

# ⚙️ Etapa 03 — Revisar as Configurações da Importação

1. Verifique as configurações apresentadas.

2. Confirme principalmente:

| Configuração | Valor Esperado |
|---|---|
| Sistema Operacional | Ubuntu (64-bit) |
| Memória RAM | Conforme definido pelo professor |
| Disco Virtual | VDI/VMDK |
| Controladora de Rede | Intel/Bridge |

3. Clique em:

   ```text
   Finalizar
   ```

4. Aguarde o processo de importação.

⏳ Esse processo pode levar alguns minutos.

---

# 🌐 Etapa 04 — Configurar Rede em Modo Bridge (Ponte)

## Objetivo da Configuração

Permitir que a máquina virtual receba um endereço IP da rede do laboratório:

```text
10.24.82.0/24
```

Assim a VM poderá ser acessada remotamente via SSH.

---

## Configuração da Rede

1. Selecione a máquina virtual importada.

2. Clique em:

   ```text
   Configurações
   ```

3. Acesse a opção:

   ```text
   Rede
   ```

4. Em **Adaptador 1**, configure:

| Campo | Configuração |
|---|---|
| Habilitar Placa de Rede | ✅ Marcado |
| Conectado a | Adaptador em Ponte |
| Nome | Placa de rede cabeada do laboratório |
| Modo Promíscuo | Permitir Tudo |
| Cabo Conectado | ✅ Marcado |

---

# 🔌 Etapa 05 — Selecionar a Rede Cabeada Correta

1. No campo:

   ```text
   Nome
   ```

2. Escolha a interface física cabeada do computador.

Normalmente ela aparece com nomes semelhantes a:

```text
Intel Ethernet
Realtek PCIe
Ethernet
```

⚠️ NÃO selecionar:
- Wi-Fi
- Bluetooth
- VPN
- Adaptadores Virtuais

---

# ▶️ Etapa 06 — Iniciar a Máquina Virtual

1. Clique na máquina virtual.

2. Clique em:

   ```text
   Iniciar
   ```

3. Aguarde o boot do Ubuntu Server.

---

# 🔑 Etapa 07 — Fazer Login no Ubuntu Server

Na tela de login digite:

```text
Usuário: (informado pelo professor)
Senha: (informada pelo professor)
```

⚠️ A senha no Linux não aparece na tela durante a digitação.

---

# 🌍 Etapa 08 — Verificar o Endereço IP da Máquina Virtual

Após realizar o login execute o comando:

```bash
ip a
```

ou

```bash
ip addr
```

---

## Resultado Esperado

A interface de rede deverá possuir um endereço IP semelhante a:

```text
10.24.82.X
```

Exemplo:

```text
10.24.82.120
```

---

# 🔐 Etapa 09 — Testar o Serviço SSH

Execute o comando:

```bash
systemctl status ssh
```

---

## Resultado Esperado

O serviço deverá aparecer como:

```text
active (running)
```

---

# 💻 Etapa 10 — Acesso Remoto via SSH

No Windows 11 abra:

```text
Prompt de Comando
```

ou

```text
PowerShell
```

Execute:

```powershell
ssh usuario@IP_DA_VM
```

Exemplo:

```powershell
ssh aluno@10.24.82.120
```

---

# ✅ Resultado Final Esperado

Ao finalizar a atividade:

- ✅ Máquina virtual importada corretamente
- ✅ Ubuntu Server iniciado
- ✅ Rede em modo Bridge configurada
- ✅ VM recebendo IP da rede `10.24.82.0/24`
- ✅ Serviço SSH ativo
- ✅ Acesso remoto funcionando

---

# 🧠 Dicas Importantes

## ✔ Sempre verificar:
- Se o cabo de rede está conectado
- Se a placa correta foi escolhida no Bridge
- Se a VM recebeu IP da rede do laboratório

---

## ✔ Comandos Úteis

### Verificar IP

```bash
ip a
```

### Verificar SSH

```bash
systemctl status ssh
```

### Reiniciar rede

```bash
sudo systemctl restart NetworkManager
```

---

# 📚 Conclusão

A máquina virtual Ubuntu Server 22.04.4 LTS foi importada com sucesso no Oracle VirtualBox 7.2 e configurada para utilizar a rede física do laboratório em modo Bridge (Ponte), permitindo comunicação direta na rede `10.24.82.0/24` e acesso remoto seguro via SSH.
