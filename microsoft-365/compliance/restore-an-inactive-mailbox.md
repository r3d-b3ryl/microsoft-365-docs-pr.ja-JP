---
title: 非アクティブなメールボックスを復元する
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 97e06a7a-ef9a-4ce8-baea-18b9e20449a3
description: 非アクティブなメールボックスの内容を既存のメールボックスに復元 (またはマージ) する方法についてOffice 365。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 09ab8893b2c663d87417fbedf0c157100b3693da
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59221861"
---
# <a name="restore-an-inactive-mailbox"></a>非アクティブなメールボックスを復元する

非アクティブなメールボックス (回復可能な削除によって削除されたメールボックスの一種) は、元従業員が組織を離れた後に、その電子メールを保持するために使用されます。別の従業員が退職した従業員の職責を引き継ぐ場合、またはその従業員が組織に復帰する場合には、非アクティブなメールボックスのコンテンツをユーザーが使用できるようにする 2 つの方法があります。

- **非アクティブなメールボックスを復元する** 退職した従業員の職務を別の従業員が引き継ぐ場合や、非アクティブなメールボックスのコンテンツに別のユーザーがアクセスすることが必要な場合は、非アクティブなメールボックスのコンテンツを既存のメールボックスに復元 (または マージ) できます。非アクティブなメールボックスからアーカイブを復元することもできます。復元された後も、非アクティブなメールボックスは保持されて、非アクティブなメールボックスとして保存されます。このトピックでは、非アクティブなメールボックスを復元するための手順について説明します。

- **非アクティブなメールボックスを回復する** 退職した従業員が組織に復帰した場合や、退職した従業員の職責を引き継ぐために新入社員が採用された場合は、非アクティブなメールボックスのコンテンツを回復することができます。 このメソッドは、非アクティブなメールボックスを、その非アクティブなメールボックスのコンテンツが含まれる新しいメールボックスに変換します。 回復された後、非アクティブなメールボックスは存在しなくなります。 手順については、「アクティブでないメールボックスを回復[する](recover-an-inactive-mailbox.md)」を参照Office 365。

非アクティブ [なメールボックスの](#more-information) 復元と回復の違いの詳細については、この記事の「詳細情報」セクションを参照してください。

> [!NOTE]
> 自動拡張アーカイブで構成されている非アクティブなメールボックスを回復または復元することはできません。 自動拡張アーカイブを使用して非アクティブなメールボックスからデータを回復する必要がある場合は、コンテンツ検索を使用してメールボックスからデータをエクスポートし、別のメールボックスにインポートします。 手順については、次のトピックを参照してください。
>
> - [コンテンツ検索](content-search.md)
> - [コンテンツ検索結果のエクスポート](export-search-results.md)

## <a name="requirements-to-restore-an-inactive-mailbox"></a>非アクティブなメールボックスを復元する要件

- 非アクティブなメールボックスを復元するには、Exchange Online PowerShell を使用する必要があります。 Exchange 管理センター (EAC) を使用することはできません。 詳しい手順については、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。

- PowerShell で次のコマンドをExchange Online、組織内の非アクティブなメールボックスの ID 情報を取得します。

  ```powershell
  Get-Mailbox -InactiveMailboxOnly | Format-List Name,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
  ```

  このコマンドによって返される情報を使用して、特定の非アクティブなメールボックスを復元します。

- 非アクティブなメールボックスの詳細については、「非アクティブなメールボックス」[を参照Office 365。](inactive-mailboxes-in-office-365.md)

## <a name="restore-inactive-mailboxes"></a>非アクティブなメールボックスの復元

**New-MailboxRestoreRequest** コマンドレットを  _SourceMailbox_ と  _TargetMailbox_ パラメーターと共に使用して、非アクティブなメールボックスのコンテンツを既存のメールボックスに復元します。このコマンドレットの使用方法について詳しくは、「 [New-MailboxRestoreRequest](/powershell/module/exchange/new-mailboxrestorerequest)」を参照してください。

1. 非アクティブなメールボックスのプロパティを含む変数を作成します。

   ```powershell
   $InactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
   ```

   > [!IMPORTANT]
   > 上記のコマンドでは、 **DistinguishedName** または **ExchangeGUID** プロパティの値を使用して非アクティブなメールボックスを識別します。これらのプロパティは組織内の各メールボックスに対して一意ですが、アクティブなメールボックスと非アクティブなメールボックスとでプライマリ SMTP アドレスが等しい可能性があります。

2. 非アクティブなメールボックスのコンテンツを既存のメールボックスに復元します。非アクティブなメールボックス (ソース メールボックス) のコンテンツは、既存のメールボックス (ターゲット メールボックス) の対応するフォルダーにマージされます。

   ```powershell
   New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -TargetMailbox newemployee@contoso.com -AllowLegacyDNMismatch
   ```

   または、非アクティブなメールボックスのコンテンツの復元先として、ターゲット メールボックス内の最上位フォルダーを指定することもできます。指定したターゲット フォルダーまたはターゲット フォルダー構造がターゲット メールボックス内に存在しない場合は、復元処理中に作成されます。

   次の使用例は、非アクティブなメールボックス内のメールボックス アイテムとサブフォルダーを、ターゲット メールボックスの最上位フォルダー構造内にある「Inactive Mailbox」という名前のフォルダーにコピーします。

   ```powershell
   New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -TargetMailbox newemployee@contoso.com -TargetRootFolder "Inactive Mailbox" -AllowLegacyDNMismatch
   ```

## <a name="restore-the-archive-from-an-inactive-mailbox"></a>非アクティブなメールボックスからアーカイブを復元する

非アクティブなメールボックスにアーカイブ メールボックスがある場合も、それを既存のメールボックスのアーカイブ メールボックスに復元できます。 非アクティブなメールボックスからアーカイブを復元するには、非アクティブなメールボックスの復元に使用するコマンドに _SourceIsArchive_ スイッチと _TargetIsArchive_ スイッチを追加する必要があります。

1. 非アクティブなメールボックスのプロパティを含む変数を作成します。

   ```powershell
   $InactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
   ```

   > [!NOTE]
   > 上記のコマンドでは、 **DistinguishedName** または **ExchangeGUID** プロパティの値を使用して非アクティブなメールボックスを識別します。これらのプロパティは組織内の各メールボックスに対して一意ですが、アクティブなメールボックスと非アクティブなメールボックスとでプライマリ SMTP アドレスが等しい可能性があります。

2. アーカイブのコンテンツを、非アクティブなメールボックス (ソース アーカイブ) から既存のメールボックスのアーカイブ (ターゲット アーカイブ) に復元します。この例では、ソース アーカイブのコンテンツが、ターゲット メールボックスのアーカイブ内の「Inactive Mailbox Archive」という名前のフォルダーにコピーされます。

   ```powershell
   New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -SourceIsArchive -TargetMailbox newemployee@contoso.com -TargetIsArchive -TargetRootFolder "Inactive Mailbox Archive" -AllowLegacyDNMismatch
   ```

## <a name="more-information"></a>詳細情報

- **非アクティブなメールボックスを回復することと復元することとの主な違い。** When you recover an inactive mailbox, the mailbox is basically converted to a new mailbox, the contents and folder structure of the inactive mailbox are retained, and the mailbox is linked to a new user account. After it's recovered, the inactive mailbox no longer exists, and any changes made to the content in the new mailbox will affect the content that was originally on hold in the inactive mailbox. Conversely, when you restore an inactive mailbox, the contents are merely copied to another mailbox. The inactive mailbox is preserved and remains an inactive mailbox. Any changes made to the content in the target mailbox won't affect the original content held in the inactive mailbox. 非アクティブなメールボックスは、コンテンツ検索ツールを使用[](content-search.md)して検索したり、その内容を別のメールボックスに復元したり、後で回復または削除することができます。

- **非アクティブなメールボックスを見つける方法。** 組織内の非アクティブなメールボックスの一覧を取得して、非アクティブなメールボックスを復元するために役立つ情報を表示するには、次のコマンドを実行できます。

  ```powershell
  Get-Mailbox -InactiveMailboxOnly | Format-List Name,PrimarySMTPAddress,DistinguishedName,ExchangeGUID,LegacyExchangeDN,ArchiveStatus
  ```

- **非アクティブなメールボックス コンテンツを保持するにはMicrosoft 365保持ポリシーを使用します。** 非アクティブなメールボックスの復元後に状態を保持する場合は、非アクティブなメールボックスを復元する前に、[](create-a-litigation-hold.md)ターゲット メールボックスを訴訟ホールドに配置するか[、Microsoft 365](retention.md)アイテム保持ポリシーを適用できます。 これにより、非アクティブなメールボックスのアイテムがターゲット メールボックスに復元された後に、完全に削除されることがなくなります。

- **非アクティブなメールボックスを復元する前に、ターゲット メールボックスでの保存機能を有効にする。** 非アクティブなメールボックスのメールボックス アイテムは古くなっている可能性があるため、非アクティブなメールボックスを復元する前に、ターゲット メールボックスでの保存機能を有効にすることを検討できます。 メールボックスでの保存機能を有効にすると、保存機能が削除されるかまたは保存期間が期限切れになるまで、それに割り当てられた保持ポリシーは処理されなくなります。 これにより、ターゲット メールボックスの所有者が非アクティブなメールボックスからの古いメッセージを処理するための時間ができます。 そうしないと、ターゲット メールボックスに構成された保存期間の設定に基づいて、期限切れになっている古いアイテムが保持ポリシーによって削除される (またはアーカイブ メールボックスが使用可能な場合にはアイテムがそこに移動される) 可能性があります。 詳細については、「メールボックスを保持[の保持に保持する」を参照](/exchange/security-and-compliance/messaging-records-management/mailbox-retention-hold)Exchange Online。

- **AllowLegacyDNMismatch スイッチの機能。** 非アクティブなメールボックスを復元する前述の例では、 **AllowLegacyDNMismatch** スイッチの使用によって、非アクティブなメールボックスを別のターゲット メールボックスに復元できるようになります。一般的な復元シナリオでは、ソース メールボックスとターゲット メールボックスが同じメールボックスのときに、コンテンツを復元することが目標となります。そのため既定では、 **New-MailboxRestoreRequest** コマンドレットにより、ソース メールボックスとターゲット メールボックスの **LegacyExchangeDN** プロパティの値が同じであることが確認されます。これにより、ソース メールボックスが誤って正しくないターゲット メールボックスに復元されることを防止します。 **AllowLegacyDNMismatch** スイッチを使用しないで非アクティブなメールボックスの復元を試行すると、ソース メールボックスとターゲット メールボックスで **LegacyExchangeDN** プロパティの値が異なる場合に、コマンドは失敗する可能性があります。

- **New-MailboxRestoreRequest コマンドレットと共に他のパラメーターを使用して、非アクティブなメールボックスのさまざまな復元シナリオを実装できます。** たとえば、次のコマンドを実行して、非アクティブなメールボックスからターゲット メールボックスのプライマリ メールボックスにアーカイブを復元できます。

  ```powershell
  New-MailboxRestoreRequest -SourceMailbox <inactive mailbox> -SourceIsArchive -TargetMailbox <target mailbox> -TargetRootFolder "Inactive Mailbox Archive" -AllowLegacyDNMismatch
  ```

  また次のコマンドを実行して、非アクティブなプライマリ メールボックスをターゲット メールボックスのアーカイブに復元することもできます。

  ```powershell
  New-MailboxRestoreRequest -SourceMailbox <inactive mailbox> -TargetMailbox <target mailbox> -TargetIsArchive -TargetRootFolder "Inactive Mailbox" -AllowLegacyDNMismatch
  ```

- **TargetRootFolder パラメーターの機能。** 前述のように、 **TargetRootFolder** パラメーターを使用して、非アクティブなメールボックスのコンテンツを復元するためにターゲット メールボックス内のフォルダー構造の最上位フォルダー ( ルートとも呼ばれる) を指定できます。このパラメーターを使用しない場合、非アクティブなメールボックスのメールボックス アイテムはターゲット メールボックスの対応する既定のフォルダーにマージされ、カスタム フォルダーがターゲット メールボックスのルートに再作成されます。次の図は、 **TargetRootFolder** パラメーターを使用しない場合と使用する場合の、これらの相違点を強調しています。

  **TargetRootFolder パラメーターを使用しない場合の、ターゲット メールボックス内のフォルダー階層**

  ![TargetRootFolder パラメーターを使用しない場合のスクリーンショット。](../media/76a759af-f483-4d1c-8cc7-243435b5562e.png)

  **TargetRootFolder パラメーターを使用する場合の、ターゲット メールボックス内のフォルダー階層**

  ![TargetRootFolder パラメーターを使用する場合のスクリーンショット。](../media/300da592-7323-48db-b8a4-07012259d113.png)