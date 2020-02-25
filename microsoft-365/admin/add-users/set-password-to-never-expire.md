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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: f493e3af-e1d8-4668-9211-230c245a0466
description: Windows PowerShell を使用して、一部のユーザーパスワードを期限切れにしないように設定する方法について説明します。
ms.openlocfilehash: 1c44f5c4d5966d70b5fed0b1b99e69b2938c6ddd
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2020
ms.locfileid: "42241571"
---
# <a name="set-an-individual-users-password-to-never-expire"></a>個別のユーザーのパスワードを無期限に設定する

## <a name="set-the-password-expiration-policy-for-your-organization"></a>組織のパスワード有効期限ポリシーを設定します。

1. 管理センターで、[**設定**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">セキュリティとプライバシー</a>] ページの順に移動します。
2. [**パスワードポリシー** ] の横にある [**編集**] を選択します。 
3. パスワードが期限切れにならないように設定されている場合は、[**オフ**] に切り替えます。 パスワードが期限切れになるまでの日数を指定するオプションが表示されます。 


## <a name="set-the-password-expiration-policy-for-individual-users"></a>個々のユーザーのパスワードの有効期限ポリシーを設定する 

Microsoft クラウドサービスのグローバル管理者は、Windows PowerShell 用 Microsoft Azure AD モジュールを使用して、特定のユーザーに対してパスワードを無期限に設定することができます。 また、Windows PowerShell コマンドレットを使用して、無期限の構成を削除したり、どのユーザーのパスワードが期限切れにならないかを確認したりすることもできます。 

このガイドは、Intune や Office 365 などの他のプロバイダーに適用されます。これは、id およびディレクトリサービスのために Azure AD にも依存しています。 ポリシーの変更可能な部分は、パスワードの有効期限のみです。

> [!NOTE]
> ディレクトリ同期によって同期されていないユーザーアカウントのパスワードのみ、期限切れにならないように構成できます。 ディレクトリ同期の詳細については、「 [CONNECT ad With AZURE ad](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)」を参照してください。


### <a name="how-to-check-the-expiration-policy-for-a-password"></a>パスワードの有効期限ポリシーを確認する方法

* 次のいずれかのコマンドを実行します。

   * 単一のユーザーのパスワードが期限切れにならないように設定されているかどうかを確認するには、UPN (たとえば、 *user@contoso.onmicrosoft.com*) またはチェックするユーザーのユーザー ID を使用して、次のコマンドレットを実行します。
```
Get-AzureADUser -ObjectId <user id or UPN> | Select-Object UserprincipalName,@{
    N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
 }
```  
例:
```
Get-AzureADUser -ObjectId userUPN@contoso.com | Select-Object UserprincipalName,@{
    N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
 }
```  

 * すべてのユーザーの**パスワードの有効期限**が設定されていないことを確認するには、次のコマンドレットを実行します。 
 
```
Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
    N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
 }
```  

* **ReportPasswordNeverExpires**という名前の現在のユーザーのデスクトップに Html で PasswordNeverExpires を持つすべてのユーザーのレポートを取得するには


```
Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
    N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
} | ConvertTo-Html | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.html
```  

* **ReportPasswordNeverExpires**という名前の現在のユーザーのデスクトップに Csv で PasswordNeverExpires を持つすべてのユーザーのレポートを取得するには


```
Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
    N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
} | ConvertTo-Csv -NoTypeInformation | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.csv
```  


### <a name="set-a-password-to-expire"></a>パスワードの有効期限を設定する

次のいずれかのコマンドを実行します。

   * パスワードの有効期限が切れるように1人のユーザーのパスワードを設定するには、UPN またはユーザーのユーザー ID を使用して次のコマンドレットを実行します。

```
 Set-AzureADUser -ObjectId <user ID> -PasswordPolicies None

```
   * 組織内のすべてのユーザーのパスワードを期限切れになるように設定するには、次のコマンドレットを使用します。

```
 Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies None

```
### <a name="set-a-password-to-never-expire"></a>パスワードを無期限に設定する

次のいずれかのコマンドを実行します。

   * 1人のユーザーのパスワードを無期限に設定するには、UPN またはユーザーのユーザー ID を使用して次のコマンドレットを実行します。 

```
Set-AzureADUser -ObjectId <user ID> -PasswordPolicies DisablePasswordExpiration

```
   * 組織内のすべてのユーザーのパスワードを期限切れにならないように設定するには、次のコマンドレットを実行します。 

```
Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies DisablePasswordExpiration

```
   > [!WARNING]
   > パスワードは`pwdLastSet`属性`-PasswordPolicies DisablePasswordExpiration`に基づいてエージングが設定されています。 ユーザーのパスワードの有効期限が切れないように設定してから90日後に移行すると、パスワードの有効期限が切れます。 `pwdLastSet`属性に基づいて、有効期限を`-PasswordPolicies None`変更した場合、90日より`pwdLastSet`前のパスワードについては、次にサインインするときにユーザーを変更する必要があります。 この変更によって、多数のユーザーに影響を与える可能性があります。 
