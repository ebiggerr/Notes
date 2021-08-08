Software Multitenancy refers to a software architecture in which a single instance of a software runs on a server and serves ==multiple tenants==. A tenant is a group of users who share a common access with specific privileges to the software instance.

With a multitenant architecture, a software application is designed to provide every tenant a **_dedicated share of the instance including its data_**, configuration, user management, tenant individual functionality and non-functional properties.

A technique that is used to create SaaS applications.

---


Multi-Tenancy in ABP

### Enabling Multi-Tenancy

```
Configuration.MultiTenancy.IsEnabled = true; 
```

Multi-tenacy is enabled in both ASP.NET Core and ASP.NET MVC 5.x startup templates.

## Host Vs Tenant

Tenant : A customer which has its own users, permission ,settings, and etc uses the application completely isolated from other tenants. A multi-teant application will have one or more tenants. If this is a CRM application, different tenants also have their own accounts, contacts, products and orders. So when we say a '**tenant user**', we mean a user owned by a tenant.

Host: The Host is singleton (there is a single host). The Host is responsible for creating and managing tenants. A '**host user**' is at a higher level and independent from all tenants and can control them.


## Session

ASP.NET Boilerplate defines the **IAbpSession** interface to obtain the current **user** and **tenant** ids. This interface is used in multi-tenancy to get the current tenant's id by default. Thus, it can filter data based on the current tenant's id. Here are the rules:

-   If both the UserId and the TenantId is null, then the current user is **not logged in** to the system. We can not know if it's a host user or tenant user. In this case, the user can not access [authorized](https://aspnetboilerplate.com/Pages/Documents/Authorization) content.
-   If the UserId is not null and the TenantId is null, then we know that the current user is a **host user**.
-   If the UserId is not null and the TenantId is not null, we know that the current user is a **tenant user**.
-   If the UserId is null but the TenantId is not null, that means we know the current tenant, but the current request is not authorized (user did not login). See the next section to understand how the current tenant is determined.

TODO // See the [session documentation](https://aspnetboilerplate.com/Pages/Documents/Abp-Session) for more information.

## Data-filters

For the multi-tenant single database approach, we must add a `TenantId` filter to only get the current tenant's entities when retrieving entities from the database.

ASP.NET Boilerplate automatically does it when you implement one of the two interfaces for your entity: **IMustHaveTenant** and **IMayHaveTenant**.


#### IMustHaveTenant Interface

This interface is used to distinguish the entities of different tenants by defining a **TenantId** property. An example entity that implements IMustHaveTenant:

```
public class Product : Entity, IMustHaveTenant
{
    public int TenantId { get; set; }

    public string Name { get; set; }

    //...other properties
}
```

This way, ASP.NET Boilerplate knows that this is a tenant-specific entity and automatically isolates the entities of a tenant from other tenants.
