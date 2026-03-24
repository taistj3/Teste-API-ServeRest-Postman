# Casos de Teste - Login Serverest

---

## 1. Login com sucesso como usuário

**Funcionalidade:** Fazer login como usuário com email e senha válidos e cadastrados.

**Objetivo:** Verificar se a API permite autenticação quando email e senha válidos são informados, retornando token de acesso.

**Pré-requisitos:**

- Subir servidor da API localmente via docker usando comando: docker run -p 3000:3000 serverest/serverest:latest
- API disponível em: http://localhost:3000/
- Usuário previamente cadastrado na base da API

**Passo a Passo:**

1. Abrir o Postman
2. Fazer uma requisição do tipo POST
3. Configurar a URL para: http://localhost:3000/login
4. Configurar o body da requisição para o formato json
5. Informar email e senha válidos e cadastrados
6. Enviar requisição e observar resposta

**Resultado Esperado:**

- Servidor deve retornar status code 200
- Resposta deve estar em formato json
- A resposta deve conter mensagem: “Login realizado com sucesso“
- Deve conter campo Authorization com token de acesso

**Resultado Obtido:**  
- Servidor retornou status code 200
- Resposta em formato json
- Mensagem de sucesso exibida corretamente como string
- Resposta contém campo Authorization com Bearer token

**Evidência:**  
[Anexe capturas de tela, logs ou qualquer evidência do teste]

**Observações:**  
[Adicione quaisquer notas ou comentários relevantes]

---

## 2. Login com sucesso como aministrador

**Funcionalidade:** Fazer login como usuário com email e senha válidos e cadastrados.

**Objetivo:** Verificar se a API permite autenticação quando email e senha válidos são informados, retornando token de acesso.

**Pré-requisitos:**

- Subir servidor da API localmente via docker usando comando: docker run -p 3000:3000 serverest/serverest:latest
- API disponível em: http://localhost:3000/
- Usuário previamente cadastrado na base da API

**Passo a Passo:**

1. Abrir o Postman
2. Fazer uma requisição do tipo POST
3. Configurar a URL para: http://localhost:3000/login
4. Configurar o body da requisição para o formato json
5. Informar email e senha válidos e cadastrados como admin
6. Enviar requisição e observar resposta

**Resultado Esperado:**

- Servidor deve retornar status code 200
- Resposta deve estar em formato json
- A resposta deve conter mensagem: “Login realizado com sucesso“
- Deve conter campo Authorization com token de acesso

**Resultado Obtido:**  
- Servidor retornou status code 200
- Resposta em formato json
- Mensagem de sucesso exibida corretamente como string
- Resposta contém campo Authorization com Bearer token

**Evidência:**  
[Anexe capturas de tela, logs ou qualquer evidência do teste]

**Observações:**  
[Adicione quaisquer notas ou comentários relevantes]

---

## 3. Email incorreto e senha correta

**Funcionalidade:** Fazer login como usuário com email incorreto e senha correta.

**Objetivo:** Verificar se a API impede autenticação quando email incorreto é informado, retornando erro de não autorizado.

**Pré-requisitos:**

- Subir servidor da API localmente via docker usando comando: docker run -p 3000:3000 serverest/serverest:latest
- API disponível em: http://localhost:3000/
- Usuário previamente cadastrado na base da API

**Passo a Passo:**

1. Abrir o Postman
2. Fazer uma requisição do tipo POST
3. Configurar a URL para: http://localhost:3000/login
4. Configurar o body da requisição para o formato json
5. Informar email incorreto e senha correta
6. Enviar requisição e observar resposta

**Resultado Esperado:**

- Servidor deve retornar status code 401
- Resposta deve estar em formato json
- A resposta deve conter mensagem: “Email e/ou senha inválidos“
- Não deve conter campo Authorization com token de acesso

**Resultado Obtido:**  
- Servidor retornou status code 401
- Resposta em formato json
- Resposta com mensagem de erro correta e em formato string
- Ausência de campo Authorization e sem retorno de token de acesso

**Evidência:**  
[Anexe capturas de tela, logs ou qualquer evidência do teste]

**Observações:**  
[Adicione quaisquer notas ou comentários relevantes]

---

## 4. Email correto e senha incorreta

**Funcionalidade:** Fazer login como usuário com email correto e senha incorreta.

**Objetivo:** Verificar se a API impede autenticação quando senha incorreta é informada, retornando erro de não autorizado.

**Pré-requisitos:**

- Subir servidor da API localmente via docker usando comando: docker run -p 3000:3000 serverest/serverest:latest
- API disponível em: http://localhost:3000/
- Usuário previamente cadastrado na base da API

**Passo a Passo:**

1. Abrir o Postman
2. Fazer uma requisição do tipo POST
3. Configurar a URL para: http://localhost:3000/login
4. Configurar o body da requisição para o formato json
5. Informar email correto e senha incorreta
6. Enviar requisição e observar resposta

**Resultado Esperado:**

- Servidor deve retornar status code 401
- Resposta deve estar em formato json
- A resposta deve conter mensagem: “Email e/ou senha inválidos“
- Não deve conter campo Authorization com token de acesso

**Resultado Obtido:**  
- Servidor retornou status code 401
- Resposta em formato json
- Resposta com mensagem de erro correta e em formato string
- Ausência de campo Authorization e sem retorno de token de acesso

**Evidência:**  
[Anexe capturas de tela, logs ou qualquer evidência do teste]

**Observações:**  
[Adicione quaisquer notas ou comentários relevantes]

---

## 5. Email com formato inválido

**Funcionalidade:** Fazer login como usuário com email em formato inválido.

**Objetivo:** Verificar se a API impede autenticação quando email é informado em formato inválido.

**Pré-requisitos:**

- Subir servidor da API localmente via docker usando comando: docker run -p 3000:3000 serverest/serverest:latest
- API disponível em: http://localhost:3000/

**Passo a Passo:**

1. Abrir o Postman
2. Fazer uma requisição do tipo POST
3. Configurar a URL para: http://localhost:3000/login
4. Configurar o body da requisição para o formato json
5. Informar email em formato inválido e senha válida
6. Enviar requisição e observar resposta

**Resultado Esperado:**

- Servidor deve retornar status code 400
- Resposta deve estar em formato json
- A resposta deve conter mensagem: "email deve ser um email válido"
- Não deve conter campo Authorization com token de acesso

**Resultado Obtido:**  
- Servidor retornou status code 400
- Resposta em formato json
- Resposta com mensagem de erro correta e em formato string
- Ausência de campo Authorization e sem retorno de token de acesso

**Evidência:**  
[Anexe capturas de tela, logs ou qualquer evidência do teste]

**Observações:**  
[Adicione quaisquer notas ou comentários relevantes]

---

## 6. Campo email vazio

**Funcionalidade:** Fazer login como usuário deixando campo email vazio.

**Objetivo:** Verificar se a API impede autenticação quando campo email não é informado.

**Pré-requisitos:**

- Subir servidor da API localmente via docker usando comando: docker run -p 3000:3000 serverest/serverest:latest
- API disponível em: http://localhost:3000/

**Passo a Passo:**

1. Abrir o Postman
2. Fazer uma requisição do tipo POST
3. Configurar a URL para: http://localhost:3000/login
4. Configurar o body da requisição para o formato json
5. Deixar campo email vazio e informar senha válida
6. Enviar requisição e observar resposta

**Resultado Esperado:**

- Servidor deve retornar status code 400
- Resposta deve estar em formato json
- A resposta deve conter mensagem: "email não pode ficar em branco"
- Não deve conter campo Authorization com token de acesso

**Resultado Obtido:**  
- Servidor retornou status code 400
- Resposta em formato json
- Resposta com mensagem de erro correta e em formato string
- Ausência de campo Authorization e sem retorno de token de acesso

**Evidência:**  
[Anexe capturas de tela, logs ou qualquer evidência do teste]

**Observações:**  
[Adicione quaisquer notas ou comentários relevantes]

---

## 7. Campo senha vazio

**Funcionalidade:** Fazer login como usuário deixando campo senha vazio.

**Objetivo:** Verificar se a API impede autenticação quando campo senha não é informado.

**Pré-requisitos:**

- Subir servidor da API localmente via docker usando comando: docker run -p 3000:3000 serverest/serverest:latest
- API disponível em: http://localhost:3000/

**Passo a Passo:**

1. Abrir o Postman
2. Fazer uma requisição do tipo POST
3. Configurar a URL para: http://localhost:3000/login
4. Configurar o body da requisição para o formato json
5. Informar email válido e deixar campo senha vazio
6. Enviar requisição e observar resposta

**Resultado Esperado:**

- Servidor deve retornar status code 400
- Resposta deve estar em formato json
- A resposta deve conter mensagem: "password não pode ficar em branco"
- Não deve conter campo Authorization com token de acesso

**Resultado Obtido:**  
- Servidor retornou status code 400
- Resposta em formato json
- Resposta com mensagem de erro correta e em formato string
- Ausência de campo Authorization e sem retorno de token de acesso

**Evidência:**  
[Anexe capturas de tela, logs ou qualquer evidência do teste]

**Observações:**  
[Adicione quaisquer notas ou comentários relevantes]

---

## 8. Campos email e senha vazios

**Funcionalidade:** Fazer login como usuário deixando campos email e senha vazios.

**Objetivo:** Verificar se a API impede autenticação quando campos obrigatórios não são informados.

**Pré-requisitos:**

- Subir servidor da API localmente via docker usando comando: docker run -p 3000:3000 serverest/serverest:latest
- API disponível em: http://localhost:3000/

**Passo a Passo:**

1. Abrir o Postman
2. Fazer uma requisição do tipo POST
3. Configurar a URL para: http://localhost:3000/login
4. Configurar o body da requisição para o formato json
5. Deixar campos email e senha vazios
6. Enviar requisição e observar resposta

**Resultado Esperado:**

- Servidor deve retornar status code 400
- Resposta deve estar em formato json
- A resposta deve conter mensagem: "email não pode ficar em branco"
- A resposta deve conter mensagem: "password não pode ficar em branco"
- Não deve conter campo Authorization com token de acesso

**Resultado Obtido:**  
- Servidor retornou status code 401
- Resposta em formato json
- Resposta com mensagem de erro correta e em formato string
- Ausência de campo Authorization e sem retorno de token de acesso

**Evidência:**  
[Anexe capturas de tela, logs ou qualquer evidência do teste]

**Observações:**  
[Adicione quaisquer notas ou comentários relevantes]