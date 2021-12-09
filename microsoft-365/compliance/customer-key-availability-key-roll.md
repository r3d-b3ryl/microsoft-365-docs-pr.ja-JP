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
description: 顧客キーで使用される Azure Key Vault に格納されている顧客ルート キーをロールする方法について説明します。 サービスには、Exchange Online、Skype for Business、SharePoint、オンライン、OneDrive for Business、Teamsがあります。
ms.openlocfilehash: 5f2de108d493e4b6d4233f4a932a24f524e468bb
ms.sourcegitcommit: 0ee2dabe402d44fecb6856af98a2ef7720d25189
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2021
ms.locfileid: "61373274"
---
# <a name="roll-or-rotate-a-customer-key-or-an-availability-key"></a>カスタマー キーまたは可用性キーをローリングまたはローテーションする

> [!CAUTION]
> セキュリティ要件またはコンプライアンス要件によってキーをロールする必要がある場合にのみ、顧客キーで使用する暗号化キーをロールします。 また、ポリシーに関連付けられているキーや関連付けられたキーは削除しない。 キーをロールすると、前のキーで暗号化されたコンテンツが表示されます。 たとえば、アクティブなメールボックスは頻繁に再暗号化されますが、非アクティブなメールボックス、切断されたメールボックス、および無効になっているメールボックスは、以前のキーで暗号化されます。 SharePointオンラインは復元および回復のためにコンテンツのバックアップを実行します。そのため、古いキーを使用してコンテンツがアーカイブされている可能性があります。

## <a name="about-rolling-the-availability-key"></a>可用性キーのローリングについて

Microsoft は、可用性キーの直接制御を顧客に公開しない。 たとえば、Azure Key Vault で所有しているキーのみをロール (回転) できます。 Microsoft 365内で定義されたスケジュールで可用性キーをロール処理します。 これらの主要なロールには、顧客向けサービス レベル契約 (SLA) はありません。 Microsoft 365サービス コードを使用して、Microsoft 365手動以外のプロセスで可用性キーをローテーションします。 Microsoft 管理者は、ロール プロセスを開始できます。 キーは、キー ストアに直接アクセスせずに自動化されたメカニズムを使用してロールされます。 可用性キー シークレット ストアへのアクセスは、Microsoft 管理者にプロビジョニングされません。 可用性キーのローリングでは、最初にキーを生成するのと同じメカニズムが利用されます。 可用性キーの詳細については、「可用性キー [について」を参照してください](customer-key-availability-key-understand.md)。

> [!IMPORTANT]
> Exchange OnlineおよびSkype for Business可用性キーは、作成する DEP ごとに一意の可用性キーが生成されるので、新しい DEP を作成する顧客が効果的にロールできます。 SharePoint Online、OneDrive for Business、および Teams ファイルの可用性キーはフォレスト レベルで存在し、DEP と顧客間で共有されます。つまり、ローリングは Microsoft 内部で定義されたスケジュールでのみ行われます。 新しい DEP が作成されるたび、SharePoint、OneDrive、および Teams がテナント中間キー (TIK) をロールする度に可用性キーをローリングしないリスクを軽減するために、新しい DEP が作成されるごとに、顧客のルート キーと可用性キーによってラップされるキー。

## <a name="request-a-new-version-of-each-existing-root-key-you-want-to-roll"></a>ロールする各既存のルート キーの新しいバージョンを要求する

キーをロールするときに、既存のキーの新しいバージョンを要求します。 既存のキーの新しいバージョンを要求するには、最初にキーを作成したのと同じ構文で、同じコマンドレット [Add-AzKeyVaultKey](/powershell/module/az.keyvault/add-azkeyvaultkey)を使用します。 データ暗号化ポリシー (DEP) に関連付けられたキーのローリングが完了したら、別のコマンドレットを実行して、顧客キーが新しいキーの使用を開始します。 各 Azure Key Vault (AKV) でこの手順を実行します。

例:

1. Azure サブスクリプションにサインインするには、Azure PowerShell。 手順については、「サインインする」[を参照Azure PowerShell。](/powershell/azure/authenticate-azureps)

2. 次の例Add-AzKeyVaultKey、このコマンドレットを実行します。

   ```powershell
   Add-AzKeyVaultKey -VaultName Contoso-CK-EX-NA-VaultA1 -Name Contoso-CK-EX-NA-VaultA1-Key001 -Destination HSM -KeyOps @('wrapKey','unwrapKey') -NotBefore (Get-Date -Date "12/27/2016 12:01 AM")
   ```

   この例では **、Contoso-CK-EX-NA-VaultA1-Key001** という名前のキーが **Contoso-CK-EX-NA-VaultA1** コンテナーに存在する場合、コマンドレットは新しいバージョンのキーを作成します。 この操作では、キーのバージョン履歴内の以前のキー バージョンが保持されます。 暗号化されたデータを復号化するには、以前のキー バージョンが必要です。 DEP に関連付けられたキーのローリングが完了したら、追加のコマンドレットを実行して、顧客キーが新しいキーの使用を開始します。 次のセクションでは、コマンドレットの詳細について説明します。
  
## <a name="update-the-keys-for-multi-workload-deps"></a>複数ワークロード DEP のキーを更新する

複数のワークロードで使用される DEP に関連付けられた Azure Key Vault キーのいずれかをロールする場合は、新しいキーをポイントするように DEP を更新する必要があります。 このプロセスでは、可用性キーは回転しない。

顧客キーに新しいキーを使用して複数のワークロードを暗号化するように指示するには、次の手順を実行します。

1. ローカル コンピューターで、組織でグローバル管理者またはコンプライアンス管理者のアクセス許可を持つ仕事または学校のアカウントを使用して、Exchange Online [PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)に接続します。Windows PowerShell ウィンドウで。

2. このコマンドレットをSet-M365DataAtRestEncryptionPolicyします。
  
   ```powershell
   Set-M365DataAtRestEncryptionPolicy -[Identity] "PolicyName" -Refresh
   ```

PolicyName *は* 、ポリシーの名前または一意の ID です。 たとえば、Contoso_Global。

例:

```powershell
Set-M365DataAtRestEncryptionPolicy -Identity "Contoso_Global" -Refresh
```

## <a name="update-the-keys-for-exchange-online-deps"></a>DEP のキー Exchange Onlineする

Exchange Online および Skype for Business で使用される DEP に関連付けられている Azure Key Vault キーのいずれかをロールする場合は、新しいキーをポイントするように DEP を更新する必要があります。 これにより、可用性キーはローテーションされない。

新しいキーを使用してメールボックスを暗号化するように顧客キーに指示するには、次のように Set-DataEncryptionPolicyコマンドレットを実行します。

1. 次のコマンドでSet-DataEncryptionPolicyコマンドレットを実行Azure PowerShell。
  
   ```powershell
   Set-DataEncryptionPolicy -Identity <DataEncryptionPolicyID> -Refresh
   ```

2. メールボックスの DataEncryptionPolicyID プロパティの値を確認するには、「メールボックスに割り当てられた DEP を決定する」の手順 [を使用します](customer-key-manage.md#determine-the-dep-assigned-to-a-mailbox)。 サービスが更新されたキーを適用すると、このプロパティの値が変更されます。
  
## <a name="update-the-keys-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>オンライン、SharePoint、OneDrive for BusinessファイルのキーをTeamsする

SharePointオンラインでは、一度に 1 つのキーのみをロールできます。 キー コンテナーで両方のキーをロールする場合は、最初の操作が完了するのを待ちます。 Microsoft では、この問題を回避するために操作をずらしてください。 SharePoint Online および OneDrive for Business で使用される DEP に関連付けられている Azure Key Vault キーのいずれかをロールする場合は、新しいキーをポイントするように DEP を更新する必要があります。 これにより、可用性キーはローテーションされない。

1. 次のようにUpdate-SPODataEncryptionPolicyコマンドレットを実行します。
  
   ```powershell
   Update-SPODataEncryptionPolicy  <SPOAdminSiteUrl> -KeyVaultName <ReplacementKeyVaultName> -KeyName <ReplacementKeyName> -KeyVersion <ReplacementKeyVersion> -KeyType <Primary | Secondary>
   ```

   このコマンドレットは、SharePoint Online および OneDrive for Businessのキー ロール操作を開始しますが、アクションはすぐには完了されません。

2. キー ロール操作の進行状況を確認するには、次のように Get-SPODataEncryptionPolicyコマンドレットを実行します。

   ```powershell
   Get-SPODataEncryptionPolicy <SPOAdminSiteUrl>
   ```

## <a name="related-articles"></a>関連記事

- [顧客キーによるサービスの暗号化 (Office 365](customer-key-overview.md)

- [Office 365 のカスタマー キーを設定する](customer-key-set-up.md)

- [Office 365 のカスタマー キーを管理する](customer-key-manage.md)

- [可用性キーの詳細](customer-key-availability-key-understand.md)
