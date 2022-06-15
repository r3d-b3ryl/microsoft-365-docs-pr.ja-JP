---
title: 非アクティブなメールボックスを回復する
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
ms.assetid: 35d0ecdb-7cb0-44be-ad5c-69df2f8f8b25
ms.custom: seo-marvel-apr2020
description: 非アクティブなメールボックスの内容を含む新しいメールボックスに変換して、Office 365内の非アクティブなメールボックスの内容を回復する方法について説明します。
ms.openlocfilehash: 2c679407cb4f7203bb69d88c871bd844694a7c47
ms.sourcegitcommit: 3b194dd6f9ce531ae1b33d617ab45990d48bd3d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/15/2022
ms.locfileid: "66101582"
---
# <a name="recover-an-inactive-mailbox"></a>非アクティブなメールボックスを回復する

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

非アクティブなメールボックス (論理的に削除されたメールボックスの一種) は、組織を離れた後に元従業員のメールを保持するために使用されます。 その従業員が組織に復帰する場合、または別の従業員が元従業員の職責を引き継ぐ場合には、非アクティブなメールボックスのコンテンツをユーザーが使用できるようにする 2 つの方法があります。

- **非アクティブなメールボックスを回復します。** 元従業員が組織に戻った場合、または新入社員が元従業員の職務を引き受けるために採用された場合は、非アクティブなメールボックスの内容を回復できます。 この方法では、非アクティブなメールボックスを、その非アクティブなメールボックスのコンテンツが含まれる新しいアクティブなメールボックスに変換します。 回復された後、非アクティブなメールボックスは存在しなくなります。 この記事の手順では、このメソッドについて説明します。

- **非アクティブなメールボックスを復元します。** 別の従業員が元従業員の職務を引き受ける場合、または別のユーザーが非アクティブなメールボックスの内容にアクセスする必要がある場合は、非アクティブなメールボックスの内容を既存のメールボックスに復元 (またはマージ) できます。 非アクティブなメールボックスからアーカイブを復元することもできます。 この方法の手順については、「[Office 365で非アクティブなメールボックスを復元する](restore-an-inactive-mailbox.md)」を参照してください。

非アクティブなメールボックスを復元することと回復することの違いについて、および非アクティブなメールボックスを回復する際になされる処理について詳しくは、「[詳細情報](#more-information)」セクションを参照してください。

> [!NOTE]
> 自動展開アーカイブで構成されている非アクティブなメールボックスを回復または復元することはできません。 自動展開アーカイブを使用して非アクティブなメールボックスからデータを回復する必要がある場合は、コンテンツ検索を使用してメールボックスからデータをエクスポートし、別のメールボックスにインポートします。 手順については、次の記事を参照してください。
>
> - [コンテンツ検索](content-search.md)
> - [コンテンツ検索結果をエクスポートする](export-search-results.md)

## <a name="requirements-to-recover-an-inactive-mailbox"></a>非アクティブなメールボックスを回復するための要件

- 非アクティブなメールボックスを回復するにはExchange Online PowerShell を使用する必要があります。 この手順では、Exchange管理センター (EAC) またはMicrosoft Purview コンプライアンス ポータルを使用することはできません。 Exchange Online PowerShell を使用する詳細な手順については、「PowerShell [をExchange OnlineするConnect」を](/powershell/exchange/connect-to-exchange-online-powershell)参照してください。

- 組織内の非アクティブなメールボックスの識別情報を取得するには、次のコマンドを実行します。

  ```powershell
  Get-Mailbox -InactiveMailboxOnly | Format-List Name,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
  ```

  このコマンドによって返される情報を使用して、特定の非アクティブなメールボックスを回復します。

## <a name="recover-inactive-mailboxes"></a>非アクティブなメールボックスを回復する

非アクティブなメールボックスを回復するには、*InactiveMailbox* パラメーターと共に **New-Mailbox** コマンドレットを使用します。

1. 非アクティブなメールボックスのプロパティを含む変数を作成します。

   ```powershell
   $InactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
   ```

   > [!IMPORTANT]
   > 上記のコマンドでは、 **DistinguishedName** または **ExchangeGUID** プロパティの値を使用して非アクティブなメールボックスを識別します。これらのプロパティは組織内の各メールボックスに対して一意ですが、アクティブなメールボックスと非アクティブなメールボックスとでプライマリ SMTP アドレスが等しい可能性があります。

2. 次の例では、上記のコマンドで取得したプロパティを使用して、ユーザー Ann Beebe のために非アクティブなメールボックスをアクティブなメールボックスに回復します。 *Name* パラメーターと *MicrosoftOnlineServicesID* パラメーターに指定された値が組織内で一意であることを確認します。

   ```powershell
   New-Mailbox -InactiveMailbox $InactiveMailbox.DistinguishedName -Name annbeebe -FirstName Ann -LastName Beebe -DisplayName "Ann Beebe" -MicrosoftOnlineServicesID Ann.Beebe@contoso.com -Password (ConvertTo-SecureString -String 'P@ssw0rd' -AsPlainText -Force) -ResetPasswordOnNextLogon $true
   ```

   回復された非アクティブなメールボックスのプライマリ SMTP アドレスは、  *MicrosoftOnlineServicesID*  パラメーターで指定されたものと同じ値になります。

非アクティブなメールボックスを回復すると、新しいユーザー アカウントも作成されます。 ライセンスを割り当てることで、このユーザー アカウントをアクティブ化する必要があります。 Microsoft 365 管理センターでライセンスを割り当てるには、「[ユーザーの追加とライセンスの同時割り当て](../admin/add-users/add-users.md)」を参照してください。

## <a name="more-information"></a>詳細情報

- **非アクティブなメールボックスを回復することと復元することとの主な違い。** 非アクティブなメールボックスを回復すると、そのメールボックスは新しいメールボックスに変換され、非アクティブなメールボックスのコンテンツとフォルダー構造が保持されて、メールボックスが新しいユーザー アカウントにリンクされます。 After it's recovered, the inactive mailbox no longer exists, and any changes made to the content in the new mailbox will affect the content that was originally on hold in the inactive mailbox. Conversely, when you restore an inactive mailbox, the contents are merely copied to another mailbox. The inactive mailbox is preserved and remains an inactive mailbox. ターゲット メールボックス内のコンテンツに加えられる変更は、非アクティブなメールボックス内に保持されている元のコンテンツに影響を与えません。 非アクティブなメールボックスは、インプレース電子情報開示を使用して検索すること、そのコンテンツを別のメールボックスに復元すること、それを後に回復したり削除したりすることが引き続き可能です。

- **非アクティブなメールボックスを回復する際になされる処理。** 非アクティブなメールボックスを復元する際、次の処理が発生します。

  - 非アクティブなメールボックスに適用された保留は、回復前に非アクティブなメールボックスに適用された保留の種類に基づいて変更または削除されます。
    
    - **保持ロックを使用してアイテム保持ポリシーをMicrosoft 365します。** 非アクティブなメールボックスが [保持ロック](retention-preservation-lock.md)を持つアイテム保持ポリシーに含まれていた場合、回復されたメールボックスは同じアイテム保持ポリシーに割り当てられます。
    
    - **保持ロックなしでアイテム保持ポリシーをMicrosoft 365します。** 非アクティブなメールボックスは、Microsoft 365アイテム保持ポリシーから削除されます。 ただし、特定の年齢より古いコンテンツを削除する組織全体のアイテム保持ポリシーに基づいてメールボックス コンテンツが削除されないように、回復されたメールボックスに対して訴訟ホールドが有効になります。 訴訟ホールドを保持するか、削除することができます。 詳細については、「 [訴訟ホールドの作成](create-a-litigation-hold.md)」を参照してください。

    - **訴訟ホールド。** 非アクティブなメールボックスに対して訴訟ホールドが有効になっている場合は、回復されたメールボックスから削除されます。

    - **インプレース保持** In-Place保持は、回復されたメールボックスから削除されます。 つまり、回復されたメールボックスは、任意のIn-Place保留またはIn-Place電子情報開示検索からソース メールボックスとして削除されます。

  - 単一アイテムの回復期間 ( **RetainDeletedItemsFor** メールボックス プロパティで定義されている) は 30 日に設定されます。通常は、新しいメールボックスが Exchange Online に作成されるとき、この保存期間は 14 日に設定されます。この期間を最大値の 30 日間に設定すると、非アクティブなメールボックスから完全に削除 (またはパージ) されたデータを回復するための時間が拡大します。また、単一アイテムの回復を無効にすることや、単一アイテムの回復期間を既定の 14 日間に戻すこともできます。詳細については、「 [Enable or disable single item recovery for a mailbox](/exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-single-item-recovery)」を参照してください。

  - アイテム保持ホールドが有効になり、アイテム保持ホールド期間が 30 日に設定されます。 つまり、既定のExchangeアイテム保持ポリシーと、新しいメールボックスに割り当てられている組織全体またはExchange全体のMicrosoft 365アイテム保持ポリシーは 30 日間処理されません。 これにより、復帰した従業員や回復された非アクティブなメールボックスの新しい所有者は、古いメッセージを処理するための時間を持つことができます。 それ以外の場合、ExchangeまたはMicrosoft 365アイテム保持ポリシーは、ExchangeまたはMicrosoft 365アイテム保持ポリシーに構成された設定に基づいて、有効期限が切れている古いメールボックス アイテムを削除する (または、有効になっている場合はアーカイブ メールボックスにアイテムを移動する) 可能性があります。 30 日後に保存機能が期限切れになると、 **RetentionHoldEnabled** メールボックスのプロパティが **False** に設定されて、管理フォルダー アシスタントがメールボックスに割り当てられたポリシーの処理を開始します。 この追加の時間を必要としない場合は、単にアイテム保持ホールドを除去できます。 または、 **Set-Mailbox -EndDateForRetentionHold** コマンドを使用してアイテム保持ホールドの期間を拡大することもできます。 詳細については、「 [Place a mailbox on retention hold](/exchange/security-and-compliance/messaging-records-management/mailbox-retention-hold)」を参照してください。

- **非アクティブなメールボックスの元の状態を保持する必要がある場合は、回復されたメールボックスを保留にします。** 新しいメールボックスの所有者またはアイテム保持ポリシーで、回復された非アクティブなメールボックスからメッセージが完全に削除されないようにするには、メールボックスを訴訟ホールドに置くことができます。 詳細については、「 [訴訟ホールドの作成](./create-a-litigation-hold.md)」を参照してください。

- **非アクティブなメールボックスを回復する際に使用可能なユーザー ID。** 非アクティブなメールボックスを回復する場合、  *MicrosoftOnlineServicesID*  パラメーターに指定する値は、非アクティブなメールボックスに関連付けられた元のメールボックスとは異なる場合があります。 元のユーザー ID を使用することもできます。 ただし、前に説明したように、非アクティブなメールボックスを回復するときに、  *Name*  と  *MicrosoftOnlineServicesID*  に使用される値が組織内で一意であることを確認してください。

- **非アクティブなメールボックスのメールボックス保持期間が期限が切れになっていない場合の処理。** 非アクティブなメールボックスが回復可能な削除によって削除されてから 30 日が経過していない場合は、 **New-Mailbox -InactiveMailbox** コマンドを使用してそれを回復することができません。 対応するユーザー アカウントを復元して回復する必要があります。 詳細については、「 [組織からユーザーを削除する](../admin/add-users/delete-a-user.md)」を参照してください。

- **回復可能な削除によって削除された非アクティブなメールボックスの、メールボックス保持期間が期限切れかどうかを判別する方法。** 次のコマンドを実行します。
    
  ```powershell
  Get-Mailbox -InactiveMailboxOnly <identity of inactive mailbox> | Format-List ExternalDirectoryObjectId
  ```
    
    - **ExternalDirectoryObjectId** プロパティの値がない場合は、メールボックスの保持期間が切れているため、**New-Mailbox -InactiveMailbox** コマンドを実行して非アクティブなメールボックスを回復できます。
    - **ExternalDirectoryObjectId** プロパティの値がある場合は、論理的に削除されたメールボックスの保持期間の有効期限が切れていないため、[ユーザー アカウントを復元](../admin/add-users/delete-a-user.md)してメールボックスを回復する必要があります。

- **非アクティブなメールボックスを回復した後に、アーカイブ メールボックスを有効にすることを検討する。** これにより、復帰したユーザーや新しい従業員が古いメッセージ アーカイブ メールボックスに移動できるようになります。 また、アイテム保持の有効期限が切れると、Exchange Online メールボックスに割り当てられた既定のExchange MRM アイテム保持ポリシーの一部であるアーカイブ ポリシーによって、2 年以上前のアイテムがアーカイブ メールボックスに移動されます。 アーカイブ メールボックスを有効にしない場合は、2 年以上経過しているアイテムがユーザーのプライマリ メールボックスに残ります。 詳細については、「 [アーカイブ メールボックスを有効にする」を](enable-archive-mailboxes.md)参照してください。
