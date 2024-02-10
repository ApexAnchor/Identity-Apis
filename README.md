# Authentication in ASP.NET Core Web API with Bearer Tokens & Cookies

## Introduction

This guide will walk you through configuring authentication in an ASP.NET Core Web API using Microsoft.AspNetCore.Identity- Tokens and Cookie approach.

## Steps
1. Create a sample Web Api project using the default template
2. Create a db context called ApplicationDbContext inheriting from IdentityDbContext (Make sure to add necessary packages)
3. Configure application to use Entity framework using Sqllite ( you can use any other data base)
4. Add the Identiy Apis to the application which provides all the in-built apis from Identity framework

```
builder.Services.AddAuthorization()    
                .AddIdentityApiEndpoints<IdentityUser>()
                .AddEntityFrameworkStores<ApplicationDbContext>();
```
5. Map the identity api
```
app.MapGroup("api/auth")
   .MapIdentityApi<IdentityUser>();
```
6. Decorate Authorize attribute on your apis
