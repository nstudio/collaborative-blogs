## Add Applitools to any web app in Nx with xplat

[Applitools](https://applitools.com/) is a powerful visual testing tool that can automatically run tests at scale across every app, browser, OS, and screen size.

[xplat](https://nstudio.io/xplat/) is a set of Angular schematics designed to help you build large cross platform applications inside an [Nx](https://nx.dev/) monorepo workspace.

One of the many challenges in building large cross platform applications which could be deploying to many different types of devices (browsers, mobile phones, TV's, watches, etc.) is testing them. In a monorepo like Nx we can share a lot of code across many of these applications. Changes to any shared libraries in the codebase can at anytime adversely affect the ability to deploy to any of the targeting devices. We want to detect these changes quickly and readily.

## xplat-helper

Recently we introduced a new generator called `xplat-helper` in our tooling meant to deliver a growing number of various helpers to large cross platform codebases in Nx.

We're excited to show you one of the new ones today. It's specifically designed to add Applitools tooling to any web app configured with [Cypress](https://www.cypress.io/) right away.

```
ng generate xplat-helper applitools --target=web-myapp
```

With one command we have now configured a web app to use Applitools for visual testing.
The `--target` argument can specify any web app name within your `apps` folder in the workspace.

You can now run your e2e tests the same way you're used to: `ng e2e`
However now it will also communicate with Applitools for advanced and powerful visual testing.

After running the command, you will see a note at the top which mentions:
```
Ensure your APPLITOOLS_API_KEY environment variable is set: https://applitools.com/tutorials/cypress.html#step-by-step-guide-run-the-demo-app
```

Be sure to setup your environment variable to get a successful connection.

## What's Next? 

We're working through details to make this work the same way for [NativeScript](https://www.nativescript.org/) apps as well as other integrations.

In fact the `xplat-helper` generator is also what can be used to simplify your NativeScript import paths as [detailed here](https://nstudio.io/blog/say-hello-to-scoped-nativescript/).

Expect to see more helpful options introduced with the `xplat-helper` in the future. 

Here's just a few we are planning (Not available yet! but in progress):

* `ng g xplat-helper firebase --platforms=web,nativescript`

    > Quickly add a seamless shared setup for firebase across Web and NativeScript.

* `ng g xplat-helper travis --platforms=web,nativescript` 

    > Fully operational and configurable Travis CI scripting for automated deployments for Web and NativeScript.

* `ng g xplat-helper storage --platforms=web,nativescript` 

    > Nice and tidy shared storage handling for seamless Web and NativeScript.
