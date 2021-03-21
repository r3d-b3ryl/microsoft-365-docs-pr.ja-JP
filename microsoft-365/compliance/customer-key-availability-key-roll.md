---
title: カスタマー キーまたは可用性キーをローリングまたはローテーションする
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 02/05/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 顧客キーで使用される Azure Key Vault に格納されている顧客ルート キーをロールする方法について説明します。 サービスには、Exchange Online、Skype for Business、SharePoint Online、OneDrive for Business、Teams ファイルが含まれます。
ms.openlocfilehash: 980d6b198b326cb75bb2b4ef4d2c980f605f23e5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923333"
---
# <a name="roll-or-rotate-a-customer-key-or-an-availability-key"></a>カスタマー キーまたは可用性キーをローリングまたはローテーションする

> [!CAUTION]
> セキュリティ要件またはコンプライアンス要件によってキーをロールする必要がある場合にのみ、顧客キーで使用する暗号化キーをロールします。 また、ポリシーに関連付けられているキーや関連付けられたキーは削除しない。 キーをロールすると、前のキーで暗号化されたコンテンツが表示されます。 たとえば、アクティブなメールボックスは頻繁に再暗号化されますが、非アクティブなメールボックス、切断されたメールボックス、および無効になっているメールボックスは、以前のキーで暗号化されます。 SharePoint Online は復元および回復の目的でコンテンツのバックアップを実行します。そのため、古いキーを使用してコンテンツがアーカイブされている可能性があります。

## <a name="about-rolling-the-availability-key"></a>可用性キーのローリングについて

Microsoft は、可用性キーの直接制御を顧客に公開しない。 たとえば、Azure Key Vault で所有しているキーのみをロール (回転) できます。 Microsoft 365 は、内部で定義されたスケジュールで可用性キーをロールします。 これらの主要なロールには、顧客向けサービス レベル契約 (SLA) はありません。 Microsoft 365 は、自動化された手動以外のプロセスで Microsoft 365 サービス コードを使用して可用性キーをローテーションします。 Microsoft 管理者は、ロール プロセスを開始できます。 キーは、キー ストアに直接アクセスせずに自動化されたメカニズムを使用してロールされます。 可用性キー シークレット ストアへのアクセスは、Microsoft 管理者にプロビジョニングされません。 可用性キーのローリングでは、最初にキーを生成するのと同じメカニズムが利用されます。 可用性キーの詳細については、「可用性キー [について」を参照してください](customer-key-availability-key-understand.md)。

> [!IMPORTANT]
> Exchange Online および Skype for Business 可用性キーは、作成する DEP ごとに一意の可用性キーが生成されるので、新しい DEP を作成する顧客が効果的にロールできます。 SharePoint Online、OneDrive for Business、Teams ファイルの可用性キーはフォレスト レベルで存在し、DEP と顧客間で共有されます。つまり、ローリングは Microsoft 内部で定義されたスケジュールでのみ行われます。 新しい DEP が作成されるごとに可用性キーを展開しないリスクを軽減するために、SharePoint、OneDrive、Teams は、新しい DEP が作成されるごとに、顧客のルート キーと可用性キーによってラップされたキーであるテナント中間キー (TIK) をロールします。

## <a name="request-a-new-version-of-each-existing-root-key-you-want-to-roll"></a>ロールする各既存のルート キーの新しいバージョンを要求する

キーをロールするときに、既存のキーの新しいバージョンを要求します。 既存のキーの新しいバージョンを要求するには、最初にキーを作成したのと同じ構文で、同じコマンドレット [Add-AzKeyVaultKey](/powershell/module/az.keyvault/add-azkeyvaultkey)を使用します。 データ暗号化ポリシー (DEP) に関連付けられたキーのローリングが完了したら、別のコマンドレットを実行して、顧客キーが新しいキーの使用を開始します。 各 Azure Key Vault (AKV) でこの手順を実行します。

次に例を示します。

1. Azure PowerShell を使用して Azure サブスクリプションにサインインします。 手順については [、「Azure PowerShell でサインインする」を参照してください](/powershell/azure/authenticate-azureps)。

2. 次の例Add-AzKeyVaultKey、このコマンドレットを実行します。

   ```powershell
   Add-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination HSM -KeyOps @('wrapKey','unwrapKey') -NotBefore (Get-Date -Date "12/27/2016 12:01 AM")
   ```

   この例では **、Contoso-O365EX-NA-VaultA1-Key001** という名前のキーが **Contoso-O365EX-NA-VaultA1** コンテナーに存在する場合、コマンドレットは新しいバージョンのキーを作成します。 この操作では、キーのバージョン履歴内の以前のキー バージョンが保持されます。 暗号化されたデータを復号化するには、以前のキー バージョンが必要です。 DEP に関連付けられたキーのローリングが完了したら、追加のコマンドレットを実行して、顧客キーが新しいキーの使用を開始します。 次のセクションでは、コマンドレットの詳細について説明します。
  
## <a name="update-the-customer-key-for-exchange-online-and-skype-for-business"></a>Exchange Online および Skype for Business のカスタマー キーを更新する

Exchange Online および Skype for Business で使用される DEP に関連付けられている Azure Key Vault キーのいずれかをロールする場合は、新しいキーをポイントするように DEP を更新する必要があります。 これにより、可用性キーはローテーションされない。

新しいキーを使用してメールボックスを暗号化するように顧客キーに指示するには、次のように Set-DataEncryptionPolicyコマンドレットを実行します。

1. Azure PowerShell でSet-DataEncryptionPolicyコマンドレットを実行します。
  
   ```powershell
   Set-DataEncryptionPolicy -Identity <DataEncryptionPolicyID> -Refresh
   ```

   72 時間以内に、この DEP に関連付けられているアクティブなメールボックスが新しいキーで暗号化されます。

2. メールボックスの DataEncryptionPolicyID プロパティの値を確認するには、「メールボックスに割り当てられた DEP を決定する」の手順 [を使用します](customer-key-manage.md#determine-the-dep-assigned-to-a-mailbox)。 サービスが更新されたキーを適用すると、このプロパティの値が変更されます。
  
## <a name="update-the-customer-key-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>SharePoint Online、OneDrive for Business、Teams ファイルのカスタマー キーを更新する

SharePoint Online では、一度に 1 つのキーのみをロールできます。 キー コンテナーで両方のキーをロールする場合は、最初の操作が完了するのを待ちます。 Microsoft では、この問題を回避するために操作をずらしてください。 SharePoint Online および OneDrive for Business で使用される DEP に関連付けられている Azure Key Vault キーのいずれかをロールする場合は、DEP を更新して新しいキーをポイントする必要があります。 これにより、可用性キーはローテーションされない。

1. 次のようにUpdate-SPODataEncryptionPolicyコマンドレットを実行します。
  
   ```powershell
   Update-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl> -KeyVaultName <ReplacementKeyVaultName> -KeyName <ReplacementKeyName> -KeyVersion <ReplacementKeyVersion> -KeyType <Primary | Secondary>
   ```

   このコマンドレットは、SharePoint Online および OneDrive for Business のキー ロール操作を開始しますが、アクションはすぐには完了されません。

2. キー ロール操作の進行状況を確認するには、次のように Get-SPODataEncryptionPolicyコマンドレットを実行します。

   ```powershell
   Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
   ```

## <a name="related-articles"></a>関連記事

- [顧客キーによるサービスの暗号化 (Office 365)](customer-key-overview.md)

- [Office 365 のカスタマー キーを設定する](customer-key-set-up.md)

- [Office 365 のカスタマー キーを管理する](customer-key-manage.md)

- [可用性キーの詳細](customer-key-availability-key-understand.md)