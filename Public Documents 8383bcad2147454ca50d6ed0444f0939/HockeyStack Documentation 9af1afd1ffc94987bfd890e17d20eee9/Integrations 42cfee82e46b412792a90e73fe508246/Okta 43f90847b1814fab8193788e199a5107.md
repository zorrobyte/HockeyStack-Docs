# Okta

# Okta and Hockeystack Integration

Hockeystack integrates with Okta using Single Sign-On (SSO) to provide secure and streamlined access for users. To set up this integration, follow these steps:

## Create Okta OIDC App Integration

1. [Go to the Okta Help Center and read the guide on how to create an Okta OIDC app integration.](https://help.okta.com/en-us/content/topics/apps/apps_app_integration_wizard_oidc.htm)
2. When setting up your Okta OIDC app integration, use the following settings:
    - Select OIDC as the Sign-in method.
    - Select Web application as the Application type.
    - Set up the following parameters:
        - **Name**: The name of your application.
        - **Sign-in Redirect URIs**: [https://hockeystack-production.us.auth0.com/login/callback](https://hockeystack-production.us.auth0.com/login/callback)
        - **Trusted Origins**: [https://hockeystack.com](https://hockeystack.com/)
3. Okta will generate a Client ID and Client Secret for your app integration. Make sure to record these.
4. Add users to the Okta app integration: Users need to be in the Okta application and have a HockeyStack account to be able to log in.

## Share Client ID and Client Secret with Hockeystack Team

Once you have set up the Okta app, please share the Client ID and Client Secret with the HockeyStack Team. They will complete the setup and enable SSO for your organization.