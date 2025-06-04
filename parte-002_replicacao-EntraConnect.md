+ 📍 PARTE 002  Expansão do Ambiente e Configuração do File Server

## 1. Configuração do Segundo Controlador de Domínio (ADDS-001)

 - Implantação de um segundo Domain Controller com Windows Server 2022 para modernização da infraestrutura.
 - Promoção do servidor a controlador de domínio e verificação completa da replicação de objetos entre o ADDS000 (Server 2012) e o ADDS001 (Server 2022).
 - Criação de usuário de serviço com privilégios de Administrador Global, necessário para configuração do Azure Entra Connect.
 - Autenticação no portal Azure e instalação da ferramenta Azure Entra Connect para sincronização de identidades locais com o Entra ID (Azure AD).
 - Configuração e monitoramento da replicação do diretório ativo com o Entra ID.
 - Validação de logins e autenticação dos usuários sincronizados, garantindo a integridade e funcionamento do ambiente híbrido.

## 2. Criação e Configuração do File Server (FILESERVER)

- Provisionamento de VM Windows Server 2022 destinada ao serviço de arquivos corporativos.
- Configuração do Storage HP P4000 via Centralized Management Console (CMC), utilizando SSD externo para armazenamento dedicado.
- Criação e alocação de duas LUNs de 50GB cada:
   LUN 1: Volume principal para compartilhamento de arquivos (FileShare).
   LUN 2: Volume reservado para armazenamento de backups futuros.
- Implementação do iSCSI Initiator no FILESERVER01 para conexão e mapeamento das LUNs do storage.
- Configuração do compartilhamento de rede principal: 
    Unidade FILESHARE (Z:)
- 📁 OFFICE (Compartilhamento Principal)
  - 📁 FINANCE
  - 📁 HR
  - 📁 IT
  - 📁 SALES


 Alinhadas às políticas de segurança e grupos de permissões definidos no Active Directory.
 Realização de testes de acesso e validação das permissões aplicadas, assegurando que cada departamento possui o controle correto sobre seus dados.

 

![001 - WIN SRV 2022 - ADDS-001](https://github.com/user-attachments/assets/e63152ee-ab2e-4e13-8ffe-c0ba05df91a1)
![002 - PROMOÇAO A DOMAIN CONTROLLER](https://github.com/user-attachments/assets/b7269322-cfd5-4071-ac16-4e163b5cd825)
![003 - DOMAIN CONTROLERS](https://github.com/user-attachments/assets/b9e04339-34e4-4292-aeb6-51b2a17f9e99)
![004 - USER SVC GLOBAL ADMIN](https://github.com/user-attachments/assets/ef8e88e1-d613-4602-a34e-d4645c7c8c94)
![005 - ENTRA CONNECT PART 001](https://github.com/user-attachments/assets/8f166f9c-7cad-43a3-ab65-aed9f399f0ba)
![006 - ENTRA CONNECT PART 002](https://github.com/user-attachments/assets/1d343ed8-01d8-4d56-a501-d3dda21a5fb9)
![007 - ENTRA CONNECT](https://github.com/user-attachments/assets/cc3f25fd-8106-48ae-a046-505d9d12428f)
![008 - USERS REPLICADOS](https://github.com/user-attachments/assets/424a0d49-d7b3-4d9e-b641-06d091392a11)
![009 - GRUPOS REPLICADOS](https://github.com/user-attachments/assets/c3e069d2-6de5-44d5-ae97-b2a7ff3a3603)
![010 - LICENÇA GRUP - PARTE 01](https://github.com/user-attachments/assets/a6867185-cc5e-482d-95cb-914952c65408)
![011 - LICENÇA GRUP - PARTE 02](https://github.com/user-attachments/assets/78b10c9e-d4cc-47be-802d-f30ad3c22a23)
![012 - LICENÇA GRUP - PARTE 03](https://github.com/user-attachments/assets/5bec9e05-aa50-4672-990d-5665ac3f9230)
![013 - LICENÇA GRUP - PARTE 04](https://github.com/user-attachments/assets/1f6b5745-412f-4797-a887-55c2f26cd403)
![014 - LICENÇA GRUP - PARTE 05](https://github.com/user-attachments/assets/ae78ad6b-5676-48f6-89e6-f60515a60d18)
![015 - LICENÇA GRUP - PARTE 06](https://github.com/user-attachments/assets/5471c8cd-60bd-4938-bd45-4217b71d8544)















