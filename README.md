## API_Petstore_testes_automatizados

Este projeto foi desenvolvido para o desafio de Testes Automatizados API (com Postman), documentação disponível em:
https://documenter.getpostman.com/view/13303115/UVyn2yyi


A documentação completa da API Petstore utilizada, pode ser acessada em:
https://petstore.swagger.io/#/

Os arquivos json da coleção e do ambiente (Tests) utilizados para a realização dos testes de API constam na Pasta Postman_Collections:
- API_Petstore.postman_collection;
- Tests.postman_environment;


O projeto foi dividido em duas pastas principais: PET e USER.


### PET
Contém todas as requisições relacionadas aos pets.

- Request "POST - Add a new pet": utilizado para adicionar novos pets;
    
    No caso deste teste, ao add um novo pet, o "id_pet" é atualizado (parâmetro constando como variável do ambiente) e utilizado como padrão nas demais requisições desta pasta (GET - Find pet by ID e DELETE - Deletes a pet).

- Request "GET - Finds pets by status": utilizado para buscar pets por determinado status;
- Request "GET - Find pet by ID": utilizado para buscar um pet específico, através do seu ID;
- Request "DELETE - Deletes a pet": utilizado para apagar um pet específico, através do seu ID;



### USER
Contém todas as requisições relacionadas aos usuários.

- Request "POST - Creates list of users": utilizado para adicionar novos usuários;
- Request "GET - Logs user into the system": utilizado para realizar o login de usuários no sistema (Basic Auth);
- Request "DELETE - Delete user": utilizado para apagar um usuário específico, através do seu ID;



### TESTES REALIZADOS
Os testes foram divididos de acordo com o método utilizado nas requisições.


#### TESTES DAS REQUISIÇÕES GET AND POST
Foram realizados testes para garantir que a resposta das requisições atenda aos parâmetros esperados:
- Status code 200;
- Status code contendo string 'OK';
- Response contendo o formato JSON;


#### TESTE EXCLUSIVO PARA REQUISIÇÕES POST
Testes realizados para testar o tempo de resposta das requisições Post (esperado menor que 4 segundos).


#### TESTES DAS REQUISIÇÕES DELETE
De acordo com o padrão de resposta esperado, atendimento aos parâmetros:
- Campo "type" contendo "unknown";
- Campo "code" contendo "200";


#### TESTE DE CONTRATO
Validação do body da response para criação de usuário, verificando se corresponde ao Schema esperado:

{
    "code": 200,
    "type": "unknown",
    "message": "ok"
}
