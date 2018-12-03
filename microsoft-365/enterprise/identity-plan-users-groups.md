---
title: '手順 1: ユーザーおよびグループを計画する'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 組織に最適なユーザーとグループのセットを計画します。
ms.openlocfilehash: 8062cc2b681f0ae45a8114a6d827f5d1ece2fe3e
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868991"
---
# <a name="step-1-plan-for-users-and-groups"></a><span data-ttu-id="b27c6-103">手順 1: ユーザーおよびグループを計画する</span><span class="sxs-lookup"><span data-stu-id="b27c6-103">Step 1: Plan for users and groups</span></span>

<span data-ttu-id="b27c6-104">*この手順は必須であり、Microsoft 365 Enterprise のバージョン E3 および E5 の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="b27c6-104">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="b27c6-p101">この手順では、正しい構成でセキュリティ機能とユーザー、グループ、およびグループ メンバーシップを組み合わせた ID インフラストラクチャを作成します。これにより、次の操作が可能になります。</span><span class="sxs-lookup"><span data-stu-id="b27c6-p101">In Step 1, you'll create your identity infrastructure that combines users, groups, and group membership with security features in the correct configuration. This allows you to:</span></span>

- <span data-ttu-id="b27c6-107">環境内のリソースにアクセスできるユーザーを制御する。</span><span class="sxs-lookup"><span data-stu-id="b27c6-107">Maintain control over who has access to resources in your environment.</span></span>
- <span data-ttu-id="b27c6-108">ID の強力な保証 (ユーザーは、そのユーザーが宣言したとおりである) と安全なデバイスからのアクセスを実現するコントロールにより、アクセスを保護する。</span><span class="sxs-lookup"><span data-stu-id="b27c6-108">Secure access with controls that ensure strong assurances of identity (users are who they say they are) and access from safe devices.</span></span>
- <span data-ttu-id="b27c6-109">適切なアクセス許可を使用して環境内のリソースをプロビジョニングし、データの損傷や漏洩が発生する可能性を低減させる。</span><span class="sxs-lookup"><span data-stu-id="b27c6-109">Provision resources in your environment with appropriate permissions to reduce the potential for harm and data leakage.</span></span> 
- <span data-ttu-id="b27c6-110">環境で異常なユーザーの行動を監視し、自動的に処置を実行する。</span><span class="sxs-lookup"><span data-stu-id="b27c6-110">Monitor your environment for anomalous user behavior and automatically taking action.</span></span>

## <a name="plan-your-primary-identity-provider"></a><span data-ttu-id="b27c6-111">プライマリ ID プロバイダーを計画する</span><span class="sxs-lookup"><span data-stu-id="b27c6-111">Plan your primary identity provider</span></span>

<span data-ttu-id="b27c6-p102">ID インフラストラクチャを作成するには、プライマリ ID プロバイダーを指定します。このサービスは、ユーザー アカウントとその属性、グループとメンバーシップを保存し、それらの継続的な管理をサポートします。</span><span class="sxs-lookup"><span data-stu-id="b27c6-p102">To create your identity infrastructure, you'll designate a primary identity provider. This service stores user accounts and their attributes, groups and their memberships, and supports their ongoing administration.</span></span>

<span data-ttu-id="b27c6-114">組織が Microsoft 365 Enterprise を導入する場合、プライマリ ID プロバイダーは次のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="b27c6-114">When your organization adopts Microsoft 365 Enterprise, your primary identity provider is either:</span></span>

- <span data-ttu-id="b27c6-p103">**Windows Server Active Directory (AD)**: Windows Server を実行しているコンピューターでホストされているイントラネット ID プロバイダーです。これは通常、既存のオンプレミス ID プロバイダーを使用する組織で使用されます。</span><span class="sxs-lookup"><span data-stu-id="b27c6-p103">**Windows Server Active Directory (AD)**, an intranet identity provider hosted on computers running Windows Server. This is typically used by organizations that have an existing on-premises identity provider.</span></span>
- <span data-ttu-id="b27c6-p104">**Azure Active Directory (Azure AD)**: 環境の管理および保護のためのさまざまな機能を提供するクラウド ベースの Identity as a Service (IDaaS) です。これは通常、既存のオンプレミス インフラストラクチャを持たない組織で使用されます。</span><span class="sxs-lookup"><span data-stu-id="b27c6-p104">**Azure Active Directory (Azure AD**), a cloud-based Identity as a Service (IDaaS) that provides a broad range of capabilities for managing and protecting your environment. This is typically used by organizations that have no existing on-premises infrastructure.</span></span>

<span data-ttu-id="b27c6-p105">組織に既存のオンプレミス ID プロバイダーがある場合、Windows Server AD のユーザー アカウントとグループを Azure AD と同期し、Microsoft 365 Enterprise のクラウドベース サービスによりシームレスにアクセスできるようにします。また、Azure AD を使用して、Microsoft クラウドにのみ存在するグループを作成および管理することもできます。</span><span class="sxs-lookup"><span data-stu-id="b27c6-p105">If your organization has an existing on-premises identity provider, you need to synchronize your user accounts and groups from Windows Server AD to Azure AD to provide more seamless access to the cloud-based services of Microsoft 365 Enterprise. You can also use Azure AD to create and manage groups that exist only in the Microsoft cloud.</span></span>

<span data-ttu-id="b27c6-121">Azure AD でユーザーとグループを作成した後には、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="b27c6-121">After you have your users and groups in Azure AD, you can:</span></span>

- <span data-ttu-id="b27c6-122">すべてのクラウド アプリケーションのすべての Azure AD アカウントを管理する。</span><span class="sxs-lookup"><span data-stu-id="b27c6-122">Manage all the Azure AD accounts for all your cloud applications.</span></span> 
- <span data-ttu-id="b27c6-123">同じコントロールのセットを使用して、環境全体でアプリケーションへのアクセスを保護する。</span><span class="sxs-lookup"><span data-stu-id="b27c6-123">Use the same set of controls to protect access to applications across your environment.</span></span>
- <span data-ttu-id="b27c6-124">外部パートナーと共同作業を行う。</span><span class="sxs-lookup"><span data-stu-id="b27c6-124">Collaborate with external partners.</span></span>
- <span data-ttu-id="b27c6-125">アカウントの異常な動作 (不審なサインイン試行など) を監視し、自動的に対処する。</span><span class="sxs-lookup"><span data-stu-id="b27c6-125">Monitor anomalous account behavior, such as suspicious sign-in attempts, and automatically act.</span></span>

<span data-ttu-id="b27c6-126">次の 2 つのセクションで説明する手順に従い、ユーザー アカウントおよびグループを計画および導入します。</span><span class="sxs-lookup"><span data-stu-id="b27c6-126">Follow the instructions in the next two sections to plan for and implement your user accounts and groups.</span></span>

## <a name="categorize-your-users"></a><span data-ttu-id="b27c6-127">ユーザーを分類する</span><span class="sxs-lookup"><span data-stu-id="b27c6-127">Categorize your users</span></span>
<span data-ttu-id="b27c6-p106">組織内のユーザーは、さまざまな方法で分類できます。たとえば、永続的なステータスを持つ正社員、一時的なステータスを持つベンダー、契約社員、パートナーなどです。また、ユーザー アカウントを持たないものの、コミュニケーションやコラボレーションに対応するため特定のサービスとリソースへのアクセスを許可する必要がある外部ユーザーなどもあります。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="b27c6-p106">Users in organizations can be categorized in a number of ways. For example, some are employees and have a permanent status. Some are vendors, contractors, or partners that have a temporary status. Some are external users that have no user accounts but must still be granted access to specific services and resources to support interaction and collaboration. For example:</span></span>

- <span data-ttu-id="b27c6-133">テナント アカウントは、組織内でクラウド サービスのライセンスを付与したユーザーを表します。</span><span class="sxs-lookup"><span data-stu-id="b27c6-133">Tenant accounts represent users within your organization that you license for cloud services</span></span>
- <span data-ttu-id="b27c6-134">B2B (Business to Busines) アカウントは、コラボレーションへの参加のために招待された組織外部のユーザーを表します。</span><span class="sxs-lookup"><span data-stu-id="b27c6-134">Business to Business (B2B) accounts represent users outside your organization that you invite to participate in collaboration</span></span>

<span data-ttu-id="b27c6-p107">組織のユーザーの既存の種類を調べます。どのようにグループ化していますか。たとえば、組織の上位の職種または目的によりユーザーをグループ化できます。</span><span class="sxs-lookup"><span data-stu-id="b27c6-p107">Take stock of the types of users to your organization. What are the groupings? For example, you can group users by high-level function or purpose to your organization.</span></span>

<span data-ttu-id="b27c6-p108">また、一部のクラウド サービスを、ユーザー アカウントを持たない組織外のユーザーと共有できます。この場合、このような外部ユーザーのグループも指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b27c6-p108">Additionally, some cloud services can be shared with users outside your organization without any user accounts. You'll need to identify these groups of users as well.</span></span>

## <a name="plan-for-windows-server-ad-and-azure-ad-groups"></a><span data-ttu-id="b27c6-140">Windows Server AD と Azure AD のグループを計画する</span><span class="sxs-lookup"><span data-stu-id="b27c6-140">Plan for Windows Server AD and Azure AD groups</span></span>

<span data-ttu-id="b27c6-p109">Azure AD では、クラウド環境の管理を簡素化するさまざまな目的のためにグループを使用できます。たとえば、Azure AD グループでは次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="b27c6-p109">You can use groups in Azure AD for several purposes that simplify management of your cloud environment. For example, for Azure AD groups, you can:</span></span>

- <span data-ttu-id="b27c6-143">グループベースのライセンスを使用して、ユーザー アカウントが Azure AD に追加された時点または Windows Server AD から同期された時点で、Office 365 と Enterprise Mobility + Security (EMS) のライセンスをアカウントに自動的に割り当てる。</span><span class="sxs-lookup"><span data-stu-id="b27c6-143">Use group-based licensing to assign licenses for Office 365 and Enterprise Mobility + Security (EMS) to your user accounts automatically as soon as they are added in Azure AD or synchronized from Windows Server AD.</span></span> 
- <span data-ttu-id="b27c6-144">ユーザー アカウントの属性 (部門など) に基づいて、ユーザー アカウントを特定のグループに動的に追加する。</span><span class="sxs-lookup"><span data-stu-id="b27c6-144">Add user accounts to specific groups dynamically based on user account attributes, such as department.</span></span>  
- <span data-ttu-id="b27c6-145">Software as a Service (SaaS) アプリケーションのユーザーを自動的にプロビジョニングし、多要素認証やその他の条件付きアクセス ルールでこれらのアプリケーションへのアクセスを保護する。</span><span class="sxs-lookup"><span data-stu-id="b27c6-145">Automatically provision users for Software as a Service (SaaS) applications and to protect access to those applications with multi-factor authentication and other conditional access rules.</span></span>
- <span data-ttu-id="b27c6-p110">SharePoint Online チーム サイトのアクセス許可とアクセス レベルをプロビジョニングする。Azure AD グループを Azure Information Protection スコープ ポリシーと組み合わせて使用し、暗号化とアクセス許可でファイルを保護できる。</span><span class="sxs-lookup"><span data-stu-id="b27c6-p110">Provision permissions and levels of access for SharePoint Online team sites. Azure AD groups can also be used with scoped Azure Information Protection policies to protect files with encryption and permissions.</span></span> 

## <a name="results"></a><span data-ttu-id="b27c6-148">結果</span><span class="sxs-lookup"><span data-stu-id="b27c6-148">Results</span></span>

<span data-ttu-id="b27c6-149">この手順の完了後の成果物は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b27c6-149">When you complete this step, you’ll have:</span></span>

- <span data-ttu-id="b27c6-150">組織内の従業員、ベンダー、契約社員、組織のために働くまたは組織と協働する外部パートナーに対応する、Azure AD のユーザー アカウントのリスト。</span><span class="sxs-lookup"><span data-stu-id="b27c6-150">A list of user accounts in Azure AD that correspond to the employees in your organization and the vendors, contractors, and external partners that work for or with your organization.</span></span>
- <span data-ttu-id="b27c6-151">Azure AD のグループとそのメンバーシップのセット。これは、Microsoft クラウド サービスのセキュリティ設定の自動ライセンス プロビジョニングのためのユーザー アカウントおよびその他のグループの論理セットを反映しています。</span><span class="sxs-lookup"><span data-stu-id="b27c6-151">A set of groups and their membership in Azure AD that reflect logical sets of user accounts and other groups for automatic licensing provisioning of security settings for Microsoft cloud services.</span></span>

<span data-ttu-id="b27c6-152">中間チェックポイントとして、この手順の[終了条件](identity-exit-criteria.md#crit-identity-user-groups)を確認できます。</span><span class="sxs-lookup"><span data-stu-id="b27c6-152">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-user-groups) for this step.</span></span>


## <a name="next-step"></a><span data-ttu-id="b27c6-153">次の手順</span><span class="sxs-lookup"><span data-stu-id="b27c6-153">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step2.png)| [<span data-ttu-id="b27c6-154">全体管理者アカウントを保護する</span><span class="sxs-lookup"><span data-stu-id="b27c6-154">Protect global administrator accounts</span></span>](identity-designate-protect-admin-accounts.md) |

