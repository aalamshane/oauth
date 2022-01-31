# oauth2
To enable this project to work you will need to do the following
1. Create a GitHub Oauth app
    - Login to GitHub
    - select your user avatar in the upper right corner
    - choose ***Settings*** 
    - choose ***Developer settings*** (near the bottom)
    - choose ***OAuth apps***
    - click on ***New OAuth App*** button
    - use these values
      - Application name: SSO - docker SSL
      - Homepage URL: https://localhost:7083/lsso-client
      - Authorization callback URL: https://localhost:7083/lsso-client/login/oauth2/code/github
    - click on ***Register application*** button
    - click on ***Generate a new client secret*** button
2. Copy the GitHub client ID and secret to the env file
3. Build the Spring application with ***mvn clean package*** 
4. Copy the Spring output jar from ***\target*** to ***\infrastructure\app\app***.  No need to rename it as that will be done by the Docker file.
5. from the *Infrastructure* directory
    - docker compose build
    - docker compose -p social up
6. In your browser https://localhost:7083/lsso-client/
