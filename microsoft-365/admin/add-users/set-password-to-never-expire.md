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
description: Windows PowerShellを使用して、一部のユーザーパスワードが期限切れにならない場合は、Microsoft 365管理者アカウントにサインインします。
ms.openlocfilehash: 0747e0bfe8a7389db554d5d6a7f685605e013306
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2021
ms.locfileid: "52571927"
---
# <a name="set-an-individual-users-password-to-never-expire"></a><span data-ttu-id="581f5-103">個別のユーザーのパスワードを無期限に設定する</span><span class="sxs-lookup"><span data-stu-id="581f5-103">Set an individual user's password to never expire</span></span>

<span data-ttu-id="581f5-104">この資料では、個々のユーザーが期限切れにならないパスワードを設定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="581f5-104">This article explains how to set a password for an individual user to not expire.</span></span> <span data-ttu-id="581f5-105">PowerShell を使用してこれらの手順を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="581f5-105">You have to complete these steps using PowerShell.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="581f5-106">開始する前に</span><span class="sxs-lookup"><span data-stu-id="581f5-106">Before you begin</span></span>

<span data-ttu-id="581f5-107">この記事は、職場、学校、または非営利団体のパスワードの有効期限ポリシーを設定する管理者を対象としています。</span><span class="sxs-lookup"><span data-stu-id="581f5-107">This article is for people who set password expiration policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="581f5-108">これらの手順を完了するには、Microsoft 365 の管理者アカウントでサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="581f5-108">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> <span data-ttu-id="581f5-109">[管理者アカウントとは](../../business-video/admin-center-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="581f5-109">[What's an admin account?](../../business-video/admin-center-overview.md).</span></span> 

<span data-ttu-id="581f5-110">これらの手順を実行するには、 [グローバル管理者またはパスワード管理者](about-admin-roles.md) である必要があります。</span><span class="sxs-lookup"><span data-stu-id="581f5-110">You must be an [global admin or password administrator](about-admin-roles.md) to perform these steps.</span></span>

<span data-ttu-id="581f5-111">Microsoft クラウド サービスのグローバル管理者は[、Graphに Azure Active Directory PowerShell を](/powershell/azure/active-directory/install-adv2?view=azureadps-2.0)使用して、特定のユーザーに対してパスワードの有効期限が切れないように設定できます。</span><span class="sxs-lookup"><span data-stu-id="581f5-111">A global admin for a Microsoft cloud service can use the [Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2?view=azureadps-2.0) to set passwords not to expire for specific users.</span></span> <span data-ttu-id="581f5-112">[また、AzureAD](/powershell/module/Azuread)コマンドレットを使用して、無期限の構成を削除したり、どのユーザー パスワードが期限切れに設定されているかを確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="581f5-112">You can also use [AzureAD](/powershell/module/Azuread) cmdlets to remove the never-expires configuration or to see which user passwords are set to never expire.</span></span>

<span data-ttu-id="581f5-113">このガイドは、Id サービスとディレクトリ サービスを Azure AD に依存する Intune や Microsoft 365 などの他のプロバイダーにも適用されます。</span><span class="sxs-lookup"><span data-stu-id="581f5-113">This guide applies to other providers, such as Intune and Microsoft 365, which also rely on Azure AD for identity and directory services.</span></span> <span data-ttu-id="581f5-114">パスワードの有効期限は、ポリシーの変更可能な唯一の部分です。</span><span class="sxs-lookup"><span data-stu-id="581f5-114">Password expiration is the only part of the policy that can be changed.</span></span>

> [!NOTE]
> <span data-ttu-id="581f5-115">ディレクトリ同期を通じて同期されないユーザー アカウントのパスワードのみを期限切れに設定できます。</span><span class="sxs-lookup"><span data-stu-id="581f5-115">Only passwords for user accounts that are not synchronized through directory synchronization can be configured to not expire.</span></span> <span data-ttu-id="581f5-116">ディレクトリ同期の詳細については[、「Azure AD を使用Connect AD」](/azure/active-directory/connect/active-directory-aadconnect)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="581f5-116">For more information about directory synchronization, see [Connect AD with Azure AD](/azure/active-directory/connect/active-directory-aadconnect).</span></span>

## <a name="how-to-check-the-expiration-policy-for-a-password"></a><span data-ttu-id="581f5-117">パスワードの有効期限ポリシーを確認する方法</span><span class="sxs-lookup"><span data-stu-id="581f5-117">How to check the expiration policy for a password</span></span>

<span data-ttu-id="581f5-118">AzureAD モジュールのGet-AzureADUser コマンドの詳細については、参照記事 [「Get-AzureADUser」](/powershell/module/Azuread/Get-AzureADUser?view=azureadps-2.0)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="581f5-118">For more information about the Get-AzureADUser command in the AzureAD module, see the reference article [Get-AzureADUser](/powershell/module/Azuread/Get-AzureADUser?view=azureadps-2.0).</span></span>

<span data-ttu-id="581f5-119">次のいずれかのコマンドを実行します：</span><span class="sxs-lookup"><span data-stu-id="581f5-119">Run one of the following commands:</span></span>

- <span data-ttu-id="581f5-120">1 人のユーザーのパスワードが無期限に設定されているかどうかを確認するには、UPN *(user@contoso.onmicrosoft.com)* など) または確認するユーザーのユーザー ID を使用して、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="581f5-120">To see if a single user's password is set to never expire, run the following cmdlet by using the UPN (for example, *user@contoso.onmicrosoft.com*) or the user ID of the user you want to check:</span></span>

    ```powershell
    Get-AzureADUser -ObjectId <user id or UPN> | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```

    <span data-ttu-id="581f5-121">例:</span><span class="sxs-lookup"><span data-stu-id="581f5-121">Example:</span></span>

    ```powershell
    Get-AzureADUser -ObjectId userUPN@contoso.com | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```  

- <span data-ttu-id="581f5-122">すべてのユーザーの **[パスワードを無期限** にする] 設定を表示するには、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="581f5-122">To see the **Password never expires** setting for all users, run the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
     }
    ```

- <span data-ttu-id="581f5-123">名前が l の現在のユーザーのデスクトップ上の Html でパスワードを持つすべてのユーザーのレポート **ReportPasswordNeverExpires.htm** 取得するには</span><span class="sxs-lookup"><span data-stu-id="581f5-123">To get a report of all the users with PasswordNeverExpires in Html on the desktop of the current user with name  **ReportPasswordNeverExpires.html**</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Html | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.html
    ```  

- <span data-ttu-id="581f5-124">名前が **ReportPasswordNeverExpires.csv** の現在のユーザーのデスクトップ上の CSV でパスワードを持つすべてのユーザーのレポートを取得するには</span><span class="sxs-lookup"><span data-stu-id="581f5-124">To get a report of all the users with PasswordNeverExpires in CSV on the desktop of the current user with name **ReportPasswordNeverExpires.csv**</span></span>

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

- <span data-ttu-id="581f5-125">組織内のすべてのユーザーのパスワードを無期限に設定するには、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="581f5-125">To set the passwords of all the users in an organization to never expire, run the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies DisablePasswordExpiration
    ```

> [!WARNING]
> <span data-ttu-id="581f5-126">パラメータを使用して構成されたユーザー アカウント `-PasswordPolicies DisablePasswordExpiration` は、属性に基づいて経過時間が残っています `pwdLastSet` 。</span><span class="sxs-lookup"><span data-stu-id="581f5-126">User accounts configured with the `-PasswordPolicies DisablePasswordExpiration` parameter still age based on the `pwdLastSet` attribute.</span></span> <span data-ttu-id="581f5-127">属性に基づいて `pwdLastSet` 、有効期限を に変更した場合 `-PasswordPolicies None` 、90 日を超える pwdLastSet を持つすべてのパスワードは、ユーザーが次回サインインするときに変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="581f5-127">Based on the `pwdLastSet` attribute, if you change the expiration to `-PasswordPolicies None`, all passwords that have a pwdLastSet older than 90 days require the user to change them the next time they sign in.</span></span> <span data-ttu-id="581f5-128">この変更は、多数のユーザーに影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="581f5-128">This change can affect a large number of users.</span></span>

### <a name="set-a-password-to-expire"></a><span data-ttu-id="581f5-129">パスワードを期限切れに設定する</span><span class="sxs-lookup"><span data-stu-id="581f5-129">Set a password to expire</span></span>

<span data-ttu-id="581f5-130">次のいずれかのコマンドを実行します：</span><span class="sxs-lookup"><span data-stu-id="581f5-130">Run one of the following commands:</span></span>

- <span data-ttu-id="581f5-131">パスワードの有効期限が切れるように 1 人のユーザーのパスワードを設定するには、UPN またはユーザーのユーザー ID を使用して次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="581f5-131">To set the password of one user so that the password expires, run the following cmdlet by using the UPN or the user ID of the user:</span></span>

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies None
    ```

- <span data-ttu-id="581f5-132">組織内のすべてのユーザーのパスワードを設定して有効期限が切れるようにするには、次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="581f5-132">To set the passwords of all users in the organization so that they expire, use the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies None
    ```

## <a name="related-content"></a><span data-ttu-id="581f5-133">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="581f5-133">Related content</span></span>

<span data-ttu-id="581f5-134">[ユーザーが自分でパスワードをリセットできるようにする](../add-users/let-users-reset-passwords.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="581f5-134">[Let users reset their own passwords](../add-users/let-users-reset-passwords.md) (article)</span></span>

<span data-ttu-id="581f5-135">[パスワードをリセットする](../add-users/reset-passwords.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="581f5-135">[Reset passwords](../add-users/reset-passwords.md) (article)</span></span>