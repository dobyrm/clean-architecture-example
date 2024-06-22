# clean-architecture-example

## Project Folder Structure

This project follows the principles of Clean Architecture, with clear separation of concerns across different layers of the application. Below is the detailed folder structure with descriptions of the subfolders contained in each layer.

### Folder Structure

```
src
    modules
        module-name
            application
                use-cases
                services
                interfaces
            domain
                entities
                value-objects
                repositories
                services
                events
            infrastructure
                orm
                repositories
                services
                events
            presentation
                controllers
                routes
                dtos
            module-name.container.ts
        module.container.ts
    shared
        application
            use-cases
            services
            interfaces
        domain
            entities
            value-objects
            repositories
            services
            events
        infrastructure
            orm
            repositories
            services
            events
        presentation
            controllers
            routes
            dtos
        shared.container.ts
    app.ts
    container.ts
```

### Folder Descriptions

- **modules**: Contains feature-specific modules, each with its own layers (application, domain, infrastructure, presentation).
  - **module-name**: Represents a specific module with the following subfolders:
    - **application**: Handles the application logic.
      - `use-cases`: Business logic and operations.
      - `services`: Auxiliary tasks and coordination services.
      - `interfaces`: Defines contracts for services and repositories.
    - **domain**: Contains domain-specific logic and entities.
      - `entities`: Business objects and their attributes.
      - `value-objects`: Immutable objects that describe certain properties.
      - `repositories`: Interfaces for data persistence.
      - `services`: Business logic that does not fit into entities.
      - `events`: Domain events signaling state changes.
    - **infrastructure**: Manages data persistence and external services.
      - `orm`: ORM configurations and entities.
      - `repositories`: Implementations of repository interfaces.
      - `services`: Implementations of infrastructure services.
      - `events`: Event handlers and mechanisms for event publishing.
    - **presentation**: Handles the user interface and API.
      - `controllers`: Handle requests and execute use-cases.
      - `routes`: Define API endpoints.
      - `dtos`: Data Transfer Objects for communication between layers.
    - `module-name.container.ts`: Dependency injection container for the module.

- **shared**: Contains shared resources and services used across multiple modules.
  - **application**: Shared application logic.
    - `use-cases`, `services`, `interfaces`: Similar to the structure in individual modules but shared across the application.
  - **domain**: Shared domain logic.
    - `entities`, `value-objects`, `repositories`, `services`, `events`: Common domain logic shared by multiple modules.
  - **infrastructure**: Shared infrastructure logic.
    - `orm`, `repositories`, `services`, `events`: Common infrastructure logic shared by multiple modules.
  - **presentation**: Shared presentation logic.
    - `controllers`, `routes`, `dtos`: Common presentation logic shared by multiple modules.
  - `shared.container.ts`: Dependency injection container for shared services.

- **app.ts**: Main application entry point.
- **container.ts**: Global dependency injection container.
