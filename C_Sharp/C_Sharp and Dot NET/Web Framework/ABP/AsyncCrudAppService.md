```

namespace Abp.Application.Services  
{  
  public abstract class AsyncCrudAppService<TEntity, TEntityDto, TPrimaryKey, TGetAllInput, TCreateInput> :   
    AsyncCrudAppService<TEntity, TEntityDto, TPrimaryKey, TGetAllInput, TCreateInput, TCreateInput>  
    where TEntity : class, IEntity<TPrimaryKey>  
    where TEntityDto : IEntityDto<TPrimaryKey>  
    where TGetAllInput : IPagedAndSortedResultRequest  
 where TCreateInput : IEntityDto<TPrimaryKey>  
  {  
    protected AsyncCrudAppService(IRepository<TEntity, TPrimaryKey> repository)  
      : base(repository)  
    {  
    }  
  }  
}
```