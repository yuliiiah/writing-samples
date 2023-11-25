---
Audience: Product developers
---

# Product lifecycle

During product onboarding, CreatorHub offers you to provide various product details and request AdHoc context variables. The configuration you specify in CreatorHub takes effect when users interact with your product in AdHoc.

This page guides you through the product lifecycle from CreatorHub to AdHoc, aiming to help you make informed choices when developing and onboarding new products.

> **Reminder:** We use the term _product_ to identify apps, tools, datasets, and APIs you can develop for AdHoc. For more details, [refer to Product as a concept](https://dummy-link.com).

The following diagram illustrates the product lifecycle with the onboarding, adoption, contextualization, and launch stages.

![](./images/product-lifecycle/adhoc-product-lifecycle.svg)

## Onboarding

The following table describes the key systems involved in Onboarding.

| System     | Purpose                                                                                                        |
| ---------- | -------------------------------------------------------------------------------------------------------------- |
| CreatorHub | Entry point for product onboarding. [Refer to Welcome to CreatorHub](https://dummy-link.com) for more details. |

When onboarding a product, you specify its configuration and marketing details in CreatorHub:

- **Product configuration**: General parameters, requirements for AdHoc context, user access, and tenant availability.
- **Marketing details**: Snapshot details, features and highlights, training materials, and contact points.

Once you've successfully onboarded a product, CreatorHub API makes the product configuration details available to App Market and the Navigation and Orchestration services.

Following this, your product transitions to the Adoption and Contextualization stages.

## Adoption

The following table describes the key systems involved in Adoption.

| System     | Purpose                                                                                                                                     |
| ---------- | ------------------------------------------------------------------------------------------------------------------------------------------- |
| App Market | A tenant-agnostic catalog that offers comprehensive product overviews, highlighting their features, training materials, and contact points. |

During Adoption, AdHoc users can browse App Market and request specific products. Then, tenant admins can request your team to make the product available for their tenant.

## Contextualization

> **Note:** The Contextualization stage takes place every time you update the product configuration in CreationHub.

The following table describes the key systems involved in Contextualization.

| System                | Purpose                                                                                                                                                           |
| --------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Navigation Service    | Maintains tenant navigation. [Refer to Tenant navigation](https://dummy-link.com) for more details.                                                               |
| Orchestration Service | Enables AdHoc users to manage projects through a combination of workflows and phases. [Refer to Projects and workflows](https://dummy-link.com) for more details. |
| Config Service        | Creates product instance boilerplates that are ready for launch in AdHoc.                                                                                         |
| Tenant Config         | Contains tenant requirements for navigation, project workflows, and user access.                                                                                  |

During Contextualization, your product goes through several processing stages to receive the necessary AdHoc context and align its internal user roles with the tenant-specific access requirements.

First, the Navigation and Orchestration services process the AdHoc context requirements:

- Navigation Service processes the navigation requirements to ensure that tenant admins can add your product to the appropriate tenant navigation levels.

  This step is crucial for products that that work based on the client, market, and brand context variables.

- Orchestration Service processes the workflow requirements to ensure that your product is available in the appropriate project workflows and phases.

> **Note:** Navigation and Orchestration services operate based on the context data AdHoc provides to help you develop highly specialized products. [Refer to Available AdHoc context](https://dummy-link.com) for more details.

Config Service combines Navigation and Orchestration outputs with the user access requirements, creating a product instance boilerplate.

Then, Config Service processes the tenant availability requirements to understand which tenants should have access to your product and compares the product instance boilerplate against the necessary Tenant Configs. This step aligns the contextualized product configuration with the tenant navigation, workflows, and user access, creating a tenant-specific product instances.

Following this, your product transitions to the Launch stage.

## Launch

The following table describes the key systems involved in Adoption.

| System   | Puprose                                                                |
| -------- | ---------------------------------------------------------------------- |
| Base App | A part of the AdHoc interface that makes products available to launch. |

During Launch, tenant users can interact with your product. When a user opens a product in AdHoc, Base App processes that user's credentials to understand their role and permissions and display the appropriate tenant-specific product instance.

## Next steps

Now that you understand how AdHoc processes the product configuration details you specify in CreatorHub, [learn more about AdHoc Authz](https://dummy-link.com) or [pick one of our Product boilerplates to create your first product](https://dummy-link.com).
