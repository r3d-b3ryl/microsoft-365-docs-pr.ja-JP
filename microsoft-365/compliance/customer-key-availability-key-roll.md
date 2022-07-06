---
title: カスタマー キーまたは可用性キーをローリングまたはローテーションする
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: カスタマー キーで使用される Azure Key Vaultに格納されている顧客ルート キーをロールする方法について説明します。 サービスには、Exchange Online、Skype for Business、SharePoint Online、OneDrive for Business、Teams ファイルが含まれます。
ms.openlocfilehash: 474df9b4776df09b4a46ca002f506155606bdb52
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2022
ms.locfileid: "66636493"
---
# <a name="roll-or-rotate-a-customer-key-or-an-availability-key"></a>カスタマー キーまたは可用性キーをローリングまたはローテーションする

> [!CAUTION]
> カスタマー キーで使用する暗号化キーは、セキュリティ要件またはコンプライアンス要件でキーをロールする必要がある場合にのみロールします。 また、ポリシーに関連付けられているキーや関連付けられているキーは削除しないでください。 キーをロールすると、前のキーで暗号化されたコンテンツが表示されます。 たとえば、アクティブなメールボックスは頻繁に再暗号化されますが、非アクティブ、切断、無効のメールボックスは、前のキーで暗号化される場合があります。 SharePoint Online では、復元と回復の目的でコンテンツのバックアップが実行されるため、古いキーを使用してアーカイブされたコンテンツが引き続き存在する可能性があります。

## <a name="about-rolling-the-availability-key"></a>可用性キーのローリングについて

Microsoft は、可用性キーの直接制御を顧客に公開しません。 たとえば、Azure Key Vaultで所有しているキーのみをロール (ローテーション) できます。 Microsoft 365 は、内部的に定義されたスケジュールで可用性キーをロールします。 これらのキー ロールには、顧客向けのサービス レベル アグリーメント (SLA) はありません。 Microsoft 365 では、Microsoft 365 サービス コードを使用して、手動以外の自動化されたプロセスで可用性キーをローテーションします。 Microsoft 管理者は、ロール プロセスを開始できます。 キーは、キー ストアに直接アクセスすることなく、自動化されたメカニズムを使用してロールされます。 可用性キー シークレット ストアへのアクセスは、Microsoft 管理者にはプロビジョニングされません。 可用性キーローリングでは、キーを最初に生成するために使用されるのと同じメカニズムが利用されます。 可用性キーの詳細については、「可用性キー [について」](customer-key-availability-key-understand.md)を参照してください。

> [!IMPORTANT]
> Exchange OnlineおよびSkype for Business可用性キーは、新しい DEP を作成する顧客によって効果的にロールできます。これは、作成する DEP ごとに一意の可用性キーが生成されるためです。 SharePoint Online、OneDrive for Business、Teams ファイルの可用性キーはフォレスト レベルで存在し、DEP と顧客間で共有されます。つまり、ローリングは Microsoft の内部定義されたスケジュールでのみ行われます。 新しい DEP が作成されるたびに可用性キーをローリングしないリスクを軽減するために、SharePoint、OneDrive、Teams は、新しい DEP が作成されるたびに、顧客のルート キーと可用性キーでラップされたキーであるテナント中間キー (TIK) をロールします。

## <a name="request-a-new-version-of-each-existing-root-key-you-want-to-roll"></a>ロールする既存の各ルート キーの新しいバージョンを要求する

キーをロールする場合は、既存のキーの新しいバージョンを要求します。 既存のキーの新しいバージョンを要求するには、最初にキーの作成に使用したのと同じ構文で、同じコマンドレット [Add-AzKeyVaultKey](/powershell/module/az.keyvault/add-azkeyvaultkey) を使用します。 データ暗号化ポリシー (DEP) に関連付けられているキーのローリングが完了したら、別のコマンドレットを実行して、カスタマー キーが新しいキーの使用を開始することを確認します。 各 Azure Key Vault (AKV) でこの手順を実行します。

例:

1. Azure PowerShellを使用して Azure サブスクリプションにサインインします。 手順については、「[Azure PowerShellでサインイン](/powershell/azure/authenticate-azureps)する」を参照してください。

2. 次の例に示すように、Add-AzKeyVaultKey コマンドレットを実行します。

   ```powershell
   Add-AzKeyVaultKey -VaultName Contoso-CK-EX-NA-VaultA1 -Name Contoso-CK-EX-NA-VaultA1-Key001 -Destination HSM -KeyOps @('wrapKey','unwrapKey') -NotBefore (Get-Date -Date "12/27/2016 12:01 AM")
   ```

   この例では、 **Contoso-CK-EX-NA-VaultA1-Key001** という名前のキーが **Contoso-CK-EX-NA-VaultA1** コンテナーに存在するため、コマンドレットによって新しいバージョンのキーが作成されます。 この操作では、キーのバージョン履歴に以前のキー バージョンが保持されます。 暗号化を続けるデータを暗号化解除するには、以前のキー バージョンが必要です。 DEP に関連付けられているキーのローリングが完了したら、追加のコマンドレットを実行して、カスタマー キーが新しいキーの使用を開始することを確認します。 次のセクションでは、コマンドレットについて詳しく説明します。
  
## <a name="update-the-keys-for-multi-workload-deps"></a>複数ワークロードの DEP のキーを更新する

複数のワークロードで使用される DEP に関連付けられている Azure Key Vault キーのいずれかをロールする場合は、新しいキーを指すように DEP を更新する必要があります。 このプロセスでは、可用性キーはローテーションされません。

新しいキーを使用して複数のワークロードを暗号化するように Customer Key に指示するには、次の手順を実行します。

1. ローカル コンピューターで、組織内のグローバル管理者またはコンプライアンス管理者のアクセス許可を持つ職場または学校アカウントを使用[して、Exchange Online PowerShell に接続](/powershell/exchange/connect-to-exchange-online-powershell)します。

2. Set-M365DataAtRestEncryptionPolicy コマンドレットを実行します。
  
   ```powershell
   Set-M365DataAtRestEncryptionPolicy -[Identity] "PolicyName" -Refresh
   ```

*ここで、PolicyName* はポリシーの名前または一意の ID です。 たとえば、Contoso_Global。

例:

```powershell
Set-M365DataAtRestEncryptionPolicy -Identity "Contoso_Global" -Refresh
```

## <a name="update-the-keys-for-exchange-online-deps"></a>Exchange Online DEP のキーを更新する

Exchange OnlineとSkype for Businessで使用される DEP に関連付けられている Azure Key Vault キーのいずれかをロールする場合は、新しいキーを指すように DEP を更新する必要があります。 これにより、可用性キーはローテーションされません。

新しいキーを使用してメールボックスを暗号化するようにカスタマー キーに指示するには、次のようにSet-DataEncryptionPolicyコマンドレットを実行します。

1. Azure PowerShellでSet-DataEncryptionPolicy コマンドレットを実行します。
  
   ```powershell
   Set-DataEncryptionPolicy -Identity <DataEncryptionPolicyID> -Refresh
   ```

2. メールボックスの DataEncryptionPolicyID プロパティの値を確認するには、「メールボックスに [割り当てられている DEP を決定する」](customer-key-manage.md#determine-the-dep-assigned-to-a-mailbox)の手順を使用します。 サービスが更新されたキーを適用すると、このプロパティの値が変更されます。
  
## <a name="update-the-keys-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>SharePoint Online、OneDrive for Business、Teams ファイルのキーを更新する

SharePoint Online では、一度に 1 つのキーのみをロールできます。 キー コンテナーで両方のキーをロールする場合は、最初の操作が完了するまで待ちます。 Microsoft では、この問題を回避するために、操作をずらすことをお勧めします。 SharePoint Online とOneDrive for Businessで使用される DEP に関連付けられている Azure Key Vault キーのいずれかをロールする場合は、新しいキーを指すように DEP を更新する必要があります。 これにより、可用性キーはローテーションされません。

1. 次のようにUpdate-SPODataEncryptionPolicyコマンドレットを実行します。
  
   ```powershell
   Update-SPODataEncryptionPolicy  <SPOAdminSiteUrl> -KeyVaultName <ReplacementKeyVaultName> -KeyName <ReplacementKeyName> -KeyVersion <ReplacementKeyVersion> -KeyType <Primary | Secondary>
   ```

   このコマンドレットは SharePoint Online とOneDrive for Businessのキー ロール操作を開始しますが、アクションはすぐには完了しません。

2. キー ロール操作の進行状況を確認するには、次のようにGet-SPODataEncryptionPolicyコマンドレットを実行します。

   ```powershell
   Get-SPODataEncryptionPolicy <SPOAdminSiteUrl>
   ```

## <a name="related-articles"></a>関連記事

- [カスタマー キーによるサービスの暗号化](customer-key-overview.md)

- [カスタマー キーを設定する](customer-key-set-up.md)

- [カスタマー キーを管理する](customer-key-manage.md)

- [可用性キーの詳細](customer-key-availability-key-understand.md)
