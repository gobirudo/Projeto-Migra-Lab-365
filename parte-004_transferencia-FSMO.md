+ PARTE 004 - Transferência de FSMO e Configuração de Redundância no AD

## Transferência das FSMO

- Servidor antigo: ADDS-000 (Windows Server 2012)
- Servidor novo principal: ADDS-001 (Windows Server 2022)

Procedimentos realizados:
- Transferência das 5 funções FSMO (Schema Master, Domain Naming Master, RID Master, PDC Emulator e Infrastructure Master) do ADDS-000 para o ADDS-001.
- Validação da transferência via comandos e ferramentas nativas do AD (ex: `netdom query fsmo`).
- Testes de replicação entre controladores para garantir integridade e sincronização correta.

## Despromoção do ADDS-000

- Remoção do AD do servidor ADDS-000 com a despromoção completa do Domain Controller.
- Reinício do servidor e verificação da remoção completa do serviço de AD.
- Snapshots tirados antes e depois da operação para segurança.
- Testes de replicação de novos usuarios pós migração

## Implementação da Redundância com Novo Domain Controller

- Subida de um novo servidor: ADDS-002 (Windows Server 2022)
- Promoção do ADDS-002 como Domain Controller adicional no domínio existente.
- Sincronização completa da replicação com o ADDS-001.
- Configuração final do ambiente com:
  - ADDS-001 como Domain Controller principal e FSMO holder.
  - ADDS-002 como controlador secundário para redundância.

---

Status final: Ambiente AD atualizado, redundante, com servidores modernos e replicação estável para suportar demandas atuais e futuras.
