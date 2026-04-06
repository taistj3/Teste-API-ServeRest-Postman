# CT 1 — Listar produtos cadastrados

**Funcionalidade:** Listar produtos cadastrados.

**Objetivo:** Verificar se a API retorna a lista de produtos cadastrados.

**Pré-requisitos:**

- Subir servidor da API localmente via docker usando comando:
  docker run -p 3000:3000 serverest/serverest:latest;
- API disponível em:
  http://localhost:3000/;
- Existirem produtos cadastrados na base (opcional);

**Passo a Passo:**

1. Abrir o Postman;
2. Fazer uma requisição do tipo GET;
3. Configurar a URL para:
   http://localhost:3000/produtos;
4. Enviar requisição;
5. Observar resposta.

**Resultado Esperado:**

- Servidor deve retornar status code 200;
- Resposta deve estar em formato json.

**Resultado Obtido:** [Espaço para registrar o resultado após a execução do teste]

**Evidência:** [Anexe capturas de tela, logs ou qualquer evidência do teste]

**Observações:** [Adicione quaisquer notas ou comentários relevantes]

---

# CT 2 — Cadastrar produto com dados válidos

**Funcionalidade:** Cadastrar produto com dados válidos.

**Objetivo:** Verificar se a API cadastra um produto corretamente quando enviados dados válidos e token de autorização.

**Pré-requisitos:**

- Subir servidor da API localmente via docker usando comando:
  docker run -p 3000:3000 serverest/serverest:latest;
- API disponível em:
  http://localhost:3000/;
- Possuir token válido salvo em variável de ambiente {{token}}.

**Passo a Passo:**

1. Abrir o Postman;
2. Fazer uma requisição do tipo POST;
3. Configurar a URL para:
   http://localhost:3000/produtos;
4. Adicionar Authorization Bearer Token usando variável {{token}};
5. Configurar o body da requisição no formato json com dados válidos de produto;
6. Enviar requisição;
7. Observar resposta.

**Resultado Esperado:**

- Servidor deve retornar status code 201;
- Resposta deve estar em formato json;
- Resposta deve conter mensagem:
  "Cadastro realizado com sucesso";
- Resposta deve conter campo _id;
- ID deve ser salvo em variável de ambiente {{ID}}.

**Resultado Obtido:** [Espaço para registrar o resultado após a execução do teste]

**Evidência:** [Anexe capturas de tela, logs ou qualquer evidência do teste]

**Observações:** [Adicione quaisquer notas ou comentários relevantes]

---

# CT 3 — Cadastrar produto sem token

**Funcionalidade:** Cadastrar produto sem token de autorização.

**Objetivo:** Verificar se a API impede o cadastro de produto quando não é enviado token válido.

**Pré-requisitos:**

- Subir servidor da API localmente via docker usando comando:
  docker run -p 3000:3000 serverest/serverest:latest;
- API disponível em:
  http://localhost:3000/.

**Passo a Passo:**

1. Abrir o Postman;
2. Fazer uma requisição do tipo POST;
3. Configurar a URL para:
   http://localhost:3000/produtos;
4. Não enviar token de autorização;
5. Configurar o body da requisição no formato json com dados válidos de produto;
6. Enviar requisição;
7. Observar resposta.

**Resultado Esperado:**

- Servidor deve retornar status code 401;
- Resposta deve estar em formato json;
- Resposta deve conter mensagem:
  "Token de acesso ausente, inválido, expirado ou usuário do token não existe mais".

**Resultado Obtido:** [Espaço para registrar o resultado após a execução do teste]

**Evidência:** [Anexe capturas de tela, logs ou qualquer evidência do teste]

**Observações:** [Adicione quaisquer notas ou comentários relevantes]

---

# CT 4 — Buscar produto por ID válido

**Funcionalidade:** Buscar produto por ID válido.

**Objetivo:** Verificar se a API retorna corretamente os dados de um produto existente.

**Pré-requisitos:**

- Subir servidor da API localmente via docker usando comando:
  docker run -p 3000:3000 serverest/serverest:latest;
- API disponível em:
  http://localhost:3000/;
- Produto previamente cadastrado;
- ID do produto salvo na variável {{ID}}.

**Passo a Passo:**

1. Abrir o Postman;
2. Fazer uma requisição do tipo GET;
3. Configurar a URL para:
   http://localhost:3000/produtos/{{ID}};
4. Enviar requisição;
5. Observar resposta.

**Resultado Esperado:**

- Servidor deve retornar status code 200;
- Resposta deve estar em formato json;
- Resposta deve conter _id igual ao valor armazenado na variável {{ID}}.

**Resultado Obtido:** [Espaço para registrar o resultado após a execução do teste]

**Evidência:** [Anexe capturas de tela, logs ou qualquer evidência do teste]

**Observações:** [Adicione quaisquer notas ou comentários relevantes]

---

# CT 5 — Buscar produto com ID inválido

**Funcionalidade:** Buscar produto com ID inválido.

**Objetivo:** Verificar se a API retorna erro ao buscar produto inexistente.

**Pré-requisitos:**

- Subir servidor da API localmente via docker usando comando:
  docker run -p 3000:3000 serverest/serverest:latest;
- API disponível em:
  http://localhost:3000/.

**Passo a Passo:**

1. Abrir o Postman;
2. Fazer uma requisição do tipo GET;
3. Configurar a URL para:
   http://localhost:3000/produtos/id_invalido;
4. Enviar requisição;
5. Observar resposta.

**Resultado Esperado:**

- Servidor deve retornar status code 400;
- Resposta deve estar em formato json;
- Resposta deve conter mensagem:
  "Produto não encontrado".

**Resultado Obtido:** [Espaço para registrar o resultado após a execução do teste]

**Evidência:** [Anexe capturas de tela, logs ou qualquer evidência do teste]

**Observações:** [Adicione quaisquer notas ou comentários relevantes]

---

# CT 6 — Editar produto existente

**Funcionalidade:** Editar produto existente.

**Objetivo:** Verificar se a API atualiza corretamente os dados de um produto existente.

**Pré-requisitos:**

- Subir servidor da API localmente via docker usando comando:
  docker run -p 3000:3000 serverest/serverest:latest;
- API disponível em:
  http://localhost:3000/;
- Produto previamente cadastrado;
- ID salvo na variável {{ID}};
- Possuir token válido salvo na variável {{token}}.

**Passo a Passo:**

1. Abrir o Postman;
2. Fazer uma requisição do tipo PUT;
3. Configurar a URL para:
   http://localhost:3000/produtos/{{ID}};
4. Adicionar Authorization Bearer Token {{token}};
5. Configurar body no formato json com novos dados válidos;
6. Enviar requisição;
7. Observar resposta.

**Resultado Esperado:**

- Servidor deve retornar status code 200;
- Resposta deve estar em formato json;
- Resposta deve conter mensagem:
  "Registro alterado com sucesso".

**Resultado Obtido:** [Espaço para registrar o resultado após a execução do teste]

**Evidência:** [Anexe capturas de tela, logs ou qualquer evidência do teste]

**Observações:** [Adicione quaisquer notas ou comentários relevantes]

---

# CT 7 — Excluir produto existente

**Funcionalidade:** Excluir produto existente.

**Objetivo:** Verificar se a API exclui corretamente um produto existente.

**Pré-requisitos:**

- Subir servidor da API localmente via docker usando comando:
  docker run -p 3000:3000 serverest/serverest:latest;
- API disponível em:
  http://localhost:3000/;
- Produto previamente cadastrado;
- ID salvo na variável {{ID}};
- Possuir token válido salvo na variável {{token}}.

**Passo a Passo:**

1. Abrir o Postman;
2. Fazer uma requisição do tipo DELETE;
3. Configurar a URL para:
   http://localhost:3000/produtos/{{ID}};
4. Adicionar Authorization Bearer Token {{token}};
5. Enviar requisição;
6. Observar resposta.

**Resultado Esperado:**

- Servidor deve retornar status code 200;
- Resposta deve estar em formato json;
- Resposta deve conter mensagem:
  "Registro excluído com sucesso".

**Resultado Obtido:** [Espaço para registrar o resultado após a execução do teste]

**Evidência:** [Anexe capturas de tela, logs ou qualquer evidência do teste]

**Observações:** [Adicione quaisquer notas ou comentários relevantes]