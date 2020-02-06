---
title: 顧客キーまたは可用性キーをロールまたは回転する
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
description: Office 365 の顧客キーで使用される Azure Key Vault に格納されている顧客のルートキーをロールする方法について説明します。 サービスには、Exchange Online、Skype for Business、SharePoint Online、OneDrive for Business、Teams の各ファイルが含まれます。
ms.openlocfilehash: 9699960666eaa9aa62bb027d3a4549cb50cd52e3
ms.sourcegitcommit: 5ff1dc62e8855be155cb2de45cf4ee5a02c321fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41804826"
---
# <a name="roll-or-rotate-a-customer-key-or-an-availability-key"></a>顧客キーまたは可用性キーをロールまたは回転する

> [!CAUTION]
> セキュリティまたはコンプライアンスの要件によってキーをロールする必要がある場合は、顧客キーと共に使用する暗号化キーのみをロールアウトしてください。 また、ポリシーに関連付けられている、またはポリシーに関連付けられていたキーは削除しないでください。 キーをロールすると、以前のキーを使用してコンテンツが暗号化されます。 たとえば、アクティブなメールボックスは頻繁に再暗号化されますが、非アクティブ、切断済み、および無効になったメールボックスは、以前のキーで暗号化されたままになります。 SharePoint Online は復元と回復のためにコンテンツのバックアップを実行するので、古いキーを使用してアーカイブされたコンテンツが残っている場合があります。

## <a name="about-rolling-the-availability-key"></a>可用性キーのローリングについて

Microsoft は、お客様に可用性キーの直接制御を公開しません。 たとえば、Azure Key Vault で所有するキーのみをロール (回転) することができます。 Office 365 は、内部で定義されたスケジュールで可用性キーをロールします。 これらの主要なロールには、顧客向けのサービスレベル契約 (SLA) はありません。 Office 365 は、手動ではない自動化されたプロセスで Office 365 サービスコードを使用して、可用性キーを回転させます。 Microsoft 管理者がロールプロセスを開始する場合があります。 キーは、キーストアに直接アクセスせずに自動機構を使用してロールされます。 可用性キーシークレットストアへのアクセスは、Microsoft 管理者にはプロビジョニングされません。 可用性キーのローリングは、最初にキーを生成するのと同じメカニズムを利用します。 可用性キーの詳細については、「[可用性キーに](customer-key-availability-key-understand.md)ついて」を参照してください。

> [!IMPORTANT]
> Exchange Online と Skype for Business の可用性キーは、作成する DEP ごとに一意の可用性キーが生成されるため、ユーザーが新しい DEP を作成することによって効果的にロールバックできます。 SharePoint Online、OneDrive for Business、Teams の各ファイルの可用性キーは、フォレストレベルに存在し、DEPs と顧客間で共有されています。これは、Microsoft 社内で定義されたスケジュールでのみ発生します。 新しい DEP が作成されるたびに可用性キーがロールされないリスクを軽減するために、SharePoint、OneDrive、および Teams は、新しい DEP が作成されるたびに、顧客のルートキーと可用性キーによってラップされるキーであるテナントの中間キー (TIK) をロールします。

## <a name="request-a-new-version-of-each-existing-root-key-you-want-to-roll"></a>ロールアップする各既存のルートキーの新しいバージョンを要求する

キーをロールする場合は、新しいバージョンの既存のキーを要求します。 既存のキーの新しいバージョンを要求するには、最初にキーを作成したときと同じ構文を使用して、同じコマンドレット[AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/add-azkeyvaultkey)を使用します。 データ暗号化ポリシー (DEP) に関連付けられているキーのローリングを完了した後、別のコマンドレットを実行して、顧客キーが新しいキーの使用を開始するようにします。 各 Azure Key Vault (AKV) でこの手順を実行します。

例:

1. Azure PowerShell を使用して Azure サブスクリプションにサインインします。 手順については、「 [Azure PowerShell を使用](https://docs.microsoft.com/powershell/azure/authenticate-azureps)してサインインする」を参照してください。

2. 次の例に示されているように、AzKeyVaultKey コマンドレットを実行します。

   ```powershell
   Add-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination HSM -KeyOps @('wrapKey','unwrapKey') -NotBefore (Get-Date -Date "12/27/2016 12:01 AM")
   ```

   この例では、O365EX という名前のキーが**VaultA1-Key001** **vault に**存在するため、このコマンドレットによってキーの新しいバージョンが作成されます。 この操作により、キーのバージョン履歴にある以前のキーバージョンが保持されます。 暗号化されたデータを復号化するには、以前のキーバージョンが必要です。 DEP に関連付けられているキーのロールアウトを完了したら、追加のコマンドレットを実行して、顧客キーが新しいキーの使用を開始していることを確認します。 次のセクションでは、コマンドレットについて詳しく説明します。
  
## <a name="update-the-customer-key-for-exchange-online-and-skype-for-business"></a>Exchange Online と Skype for Business の顧客キーを更新する

Exchange Online と Skype for Business で使用されている DEP に関連付けられている Azure キーヴォールトキーのいずれかをロールバックする場合は、新しいキーをポイントするように DEP を更新する必要があります。 これは、可用性キーを回転させません。

Office 365 でメールボックスを暗号化するために新しいキーを使用するよう顧客キーに指示するには、次のように、Set-DataEncryptionPolicy コマンドレットを実行します。

1. Azure PowerShell で Set-DataEncryptionPolicy コマンドレットを実行します。
  
   ```powershell
   Set-DataEncryptionPolicy -Identity <DataEncryptionPolicyID> -Refresh
   ```

   72時間以内に、この DEP に関連付けられているアクティブなメールボックスは新しいキーで暗号化されます。

2. メールボックスの DataEncryptionPolicyID プロパティの値を確認するには、「[メールボックスに DEP が割り当てられているかどうかを判断](customer-key-manage.md#determine-the-dep-assigned-to-a-mailbox)する」の手順を使用します。 このプロパティの値は、更新されたキーがサービスによって適用されると変更されます。
  
## <a name="update-the-customer-key-for-sharepointonlineonedriveforbusinessandteamsfiles"></a>SharePoint Online、OneDrive for Business、および Teams ファイルの顧客キーを更新する

SharePoint Online では、一度に1つのキーのみをロールすることができます。 キーコンテナーで両方のキーをロールする場合は、最初の操作が完了するまで待機します。 Microsoft では、この問題を回避するために運用をずらすことをお勧めします。 SharePoint Online と OneDrive for business で使用されている DEP に関連付けられている Azure キーヴォールトキーのいずれかをロールバックする場合は、新しいキーをポイントするように DEP を更新する必要があります。 これは、可用性キーを回転させません。

1. Get-spodataencryptionpolicy コマンドレットを次のように実行します。
  
   ```powershell
   Update-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl> -KeyVaultName <ReplacementKeyVaultName> -KeyName <ReplacementKeyName> -KeyVersion <ReplacementKeyVersion> -KeyType <Primary | Secondary>
   ```

   このコマンドレットは、SharePoint Online と OneDrive for business のキーロール操作を開始しますが、アクションはすぐには完了しません。

2. キーロール操作の進行状況を確認するには、次のように Get-spodataencryptionpolicy コマンドレットを実行します。

   ```powershell
   Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
   ```

## <a name="related-articles"></a>関連記事

- [Office 365 の顧客キーによるサービスの暗号化](customer-key-overview.md)

- [Office 365 の顧客キーを設定する](customer-key-set-up.md)

- [Office 用の顧客キーの管理365](customer-key-manage.md)

- [可用性キーについて](customer-key-availability-key-understand.md)
