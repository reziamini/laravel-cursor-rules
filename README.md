# Laravel Cursor Rules

A comprehensive set of Cursor AI rules for building scalable, maintainable Laravel applications with modular architecture.

## Overview

This repository contains Cursor IDE rules that enforce best practices for Laravel development. These rules promote clean architecture, test-driven development, and maintainable code through automated code suggestions and standards enforcement.

## Installation

1. Clone this repository:
```bash
git clone https://github.com/reziamini/laravel-cursor-rules.git
```

2. Copy the `.cursor` directory to your Laravel project root:
```bash
cp -r laravel-cursor-rules/.cursor /path/to/your/laravel/project/
```

3. Restart Cursor IDE to load the new rules.

## Rules Overview

### 🔧 Coding Standards (`coding-standards.mdc`)
- PHP 8+ syntax and PSR compliance
- SOLID, DRY, KISS principles
- Service layer architecture
- Type-safe methods and proper casting
- DTO patterns for data transfer
- Contract-based development

### 🏗️ Module Structure (`module-structure.mdc`)
- Modular architecture with independent business features
- Clear directory structure for each module
- Cross-module communication patterns (Commands vs Events)
- Shared logic organization in `Modules/Share/`

### 🗄️ Database Schema (`db-schema.mdc`)
- Migration best practices with foreign key constraints
- Soft delete requirements
- Factory and seeder organization
- Schema documentation requirements

### 🌐 API Standards (`api-standards.mdc`)
- Consistent JSON response structure
- Laravel Resource usage
- Proper HTTP status codes
- Authentication with Laravel Passport
- Policy-based authorization

### ✅ Feature Testing (`feature-testing.mdc`)
- Pest PHP testing framework
- Comprehensive endpoint testing
- AAA (Arrange/Act/Assert) pattern
- Database state assertions
- Authentication and authorization testing

### 🔗 Integration Testing (`integration-testing.mdc`)
- Service layer testing with real database
- Direct service method calls
- Exception and edge case testing
- Database transaction management

### 📮 Postman Collection (`postman-collection.mdc`)
- Organized API documentation
- Environment variables for tokens and URLs
- Request/response examples
- Module-based folder structure

## Architecture Principles

This rule set enforces a **modular monolith** architecture where:

- **Modules** are independent business features
- **Services** contain all business logic
- **DTOs** handle data transfer between layers
- **Contracts** define module interfaces
- **Policies** manage authorization
- **Resources** format API responses

## Response Format

All API responses follow a consistent JSON structure:

```json
{
  "success": true,
  "code": 200,
  "data": { ... }
}
```

For paginated responses:
```json
{
  "success": true,
  "code": 200,
  "data": [...],
  "pagination": {
    "current_page": 1,
    "last_page": 5,
    "per_page": 15,
    "total": 75
  }
}
```

For errors:
```json
{
  "success": false,
  "code": 422,
  "error": "Validation failed"
}
```

## Testing Strategy

- **Feature Tests**: HTTP endpoint validation through full stack
- **Integration Tests**: Service layer validation with real database
- **Unit Tests**: Individual class/method testing (when needed)

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test the rules in your own Laravel project
5. Submit a pull request

## License

This project is open source and available under the [MIT License](LICENSE).

## Author

**Reza Amini** - [GitHub](https://github.com/reziamini)

## Support

If you find these rules helpful, please ⭐ this repository!

For questions or suggestions, open an issue on GitHub.