+ 📍 PARTE 001 : Simulação de Ambiente Obsoleto com Active Directory

! 🎯 Objetivo
Simular um ambiente legado com Active Directory rodando em Windows Server 2012, com estrutura organizacional e de segurança montada, para posterior otimização, modernização e migração para versão mais recente.

---

 🧱 Servidor AD Inicial

- Nome da VM `ADDS-000`
- Sistema Operacional Windows Server 2012
- Função Controlador de domínio inicial e legado
- Finalidade Base para criação do domínio e estrutura de OU. Posteriormente será despromovido após migração.

---

 🗂️ Estrutura de OUs Criadas

📁 OFFICE
├── 📁 FINANCE
│   ├── 👤 FINANCE.USER.001
│   ├── 👤 FINANCE.MANAGER.001
│   ├── 👥 GR_FINANCE_USERS
│   └── 👥 GR_FINANCE_MANAGERS
├── 📁 HR - HUMAN RESOURCES
│   ├── 👤 HR.USER.001
│   ├── 👤 HR.MANAGER.001
│   ├── 👥 GR_HR_USERS
│   └── 👥 GR_HR_MANAGERS
├── 📁 IT - TECHNOLOGY
│   ├── 👤 IT.USER.001
│   ├── 👤 IT.MANAGER.001
│   ├── 👥 GR_IT_USERS
│   └── 👥 GR_IT_MANAGERS
├── 📁 SALES
│   ├── 👤 SALES.USER.001
│   ├── 👤 SALES.MANAGER.001
│   ├── 👥 GR_SALES_USERS
│   └── 👥 GR_SALES_MANAGERS
├── 📁 CEO
│   └── 👤 BIG.BOSS

📁 SECURITY GROUPS
├── 🔒 GR_DATA_FINANCE_READ
├── 🔒 GR_DATA_FINANCE_WRITE
├── 🔒 GR_DATA_HR_READ
├── 🔒 GR_DATA_HR_WRITE
├── 🔒 GR_DATA_IT_READ
├── 🔒 GR_DATA_IT_WRITE
├── 🔒 GR_DATA_SALES_READ
├── 🔒 GR_DATA_SALES_WRITE
└── 🧾 GR_M365_LICENCES

✅ Ícones pra facilitar:

📁 = OU (Organizational Unit)
👤 = Usuário
👥 = Grupo de distribuição/local
🔒 = Grupo de segurança
🧾 = Grupo de licenciamento


---

 👥 Organização de Grupos e Permissões

- Cada grupo `GR_SETOR_USERS` e `GR_SETOR_MANAGERS` possui os usuários respectivos como membros.
- Os grupos de segurança `GR_DATA_<SETOR>_READ/WRITE` controlam o acesso futuro ao File Server e SharePoint.
- O grupo `GR_M365_LICENCES` será utilizado para atribuição de licenças do Microsoft 365 (plano E5 na simulação).

---

 🧬 Próximo Passo: Controlador Moderno (Preparação para Migração)

- Nome da VM `ADDS-001`
- Sistema Operacional Windows Server 2022
- Objetivo 
  - Ser promovido a Domain Controller adicional
  - Receber as FSMO roles do servidor legado
  - Atuar como DC principal após despromoção do `ADDS-000`
  - Ter instalado o Microsoft Entra Connect para sincronização com o Entra ID (Azure AD)

---

📌 *Esse primeiro estágio simula empresas que ainda operam com servidores antigos e enfrentam o desafio de atualizar sua infraestrutura sem causar impacto no ambiente de produção.*
