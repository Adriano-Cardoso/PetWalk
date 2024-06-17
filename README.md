# PetWalk

PetWalkEventSystem é uma arquitetura orientada a eventos construída em Java Spring Boot e Apache Kafka para gerenciar passeios de pets. O sistema é dividido em diversos serviços, cada um responsável por uma parte específica do negócio.

## Tecnologias Utilizadas

- Java 17
- Spring Boot 3.x
- Spring Kafka
- Spring Data JPA
- Spring Security
- Apache Kafka
- PostgreSQL
- Docker
- JUnit e Mockito

## Estrutura do Projeto

### 1. UserService

Responsável pelo gerenciamento de usuários (clientes e passeadores).

**Métodos:**
- `createUser(User user)`
- `getUserById(Long id)`
- `updateUser(Long id, User user)`
- `deleteUser(Long id)`
- `getAllUsers()`

### 2. PetService

Responsável pelo gerenciamento de pets.

**Métodos:**
- `createPet(Pet pet)`
- `getPetById(Long id)`
- `updatePet(Long id, Pet pet)`
- `deletePet(Long id)`
- `getAllPets()`

### 3. WalkService

Responsável pelo gerenciamento de passeios.

**Métodos:**
- `scheduleWalk(Walk walk)`
- `getWalkById(Long id)`
- `updateWalk(Long id, Walk walk)`
- `cancelWalk(Long id)`
- `getAllWalks()`

### 4. NotificationService

Responsável pelo gerenciamento de notificações.

**Métodos:**
- `sendNotification(Notification notification)`

## Comunicação entre Serviços

A comunicação entre os serviços é feita através de eventos publicados e consumidos no Apache Kafka.

### Tópicos do Kafka

- **UserTopic:** Eventos relacionados a usuários.
- **PetTopic:** Eventos relacionados a pets.
- **WalkTopic:** Eventos relacionados a passeios.
- **NotificationTopic:** Eventos de notificações.

### Exemplo de Eventos

- **UserCreated**
- **UserUpdated**
- **PetCreated**
- **WalkScheduled**
- **NotificationSent**



### Passos

1. Clone o repositório:
    ```bash
    git clone https://github.com/seu-usuario/PetWalkEventSystem.git
    cd PetWalkEventSystem
    ```

2. Suba os contêineres do Docker:
    ```bash
    docker-compose up -d
    ```

3. Configure o banco de dados PostgreSQL no `application.properties`.

4. Execute o projeto:
    ```bash
    ./mvnw spring-boot:run
    ```

### Testes

Para executar os testes:
```bash
./mvnw test
