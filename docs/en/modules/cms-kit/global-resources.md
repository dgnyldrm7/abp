# CMS Kit: Global Resources

CMS Kit Global Resources system allows to add global styles and scripts dynamically.

## Enabling the Global Resources Feature

By default, CMS Kit features are disabled. Therefore, you need to enable the features you want, before starting to use it. You can use the [Global Feature](../../framework/infrastructure/global-features.md) system to enable/disable CMS Kit features on development time. Alternatively, you can use the ABP's [Feature System](../../framework/infrastructure/features.md) to disable a CMS Kit feature on runtime.

> Check the ["How to Install" section of the CMS Kit Module documentation](index.md#how-to-install) to see how to enable/disable CMS Kit features on development time.

## The User Interface

### Menu items

CMS Kit module admin side adds the following items to the main menu, under the *Global Resources* menu item:

* **Global Resources**: Global resources management page.

`CmsKitAdminMenus` class has the constants for the menu item names.

### Global Resources Page

Global Resources page is used to manage global styles and scripts in the system.

![cms-kit-global-resources-page](../../images/cmskit-module-global-resources-page.png)

# Internals

## Domain Layer

#### Aggregates

This module follows the [Entity Best Practices & Conventions](../../framework/architecture/best-practices/entities.md) guide.

- `GlobalResource` (aggregate root): Stores a resource.

#### Repositories

This module follows the [Repository Best Practices & Conventions](../../framework/architecture/best-practices/repositories.md) guide.

Following custom repositories are defined for this feature:

- `IGlobalResourceRepository`

#### Domain services

This module follows the [Domain Services Best Practices & Conventions](../../framework/architecture/best-practices/domain-services.md) guide.

##### Global Resource Manager

`GlobalResourceManager` is used to perform operations for the `GlobalResource` aggregate root.

### Application layer

#### Application services

- `GlobalResourceAdminAppService` (implements `IGlobalResourceAdminAppService`): Implements the management operations of global resources system.
- `GlobalResourcePublicAppService` (implements `IGlobalResourcePublicAppService`): Implements the public use cases of global resources system.

#### Database

#### Entity Framework Core

##### Tables

- CmsGlobalResources

#### MongoDB

##### Collections

- CmsGlobalResources