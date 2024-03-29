# Convert Postman Collections Into OpenAPI 3.1
We need a basic API for converting Postman collections into OpenAPI 3.1 format, supporting a prototype or proxy first approach to producing or generating a Postman collection and then using it to produce an OpenAPI. Allowing teams to produce OpenAPI from existing APIs or the APIs they have mocked as a collection, making it easier to be API-first without necessarily being API design first.

## Proposed Tooling

- [Postman-to-openapi](https://joolfe.github.io/postman-to-openapi/)
- [Postman2OpenAPI](https://github.com/kevinswiber/postman2openapi)

## Requirements

- Accept Postman v2 or v2.1 as input
- Leverage OpenAPI 3.1 as the output
- Run as simple one call API without authentication
- Follow Postman Open Technologies platform governance

## Platform Governance
This is the Postman Open Technologies approach to platform governance. It is applied across all APIs being developed and sustained as part of our team activity. This should act as a living checklist that is published on the workspace overview and the README for the Github repository supporting the project.

### API DEFINITION (DISCOVERY)
This part of API governance ensures that this API is able to be seen and found, with all the moving parts documented and available for driving the conversation forward.

 - **Workspace** - All work on this API is managed via a single API workspace, providing a single place to access artifacts, documentation, tests, automation, and other relevant information, including how this API is governed as part of a wider operation.
 - **OpenAPI** - There is an OpenAPI available for this API, providing a single source of truth of what is possible with this API, fully describing the surface area of the synchronous API, including requests and responses.
 - **Repository** - There is a single Github repository for this API, providing the source control for the code that powers the API, allowing for the deployment of the API to be made repeatable and reliable.
*** **Environments** - There are staging and production environments available for working with this API, providing secrets, tokens, and other variables that are environment specific, but can be used to integrate, automate, and govern this API.
*** **Documentation Collectio**n - There is always an update to set of documentation for this API, providing a reference of all available paths, parameters, and examples of how tis API works--making sure consumers have everything they need.
 - **Team** - The team behind this API are listed as contributors here in this workspace, but also via the Github repository, helping provide more visibility into who is moving the API forward, and is available to answer questions.

It is extremely difficult to govern APIs that you cannot find, making this dimension of platform governance essential to realizing every other dimension of API governance at scale across operations.

### API INSTANCE (RELIABILITY)
This part of API governance ensures that this API is as reliable as it possibly can, setting the baseline for what tests are expected as part of the quality surrounding this API.

 - **Contract Test Collection (API)** - Making sure there is a contract test in place for every path available as part of this API, making sure that the API is being tested for any change to the underlying contract.
 - **Performance Test Collection (API)** - Making sure there is a performance test in place to make sure that this API is always performing at the expected levels, ensuring that we are meeting the SLA.
 - **Security Test Collection (API)** - Making sure there is a security test in place to make sure that this API is always properly secured against the most common attacks, protecting from unwanted use.

Other types of tests can be added, providing integration, user acceptance, or possibly additional governance, but this provides the minimum bar for what is expected when it comes to this API's reliability.

### API DESIGN (CONSISTENCY)
This is where we get into more traditional territory people think of when the phrase API governance is mentioned, ensuring that the design, or surface area of the API follows a consistent set of rules and affordances.

 - **Design Governance Collection** - Ensuring that you can run a well defined set of rules against the surface area of an API, using the OpenAPI to understand how consistent this API is.
    - **Info** - Covering the basics of the name, description, and meta data.
    - **Versioning** - Requiring that this API is being versioned properly.
    - **Operations** - Checking the structure of operations for this API.
    - **Parameters** - Making sure that header, path, and query parameters conform.
    - **Responses** - Looking at each API operation response for consistency.
    - **Schema** - Evaluating just the schema being passed back and forth.

There are plenty of other rules we can add to this list, but this provides a baseline for what is needed when it comes to the design of this API, and providing not just the tests, but an interactive design guidelines we can execute for this API. 

### API OPERATIONS (DELIVERY)
This is where we start governing not just the instance of an API, and the design of the interface, but also make sure we are governing the operations around that API, help standardize and stabilize how we deliver this API. 

 - **Monitors** - Making sure we are monitoring operations, making sure we are paying attention even when the team is off doing other things.
    - **Contract** - There is a monitor scheduled to test the contract every 24 hours.
    - **Performance** - There is a monitor to test the performance of the API every hour.
    - **Security** - There is a monitor to test the security of the API every 24 hours.
    - **Governance - There is a monitor to test the governance of the API every 24 hours.
 - **Pipeline** - Making sure we are apply governance at the CI/CD pipeline layer, running the contract, security, and governance tests with each build.
    - **Contract** - Running the contract testing collection in the pipeline.
    - **Security** - Running the contract security collection in the pipeline.
    - **Governance** - Running the governance testing collection in the pipeline. 

This will be the area of this platform governance that will likely expand and contract based upon the operational needs of each individual API, but also as new ways of looking at, configuring, and automating with operations are established. 

### API REPORTING (OBSERVABILITY)
This is the part of governance where we make sure all of the activity around this API is as observable as possible, making sure that we can observe the overall state of this API, but also understand it in aggregate with all the other APIs.

 - **Reporting (TEAM ONLY)** - Leveraging native reporting to understand what is happening with this API.
 - **Application Performance Management (APM) (New Relic)** - Using monitors to pipe the results of collections runs into DataDog to make the API observable.
 - **Activity** - Understanding how the workspace, APIs, collections, monitors, and other elements are being configured as prt of work. 

Every test, governance, and operational collection should publish results in an observable way, either relying on native platform capabilities, or publishing via integrations and APIs to 3rd party solutions.
