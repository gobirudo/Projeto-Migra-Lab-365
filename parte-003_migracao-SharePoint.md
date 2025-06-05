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


***************************
📸 PRINTS - MIGRAÇÃO
***************************

🗂️ Populando o File Server com arquivos de teste

Realizado a criação de algumas pastas e adição de arquivos para simular uso real.

Foi utilizado o seguinte comando PowerShell:

powershell
mkdir Z:\OFFICE\HR - HUMAN RESOURCES
for ($i=1; $i -le 5; $i++) {
    fsutil file createnew "Z:\OFFICE\HR - HUMAN RESOURCES\hr-file-$i.txt" 104857600
}

- Esse comando cria 5 arquivos de 100MB cada. A unidade, nomes de pasta e tamanhos podem ser ajustados conforme o cenário.
![023 -FILESERVER - PARTE 04](https://github.com/user-attachments/assets/c17526e2-4771-42d2-b16f-4fab74dd32a1)

![024 -FILESERVER - PARTE 05](https://github.com/user-attachments/assets/1c0935d0-b6a6-43a4-adc1-101e6d6f7fdd)

![025 -FILESERVER - PARTE 06](https://github.com/user-attachments/assets/83a8c5a1-1ba1-4a29-ac6c-acd4c659b64d)

<br>
<br>


🔽 Download da ferramenta de migração
Link oficial utilizado para download da SharePoint Migration Tool:
https://learn.microsoft.com/en-us/sharepointmigration/how-to-use-the-sharepoint-migration-tool

🚀 Iniciando a SharePoint Migration Tool
Execute o programa SharePoint Migration Tool:

Será necessário logar com uma conta que tenha permissões adequadas para realizar a migração:

📁 Selecionando a origem e destino da migração
Selecione a opção File Share como origem:

Avance para o próximo passo:

Adicione o caminho da pasta de origem ou clique em "Choose folder" para selecionar manualmente:

Defina o destino da migração no SharePoint:

Nome do site será sugerido automaticamente, mas pode ser editado:

Mantive a pasta "Downloads" como local temporário dos dados durante a migração:

✅ Revisão e conclusão da migração
Resumo geral da tarefa de migração:

As permissões originais foram levadas junto com os arquivos:

Migração concluída com sucesso:

🔎 Verificando os arquivos no SharePoint
Acesse o site SharePoint correspondente e visualize os arquivos migrados:
