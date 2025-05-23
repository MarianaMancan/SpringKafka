📦 Kafka Producer/Consumer com Docker

Este projeto demonstra uma arquitetura básica de streaming de dados com Apache Kafka, utilizando Docker Compose para orquestração dos containers Kafka e Zookeeper.

🧱 Arquitetura

A imagem abaixo representa a arquitetura usada no projeto:
![image](https://github.com/user-attachments/assets/575b5a07-a5d3-4bc9-9ca9-9f913ebaf0f2)

---Producer envia mensagens (streams de registros) para um tópico Kafka.

---As mensagens são armazenadas em um log particionado e replicado.

---Consumer consome as mensagens do tópico.

Um tópico no Kafka é uma coleção de eventos que pode ser:

---Replicado e particionado

--Durável (por horas, dias ou anos)

--Grande ou pequeno

✨ Como executar o projeto

✅ 1. Subir os containers
docker-compose up -d
Esse comando irá subir os serviços zookeeper e kafka com as configurações apropriadas.

🔍 2. Listar os tópicos disponíveis no broker
docker exec -it kafka kafka-topics --bootstrap-server localhost:29092 --list
O Kafka está configurado com localhost:29092 para acesso externo via Docker.

 3. Consumir mensagens de um tópico
 4. docker exec -it kafka kafka-console-consumer \
  --topic mensagem \
  --from-beginning \
  --bootstrap-server kafka:9092

Este comando consome todas as mensagens desde o início do tópico mensagem.

🛠 Tecnologias usadas

Docker

Docker Compose

Apache Kafka 7.6.0

Zookeeper 7.6.0

Spring Boot (como exemplo de aplicação produtora ou consumidora)
