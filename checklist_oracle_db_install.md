## :notebook_with_decorative_cover: Checklist - Criação e configuração do laboratório de estudo:
1. Criação da VM na Oracle Virtual Box:
    - Configuração utilizada: 2 CPUs, 4 MB de RAM, 60 GB de Armazenamento.
2. Conexão na VM via protocolo SSH (usando o terminal do Linux da minha máquina pessoal);
3. Adicionar o hostname da VM ao arquivo "/etc/hosts":
	- Hostname: ol7-dba.localdomain;
	- Apelido: ol7-dba.
4. Configuração prévias à instação do Oracle Database (ajustes no kernel, grupo de usuário, download dos pacotes necessários e criação do usuário "oracle") feito por meio do pacote de instalação fornecido pela oracle "oracle-database-preinstall-19c";
5. Arquivo de instalação do Oracle Database transferido do meu computador pessoal para a VM por meio do protocólo SFTP (usando o terminal Linux)
6. Configurando o IP da VM para torná-lo estático no arquivo "/etc/sysconfig/network-scripts/ifcfg-enp0s3":
	- BOOTPROTO: "static";
	- Adição da linha "IPADDR";
	- IPADDR: IP da VM.
7. Segurança e Firewall da VM desabilitados(arquivo "/etc/selinux/config" editado, e firewalld desabilitado);
8. Criação do diretório onde ficarão os binários do oracle;
9. Permissões associadas aos diretórios passadas para o usuário "oracle" e o grupo de usuários "oinstall";
10. Instalação do X11 na VM para poder usar dos recursos gráficos na instalação do Oracle Database;
11. Instalação do Oracle Database;
12. Variável de ambiente setada para reconhecer o binário do SQL*Plus (". oraenv" -> [nome do banco]);
13. Teste feito no SQL*Plus para afirmar a funcionalidade do banco;
14. Configuração do usuário "HR" para o uso do PDB "human_resources" (unlock + script de configuração)
15. Configuração do hostname no listener e no tnsnames (arquivos "listener.ora" e "tnsnames.ora", respectivamente), alteração do listener local no SQL*Plus e listener resetado;
16. Teste feito no schema "human_resources", conectando-se com o usuário "HR" e fazendo um select na tabela employees com sucesso;
17. Conexão com o banco da VM por meio do Oracle SQL Developer;
18. Duas conexões salvas com o usuário "sys" (SYSDBA), uma no CDB e a outra no PDB. Uma conexão salva com o usuário "HR" no PDB;
19. Teste feito via SQL Developer com sucesso.
