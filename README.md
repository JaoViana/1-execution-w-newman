# 1-execution-w-newman
- Bem vindo!
Com esse pequeno texto tentei explicar a primeira execução de uma automação utilizando o Newman

--> Utilizando e executando o Newman
*Antes de tudo, é preciso ter o nodejs instalado na maquina*
*Documentação do newman: https://learning.postman.com/docs/running-collections/using-newman-cli/command-line-integration-with-newman/*

-> Executando coleção via linha de comando
- newman run {{caminho_coleccao_json}}: Executa uma coleção em json;
- newman run {{url_da_colecao}}: Executa uma coleção via url;
- newman run colecao_postman.json -e testEnv.json: Executa coleção com arquivo de variáveis;

-> Rodando o primeiro programa:
- Antes de mais nada vamos seguir uns passos:
1. Para iniciarmos a execução de alguma automação é preciso que os arquivos (geralmente .json) sejam exportandos do programa aonde foram executados.
No nosso caso, seria do postman. Lembrando que: o arquivo deve ser um arquivo .json e sempre está na versão 2.1 (atualmente é a mais recomendada)
2. Com o arquivo salvo (salvo em qualquer pasta!) no computador, vamos utilizar o comando "newman run.." para roda-lo.
No meu caso, o arquivo se chama "GO_Rest_API.postman_collection.json".
Utilizando a formula: newman run (comando) + C:\Users\joao.ramos\Documents\API\Estudo de Newman (pasta de origem) + "GO_Rest_API.postman_collection.json" (nome do arquivo)
Logo: newman run C:\Users\joao.ramos\Documents\API\Estudo de Newman> newman run GO_Rest_API.postman_collection.json e executa-lo no prompt de comando.
(De maneira simples e sem erros: Abrir o cmd na pasta origem e executar pelo o nome torna o trabalho muito mais assertivo).
3. Agora que sabemos que podemos executar o programa, é importante também (caso seja necessário) executar as variavéis de ambiente. Nesse caso, podemos utilizar o comando "-e".
Ficaria assim:
newman run GO_Rest_API.postman_collection.json -e New_Environment.postman_environment.json
4. Existe também o comando "-n" que é digitado na frente de cada programa e serve para rodar um número X de vezes.

-> Outros comandos:
1. -h : Menu de ajuda
2. --folder[nome da pasta]: Executa uma pasta especifica de uma coleção
Ex: newman run GO_Rest_API.postman_collection.json -e New_Environment.postman_environment.json --folder Usuários 
3. --delay --request: Serve para adicionar um tempo na execução entre as requisiões
Ex: --delay --request 10000 newman run GO_Rest_API.postman_collection.json -e New_Environment.postman_environment.json --folder Usuários 
4. --bail: Para o automação se encontrar um erro de assert
Ex: newman run GO_Rest_API.postman_collection.json -e New_Environment.postman_environment.json --bail
4. --verbose: Aumenta o número de informações fornecidas
5. --silent: Oculta as interações
6. -d: Specify a data file to use either json or csv


