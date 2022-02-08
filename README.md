# Convert Postman Collections Into OpenAPI 3.1
We need a basic API for converting Postman collections into OpenAPI 3.1 format, supporting a prototype or proxy first approach to producing or generating a Postman collection and then using it to produce an OpenAPI. Allowing teams to produce OpenAPI from existing APIs or the APIs they have mocked as a collection, making it easier to be API-first without necessarily being API design first.

Proposed Tooling:

- Postman-to-openapi - https://joolfe.github.io/postman-to-openapi/
- Postman2OpenAPI - https://github.com/kevinswiber/postman2openap

Requirements:

- Accept Postman v2 or v2.1 as input
- Leverage OpenAPI 3.1 as the output
- Run as simple one call API without authentication
- Follow Postman Open Technologies platform governance
