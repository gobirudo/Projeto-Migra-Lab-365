+ PARTE 002  Expansão do Ambiente e Configuração do File Server

## 1. Configuração do Segundo Controlador de Domínio (ADDS001)

 Implantação de um segundo Domain Controller com Windows Server 2022 para modernização da infraestrutura.
 Promoção do servidor a controlador de domínio e verificação completa da replicação de objetos entre o ADDS000 (Server 2012) e o ADDS001 (Server 2022).
 Criação de usuário de serviço com privilégios de Administrador Global, necessário para configuração do Azure Entra Connect.
 Autenticação no portal Azure e instalação da ferramenta Azure Entra Connect para sincronização de identidades locais com o Entra ID (Azure AD).
 Configuração e monitoramento da replicação do diretório ativo com o Entra ID.
 Validação de logins e autenticação dos usuários sincronizados, garantindo a integridade e funcionamento do ambiente híbrido.

## 2. Criação e Configuração do File Server (FILESERVER01)

 Provisionamento de VM Windows Server 2022 destinada ao serviço de arquivos corporativos.
 Configuração do Storage HP P4000 via Centralized Management Console (CMC), utilizando SSD externo para armazenamento dedicado.
 Criação e alocação de duas LUNs de 50GB cada:
   LUN 1: Volume principal para compartilhamento de arquivos (FileShare).
   LUN 2: Volume reservado para armazenamento de backups futuros.
 Implementação do iSCSI Initiator no FILESERVER01 para conexão e mapeamento das LUNs do storage.
 Configuração do compartilhamento de rede principal: 
    Unidade FILESHARE (Z:)
    📁 OFFICE (Compartilhamento Principal)
    ├── 📁 FINANCE
    ├── 📁 HR
    ├── 📁 IT
    └── 📁 SALES


 Alinhadas às políticas de segurança e grupos de permissões definidos no Active Directory.
 Realização de testes de acesso e validação das permissões aplicadas, assegurando que cada departamento possui o controle correto sobre seus dados.
