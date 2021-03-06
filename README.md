
<p  align="center">
<a  href="http://nestjs.com/"  target="blank"><img  src="https://nestjs.com/img/logo_text.svg"  width="320"  alt="Nest Logo" /></a>
</p>

  

[circleci-image]: https://img.shields.io/circleci/build/github/nestjs/nest/master?token=abc123def456

[circleci-url]: https://circleci.com/gh/nestjs/nest

  

<p  align="center">A progressive <a  href="http://nodejs.org"  target="_blank">Node.js</a> framework for building efficient and scalable server-side applications.</p>

  

**Technology Used:** Nest.js, MongoDB, Typescript

  

**Nest.js Version**: v8

**Entry File:**

  

The project starts from **src/main.ts** file where the server starts and module definition and database connection is initialized in the **src/app.module.ts** file.



**API structure:**

  

For each API there is going to be a **module** and these modules should be included in **imports** section in the **src/app.module.ts**. To handle user’s request each module should contain at least a single **controller** or multiple **controller** files and to process the response there should be at least a single **service** or multiple **service** files. To interact with the database there should be a **repository** file.

  

So, basically for each API the flow will be 
```
. └── project/
	 └── module/
		 ├── controller 
		 ├── service 
		 └── repository
```


## Folder Structure For user’s API

Module:
```
. └── project/
	  └── src/
		 └── users/
			 └── users.module.ts**
```
  


Controller 
```
. └── project/
	  └── src/
		  └── users/
			  └── controllers/
				  └── users.controller.ts
```
  
Service -> 
```
project
. └── project/
	  └── src/
		  └── users/
			  └── services/
				  └── users.service.ts
```



Repository -> 
```
. └── project/
	  └── src/
		  └── users/
			  └── repositories/
				  └── users.repositories.ts
```

  


## Folder introduction:

  

**Controllers:** It contains all the controller files for the API and the controller’s testing files.



**Decorators:** It contains the custom decorators to use in the controller’s API endpoint.



**DTO:** It contains the Data transfer object files which are used to define data object and can also apply validation using **class-validators**.



**Entities:** It contains the entity file to define how the data should be stored in the database.


**Enums:** It contains the enum files to define the options.



**Guards:** It contains the guard files in here **jwt.guard.ts** to authorize the user strategy file in here **jwt.strategy.ts** to authenticate the provided json-web-token while any user logs in.



**Interfaces:** It contains the interface file which defines what the jwt payload should contain.



**Repositories:** It contains the repository file to interact with the database.



**Services:** It contains the service file to process the response of the processed request from controller file and the testing of service files.



**Authentication:** We are using jwt based authentication using **passport-jwt** package.



## Documentation:

  

For generating YAML documentation we are using **swagger** package which is defined in the **src/main.ts** file.

  

## Testing:

  

For unit testing we are using **nestjs/testing** package.


## Logging:

  

For logging we used nestjs bulit in logger instance from **nestjs/common** package.

  

## Run project:

  

After cloning you should type in terminal:

  

    npm install

  

To start the project in developer’s watch mode you should type:

  

    npm run start:dev

  

To start the project in production mode you should type:

  

    npm run start:prod


## Running in docker

simplest command to run it in docker is 

```
docker-compose -f docker-compose.yml up --build
```

to start dev container and start it immediately

> but, if you find any  error regarding bcrypt, then delete the
> container and image, go to project folder and delete **dist** and
> **node_modules** folder and then run this command again. Hope it will solve your issue, but if you face any further issue, please contact
> me.

To run the container instance:

    docker start nestjs_api_dev

`nestjs_api_dev` is the container name

To stop the container instance

    docker stop nestjs_api_dev
