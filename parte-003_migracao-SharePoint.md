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
 PRINTS
**************************

- Realizado a criação de algmas pastas e adição de alguns arquivos...
- Foi utilizado o seguinte comando:
- mkdir Z:\OFFICE\HR - HUMAN RESOURCES
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

![00 -SHAREPOINT - PARTE 05](https://github.com/user-attachments/assets/4dd39044-8e0c-4159-8b01-6ae2e123fcb3)
![001 -SHAREPOINT - PARTE 01](https://github.com/user-attachments/assets/980c6763-1d97-4595-aece-f5f8fb3c5c11)
![002 -SHAREPOINT - PARTE 02](https://github.com/user-attachments/assets/71196bcf-236d-4d42-8d9f-09594c0f87c8)
![003 -SHAREPOINT - PARTE 03](https://github.com/user-attachments/assets/22dfe561-76ad-4ee4-8a7c-54c638d58025)
![004 -SHAREPOINT - PARTE 04](https://github.com/user-attachments/assets/9e4963dc-93d6-482a-8144-af8f4ce4590b)
![005 -SHAREPOINT - PARTE 05](https://github.com/user-attachments/assets/7d5ba040-766f-4319-a685-273884519109)
![006 -SHAREPOINT](https://github.com/user-attachments/assets/686062a2-0712-4c7b-969b-5ebbacc3e622)
![007 -SHAREPOINT](https://github.com/user-attachments/assets/e7626a3b-dbf8-41fe-85ab-8b26167c48e1)
![008 -SHAREPOINT](https://github.com/user-attachments/assets/68dab5b7-327e-4b3c-9b15-223a23472e6f)
![009 -SHAREPOINT](https://github.com/user-attachments/assets/c7bf83c7-4731-4172-9470-bea6eaa68f89)
![010 -SHAREPOINT ](https://github.com/user-attachments/assets/fb3ab186-704b-4f26-8054-d3de90d1d526)
![011 -SHAREPOINT](https://github.com/user-attachments/assets/914a2716-9f3f-437e-8797-f782917733de)
![012 -SHAREPOINT](https://github.com/user-attachments/assets/b3ad4096-1c94-4299-8381-75e47528cb45)
![013 -SHAREPOINT](https://github.com/user-attachments/assets/09e014a5-b3f0-48c3-98da-b13495305a4f)
![014 -SHAREPOINT](https://github.com/user-attachments/assets/78be6a9f-50eb-4a98-98ae-60fed539f75b)
![015 -SHAREPOINT](https://github.com/user-attachments/assets/ff180e34-4fcc-49fe-980f-b3b763f3498a)
![016 -SHAREPOINT](https://github.com/user-attachments/assets/9489e694-bc3a-4e86-ac70-a5ff5486aaa1)
![017 -SHAREPOINT](https://github.com/user-attachments/assets/beeabb00-ad7e-498d-afde-11ba2977f49c)
![018 -SHAREPOINT](https://github.com/user-attachments/assets/6e7ed0c6-0cc9-41a6-8d85-a5e51bd9edcf)
![019 -SHAREPOINT](https://github.com/user-attachments/assets/1a15393b-9af3-47be-bd43-4748493aa1b9)
![020 -SHAREPOINT](https://github.com/user-attachments/assets/7fd96fae-a23b-4cc3-b4d1-130ab6423f8b)
![021 -SHAREPOINT](https://github.com/user-attachments/assets/24a7ac36-4a3a-4b1a-aae1-43a08980e07d)
![022 -SHAREPOINT](https://github.com/user-attachments/assets/c40cb044-4447-475a-859c-c8ef48456f91)
![023 -SHAREPOINT](https://github.com/user-attachments/assets/578a478f-4a83-46a6-8366-6471fcefe3fa)
![024 -SHAREPOINT](https://github.com/user-attachments/assets/27f1806f-b6b5-47f6-8132-86262e6225a8)





