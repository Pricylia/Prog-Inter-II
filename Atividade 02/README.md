# Atividade B - Galera do Vôlei - API Contracts/ Design API

### **JOGADORES**
- Filtro de jogadores
  ```
  GET /api/jogadores?sexo=?&idade?&categoria=?
  ```

1. Listar jogadores
- Endpoint:
  ```
  GET api/jogadores
  ```
- Parâmetros:
  ```
  { "username": "string", "idade": "number", "genero": string, "categoria": string}
  ```
- Resposta:
  ```
  { "message": string}
  ```
- Códigos de erro:
  ```
  404 (lista não retornada)
  204 (requisição bem sucedida, sem jogador a ser exibido)
  500 (falha inesperada no servidor)
  ```

2. Criar jogador
- Endpoint:
  ```
  POST api/jodador/criar
  ```
  ```
  GET api/jogadores
  ```
- Parâmetros:
  ```
  { "username": "string", "idade": "number", "genero": string, "categoria": string}
  ```
- Resposta:
  ```
  { "message": string}
  ```
- Códigos de erro:
  ```
  409 (usuário já cadastrado)
  500 (falha inesperada no servidor)
  ```

3. Atualizar jogador
- Endpoint:
  ```
  PUT /api/jogadores/{id}
  ```
- Parâmetros:
  ```
  { "username": "string", "idade": "number", "genero": string, "categoria": string}
  ```
- Resposta:
  ```
  { "message": string}
  ```
- Códigos de erro:
  ```
  404 (jogador não encontrado)
  400 (dados inválidos)
  500 (falha inesperada no servidor)
  ```

4. Deletar jogador
- Endpoint:
  ```
  DELETE /api/jogadores/{id}
  ```
- Parâmetros:
  ```
  { "username": "string", "idade": "number", "genero": string, "categoria": string}
  ```
- Resposta:
  ```
  { "message": string}
  ```
- Códigos de erro:
  ```
  404 (jogador não encontrado)
  500 (falha inesperada no servidor)
  ```
---

### **PARTIDAS**
- Filtrar partida
  ```
  GET /api/partidas?categoria=?&status=?&data=?
  ```
1. Listar partidas
 ```
  GET /api/partidas
 ```
2. Criar Partida
- Endpoint:
  ```
  POST api/partida/criar
  ```
- Parâmetros:
  ```
  {"tipo": string, "categoria": string, "local": string, "data": date, "hora": hora, "status": string}
  ```
- Resposta:
  ```
  { "message": "Partida criada com sucesso"}
  {
  "id": "int",
  "tipo": "string",
  "categoria": "string",
  "local": "string",
  "data": "date",
  "hora": "string",
  "status": "string"
  }
  ```
- Códigos de erro:
  ```
  404 (partida não encontrada)
  500 (falha inesperada no servidor)
  ```
3. Atualizar Partida
 - Endpoint:
  ```
  PUT /api/partida/{id}/atualizar
  ```
 - Parâmetros
  ```
  {"id": int}
  ```
 - Resposta
  ```
  { "message": "Partida atualizada com sucesso" }
  {
    "id": int,
    "tipo": string,
    "categoria": string,
    "local": string,
    "data": date,
    "hora": string,
    "status": string
  }
  ```
 - Código de erro:
  ```
  404 (Partida não encontrada)
  400 (Parâmetros inválidos)
  500 (Falha inesperada no servidor)
  ```
4. Deletar partida
 - Endpoint:
  ```
  DELETE /api/partida/{id}/deletar
  ```
 - Parâmetros:
  ```
  {"id": int}
  ```
 - Resposta
  ```
  { "message": "Partida deletada com sucesso" }
  ```
 - Código de erro:
  ```
  404: Partida não encontrada
  500: Falha inesperada no servidor
  ```
