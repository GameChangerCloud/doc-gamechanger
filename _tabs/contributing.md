---
# the default layout is 'page'
icon: fa fa-users
order: 3
---

# Want to contribute to GameChangerCoud ?

GameChanger remains a work in progress, contributors are more than welcome. You can contribute to the following projects or suggest improvements through our [contact form](/contact/). 

## How can I contribute to Gamechanger ?
### Reporting bugs

To report a bug, please create an issue on github of the concerned repository and follow the guidelines below.

Please provide the steps to reproduce your problem and, if possible, a full reproducible environment.

*  Explain with a simple sentence the expected behavior  
*  Project version: e.g 1.0.17  
*  GraphQL Schema & Query: e.g gist, pastebin or directly the query
*  Is it a regression from a previous versions? e.g Yes|No
*  Stack trace

### Suggesting enhancements

A feature is missing from the GraphQL Specification?
A part of the project could be improved?

Do not hesitate to ask a new feature or join in and send us a pull request with your own feature!

Before coding anything, make sure to:
*  Stage 1 - Proposal : Propose your changes/ideas through an issue (optional)
*  Stage 2 - Draft : Push your code & create a pull-request with the WHY of your work.
*  Stage 3 - Candidate : Stable code, tested & documented.
*  Stage 4 - Congrats ! Your code is merged and available.

### Pull Requests

Before submitting your pull-request, make sure the following is done.
*  Fork the repository and create your branch from master so that it can be merged easily.
*  Make sure all of the significant new logic is covered by tests.
*  Make sure all quality checks are green.

The next steps for GameChanger would be to :
*  conceive a [fourth client side generator](/contributing/client-generator-based-on-vuejs), which would be based on an Angular schematic for the generation of the files and Vue.js as the front-end framework  
*  [change the projects based on yeoman](/contributing/from-yeoman-to-angular-schematic/) so that they would instead use an Angular schematic  
*  work on the generator based on Ember to [bring it up to date](/contributing/update-the-generator-based-on-ember/) 
* [update the front-end and back-end generators](/contributing/make-generators-function-with-additional-scalars) so that would function with geographical and custom scalars
*  [support incremental generation](/contributing/support-incremental-generation/)

