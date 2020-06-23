# Create a simple GitHub Actions CI pipeline

## You Will Need

- Docker
  - [Windows](https://hub.docker.com/editions/community/docker-ce-desktop-windows/)
  - [macOS](https://hub.docker.com/editions/community/docker-ce-desktop-mac/)

---

## Task

- Create a GitHub Actions Workflow to
  - Test and Package the `PlayStudios.MyService` application
  - Build a Docker image for running the application
    - The image does not need to be pushed to a registry
- This is not an exercise on your .Net knowledge, use the following commands to prepare the application
  - Unit tests are run with
    ```Bash
    dotnet test ./PlayStudios.MyService/
    ```
  - The application is packaged with
    ```Bash
    dotnet publish \
      ./PlayStudios.MyService/PlayStudios.MyService.WebApi/ \
      -c Release \
      -o ./dist
    ```
  - The packaged application is run with
    ```Bash
    dotnet ./dist/PlayStudios.MyService.WebApi.dll
    ```
- Think about what should be in a **production ready** Dockerfile

---

## Testing

- Run the built Docker image and browse to `http://localhost:5000/weatherforecast`

---

## References

- https://docs.docker.com/engine/reference/builder/
- https://help.github.com/en/actions/reference/workflow-syntax-for-github-actions
- https://help.github.com/en/actions/reference/context-and-expression-syntax-for-github-actions
