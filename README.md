# Azure Function para Validação de CPF

Este projeto é uma Azure Function que valida CPFs com base nas regras de validação do Brasil. Ele foi desenvolvido utilizando **.NET 8 Isolado** e segue a abordagem de microsserviços serverless.

## 📋 Pré-requisitos

Antes de começar, certifique-se de ter instalado:
- [.NET SDK](https://dotnet.microsoft.com/download)
- [Azure Functions Core Tools](https://learn.microsoft.com/azure/azure-functions/functions-run-local)
- [Visual Studio](https://visualstudio.microsoft.com/) com a carga de trabalho **Desenvolvimento de Azure**.

## 🚀 Configuração do Projeto

1. Clone este repositório:
    ```bash
    git clone https://github.com/seu-usuario/valida-cpf-function.git
    cd valida-cpf-function
    ```

2. Abra o projeto no Visual Studio.

3. Configure o arquivo `local.settings.json` com o seguinte conteúdo:
    ```json
    {
        "IsEncrypted": false,
        "Values": {
            "AzureWebJobsStorage": "UseDevelopmentStorage=true",
            "FUNCTIONS_WORKER_RUNTIME": "dotnet"
        }
    }
    ```

## 🏃‍♂️ Como Executar Localmente

1. Abra o projeto no Visual Studio e pressione `F5` para iniciar o projeto.
2. A URL local para testar a função será exibida no terminal. Um exemplo de URL seria:
    ```bash
    http://localhost:7071/api/fnvalidacpf
    ```

3. Envie uma requisição POST para essa URL utilizando uma ferramenta como Postman ou cURL. O corpo da requisição deve ser um JSON com o seguinte formato:
    ```json
    {
        "cpf": "12345678909"
    }
    ```

4. A resposta retornará:
    - Se o CPF for válido: `"CPF válido, e não consta na base de dados de fraudes."`
    - Se o CPF for inválido: `"CPF inválido."`

## 🖥️ Publicação no Azure

1. No Visual Studio, clique com o botão direito no projeto e selecione **Publicar**.
2. Siga as instruções para configurar um recurso no Azure.
3. Após a publicação, a função estará disponível na URL fornecida pelo Azure.

## 🛠️ Estrutura do Código

- **fnvalidacpf.cs**: Contém a lógica principal para validação de CPF.
- **local.settings.json**: Configurações locais para execução.
- **host.json**: Configurações adicionais para a Azure Function.

## 📄 Regras de Validação de CPF

1. O CPF deve conter 11 dígitos.
2. Não deve conter todos os números iguais (ex.: `111.111.111-11`).
3. Os dígitos verificadores são validados com base em cálculos matemáticos.

## 📚 Referências

- [Azure Functions Documentação Oficial](https://learn.microsoft.com/azure/azure-functions/)
- [Validação de CPF - Receita Federal](https://www.gov.br/receitafederal/)

## 🤝 Contribuições

Contribuições são bem-vindas! Sinta-se à vontade para abrir issues ou pull requests.

## 📝 Licença

Este projeto está sob a licença MIT. Consulte o arquivo `LICENSE` para mais detalhes.

---

**Desenvolvido por [Seu Nome/Empresa]** 💻
