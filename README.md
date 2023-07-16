# fullcycle-keycloak-go

Após baixar o repositório, rode docker-compose up -d. Isso disponibilizará o keycloak e o mysql.
Logue no keyclok acessando http://localhost:8080 com as credenciais admin / admin.

No keycloak, crie:

*  Realm: myrealm
*  User: myuser
   *  Em credentials crie uma senha.
*  Client: myclient
    * Em root url coloque http://host.docker.internal:8081
    * Em Access Type selecione confidential.
    * Na aba credentials copie a secret e cole na linha 14 do arquivo main.go

Pare o contianer e rode novamente com docker-compose up -d --build. 

Depois, acesse a aplicação go em http://localhost:8081.

Informe o usuário myuser e a senha que você criou. Após isso você será redirecionado para a aplicação go que exibirá os tokens que você recebeu do keycloak.

