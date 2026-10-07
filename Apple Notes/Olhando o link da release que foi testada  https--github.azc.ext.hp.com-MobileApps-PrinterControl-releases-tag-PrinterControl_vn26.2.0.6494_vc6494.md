---
apple-notes-id: C29EFC29-9A8B-4781-BD44-44940210E56E
---
Ele foi liberado no dia 06 de maio, olhando no link de mfe de AA no dia 06, https://github.azc.ext.hp.com/HPX-Core-Experiences/aa-mfe-prod-list/blob/f8f1366d9657f366e157884ce662e09da3419a91/26.2/Stage/README.md, o mfe de devices se encontra na versão 3.27.8,

Entretanto houve uma correção na versão 4.3.1 deste mfe(devices-me) PR https://github.azc.ext.hp.com/HPX-Core-Experiences/react-devices-mfe/pull/421

Olhando para o repositório de versões AA notamos que a correção não foi integrada pois a versão corrida é a 4.3.1 e a ultima versão integrada é a 3.27.8-patch-1
https://github.azc.ext.hp.com/HPX-Core-Experiences/aa-mfe-prod-list/blob/main/26.2/Stage/README.md


![[Pasted Graphic 37.png]]

 
É necessário esperar para que a correção seja integrada ao build de AA. Por isso a atividade está bloqueada.
Condições de desbloqueio:
1. visitar o link: https://github.azc.ext.hp.com/HPX-Core-Experiences/aa-mfe-prod-list/blob/main/26.2/Stage/README.md
2. Verificar se a versão @hpx-core-experiences/react-devices-mfe >= 4.3.1