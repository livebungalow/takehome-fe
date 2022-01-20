# Bungalow Frontend Take Home Assessment

### Overview
The following technical challenge is intended to evaluate stylistic decisions in both the code you write, and the way you think about UI/UX. The work you do here is meant to emulate a development experience you might have on any given day working on our engineering team. In that spirit, you may ask any questions along the way that you would ask if you were working beside us as a team member.

**In this project, you will create a small app that allows a user to see properties (and it’s details) in various markets.**

At Bungalow, we primarily use [Vue](https://vuejs.org/) for our frontend, with many projects implementing [Nuxt](https://nuxtjs.org/) as well, which is a framework layer on top of Vue (similar to what NextJS is for React). It provides additional structure, tooling and automation to improve the developer experience.

### Requirements
1. **Clone and build the take home project**
* Clone this public repo: https://github.com/livebungalow/takehome-fe
* Run the following command(s) to build the project and get started:

```bash
# Builds and runs the project:
npm install && npm run serve
```

* Once the project is up and running you should be able to visit https://localhost:8080 to view it!
* If you like, you can add Vuetify to the project to add out-of-the-box designed components that look great and speed up development (we use this, and recommend it) - you can check out how to install it here.
* 🚨  Important: CORS whitelists in our APIs will require you to use localhost:8080 for your app!
  * We strongly recommend using the default Vue CLI configuration when creating project, since this should be set up out of the box!

2. **Implement a UI to achieve the acceptance criteria provided.**
* Review the acceptance criteria provided below, and create an interface to achieve it to the best of your ability/understanding. Other that the fact the properties should be cards/tiles in a grid, there are no other design constraints.
* To achieve the goal, you’ll need to ingest the Markets and Listings APIs referenced below to pull a list of available markets, and then properties to display within a given market.

3. **Fill in the FEEDBACK.md file within the project**
* We’ve added a README file to your project named FEEDBACK.md that you can use to capture any additional commentary, assumptions you made or any instructions for those reviewing the project.
* You can also discuss any additional features you would implement given extra time or things you wanted to do but didn’t get to, this helps us understand your thought process!
  
4. **Add the project to Github**
* Add your project to Github so that it can be easily shared with us, if you need to make the repo private, send an invite to engineering@bungalow.com to give us access.

### Acceptance Criteria
_As a user..._
* I want to be able to visit the app and be presented with available markets for me to choose from.
* Once I choose a desired market, I want to be taken to a list of available properties in that market.
* The properties should be displayed as tiles/cards in a grid – and should provide relevant details about properties at a glance that would be valuable to someone looking to find a place to live

### API Docs
* Markets API (GET)
  Returns a list of available markets, the slug from a given market can be used in the Listings API
  Example URL: https://stage-fieldstone.bungalow.com/api/v1/markets/

* Listings API (GET)
  Returns all of the available properties for a given market, accepts marget__slug as a query param.
  Example URL: https://stage-fieldstone.bungalow.com/api/v1/listings/properties/?market__slug=seattle

You can see more detail on these public APIs in our documentation here.

### Expectations
Our expectations are for you to spend ~2 hours on this, with the results will be evaluated accordingly. In your project please provide README file with any additional commentary you want to provide, assumptions you have made, or any next steps you would’ve taken given more time.

In summary:
* We don’t expect you to spend more than 2 hours working on this, we’ll grade it as such
* Add the work to a GitHub repo (private or public - whatever you need) then invite us to the project.
* Please ask any questions if you need help or clarification, just like you would in a real world scenario
* Document your thoughts, findings and instructions for us so that we can review and discuss them with you in a follow up call!

### Extra Credit
Having fun? Feeling inspired? Here are a couple of extra items that you could explore if you’re interested. If you don’t have time, feel free to jot down some notes in the README about what you would do, given time!
* Filtering and sorting of the property cards
* Mobile first design/responsiveness
* Pagination for larger markets
* Anything we missed?

---

#### Project Scripts & Commands
```bash
npm install    # Project setup
npm run serve  # Compiles and hot-reloads for development
npm run build  # Compiles and minifies for production
npm run lint   # Lints and fixes files
```
#### Customize Vue's Configuration
See [Configuration Reference](https://cli.vuejs.org/config/).

