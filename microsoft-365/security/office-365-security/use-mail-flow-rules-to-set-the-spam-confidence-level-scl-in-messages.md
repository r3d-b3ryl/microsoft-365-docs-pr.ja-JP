---
title: メッセージ内の SCL にメール フロー ルールを使用する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 4ccab17a-6d49-4786-aa28-92fb28893e99
ms.collection:
- M365-security-compliance
description: メール フロー ルール (トランスポート ルール) を作成してメッセージを特定し、Exchange Online Protection でそのメッセージの Spam Confidence Level (SCL) を設定する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 67a4c25a1006e9b1554cf8ffbc2d5e29b4063752
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827375"
---
# <a name="use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages-in-eop"></a>メール フロー ルールを使用して、EOP のメッセージの Spam Confidence Level (SCL) を設定する

Exchange Online にメールボックスがある Microsoft 365 組織や、Exchange Online メールボックスを使用しないスタンドアロンの Exchange Online Protection (EOP) 組織では、EOP はスパム対策ポリシー (スパム フィルター ポリシーまたはコンテンツ フィルター ポリシーとも呼ばれる) を使用して、スパムがないか受信メッセージをスキャンします。 詳細については、「[EOP でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。

特定のメッセージがスパム フィルターによってスキャンされる前にスパムとしてマークする、またはスパム フィルター処理を省略してメッセージにマージするには、メール フロー ルール (トランスポート ルールとも呼ばれる) を作成してメッセージを特定して Spam Confidence Level (SCL) を設定できます。 SCL の詳細については、EOP の [Spam Confidence Level (SCL) を参照してください](spam-confidence-levels.md)。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- これらの手順を実行する前に、Exchange Online でアクセス許可を割り当てる必要があります。 特に、組織管理、コンプライアンス管理、**およびレコード**管理の各役割に既定で**Organization Management**割り当てられる **、** トランスポート ルールの**役割を割り**当てる必要があります。 詳細については、「[Exchange Online で役割グループを管理する](https://docs.microsoft.com/Exchange/permissions-exo/role-groups)」を参照してください。

- Exchange Online の EAC を開くには、「Exchange Online [の Exchange 管理センター」を参照してください](https://docs.microsoft.com/Exchange/exchange-admin-center)。

- Exchange Online でのメール フロー ルールの詳細については、Exchange Online の「 [メール フロー ルール (トランスポート ルール)」を参照してください。](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

## <a name="use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message"></a>EAC を使用して、メッセージの SCL を設定するメール フロー ルールを作成する

1. EAC で、 **[メール フロー]** \> **[ルール]** に移動します。

2. [追加 **] アイコン** ![ をクリック ](../../media/ITPro-EAC-AddIcon.png) し、[新しい **ルールを作成する] を選択します**。

3. **[新しいルール]** のページが開いたら、以下の設定を行ってください:

   - **名前**: わかりやすい一意のルールの名前を入力します。

   - [**その他のオプション**] をクリックします。

   - **メッセージを識別する条件を**1 つ以上選択した場合に、このルールを適用します。 詳細については [、Exchange Online のメール フロー ルールの条件と例外 (述語) を参照してください](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)。

   - **次の手順**を **行います。メッセージプロパティを** \> **変更すると、SCL (Spam Confidence Level) が設定されます**。 表示される **SCL の** 指定ダイアログで、次のいずれかの値を構成します。

   - **スパム フィルター処理をバイパス**する: メッセージはスパム フィルター処理をスキップします。

     > [!CAUTION]
     > メッセージがスパム フィルタリングをスキップできるのを非常に大きく行ってください。 攻撃者は、この脆弱性を使用して、フィッシングやその他の悪意のあるメッセージを組織に送信できます。 メール フロー ルールには、送信者のメール アドレスまたはドメインだけが必要です。 詳細については、「EOP で差出 [人セーフ リストを作成する」を参照してください](create-safe-sender-lists-in-office-365.md)。

   - **0 ~ 4:** 追加の処理に関してメッセージがスパム フィルタリングによって送信されます。

   - **5 または 6:** メッセージはスパムとしてマーク **されます**。 スパム対策ポリシーでスパム フィルター **の確認に** 構成したアクションが、メッセージに適用されます (既定値は **、メッセージを [迷惑メール フォルダーに移動] です**)。

   - **7 ~ 9:** メッセージは高信頼 **スパムとしてマークされます**。 スパム対策ポリシーで **高** 信頼スパム対策フィルターの確認に構成したアクションが、メッセージに適用されます (既定値は **[迷惑メール フォルダーにメッセージを移動] です**)。

4. ルールに必要なその他のプロパティを指定します。 完了したら、**[保存]** をクリックします。

## <a name="how-do-you-know-this-worked"></a>正常な動作を確認する方法

この処理が正常に動作することを確認するには、組織内のユーザーに電子メール メッセージを送信し、必要なアクションがメッセージに対して実行されたかどうかを確認します。 たとえば、 **[SCL (Spam Confidence Level) の設定]** を **[スパム対策フィルターのバイパス]** に設定した場合、メッセージは指定された受信者の受信トレイに送信される必要があります。 ただし **、SCL (Spam Confidence Level)** を **9**に設定し、該当するスパム対策ポリシーに **対する高信頼** スパム対策アクションがメッセージを迷惑メール フォルダーに移動する場合、メッセージは指定された受信者の迷惑メール フォルダーに送る必要があります。
