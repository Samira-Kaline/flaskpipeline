# Executando a pipeline

## Permissões

Antes de começar a execução da pipeline é importante 
que algumas permissões estejam em rigor por isso siga o passo a passo descrito.

1. Entre no repositorio abaixo:

    `$ cd /var/run`

2. Mude as permissões do arquivo docker.sock:
   
   `$ sudo chmod 777 docker.sock`

3. Adicione o usuário do `jenkins``
   
   `$ useradd jenkins`

4. Modificar o grupo do usuário `jenkins` para o grupo `docker`.
   
   `$ sudo usermod -aG docker jenkins`

   Permitindo que o usuário `jenkins` possa excutar os comandos do docker sem precisar de permissão

5. Agora verifique se o usuário `jenkins` foi adicionado o grupo docker.

    `$ grep docker /etc/group`

## Criar e executando a Pipeline

Em `localhost:8080` ou no Jenkins.

1. Logar com o usuário criado
2. Em `Painel de controle` vá em `Nova tarefa`
3. Dê um nome para a pipeline
4. Selecione a opção `Pipeline`
5. Clique em `Tudo certo` para continuar
6. Adicione a descrição(Opcional)
7. Em `Pipeline: Definition` selecione a opção `Pipeline script from SCM`
8. Em `SCM` selecione a opção `Git`
9. Coloque o link do repositorio `https://github.com/Samira-Kaline/flaskpipeline.git` no campo `Repository URL`
10. Adicione na opção `Branch Specifier (blank for 'any')` o branch do repositorio `*/main`
11. Clique em `Salvar`
12. No lado esquedo da tela do jenkins irá aparecer a opção `Contrua agora`, clique para iniciar.
13. Por fim, clique em `Open Blue Ocean`, para abrir o Blue Ocean para geranciar a pipeline