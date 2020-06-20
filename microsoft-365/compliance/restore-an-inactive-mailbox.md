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
description: Office 365 で、非アクティブなメールボックスの内容を既存のメールボックスに復元 (またはマージ) する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8ae3927aaaba64711cdcc3362399b109f228cb12
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818937"
---
# <a name="restore-an-inactive-mailbox"></a>非アクティブなメールボックスを復元する

An inactive mailbox (which is a type of soft-deleted mailbox) is used to retain a former employee's email after he or she leaves your organization. If another employee takes on the job responsibilities of the departed employee or if that employee returns to your organization, there are two ways that you can make the contents of the inactive mailbox available to a user:
  
- **Restore an inactive mailbox** If another employee takes on the job responsibilities of the departed employee, or if another user needs access to the contents of the inactive mailbox, you can restore (or merge) the contents of the inactive mailbox to an existing mailbox. You can also restore the archive from an inactive mailbox. After it's restored, the inactive mailbox is preserved and is retained as an inactive mailbox. This topic describes the procedures for restoring an inactive mailbox.

- **非アクティブなメールボックスを回復する** 退職した従業員が組織に復帰した場合や、退職した従業員の職責を引き継ぐために新入社員が採用された場合は、非アクティブなメールボックスのコンテンツを回復することができます。 このメソッドは、非アクティブなメールボックスを、その非アクティブなメールボックスのコンテンツが含まれる新しいメールボックスに変換します。 回復された後、非アクティブなメールボックスは存在しなくなります。 詳細な手順については、「 [Office 365 の非アクティブなメールボックスを回復する](recover-an-inactive-mailbox.md)」を参照してください。

非アクティブなメールボックスの復元と回復の違いの詳細については、この記事の「**詳細情報**」セクションを参照してください。
  
## <a name="requirements-to-restore-an-inactive-mailbox"></a>非アクティブなメールボックスを復元するための要件

- 非アクティブなメールボックスを復元するには、Exchange Online PowerShell を使用する必要があります。 Exchange 管理センター (EAC) を使用することはできません。 詳細な手順については、「 [Exchange Online PowerShell への接続](https://go.microsoft.com/fwlink/?linkid=396554)」を参照してください。

- Exchange Online PowerShell で次のコマンドを実行して、組織内の非アクティブなメールボックスの id 情報を取得します。

    ```powershell
    Get-Mailbox -InactiveMailboxOnly | FL Name,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
    ```

     このコマンドによって返される情報を使用して、特定の非アクティブなメールボックスを復元します。

- 非アクティブなメールボックスの詳細については、「 [Office 365 の非アクティブなメールボックス](inactive-mailboxes-in-office-365.md)」を参照してください。

## <a name="restore-an-inactive-mailbox"></a>非アクティブなメールボックスを復元する

Use the **New-MailboxRestoreRequest** cmdlet with the  _SourceMailbox_ and  _TargetMailbox_ parameters to restore the contents of an inactive mailbox to an existing mailbox. For more information about using this cmdlet, see [New-MailboxRestoreRequest](https://go.microsoft.com/fwlink/?linkid=856298).
  
1. 非アクティブなメールボックスのプロパティを含む変数を作成します。

    ```powershell
    $InactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
    ```

    > [!IMPORTANT]
    > In the previous command, use the value of the **DistinguishedName** or **ExchangeGUID** property to identify the inactive mailbox. These properties are unique for each mailbox in your organization, whereas it's possible that an active and an inactive mailbox might have the same primary SMTP address.
  
2. Restore the contents of the inactive mailbox to an existing mailbox. The contents of the inactive mailbox (source mailbox) will be merged into the corresponding folders in the existing mailbox (target mailbox).

    ```powershell
    New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -TargetMailbox newemployee@contoso.com -AllowLegacyDNMismatch
    ```

   Alternatively, you can specify a top-level folder in the target mailbox in which to restore the contents from the inactive mailbox. If the specified target folder or target folder structure doesn't already exist in the target mailbox, it is created during the restore process. 

    次の使用例は、非アクティブなメールボックス内のメールボックス アイテムとサブフォルダーを、ターゲット メールボックスの最上位フォルダー構造内にある「Inactive Mailbox」という名前のフォルダーにコピーします。

   ```powershell
   New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -TargetMailbox newemployee@contoso.com -TargetRootFolder "Inactive Mailbox" -AllowLegacyDNMismatch
   ```

## <a name="restore-the-archive-from-an-inactive-mailbox"></a>非アクティブなメールボックスからアーカイブを復元する

If an inactive mailbox has an archive mailbox, you can also restore it to the archive mailbox of an existing mailbox. To restore the archive from an inactive mailbox, you have to add the  _SourceIsArchive_ and  _TargetIsAchive_ switches to the command used to restore an inactive mailbox.
  
1. 非アクティブなメールボックスのプロパティを含む変数を作成します。

    ```powershell
    $InactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
    ```

    > [!NOTE]
    > In the previous command, use the value of the **DistinguishedName** or **ExchangeGUID** property to identify the inactive mailbox. These properties are unique for each mailbox in your organization, whereas it's possible that an active and an inactive mailbox might have the same primary SMTP address. 
  
2. Restore the contents of the archive from the inactive mailbox (source archive) to the archive of an existing mailbox (target archive). In this example, the contents from the source archive are copied to a folder named "Inactive Mailbox Archive" in the archive of the target mailbox.

    ```powershell
    New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -SourceIsArchive -TargetMailbox newemployee@contoso.com -TargetIsArchive -TargetRootFolder "Inactive Mailbox Archive" -AllowLegacyDNMismatch
    ```

## <a name="more-information"></a>詳細情報

- **非アクティブなメールボックスを回復することと復元することとの主な違い。** When you recover an inactive mailbox, the mailbox is basically converted to a new mailbox, the contents and folder structure of the inactive mailbox are retained, and the mailbox is linked to a new user account. After it's recovered, the inactive mailbox no longer exists, and any changes made to the content in the new mailbox will affect the content that was originally on hold in the inactive mailbox. Conversely, when you restore an inactive mailbox, the contents are merely copied to another mailbox. The inactive mailbox is preserved and remains an inactive mailbox. Any changes made to the content in the target mailbox won't affect the original content held in the inactive mailbox. 非アクティブなメールボックスは、[コンテンツ検索ツール](content-search.md)を使用して検索することも、そのコンテンツを別のメールボックスに復元したり、後で回復または削除したりすることもできます。

- **How do you find inactive mailboxes?** To get a list of the inactive mailboxes in your organization and display information that is useful for restoring an inactive mailbox, you can run this command.

  ```powershell
  Get-Mailbox -InactiveMailboxOnly | FL Name,PrimarySMTPAddress,DistinguishedName,ExchangeGUID,LegacyExchangeDN,ArchiveStatus
  ```

- **訴訟ホールドまたは Microsoft 365 のアイテム保持ポリシーを使用して、非アクティブなメールボックスのコンテンツを保持します。** 復元後に非アクティブなメールボックスの状態を保持する場合は、非アクティブなメールボックスを復元する前に、対象のメールボックスを[訴訟ホールド](https://go.microsoft.com/fwlink/?linkid=856286)の対象にするか、 [Microsoft 365 アイテム保持ポリシー](retention-policies.md)を適用することができます。 これにより、非アクティブなメールボックスのアイテムがターゲット メールボックスに復元された後に、完全に削除されることがなくなります。

- **非アクティブなメールボックスを復元する前に、ターゲット メールボックスでの保存機能を有効にする。** 非アクティブなメールボックスのメールボックス アイテムは古くなっている可能性があるため、非アクティブなメールボックスを復元する前に、ターゲット メールボックスでの保存機能を有効にすることを検討できます。 メールボックスでの保存機能を有効にすると、保存機能が削除されるかまたは保存期間が期限切れになるまで、それに割り当てられた保持ポリシーは処理されなくなります。 これにより、ターゲット メールボックスの所有者が非アクティブなメールボックスからの古いメッセージを処理するための時間ができます。 そうしないと、ターゲット メールボックスに構成された保存期間の設定に基づいて、期限切れになっている古いアイテムが保持ポリシーによって削除される (またはアーカイブ メールボックスが使用可能な場合にはアイテムがそこに移動される) 可能性があります。 詳細については、「 [Exchange Online でメールボックスを保持ホールドの状態にする](https://go.microsoft.com/fwlink/?linkid=856300)」を参照してください。

- **What does the AllowLegacyDNMismatch switch do?** In the previous examples to restore an inactive mailbox, the **AllowLegacyDNMismatch** switch is used to allow restoring the inactive mailbox to a different target mailbox. In a typical restore scenario, the goal is to restore content where the source and target mailboxes are the same mailbox. So by default, the **New-MailboxRestoreRequest** cmdlet checks to make sure that the value of the **LegacyExchangeDN** property on the source and target mailboxes is the same. This helps prevents you from accidentally restoring a source mailbox into the wrong target mailbox. If you try to restore an inactive mailbox without using the **AllowLegacyDNMismatch** switch, the command might fail if the source and target mailboxes have different values for the **LegacyExchangeDN** property.

- **You can use other parameters with the New-MailboxRestoreRequest cmdlet to implement different restore scenarios for inactive mailboxes.** For example, you can run this command to restore the archive from the inactive mailbox into the primary mailbox of the target mailbox. 

  ```powershell
  New-MailboxRestoreRequest -SourceMailbox <inactive mailbox> -SourceIsArchive -TargetMailbox <target mailbox> -TargetRootFolder "Inactive Mailbox Archive" -AllowLegacyDNMismatch
  ```

  また次のコマンドを実行して、非アクティブなプライマリ メールボックスをターゲット メールボックスのアーカイブに復元することもできます。

  ```powershell
  New-MailboxRestoreRequest -SourceMailbox <inactive mailbox> -TargetMailbox <target mailbox> -TargetIsArchive -TargetRootFolder "Inactive Mailbox" -AllowLegacyDNMismatch
  ```

- **What does the TargetRootFolder parameter do?** As previously explained, you can use the **TargetRootFolder** parameter to specify a folder in the top of the folder structure (also called the root) in the target mailbox in which to restore the contents of the inactive mailbox. If you don't use this parameter, mailbox items from the inactive mailbox are merged into the corresponding default folders of the target mailbox, and custom folders are re-created in the root of the target mailbox. The following illustrations highlight these differences between not using and using the **TargetRootFolder** parameter.

    **TargetRootFolder パラメーターを使用しない場合の、ターゲット メールボックス内のフォルダー階層**

    ![TargetRootFolder パラメーターを使用していないときのスクリーン ショット](../media/76a759af-f483-4d1c-8cc7-243435b5562e.png)
  
    **TargetRootFolder パラメーターを使用する場合の、ターゲット メールボックス内のフォルダー階層**

    ![TargetRootFolder パラメーターが使用されているときのスクリーン ショット](../media/300da592-7323-48db-b8a4-07012259d113.png)
