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
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: f493e3af-e1d8-4668-9211-230c245a0466
description: 管理者アカウントにサインインMicrosoft 365を使用して、個々のユーザー パスワードを有効期限が切れWindows PowerShell。
ms.openlocfilehash: 29d0ebcbb3f9fb197e574731e23aaa64c2fa7894
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "53394257"
---
# <a name="set-an-individual-users-password-to-never-expire"></a><span data-ttu-id="80d83-103">個別のユーザーのパスワードを無期限に設定する</span><span class="sxs-lookup"><span data-stu-id="80d83-103">Set an individual user's password to never expire</span></span>

<span data-ttu-id="80d83-104">この記事では、個々のユーザーのパスワードを期限切れにしない設定方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="80d83-104">This article explains how to set a password for an individual user to not expire.</span></span> <span data-ttu-id="80d83-105">PowerShell を使用してこれらの手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="80d83-105">You have to complete these steps using PowerShell.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="80d83-106">開始する前に</span><span class="sxs-lookup"><span data-stu-id="80d83-106">Before you begin</span></span>

<span data-ttu-id="80d83-107">この記事は、職場、学校、または非営利団体のパスワードの有効期限ポリシーを設定する管理者を対象としています。</span><span class="sxs-lookup"><span data-stu-id="80d83-107">This article is for people who set password expiration policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="80d83-108">これらの手順を完了するには、Microsoft 365 の管理者アカウントでサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="80d83-108">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> <span data-ttu-id="80d83-109">[管理者アカウントとは](../../business-video/admin-center-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="80d83-109">[What's an admin account?](../../business-video/admin-center-overview.md).</span></span>

<span data-ttu-id="80d83-110">これらの手順を実行するには [、グローバル管理者またはパスワード](about-admin-roles.md) 管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="80d83-110">You must be an [global admin or password administrator](about-admin-roles.md) to perform these steps.</span></span>

<span data-ttu-id="80d83-111">Microsoft クラウド サービスのグローバル管理者は、Azure Active Directory [PowerShell](/powershell/azure/active-directory/install-adv2)を使用して、Graphユーザーに対して有効期限が切れないパスワードを設定できます。</span><span class="sxs-lookup"><span data-stu-id="80d83-111">A global admin for a Microsoft cloud service can use the [Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2) to set passwords not to expire for specific users.</span></span> <span data-ttu-id="80d83-112">AzureAD コマンドレット [を使用して](/powershell/module/Azuread) 、有効期限が切れない構成を削除したり、有効期限が切れないユーザー パスワードを確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="80d83-112">You can also use [AzureAD](/powershell/module/Azuread) cmdlets to remove the never-expires configuration or to see which user passwords are set to never expire.</span></span>

<span data-ttu-id="80d83-113">このガイドは、Intune や Microsoft 365 などの他のプロバイダーにも適用されます。これは、Azure AD ID およびディレクトリ サービスにも依存します。</span><span class="sxs-lookup"><span data-stu-id="80d83-113">This guide applies to other providers, such as Intune and Microsoft 365, which also rely on Azure AD for identity and directory services.</span></span> <span data-ttu-id="80d83-114">パスワードの有効期限は、変更できるポリシーの唯一の部分です。</span><span class="sxs-lookup"><span data-stu-id="80d83-114">Password expiration is the only part of the policy that can be changed.</span></span>


## <a name="how-to-check-the-expiration-policy-for-a-password"></a><span data-ttu-id="80d83-115">パスワードの有効期限ポリシーを確認する方法</span><span class="sxs-lookup"><span data-stu-id="80d83-115">How to check the expiration policy for a password</span></span>

<span data-ttu-id="80d83-116">AzureAD モジュールの Get-AzureADUser コマンドの詳細については、参照記事 [Get-AzureADUser を参照してください](/powershell/module/Azuread/Get-AzureADUser)。</span><span class="sxs-lookup"><span data-stu-id="80d83-116">For more information about the Get-AzureADUser command in the AzureAD module, see the reference article [Get-AzureADUser](/powershell/module/Azuread/Get-AzureADUser).</span></span>

<span data-ttu-id="80d83-117">次のいずれかのコマンドを実行します：</span><span class="sxs-lookup"><span data-stu-id="80d83-117">Run one of the following commands:</span></span>

- <span data-ttu-id="80d83-118">1 人のユーザーのパスワードが有効期限が切れないに設定されている場合は *、UPN (user@contoso.onmicrosoft.com* など) または確認するユーザーのユーザー ID を使用して、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="80d83-118">To see if a single user's password is set to never expire, run the following cmdlet by using the UPN (for example, *user@contoso.onmicrosoft.com*) or the user ID of the user you want to check:</span></span>

    ```powershell
    Get-AzureADUser -ObjectId <user id or UPN> | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```

    <span data-ttu-id="80d83-119">例:</span><span class="sxs-lookup"><span data-stu-id="80d83-119">Example:</span></span>

    ```powershell
    Get-AzureADUser -ObjectId userUPN@contoso.com | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```

- <span data-ttu-id="80d83-120">すべてのユーザーに **対して [パスワードの有効期限が切** れることはありません] 設定を表示するには、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="80d83-120">To see the **Password never expires** setting for all users, run the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
     }
    ```

- <span data-ttu-id="80d83-121">現在のユーザーのデスクトップで PasswordNeverExpires を Html で持つすべてのユーザーのレポートを取得するには、ReportPasswordNeverExpires.htm **l**</span><span class="sxs-lookup"><span data-stu-id="80d83-121">To get a report of all the users with PasswordNeverExpires in Html on the desktop of the current user with name  **ReportPasswordNeverExpires.html**</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Html | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.html
    ```

- <span data-ttu-id="80d83-122">現在のユーザーのデスクトップで PasswordNeverExpires を CSV で持つすべてのユーザーのレポートを取得 **するには**、名前を付ReportPasswordNeverExpires.csv</span><span class="sxs-lookup"><span data-stu-id="80d83-122">To get a report of all the users with PasswordNeverExpires in CSV on the desktop of the current user with name **ReportPasswordNeverExpires.csv**</span></span>

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

- <span data-ttu-id="80d83-123">組織内のすべてのユーザーのパスワードに有効期限を設定するには、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="80d83-123">To set the passwords of all the users in an organization to never expire, run the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies DisablePasswordExpiration
    ```

> [!WARNING]
> <span data-ttu-id="80d83-124">パラメーターを使用して構成された `-PasswordPolicies DisablePasswordExpiration` ユーザー アカウントは、属性に基づいて年齢を変更 `pwdLastSet` します。</span><span class="sxs-lookup"><span data-stu-id="80d83-124">User accounts configured with the `-PasswordPolicies DisablePasswordExpiration` parameter still age based on the `pwdLastSet` attribute.</span></span> <span data-ttu-id="80d83-125">属性に基づいて、有効期限をに変更した場合 `pwdLastSet` 、pwdLastSet が 90 日を超えるすべてのパスワードでは、次回サインイン時にパスワードを変更する必要があります `-PasswordPolicies None` 。</span><span class="sxs-lookup"><span data-stu-id="80d83-125">Based on the `pwdLastSet` attribute, if you change the expiration to `-PasswordPolicies None`, all passwords that have a pwdLastSet older than 90 days require the user to change them the next time they sign in.</span></span> <span data-ttu-id="80d83-126">この変更は、多数のユーザーに影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="80d83-126">This change can affect a large number of users.</span></span>

### <a name="set-a-password-to-expire"></a><span data-ttu-id="80d83-127">パスワードの有効期限を設定する</span><span class="sxs-lookup"><span data-stu-id="80d83-127">Set a password to expire</span></span>

<span data-ttu-id="80d83-128">次のいずれかのコマンドを実行します：</span><span class="sxs-lookup"><span data-stu-id="80d83-128">Run one of the following commands:</span></span>

- <span data-ttu-id="80d83-129">パスワードの有効期限が切れる 1 人のユーザーのパスワードを設定するには、UPN またはユーザーのユーザー ID を使用して次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="80d83-129">To set the password of one user so that the password expires, run the following cmdlet by using the UPN or the user ID of the user:</span></span>

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies None
    ```

- <span data-ttu-id="80d83-130">組織内のすべてのユーザーのパスワードを期限切れに設定するには、次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="80d83-130">To set the passwords of all users in the organization so that they expire, use the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies None
    ```

## <a name="related-content"></a><span data-ttu-id="80d83-131">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="80d83-131">Related content</span></span>

<span data-ttu-id="80d83-132">[ユーザーが自分でパスワードをリセットできるようにする](../add-users/let-users-reset-passwords.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="80d83-132">[Let users reset their own passwords](../add-users/let-users-reset-passwords.md) (article)</span></span>\
<span data-ttu-id="80d83-133">[パスワードをリセットする](../add-users/reset-passwords.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="80d83-133">[Reset passwords](../add-users/reset-passwords.md) (article)</span></span>\
<span data-ttu-id="80d83-134">[組織のパスワード有効期限ポリシーを設定する](../manage/set-password-expiration-policy.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="80d83-134">[Set the password expiration policy for your organization](../manage/set-password-expiration-policy.md) (article)</span></span>
