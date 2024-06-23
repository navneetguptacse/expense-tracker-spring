# Expense-Tracker
A small project to understand spring boot, spring boot data JPA, and spring boot security. The expense-tracker is a service which comes with default set of categories. APIs are available to add/edit/delete categories and expenses. Swagger UI is integrated and it can be used to refer API documentation.

## To run the application
Start the CI.
```
docker-compose up
```

## To deploy on K8s
Follow steps described in >>> [`URL`](https://github.com/navneetguptacse/kubernetes.io/tree/master/expense-tracker) to deploy expense tracker on K8s.

## To access Swagger UI
- Application is available at >>> [`http://localhost:8080`](http://localhost:8080)
- Swagger documentation is available at >>> [`http://localhost:8080/swagger-ui.html`](http://localhost:8080/swagger-ui.html#/)
- To access the REST end points, use basic authentication.

# Available rest end points
Refer swagger documentation for more information related to headers, parameters, and body information.
- Get all categories. `::` `GET` >>> `http://localhost:8080/api/v1/category`
- Get category by id. `::` `GET` >>> `http://localhost:8080/api/v1/category?id={categoryId}`
- Get category by name. `::` `GET` >>> `http://localhost:8080/api/v1/category?name={categoryName}`
- Add new category. `::` `POST` >>> `http://localhost:8080/api/v1/category`
- Delete existing categories by names. `::` `DELETE` >>> `http://localhost:8080/api/v1/category`
- Delete an existing category by Id. `::` `DELETE` >>> `http://localhost:8080/api/v1/category/{categoryId}`
- Update an existing category. `::` `PUT` >>> `http://localhost:8080/api/v1/category/{oldcategoryname}`
- Get all expenses. `::` `GET` >>> `http://localhost:8080/api/v1/expenses`
- Get expense by id. `::` `GET` >>> `http://localhost:8080/api/v1/expenses?id={expenseId}`
- Get expense by name. `::` `GET` >>> `http://localhost:8080/api/v1/expenses?name={expenseName}`
- Add new expense. `::` `POST` >>> `http://localhost:8080/api/v1/expenses`
- Delete existing expense. `::` `DELETE` >>> `http://localhost:8080/api/v1/expenses/{expenseId}`
- Update an existing expense. `::` `PUT` >>> `http://localhost:8080/api/v1/expenses/{oldExpenseId}`

# Docker builds

To create images for x86 and arm platforms

```
docker login ghcr.io
docker buildx create --name mybuilder
docker buildx use mybuilder
docker buildx build --platform linux/amd64,linux/arm64 -t ghcr.io/navneetguptacse/expense-tracker:alpine --push .
```

# Dependency-track

This project is configured with CycloneDX maven plugin to generate SBOM file. As part of CI this SBOM file will
be uploaded to [Dependency-Track](https://dependencytrack.org/) hosted on OCI for risk assessment.

## License

This project is licensed under the MIT License. See the [`LICENSE`](LICENSE) file for details.

## Contributing
Contributions to the project are welcome! If you'd like to contribute, please fork the repository, make your changes, and submit a pull request.

## Acknowledgments
[`(Navneet)`](https://github.com/navneetguptacse/expense-tracker-spring) >>> for developing as per practicing and contributions to the project as solo developer.

I hope this README file provides a comprehensive overview of the Expense-Tracker project! Let me know if you need any further modifications.

**Note:** This project is for educational purposes and should not be used as a substitute for professional medical advice.

#### `Copyright (c) 2024 The Centrabyte Inc. with ❤️ by Navneet Gupta`
