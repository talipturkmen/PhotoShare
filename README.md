# PhotoShare

> **Archived.** This is a 2018 course/learning project and is no longer maintained. Dependencies are outdated and contain known vulnerabilities; do not deploy as-is.

A photo-sharing web application. Users register and log in, upload photos, browse all photos and their own albums, view photo details, and add comments to photos. Authentication uses JWT tokens issued by the backend.

## Tech stack

- Backend (`backend/`): Java 1.8, Spring Boot 1.3.3 (Spring Data JPA, Thymeleaf, Spring Web), MySQL (`mysql-connector-java`), `jjwt` 0.6.0, Maven wrapper
- Front end (`frontend/`): Angular 2 (`@angular/core ~2.0.0`), TypeScript 2.0.2, Angular CLI beta.17, Semantic UI (bundled CSS and JS)

## Repository structure

- `backend/`: Spring Boot application (port 8080)
  - `src/main/java/com/PhotoShare/backend/`: `controller/` (photo, user, comment endpoints), `service/`, `dao/`, `model/` (`User`, `Photo`, `Comment`), `config/` (JWT filter)
  - `src/main/resources/`: `application.properties`, static images
- `frontend/`: Angular application
  - `src/app/components/`: login, register, photo list, photo detail, album, comments, add photo
  - `src/app/services/`, `src/app/models/`

## Running it

This is best-effort documentation; the project was not re-run during the cleanup.

1. Install JDK 8 and MySQL, and start MySQL on `localhost:3306`.
2. Create a database named `PhotoShare`.
3. Check the datasource credentials in `backend/src/main/resources/application.properties` (the defaults are `root` / `sesame`).
4. From `backend/`, run `./mvnw spring-boot:run`. The backend serves images at `http://localhost:8080/images/`.
5. From `frontend/`, run `npm install` and then `npm start` (`ng serve`).

## Known issues

- The JWT signing key is hard-coded as `secretkey` in the backend.
- Passwords are stored and compared in plain text.
- The front ends depend on Angular 2 and Angular CLI beta, which are long out of support.
- This code is not suitable for real use. See the archive note above.
