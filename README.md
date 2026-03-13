# AzRemote Redirect Static Web App

This static site is deployed to Azure Static Web Apps (or any static host) and immediately redirects visitors from `https://azremote.accessit.online` to the Azure Virtual Desktop web client at `https://client.wvd.microsoft.com/arm/webclient`.

## Files

- `index.html` &mdash; the landing page with an instant meta refresh and JavaScript redirect, plus a manual fallback link.
- `staticwebapp.config.json` &mdash; configures an HTTP 302 redirect for every request when running on Azure Static Web Apps.

## Local testing

You can verify the redirect before deploying using any static file server, for example:

```bash
cd Azure/AzRemoteRedirect
npx serve .
```

Then open `http://localhost:3000` and confirm you are forwarded to the Azure Virtual Desktop URL.

## Deployment

Publish this folder as the app source in your Azure Static Web App workflow (or drag/drop via the VS Code Azure Static Web Apps extension). Custom domains such as `azremote.accessit.online` must be configured in the Azure portal once the app is deployed.
