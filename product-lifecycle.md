---
Audience: Product developers
---

# Product lifecycle

CreatorHub enables you to specify various product details and request AdHoc context data. The configuration you specify in CreatorHub takes effect when users interact with your product in AdHoc.

This page guides you through the lifecycle of new products, from CreatorHub to AdHoc, aiming to help you make informed choices during product development and onboarding.

> **Reminder:** We use the term _product_ to identify apps, tools, datasets, and APIs you can develop for AdHoc. For more details, [refer to Product as a concept](https://dummy-link.com).

The following diagram illustrates the product lifecycle in the [Onboarding](#onboarding), [Adoption](#adoption), [Contextualization](#contextualization), and [Launch](#launch) stages.

![](./images/product-lifecycle/adhoc-product-lifecycle.svg)

> **Note:** Your product goes through a simplified version of this lifecycle every time you update its configuration in CreatorHub.

## Onboarding

The following table describes the key system involved in Onboarding.

| **System** | **Purpose**                                                                                                                                           |
| ---------- | ----------------------------------------------------------------------------------------------------------------------------------------------------- |
| CreatorHub | Entry point for product configuration and marketing. [Refer to Configure and market products in CreatorHub](https://dummy-link.com) for more details. |

When onboarding a product, you specify its configuration and marketing details in CreatorHub:

- **Product configuration**: General parameters, requirements for AdHoc context data, user authorization, and tenant availability.
- **Marketing details**: Snapshot details, features and highlights, training materials, and contact points.

Once you've successfully onboarded a product, the CreatorHub API makes the product details available to App Market and the Navigation and Orchestration services.

Following this, your product transitions to the Adoption and Contextualization stages.

## Adoption

The following table describes the key system involved in Adoption.

| **System** | **Purpose**                                                                                                                                 |
| ---------- | ------------------------------------------------------------------------------------------------------------------------------------------- |
| App Market | A tenant-agnostic catalog that offers comprehensive product overviews, highlighting their features, training materials, and contact points. |

During Adoption, AdHoc users can browse App Market and request your product through their tenant admins. Then, based on your product's specifics, the tenant admin can ask your team to make the product available to their tenants or discuss adjusting your product configuration to fit their tenant requirements for user access, specific markets, etc.

Once your team and the tenant admin agree on the terms, you can make your product available in CreatorHub for that specific tenant. AddHoc records the change in availability in the target Tenant Config.

## Contextualization

The following table describes the key systems involved in Contextualization.

| **System**            | **Purpose**                                                                                                                                                                                   |
| --------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Navigation Service    | Maintains tenant navigation and extends the product configuration with navigation-specific AdHoc context. [Refer to Tenant navigation](https://dummy-link.com) for more details.              |
| Orchestration Service | Maintains project workflows and phases and extends the product configuration with project-specific AdHoc context. [Refer to Projects and workflows](https://dummy-link.com) for more details. |
| Config Service        | Creates product instance boilerplates that contain the product configuration and required AdHoc context.                                                                                      |
| Tenant Config         | Contains tenant-specific product instances with finalized requirements for navigation, project requirements, and user access.                                                                 |

During Contextualization, your product goes through several processing stages to receive the necessary AdHoc context and align its configuration with the target tenant's requirements.

> **Tip:** [Refer to Available AdHoc context](https://dummy-link.com) to learn what context variables you can request during onboarding to develop highly specialized products.

First, the Navigation and Orchestration services process the AdHoc context requirements:

- Navigation Service processes the navigation requirements to ensure that tenant admins can add your product to the appropriate tenant navigation levels.

- Orchestration Service processes the project requirements to ensure that users can add your product to the appropriate project workflows and phases.

Then, Config Service does the following:

1. Combines Navigation and Orchestration outputs with the user authorization requirements, creating a product instance boilerplate.

   This boilerplate fulfills the navigation and orchestration context requirements and preserves other requirements (general parameters, user authorization, and tenant availability) as is.

2. Processes the tenant availability requirements to select Tenant Configs for tenants with access to your product.
3. Checks the product instance boilerplate against the target Tenant Config and adds a tenant-specific product instance to that Tenant Config if the boilerplate aligns with the tenant requirements.

   > **Note:** If the product instance boilerplate doesn't agree with the target Tenant Config, you will receive a detailed report in CreatorHub to help you adjust the product configuration.

Following this, the tenant-specific instance of your product is always ready to Launch from AdHoc.

## Launch

The following table describes the key system involved in Launch.

| **System** | **Purpose**                                                                                                                 |
| ---------- | --------------------------------------------------------------------------------------------------------------------------- |
| Base App   | Part of the AdHoc interface that verifies user credentials and makes tenant-specific product instances available to launch. |

While your product remains in the Launch stage, the authorized tenant users can continuously interact with it from the tenant navigation and within specific project workflows and phases.

When a user opens your product in AdHoc, Base App processes their credentials to launch the product with the access level tailored to that user's authorization level.

> **Tip:** [Refer to the AdHoc Authz docs](https://dummy-link.com) for more details on how you can govern user authorization in AdHoc.

## Next steps

Now that you understand how AdHoc processes the product configuration and marketing details you specify in CreatorHub, continue exploring our docs or [pick one of our Product boilerplates](https://dummy-link.com) and [start developing your first product](https://dummy-link.com).
