---
# the default layout is 'page'
order: 1
icon: fa fa-question-circle
title: What is GameChanger ?
---

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;GameChanger is a development platform which aimsto quickly generate, develop, & deploy fully Cloud compliant applications & infrastructure, using GraphQL as entry point.
By using GameChanger, you can easily generate a full project, with both server and client sides, by simply passing 
a graphql schema to its graphiql interface and selecting which technologies to use for the client side.

Let us dive in the several repositories of GameChanger Cloud to better understand which technologies are available and which are their purposes.

The GameChanger organisation manages 8 repositories :   
*  [addon-ember-client-gamechanger](https://github.com/GameChangerCloud/addon-ember-client-gamechanger)  
*  [schematic-angular-client-gamechanger](https://github.com/GameChangerCloud/schematic-angular-client-gamechanger)  
*  [easygraphql-parser-gamechanger](https://github.com/GameChangerCloud/easygraphql-parser-gamechanger) 
*  [gamechangercloud.github.io](https://github.com/GameChangerCloud/gamechangercloud.github.io)   
*  [generator-aws-server-gamechanger](https://github.com/GameChangerCloud/generator-aws-server-gamechanger)    
*  [generator-react-client-gamechanger](https://github.com/GameChangerCloud/generator-react-client-gamechanger)  
*  [graphiql-gamechanger](https://github.com/GameChangerCloud/graphiql-gamechanger)  
*  [schematic-nest-server-gamechanger](https://github.com/GameChangerCloud/schematic-nest-server-gamechanger)  

These projects can be grouped in five categories. The ones responsible for generating the clients ide, those reponsible for generating the server side, the graphiql, the parser and the documentation, responsible for this website. We will now take a look at the first four categories.

## Client side generators

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Each repository of this category is a generator of a client-side according to a certain front-end technology. As you can see, three of the most common and used front-end frameworks can be used to generate the client-side of your application: Ember, React and Angular. The naming of the latter is quite different from its peers as the technology used to generate its files is different. Infact, the project angular-client-gamechanger uses an Angular schematic while the two others use yeoman. This choice of change was made as the community of the yeoman generator technology seems less and less active. 

However, only the one based on Angular is operational, as the others have to be refactored to use an Angular Schematic.


## Server side generators

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;As its name suggests, this category of generators is in charge of the server side of your application. Before, you could generate the serverside of your application with a back-end based on AWS server. Now, the server side of your generated application is based according to NestJS, a back-end framework. The two server-side use an AWS lambda as well as an RDS Base howerver the second is based on graphql and defines the graphql API using NestJS whereas the first also uses AWS for the API and is based on SQL. Finally, as it was the case for the client side, the naming is different for the two generator as they respectively use an Angular Schematic and Yeoman.  

## GraphiQL

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;The GameChanger GraphiQL is kind of a GraphQL Playground which also serve as the interface for generating your fullstack application. Once provided with a graphql schema and a choice for the client-side technology, it will generate a script that you will have to execute to generate your whole application.

## Parser

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;The repository easygraphql-parser-gamechanger is at the core of GameChanger. In fact, it defines the package responsible for interpreting the provided graphql schema, converting it into an array of types and enhancing this array with additionnal informations about the fields, the types and the relationships they have with each other.

