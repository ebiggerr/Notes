Used to transfer data between the [[Domain Driven Design#Application Layer]] and the `Presentation Layer`.

The `Presentation layer` calls an `Application Service` method with a DTO. The application service then uses these domain projects to perform some specific business logic, and then finally returns a DTO back to the presentation layer.

## DTO conventions and Validation

```

public interface IPersonAppService: IApplicationService
{
	SearchPeopleOutput SearchPeople(SearchPeopleInput input);
}
```

ASP suggests naming input/output parameters as MethodNameInput and MethodNameOutput and defining a separated input and output DTO for every application service method.