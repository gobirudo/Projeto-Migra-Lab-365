+ PARTE 004 - Transferência de FSMO e Configuração de Redundância no AD

## 🛡️ Etapa 1: Backup do Ambiente de Diretório

Antes de qualquer modificação crítica na infraestrutura de Active Directory, foi realizado um processo completo de **backup preventivo**:

- **Servidor de backup:** VEEAM-01 (Windows Server)
- **Storage:** LUN 02 (50GB) no STORAGE-01, provisionada e conectada via iSCSI Initiator ao VEEAM-01
- **Repositório Veeam configurado** no disco da LUN 02
- **Backups criados:** Servidores ADDS-000 e ADDS-001
- **Testes realizados:**
  - Verificação de consistência dos backups
  - Teste de restauração pontual (Instant VM Recovery)
  - Validação do repositório de backup via console do Veeam

---

## 🔁 Etapa 2: Transferência das FSMO

- **Servidor antigo:** ADDS-000 (Windows Server 2012)
- **Novo holder:** ADDS-001 (Windows Server 2022)

Procedimentos:

- Transferência das 5 funções FSMO:
  - Schema Master
  - Domain Naming Master
  - RID Master
  - PDC Emulator
  - Infrastructure Master
- Comandos utilizados:
  - `netdom query fsmo`
  - `ntdsutil`
- **Validações pós-transferência:**
  - Verificação do novo holder de FSMO
  - Testes de replicação
  - Autenticação de usuários no novo DC

---

## 🧹 Etapa 3: Despromoção do ADDS-000

- Execução do `dcpromo` para remoção do ADDS-000 como controlador
- Reinicialização e validação da remoção dos serviços de AD
- **Snapshots** tirados antes e depois da operação para segurança
- Testes de replicação e login com novos usuários após a remoção

---

## 🔄 Etapa 4: Implementação de Redundância com ADDS-002

- Criação e promoção do servidor **ADDS-002** (Windows Server 2022)
- Ingresso no domínio como **Domain Controller adicional**
- Replicação validada entre ADDS-001 e ADDS-002
- Sincronização automática confirmada
---

Status final: Ambiente AD atualizado, redundante, com servidores modernos e replicação estável para suportar demandas atuais e futuras.
