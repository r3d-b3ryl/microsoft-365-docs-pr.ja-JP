---
title: 非アクティブなメールボックスを回復する
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
ms.assetid: 35d0ecdb-7cb0-44be-ad5c-69df2f8f8b25
description: '元従業員が組織に戻った場合、または新しい従業員が退職した従業員の職務を受けた場合は、Office 365 の非アクティブなメールボックスの内容を復元できます。 非アクティブなメールボックスを復元すると、非アクティブなメールボックスのコンテンツが含まれる新しいメールボックスに変換されます。 '
ms.openlocfilehash: 63d71d2f6e23af55d94f006e772f35747c83d59c
ms.sourcegitcommit: 584e2e9db8c541fe32624acdca5e12ee327fdb63
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2020
ms.locfileid: "44678973"
---
# <a name="recover-an-inactive-mailbox"></a>非アクティブなメールボックスを回復する

非アクティブなメールボックス (回復可能な削除によって削除されたメールボックスの一種) は、元従業員が組織を離れた後に、その電子メールを保持するために使用されます。その従業員が組織に復帰する場合、または別の従業員が元従業員の職責を引き継ぐ場合には、非アクティブなメールボックスのコンテンツをユーザーが使用できるようにする 2 つの方法があります。 
  
- **非アクティブなメールボックスを回復します。** 元従業員が組織に戻った場合、または新しい従業員が元従業員の職務を引き継ぐために採用された場合は、非アクティブなメールボックスの内容を復元できます。 この方法では、非アクティブなメールボックスを、その非アクティブなメールボックスのコンテンツが含まれる新しいアクティブなメールボックスに変換します。 回復された後、非アクティブなメールボックスは存在しなくなります。 このトピックの手順では、この方法について説明します。 
    
- **非アクティブなメールボックスを復元します。** 別の従業員が元従業員の職務を引き受けた場合、または他のユーザーが非アクティブなメールボックスのコンテンツにアクセスする必要がある場合は、非アクティブなメールボックスの内容を既存のメールボックスに復元 (またはマージ) することができます。 非アクティブなメールボックスからアーカイブを復元することもできます。 この方法の手順については、「 [Office 365 の非アクティブなメールボックスを復元する](restore-an-inactive-mailbox.md)」を参照してください。

非アクティブなメールボックスを復元することと回復することの違いについて、および非アクティブなメールボックスを回復する際になされる処理について詳しくは、「[詳細情報](#more-information)」セクションを参照してください。
  
## <a name="before-you-begin"></a>はじめに

- 非アクティブなメールボックスを回復するには、Exchange Online PowerShell を使用する必要があります。 Exchange 管理センター (EAC) を使用することはできません。 詳細な手順については、「 [Exchange Online PowerShell への接続](https://go.microsoft.com/fwlink/?linkid=396554)」を参照してください。
    
- 組織内の非アクティブなメールボックスの識別情報を取得するには、次のコマンドを実行します。 

    ```powershell
    Get-Mailbox -InactiveMailboxOnly | FL Name,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
    ```

    このコマンドによって返される情報を使用して、特定の非アクティブなメールボックスを回復します。

## <a name="recover-an-inactive-mailbox"></a>非アクティブなメールボックスを回復する

*InactiveMailbox*パラメーターを指定して**新しいメールボックス**コマンドレットを使用して、非アクティブなメールボックスを回復します。 
  
1. 非アクティブなメールボックスのプロパティを含む変数を作成します。 
    
    ```powershell
    $InactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
    ```

    > [!IMPORTANT]
    > 上記のコマンドでは、 **DistinguishedName** または **ExchangeGUID** プロパティの値を使用して非アクティブなメールボックスを識別します。これらのプロパティは組織内の各メールボックスに対して一意ですが、アクティブなメールボックスと非アクティブなメールボックスとでプライマリ SMTP アドレスが等しい可能性があります。 
  
2. 次の例では、上記のコマンドで取得したプロパティを使用して、ユーザー Ann Beebe のために非アクティブなメールボックスをアクティブなメールボックスに回復します。 *Name*および*MicrosoftOnlineServicesID*パラメーターに指定する値が組織内で一意であることを確認してください。 

    ```powershell
    New-Mailbox -InactiveMailbox $InactiveMailbox.DistinguishedName -Name annbeebe -FirstName Ann -LastName Beebe -DisplayName "Ann Beebe" -MicrosoftOnlineServicesID Ann.Beebe@contoso.com -Password (ConvertTo-SecureString -String 'P@ssw0rd' -AsPlainText -Force) -ResetPasswordOnNextLogon $true
    ```

    回復された非アクティブなメールボックスのプライマリ SMTP アドレスの値は、 *MicrosoftOnlineServicesID*パラメーターで指定されたものと同じになります。 
    
非アクティブなメールボックスを回復した後、新しいユーザーアカウントも作成されます。 ライセンスを割り当てて、このユーザー アカウントをアクティブにする必要があります。 Microsoft 365 管理センターでライセンスを割り当てるには、「 [microsoft 365 for business のライセンスの割り当てまたは割り当て解除](https://go.microsoft.com/fwlink/p/?LinkId=276798)」を参照してください。
  
## <a name="more-information"></a>詳細情報

- **非アクティブなメールボックスを回復することと復元することとの主な違い。** 非アクティブなメールボックスを回復すると、そのメールボックスは新しいメールボックスに変換され、非アクティブなメールボックスのコンテンツとフォルダー構造が保持されて、メールボックスが新しいユーザー アカウントにリンクされます。 After it's recovered, the inactive mailbox no longer exists, and any changes made to the content in the new mailbox will affect the content that was originally on hold in the inactive mailbox. Conversely, when you restore an inactive mailbox, the contents are merely copied to another mailbox. The inactive mailbox is preserved and remains an inactive mailbox. ターゲット メールボックス内のコンテンツに加えられる変更は、非アクティブなメールボックス内に保持されている元のコンテンツに影響を与えません。 非アクティブなメールボックスは、インプレース電子情報開示を使用して検索すること、そのコンテンツを別のメールボックスに復元すること、それを後に回復したり削除したりすることが引き続き可能です。 

- **非アクティブなメールボックスを回復する際になされる処理。** 非アクティブなメールボックスを復元する際、次の処理が発生します。 

   - 非アクティブなメールボックスに適用された保留リストは、回復前に非アクティブなメールボックスに適用された保持の種類に基づいて変更または削除されます。
  
     - **訴訟ホールド。** 非アクティブなメールボックスに対して訴訟ホールドが有効になっていた場合は、回復されたメールボックスから削除されます。
  
     - **インプレース保持**インプレース保持は、回復されたメールボックスから削除されます。 これは、回復されたメールボックスが、インプレース保持またはインプレース電子情報開示検索からソースメールボックスとして削除されることを意味します。
     
     - **保持ロック付きの Microsoft 365 アイテム保持ポリシー。** 非アクティブなメールボックスが保持ポリシー (ロックされた*保持ポリシー*と呼ばれます) に割り当てられている場合、回復したメールボックスは同じロックされた保持ポリシーに割り当てられます。 ロックされた保持ポリシーの詳細については、「[アイテム保持ポリシーについ](retention-policies.md#use-preservation-lock-to-comply-with-regulatory-requirements)て」を参照してください。
  
     - **ロックを保持しない Microsoft 365 アイテム保持ポリシー。** 非アクティブなメールボックスは、そのメールボックスに適用されていた、ロックされていない Microsoft 365 保持ポリシーから削除されます。 ただし、回復されたメールボックスで訴訟ホールドが有効になっている場合は、特定の保存期間よりも古いコンテンツを削除する組織全体のアイテム保持ポリシーに基づいてメールボックスのコンテンツが削除されないようにします。 訴訟ホールドを保持するか、削除することができます。 詳細については、「[訴訟ホールドを作成する](create-a-litigation-hold.md)」を参照してください。

  - 単一アイテムの回復期間 ( **RetainDeletedItemsFor** メールボックス プロパティで定義されている) は 30 日に設定されます。通常は、新しいメールボックスが Exchange Online に作成されるとき、この保存期間は 14 日に設定されます。この期間を最大値の 30 日間に設定すると、非アクティブなメールボックスから完全に削除 (またはパージ) されたデータを回復するための時間が拡大します。また、単一アイテムの回復を無効にすることや、単一アイテムの回復期間を既定の 14 日間に戻すこともできます。詳細については、「 [Enable or disable single item recovery for a mailbox](https://go.microsoft.com/fwlink/?linkid=856769)」を参照してください。
  
  - アイテム保持ホールドが有効になり、アイテム保持ホールド期間が 30 日に設定されます。 これは、新しいメールボックスに割り当てられた既定の Exchange アイテム保持ポリシーと、組織全体または Exchange 全体の Microsoft 365 保持ポリシーが30日間処理されないことを意味します。 これにより、復帰した従業員や回復された非アクティブなメールボックスの新しい所有者は、古いメッセージを処理するための時間を持つことができます。 それ以外の場合、Exchange または Microsoft 365 の保持ポリシーは、Exchange または Microsoft 365 の保持ポリシーに対して構成された設定に基づいて期限切れになった古いメールボックスアイテムを削除する (または、有効になっている場合はアーカイブメールボックスにアイテムを移動する) 可能性があります。 30 日後に保存機能が期限切れになると、 **RetentionHoldEnabled** メールボックスのプロパティが **False** に設定されて、管理フォルダー アシスタントがメールボックスに割り当てられたポリシーの処理を開始します。 この追加の時間を必要としない場合は、単にアイテム保持ホールドを除去できます。 または、 **Set-Mailbox -EndDateForRetentionHold** コマンドを使用してアイテム保持ホールドの期間を拡大することもできます。 詳細については、「 [Place a mailbox on retention hold](https://go.microsoft.com/fwlink/?linkid=856300)」を参照してください。

- **非アクティブなメールボックスの元の状態を保持する必要がある場合は、回復されたメールボックスにホールドを設定します。** 新しいメールボックスの所有者またはアイテム保持ポリシーによって、回復された非アクティブなメールボックスからメッセージが完全に削除されないようにするには、メールボックスを訴訟ホールドの対象にすることができます。 詳細については、「[メールボックスを訴訟ホールドの対象にする](https://go.microsoft.com/fwlink/?linkid=856286)」を参照してください。
    
- **非アクティブなメールボックスを回復する際に使用可能なユーザー ID。** 非アクティブなメールボックスを回復する場合、 *MicrosoftOnlineServicesID*パラメーターに指定する値は、非アクティブなメールボックスに関連付けられていた元のものとは異なる場合があります。 元のユーザー ID を使用することもできます。 ただし、前述のように、非アクティブなメールボックスを回復するときに、 *Name*および*MicrosoftOnlineServicesID*に使用する値が組織内で一意であることを確認してください。 
    
- **非アクティブなメールボックスのメールボックス保持期間が期限が切れになっていない場合の処理。** 非アクティブなメールボックスが回復可能な削除によって削除されてから 30 日が経過していない場合は、 **New-Mailbox -InactiveMailbox** コマンドを使用してそれを回復することができません。 対応するユーザーアカウントを復元することによって回復する必要があります。 詳細については、「 [ユーザーを削除または復元する](https://go.microsoft.com/fwlink/p/?LinkId=279162)」を参照してください。
    
- **回復可能な削除によって削除された非アクティブなメールボックスの、メールボックス保持期間が期限切れかどうかを判別する方法。** 次のコマンドを実行します。 
    
    ```powershell
    Get-Mailbox -InactiveMailboxOnly <identity of inactive mailbox> | FL ExternalDirectoryObjectId
  ```

    **ExternalDirectoryObjectId** プロパティの値が存在しない場合は、メールボックスの保存期間の期限が切れているので、 **New-Mailbox -InactiveMailbox** コマンドを実行することにより非アクティブなメールボックスを回復できます。 **Externaldirectoryobjectid**プロパティの値がある場合、回復可能な削除によって削除されたメールボックスの保持期間は期限が切れていないため、ユーザーアカウントを復元することによってメールボックスを回復する必要があります。 詳しくは、「 [ユーザーを削除または復元する](https://go.microsoft.com/fwlink/p/?LinkId=279162)」を参照してください。
    
- **非アクティブなメールボックスを回復した後に、アーカイブ メールボックスを有効にすることを検討する。** これにより、復帰したユーザーや新しい従業員が古いメッセージ アーカイブ メールボックスに移動できるようになります。 アイテム保持ホールドの期限が切れると、Exchange Online メールボックスに割り当てられた既定の Exchange アイテム保持ポリシーの一部であるアーカイブ ポリシーが、2 年以上経過しているアイテムをアーカイブ メールボックスに移動します。 アーカイブ メールボックスを有効にしない場合は、2 年以上経過しているアイテムがユーザーのプライマリ メールボックスに残ります。 詳細については、「[アーカイブメールボックスを有効にする](enable-archive-mailboxes.md)」を参照してください。
 