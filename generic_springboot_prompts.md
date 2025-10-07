# 🚀 Generic Multi-Step Spring Boot Project Prompt Template (Industry Standard)

---

## 🧩 **STEP 1 — Generate Entities and DTOs**

You are an expert Java backend engineer and software architect.  

Generate a complete set of **JPA entity classes and corresponding DTOs** based on a SQL query, database schema, or entity description provided by the user.  

### INPUT
- SQL query, schema, or entity description
- Target database (Oracle, PostgreSQL, MySQL, etc.)
- Java version: 17+
- Spring Boot version: latest stable
- Any required field types or constraints

### OBJECTIVE
1. Infer entities, fields, types, and relationships (OneToMany, ManyToOne, ManyToMany) from the input.
2. Generate JPA entities with proper annotations (@Entity, @Table, @Column, @Id, etc.).
3. Include relationships with proper fetch types and cascade rules.
4. Generate corresponding request and response DTOs, ready for later validation.
5. Include constructors, getters, setters, and equality/hashCode methods.
6. Organize code into `entity` and `dto` packages.
7. Add comments explaining inferred relationships and field mapping choices.

---

## 🧩 **STEP 2 — Implement Business Logic, Validation, and Configuration**

You are now implementing the service, repository, controller, and core infrastructure for the project.  

### INPUT
- Entities and DTOs generated in Step 1
- Business requirements (CRUD, workflows, validation rules)
- Additional requirements (e.g., datasource, YAML config, logging, OpenAPI/Swagger, security, caching)

### OBJECTIVE
1. Create repositories for each entity with CRUD and custom query support.
2. Create service interfaces and implementations implementing business logic.
3. Create REST controllers exposing endpoints for the services.
4. Apply **field-level validation** on request DTOs using standard annotations (e.g., @NotNull, @NotEmpty, @Email, @Positive).
5. Add **global exception handling** for:
   - Validation errors
   - Constraint violations
   - Generic exceptions
6. Integrate configuration and infrastructure requirements:
   - Database configuration (YAML/properties)
   - Logging setup
   - API documentation (OpenAPI/Swagger)
7. Organize code in industry-standard packages: `controller`, `service`, `service.impl`, `repository`, `exception`, `config`, `util`.
8. Provide sample unit and integration test(s) for services or controllers.

---

## 🧩 **STEP 3 — Implement Response Mapping and JSON Wrappers**

You are now implementing the mapping layer and standardized JSON responses.  

### INPUT
- Entities and DTOs from Step 1
- Services and controllers from Step 2

### OBJECTIVE
1. Implement entity-to-DTO mapping, including nested mappings where necessary.
2. Ensure mappings are reusable across services and maintain separation of concerns.
3. Standardize JSON responses using a wrapper with at least these fields: status, message, data, timestamp.
4. Integrate mappings in service layer methods before returning responses from controllers.
5. Ensure code is clean, maintainable, and follows best practices.

---

## ✅ **USAGE INSTRUCTIONS**

1. Run **Step 1** → Generates entities and DTOs.  
2. Run **Step 2** → Adds repository, service, controller, validation, exception handling, and configuration.  
3. Run **Step 3** → Adds entity-to-DTO mapping and JSON wrapper integration.  

---

### ✨ **Key Features of this Template**

- Generic and database-agnostic.
- Industry-standard layered architecture.
- Modular steps for easy GPT-based execution.
- Fully compatible with GPT-4.1 or similar LLMs.
- Includes validation, global exception handling, and standardized responses.
