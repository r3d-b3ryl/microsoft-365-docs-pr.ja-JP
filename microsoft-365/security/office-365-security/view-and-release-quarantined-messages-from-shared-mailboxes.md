---
title: 共有メールボックスから検疫済みメッセージを表示および解放する
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: ''
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
ROBOTS: NOINDEX
description: ユーザーは、アクセス許可を持つ共有メールボックスに送信された検疫済みメッセージを表示および処理する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e78a46bca97ea58a88195c9d05e11332528cf3af
ms.sourcegitcommit: 317fab13e84b2867087a6ba0a593313ecf43bbed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2021
ms.locfileid: "60364870"
---
# <a name="view-and-release-quarantined-messages-from-shared-mailboxes"></a>共有メールボックスから検疫済みメッセージを表示および解放する

> [!NOTE]
> この記事で説明する機能は、現在プレビュー中であり、すべてのユーザーが利用できる機能ではなく、変更される可能性があります。

ユーザーは [、「EOP](find-and-release-quarantined-messages-as-a-user.md)で検疫済みメッセージをユーザーとして検索して解放する」の説明に従って、検疫済みメッセージを受信者の 1 つとして管理できます。 しかし、「共有 **メールボックス**」の説明に従って、ユーザーがフル アクセスおよび Send As または Send on Behalf のアクセス許可を持つ共有メールボックス [については](/exchange/collaboration-exo/shared-mailboxes)、Exchange Online?

以前は、ユーザーが共有メールボックスに送信された検疫済みメッセージを管理するには、管理者が共有メールボックスの自動マッピングを有効のままにする必要がありました (管理者がユーザーに別のメールボックスへのアクセス権を与える場合、既定で有効になっています)。 ただし、ユーザーがアクセスできるメールボックスのサイズと数に応じて、Outlook がユーザーがアクセスできるすべてのメールボックスを開くしようとすると、パフォーマンスが低下する可能性があります。 このため、多くの管理者が共有メールボックス [の自動マップを削除する選択をします](/outlook/troubleshoot/profiles-and-accounts/remove-automapping-for-shared-mailbox)。

これで、ユーザーが共有メールボックスに送信された検疫済みメッセージを管理するために、自動マッピングは不要になります。 動作します。 共有メールボックスに送信された検疫済みメッセージにアクセスするには、次の 2 つの方法があります。

- 管理者が検疫通知[](quarantine-policies.md)(以前はエンド ユーザースパム通知と呼ばれる) を許可するように検疫ポリシーを構成している場合、共有メールボックス内の検疫通知にアクセスできるユーザーは、通知の [確認] ボタンをクリックして、Microsoft 365 Defender ポータルの検疫に移動できます。 この方法では、ユーザーが共有メールボックスに送信された検疫済みメッセージのみを管理できます。 ユーザーは、このコンテキストで独自の検疫メッセージを管理できません。
- ユーザーは、Microsoft 365 Defender ポータルで検疫に [移動し、[](find-and-release-quarantined-messages-as-a-user.md)フィルター]をクリックして、受信者アドレス **(共有** メールボックスの電子メール アドレス) で結果をフィルター処理できます。 メインの [**検疫] ページ** で、[受信者] 列をクリックして、共有メールボックスに送信されたメッセージで並べ替えを行います。

## <a name="things-to-keep-in-mind"></a>留意すべき点

- _検疫ポリシーは、_ メッセージが検疫された理由 (サポートされている機能の場合) に基づいて、検疫されたメッセージに対してユーザーが許可される操作または実行しない操作を定義します。 既定の検疫ポリシーでは、受信者がメッセージを表示および処理できる履歴機能が適用されます。 管理者は、ユーザーの制限が少ない、または制限の厳しい機能を定義するカスタム検疫ポリシーを作成して適用できます。 詳細については、「[検疫ポリシー](quarantine-policies.md)」を参照してください。

- 検疫済みメッセージに対して最初に行動するユーザーは、共有メールボックスを使用するすべてのユーザーに対するメッセージの運命を決定します。 たとえば、共有メールボックスに 10 人のユーザーがアクセスし、ユーザーが検疫メッセージを削除する場合、メッセージは 10 人のユーザー全員に対して削除されます。 同様に、ユーザーがメッセージを解放すると判断した場合は、共有メールボックスに解放され、共有メールボックスの他のすべてのユーザーがアクセスできます。

- 現在、[**送信者のブロック]** ボタンは、共有メールボックスに送信された検疫済みメッセージの詳細フライアウトでは使用できません。

- 共有メールボックスの検疫操作について、入れ子になったセキュリティ グループを使用して共有メールボックスへのアクセスを許可する場合は、入れ子になったグループのレベルを 2 つ以下にすることをお勧めします。 たとえば、グループ A はグループ B のメンバーで、グループ C のメンバーです。共有メールボックスにアクセス許可を割り当てるには、ユーザーをグループ A に追加してから、グループ C を共有メールボックスに割り当てない。  

- [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)で共有メールボックスの検疫済みメッセージを管理するには、エンド ユーザーが _RecipientAddress_ パラメーターの値に対して共有メールボックスの電子メール アドレスを持つ [Get-QuarantineMessage](/powershell/module/exchange/get-quarantinemessage)コマンドレットを使用してメッセージを識別する必要があります。 例:

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
