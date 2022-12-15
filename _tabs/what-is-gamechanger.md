---
# the default layout is 'page'
order: 1
icon: fa fa-question-circle
title: What is GameChanger ?
---

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;GameChanger is a development platform to quickly generate, develop, & deploy fully Cloud compliant applications & infrastructure, using GraphQL as entry point.
By using GameChanger, you can easily generate a full project, with both server and client side, by simply passing 
a graphql schema to its graphiql interface and slecting which technologies to use for the each side.

Let us dive in the several repositories of GameChanger Cloud to better understand which technologies are available.

The GameChanger organisation manages 9 repositories :   
*  [addon-ember-client-gamechanger](https://github.com/GameChangerCloud/addon-ember-client-gamechanger)  
*  [schematic-angular-client-gamechanger](https://github.com/GameChangerCloud/schematic-angular-client-gamechanger)  
*  [gamechangercloud.github.io](https://github.com/GameChangerCloud/gamechangercloud.github.io)  
*  [easygraphql-parser-gamechanger](https://github.com/GameChangerCloud/easygraphql-parser-gamechanger)  
*  [generator-aws-server-gamechanger](https://github.com/GameChangerCloud/generator-aws-server-gamechanger)  
*  [generator-aws-server-typeorm-gamechanger](https://github.com/GameChangerCloud/generator-aws-server-typeorm-gamechanger)  
*  [generator-react-client-gamechanger](https://github.com/GameChangerCloud/generator-react-client-gamechanger)  
*  [graphiql-gamechanger](https://github.com/GameChangerCloud/graphiql-gamechanger)  
*  [schematic-nest-server-gamechanger](https://github.com/GameChangerCloud/schematic-nest-server-gamechanger)  

These projects can be grouped in four categories. The ones responsible for generating the client side, those reponsible for generating the server side, the graphiql and the documentation, responsible for this website. We will now take a look at the first three categories.

## Client-side generators

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Each repository of this category is a generator of a client-side according to a certain front end technology. As you can see, three of the most common and used front-end frameworks can be used to generate the client-side of your application: Ember, React and Angular. The naming of the latter is quite different from its peers as the technology used to generate its files is different. Infact, the project angular-client-gamechanger uses an Angular schematic while the two others use yeoman. This choice of change was made as the community of the yeoman generator technology seems less and less active.  

The next projects for this side of the GameChanger solution would thus be to :  
1.  conceive a [fourth client side generator](/contributing/client-generator-based-on-vuejs), which would be based on an Angular schematic for the generation of the files and Vue.js as the front-end framework  
2.  [change the projects based on yeoman](/contributing/from-yeoman-to-angular-schematic/) so that they would instead use an Angular schematic  
3.  work on the generator based on Ember to [bring it up to date](/contributing/update-the-generator-based-on-ember/) as it was implemented a long ago.
4. [update the front-end and back-end generators](/contributing/make-generators-function-with-additional-scalars) so that would function with geographical and custom scalars.

## Server-side generators

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;As its name suggests, this category of generators is in charge of the client side of your application. Before, you could generate the server-side of your application with a back-end based on AWS server. Now, the server-side of your generated application is based according to NestJS, a back-end framework. The two server-side use an AWS lambda as well as an RDS Base howerver the second is based on graphql and defines the graphql API using NestJS whereas the first also uses AWS for the API and is based on SQL. Finally, as it was the case for the client side, the naming is dirrefent for the two generator as they respectively use an Angular Schematic and Yeoman.  

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;As a matter of fact, the repository generator-aws-server-typeorm-gamechanger was made to generate the server-side using NestJS ans graphql but was abandonned as it was using Yeoman.

## GraphiQL

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;The GameChanger GraphiQL is kind of a GraphQL Playground which also serve as the interface for generating your fullstack application. Once provided with a graphql schema and a choice for the client-side technology, it will generate a script that you will have to execute to generate your whole application.

## Parser

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;The repository easygraphql-parser-gamechanger is at the core of GameChanger. In fact, it defines the package responsible for interpreting the provided graphql schema, converting it into an array of types and enhancing this array with additionnal informations about the fields, the types and the relationships they have with each other.

