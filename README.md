## [WIP] Lib ExceptionHandler para aplicações gRPC Micronaut 

Este repositório possui uma implementação inicial de um ServerInterceptor do gRPC capaz de tratar exceções
geradas a partir de uma rota gRPC. A princípio somente exceções que estendem de BaseBusinessException estão
sendo capturadas.

A estrutura atual de exceções está da seguinte forma:

<img src="./img/exception-structure.png" alt="Estrutura inicial"/>

Para você implementar uma exceção customizada que seja capturada pelo interceptor basta estender da **BaseBusinessException** e adicionar sua própria mensagem e código de erro.

## Testando a lib localmente

Para testar a implementação basta executar a task `shadowJar` do projeto `micronaut-grpc-exception-handler` e
importar o jar gerado no build.gradle do projeto `exception-handler-demo` substituindo o caminho 
`implementation files("diretorio-do-jar/micronaut-grpc-exception-handler-0.0.1.jar")` pelo path onde foi salvo o jar gerado anteriormente.
Após importar o jar, ainda no `exception-handler-demo`, abra o pacote controller e dentro da classe **ClientController** há uma lista com alguns nomes de exemplo, para obter uma exceção basta fazer uma request utilizando um nome existente. 


### Referências
[EXCEPTION HANDLING AND ERROR PROPAGATION IN GRPC JAVA](https://sultanov.dev/blog/exception-handling-in-grpc-java-server/)
