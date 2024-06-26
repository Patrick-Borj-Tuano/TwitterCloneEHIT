# Twitter Clone

## Repository Owner

- Each group must assign one repository owner
- The repository owner must fork this repository. Only the repository owner should fork the repository
  - This could be done by clicking the "Fork" button on the top right.
- The repository owner must invite their goupmates as collaborators in their fork
  - This could be done by going to Settings>Collaborators>Add people
- The group must use the fork to collaborate on their project. They must commit and push their code in their forks.
- The group must submit the link of the repository of the repository owner in the submission bin

## Getting Started

Follow these steps to set up and run the Twitter Clone project:

1. **Install Node.js**:
   Make sure you have Node.js installed on your system. If not, download and install it from the official website.

2. **Fork and Clone the Repository**:

   - Clone your forked repository to your local machine using Git.

3. **Install Dependencies**:

   - Open a terminal and navigate to the cloned repository.
   - Install the API dependencies by running the command:
     ```
     npm run init-api
     ```
   - Install the UI dependencies by running the command:
     ```
     npm run init-ui
     ```

4. **Run the API**:

   - Start the API server by running:
     ```
     npm run start-api
     ```
   - Visit `http://localhost:3000` in your web browser to check if the API is up and running.
   - Visit `http://localhost:3000/api/docs` in your web browser to see the documentation of the API.

5. **Run the UI**:

   - Open a new terminal window (keep the API terminal running).
   - Start the UI development server with:
     ```
     npm run start-ui
     ```
   - Visit `http://127.0.0.1:8080` in your web browser to see if the UI is working.

6. **Start Developing**:
   - Begin working on the UI in the `TwitterCloneUi` folder.
   - Add your HTML, CSS, and JS files to build the Twitter Clone interface.

Remember: **Do not modify the `TwitterCloneApi` folder**; it contains essential API code.

## Deployment

To deploy this application you need to to use netlify. See the [documentation](https://docs.netlify.com/) to see how deployments are done in Netlify.

The netlify.toml file contains nearly all the necessary values needed for deploying the application. There are no additional values needed to be set up except the JWT_KEY environment variable

## Step by step Deployment Guide

The deployment process for netlify should be straight forward, but here's a step by step guide in case you need it.

1. Make sure that your forked is synced
2. Visit [the netlify website](https://netlify.app/) and click on "Deploy to Netlify"
3. Create an account and sign up with your github profile
4. Click on the "Add new site" button and select "Import and Exisitng Project"
5. Click on "Deploy with Github". Netlify might ask for Authentication in which case you would need to allow Netlify.
6. Select your repository from the list.
7. Set the site name to your desired name.
8. The `Build command`, `Publish directory`, and `Functions directory` should be prefilled with the necessary information. If not, make sure to sync your fork and check again.
9. Click on "Deploy" and wait a couple of minutes for netlify to deploy your application. Once netlify is finished, a green tag with the text "Published" should appear in "Production Deploys"
10. Et voila, you have deployed your application 🎉 Now you need to step up the JWT_KEY

### Setting up the JWT_KEY

The JWT_KEY is used to generate the tokens and make sure that the tokens generated by the system is indeed generated by the system itself. Otherwise, attackers might be able to generate tokens themselves and compromise the system. This is why the key needs to be generated and entered manually. They must not be known to anyone but the developers.

1. To setup the JWT_KEY environment variable, you would first need to generate a secret key. You may refer to [this](https://dev.to/tkirwa/generate-a-random-jwt-secret-key-39j4) tutorial for generating a secret key
   - Once generated, your private key may look something like this `ddcb75b4f402f240234eec4bf175fa9e8c15aea5...`
2. Once you have created a secret key, you need to add your private key as an environment variable. The name of the key must be `JWT_KEY` and the value is your private key.
   - You may refer to [this](https://docs.netlify.com/environment-variables/get-started/#site-environment-variables) documentation for a tutorial on how to set environment variables in netlify

Happy coding! 🚀🐦
