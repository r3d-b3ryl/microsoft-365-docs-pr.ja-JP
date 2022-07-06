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
description: ユーザーは、アクセス許可を持つ共有メールボックスに送信された検疫済みメッセージを表示して操作する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a37ed03535bd3f3b48aca81c7bf7adeb3c660b46
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2022
ms.locfileid: "66629015"
---
# <a name="view-and-release-quarantined-messages-from-shared-mailboxes"></a>共有メールボックスから検疫済みメッセージを表示および解放する

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**適用対象:**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

ユーザーは、「EOP で検疫されたメッセージを検索して解放する」の説明に従って、受信者の 1 つである [検疫済みメッセージを](find-and-release-quarantined-messages-as-a-user.md)管理できます。 ただし、「Exchange Onlineの **共有メールボックス**」で説明されているように、ユーザーがメールボックスへのフル アクセスと送信または代理で送信のアクセス許可を持つ [共有メールボックス](/exchange/collaboration-exo/shared-mailboxes)についてはどうでしょうか。

以前は、ユーザーが共有メールボックスに送信された検疫済みメッセージを管理するには、管理者が共有メールボックスに対して自動マッピングを有効のままにしておく必要があります (管理者が別のメールボックスへのアクセス権をユーザーに付与すると、既定で有効になっています)。 ただし、ユーザーがアクセスできるメールボックスのサイズと数によっては、Outlook がユーザーがアクセス権を持つ _すべての_ メールボックスを開こうとするため、パフォーマンスが低下する可能性があります。 このため、多くの管理者は [、共有メールボックスの自動マッピングを削除](/outlook/troubleshoot/profiles-and-accounts/remove-automapping-for-shared-mailbox)することを選択します。

これで、ユーザーが共有メールボックスに送信された検疫済みメッセージを管理するための自動マッピングは不要になりました。 動作するだけです。 共有メールボックスに送信された検疫済みメッセージにアクセスするには、次の 2 つの方法があります。

- 管理者が検疫通知を許可するように [検疫ポリシー](quarantine-policies.md)を構成している場合 (以前はエンド ユーザースパム通知と呼ばられていました)、共有メールボックスの検疫通知にアクセスできるユーザーは、通知の **[確認**] ボタンをクリックして、Microsoft 365 Defender ポータルの検疫に移動できます。 この方法では、ユーザーが共有メールボックスに送信された検疫済みメッセージのみを管理できる点に注意してください。 このコンテキストでは、ユーザーが独自の検疫メッセージを管理することはできません。
- ユーザーは [、Microsoft 365 Defender ポータルで検疫に移動](find-and-release-quarantined-messages-as-a-user.md)し、[**フィルター**] をクリックして **、受信者アドレス** (共有メールボックスの電子メール アドレス) で結果をフィルター処理できます。 メインの **[検疫]** ページで、[ **受信者]** 列をクリックして、共有メールボックスに送信されたメッセージで並べ替えることができます。

## <a name="things-to-keep-in-mind"></a>留意すべき点

- _検疫ポリシーでは、_ メッセージが検疫された理由 (サポートされている機能の場合) に基づいて、検疫済みメッセージに対してユーザーが許可または許可しない操作を定義します。 既定の検疫ポリシーでは、受信者がメッセージを表示して操作できるようにする履歴機能が適用されます。 管理者は、ユーザーに対して制限の少ない、またはより制限の厳しい機能を定義するカスタム検疫ポリシーを作成して適用できます。 詳細については、「[検疫ポリシー](quarantine-policies.md)」を参照してください。

- 検疫されたメッセージに対して最初に操作するユーザーは、共有メールボックスを使用するすべてのユーザーに対するメッセージの宿命を決定します。 たとえば、共有メールボックスに 10 人のユーザーがアクセスし、ユーザーが検疫メッセージを削除した場合、メッセージは 10 人のユーザー全員に対して削除されます。 同様に、ユーザーがメッセージを解放することにした場合、メッセージは共有メールボックスに解放され、共有メールボックスの他のすべてのユーザーがアクセスできます。

- 現時点では、[ **送信者のブロック** ] ボタンは、共有メールボックスに送信された検疫済みメッセージの **詳細** ポップアップでは使用できません。

- 共有メールボックスの検疫操作に関しては、入れ子になったセキュリティ グループを使用して共有メールボックスへのアクセスを許可する場合は、入れ子になったグループのレベルを 2 つ以下にすることをお勧めします。 たとえば、グループ A はグループ B のメンバーであり、グループ C のメンバーです。共有メールボックスにアクセス許可を割り当てるには、ユーザーをグループ A に追加してから、グループ C を共有メールボックスに割り当てないでください。

- 2022 年 7 月の時点で、ユーザー プリンシパル名 (UPN) とは異なるプライマリ SMTP アドレスを持つユーザーは、共有メールボックスの検疫済みメッセージにアクセスできる必要があります。

- [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) で共有メールボックスの検疫済みメッセージを管理するには、エンド ユーザーは _、RecipientAddress_ パラメーターの値に共有メールボックスの電子メール アドレスを含む [Get-QuarantineMessage](/powershell/module/exchange/get-quarantinemessage) コマンドレットを使用してメッセージを識別する必要があります。 例:

  ```powershell
  Get-QuarantineMessage -RecipientAddress officeparty@contoso.com
  ```

  その後、エンド ユーザーは、検疫されたメッセージを一覧から選択して、表示またはアクションを実行できます。

  次の使用例は、共有メールボックスに送信されたすべての検疫済みメッセージを示し、リスト内の最初のメッセージを検疫から解放します (リストの最初のメッセージは 0、2 番目のメッセージは 1 です)。

  ```powershell
  $SharedMessages = Get-QuarantineMessage -RecipientAddress officeparty@contoso.com | select -ExpandProperty Identity
  $SharedMessages
  Release-QuarantineMessage -Identity $SharedMessages[0]
  ```

  構文およびパラメーターの詳細については、以下のトピックを参照してください。

  - [Get-QuarantineMessage](/powershell/module/exchange/get-quarantinemessage)
  - [Get-QuarantineMessageHeader](/powershell/module/exchange/get-quarantinemessageheader)
  - [Preview-QuarantineMessage](/powershell/module/exchange/preview-quarantinemessage)
  - [Release-QuarantineMessage](/powershell/module/exchange/release-quarantinemessage)
