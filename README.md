# APP

This is a simple app for a gym made with Node JS, using REST API 

## Functional Requirements 

- [x] Register
- [ ] Authentication
- [ ] Profile
- [ ] Check-in by user (number)
- [ ] User history check-in 
- [ ] Search closest gym by coordinates
- [ ] Search gym by name
- [ ] User make check-in
- [ ] Validate check-in from a user
- [ ] Create a gym 


## Model rules

- [x] User can't register with duplicate email
- [ ] User can't make multiple check-in in a single day
- [ ] User can't make check-in if user isn't closest to gym (100m)
- [ ] Check-in only can be validated until 20min after created
- [ ] Check-in only can be validated by administrators
- [ ] Only administrators can create gyms


## Non functional requirements

- [x] User password must be cryptographically
- [x] Data gonna be prestited in PostgreSql
- [ ] Every lists gonna be paginated (20 rows for page)
- [ ] User gonna be identifyied by a JWT token


## installation 
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

# Design pattern

- Repository 
- Inversão de dependencias: O que cria a classe é que diz o que vai ser criado 
- Fatorizar código 

# Testing

For testing gonna use data in memory, for not presiting data in database


