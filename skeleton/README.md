# ${{ values.name | dump }}

- [Overview](#overview)
- [Usage](#usage)


# Overview

Use this component to create an **GraphQL Output Port** based on a Hasura Enterprise instance which helps in interacting with the data.


### What's an Output Port?

An Output Port refers to the interface that a Data Product uses to provide data to other components or systems within the organization. The methods of data sharing can range from APIs to file exports and database links.

## Hasura

Hasura is an open-source platform that provides a unified API layer over your data sources. It can be used to expose data from a variety of sources, including relational databases, NoSQL databases, and cloud storage.
It provides a number of benefits, including:
- Ease of use: Hasura is easy to use, even for non-technical users. It can be deployed in minutes, and it does not require any code changes to your data sources.
- Flexibility: Hasura can be used to expose data from a variety of sources. It also supports a variety of data access patterns, such as CRUD, GraphQL, and SQL.
- Security: Hasura provides a number of security features, such as role-based access control (RBAC) and data encryption.
- Scalability: Hasura can be scaled easily to meet the needs of your applications. It can also be deployed in a variety of environments, including on-premises, in the cloud, and in hybrid deployments.

Hasura's GraphQL API makes it easy to consume data from your data products. GraphQL is a powerful query language that allows you to specify exactly the data that you need. This makes it easy to build applications that only use the data that they need, which can improve performance and scalability.

Learn more about it on the [official website](https://hasura.io/docs/latest/index/).


# Usage

To get information about this component and how to use it, refer to this [document](./docs/index.md).