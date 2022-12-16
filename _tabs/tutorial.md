---
# the default layout is 'page'
order: 2
icon: fa fa-book
---

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Before thinking about using GameChanger Cloud you need to have a correct GraphQL schema and install a few dependencies which are required for the next steps. We consider that Node.js is installed on your machine.

## GraphQL Schema

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;The generation of your application is based on a GraphQL schema. Keep in mind that GraphQL has a few particularities. It is based on a system of types and fields. Each entity is described by a type and its attributes by fields. For example, if you want to define a Developer entity with an id, a firstname, a lastname and a list of names of projects, your schema should looks like this:

```graphql
type Developer {
    id: ID!
    firstname: String!
    lastname: String!
    projects: [String]
}
```
Let's take a look at the above code to have a better understanding :

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`Developer` is a GraphQL Object types that represents your entity.
`id`, `firstname`, `lastname`, and `projets` are fields which represent attributes.
`String` is the scalar type. GraphQL provides some default scalars but you can also  add new scalar types provided by GameChanger Cloud, we will talk about that later.
The exclamation point (`!`) states that tha concerned field is non-nullable.
`[String]` means that the field as to be a list of scalar of type `String`. 

>You can turn your list or its content non-nulable using the "`!`"
{: .prompt-tip }

### Scalar types

By default, GraphQL provides a set of scalars:

*  `Int` a signed 32-bit integer.
*  `Float` a signed double-precision floating-point value.
*  `String` a UTF-8 character sequence
*  `Boolean` true or false
*  `ID` represents a unique identifier, used to fetch an object or as key for a cache.  

GameChanger use these but also provides its own set of scalars :

*  ObjectID
*  Date
*  Time
*  DateTime
*  UtcOffset
*  NonPositiveInt
*  PositiveInt
*  NonNegativeInt
*  NegativeInt
*  NonPositiveFloat
*  PositiveFloat
*  NonNegativeFloat
*  NegativeFloat
*  UnsignedFloat
*  UnsignedInt
*  BigInt
*  Long
*  EmailAddress
*  URL
*  PhoneNumber
*  PostalCode
*  GUID
*  HexColorCode
*  HSL
*  HSLA
*  RGB

If you want to use custom scalars provided by GameChanger Cloud you must specify them at the begining of your schema. If we take the Developer exemple described before and we want him to have a `birthday` attribute of type Date, your schema should look like this:

```graphql
scalar Date

type Developer {
    ...
    birthday: Date
}
```

## Installation
### Angular CLI and generators

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;The Command-Line Interface (CLI) of Angular is required to run the generators which are based on an Angular Schematic. To install it globally with npm, use the following command :

```bash
npm install -g @angular/cli@latest
```
You can verify that this package was installed successfully with the command :

```bash
@angular/cli --version
```
You will then have to install the generators for the front and back end of your application. 
First create a dedicated directory for GameChanger Cloud.

```bash
mkdir GameChangerCloud
cd GameChangerCloud
```
You can then initialize a parent project for schematics (answers to questions are not important) and install your schematics.

```bash
npm init
```
For the back-end, run:

```bash
npm install schematic-nest-server-gamechanger@latest
```
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;For the front generator you can choose the generator depending on the frontend framework you want to use. The front-end based on Angular is the only one available at the moment (the others have to be switched [from yeoman to angular schematic](/contributing/from-yeoman-to-angular-schematic/)). To download it, run the following:

```bash
npm install schematic-angular-client-gamechanger@latest
```
>If you prefer yarn, you can run the commands using `yarn add` and `yarn global add`.
{: .prompt-tip }

### AWS CLI

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;The AWS Command Line Interface (AWS CLI) is an open source tool that enables you to interact with AWS services. Obviously you’ll need an [AWS account](https://portal.aws.amazon.com/billing/signup#/start/email). To install it you can follow the [documentation](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html).

All set ! Now you have a choice for the next steps. You can either generate your front-end and back-end separately or all at once with [GameChanger Cloud GraphiQL](#generating-an-application-using-graphiql). We will first see how to generate the beck-end on its own and then generate the whole application.

## Generating and deploying a project manually

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;We will generate a NestJS Server side to understand how it works.
First, you have to copy your GraphQL schema in your GameChanegr Cloud directory and launch the generation. You will be asked to name the project you want to generate and set the name and extension of your schema.

```bash
cp <path to graphqQL file> .
schematics schematic-nest-server-gamechanger:generate
```
Once the files are created you can go to your server directory, install node artefacts and control your server. Do not forget to start a Postgres database (your can use a docker to do so).

```bash
cd <generated server>
npm i --production
nest start
```
>For the client-side, run `ng serve` instead of nest start
{: .prompt-tip }

Your server is running ! Last step is to deploy it to AWS:

```bash
export AWS_DEFAULT_REGION=eu-west-1
cd terraform
terraform init
terraform apply -var-file="terraform.tfvar"
```
>Make sure to set your region as the value of AWS_DEFAULT_REGION
{: .prompt-tip }

## Generating an application using GraphiQL

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Finally you need to clone the github repository of GameChanger Cloud [GraphiQL](https://github.com/GameChangerCloud/graphiql-gamechanger) which is its main entrance. Your data model will then be defined in this client application.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Once everything is downloaded, we are ready to launch GameChanger Cloud and generate your application ! 

To start you’ll have to go to the directory of the client application you cloned just before and run it.

```bash
cd graphiql-gamechanger
npm run start
```
Your application should be running on http://localhost:3000/.

Now that your application is running, you can observe three main parts on your browser. The left part is the GraphQL editor, this is where you will be defining your data model. On the right part, you can see your model in UML format. Being able to visualize your model is the best way to avoid mistakes! Finally, on the top, you can see the different actions you can do as a user.

You will then have to define your schema in the GraphQL editor. In this editor you can define your entities and queries.

### Menu
On the top menu, there are a few actions you can execute.

*  The **Prettify** button allows you to format your code  
*  The **History** button provides a list of the previous models you defined  
*  The **Explorer** button  
*  The **Generate** button is the one we are interested in to generate our application. You’ll have to chose a name for your application, choose the Javascript framework you want to work with and if you want random samples of data. This will generate a _bash script_.  
The name must be **between 2 and 15 letters**, in **lowercase** and **without the aws word**
*  The **Configure** button

### Application generation

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;You have defined the model of your dream ? You have generated your bash script ? You are now ready to generate your final application skeleton !

All you need to put the bash script in a dedicated folder and execute it.
>If you are on windows you can use the git bash CLI
{: .prompt-tip }

You should see the generation in your processing in your terminal. It takes few minutes to generate.

Your application is ready ! You can now focus on putting your idea into code.

NB: For now, the generation of the project has to be done once the graphql schema is set and will not be modified. One of GameChanger Cloud's next steps would be to [support incremental generation](/contributing/support-incremental-generation/). By doing so, the graphql schema could be modified, the generation could be redone and only the files which have to be modificated would be changed instead oh having to regenerate everything all over again.