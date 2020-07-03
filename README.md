# DotNetCore-Authentication-AzureAD

Azure Active Directory + Swagger authentication + ASP.NET Core 3.1

# How settings Azure AD

Settings start with <a href="https://docs.microsoft.com/en-us/azure/active-directory/develop/howto-create-service-principal-portal#register-an-application-with-azure-ad-and-create-a-service-principal" target="_blank">`Register an application with Azure AD`</a>.

After register the application. 

Select **API permissions** use the *User.Read* (added by default) permission.

<p align="center">
  <img src="https://drive.google.com/uc?export=view&id=12VOYMMo8XFSO1nXzCWJd0CCpYb4vlJWm"/>
</p>

After select **Authentication** click the button *Add a platform*.

<p align="center">
  <img src="https://drive.google.com/uc?export=view&id=1CguP-JhR2QVVLXB34IVYz9YP0NQYARkL"/>
</p>

Next **Configure platforms** select *Web*.

<p align="center">
  <img src="https://drive.google.com/uc?export=view&id=1t5Jzh6zW1t50KuQ8GSoIwxnQbUY5I_gf"/>
</p>

Finally **Configure Web** fill in the first text box *https://localhost:44315/swagger/oauth2-redirect.html*. 

Section *Implicit grant* for web app, select *ID tokens* and *Access tokens*.

<p align="center">
  <img src="https://drive.google.com/uc?export=view&id=1r2hSHrY4Lg7ICepxQKGtUsfCO3a-egJ8"/>
</p>

For more details visit website <a href="https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-configure-app-access-web-apis#configure-platform-settings-for-your-application" target="_blank">`Configure platform settings for your application`</a>.

We have completed the Azure AD settings.

# Settings appsettings.json

In the appsettings.json find section **AzureAd**

```
"AzureAd": {
    "Instance": "https://login.microsoftonline.com/",
    "Domain": "https://login.microsoftonline.com/{tenantId}/oauth2/authorize",
    "TenantId": "{tenantId}",
    "ClientId": "{clientId}",
    "CallbackPath": "/"
}
```
Replace the *{tenantId}* to your application with azure portal.

<p align="center">
  <img src="https://drive.google.com/uc?export=view&id=1_nw5IsS1rMpElO4kPx9cp8RgSYiaSHle"/>
</p>

Replace the *{clientId}* to your application with azure portal.

<p align="center">
  <img src="https://drive.google.com/uc?export=view&id=1yRqilNG7j8zyZ_1GApUdfwlYFtKJs08S"/>
</p>

For more details visit website <a href="https://docs.microsoft.com/en-us/azure/active-directory/develop/howto-create-service-principal-portal#get-tenant-and-app-id-values-for-signing-in" target="_blank">`Get tenant and app ID values for signing in`</a>.

We have finished setting up appsettings.json.
