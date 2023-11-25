---
Audience: Technical decision-makers
---

# Architecture overview

This page explores multitenancy, data storage, and user governance in AdHoc to offer a high-level overview of our architecture and enable you to decide whether AdHoc is the right solution for your digital agency.

## What is multitenancy?

Multitenancy is a software architecture paradigm in which a single software instance serves multiple individual entities, or tenants. All tenants share the same underlying technology infrastructure and resources, but their data is isolated and invisible to other tenants.

## Multitenancy in AdHoc

In AdHoc, tenants represent digital agencies and their clients.

We maintain each tenant's configuration in a separate database. Combined with AdHoc Authz, this approach ensures that users interact with the appropriate data based on their respective access and permissions. This means your tenant can have an isolated set of users, data, products, and workflows—without interference from or overlap with other tenants.

AdHoc can also house multiple tenants for each client your agency works with, effectively mimicking its internal hierarchy. This approach enables teams working with different clients to avoid confusion and data crossover. Each team interacts only with the data and projects relevant to their current assignments, and the baseline tenant configuration is maintained at the agency level.

To identify different tenants within AdHoc, we provide them with unique URL prefixes.

```shell
# Tenant for AdHoc
https://adhoc.adhoc.com/

# Tenant for Creative Clicks
https://creative-clicks.adhoc.com/

# Tenant for Pixel Pioneers
https://pixel-pioneers.adhoc.com/

# Tenant for the BPub client in Pixel Pioneers
https://pixel-pioneers.bpub.adhoc.com/
```

## Data storage

AdHoc stores each tenant's data separately to provide a higher degree of data isolation and offer more options for tenant customization.

The following diagram illustrates our approach to storing tenant data in dedicated databases.

![A diagram that illustrates AdHoc's approach to storing tenant data in dedicated databases.](./images/architecture/adhoc-data-storage.svg)

> **Note:** We are open to adapting our data storage approaches to your needs. For instance, if you want to implement multiple client-based tenants, we can either set up dedicated databases for each tenant or a single database that stores all agency data. [Get in touch with our sales representatives](https://dummy-link.com) to learn more.

By implementing dedicated databases for each tenant, we achieve the following:

- **Security**: Prevent cross-tenant data leaks, ensuring the highest security for your client and user data.
- **Scalability**: Offer as much storage and processing capacity as your agency requires without affecting other tenants.
- **Customization**: Tailor data schemas to address your agency's specific requirements.

## User governance

AdHoc has a built-in authorization and access management module, AdHoc Authz, which offers control over user access to different features and data within tenants. To learn more about this module, [refer to the AdHoc Authz docs](https://dummy-link.com).

Depending on the AdHoc Authz configuration, your users can have access to a single agency tenant or the primary agency tenant and multiple client tenants. This approach to user governance ensures that agencies with client-based tenants can have employees working on several projects at a time.

We also offer all users default access to the primary AdHoc tenant, enabling them to [collaborate through CreatorHub](https://dummy-link.com) and [share products through App Market](https://dummy-link.com).

Responsibility for providing access to different tenants lies with the tenant administration teams. Once fully onboarded to AdHoc, your agency can have a designated tenant admin who configures user access, permissions, and other tenant settings.

> **Note:** To simplify the initial onboarding, we offer tenant administration services with subsequent training for tenant admins in your agency. [Refer to Services and Pricing](https://dummy-link.com) to learn more.

## Next steps

Now that you understand how AdHoc approaches multitenancy, data storage, and user governance, [continue exploring the Architecture section](https://dummy-link.com) to learn how we [launch and share products](https://dummy-link.com) across digital agencies in AdHoc.
