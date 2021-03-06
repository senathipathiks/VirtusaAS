# ubb-coursesπ

The aim of this project is to create a friendlier environment for the students to learn during the university.
Our project will enable course material upload and organizing them into bite-sized lessons.
We aim to support uploading images, videos and other lessons formats. We aim to increase student interactivity with features
such as polls, quizzes, and projects such that the students will be able to more easily learn the subjects that matter.

# Core Technologies

- [React](https://reactjs.org/)
- [Spring](https://reactjs.org/)
- [PostgreSQL](https://www.postgresql.org/)

# Getting Started

### Requirements
- [JDK-11](https://www.oracle.com/technetwork/java/javase/downloads/jdk11-downloads-5066655.html)
- [node](https://nodejs.org/en/)
- [postgres](https://www.postgresql.org/)

Clone the repository and run `yarn install` in the `frontend` directory, then `yarn start` to start the development
frontend server and `mvn spring-boot:run` to start the backend folder. Keep in mind that you might need to change the
database and flyway configuration from the `application.properties` file from backend. After you start the backend, 
`flyway` will automatically generate the database schema.

# Project Structure

This project is a mono-repository. It contains both the frontend project and the backend APIs.

## Frontend

The `frontend` folder contains the react application and all the necessary dependencies for this project to work.  
It is written in React with:
* `Flow` - a library maintained by Facebook for type linting
* `react-redux` - a state-management library to maintain a single source of truth 
* `redux-sagas` - a library to make application side-effects easier to deal with
* `Sass` - a preprocessor scripting language that is interpreted or compiled into Cascading Style Sheets (CSS)

```
.
βββ public              # Folder containing default information about the webpage
βββ src                 # The source code of the project, all components reside inside their own folder
|   βββ app             # Folder containing the first page in the website
|   |   βββ config      # Folder containing main configuration files for redux, sagas and other
|   |   βββ course      # Contains all the components used in forming the pages related to courses
|   |   βββ login       # Contains the components needed for the login page
|   |   βββ ...
|   |   βββ pages       # The folder containing all available pages in the website
|   |   |   ...
|   |   βββ app.jsx     # Component file (Note: we are using javascript with flow typeing)
|   βββ index.js        # Entry point for the website
|   βββ index.scss      # Initial stylesheet, it contains default variables like colors and spacing
|   βββ ...
βββ .eslintrc           # Configuration for eslint
βββ .flowconfig         # Configuration for flow
βββ .prettierrc         # Configuration for prettier
βββ ...
```

### Guidelines
 
#### Naming
* Folders naming should be all lowercase.
* Folders naming should suggest the scope use of the components inside.
* `styles` folders should contain only styling `.scss` files.
* Component files should be lower camel case.
* Dividing the name of the component with dots (ex: `course.redux.jsx`, `desktop.coursePage.jsx`) should be done only for redux and sagas files and for final pages.
* Component names should always be upper camel case, excepting the Higher Order Components.

#### Tips 
* Always run `yarn fix` before pushing, otherwise the JS Tests will fail.
* Try to reuse as much code as possible.
* Keep the code clean and name the variables properly.
* Try to use React Hooks as much as possible.

For more information please see the `README.md` file inside the folder.

## Backend

The `backend` folder contains the Spring Boot server: configuration, models and business logic.

```
.
βββ .mvn                            # Folder containing the maven wrapper
βββ src                             # The source code of the project
|   βββ main            
|   |   βββ java 
|   |   |   βββ annotations                 # Contains special annotations intercepting requests
|   |   |   βββ configs                     # Configurations folder for authentication and requests
|   |   |   βββ models                      # Database entities folder
|   |   |   βββ repositories                # JPA Repositories folder
|   |   |   βββ services                    # Services folder
|   |   |   βββ controllers                 # Controllers folder
|   |   |   βββ security                    # Aditional security classes such as the token provider
|   |   |   βββ dtos                        # DTOs folder for the entities
|   |   |   βββ BackendApplication.java     # Main file of the project
|   |   βββ resources
|   |   |   βββ application.properties      # Application envirnoment variables
|   |   βββ βββ db.migrations               # Folder containing the database migration files
|   βββ test                # Tests folder for the entire application
|   ...   
βββ pom.xml                 # Dependencies for the application
```

For more information please see the `README.md` file inside the folder.

# Authors

- **Teodor Voicencu**
- **Mihnea Ungureanu**
- **Sebastian Stegaru**
- **Teodor Strut**
- **Nicoleta Ungur**
- **Matei Stroia**
- **Vlad Tugui**
- **Tanko Gabor Tihamer**

# License
This project is licensed under the MIT License - see the `LICENSE.md` file for details.
