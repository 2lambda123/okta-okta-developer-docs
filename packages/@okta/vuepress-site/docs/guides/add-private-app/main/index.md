---
title: Add a private SSO integration
meta:
  - name: description
    content: Use this guide to learn how to add a private SSO app integration to your Okta org.
layout: Guides
---

Use this guide to add a private, custom Single Sign-On (SSO) OIDC or SAML 2.0 integration to your Okta org. Private integrations are only used by the users of the org for which they're installed on. This guide also shows you how to test the private integration in your org.

---

**Learning outcomes**

* Learn how to add a private SSO integration to your Okta org
* Learn how to test your SSO integration in your Okta org

**What you need**

* A functional SSO integration created in accordance with the [Build a Single Sign-On integration](/docs/guides/build-sso-integration/) guide
* An Okta org (such as an [Okta Developer Edition org](https://developer.okta.com/signup))

---

## Overview

To integrate your app for Single Sign-On (SSO) with Okta, you need to first develop your app SSO integration. Then, you need to register your app with an Okta org before you can test it.

Registration involves creating an app integration instance in your Okta org to provide you with the SSO credentials or metadata for your app authentication requests. This integration is considered private because it's only available in the org from where the app integration instance was created.

> **Note:** An app integration is considered public if it's available in the Okta Integration Network (OIN) catalog for all Okta customers.

This guide assumes that you've developed your SSO integration and want to add it to your Okta org. The instructions in this guide are generic for two SSO standards:

* **OpenID Connect (OIDC)** (preferred)
* **Security Assertion Markup Language (SAML)**

> **Note:** Private integrations aren't restricted to the [OIN limitations](/docs/guides/submit-app-prereq/main/#oin-limitations). You can implement the Okta features that are available on your specific Okta org.

## Create your private integration in Okta

After you've built your SSO integration, you can use the Application Integration Wizard (AIW) in the Admin Console to create your app integration instance. This instance provides you with client credentials or metadata for your SSO flows.

> **Note:** For best practices, create two or three additional admin users in Okta to manage the integration. This ensures that your team can access the integration for updates in the future.

1. Sign in to your [developer-edition Okta org](/login/) as a user with administrative privileges.
1. Go to **Applications** > **Applications** in the Admin Console.
1. Click **Create App Integration**.

<StackSnippet snippet="create" />

<br>

> **Note:** Creating your app integration instance doesn't automatically make it available in the [OIN](https://www.okta.com/integrations/). See [Publish an OIN integration](/docs/guides/submit-app-overview/) for an overview of the submission process.

## Specify your integration settings

After you create your integration instance, the main settings page appears for your new integration in the Admin Console. Specify **General Settings** and **Sign On** options, and assign the integration to users in your org. Click **Edit** if you need to change any of the options, and **Save** when you've made your changes.

<StackSnippet snippet="settings" />

## Test your integration

This portion of the guide takes you through the steps required to test your integration.

### Assign users

First, you must assign your integration to one or more test users in your org:

1. Click the **Assignments** tab.
1. Click **Assign** and then select either **Assign to People** or **Assign to Groups**.
1. Enter the appropriate people or groups that you want to have Single Sign-On into your application, and then click **Assign** for each.
1. Verify the user-specific attributes for any people that you add, and then select **Save and Go Back**.
1. Click **Done**.

### Test Single Sign-On

1. Sign out of your Okta org. Click **Sign out** in the upper-right corner of the Admin Console.
1. Sign in to the Okta End-User Dashboard as the regular user that was assigned the integration.

   > **Note:** If you sign in as a non-admin user to your Okta org from a browser, the End-User Dashboard appears. To access the End-User Dashboard from a mobile device, see [Okta End-User-Dashboard](https://help.okta.com/okta_help.htm?type=eu&id=ext_user_dashboard_overview).
1. Click the Okta tile for the integration and confirm that the user is signed in to your app.

<StackSnippet snippet="test" />

## Next steps

After you complete testing your app integration, you can communicate to your Okta org users about the custom app SSO capability.

If you decide to publish your integration to the OIN later on:

* Review the [Publish an OIN integration](/docs/guides/submit-app-overview/) overview to understand the submission process for publishing an integration.
* Review the [OIN submission requirements](/docs/guides/submit-app-prereq/) before starting the submission process.
* Use the [OIN Manager: Submit an advanced SAML integration](/docs/guides/submit-sso-app/saml2/main/) guide to submit advanced SAML integrations to the OIN.
* For OIDC or basic SAML integrations, use the [OIN Wizard: Submit an SSO integration](/docs/guides/submit-oin-app/saml2/main/) guide, which is a more streamlined way to test and submit your integration to the OIN.

## See also

<StackSnippet snippet="see-also" />