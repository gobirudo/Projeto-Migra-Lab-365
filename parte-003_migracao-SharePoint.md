+ PARTE 003: Migração do File Server para o SharePoint e Integração com Teams

Modernização da Gestão de Arquivos: Migração para SharePoint Online e Integração com Microsoft Teams
Objetivo
O principal objetivo deste projeto foi modernizar a gestão de arquivos migrando-os do File Server local (Z:) para o SharePoint Online. Além disso, visamos estruturar a comunicação interna por meio do Microsoft Teams, simulando um ambiente corporativo realista e otimizando a colaboração e o fluxo de trabalho.

Passos Realizados
Planejamento da Migração

Foi realizada uma avaliação detalhada da estrutura atual de arquivos e permissões no File Server (unidade Z:).
Para simular um ambiente realista e validar o processo de migração, o File Server foi populado com subpastas e arquivos de exemplo.
Um mapeamento cuidadoso das pastas e grupos de segurança foi feito para garantir a manutenção da hierarquia e das permissões no SharePoint.
Criação do Site SharePoint

Um site de equipe foi configurado no SharePoint Online, com uma estrutura de bibliotecas e pastas que espelham a organização existente no File Server.
Utilização do SharePoint Migration Tool (SPMT)

A ferramenta oficial da Microsoft para migração (SharePoint Migration Tool) foi baixada e instalada.
O perfil de migração foi configurado, apontando para a unidade Z: do File Server como origem.
A migração dos arquivos foi executada, mantendo a estrutura original e as permissões correspondentes.
Atualização da Estrutura Organizacional no Active Directory

Foram configuradas as relações de hierarquia entre os usuários: cada usuário teve seu gerente (manager) definido, e os gerentes reportam ao BIG BOSS.
Esta estrutura foi criada para simular a árvore organizacional exibida no Microsoft Teams, facilitando a visualização das relações de reporte na empresa.
Configuração e Testes no Microsoft Teams

Equipes e canais foram criados no Teams, baseando-se nos departamentos estabelecidos no Active Directory.
Testes práticos de comunicação foram realizados, incluindo chats e reuniões via Microsoft Teams, simulando o fluxo de trabalho e a comunicação em uma empresa real.
Validação Pós-Migração e Integração

Testes de acesso e colaboração entre usuários nos ambientes SharePoint e Teams foram executados para garantir um funcionamento integrado e eficiente.
Ajustes finos nas permissões e na hierarquia organizacional foram aplicados com base no feedback dos testes.
Demonstração e Evidências
Para simular o ambiente de arquivos, foram criadas algumas pastas e adicionados arquivos, usando o seguinte comando PowerShell:

mkdir Z:\OFFICE\HR - HUMAN RESOURCES
for ($i=1; $i -le 5; $i++) {
    fsutil file createnew "Z:\OFFICE\HR - HUMAN RESOURCES\hr-file-$i.txt" 104857600
}

Observação: Você deve alterar a unidade, o nome das pastas e, se preferir, o tamanho dos arquivos. Este comando cria 5 arquivos de 100MB cada, numerados de hr-file-1.txt a hr-file-5.txt. O mesmo procedimento foi repetido para as demais pastas.
Capturas de Tela do File Server Pre-Migração:

Processo de Migração com SharePoint Migration Tool
A ferramenta oficial da Microsoft para migração, a SharePoint Migration Tool (SPMT), foi utilizada.

Link para Download da Ferramenta: SharePoint Migration Tool
Passos e Capturas de Tela da Migração:

Execução da Ferramenta:

Login com Credenciais (com permissões de migração):

Seleção da Origem (File Share):

Adição do Caminho da Pasta de Origem (ou seleção manual):

Seleção do Destino no SharePoint:

Preenchimento do Nome do Site no SharePoint (com possibilidade de alteração):

Confirmação do Local de Migração dos Dados (mantido como "downloads" para este exemplo):

Resumo da Configuração de Migração:

Configuração de Permissões (opção para migrar junto com os dados selecionada):

Migração Concluída:

Validação Pós-Migração no SharePoint
Após a conclusão da migração, os dados estão acessíveis no site do SharePoint, refletindo a estrutura e os arquivos migrados.

Capturas de Tela dos Dados Migrados no SharePoint:

Graças a este compromisso coletivo, este projeto reuniu muitos visitantes vindos de outros bairros, reforçando assim a visibilidade dos artistas e o orgulho local. Em conclusão, este projeto demonstra que a expressão artística pode desempenhar um papel fundamental na dinamização das comunidades.

Espero que esta organização ajude a melhorar a apresentação do seu projeto no GitHub! Se precisar de mais ajustes ou detalhes, é só avisar!



