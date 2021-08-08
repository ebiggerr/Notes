# EntityFramework Core

#### Entities
Entities defined under `/src/<projectName>`/.xx.Core


#### DbContext

```
using Microsoft.EntityFrameworkCore;  
using Abp.Zero.EntityFrameworkCore;  
using demo.Authorization.Roles;  
using demo.Authorization.Users;  
using demo.MultiTenancy;  
using demo.Tasks;  
using demo.Events;  
  
namespace demo.EntityFrameworkCore  
{  
    public class demoDbContext : AbpZeroDbContext<Tenant, Role, User, demoDbContext>  
    {  
        /* Define a DbSet for each entity of the application */  
 		public DbSet<Task> Tasks { get; set; }  //entity
  
        public DbSet<Event> Events { get; set; }  
  
        public DbSet<EventRegistration> EventRegistrations { get; set; }  
  
        public demoDbContext(DbContextOptions<demoDbContext> options)  
            : base(options)  
        {  
        }  
  
          
    }  
  
}
```



#### Database Migration

```
//Command on the Nuget Package Console Manager
// Two main commands

Add-Migration <Name> 

//For version control of the database model, using different name 
// For example, new entity called Student 
// <Name> can be AddedStudent

update-database <Name> 

// <Name> is optional, does not need to specify the name when you want to apply the latest migration generated
//Apply the migration generated to the database
```