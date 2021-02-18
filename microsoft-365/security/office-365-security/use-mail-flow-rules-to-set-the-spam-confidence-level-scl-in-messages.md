---
title: メッセージ内の SCL へのメール フロー ルールの使用
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 4ccab17a-6d49-4786-aa28-92fb28893e99
ms.collection:
- M365-security-compliance
description: Exchange Online Protection でメッセージを識別し、メッセージの SCL (Spam Confidence Level) を設定するメール フロー ルール (トランスポート ルール) を作成する方法について学習します。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: aa2893214543f77114d517dc38f874d6172a920a
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287559"
---
# <a name="use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages-in-eop"></a>メール フロー ルールを使用して EOP 内のメッセージの Spam Confidence Level (SCL) を設定する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Exchange Online または Exchange Online メールボックスのないスタンドアロンの Exchange Online Protection (EOP) 組織にメールボックスがある Microsoft 365 組織では、EOP はスパム対策ポリシー (スパム フィルター ポリシーまたはコンテンツ フィルター ポリシーとも呼ばれる) を使用して、受信メッセージにスパムがないかスキャンします。 詳細については、「[EOP でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。

特定のメッセージをスパム フィルターでスキャンする前にスパムとしてマークする場合や、スパム フィルター処理をスキップするメッセージをマークする場合は、メール フロー ルール (トランスポート ルールとも呼ばれる) を作成してメッセージを識別し、Spam Confidence Level (SCL) を設定できます。 SCL の詳細については [、EOP の「Spam Confidence Level (SCL)」を参照してください](spam-confidence-levels.md)。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- この記事の手順を実行する前に、Exchange Online または Exchange Online Protection でアクセス許可を割り当てる必要があります。 具体的には、既定で組織の管理、コンプライアンス管理 **(グローバル** 管理者)、および **レコード** 管理の役割グループに割り当てられるトランスポート ルールの役割が必要です。

  詳細については、次のトピックをご覧ください。

  - [Exchange Online のアクセス許可](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)
  - [スタンドアロン EOP のアクセス許可](feature-permissions-in-eop.md)
  - [EAC を使用して役割グループのメンバーの一覧を変更する](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- Exchange Online で EAC を開く方法については [、Exchange Online の Exchange 管理センターを参照してください](https://docs.microsoft.com/Exchange/exchange-admin-center)。 スタンドアロン EOP で EAC を開く方法については、 [スタンドアロン EOP の Exchange 管理センターを参照してください](exchange-admin-center-in-exchange-online-protection-eop.md)。

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。 スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。

- Exchange Online および Exchange Online Protection のメール フロー ルールの詳細については、「Exchange Online のメール フロー ルール[(トランスポート ルール)」を参照してください](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)。

## <a name="use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message"></a>EAC を使用して、メッセージの SCL を設定するメール フロー ルールを作成する

1. EAC で、 **[メール フロー]** \> **[ルール]** に移動します。

2. [追加 **] アイコン** ![ をクリックし ](../../media/ITPro-EAC-AddIcon.png) 、[新しいルールの **作成] を選択します**。

3. **[新しいルール]** のページが開いたら、以下の設定を行ってください:

   - **[名前**]: ルールのわかりやすい一意の名前を入力します。

   - [**その他のオプション**] をクリックします。

   - **次の場合にこのルールを適用** します。メッセージを識別する 1 つ以上の条件を選択します。 詳細については [、Exchange Online のメール フロー ルールの条件と例外 (述語) を参照してください](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)。

   - **Do the following**: Select **Modify the message properties** set the spam confidence level \> **(SCL)**. 表示される **[SCL の** 指定] ダイアログで、次のいずれかの値を構成します。

   - **スパム フィルターをバイパス** する : メッセージはスパム フィルター処理をスキップします。

     > [!CAUTION]
     > メッセージがスパム フィルタリングをスキップすることを許可することを十分に注意してください。 攻撃者はこの脆弱性を利用して、フィッシング詐欺などの悪意のあるメッセージを組織に送信できます。 メール フロー ルールには、送信者の電子メール アドレスまたはドメイン以外の情報が必要です。 詳細については、「EOP で差出人 [セーフ リストを作成する」を参照してください](create-safe-sender-lists-in-office-365.md)。

   - **0 ~ 4**: メッセージはスパム フィルターを使用して送信され、追加の処理が行されます。

   - **5 または 6**: メッセージはスパムとしてマーク **されます**。 スパム対策ポリシーでスパム フィルターの条件に対して構成したアクションがメッセージに適用されます (既定値は [メッセージを迷惑メール フォルダーに移動する]**です**)。

   - **7 ~ 9:** メッセージは信頼度の高いスパム **としてマークされます**。 スパム対策ポリシーで信頼度の高いスパム フィルターの条件に対して構成したアクションがメッセージに適用されます (既定値は [メッセージを迷惑メール フォルダーに移動する]**です)。**

4. ルールに必要な追加のプロパティを指定します。 完了したら、**[保存]** をクリックします。

## <a name="how-do-you-know-this-worked"></a>正常な動作を確認する方法

この処理が正常に動作することを確認するには、組織内のユーザーに電子メール メッセージを送信し、必要なアクションがメッセージに対して実行されたかどうかを確認します。 たとえば、 **[SCL (Spam Confidence Level) の設定]** を **[スパム対策フィルターのバイパス]** に設定した場合、メッセージは指定された受信者の受信トレイに送信される必要があります。 ただし **、Spam Confidence Level (SCL)** を **9** に設定し、適用可能なスパム対策ポリシーの信頼度の高いスパムアクションがメッセージを [迷惑メール] フォルダーに移動する場合、メッセージは指定した受信者の迷惑メール フォルダーに送信されます。
