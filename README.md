# Contract testing workshop: Spring cloud contract and Pact
Workshop on consumer driven contracts

[Diagram of consumer driven contracts]

## Requirements
- Java
- Node & NPM

## Terminology
Consumer -> Gets a message from the queue, sends an HTTP request
Producer -> Puts a message from the queue, responds to an HTTP request
Service -> Backend service / microservice / backend client
Frontend -> Web app., Angular app., frontend client

## HTTP Contracts with Spring Cloud Contracts
### Assignment 1: A frontend consumer and a backend provider

Consumer: Tournament registration frontend client.
Provider: Registrant backend service.

> As a user, I want to register myself for an upcoming tournament so I can participate in it.
>
> A user needs to fill in his
> - email 
> - weight
> - birthDate
> - name
> - firstName
> - clubName
> - gender (m/f)
> 
> Make a contract for a successful request (user registered), and an unsuccessful request (not registered, missing required field, f.e. name)

Write on paper or in a note taking app a contract for the above feature. 
Come to an agreement on how the consumer and provider are going to communicate with each other.

Make sure to define the following:

- the path of the request
- the HTTP method of the request
- potential request headers
- potential query parameters in the request
- the JSON structure of the request body
- the JSON structure of the response body
- the HTTP status code of the response
- potential response headers.

Keep this document as a reference for later.

### Assignment 2: Write the contract in Spring Cloud Contract
#### Step 1: Create the contract on the producer side.
Consumer driven, does not mean consumer owned. 
Contracts remain with the producer in Spring cloud contracts.

1. Clone the Registrant service (producer)
2. Create the groovy contracts based on the definition you created in the first assignment.
([HTTP Contract DSL Documentation](https://cloud.spring.io/spring-cloud-contract/reference/html/project-features.html#features-http))
3. When you are ready create a PR in the producer repository.
4. Generate the stubs for the consumer by running ``` mvn clean install –DskipTests```

While the PR is open, the consumer can start developing, 
in the meantime the producer can provide feedback on the contract inside the PR, 
or when he agrees with the contract he can begin with the implementation.

### Assignment 3: A Service Consumer and Service Provider

> As the registrant service, I want to get a list of tournaments for the current or upcoming competition year.
> A competition year starts from 1 september until 30 june.
> I want to receive the name, startdate and max # of participants

Write on paper or in a note taking app a contract for the above feature. Come to an agreement on how the
consumer and provider are going to communicate with each other.

Make sure to define the following:

- the path of the request
- the HTTP method of the request
- potential request headers
- potential query parameters in the request
- the JSON structure of the request body
- the JSON structure of the response body
- the HTTP status code of the response
- potential response headers.

Keep this document as a reference for later.

### Assignment 2: Write the contract in Spring Cloud Contract
#### Step 1: Create the contract on the producer side.
Consumer driven, does not mean consumer owned. Contracts remain with the producer.

1. Clone the Registrant service (producer)
2. Create the groovy contracts based on the definition you created in the first assignment.
([HTTP Contract DSL Documentation](https://cloud.spring.io/spring-cloud-contract/reference/html/project-features.html#features-http))
3. When you are ready create a PR in the producer repository.
4. Generate the stubs for the consumer by running ``` mvn clean install –DskipTests```

While the PR is open, the consumer can start developing 




