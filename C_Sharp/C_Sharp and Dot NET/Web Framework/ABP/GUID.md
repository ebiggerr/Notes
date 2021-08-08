GUID is a common primary key type that is used in database management systems.

`ICurrentUser.Id` property ([see](https://docs.abp.io/en/abp/latest/CurrentUser)) is type of GUID, that means the ABP Framework assumes that the User Id is always GUID.

## IGuidGenerator

GUID is not sequential by default, see
```
 Id = Guid.NewGuid(); // random
```

`IGuidGenerator` service creates sequential GUIDs (implemented by the `SequentialGuidGenerator` by default). Use `IGuidGenerator.Create()` when you need to manually set Id of an [entity](Entities).

Assume we have `Product` entity that has a `Guid` key.

```
using System;
using Volo.Abp.Domain.Entities;

namespace AbpDemo
{
    public class Product : AggregateRoot<Guid>
    {
        public string Name { get; set; }

        private Product() { /* This constructor is used by the ORM/database provider */ }

        public Product(Guid id, string name)
            : base(id)
        {
            Name = name;
        }
    }
}


using System;
using System.Threading.Tasks;
using Volo.Abp.DependencyInjection;
using Volo.Abp.Domain.Repositories;
using Volo.Abp.Guids;

namespace AbpDemo
{
    public class MyProductService : ITransientDependency
    {
        private readonly IRepository<Product, Guid> _productRepository;
        private readonly IGuidGenerator _guidGenerator;

        public MyProductService(
            IRepository<Product, Guid> productRepository,
            IGuidGenerator guidGenerator)
        {
            _productRepository = productRepository;
            _guidGenerator = guidGenerator;
        }
        
        public async Task CreateAsync(string productName)
        {
            var product = new Product(_guidGenerator.Create(), productName);

            await _productRepository.InsertAsync(product);
        }
    }
}

```

The `MyProductService` injects the `IGuidGenerator` in the constructor. If the class is an `application service` or deriving from one of the other base classes, we can directly use the `GuidGenerator` base property which is pre-injected `IGuidGenerator` instance.


### AbpSequentialGuidGeneratorOptions