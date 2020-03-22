---
title: メッセージ内の SCL にメールフロールールを使用する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 4ccab17a-6d49-4786-aa28-92fb28893e99
ms.collection:
- M365-security-compliance
description: 管理者は、Exchange Online Protection でメッセージの SCL を設定する方法について説明します。
ms.openlocfilehash: b7ea9a0f046e5a48f0de8d4ac9ae6d53821f03c0
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895097"
---
# <a name="use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages"></a>メール フロー ルールを使用して、メッセージの Spam Confidence Level (SCL) を設定する

Exchange Online または exchange online メールボックスを持たないスタンドアロンの Exchange Online Protection (EOP) 顧客のメールボックスを使用している Office 365 お客様の場合、EOP では、スパム対策ポリシー (スパムフィルターポリシーまたはコンテンツフィルターポリシーとも呼ばれます) を使用してスキャンします。スパムの受信メッセージ。 詳細については、「 [Office 365 でスパム対策ポリシーを構成する](configure-your-spam-filter-policies.md)」を参照してください。

特定のメッセージをスパムフィルターによってもスキャンされる前に、スパムとしてマークしたり、スパムフィルター処理をスキップするようメッセージをマークしたりするには、メールフロールール (トランスポートルールとも呼ばれます) を作成して、メッセージを識別し、スパム信頼レベル (SCL) を設定できます。 SCL の詳細については、「 [Office 365 のスパム信頼レベル (SCL)](spam-confidence-levels.md)」を参照してください。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- これらの手順を実行する前に、Exchange Online でアクセス許可を割り当てる必要があります。 具体的には、既定では、**組織の管理**、**コンプライアンス管理**、および**レコード管理**の役割に割り当てられている**トランスポートルール**の役割が割り当てられている必要があります。 詳細については、「[Exchange Online で役割グループを管理する](https://docs.microsoft.com/Exchange/permissions-exo/role-groups)」を参照してください。

- Exchange Online で EAC を開くには、「exchange [online の exchange 管理センター](https://docs.microsoft.com/Exchange/exchange-admin-center)」を参照してください。

- Exchange Online のメールフロールールの詳細については、「[メールフロールール (トランスポートルール) (Exchange online)](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) 」を参照してください。

## <a name="use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message"></a>EAC を使用して、メッセージの SCL を設定するメールフロールールを作成する

1. EAC で、 **[メール フロー]** \> **[ルール]** に移動します。

2. [追加] アイコン](../../media/ITPro-EAC-AddIcon.png) **をクリックし**、[**新しいルールの作成**] を選択します。 ![

3. **[新しいルール]** のページが開いたら、以下の設定を行ってください:

   - [**名前**]: わかりやすい一意のルールの名前を入力します。

   - [**その他のオプション**] をクリックします。

   - [次の**場合、このルールを適用**する]: メッセージを識別する1つまたは複数の条件を選択します。 詳細については、「 [Exchange Online のメールフロールールの条件と例外 (述語)](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)」を参照してください。

   - **次の操作を行い**ます。 [ \> **メッセージのプロパティを変更する**] [**スパム信頼レベル (SCL) を設定**する] を選択します。 表示される [ **SCL の指定**] ダイアログで、次のいずれかの値を構成します。

   - **スパムフィルターをバイパス**する: SCL を-1 に設定します。これは、メッセージがスパムフィルター処理をスキップすることを意味します。

     > [!CAUTION]
     > メッセージでスパムフィルターをスキップすることについて慎重に検討してください。 攻撃者はこの脆弱性を利用して、フィッシングやその他の悪意のあるメッセージを組織に送信することができます。 メールフロールールには、送信者の電子メールアドレスまたはドメインだけではなく、より多くの情報が必要です。 詳細については、「 [Office の信頼できる差出人のリストを作成する 365](create-safe-sender-lists-in-office-365.md)」を参照してください。

   - **0 ~ 4**: メッセージは、スパムフィルタリングを介して送信され、追加の処理が行われます。

   - **5 または 6**: メッセージは**スパム**としてマークされます。 スパム対策ポリシーで verdicts**スパム**フィルター処理用に構成したアクションがメッセージに適用されます (既定値は **[迷惑メールフォルダーにメッセージを移動**します)]。

   - **7 ~ 9**: メッセージは、**信頼度の高いスパム**としてマークされます。 迷惑メール対策ポリシーで、**高信頼度の高いスパム**フィルター処理に対して構成したアクションがメッセージに適用されます (既定値は **[迷惑メールフォルダーにメッセージを移動**] です)。

4. ルールに必要な追加のプロパティを指定します。 完了したら、**[保存]** をクリックします。

## <a name="how-do-you-know-this-worked"></a>正常な動作を確認する方法

この処理が正常に動作することを確認するには、組織内のユーザーに電子メール メッセージを送信し、必要なアクションがメッセージに対して実行されたかどうかを確認します。たとえば、 **[SCL (Spam Confidence Level) の設定]** を **[スパム対策フィルターのバイパス]** に設定した場合、メッセージは指定された受信者の受信トレイに送信される必要があります。また、 **[SCL (Spam Confidence Level) の設定]** を **9** に設定し、適用可能なコンテンツ フィルター ポリシーの **[精度の高いスパム]** に対するアクションが迷惑メール フォルダーへのメッセージの送信である場合、メッセージは指定された受信者の迷惑メール フォルダーに送られる必要があります。
