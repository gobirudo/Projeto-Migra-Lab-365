+ PARTE 003: Migração do File Server para o SharePoint e Integração com Teams

! Objetivo  
Modernizar a gestão dos arquivos migrando do File Server local para o SharePoint Online, além de estruturar a comunicação interna via Microsoft Teams simulando um ambiente corporativo realista.

### Passos realizados

1. Planejamento da migração  
   - Avaliação da estrutura atual de arquivos e permissões no File Server (unidade `Z:`).  
   - Pequena população do File Server com subpastas e arquivos para simular um ambiente realista e validar a migração.  
   - Mapeamento das pastas e grupos de segurança para manter a hierarquia e as permissões no SharePoint.

2. Criação do site SharePoint  
   - Configuração do site de equipe no SharePoint Online, com estrutura de bibliotecas e pastas que refletem a organização do File Server.

3. Utilização do SharePoint Migration Tool  
   - Download e instalação da ferramenta oficial da Microsoft para migração (SharePoint Migration Tool).  
   - Configuração do perfil de migração apontando para a unidade `Z:` do File Server.  
   - Migração dos arquivos mantendo a estrutura e as permissões correspondentes.

4. Atualização da estrutura organizacional no Active Directory  
   - Configuração de relações de hierarquia entre usuários: cada usuário tem seu gerente (`manager`) definido e o gerente reporta ao `BIG BOSS`.  
   - Essa estrutura foi pensada para simular a árvore organizacional exibida no Microsoft Teams, facilitando a visualização de quem é quem e as relações de reporte.

5. Configuração e testes no Microsoft Teams  
   - Criação de equipes e canais no Teams baseados nos departamentos criados no AD.  
   - Realização de testes práticos de comunicação, incluindo chats e reuniões via Microsoft Teams, simulando o fluxo de trabalho e comunicação em uma empresa real.

6. Validação pós-migração e integração  
   - Testes de acesso e colaboração entre usuários nos ambientes SharePoint e Teams para garantir funcionamento integrado e eficiente.  
   - Ajustes finos nas permissões e na hierarquia organizacional conforme feedback dos testes.
