---
title: {{ mms-name }} access management
description: To allow access to {{ mms-name }} service resources (DB clusters and hosts, cluster backups, databases, and their users), assign the user the appropriate roles for the folder or cloud hosting the resources.
keywords:
  - access
  - access setup
  - access {{ MS }}
  - ms sql server
  - {{ MS }}
---

# Access management in {{ mms-name }}


In this section, you'll learn:
* [What resources you can assign roles to](#resources).
* [What roles exist in the service](#roles-list).
* [What roles are required](#required-roles) for particular actions.

{% include [about-access-management](../../_includes/iam/about-access-management.md) %}

## What resources you can assign roles to {#resources}

{% include [basic-resources](../../_includes/iam/basic-resources-for-access-control.md) %}

To allow access to {{ mms-name }} service resources (DB clusters and hosts, cluster backups, databases, and their users), assign the user the appropriate roles for the folder or cloud hosting the resources.

## What roles exist in the service {#roles-list}

The diagram shows which roles are available in the service and how they inherit each other's permissions. For example, the `editor` role includes all `viewer` role permissions. A description of each role is given under the diagram.

![image](../../_assets/mdb/service-roles-hierarchy.svg)

Active roles in the service:
* Service roles:
  * {% include [resource-manager.clouds.owner](../../_includes/iam/roles/short-descriptions/resource-manager.clouds.owner.md) %}
  * {% include [resource-manager.clouds.member](../../_includes/iam/roles/short-descriptions/resource-manager.clouds.member.md) %}
  * {% include [vpc.publicAdmin](../../_includes/iam/roles/short-descriptions/vpc.publicAdmin.md) %}
  * {% include [mdb.admin](../../_includes/iam/roles/short-descriptions/mdb.admin.md) %}
* Primitive roles:
  * {% include [viewer](../../_includes/iam/roles/short-descriptions/viewer.md) %}
  * {% include [editor](../../_includes/iam/roles/short-descriptions/editor.md) %}
  * {% include [admin](../../_includes/iam/roles/short-descriptions/admin.md) %}

## What roles do I need {#required-roles}

The table below lists the roles needed to perform a given action. You can always assign a role granting more permissions than the role specified. For example, you can assign `editor` instead of `viewer`.

Action | Methods | Required roles
--- | --- | ---
**View data** | |
View information about the cluster and related resources | `get`, `list` | `viewer` for the folder hosting the cluster
**Manage resources** | |
Create clusters and backups in the folder | `create` | `mdb.admin` or `editor` for the folder
Creating clusters with hosts that have public access enabled | `create` | Or `vpc.publicAdmin` together with `mdb.admin`, or `editor` for the folder
Change and delete clusters and related resources | `update`, `delete` | `mdb.admin` or `editor` for the folder hosting the cluster
**Manage resource access** | |
[Add](../operations/cluster-users.md#adduser), [edit](../operations/cluster-users.md#updateuser), [remove](../operations/cluster-users.md#removeuser) cluster users | `create`, `update`, `delete` | `editor` for the folder hosting the cluster
[Manage access to databases](../operations/grant.md) in the cluster | `grantPermission`, `revokePermission` | `editor` for the folder hosting the cluster
[Assign](../../iam/operations/roles/grant.md), [revoke](../../iam/operations/roles/revoke.md), and view roles granted for the resource or cloud | `setAccessBindings`, `updateAccessBindings`, `listAccessBindings` | `admin` for this folder or cloud

## What's next {#whats-next}

* [How to assign a role](../../iam/operations/roles/grant.md).
* [How to revoke a role](../../iam/operations/roles/revoke.md).
* [Learn more about access management in {{ yandex-cloud }}](../../iam/concepts/access-control/index.md).
* [For more information about role inheritance](../../resource-manager/concepts/resources-hierarchy.md#access-rights-inheritance).
