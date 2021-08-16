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
description: ユーザーは、アクセス許可を持つ共有メールボックスに送信された検疫済みメッセージを表示および処理する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 90c4476d2c882c98b6b24a738adc2d9e2a9d6244994bd8f82c36b0d1f544c488
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53883872"
---
# <a name="view-and-release-quarantined-messages-from-shared-mailboxes"></a>共有メールボックスから検疫済みメッセージを表示および解放する

> [!NOTE]
> この記事で説明する機能は、現在プレビュー中であり、すべてのユーザーが利用できる機能ではなく、変更される可能性があります。

ユーザーは [、「EOP](find-and-release-quarantined-messages-as-a-user.md)で検疫済みメッセージをユーザーとして検索して解放する」の説明に従って、検疫済みメッセージを受信者の 1 つとして管理できます。 しかし、「共有 **メールボックス**」の説明に従って、ユーザーがフル アクセスおよび Send As または Send on Behalf のアクセス許可を持つ共有メールボックス [については](/exchange/collaboration-exo/shared-mailboxes)、Exchange Online?

以前は、ユーザーが共有メールボックスに送信された検疫済みメッセージを管理するには、管理者が共有メールボックスの自動マッピングを有効のままにする必要がありました (管理者がユーザーに別のメールボックスへのアクセス権を与える場合、既定で有効になっています)。 ただし、ユーザーがアクセスできるメールボックスのサイズと数に応じて、Outlook がユーザーがアクセスできるすべてのメールボックスを開くしようとすると、パフォーマンスが低下する可能性があります。 このため、多くの管理者が共有メールボックス [の自動マップを削除する選択をします](/outlook/troubleshoot/profiles-and-accounts/remove-automapping-for-shared-mailbox)。

これで、ユーザーが共有メールボックスに送信された検疫済みメッセージを管理するために、自動マッピングは不要になります。 動作します。 共有メールボックスに送信された検疫済みメッセージにアクセスするには、次の 2 つの方法があります。

- 管理者がスパム対策[](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications)ポリシーでエンド ユーザースパム通知を有効にしている場合、共有メールボックス内のエンド ユーザースパム通知にアクセスできるユーザーは、通知の [確認] ボタンをクリックして、Microsoft 365 Defender ポータルで検疫に移動できます。 この方法では、ユーザーが共有メールボックスに送信された検疫済みメッセージのみを管理できます。 ユーザーは、このコンテキストで独自の検疫メッセージを管理できません。
- ユーザーは、[ポータルの検疫にMicrosoft 365 Defenderできます](find-and-release-quarantined-messages-as-a-user.md)。 既定では、ユーザーに送信されたメッセージだけが表示されます。 ただし、ユーザーは[結果の並べ替え] (既定では [メッセージ **ID]** ボタン) を [受信者の電子メール アドレス] に変更し、共有メールボックスの電子メール アドレスを入力し、[更新] をクリックして、共有メールボックスに送信された検疫済みメッセージを確認できます。 

  ![検疫済みメッセージを受信者の電子メール アドレスで並べ替える。](../../media/quarantine-sort-results-by-recipient-email-address.png)

方法に関係なく、ユーザーは検疫済みメッセージの **[受信者** ] 列を含め、混乱を回避できます。 表示する列の最大数は 7 なので、ユーザーは [列の変更] をクリックし、既存の列 (ポリシーの種類など) を削除し、[受信者] を選択し、[保存] または [既定で保存] をクリックする必要があります。 

  ![[ポリシーの種類] 列を削除し、[受信者] 列を検疫に追加します。](../../media/quarantine-add-recipient-column.png)

## <a name="things-to-keep-in-mind"></a>留意すべき点

- 検疫済みメッセージに対して最初に行動するユーザーは、共有メールボックスを使用するすべてのユーザーに対するメッセージの運命を決定します。 たとえば、共有メールボックスに 10 人のユーザーがアクセスし、ユーザーが検疫メッセージを削除する場合、メッセージは 10 人のユーザー全員に対して削除されます。 同様に、ユーザーがメッセージを解放すると判断した場合は、共有メールボックスに解放され、共有メールボックスの他のすべてのユーザーがアクセスできます。

- 現在、[**送信者のブロック]** ボタンは、共有メールボックスに送信された検疫済みメッセージの詳細フライアウトでは使用できません。

- 共有メールボックスの検疫操作について、入れ子になったセキュリティ グループを使用して共有メールボックスへのアクセスを許可する場合は、入れ子になったグループのレベルを 2 つ以下にすることをお勧めします。 たとえば、グループ A はグループ B のメンバーで、グループ C のメンバーです。共有メールボックスにアクセス許可を割り当てるには、ユーザーをグループ A に追加してから、グループ C を共有メールボックスに割り当てない。  

- [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)で共有メールボックスの検疫済みメッセージを管理するには、エンド ユーザーが _RecipientAddress_ パラメーターの値に対して共有メールボックスの電子メール アドレスを持つ [Get-QuarantineMessage](/powershell/module/exchange/get-quarantinemessage)コマンドレットを使用してメッセージを識別する必要があります。 次に例を示します。

  ```powershell
  Get-QuarantinedMessage -RecipientAddress officeparty@contoso.com
  ```

  次に、エンド ユーザーは、リストから検疫済みメッセージを選択して、表示またはアクションを実行できます。

  この例では、共有メールボックスに送信された検疫済みメッセージのすべてが表示され、リスト内の最初のメッセージが検疫から解放されます (リストの最初のメッセージは 0、2 番目は 1 など)。

  ```powershell
  $SharedMessages = Get-QuarantinedMessage -RecipientAddress officeparty@contoso.com | select -ExpandProperty Identity
  $SharedMessages
  Release-QuarantinedMessage -Identity $SharedMessages[0]
  ```

  構文およびパラメーターの詳細については、以下のトピックを参照してください。

  - [Get-QuarantineMessage](/powershell/module/exchange/get-quarantinemessage)
  - [Get-QuarantineMessageHeader](/powershell/module/exchange/get-quarantinemessageheader)
  - [Preview-QuarantineMessage](/powershell/module/exchange/preview-quarantinemessage)
  - [Release-QuarantineMessage](/powershell/module/exchange/release-quarantinemessage)
