## Atividade B - API Contracts/ Design API

### **JOGADORES**
Gerenciamento e consulta de jogadores na plataforma.

---

1. Listar jogadores
- Endpoint: GET /api/jogadores

- Descrição: Retorna uma lista de jogadores, com opção de filtro.

- Parâmetros de Filtro (query):
sexo: Filtra pelo sexo do jogador.
idade: Filtra pela idade do jogador.
categoria: Filtra pela categoria do jogador.

- Resposta - Sucesso (200):
  ```
  {"id": "int", "username": "string", "idade": "number", "genero": "string", "categoria": "string"}
  ```
- Códigos de erro:
  ```
  404 (lista não retornada)
  204 (requisição bem sucedida, sem jogador a ser exibido)
  500 (falha inesperada no servidor)
  ```

2. Criar jogador
- Endpoint:POST api/jodador/criar

- Descrição: Cria um novo jogador no sistema.

- Parâmetros do Corpo (body):
  ```
  { "username": "string", "idade": "number", "genero": string, "categoria": string}
  ```
- Resposta - Sucesso (201):
  ```
  { "message": "Jogador criado com sucesso" }
  ```
- Códigos de erro:
  ```
  409 (usuário já cadastrado)
  500 (falha inesperada no servidor)
  ```

3. Atualizar jogador
- Endpoint: PUT /api/jogadores/{id}
  
- Descrição: Atualiza os dados de um jogador existente.

- Parâmetros:
  ```
  { "username": "string", "idade": "number", "genero": string, "categoria": string}
  ```
- Resposta - do Corpo (body):
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
- Endpoint: DELETE /api/jogadores/{id}
  
- Descrição: Remove um jogador do sistema.

- Resposta:
  ```
  { "message": "Jogador deletado com sucesso"}
  ```
- Códigos de erro:
  ```
  404 (jogador não encontrado)
  500 (falha inesperada no servidor)
  ```
---

### **PARTIDAS**
1. Listar Partidas
- Endpoint: GET /api/partidas

- Descrição: Retorna uma lista de partidas, com opção de filtro.

- Parâmetros de Filtro (query):
  ```
  categoria: Filtra pela categoria da partida.
  status: Filtra pelo status da partida.
  data: Filtra pela data da partida.
  ```

- Respostas:
  ```
  { "id": "int", "tipo": "string", "categoria": "string", "local": "string", "data": "date", "hora": "string", "status": "string" }
  ```

- Erros:
  ```
  404 (jogador não encontrado)
  204: Requisição bem-sucedida, mas sem partidas a serem exibidas.
  500 (falha inesperada no servidor)
  ```

2. Criar Partida
- Endpoint: POST api/partida/criar

- Descrição: Cria uma nova partida no sistema.

- Parâmetros do Corpo (body):
  ```
  { "tipo": "string", "categoria": "string", "local": "string", "data": "date", "hora": "string", "status": "string" }
  ```

- Resposta - Sucesso (201):
  ```
  { "message": "Partida criada com sucesso"}
  ```
- Erro:
  ```
  404 (partida não encontrada)
  500 (falha inesperada no servidor)
  ```
3. Atualizar Partida
- Endpoint: PUT /api/partida/{id}/atualizar
 
- Descrição: Atualiza os dados de uma partida existente.

- Parâmetros do Corpo (body):
  ```
  { "tipo": "string", "categoria": "string", "local": "string", "data": "date", "hora": "string", "status": "string" }
  ```
  
- Resposta - Sucesso (200):
  ```
  { "message": "Partida atualizada com sucesso" }
  ```
- Erro:
  ```
  404 (Partida não encontrada)
  400 (Parâmetros inválidos)
  500 (Falha inesperada no servidor)
  ```
4. Deletar partida
- Endpoint: DELETE /api/partida/{id}/deletar

- Descrição: Remove uma partida do sistema.

- Resposta
  ```
  { "message": "Partida deletada com sucesso" }
  ```
- Código de erro:
  ```
  404: Partida não encontrada
  500: Falha inesperada no servidor
  ```
