# CT 1 — Listar produtos cadastrados

**Funcionalidade:** Listar produtos cadastrados.

**Objetivo:** Verificar se a API retorna a lista de produtos cadastrados.

**Pré-requisitos:**

- Subir servidor da API localmente via docker usando comando:
  docker run -p 3000:3000 serverest/serverest:latest;
- API disponível em:
  http://localhost:3000/;
- Existirem produtos cadastrados na base;

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

# CT 5 — Buscar produto com ID inexistente

**Funcionalidade:** Buscar produto com ID inexistente.

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
   http://localhost:3000/produtos/id_inexistente;
4. ID deve ter 16 dígitos;
5. Enviar requisição;
6. Observar resposta.

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

---

# CT 8 — Cadastrar produto com nome duplicado

**Funcionalidade:** Cadastrar produto com nome já existente.

**Objetivo:** Verificar se a API impede cadastro de produto com nome duplicado, garantindo integridade dos dados.

**Pré-requisitos:**

- Subir servidor da API localmente via docker usando comando:
  docker run -p 3000:3000 serverest/serverest:latest;
- API disponível em:
  http://localhost:3000/;
- Produto já cadastrado com determinado nome;
- Possuir token válido salvo na variável {{token}}.

**Passo a Passo:**

1. Abrir o Postman;
2. Fazer uma requisição do tipo POST;
3. Configurar a URL para:
   http://localhost:3000/produtos;
4. Adicionar Authorization Bearer Token {{token}};
5. Configurar o body da requisição com nome de produto já existente;
6. Enviar requisição;
7. Observar resposta.

**Resultado Esperado:**

- Servidor deve retornar status code 400;
- Resposta deve estar em formato json;
- Resposta deve conter mensagem:
    "Já existe produto com esse nome".

**Resultado Obtido:** 

- Servidor retornou status code 400;
- Resposta em formato json com mensagem:
    "Já existe produto com esse nome".

**Evidência:** [Anexe capturas de tela, logs ou qualquer evidência do teste]

**Observações:** [Adicione quaisquer notas ou comentários relevantes]

---

# CT 9 — Cadastrar produto com preço negativo

**Funcionalidade:** Cadastrar produto com preço inválido.

**Objetivo:** Verificar se a API impede cadastro de produto com preço negativo.

**Pré-requisitos:**

- Subir servidor da API localmente via docker usando comando:
  docker run -p 3000:3000 serverest/serverest:latest;
- API disponível em:
  http://localhost:3000/;
- Possuir token válido salvo na variável {{token}}.

**Passo a Passo:**

1. Abrir o Postman;
2. Fazer uma requisição do tipo POST;
3. Configurar a URL para:
   http://localhost:3000/produtos;
4. Adicionar Authorization Bearer Token {{token}};
5. Configurar o body da requisição com valor de preço negativo;
6. Enviar requisição;
7. Observar resposta.

**Resultado Esperado:**

- Servidor deve retornar status code 400;
- Resposta deve estar em formato json;
- Resposta deve conter campo "preco" com mensagem:
    "preco deve ser um número positivo".

**Resultado Obtido:** 

- Servidor retornou status code 400;
- Resposta está em formato json;
- Resposta contém campo "preco" com mensagem:
    "preco deve ser um número positivo".

**Evidência:** [Anexe capturas de tela, logs ou qualquer evidência do teste]

**Observações:** [Adicione quaisquer notas ou comentários relevantes]

---

# CT 10 — Cadastrar produto com quantidade negativa

**Funcionalidade:** Cadastrar produto com quantidade inválida.

**Objetivo:** Verificar se a API impede cadastro de produto com quantidade negativa.

**Pré-requisitos:**

- Subir servidor da API localmente via docker usando comando:
  docker run -p 3000:3000 serverest/serverest:latest;
- API disponível em:
  http://localhost:3000/;
- Possuir token válido salvo na variável {{token}}.

**Passo a Passo:**

1. Abrir o Postman;
2. Fazer uma requisição do tipo POST;
3. Configurar a URL para:
   http://localhost:3000/produtos;
4. Adicionar Authorization Bearer Token {{token}};
5. Configurar o body da requisição com valor de quantidade negativo;
6. Enviar requisição;
7. Observar resposta.

**Resultado Esperado:**

- Servidor deve retornar status code 400;
- Resposta deve estar em formato json;
- Resposta deve conter campo "quantidade" com mensagem:
    "quantidade deve ser maior ou igual a 0".

**Resultado Obtido:** 

- Servidor retornou status code 400;
- Resposta está em formato json;
- Resposta contém campo "quantidade" com mensagem:
    "quantidade deve ser maior ou igual a 0".

**Evidência:** [Anexe capturas de tela, logs ou qualquer evidência do teste]

**Observações:** [Adicione quaisquer notas ou comentários relevantes]

---

# CT 11 — Cadastrar produto com campos obrigatórios ausente

**Funcionalidade:** Cadastrar produto sem informar todos os campos obrigatórios.

**Objetivo:** Verificar se a API valida obrigatoriedade dos campos e impede cadastro incompleto.

**Pré-requisitos:**

- Subir servidor da API localmente via docker usando comando:
  docker run -p 3000:3000 serverest/serverest:latest;
- API disponível em:
  http://localhost:3000/;
- Possuir token válido salvo na variável {{token}}.

**Passo a Passo:**

1. Abrir o Postman;
2. Fazer uma requisição do tipo POST;
3. Configurar a URL para:
   http://localhost:3000/produtos;
4. Adicionar Authorization Bearer Token {{token}};
5. Configurar o body da requisição omitindo um campo obrigatório (preço);
6. Enviar requisição;
7. Observar resposta.

**Resultado Esperado:**

- Servidor deve retornar status code 400;
- Resposta deve estar em formato json;
- Resposta deve conter mensagem informando campo obrigatório ausente.

**Resultado Obtido:** 

- Servidor retornou status code 400;
- Resposta está em formato json;
- Resposta contém mensagem informando campo obrigatório ausente:
    "preco é obrigatório".

**Evidência:** [Anexe capturas de tela, logs ou qualquer evidência do teste]

**Observações:** [Adicione quaisquer notas ou comentários relevantes]

---

# CT 12 — Editar produto inexistente

**Funcionalidade:** Editar produto com ID inexistente.

**Objetivo:** Verificar comportamento da API ao tentar editar recurso que não existe.

**Pré-requisitos:**

- Subir servidor da API localmente via docker usando comando:
  docker run -p 3000:3000 serverest/serverest:latest;
- API disponível em:
  http://localhost:3000/;
- Possuir token válido salvo na variável {{token}}.

**Passo a Passo:**

1. Abrir o Postman;
2. Fazer uma requisição do tipo PUT;
3. Configurar a URL para:
   http://localhost:3000/produtos/id_invalido;
4. Adicionar Authorization Bearer Token {{token}};
5. Configurar body com dados válidos;
6. Enviar requisição;
7. Observar resposta.

**Resultado Esperado:**

- Servidor deve retornar status code 201;
- Resposta deve estar em formato json;
- Resposta deve conter mensagem:
    "Cadastro realizado com sucesso"
- Resposta deve conter campo "_id" com novo ID.

**Resultado Obtido:** 

- Servidor retornou status code 201;
- Resposta está em formato json;
- Resposta contém mensagem:
    "Cadastro realizado com sucesso"
- Resposta contém campo "_id" com novo ID.

**Evidência:** [Anexe capturas de tela, logs ou qualquer evidência do teste]

**Observações:** 

- Documentação no Swagger contém a seguinte regra de negócio relacionada a este endpoint: Não é permitido cadastrar produto com nome já utilizado. Caso não seja encontrado usuário com o ID informado é realizado novo cadastro ao invés de alteração.

---

# CT 13 — Excluir produto inexistente

**Funcionalidade:** Excluir produto inexistente.

**Objetivo:** Verificar se a API trata corretamente tentativa de exclusão de recurso inexistente.

**Pré-requisitos:**

- Subir servidor da API localmente via docker usando comando:
  docker run -p 3000:3000 serverest/serverest:latest;
- API disponível em:
  http://localhost:3000/;
- Possuir token válido salvo na variável {{token}}.

**Passo a Passo:**

1. Abrir o Postman;
2. Fazer uma requisição do tipo DELETE;
3. Configurar a URL para:
   http://localhost:3000/produtos/id_invalido;
4. Adicionar Authorization Bearer Token {{token}};
5. Enviar requisição;
6. Observar resposta.

**Resultado Esperado:**

- Servidor deve retornar status code 200 ou 400 conforme regra da API;
- Resposta deve estar em formato json;
- Resposta deve conter mensagem coerente com operação de exclusão.

**Resultado Obtido:** [Espaço para registrar o resultado após a execução do teste]

**Evidência:** [Anexe capturas de tela, logs ou qualquer evidência do teste]

**Observações:** [Adicione quaisquer notas ou comentários relevantes]

---

# CT 14 — Buscar produto após exclusão

**Funcionalidade:** Buscar produto após exclusão.

**Objetivo:** Verificar consistência dos dados após remoção de recurso.

**Pré-requisitos:**

- Subir servidor da API localmente via docker usando comando:
  docker run -p 3000:3000 serverest/serverest:latest;
- API disponível em:
  http://localhost:3000/;
- Produto previamente cadastrado;
- Produto previamente excluído;
- ID salvo na variável {{ID}}.

**Passo a Passo:**

1. Abrir o Postman;
2. Fazer uma requisição do tipo GET;
3. Configurar a URL para:
   http://localhost:3000/produtos/{{ID}};
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

# CT 15 — Buscar produto com ID com inválido

**Funcionalidade:** Buscar produto com ID inválido.

**Objetivo:** Verificar se a API retorna erro ao buscar produto com ID que contenha menos de 16 dígitos.

**Pré-requisitos:**

- Subir servidor da API localmente via docker usando comando:
  docker run -p 3000:3000 serverest/serverest:latest;
- API disponível em:
  http://localhost:3000/.

**Passo a Passo:**

1. Abrir o Postman;
2. Fazer uma requisição do tipo GET;
3. Configurar a URL para:
   http://localhost:3000/produtos/id_inválido;
4. ID deve ter menos de 16 dígitos;
5. Enviar requisição;
6. Observar resposta.

**Resultado Esperado:**

- Servidor deve retornar status code 400;
- Resposta deve estar em formato json;
- Resposta deve conter mensagem:
  "id deve ter exatamente 16 caracteres alfanuméricos".

**Resultado Obtido:** [Espaço para registrar o resultado após a execução do teste]

**Evidência:** [Anexe capturas de tela, logs ou qualquer evidência do teste]

**Observações:** [Adicione quaisquer notas ou comentários relevantes]

---

# CT 16 — Validar estrutura do contrato na listagem de produtos

**Funcionalidade:** Validar estrutura da resposta da API.

**Objetivo:** Garantir que o contrato da API mantém consistência dos campos retornados.

**Pré-requisitos:**

- Subir servidor da API localmente via docker usando comando:
  docker run -p 3000:3000 serverest/serverest:latest;
- API disponível em:
  http://localhost:3000/.

**Passo a Passo:**

1. Abrir o Postman;
2. Fazer uma requisição do tipo GET;
3. Configurar a URL para:
   http://localhost:3000/produtos;
4. Enviar requisição;
5. Observar estrutura da resposta.

**Resultado Esperado:**

- Servidor deve retornar status code 200;
- Resposta deve estar em formato json;
- Cada item da lista deve conter:
  - _id
  - nome
  - preco
  - descricao
  - quantidade
- Tipos de dados devem ser consistentes entre requisições.

**Resultado Obtido:** [Espaço para registrar o resultado após a execução do teste]

**Evidência:** [Anexe capturas de tela, logs ou qualquer evidência do teste]

**Observações:** [Adicione quaisquer notas ou comentários relevantes]