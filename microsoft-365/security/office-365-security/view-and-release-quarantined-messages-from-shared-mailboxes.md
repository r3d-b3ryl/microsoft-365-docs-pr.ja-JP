---
title: 共有メールボックスから検疫済みメッセージを表示および解放する
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: ''
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
ROBOTS: NOINDEX
description: ユーザーは、アクセス許可を持つ共有メールボックスに送信された検疫済みメッセージを表示および処理する方法を学習できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3efccca375745b0850c91039165b72a7d6f0bcb3
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931448"
---
# <a name="view-and-release-quarantined-messages-from-shared-mailboxes"></a>共有メールボックスから検疫済みメッセージを表示および解放する

> [!NOTE]
> この記事で説明する機能は現在プレビュー中であり、すべてのユーザーが利用できる機能ではありません。また、変更される可能性があります。

ユーザーは、「EOP でユーザーとして検疫済みメッセージを検索して解放する」の説明に従って、受信者の 1 人である検疫済みメッセージ [を管理できます](find-and-release-quarantined-messages-as-a-user.md)。 しかし [、「Exchange Online](https://docs.microsoft.com/exchange/collaboration-exo/shared-mailboxes)の共有メールボックス」の説明に従って、ユーザーがメールボックスに対するフル アクセスおよび [差出人を指定して送信] または [代理送信] のアクセス許可を持つ共有メールボックスについてはどうでしょうか。

以前は、ユーザーが共有メールボックスに送信された検疫済みメッセージを管理する機能を使用するには、管理者が共有メールボックスに対して自動マッピングを有効のままにする必要がありました (管理者が別のメールボックスへのアクセスをユーザーに許可すると、既定で有効になっています)。 ただし、ユーザーがアクセスできるメールボックスのサイズと数によっては、Outlook がユーザーがアクセスできるすべてのメールボックスを開けようとすると、パフォーマンスが低下する可能性があります。 このため、多くの管理者は共有メールボックス [の自動マッピングを削除します](https://docs.microsoft.com/outlook/troubleshoot/profiles-and-accounts/remove-automapping-for-shared-mailbox)。

現在では、ユーザーが共有メールボックスに送信された検疫済みメッセージを管理するために、自動マッピングが必要なくなりました。 正常に動作します。 共有メールボックスに送信された検疫済みメッセージにアクセスするには、次の 2 つの方法があります。

- 管理者がスパム対策[](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-your-spam-filter-policies)ポリシーでエンド ユーザーのスパム通知を有効にしている場合、共有メールボックス内のエンド ユーザーのスパム通知にアクセスできるユーザーは、通知の[確認] ボタンをクリックして、セキュリティ & コンプライアンス センターで検疫に移動できます。 この方法では、ユーザーが共有メールボックスに送信された検疫済みメッセージのみを管理できます。 ユーザーは、このコンテキストで自分の検疫メッセージを管理できません。

- ユーザーは、 [セキュリティ/コンプライアンス センターで検疫&移動できます](find-and-release-quarantined-messages-as-a-user.md)。 既定では、ユーザーに送信されたメッセージだけが表示されます。 ただし、ユーザーは並べ替えの結果 **(既定** では [メッセージ **ID]** ボタン) を受信者の電子メール アドレスに変更し、共有メールボックスの電子メール アドレスを入力し、[最新の情報に更新] をクリックして、共有メールボックスに送信された検疫済みメッセージを表示できます。

  ![受信者の電子メール アドレスによる検疫済みメッセージの並べ替え。](../../media/quarantine-sort-results-by-recipient-email-address.png)

方法に関係なく、ユーザーは検疫済みメッセージの **[受信者** ] 列を含めて混乱を避ける可能性があります。 表示する列の最大数は 7 なので、ユーザーは列の変更、既存の列の削除 (ポリシーの種類など)、受信者の選択、既定で [保存] または [保存] の順にクリックする必要 **があります。**  

  ![[ポリシーの種類] 列を削除し、[受信者] 列を検疫に追加します。](../../media/quarantine-add-recipient-column.png)

## <a name="things-to-keep-in-mind"></a>留意すべき点

- 検疫済みメッセージに対して最初に処理を行うユーザーは、共有メールボックスを使用しているすべてのユーザーのメッセージの形式を決定します。 たとえば、10 人のユーザーが共有メールボックスにアクセスし、ユーザーが検疫メッセージを削除する場合、メッセージは 10 人すべてのユーザーに対して削除されます。 同様に、ユーザーがメッセージを解放すると、そのメッセージは共有メールボックスに解放され、共有メールボックスの他のすべてのユーザーがアクセスできます。

- 現在、[送信者 **のブロック]** ボタンは、共有メールボックスに送信された検疫済みメッセージの [詳細] フライアウトでは使用できません。

- [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)で共有メールボックスの検疫済みメッセージを管理するには、エンド ユーザーは _、RecipientAddress_ パラメーターの値に共有メールボックスの電子メール アドレスを指定して [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage)コマンドレットを使用して、メッセージを識別する必要があります。 例:

  ```powershell
  Get-QuarantinedMessage -RecipientAddress officeparty@contoso.com
  ```

  その後、エンド ユーザーはリストから検疫済みメッセージを選択して、表示またはアクションを実行できます。

  この例では、共有メールボックスに送信された検疫済みメッセージすべてが表示され、リスト内の最初のメッセージが検疫から解放されます (リスト内の最初のメッセージは 0、2 番目は 1 など)。

  ```powershell
  $SharedMessages = Get-QuarantinedMessage -RecipientAddress officeparty@contoso.com | select -ExpandProperty Identity
  $SharedMessages
  Release-QuarantinedMessage -Identity $SharedMessages[0]
  ```

  構文およびパラメーターの詳細については、以下のトピックを参照してください。

  - [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage)
  - [Get-QuarantineMessageHeader](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessageheader)
  - [Preview-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage)
  - [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage)
