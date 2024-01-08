# Getting Started

### Reference Documentation
For further reference, please consider the following sections:

* [Official Gradle documentation](https://docs.gradle.org)
* [Spring Boot Gradle Plugin Reference Guide](https://docs.spring.io/spring-boot/docs/3.2.1/gradle-plugin/reference/html/)
* [Create an OCI image](https://docs.spring.io/spring-boot/docs/3.2.1/gradle-plugin/reference/html/#build-image)
* [Coroutines section of the Spring Framework Documentation](https://docs.spring.io/spring/docs/6.1.2/spring-framework-reference/languages.html#coroutines)
* [Spring Reactive Web](https://docs.spring.io/spring-boot/docs/3.2.1/reference/htmlsingle/index.html#web.reactive)

### Guides
The following guides illustrate how to use some features concretely:

* [Building a Reactive RESTful Web Service](https://spring.io/guides/gs/reactive-rest-service/)

### Additional Links
These additional references should also help you:

* [Gradle Build Scans – insights for your project's build](https://scans.gradle.com#gradle)

Terminal commands:

To spin Docker container Up:
    docker-compose -f ./docker-compose-dynamodb.yaml
To create a Table:
    aws dynamodb --endpoint-url http://localhost:8042 \
create-table --table-name demo-customer-info \
--attribute-definitions AttributeName=customerId,AttributeType=S \
--key-schema AttributeName=customerId,KeyType=HASH \
--provisioned-throughput ReadCapacityUnits=5,WriteCapacityUnits=5

Send Post Http requests - To create a new Customer record in the table
~/demo/dynamodemo ❯ curl -H "Content-type: application/json" -X POST http://localhost:8080/users 
                    -d '{"emailAddress": "sample@email.com", "firstName": "Bob", "lastName": "Jones"}'

To Get Http requests - To get the customer id matched record from the table
~/demo/dynamodemo ❯ curl http://localhost:8080/users/16c07cc3-da69-4960-98f5-040e0ad5f4d8

