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

- Abaixo segue as etapas utilizadas para configuração dos backups.
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

- Abaxo as etapas para fazer o restore das VMS, para testar se os backups estão integros, pois será realizado as transferencias das FSMO's.
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

- Nesta etapa, suspendi a VM ADDS-000 para não implicar na VM restaurada, e foi realizado os testes de criação de user e replicação feita com sucesso com o outro ADDS-001.
![PARTE 045 - VEEAM BACKUP RESTORE](https://github.com/user-attachments/assets/987b7f87-ccc4-4882-a713-54dc5900b55f)
![PARTE 046 - VEEAM BACKUP RESTORE](https://github.com/user-attachments/assets/8e40c3b0-a976-4e24-bd67-c87c5ea53826)
![PARTE 047 - VEEAM BACKUP RESTORE](https://github.com/user-attachments/assets/d04fc207-b0f6-4075-9cc6-06b1b8345d7c)

- Fiz um Snapshot para + garantia de restore rápido.
![PARTE 048 - SNAPSHOT](https://github.com/user-attachments/assets/e39406c2-25da-4ebc-b4d3-d3716cbe8ac7)

 *****************************
             PRINTS - TRANSF. FSMO e Despromoção do Controlador de domínio antigo (ADDS-000)
 ******************************

 - Realizado a pausa do serviço de sincronização do Entra-ID:
 - COMANDO : Get-ADSyncScheduler (para checar o serviço)
 - COMANDO : Set-ADSyncScheduler -SyncCycleEnabled $false (para parar o serviço)

![PARTE 049 - FSMO](https://github.com/user-attachments/assets/a1f2b5d2-7101-403c-90cf-0756be91b68b)
![PARTE 050 - FSMO](https://github.com/user-attachments/assets/b9844dac-1203-48cf-a9e3-66666e6bb543)
![PARTE 051 - FSMO](https://github.com/user-attachments/assets/946253a8-2af4-43c3-8abd-5373f68431ef)
![PARTE 052 - FSMO](https://github.com/user-attachments/assets/2c0f5b66-f94a-4669-9f23-1fd2f51511eb)
![PARTE 053 - FSMO](https://github.com/user-attachments/assets/15f233b8-2c86-4875-84a2-bb29b59867cd)
![PARTE 054 - FSMO](https://github.com/user-attachments/assets/c7e41b9b-2b2e-4236-8bed-44a6a6c710c2)
![PARTE 055 - FSMO](https://github.com/user-attachments/assets/6955537f-ffa5-43ae-9992-d72fcfc164dc)
![PARTE 056 - FSMO](https://github.com/user-attachments/assets/c8b5d153-e954-4a53-8fac-125b3b958149)
![PARTE 057 - FSMO](https://github.com/user-attachments/assets/7e319387-5659-438e-81b7-6d0ffa8a5f1f)
![PARTE 058 - FSMO](https://github.com/user-attachments/assets/8bcf9540-b3c2-46cf-9fbc-50464a5ce1ef)
![PARTE 059 - FSMO](https://github.com/user-attachments/assets/4fe7c85f-3483-4650-9457-a4fb3d661a34)
![PARTE 060 - FSMO](https://github.com/user-attachments/assets/d28b9175-ec8f-4ba6-93c7-abdb01882488)
![PARTE 061 - ENTRA CONNECT START](https://github.com/user-attachments/assets/c58db942-67c4-45f0-9efe-2efcbee92b84)
![PARTE 062 - ENTRA CONNECT DELTA](https://github.com/user-attachments/assets/2db06544-7327-417a-acc8-c761ff6482cc)
![PARTE 063 - ENTRA CONNECT DELTA](https://github.com/user-attachments/assets/9cb5e49e-97d8-44e5-8e3e-d5d839f62834)
![PARTE 064 - ENTRA CONNECT DELTA](https://github.com/user-attachments/assets/6397f360-18ce-4fe8-b552-8fdc7ec15689)
![PARTE 065 - ENTRA CONNECT DELTA](https://github.com/user-attachments/assets/16ed352e-f432-4412-a6c1-f3f17eda3867)
![PARTE 066 - ENTRA CONNECT DELTA](https://github.com/user-attachments/assets/1896557a-a2e5-49bb-af6c-fb7c51c35e83)
![PARTE 067 - ENTRA CONNECT DELTA](https://github.com/user-attachments/assets/80c7d7de-3bff-4fb9-9ad4-7b8e0da879a8)
![PARTE 068 - DEMOTE](https://github.com/user-attachments/assets/0c98c274-75b8-4f4a-ac11-57c2cd85a3ab)
![PARTE 069 - DEMOTE](https://github.com/user-attachments/assets/27a83aa0-b107-4818-b2aa-a54a0ac0b4f4)
![PARTE 070 - DEMOTE](https://github.com/user-attachments/assets/bbfa0c7e-12de-4654-8f67-5c937f26b020)
![PARTE 071 - DEMOTE](https://github.com/user-attachments/assets/cefd5557-c967-4702-a2d7-2ca2f872cfb8)
![PARTE 072 - DEMOTE](https://github.com/user-attachments/assets/594b84f5-7969-4301-a664-c54957b36f4f)
![PARTE 073 - DEMOTE](https://github.com/user-attachments/assets/57442e3a-ddfc-4ea1-839b-5fa59821bc6d)
![PARTE 074 - DEMOTE](https://github.com/user-attachments/assets/edb48036-f87a-4de1-977b-c330c656e1fa)
![PARTE 075 - DEMOTE](https://github.com/user-attachments/assets/2cc64502-c5ea-4677-8fd6-9c1db37d770f)
![PARTE 076 - DEMOTE](https://github.com/user-attachments/assets/548b1630-15de-47a1-9b3b-29d14b0839cc)
![PARTE 077 - DEMOTE](https://github.com/user-attachments/assets/e4ee580c-404b-4a97-b805-90b50e675cb0)
![PARTE 078 - DEMOTE](https://github.com/user-attachments/assets/3bcf9838-37bc-491d-9d60-ae7c710fe495)









