# Projet gRPC WebSocket Reverse Proxy

## Description
Ce projet met en place un service de chat simplifié en utilisant gRPC et un reverse proxy WebSocket. L'objectif est de relayer les messages entre un client WebSocket et un serveur gRPC.

## Technologies utilisées
- Node.js
- Protocol Buffers (Protobuf)
- gRPC avec `@grpc/grpc-js` et `@grpc/proto-loader`
- WebSockets avec `ws`

## Installation
1. Cloner le dépôt :
   ```sh
   git clone https://github.com/BintaBall/reverse_proxy_grpc_tp5
   cd grpc-ws-reverse-proxy
   ```
2. Installer les dépendances :
   ```sh
   npm install
   ```

## Structure du projet
```
grpc-ws-reverse-proxy/
│-- chat.proto           # Définition du service gRPC
│-- server.js           # Implémentation du serveur gRPC
│-- proxy.js            # Reverse proxy WebSocket
│-- client.html         # Interface Web pour tester le chat (Bonus)
│-- package.json        # Configuration du projet
```

## Configuration et Exécution
### 1. Démarrer le serveur gRPC
```sh
node server.js
```
Le serveur écoute sur `0.0.0.0:50051`.

### 2. Démarrer le reverse proxy WebSocket
```sh
node proxy.js
```
Le proxy écoute sur `ws://localhost:8080`.

## Test avec Postman
1. Ouvrir Postman et créer une nouvelle requête WebSocket.
2. Se connecter à `ws://localhost:8080`.
3. Envoyer un message JSON au format suivant :
   ```json
   {
     "chat_message": {
       "id": "msg1",
       "room_id": "room1",
       "sender_id": "client1",
       "content": "Hello World!"
     }
   }
   ```

## Fonctionnalités supplémentaires
### Historique des messages
Une méthode `GetChatHistory` a été ajoutée pour récupérer les derniers messages échangés.

### Client Web (Bonus)
Un fichier `client.html` est fourni pour tester le chat via un navigateur. Ce client utilise WebSockets pour envoyer et recevoir des messages en temps réel.
![Exemple de la page client](images\cleint1.png)
![Exemple de la page client](images\cleint2.png)
![Exemple de la page client](images\cleint2.png)



## Auteur
Projet développé dans le cadre du TP5 de SoA et Microservices, année 2024/2025.

