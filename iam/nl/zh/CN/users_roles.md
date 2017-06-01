---

copyright:

  years: 2015, 2016
lastupdated: "2017-05-17"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# 用户角色和许可权
{: #userroles}

可以在帐户的**用户**页面中，管理 {{site.data.keyword.Bluemix_notm}} Platform 和 Infrastructure 服务上的用户。如果要仅管理平台用户对组织和空间的 Cloud Foundry 访问权，那么“用户”页面上还提供有“团队目录”页面的链接。但是，您不必离开“用户”页面来管理 Cloud Foundry 访问权。
{:shortdesc}

要访问“用户”页面，请在 {{site.data.keyword.Bluemix_notm}} 菜单中，单击**管理** &gt; **帐户** &gt; **用户**。帐户所有者可对组织和空间执行所有操作，包括管理用户及其分配的角色。组织管理员和空间管理员也有权管理角色。 

如果您是添加到其他人帐户的用户，并且希望查看分配给您的角色和许可权，请转至**管理** &gt; **安全性** &gt; **身份和访问权** &gt; **用户**，然后单击您的姓名。

## 帐户角色
{: #userrolesinfo}

在帐户级别，有两个角色支持访问不同的帐户管理功能：

| 帐户角色 | 许可权 |
|----------------|---------|
|所有者 | 帐户所有者有权访问其个人档案、团队目录、记帐信息、花费通知和使用情况仪表板。在“团队目录”或“用户”页面中，所有者可以邀请新的团队成员并调整角色。所有者还可以添加促销信贷，设置或更改记帐限制，设置服务访问权以及管理组织和空间。 |
|成员 | 成员有权在 {{site.data.keyword.Bluemix_notm}} 标题中访问其个人档案、团队目录、帐户信贷和记帐限制。但是，在“团队目录”页面上，成员只能查看该帐户内的团队成员。 |
{:caption="表 1. 帐户角色和许可权" caption-side="top"}

所有新用户都会添加为该帐户的成员。您可以为被邀请者添加组织和空间角色，以在 {{site.data.keyword.Bluemix_notm}} 中启用特定视图和许可权。缺省情况下，会向添加到组织的新团队成员（在本地或专用环境中除外）分配审计员组织角色。对于特定空间，可以选择向被邀请者分配开发者或审计员角色。一旦被邀请者接受邀请并加入 {{site.data.keyword.Bluemix_notm}}，您就可以在“用户”或“团队目录”页面上编辑这些被邀请者的角色。

## Cloud Foundry 角色
{: #cfroles}

Cloud Foundry 角色包含帐户中定义的组织和空间的访问许可权。可以在组织级别分配以下角色：

| 组织角色 | 许可权 |
|-------------------|-------------|
|管理器 | 组织管理员可以创建、查看、编辑或删除组织内的空间，查看组织的使用情况和配额，邀请团队成员加入组织，管理谁有权访问组织及其在组织中的角色，以及管理组织的定制域。 |
|记帐管理员 | 记帐管理员可以在“使用情况仪表板”页面上查看组织的运行时和服务使用情况信息。  |
|审计员 | 组织审计员可以查看组织中的应用程序和服务内容。审计员还可以查看组织中的用户及其分配的角色，以及组织的配额。缺省情况下，会向所有被邀请者（在本地或专用环境中除外）分配此角色。 |
{:caption="表 2. 组织角色和许可权" caption-side="top"}

可以在空间级别分配以下角色：

| 空间角色 | 许可权 |
|------------|-------------|
|管理器 | 空间管理员可以添加现有用户，并管理空间内的角色。空间管理员还可以查看空间中每个应用程序的实例数、服务绑定和资源使用情况。 |
|开发者 | 空间开发者可以创建、删除和管理空间内的应用程序和服务。某些管理任务包括部署应用程序，启动或停止应用程序，重命名应用程序，删除应用程序，重命名空间，将服务绑定到应用程序或从应用程序取消绑定服务，以及查看空间中每个应用程序的实例数、服务绑定和资源使用情况。此外，空间开发者还可以将内部或外部 URL 与空间中的应用程序相关联。   |
|审计员 | 空间审计员具有对有关空间的所有信息的只读访问权，例如有关空间中每个应用程序的实例数、服务绑定和资源使用情况的信息。 |
{:caption="表 3. 空间角色和许可权" caption-side="top"}

**注**：分配有管理员或开发者空间角色的用户可以访问 VCAP_SERVICES 环境变量。但是，分配有审计员角色的用户无法访问 VCAP_SERVICES。

## 身份和访问权管理策略与角色
{: #iamusermanpol}

帐户所有者会自动分配有管理身份和访问权的帐户访问权管理员角色，此角色将支持您分配和管理服务策略。通过此类型的访问控制，可以按服务或服务实例分配策略，以允许在分配的上下文中使用管理资源和用户的访问权级别。

### 服务策略

策略使用属性组合来定义适用的一组资源，从而为用户分配对该组资源的一个或多个角色。为用户分配策略时，首先指定要分配的服务，包括用于分配所有可用服务的选项。然后，还可以选择要分配的一个或多个角色。根据选择的服务，可能会提供其他配置选项。

如果您具有合适的角色，那么可以分配和管理策略。下表显示了策略管理任务以及每个任务所需的角色。

{: #iamui_table1}

| 操作 | 所需角色 |
|----------|---------|
| 创建关于帐户的策略 | 帐户访问权管理员 |
| 创建关于帐户中所有服务的策略 | 帐户访问权管理员 |
| 创建关于帐户中所有服务实例的策略 | 帐户访问权管理员 |
| 创建关于帐户中某个服务的策略 | 帐户访问权管理员或帐户中该服务的管理员 |
| 创建服务实例 | 帐户访问权管理员或编辑者，或帐户中该服务的管理员或编辑者 |
| 创建关于某个服务实例的策略 | 帐户访问权管理员、帐户中该服务的管理员或该服务实例的管理员 |
{: caption="表 4. 用于管理启用了身份和访问权的服务策略的管理任务" caption-side="top"}

### 服务策略角色
{: #iamusermanrol}

角色是操作的集合；映射到这些角色的操作是特定于服务的。
有关每个角色允许使用的操作类型的其他详细信息，请参阅所选服务的文档。

除了控制台中提供的角色的描述外，下表还提供了根据所选服务，分配有每个角色的用户可以执行的一些任务示例。 

{: #iamui_table2}

| 角色 | 操作描述 | 示例操作|
|:-----------------|:-----------------|:-----------------|
| 查看者 | 执行不会更改状态的操作；只读操作 | <ul><li>列出设备</li><li>读取存储对象</li><li>运行查询</li><li>运行搜索</li></ul>|
| 编辑者 | 执行会修改状态以及创建或删除子资源的操作 |<ul><li>创建或删除虚拟机</li><li>连接存储器</li><li>重新引导</li><li>启动或停止</li><li>重命名</li></ul> |
| 管理员 | 执行所有操作，包括管理访问控制的能力 |<ul><li>邀请用户</li><li>创建或删除虚拟机</li><li>更新用户访问策略</li><li>列出设备</li><li>连接存储器</li><li>重新引导</li><li>启动或停止</li><li>重命名</li><li>备份和复原</li></ul>|
{: caption="表 5. 用于管理启用了身份和访问权的服务策略的管理任务" caption-side="top"}

## 基础架构许可权
{: #infrapermissions}

如果您有权分配基础架构许可权，那么可以为用户设置以下许可权： 

| 基础架构许可权 | 操作描述 |
|---------------------------|------------------------|
|仅查看 | 具有此许可权的用户只能查看系统内的项。|
|基本用户 | 具有此许可权的用户可以在系统内执行基本操作，例如添加凭单和管理设备。 |
|超级用户 | 具有此许可权的用户可以执行系统中可用的所有操作。 |
{:caption="表 6. 基础架构许可权" caption-side="top"}
