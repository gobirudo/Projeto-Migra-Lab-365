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



 *****************************
             PRINTS
 ******************************
 
---

- CONFIGURAÇÃO DO FILESERVER COM O STORAGE
- SOFTWARE UTILISADO: HP P4000 Centralized Management Console
- Criado uma Lun e atribuída ao VEEAM
![PARTE 001 - STORAGE LUN](https://github.com/user-attachments/assets/193a43a8-10ff-41db-a736-174c43ddb59b)
![PARTE 002 - VEEAM LUN](https://github.com/user-attachments/assets/fe0f4252-43df-43b3-b613-1aff78ea1df7)

- Criado o disco para servir de repositório dos backups.
![PARTE 003 - VEEAM DISK](https://github.com/user-attachments/assets/71857b5f-466e-4e96-9247-6508732121b4)
![PARTE 004 - VEEAM BACKUP](https://github.com/user-attachments/assets/d5952899-c7e4-4adc-87a9-ed0fc7fa756f)
![PARTE 005 - VEEAM BACKUP](https://github.com/user-attachments/assets/e276319b-cdba-4308-a282-787f5d75bcfc)
![PARTE 006 - VEEAM BACKUP](https://github.com/user-attachments/assets/50ed3ea1-68b9-4d67-80df-b7db7a665907)
![PARTE 007 - VEEAM BACKUP](https://github.com/user-attachments/assets/126991fb-d2fc-489f-805b-c4a6a56f28bb)
![PARTE 008 - VEEAM BACKUP](https://github.com/user-attachments/assets/6da54208-20a7-44e0-85f5-bcdab0bf0e08)
![PARTE 009 - VEEAM BACKUP](https://github.com/user-attachments/assets/41074365-d7a4-4c59-acc5-e421e58a429c)
![PARTE 010 - VEEAM BACKUP](https://github.com/user-attachments/assets/35006499-e4a0-4b99-b041-c52d36cd8b7d)
![PARTE 011 - VEEAM BACKUP](https://github.com/user-attachments/assets/a7655552-2f5a-4fe9-ae97-c8720e9795a5)
![PARTE 012 - VEEAM BACKUP](https://github.com/user-attachments/assets/60167b31-69d4-411c-bc30-a89026c60e6a)
![PARTE 013 - VEEAM BACKUP](https://github.com/user-attachments/assets/6cb18145-2ed4-4200-bc31-bbd034221ea4)
![PARTE 014 - VEEAM BACKUP](https://github.com/user-attachments/assets/5b68230a-fa1a-4588-8c58-5fd7793bc821)
![PARTE 015 - VEEAM BACKUP](https://github.com/user-attachments/assets/aecf899b-f9d1-4ee3-a55c-5e3521674d32)
![PARTE 016 - VEEAM BACKUP](https://github.com/user-attachments/assets/81cc37e9-4853-4000-800a-074a48e3ca8d)
![PARTE 017 - VEEAM BACKUP](https://github.com/user-attachments/assets/c4c540c1-2840-4b3f-92bb-3f1c82a30b2b)
![PARTE 018 - VEEAM BACKUP](https://github.com/user-attachments/assets/7f19a464-d8a4-4fc4-9239-15a47a8d991b)
![PARTE 019 - VEEAM BACKUP](https://github.com/user-attachments/assets/438e181a-74b2-4133-8452-5fe6bb95e760)
![PARTE 020 - VEEAM BACKUP](https://github.com/user-attachments/assets/a6d9463f-9154-4998-abe5-074fa1ffd5ed)
![PARTE 021 - VEEAM BACKUP](https://github.com/user-attachments/assets/6d41f498-f495-4552-8e98-68c6895cfc59)
![PARTE 022 - VEEAM BACKUP](https://github.com/user-attachments/assets/986b83b2-9f3e-4846-8c0f-db0bbe6c9bd5)
![PARTE 023 - VEEAM BACKUP](https://github.com/user-attachments/assets/a03c912a-4948-4cda-8c7e-eef207d76474)
![PARTE 024 - VEEAM BACKUP](https://github.com/user-attachments/assets/20a96d8a-227e-40af-8c6e-de0bc8a436ae)
![PARTE 025 - VEEAM BACKUP](https://github.com/user-attachments/assets/b0e81325-a861-4775-90ae-d09a21c0a499)
![PARTE 026 - VEEAM BACKUP](https://github.com/user-attachments/assets/64d1e9c9-06bb-4101-817e-fab9829f4280)
![PARTE 027 - VEEAM BACKUP](https://github.com/user-attachments/assets/00f2170e-d8fb-434e-ae7c-b90b74e03bc6)
![PARTE 028 - VEEAM BACKUP](https://github.com/user-attachments/assets/ed192ec8-4e0e-4b4c-b075-eb8d00bb5215)
![PARTE 029 - VEEAM BACKUP](https://github.com/user-attachments/assets/d0860a0b-5a52-4109-a1f2-f9d9dc3973c4)
![PARTE 030 - VEEAM BACKUP](https://github.com/user-attachments/assets/5da32147-aa20-4cc2-b7f8-1fa8e7d8b6da)
![PARTE 031 - VEEAM BACKUP RESTORE](https://github.com/user-attachments/assets/2cd664e1-e263-4738-a82b-6ab9b611f2f5)
![PARTE 032 - VEEAM BACKUP RESTORE](https://github.com/user-attachments/assets/26e6b472-8d43-4b97-a003-77e3c1f1eced)
![PARTE 033 - VEEAM BACKUP RESTORE](https://github.com/user-attachments/assets/c42deac0-1f5f-4945-aa92-d314737ad679)
![PARTE 034 - VEEAM BACKUP RESTORE](https://github.com/user-attachments/assets/78430f40-9e71-4820-ae5b-c747feb65b55)
![PARTE 035 - VEEAM BACKUP RESTORE](https://github.com/user-attachments/assets/23f1974a-9727-462b-b057-5ec3090cda93)
![PARTE 036 - VEEAM BACKUP RESTORE](https://github.com/user-attachments/assets/8d65df58-87c6-4bd2-b511-2b28583e9767)
![PARTE 037 - VEEAM BACKUP RESTORE](https://github.com/user-attachments/assets/47c86b23-698f-4cb3-b5de-24b80af78de1)
![PARTE 038 - VEEAM BACKUP RESTORE](https://github.com/user-attachments/assets/cc564b8f-dfe9-4f39-8928-2e405aa44a9c)
![PARTE 039 - VEEAM BACKUP RESTORE](https://github.com/user-attachments/assets/da6ace78-c549-48b1-a8f4-eff1587f6ff5)
![PARTE 040 - VEEAM BACKUP RESTORE](https://github.com/user-attachments/assets/63536785-8938-4bff-8be2-f1de9c7322f3)
![PARTE 041 - VEEAM BACKUP RESTORE](https://github.com/user-attachments/assets/d2d215bf-8278-4672-9c1d-df552587a184)
![PARTE 042 - VEEAM BACKUP RESTORE](https://github.com/user-attachments/assets/f743c7d1-7e40-411a-89e7-0d09ccf23681)
![PARTE 043 - VEEAM BACKUP RESTORE](https://github.com/user-attachments/assets/306288a5-50a2-49fc-bdd5-7cb76b5ff63a)
![PARTE 044 - VEEAM BACKUP RESTORE](https://github.com/user-attachments/assets/18d4d6a0-e705-4ab8-920f-003507efe521)
![PARTE 045 - VEEAM BACKUP RESTORE](https://github.com/user-attachments/assets/987b7f87-ccc4-4882-a713-54dc5900b55f)
![PARTE 046 - VEEAM BACKUP RESTORE](https://github.com/user-attachments/assets/8e40c3b0-a976-4e24-bd67-c87c5ea53826)
![PARTE 047 - VEEAM BACKUP RESTORE](https://github.com/user-attachments/assets/d04fc207-b0f6-4075-9cc6-06b1b8345d7c)
![PARTE 048 - SNAPSHOT](https://github.com/user-attachments/assets/e39406c2-25da-4ebc-b4d3-d3716cbe8ac7)
