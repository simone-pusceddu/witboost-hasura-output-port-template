## Component Information

| Field Name       | Value                     |
|:-----------------|:--------------------------|
| **Name**         | ${{ values.name }}        |
| **Description**  | ${{ values.description }} |
| **Domain**       | ${{ values.domain }}      |
| **Data Product** | ${{ values.dataproduct }} |
| **Identifier**   | ${{ values.identifier }}  |
| **Depends On**   | ${{ values.dependsOn }}   |


## GraphQL Queries

| Field Name            | Value                         |
|:----------------------|:------------------------------|
| **Custom Table Name** | ${{ values.customTableName }} |
| **select**            | ${{ values.select }}          |
| **select by pk**      | ${{ values.selectByPk }}      |
| **select aggregate**  | ${{ values.selectAggregate }} |
| **select stream**     | ${{ values.selectStream }}    |


# Data Consumption

Hasura is a powerful open-source engine that helps you build, manage, and consume GraphQL APIs quickly and easily. With Hasura, you can create flexible and scalable APIs backed by your preferred database, enabling efficient data retrieval and manipulation.

To access your Hasura GraphQL endpoints, we'll explore two options:

- using the Hasura console
- utilizing custom tools with a JWT token obtained via the Azure Command-Line Interface (CLI).

Each option serves a specific purpose, so let's dive into the details.

## Option 1: Hasura Console

The Hasura console provides a user-friendly interface for managing your GraphQL API. However, it's important to note that login to the console is only possible with an admin token. The console is primarily designed for administrative tasks, such as schema exploration, query execution, and data relationship management.

To access the Hasura console:

- Open your web browser and navigate to the URL where your Hasura console is hosted.

- In the console login page, enter the admin token provided to you.

- Once logged in, you can use the console to explore and interact with your GraphQL API. It provides features like schema exploration, query execution, and managing data relationships.

  > While the Hasura console allows you to experiment and interact with your API in a playground-like environment, it is not intended as a vehicle for data consumption in a production setting. Instead, we recommend using custom tools with a JWT token for more controlled data access and enforcing role-based permissions.

## Option 2: Custom Tools with JWT Token obtained via AZ CLI

Utilizing custom tools alongside a JWT token obtained through the Azure Command-Line Interface (CLI) offers a more secure and controlled approach to consuming data from your Hasura GraphQL API.

By leveraging the Azure CLI, you can obtain a JWT token associated with your Azure Active Directory (AAD) application. This token can be used to authenticate and authorize requests to your Hasura endpoints, ensuring that only authorized users with appropriate roles and permissions can access and manipulate the data.

Here's how to use the Azure CLI to obtain a JWT token:

- Install the Azure CLI on your machine if you haven't already. You can download it from the official Microsoft website.

- Open a terminal or command prompt and login to the Azure CLI using your Azure account credentials by running the following command:

```sh
az login
```

- Follow the authentication process prompted by the command. Once you are successfully logged in, you can proceed to the next step.

- Obtain an access token for your Hasura GraphQL API by running the following command, replacing `YOUR_TENANT_ID` with the Azure Active Directory (AAD) tenant ID of the playground:

```sh
az account get-access-token --tenant YOUR_TENANT_ID
```

The command will return a JSON response containing an access token. Take note of the value associated with the `accessToken` field.

With the JWT token at hand, you can use custom tools, such as GraphQL clients or other HTTP-based clients, to send requests to your Hasura GraphQL API. These tools will enable you to include the JWT token in the request headers, granting you the ability to enforce fine-grained access controls defined within Hasura.

By following this method, you can securely and efficiently consume data from your Hasura GraphQL API, ensuring that your application adheres to the defined access rules and permissions.