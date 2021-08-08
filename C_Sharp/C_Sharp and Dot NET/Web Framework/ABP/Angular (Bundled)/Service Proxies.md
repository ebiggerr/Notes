### Script for generating service proxies from the endpoints available from ABP.

Location of script : /nswag/refresh.bat (while server side - .Host project is running)

### service-proxies.ts

Location of service proxies : /src/shared/service-proxies/service-proxies.ts

All communication to server made via AJAX requests, we are using a client side javascript layer to call server API.

## Refreshing Service Proxies

While Nswag automatically generate proxy files, it does not refresh **service-proxies.module.ts**

Have to manually add it to the file.

```
import { NgModule } from '@angular/core'; 
import { HTTP_INTERCEPTORS } from '@angular/common/http'; 
import { AbpHttpInterceptor } from 'abp-ng2-module'; 
import * as ApiServiceProxies from './service-proxies'; 

@NgModule({ 
	providers: [ 
	ApiServiceProxies.RoleServiceProxy, 
	ApiServiceProxies.SessionServiceProxy,
	ApiServiceProxies.TenantServiceProxy, 
	ApiServiceProxies.UserServiceProxy, 
	ApiServiceProxies.TokenAuthServiceProxy,
	ApiServiceProxies.AccountServiceProxy,
	ApiServiceProxies.ConfigurationServiceProxy,
	ApiServiceProxies.TaskServiceProxy, 
	ApiServiceProxies.EventServiceProxy, 
	ApiServiceProxies.ADDNEWSERVIEWPROXY, //New Service Proxy 
	{ provide: HTTP_INTERCEPTORS, useClass: AbpHttpInterceptor, multi: true } 
	]
	}) 
	
	export class ServiceProxyModule { }

```