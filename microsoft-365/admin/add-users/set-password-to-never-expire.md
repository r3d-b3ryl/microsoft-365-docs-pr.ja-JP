---
title: 個別のユーザーのパスワードを無期限に設定する
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
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
ms.openlocfilehash: 6562a4092c47d9c4bf7bf294767e6050a3e0577a
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "44387007"
---
# <a name="set-an-individual-users-password-to-never-expire"></a><span data-ttu-id="747ca-103">個別のユーザーのパスワードを無期限に設定する</span><span class="sxs-lookup"><span data-stu-id="747ca-103">Set an individual user's password to never expire</span></span>

## <a name="set-the-password-expiration-policy-for-your-organization"></a><span data-ttu-id="747ca-104">組織のパスワード有効期限ポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="747ca-104">Set the password expiration policy for your organization</span></span>

1. <span data-ttu-id="747ca-105">管理センターで、[**設定**の \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">設定</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="747ca-105">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Settings</a> page.</span></span>
2. <span data-ttu-id="747ca-106">[設定] ページの上部で、[**セキュリティ & プライバシー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="747ca-106">At the top of the Settings page select **Security & Privacy**.</span></span>
3. <span data-ttu-id="747ca-107">[**パスワードの有効期限ポリシー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="747ca-107">Select **Password expiration policy**.</span></span> 
4. <span data-ttu-id="747ca-108">パスワードが期限切れにならないように設定されている場合は、[**ユーザーのパスワードの有効期限を何日後に設定**する] の横にあるチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="747ca-108">If passwords are set to never expire, click the check box next to **Set user passwords to expire after a number of days**.</span></span> <span data-ttu-id="747ca-109">パスワードが期限切れになるまでの日数を指定するオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="747ca-109">You'll get the option to specify the number of days until passwords expire.</span></span>

## <a name="set-the-password-expiration-policy-for-individual-users"></a><span data-ttu-id="747ca-110">個々のユーザーのパスワードの有効期限ポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="747ca-110">Set the password expiration policy for individual users</span></span>

<span data-ttu-id="747ca-111">Microsoft クラウドサービスのグローバル管理者は、 [Azure Active Directory PowerShell For Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0)を使用して、特定のユーザーに対してパスワードを無期限に設定することができます。</span><span class="sxs-lookup"><span data-stu-id="747ca-111">A global admin for a Microsoft cloud service can use the [Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0) to set passwords not to expire for specific users.</span></span> <span data-ttu-id="747ca-112">また、 [AzureAD](https://docs.microsoft.com/powershell/module/Azuread)コマンドレットを使用して、無期限の構成を削除したり、どのユーザーのパスワードが期限切れにならないかを確認したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="747ca-112">You can also use [AzureAD](https://docs.microsoft.com/powershell/module/Azuread) cmdlets to remove the never-expires configuration or to see which user passwords are set to never expire.</span></span>

<span data-ttu-id="747ca-113">このガイドは、Intune や Microsoft 365 などの他のプロバイダーに適用されます。これは、id およびディレクトリサービスのために Azure AD にも依存しています。</span><span class="sxs-lookup"><span data-stu-id="747ca-113">This guide applies to other providers, such as Intune and Microsoft 365, which also rely on Azure AD for identity and directory services.</span></span> <span data-ttu-id="747ca-114">ポリシーの変更可能な部分は、パスワードの有効期限のみです。</span><span class="sxs-lookup"><span data-stu-id="747ca-114">Password expiration is the only part of the policy that can be changed.</span></span>

<span data-ttu-id="747ca-115">Graph の Azure AD PowerShell の詳細については、「 [Azure Active Directory powershell For graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="747ca-115">For more information about Azure AD PowerShell for Graph, see [Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0).</span></span>

> [!NOTE]
> <span data-ttu-id="747ca-116">ディレクトリ同期によって同期されていないユーザーアカウントのパスワードのみ、期限切れにならないように構成できます。</span><span class="sxs-lookup"><span data-stu-id="747ca-116">Only passwords for user accounts that are not synchronized through directory synchronization can be configured to not expire.</span></span> <span data-ttu-id="747ca-117">ディレクトリ同期の詳細については、「 [CONNECT ad With AZURE ad](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="747ca-117">For more information about directory synchronization, see [Connect AD with Azure AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span></span>

### <a name="how-to-check-the-expiration-policy-for-a-password"></a><span data-ttu-id="747ca-118">パスワードの有効期限ポリシーを確認する方法</span><span class="sxs-lookup"><span data-stu-id="747ca-118">How to check the expiration policy for a password</span></span>

<span data-ttu-id="747ca-119">AzureAD モジュールの Set-azureaduser コマンドの詳細については、「 [set-azureaduser](https://docs.microsoft.com/powershell/module/Azuread/Get-AzureADUser?view=azureadps-2.0)」という参照記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="747ca-119">For more information about the Get-AzureADUser command in the AzureAD module, see the reference article [Get-AzureADUser](https://docs.microsoft.com/powershell/module/Azuread/Get-AzureADUser?view=azureadps-2.0).</span></span>

<span data-ttu-id="747ca-120">次のいずれかのコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="747ca-120">Run one of the following commands:</span></span>

- <span data-ttu-id="747ca-121">単一のユーザーのパスワードが期限切れにならないように設定されているかどうかを確認するには、UPN (たとえば、 *user@contoso.onmicrosoft.com*) またはチェックするユーザーのユーザー ID を使用して、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="747ca-121">To see if a single user's password is set to never expire, run the following cmdlet by using the UPN (for example, *user@contoso.onmicrosoft.com*) or the user ID of the user you want to check:</span></span>

    ```powershell
    Get-AzureADUser -ObjectId <user id or UPN> | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```

    <span data-ttu-id="747ca-122">例:</span><span class="sxs-lookup"><span data-stu-id="747ca-122">Example:</span></span>

    ```powershell
    Get-AzureADUser -ObjectId userUPN@contoso.com | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```  

- <span data-ttu-id="747ca-123">すべてのユーザーの**パスワードの有効期限**が設定されていないことを確認するには、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="747ca-123">To see the **Password never expires** setting for all users, run the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
     }
    ```

- <span data-ttu-id="747ca-124">**ReportPasswordNeverExpires**という名前の現在のユーザーのデスクトップに Html で PasswordNeverExpires を持つすべてのユーザーのレポートを取得するには</span><span class="sxs-lookup"><span data-stu-id="747ca-124">To get a report of all the users with PasswordNeverExpires in Html on the desktop of the current user with name  **ReportPasswordNeverExpires.html**</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Html | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.html
    ```  

- <span data-ttu-id="747ca-125">**ReportPasswordNeverExpires**という名前の現在のユーザーのデスクトップに Csv で PasswordNeverExpires を持つすべてのユーザーのレポートを取得するには</span><span class="sxs-lookup"><span data-stu-id="747ca-125">To get a report of all the users with PasswordNeverExpires in CSV on the desktop of the current user with name **ReportPasswordNeverExpires.csv**</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Csv -NoTypeInformation | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.csv
    ```

### <a name="set-a-password-to-expire"></a><span data-ttu-id="747ca-126">パスワードの有効期限を設定する</span><span class="sxs-lookup"><span data-stu-id="747ca-126">Set a password to expire</span></span>

<span data-ttu-id="747ca-127">次のいずれかのコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="747ca-127">Run one of the following commands:</span></span>

- <span data-ttu-id="747ca-128">パスワードの有効期限が切れるように1人のユーザーのパスワードを設定するには、UPN またはユーザーのユーザー ID を使用して次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="747ca-128">To set the password of one user so that the password expires, run the following cmdlet by using the UPN or the user ID of the user:</span></span>

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies None
    ```

- <span data-ttu-id="747ca-129">組織内のすべてのユーザーのパスワードを期限切れになるように設定するには、次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="747ca-129">To set the passwords of all users in the organization so that they expire, use the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies None
    ```

### <a name="set-a-password-to-never-expire"></a><span data-ttu-id="747ca-130">パスワードを無期限に設定する</span><span class="sxs-lookup"><span data-stu-id="747ca-130">Set a password to never expire</span></span>

<span data-ttu-id="747ca-131">次のいずれかのコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="747ca-131">Run one of the following commands:</span></span>

- <span data-ttu-id="747ca-132">1人のユーザーのパスワードを無期限に設定するには、UPN またはユーザーのユーザー ID を使用して次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="747ca-132">To set the password of one user to never expire, run the following cmdlet by using the UPN or the user ID of the user:</span></span>

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies DisablePasswordExpiration
    ```

- <span data-ttu-id="747ca-133">組織内のすべてのユーザーのパスワードを期限切れにならないように設定するには、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="747ca-133">To set the passwords of all the users in an organization to never expire, run the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies DisablePasswordExpiration
    ```

> [!WARNING]
> <span data-ttu-id="747ca-134">パスワード `-PasswordPolicies DisablePasswordExpiration` は属性に基づいてエージングが設定さ `pwdLastSet` れています。</span><span class="sxs-lookup"><span data-stu-id="747ca-134">Passwords set to `-PasswordPolicies DisablePasswordExpiration` still age based on the `pwdLastSet` attribute.</span></span> <span data-ttu-id="747ca-135">ユーザーのパスワードの有効期限が切れないように設定してから90日後に移行すると、パスワードの有効期限が切れます。</span><span class="sxs-lookup"><span data-stu-id="747ca-135">If you set the user passwords to never expire and then 90+ days go by, the passwords expire.</span></span> <span data-ttu-id="747ca-136">属性に基づいて、 `pwdLastSet` 有効期限を変更した場合、90日より前のパスワードについては、 `-PasswordPolicies None` 次に `pwdLastSet` サインインするときにユーザーを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="747ca-136">Based on the `pwdLastSet` attribute, if you change the expiration to `-PasswordPolicies None`, all passwords that have a `pwdLastSet` older than 90 days require the user to change them the next time they sign in.</span></span> <span data-ttu-id="747ca-137">この変更によって、多数のユーザーに影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="747ca-137">This change can affect a large number of users.</span></span>
