---
apple-notes-id: fb3d6656-1b4b-4dca-915e-af02b279cfac
---
#topicos_avancados

O principal objetivo do Haddop YARN foi dividir as funcionalidades de gerenciamento de recursos e agendamento/monitoramento de tarefas em daemons separados.

O ResouceManager é a autoridade máxima que arbitra os recursos entre todas as aplicações do sistema e possui dois componentes principais: Scheduler e ApplicationsManager

O Scheduler é responsável por alocar recursos para as aplicações em execução e são sujeitos a restrições de capacidade de recursos, filas etc.

O Scheduler é um scheduler puro no sentido de que não realiza nenhuma ação de monitoramento ou tracking de status para o aplicativo.

O ApplicationManager é o responsável por aceitar envios de jobs, negociar o primeiro contêiner para executar a instância ApplicationMaster para a aplicação e forner o serviço para reiniciar o contêiner ApplicationMaster em caso de falha.

No ecossistema **Apache Haddop**, as tabelas HBase são distribuídas no cluster por meio de regiões, as quais são automaticamente divididas  e redistribuídas à medida que seus dados crescem.
"It is used to scale a single Apache Haddop cluster to hundreds of nodes. HDFS is one of the major components of Apache Hadoop, the others being MapReduce and YARN. **HDFS shoud not be confused with or replaced by Apache HBase,** which is a coumn-orinted non-relational database managment system that sits on top of HDFS and can better support real-time data needs with ists in-memory processing engine."

 Ao serem armazenados no HDFS(Hadoop Distributed File System), os dados do Hadoop são dividos em blocos e ~~distribuidos em discos distintos de um mesmo servidor~~(máquinas distintas), que acelera o seu processamento, já que são pesquisados de forma simultânea, e não de forma sequencial.