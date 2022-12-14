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
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;- addon-ember-client-gamechanger  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;- schematic-angular-client-gamechanger  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;- documentation-gamechanger  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;- easygraphql-parser-gamechanger  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;- generator-aws-server-gamechanger  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;- generator-aws-server-typeorm-gamechanger  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;- generator-react-client-gamechanger  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;- graphiql-gamechanger  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;- schematic-nest-server-gamechanger  

These projects can be grouped in four categories. The ones responsible for generating the client side, those reponsible for generating the server side, the graphiql and the documentation, responsible for this website. We will now take a look at the first three categories.

## Client-side generators

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Each repository of this category is a generator of a client-side according to a certain front end technology. As you can see, three of the most common and used front-end frameworks can be used to generate the client-side of your application: Ember, React and Angular. The naming of the latter is quite different from its peers as the technology used to generate its files is different. Infact, the project angular-client-gamechanger uses an Angular schematic while the two others use yeoman. This choice of change was made as the community of the yeoman generator technology seems less and less active.  

The next projects for this side of the GameChanger solution would thus be to :  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;1. conceive a [fourth client side generator](/_pages/client-generator-based-on-vuejs)
, which would be base on an Angular schematic for the generation of the files and Vue.js as the front-end framework  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;2. [change the projects based on yeoman](/_pages/from-yeoman-to-angular-schematic/) so that they would instead use an Angular schematic  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;3. work on the generator based on Ember to [bring it up to date](/_pages/update-the-generator-based-on-ember/) as it was implemented a long ago.

## Server-side generators

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;As its name suggests, this category of generators is in charge of the client side of your application. At the moment, you can generated the server-side of your application with to two back-end technologies: NestJS and AWS server. The two server-sid will be using an AWS lambda as well as an RDS Base howerver the first is based on graphql and defines the graphql API using NestJS meanwhile the second also uses AWS for the API and is base on SQL. Finally, as it was the case for the client side, the naming is dirrefent for the two generator as they respectively use an Angular Schematic and Yeoman.  

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;As a matter of fact, the repository generator-aws-server-typeorm-gamechanger was made to generate the server-side using NestJS ans graphql but was abandonned as it was using Yeoman.

## GraphiQL ??? choix pour server-side, nest ou aws ???

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;The GameChanger GraphiQL is kind of a GraphQL Playground which also serve as the interface for generating your fullstack application. Once provided with a graphql schema (which is optional) and a choice for the client-side technology, it will generate a script that you will have to execute to generate your whole application.

## Parser