---
title: 個別のユーザーのパスワードを無期限に設定する
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: f493e3af-e1d8-4668-9211-230c245a0466
description: Windows PowerShell を使用して、一部のユーザーパスワードを期限切れにしないように設定する方法について説明します。
ms.openlocfilehash: 9497dfb5793ddbfc3d6845ec1efba91ad972ea38
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/21/2020
ms.locfileid: "48646657"
---
# <a name="set-an-individual-users-password-to-never-expire"></a><span data-ttu-id="11ea8-103">個別のユーザーのパスワードを無期限に設定する</span><span class="sxs-lookup"><span data-stu-id="11ea8-103">Set an individual user's password to never expire</span></span>

<span data-ttu-id="11ea8-104">この記事では、個々のユーザーのパスワードを期限切れにならないように設定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="11ea8-104">This article explains how to set a password for an individual user to not expire.</span></span> <span data-ttu-id="11ea8-105">これらの手順は、PowerShell を使用して完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="11ea8-105">You have to complete these steps using PowerShell.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="11ea8-106">開始する前に</span><span class="sxs-lookup"><span data-stu-id="11ea8-106">Before you begin</span></span>

<span data-ttu-id="11ea8-107">この記事は、職場、学校、または非営利団体のパスワードの有効期限ポリシーを設定する管理者を対象としています。</span><span class="sxs-lookup"><span data-stu-id="11ea8-107">This article is for people who set password expiration policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="11ea8-108">これらの手順を完了するには、Microsoft 365 の管理者アカウントでサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="11ea8-108">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> <span data-ttu-id="11ea8-109">[管理者アカウントとは](../admin-overview/admin-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="11ea8-109">[What's an admin account?](../admin-overview/admin-overview.md).</span></span> 

<span data-ttu-id="11ea8-110">これらの手順を実行するには、 [グローバル管理者またはパスワード管理者](about-admin-roles.md) である必要があります。</span><span class="sxs-lookup"><span data-stu-id="11ea8-110">You must be an [global admin or password administrator](about-admin-roles.md) to perform these steps.</span></span>

<span data-ttu-id="11ea8-111">Microsoft クラウドサービスのグローバル管理者は、 [Azure Active Directory PowerShell For Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0) を使用して、特定のユーザーに対してパスワードを無期限に設定することができます。</span><span class="sxs-lookup"><span data-stu-id="11ea8-111">A global admin for a Microsoft cloud service can use the [Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0) to set passwords not to expire for specific users.</span></span> <span data-ttu-id="11ea8-112">また、 [AzureAD](https://docs.microsoft.com/powershell/module/Azuread) コマンドレットを使用して、無期限の構成を削除したり、どのユーザーのパスワードが期限切れにならないかを確認したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="11ea8-112">You can also use [AzureAD](https://docs.microsoft.com/powershell/module/Azuread) cmdlets to remove the never-expires configuration or to see which user passwords are set to never expire.</span></span>

<span data-ttu-id="11ea8-113">このガイドは、Intune や Microsoft 365 などの他のプロバイダーに適用されます。これは、id およびディレクトリサービスのために Azure AD にも依存しています。</span><span class="sxs-lookup"><span data-stu-id="11ea8-113">This guide applies to other providers, such as Intune and Microsoft 365, which also rely on Azure AD for identity and directory services.</span></span> <span data-ttu-id="11ea8-114">ポリシーの変更可能な部分は、パスワードの有効期限のみです。</span><span class="sxs-lookup"><span data-stu-id="11ea8-114">Password expiration is the only part of the policy that can be changed.</span></span>

> [!NOTE]
> <span data-ttu-id="11ea8-115">ディレクトリ同期によって同期されていないユーザーアカウントのパスワードのみ、期限切れにならないように構成できます。</span><span class="sxs-lookup"><span data-stu-id="11ea8-115">Only passwords for user accounts that are not synchronized through directory synchronization can be configured to not expire.</span></span> <span data-ttu-id="11ea8-116">ディレクトリ同期の詳細については、「 [CONNECT ad With AZURE ad](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="11ea8-116">For more information about directory synchronization, see [Connect AD with Azure AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span></span>

## <a name="how-to-check-the-expiration-policy-for-a-password"></a><span data-ttu-id="11ea8-117">パスワードの有効期限ポリシーを確認する方法</span><span class="sxs-lookup"><span data-stu-id="11ea8-117">How to check the expiration policy for a password</span></span>

<span data-ttu-id="11ea8-118">AzureAD モジュールの Get-AzureADUser コマンドの詳細については、「 [set-azureaduser](https://docs.microsoft.com/powershell/module/Azuread/Get-AzureADUser?view=azureadps-2.0)」という参照記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="11ea8-118">For more information about the Get-AzureADUser command in the AzureAD module, see the reference article [Get-AzureADUser](https://docs.microsoft.com/powershell/module/Azuread/Get-AzureADUser?view=azureadps-2.0).</span></span>

<span data-ttu-id="11ea8-119">次のいずれかのコマンドを実行します：</span><span class="sxs-lookup"><span data-stu-id="11ea8-119">Run one of the following commands:</span></span>

- <span data-ttu-id="11ea8-120">単一のユーザーのパスワードが期限切れにならないように設定されているかどうかを確認するには、UPN (たとえば、 *user@contoso.onmicrosoft.com*) またはチェックするユーザーのユーザー ID を使用して、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="11ea8-120">To see if a single user's password is set to never expire, run the following cmdlet by using the UPN (for example, *user@contoso.onmicrosoft.com*) or the user ID of the user you want to check:</span></span>

    ```powershell
    Get-AzureADUser -ObjectId <user id or UPN> | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```

    <span data-ttu-id="11ea8-121">例: </span><span class="sxs-lookup"><span data-stu-id="11ea8-121">Example:</span></span>

    ```powershell
    Get-AzureADUser -ObjectId userUPN@contoso.com | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```  

- <span data-ttu-id="11ea8-122">すべてのユーザーの **パスワードの有効期限** が設定されていないことを確認するには、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="11ea8-122">To see the **Password never expires** setting for all users, run the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
     }
    ```

- <span data-ttu-id="11ea8-123">PasswordNeverExpires を使用しているすべてのユーザーのレポートを取得するには、現在のユーザーのデスクトップに名前**ReportPasswordNeverExpires.html**を指定します。</span><span class="sxs-lookup"><span data-stu-id="11ea8-123">To get a report of all the users with PasswordNeverExpires in Html on the desktop of the current user with name  **ReportPasswordNeverExpires.html**</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Html | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.html
    ```  

- <span data-ttu-id="11ea8-124">PasswordNeverExpires を使用しているすべてのユーザーについて、現在のユーザーのデスクトップ上の名前を持つすべてのユーザーのレポートを取得するには **ReportPasswordNeverExpires.csv**</span><span class="sxs-lookup"><span data-stu-id="11ea8-124">To get a report of all the users with PasswordNeverExpires in CSV on the desktop of the current user with name **ReportPasswordNeverExpires.csv**</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Csv -NoTypeInformation | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.csv

## Set a password to never expire

Run one of the following commands:

- To set the password of one user to never expire, run the following cmdlet by using the UPN or the user ID of the user:

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies DisablePasswordExpiration
    ```

- <span data-ttu-id="11ea8-125">組織内のすべてのユーザーのパスワードを期限切れにならないように設定するには、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="11ea8-125">To set the passwords of all the users in an organization to never expire, run the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies DisablePasswordExpiration
    ```

### <a name="set-a-password-to-expire"></a><span data-ttu-id="11ea8-126">パスワードの有効期限を設定する</span><span class="sxs-lookup"><span data-stu-id="11ea8-126">Set a password to expire</span></span>

<span data-ttu-id="11ea8-127">次のいずれかのコマンドを実行します：</span><span class="sxs-lookup"><span data-stu-id="11ea8-127">Run one of the following commands:</span></span>

- <span data-ttu-id="11ea8-128">パスワードの有効期限が切れるように1人のユーザーのパスワードを設定するには、UPN またはユーザーのユーザー ID を使用して次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="11ea8-128">To set the password of one user so that the password expires, run the following cmdlet by using the UPN or the user ID of the user:</span></span>

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies None
    ```

- <span data-ttu-id="11ea8-129">組織内のすべてのユーザーのパスワードを期限切れになるように設定するには、次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="11ea8-129">To set the passwords of all users in the organization so that they expire, use the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies None
    ```

> [!WARNING]
> <span data-ttu-id="11ea8-130">パラメーターを使用して構成されたユーザーアカウント `-PasswordPolicies DisablePasswordExpiration` は、ユーザーアカウント属性に基づいてエージングを維持し `pwdLastSet` ます。</span><span class="sxs-lookup"><span data-stu-id="11ea8-130">User accounts configured with the `-PasswordPolicies DisablePasswordExpiration` parameter still age based on the `pwdLastSet` user account attribute.</span></span> <span data-ttu-id="11ea8-131">たとえば、ユーザーのパスワードを期限切れにしないように設定してから90日以上経過した場合、パスワードの有効期限はまだ切れません。</span><span class="sxs-lookup"><span data-stu-id="11ea8-131">For example, if you set user passwords to never expire and then 90 or more days go by, the passwords still expire.</span></span> <span data-ttu-id="11ea8-132">ユーザー `pwdLastSet` アカウント属性に基づいて、パラメーターで構成されたユーザーアカウントの場合、 `-PasswordPolicies None` 90 日より前のパスワードはすべて、 `pwdLastSet` 次にサインインするときにユーザーを変更する必要があります。この変更によって、多数のユーザーに影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="11ea8-132">Based on the `pwdLastSet` user account attribute, for user accounts configured with the `-PasswordPolicies None` parameter, all passwords that have a `pwdLastSet` older than 90 days require the user to change them the next time they sign in.This change can affect a large number of users.</span></span>

## <a name="related-content"></a><span data-ttu-id="11ea8-133">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="11ea8-133">Related content</span></span>

[<span data-ttu-id="11ea8-134">ユーザーが自分でパスワードをリセットできるようにする</span><span class="sxs-lookup"><span data-stu-id="11ea8-134">Let users reset their own passwords</span></span>](../add-users/let-users-reset-passwords.md)

[<span data-ttu-id="11ea8-135">パスワードをリセットする</span><span class="sxs-lookup"><span data-stu-id="11ea8-135">Reset passwords</span></span>](../add-users/reset-passwords.md)