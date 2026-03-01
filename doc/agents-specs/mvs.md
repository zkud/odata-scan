# odata-scan mvs functional specification

odata-scan is nmap-like security scanning tool which is intented to probe various requests over OData services, e.g. probing entity reads to provided service with given credentials.

## Functional Requirements

1. As a security researcher, I would like to probe all entities in a service for read, by providing service url and JWT token for auth, so that I can see which entities I can access.

2. As a security expert on a project, I would like to probe all entities in a service for read, by providing service url and JWT token for auth, in CI/CD pipeline, so that I can ensure it is impossible to read entities with missing authorizations.

3. As a user, I would like to install the tool by running setup.py, so that I won't have to type python3 again and again.

**Future requirements, we should allow extention with these improvements in the initial design**
1. Support read, write, delete, update.
2. Support nested reads/writes/updates.
3. Support other auth variants, e.g. basic auth.

## Non-functional Requirements

1. All code must must be covered by unit tests except I/O calls. All I/O calls must be isolated.
2. All code must be compliant with pep 8.
3. All requirements must be specified in requirements.txt.
4. All code must be written in /src.
5. High-level architecture, including modules structure must be documented.
6. Use make for writing scripts to run unit tests, build and etc.

