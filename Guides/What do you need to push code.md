# What do you need

To keep consistency and provide the most amount of information to the user about the architecture, usage and installation of the code, the repository should adhere to the following structure:

# The README.md file:

The following is the information you need to keep in mind and follow when creating the main or any additional service needed for your application.

The file should contain at least, the following sections:

### Application Title

The name of the application should contain two parts. The first part is the target product (Learn, Student, Reach, etc.) and the second part is the name of the application itself.

An example of the name for an API application: "Learn - My awesome API application"

### Description:

This will have the target of the application, why is needed and the scope of it.

### Prerequisites:

This needs to have the information about system requirements needed before launching the application (specific packages, minimum required OSs, language versions, etc).

### Installation:

This will contain the instructions about the installation process of the application and needed configuration (if there's no README.md file in the config folder, if there is, a link to that file must be provided).

> ![TIP]
> A file under the documentation folder can be created where you explain in detail the installation of your application and then, you can refence the file here

### Launching the application

This will have the necessary commands along with the instructions of how to use the application

### Troubleshooting

A section where any troubleshooting or error messages should be addressed

# The Code:

Regarding the code, the structure itself will differ significantly from language to language, however, the code itself should have the following structure at its core:

```
  Root
    |- config
      |- <local config>
    |- database
      |- <local db files>
    |- src
      |- <App code>
    |- public
      |- <static files (if any)>
    |- tests
    |- documentation
    |- .gitignore
    |- lint-file
    |- Docker file or docker-compose file (if needed)
    |- README.md
```

This is the folder structure that should be within your project. The following will provide an explanation of each of the folders and what is expected to be present:

### config:

This folder should contain a file or files where the configuration of the application should be stored such as domains, ports, URLs, routes, etc., or any piece of information that will be needed within the application to work properly and is expected for the user to fill.

> ![TIP]
> Although is not required, it is recommended that you add a README.md file on this folder where you explain each of the config values and what it does or what type of information is expected (type of value, format, length, etc)

The folder should contain an initial configuration file with examples of configuration values (denoted with .example) and have another initial file with empty values for the user to fill.

> ![CAUTION]
> Please don't use .env files throughout the application since it could be confusing to the user or could have exposed data or PII, in addition to this, usual GitHub configurations will skip this file from being uploaded (specially with the presence of a .gitignore file)

### database:

This folder should contain the set of files that will work as local database in case your application needs one and doesn't have access to a proper database (PostgreSQL, MySQL, etc.).

This folder should contain only the files and not any handler or additional functions that can be used by the code, these functions will go within the application itself.

> ![CAUTION]
> If you're including a lite database such as SQLite, make sure that the database doesn't have any information stored in it or if there's information, is dummy data and not related to any client

### src:

This is the folder where your application code will be located. Given that structures of code changes depending on the language used to develop the application, there's no one-fit-all structure, however, it should have coherence and should be easily readable by the user.

> ![TIP]
> It is not required but we recommend that you add a README file having an overall explanation of how the code works and explaining any potential functions that might be cumbersome to read.

> ![CAUTION]
> It is required that you create a README file in case your application has an additional service within your src code explaining how it works, what configuration is needed and the installation/launch process.

### public:

If your application has any public files such as HTML, CSS or JS files that are used within your application, you can store them here and reference them in your application

### tests:

This folder will contain any unit tests or other type of test you deem necessary for the correct functioning of your application. If there's no test, the folder can be omitted.

### documentation:

This folder will contain additional information about the application such as endpoint definitions, installation guides, in-depth code walkthroughs, etc.

### .gitignore

Your application must have a .gitignore file where you add files and folders that can be omitted when uploading the code (such as node_modules or .env files). If needed [Toptal has your back](https://www.toptal.com/developers/gitignore)

### lint-file

If your application needs a specific set of rules when it comes to code, you can add a lint file for it. If there's no need, this can be omitted.

### Docker or docker-compose file

If your application can be containerized, you can add one or both files to the root of the repository. dockerfile to create the image and docker-compose.yml to create the container stack (if any)
