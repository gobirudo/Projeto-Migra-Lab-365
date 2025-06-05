🚀 PARTE 003: Migração do File Server para SharePoint e Integração com Teams
🎯 Objetivo
Modernizar a gestão de arquivos migrando do File Server local para o SharePoint Online, além de estruturar a comunicação interna via Microsoft Teams, simulando um ambiente corporativo realista.

🛠️ Passos realizados
1. Planejamento da migração

Avaliação da estrutura atual de arquivos e permissões no File Server (unidade Z:).

População inicial do File Server com subpastas e arquivos para simular ambiente realista e validar a migração.

Mapeamento das pastas e grupos de segurança para manter hierarquia e permissões no SharePoint.

2. Criação do site SharePoint

Configuração do site de equipe no SharePoint Online, com estrutura de bibliotecas e pastas refletindo a organização do File Server.

3. Utilização do SharePoint Migration Tool

Download e instalação da ferramenta oficial da Microsoft para migração (SharePoint Migration Tool).

Configuração do perfil de migração apontando para a unidade Z: do File Server.

Migração dos arquivos mantendo estrutura e permissões correspondentes.

4. Atualização da estrutura organizacional no Active Directory

Configuração da hierarquia entre usuários: cada usuário tem gerente definido, e o gerente reporta ao BIG BOSS.

Estrutura pensada para simular a árvore organizacional exibida no Microsoft Teams, facilitando a visualização das relações de reporte.

5. Configuração e testes no Microsoft Teams

Criação de equipes e canais no Teams baseados nos departamentos criados no AD.

Realização de testes práticos de comunicação, incluindo chats e reuniões, simulando fluxo de trabalho real.

6. Validação pós-migração e integração

Testes de acesso e colaboração entre usuários nos ambientes SharePoint e Teams para garantir funcionamento integrado e eficiente.

Ajustes finos nas permissões e na hierarquia organizacional conforme feedback dos testes.




***************************

 PRINTS

**************************



- Realizado a criação de algumas pastas e adição de alguns arquivos...

- Foi utilizado o seguinte comando:

# Comando

mkdir "Z:\OFFICE\HR - HUMAN RESOURCES"

for ($i=1; $i -le 5; $i++) {
    fsutil file createnew "Z:\OFFICE\HR - HUMAN RESOURCES\hr-file-$i.txt" 104857600
}


- Deve-se alterar a unidade, e o nome das pastas...e o tamanho se preferir

- O comando cria 5 arquivos de 100MB cada, numerados de arquivo_1.txt até arquivo_5.txt

- Foi realizado o mesmo procedimento para todas as demais pastas...

![023 -FILESERVER - PARTE 04](https://github.com/user-attachments/assets/c17526e2-4771-42d2-b16f-4fab74dd32a1)

![024 -FILESERVER - PARTE 05](https://github.com/user-attachments/assets/1c0935d0-b6a6-43a4-adc1-101e6d6f7fdd)

![025 -FILESERVER - PARTE 06](https://github.com/user-attachments/assets/83a8c5a1-1ba1-4a29-ac6c-acd4c659b64d)



.

.

.

- LInk utilizado para download da ferramenta de migração para o Sharepoint : https://learn.microsoft.com/en-us/sharepointmigration/how-to-use-the-sharepoint-migration-tool



![001 -SHAREPOINT - PARTE 01](https://github.com/user-attachments/assets/980c6763-1d97-4595-aece-f5f8fb3c5c11)



- Execute o programa : SharePoint Migration Tool

![009 -SHAREPOINT](https://github.com/user-attachments/assets/c7bf83c7-4731-4172-9470-bea6eaa68f89)



- Será necessário logar com alguma credencial com permissões para rodar a migração

![010 -SHAREPOINT ](https://github.com/user-attachments/assets/fb3ab186-704b-4f26-8054-d3de90d1d526)



- Selecione o campo File Share

![011 -SHAREPOINT](https://github.com/user-attachments/assets/914a2716-9f3f-437e-8797-f782917733de)



- Segue o passo

![012 -SHAREPOINT](https://github.com/user-attachments/assets/b3ad4096-1c94-4299-8381-75e47528cb45)



- Adicione o endereço da pasta ou clique em choose folder (manualmente)

![013 -SHAREPOINT](https://github.com/user-attachments/assets/09e014a5-b3f0-48c3-98da-b13495305a4f)



- Selecione o destino

![014 -SHAREPOINT](https://github.com/user-attachments/assets/78be6a9f-50eb-4a98-98ae-60fed539f75b)



- Ele vai preencher o nome do site que será criado lá no Shaprepoint, pode ser mudado, assim como fiz

![015 -SHAREPOINT](https://github.com/user-attachments/assets/ff180e34-4fcc-49fe-980f-b3b763f3498a)



- Mantive a pasta Documents como local para migrar os dados.

![016 -SHAREPOINT](https://github.com/user-attachments/assets/9489e694-bc3a-4e86-ac70-a5ff5486aaa1)



- Um breve resumo.

![017 -SHAREPOINT](https://github.com/user-attachments/assets/beeabb00-ad7e-498d-afde-11ba2977f49c)



- Preferi levar as permissões para já migrar junto com os dados

![018 -SHAREPOINT](https://github.com/user-attachments/assets/6e7ed0c6-0cc9-41a6-8d85-a5e51bd9edcf)



- Migração concluída.

![019 -SHAREPOINT](https://github.com/user-attachments/assets/1a15393b-9af3-47be-bd43-4748493aa1b9)



- Só acessar o Sharepoint, e clicar no site, e verá os dados migrados.

![020 -SHAREPOINT](https://github.com/user-attachments/assets/7fd96fae-a23b-4cc3-b4d1-130ab6423f8b)

![021 -SHAREPOINT](https://github.com/user-attachments/assets/24a7ac36-4a3a-4b1a-aae1-43a08980e07d)

![022 -SHAREPOINT](https://github.com/user-attachments/assets/c40cb044-4447-475a-859c-c8ef48456f91)

![023 -SHAREPOINT](https://github.com/user-attachments/assets/578a478f-4a83-46a6-8366-6471fcefe3fa)

![024 -SHAREPOINT](https://github.com/user-attachments/assets/27f1806f-b6b5-47f6-8132-86262e6225a8)

