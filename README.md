# APP

This is a simple app for a gym made with Node JS, using REST API 


## Functional Requirements 

- [x] Register
- [x] Authentication
- [x] Profile
- [ ] Check-in by user (number)
- [ ] User history check-in 
- [ ] Search closest gym by coordinates
- [ ] Search gym by name
- [x] User make check-in
- [ ] Validate check-in from a user
- [ ] Create a gym 


## Model rules

- [x] User can't register with duplicate email
- [x] User can't make multiple check-in in a single day
- [x] User can't make check-in if user isn't closest to gym (100m)
- [ ] Check-in only can be validated until 20min after created
- [ ] Check-in only can be validated by administrators
- [ ] Only administrators can create gyms


## Non functional requirements

- [x] User password must be cryptographically
- [x] Data gonna be prestited in PostgreSql
- [ ] Every lists gonna be paginated (20 rows for page)
- [ ] User gonna be identifyied by a JWT token


## Installation 
```
 npm init -y //inicialize npm
 npm i fastify //node express was descontinued, so let's user fastify
 npm i -D typescript tsx tsup // typescript, tsx for serving file, tsup for building
 npm i dotenv zod // dotenv for readin .env, zod for validating schema 
 npm i -D eslint @reativ/eslint-config //installin eslint for automatic ident code 
 npm i -D prisma //for reading data from database - ORM
 npm i @prisma/client //Prisma Client JS is an auto-generated query builder that enables type-safe database access
 npx prisma init //to generate prisma configuration
 npm i bcryptjs //for crypt 
 npm i -D @types/bcryptjs //for typescript version of crypt library
 npm i -D @types/node //for typescript version of crypt library
 tsc --init // for generating tsconfig 
 npm i dayjs //for working with dates
 ```

install test dependencies

```
npm i -D vitest //for testing use esbuild exists ither 
npm i -D vitest-tsconfig-paths //for using the paths configured in typescript
npm i -D @vitest/coverage-v8 //to see how many of the code are covered by tests 
npm i -D @vitest/ui //interface for unit tests
```
### File .npmrc
Here we gonna say to npm to install exact version from package.json (not adding the ^ in versions)

### File .env
For environments 

### File .eslint.json
For eslint configuration

### File .eslintignore 
For ingore folders to ignore linting

### Folder prisma 
For configuration prisma 

## Prisma

``` npx prisma migrate dev ``` for migrate the schema to be created in database
``` npx prisma studio ``` to open ui to see database schema

# Design pattern

## Repository 

Repository Design Pattern is a structural pattern that separates the logic that retrieves data from the underlying storage (such as a database) from the business logic of the application. This pattern is commonly used to manage the persistence layer in an application.


## The Dependency Inversion Principle (DIP) 

The Dependency Inversion Principle (DIP) is one of the SOLID principles of object-oriented design. DIP states that high-level modules should not depend on low-level modules but rather both should depend on abstractions. In other words, it encourages the use of abstractions (interfaces or abstract classes) to decouple high-level and low-level components, allowing for more flexibility, scalability, and easier maintenance.
To implement the Dependency Inversion Principle in JavaScript, you often use interfaces (or abstract classes) to define contracts, and then you have concrete implementations that adhere to those contracts.

## Clean code

Use variables explicit the name of function 

## Domain-driven design (DDD)

Domain-driven design (DDD) is a major software design approach, focusing on modeling software to match a domain according to input from that domain's experts. Under domain-driven design, the structure and language of software code (class names, class methods, class variables) should match the business domain

# Testing

## Unit tests

Should be a lot of diferent test, for testint the unit (explicit function)
For testing gonna use data in memory, for not presiting data in database, because test should use most isolated possible

## Test-driven development (TDD) 

Test-driven development (TDD) is a software development approach in which tests are written before the code they are intended to validate.
While TDD can be a powerful approach, it requires a mindset shift and discipline. Developers need to be committed to writing tests first and embracing the iterative nature of the process

## Tests end to end

### configuration 
Create a file for the test environment. Inside prisma/vitest-environment-prisma/

- ```  npm init -y ``` to generate a package.json file with default values 
- prisma-test-environment.ts  

After you need to link node modules, because we want to use the main package.json see command "test:create-prisma-environment" and "test:install-prisma-environment"

### Run 

``` npm run teste:e2e ```

Here, because we are using postgresql, we can have multiple schemas inside same database, so we can create a new schema and remove in end for ours tests.(Isolate the database) 



