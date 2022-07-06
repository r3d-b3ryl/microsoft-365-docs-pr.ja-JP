---
title: 非アクティブなメールボックスを復元する
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
ms.localizationpriority: medium
search.appverid:
- MOE150
- MET150
ms.assetid: 97e06a7a-ef9a-4ce8-baea-18b9e20449a3
description: 非アクティブなメールボックスの内容を既存のメールボックスに復元 (またはマージ) する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7c1a976013f522e45b4e96d6b28653fa860fe16f
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2022
ms.locfileid: "66629225"
---
# <a name="restore-an-inactive-mailbox"></a>非アクティブなメールボックスを復元する

非アクティブなメールボックス (論理的に削除されたメールボックスの一種) は、組織を離れた後に元従業員のメールを保持するために使用されます。 別の従業員が退職した従業員の職責を引き継ぐ場合、またはその従業員が組織に復帰する場合には、非アクティブなメールボックスのコンテンツをユーザーが使用できるようにする 2 つの方法があります。

- **非アクティブなメールボックスを復元する** 退職した従業員の職務を別の従業員が引き継ぐ場合や、非アクティブなメールボックスのコンテンツに別のユーザーがアクセスすることが必要な場合は、非アクティブなメールボックスのコンテンツを既存のメールボックスに復元 (または マージ) できます。 非アクティブなメールボックスからアーカイブを復元することもできます。 復元された後も、非アクティブなメールボックスは保持されて、非アクティブなメールボックスとして保存されます。 この記事では、非アクティブなメールボックスを復元する手順について説明します。

- **非アクティブなメールボックスを回復する** 退職した従業員が組織に復帰した場合や、退職した従業員の職責を引き継ぐために新入社員が採用された場合は、非アクティブなメールボックスのコンテンツを回復することができます。 このメソッドは、非アクティブなメールボックスを、その非アクティブなメールボックスのコンテンツが含まれる新しいメールボックスに変換します。 回復された後、非アクティブなメールボックスは存在しなくなります。 詳細な手順については、「[Office 365で非アクティブなメールボックスを回復する](recover-an-inactive-mailbox.md)」を参照してください。

非アクティブなメールボックスの復元と回復の違いの詳細については、この記事の「 [詳細情報](#more-information) 」セクションを参照してください。

> [!NOTE]
> 自動展開アーカイブで構成されている非アクティブなメールボックスを回復または復元することはできません。 自動展開アーカイブを使用して非アクティブなメールボックスからデータを回復する必要がある場合は、コンテンツ検索を使用してメールボックスからデータをエクスポートし、別のメールボックスにインポートします。 手順については、次の記事を参照してください。
>
> - [コンテンツ検索](content-search.md)
> - [コンテンツ検索結果をエクスポートする](export-search-results.md)

## <a name="requirements-to-restore-an-inactive-mailbox"></a>非アクティブなメールボックスを復元するための要件

- 非アクティブなメールボックスを復元するにはExchange Online PowerShell を使用する必要があります。 この手順では、Exchange 管理センター (EAC) またはMicrosoft Purview コンプライアンス ポータルを使用することはできません。 PowerShell Exchange Online使用する詳細な手順については、「PowerShell [への接続Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell)参照してください。

- Exchange Online PowerShell で次のコマンドを実行して、組織内の非アクティブなメールボックスの ID 情報を取得します。

  ```powershell
  Get-Mailbox -InactiveMailboxOnly | Format-List Name,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
  ```

  このコマンドによって返される情報を使用して、特定の非アクティブなメールボックスを特定して復元します。

- 非アクティブなメールボックスの詳細については、「[Office 365の非アクティブなメールボックス](inactive-mailboxes-in-office-365.md)」を参照してください。

## <a name="restore-inactive-mailboxes"></a>非アクティブなメールボックスを復元する

**New-MailboxRestoreRequest** コマンドレットを  _SourceMailbox_ と  _TargetMailbox_ パラメーターと共に使用して、非アクティブなメールボックスのコンテンツを既存のメールボックスに復元します。このコマンドレットの使用方法について詳しくは、「 [New-MailboxRestoreRequest](/powershell/module/exchange/new-mailboxrestorerequest)」を参照してください。

非アクティブなメールボックスを復元する前に、非アクティブなメールボックスの LegacyExchangeDN をターゲット メールボックスの X500 プロキシ アドレスとしてターゲット メールボックスに追加する必要があります。 **これは、New-MailboxRestoreRequest** コマンドレットがソース メールボックスとターゲット メールボックスの **LegacyExchangeDN** プロパティの値が同じかどうかを確認するためにチェックされるためです。 非アクティブなメールボックスを復元した後、必要に応じて、非アクティブなメールボックスの LegacyExchangeDN をソース メールボックスから削除できます。 LegacyExchangeDN を削除する前に、メールボックスの復元要求が完了するまで待ってください。

非アクティブなメールボックスを既存のメールボックスに復元するには、次の手順に従います。

1. 非アクティブなメールボックスのプロパティを含む変数を作成します。

   ```powershell
   $inactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
   ```

   > [!IMPORTANT]
   > 上記のコマンドでは、 **DistinguishedName** または **ExchangeGUID** プロパティの値を使用して非アクティブなメールボックスを識別します。これらのプロパティは組織内の各メールボックスに対して一意ですが、アクティブなメールボックスと非アクティブなメールボックスとでプライマリ SMTP アドレスが等しい可能性があります。

2. 非アクティブなメールボックスの LegacyExchangeDN を表示して、次の手順でターゲット メールボックスにプロキシ アドレスとして追加できるようにします。

   ```powershell
   $inactiveMailbox.LegacyExchangeDN
   ```

3. 非アクティブなメールボックスの LegacyExchangeDN を X500 プロキシ アドレスとしてターゲット メールボックスに追加します。

   ```powershell
   Set-Mailbox <identity of target mailbox> -EmailAddresses @{Add="X500:<LegacyExchangeDN of inactive mailbox>"}
   ```

4. 非アクティブなメールボックスのコンテンツを既存のメールボックスに復元します。非アクティブなメールボックス (ソース メールボックス) のコンテンツは、既存のメールボックス (ターゲット メールボックス) の対応するフォルダーにマージされます。

   ```powershell
   New-MailboxRestoreRequest -SourceMailbox $inactiveMailbox.DistinguishedName -TargetMailbox <identity of target mailbox> 
   ```

   または、非アクティブなメールボックスのコンテンツの復元先として、ターゲット メールボックス内の最上位フォルダーを指定することもできます。指定したターゲット フォルダーまたはターゲット フォルダー構造がターゲット メールボックス内に存在しない場合は、復元処理中に作成されます。

   次の使用例は、非アクティブなメールボックス内のメールボックス アイテムとサブフォルダーを、ターゲット メールボックスの最上位フォルダー構造内にある「Inactive Mailbox」という名前のフォルダーにコピーします。

   ```powershell
   New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -TargetMailbox <identity of target mailbox> -TargetRootFolder "Inactive Mailbox"
   ```

5. 復元要求が完了したら、必要に応じて、非アクティブなメールボックスの LegacyExchangeDN をターゲット メールボックスから削除できます。 非アクティブなメールボックスから LegacyExchangeDN を残しても、ターゲット メールボックスには影響しません。

   ```powershell
   Set-Mailbox <identity of target mailbox> -EmailAddresses @{Remove="X500:<LegacyExchangeDN of inactive mailbox>"}
   ```

## <a name="restore-the-archive-from-an-inactive-mailbox"></a>非アクティブなメールボックスからアーカイブを復元する

非アクティブなメールボックスにアーカイブ メールボックスがある場合も、それを既存のメールボックスのアーカイブ メールボックスに復元できます。 非アクティブなメールボックスからアーカイブを復元するには、非アクティブなメールボックスの復元に使用されるコマンドに _SourceIsArchive_ スイッチと _TargetIsArchive_ スイッチを追加する必要があります。

1. 非アクティブなメールボックスのプロパティを含む変数を作成します。

   ```powershell
   $inactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
   ```

   > [!NOTE]
   > 上記のコマンドでは、 **DistinguishedName** または **ExchangeGUID** プロパティの値を使用して非アクティブなメールボックスを識別します。これらのプロパティは組織内の各メールボックスに対して一意ですが、アクティブなメールボックスと非アクティブなメールボックスとでプライマリ SMTP アドレスが等しい可能性があります。

2. 非アクティブなメールボックスの LegacyExchangeDN を表示して、次の手順でターゲット メールボックスにプロキシ アドレスとして追加できるようにします。

   ```powershell
   $inactiveMailbox.LegacyExchangeDN
   ```

3. 非アクティブなメールボックスの LegacyExchangeDN を X500 プロキシ アドレスとしてターゲット メールボックスに追加します。

   ```powershell
   Set-Mailbox <identity of target mailbox> -EmailAddresses @{Add="X500:<LegacyExchangeDN of inactive mailbox>"}
   ```

4. アーカイブのコンテンツを、非アクティブなメールボックス (ソース アーカイブ) から既存のメールボックスのアーカイブ (ターゲット アーカイブ) に復元します。この例では、ソース アーカイブのコンテンツが、ターゲット メールボックスのアーカイブ内の「Inactive Mailbox Archive」という名前のフォルダーにコピーされます。

   ```powershell
   New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -SourceIsArchive -TargetMailbox <identity of target mailbox> -TargetIsArchive -TargetRootFolder "Inactive Mailbox Archive"
   ```

5. 復元要求が完了したら、必要に応じて、非アクティブなメールボックスの LegacyExchangeDN をターゲット メールボックスから削除できます。 非アクティブなメールボックスから LegacyExchangeDN を残しても、ターゲット メールボックスには影響しません。

   ```powershell
   Set-Mailbox <identity of target mailbox> -EmailAddresses @{Remove="X500:<LegacyExchangeDN of inactive mailbox>"}
   ```

## <a name="more-information"></a>詳細情報

- **非アクティブなメールボックスを回復することと復元することとの主な違い。** 非アクティブなメールボックスを回復すると、メールボックスは新しいメールボックスに変換されます。 非アクティブなメールボックスの内容とフォルダー構造は保持され、メールボックスは新しいユーザー アカウントにリンクされます。 After it's recovered, the inactive mailbox no longer exists, and any changes made to the content in the new mailbox will affect the content that was originally on hold in the inactive mailbox. Conversely, when you restore an inactive mailbox, the contents are merely copied to another mailbox. The inactive mailbox is preserved and remains an inactive mailbox. Any changes made to the content in the target mailbox won't affect the original content held in the inactive mailbox. 非アクティブなメールボックスは [、コンテンツ検索ツール](content-search.md)を使用して検索したり、その内容を別のメールボックスに復元したり、後で復元または削除したりできます。

- **非アクティブなメールボックスを見つける方法。** 組織内の非アクティブなメールボックスの一覧を取得して、非アクティブなメールボックスを復元するために役立つ情報を表示するには、次のコマンドを実行できます。

  ```powershell
  Get-Mailbox -InactiveMailboxOnly | Format-List Name,PrimarySMTPAddress,DistinguishedName,ExchangeGUID,LegacyExchangeDN,ArchiveStatus
  ```

- **Microsoft 365 アイテム保持ポリシーまたは訴訟ホールドを使用するか、非アクティブなメールボックス コンテンツを保持します。** 非アクティブなメールボックスの状態を復元した後も保持する場合は、非アクティブなメールボックスを復元する前に、 [Microsoft 365 アイテム保持ポリシー](retention.md) をターゲット メールボックスに適用するか、ターゲット メールボックスを [訴訟ホールド](create-a-litigation-hold.md) に置くことができます。 これにより、非アクティブなメールボックスのアイテムがターゲット メールボックスに復元された後に、完全に削除されることがなくなります。

- **非アクティブなメールボックスを復元する前に、ターゲット メールボックスでの保存機能を有効にする。** 非アクティブなメールボックスのメールボックス アイテムは古くなっている可能性があるため、非アクティブなメールボックスを復元する前に、ターゲット メールボックスでの保存機能を有効にすることを検討できます。 メールボックスでの保存機能を有効にすると、保存機能が削除されるかまたは保存期間が期限切れになるまで、それに割り当てられた保持ポリシーは処理されなくなります。 これにより、ターゲット メールボックスの所有者が非アクティブなメールボックスからの古いメッセージを処理するための時間ができます。 そうしないと、ターゲット メールボックスに構成された保存期間の設定に基づいて、期限切れになっている古いアイテムが保持ポリシーによって削除される (またはアーカイブ メールボックスが使用可能な場合にはアイテムがそこに移動される) 可能性があります。 詳細については、「[Exchange Onlineでメールボックスを保持保持に配置](/exchange/security-and-compliance/messaging-records-management/mailbox-retention-hold)する」を参照してください。

- **New-MailboxRestoreRequest コマンドレットと共に他のパラメーターを使用して、非アクティブなメールボックスのさまざまな復元シナリオを実装できます。** たとえば、次のコマンドを実行して、非アクティブなメールボックスからターゲット メールボックスのプライマリ メールボックスにアーカイブを復元できます。

  ```powershell
  New-MailboxRestoreRequest -SourceMailbox <inactive mailbox> -SourceIsArchive -TargetMailbox <target mailbox> -TargetRootFolder "Inactive Mailbox Archive"
  ```

  また次のコマンドを実行して、非アクティブなプライマリ メールボックスをターゲット メールボックスのアーカイブに復元することもできます。

  ```powershell
  New-MailboxRestoreRequest -SourceMailbox <inactive mailbox> -TargetMailbox <target mailbox> -TargetIsArchive -TargetRootFolder "Inactive Mailbox"
  ```

- **TargetRootFolder パラメーターの機能。** 前述のように、 **TargetRootFolder** パラメーターを使用して、非アクティブなメールボックスのコンテンツを復元するためにターゲット メールボックス内のフォルダー構造の最上位フォルダー ( ルートとも呼ばれる) を指定できます。このパラメーターを使用しない場合、非アクティブなメールボックスのメールボックス アイテムはターゲット メールボックスの対応する既定のフォルダーにマージされ、カスタム フォルダーがターゲット メールボックスのルートに再作成されます。次の図は、 **TargetRootFolder** パラメーターを使用しない場合と使用する場合の、これらの相違点を強調しています。

  **TargetRootFolder パラメーターを使用しない場合の、ターゲット メールボックス内のフォルダー階層**

  ![TargetRootFolder パラメーターが使用されていない場合のスクリーンショット。](../media/76a759af-f483-4d1c-8cc7-243435b5562e.png)

  **TargetRootFolder パラメーターを使用する場合の、ターゲット メールボックス内のフォルダー階層**

  ![TargetRootFolder パラメーターが使用されている場合のスクリーンショット。](../media/300da592-7323-48db-b8a4-07012259d113.png)
