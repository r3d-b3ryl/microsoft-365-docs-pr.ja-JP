---
title: メッセージで SCL にメール フロー ルールを使用する
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
description: メッセージを識別し、メッセージのスパム信頼レベル (SCL) を設定するメール フロー ルール (トランスポート ルール) を作成する方法についてExchange Online Protection。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 795347046342ea17870e7758a6327facf51315a4
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206094"
---
# <a name="use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages-in-eop"></a>メール フロー ルールを使用して EOP のメッセージのスパム信頼レベル (SCL) を設定する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Exchange Online またはスタンドアロン Exchange Online Protection (EOP) 組織に Exchange Online メールボックスがない Microsoft 365 組織では、EOP はスパム対策ポリシー (スパム フィルター ポリシーまたはコンテンツ フィルター ポリシーとも呼ばれる) を使用して、受信メッセージのスパムをスキャンします。 詳細については、「[EOP でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。

特定のメッセージをスパム フィルターでスキャンする前にスパムとしてマークする場合や、スパム フィルター処理をスキップするメッセージをマークする場合は、メール フロー ルール (トランスポート ルールとも呼ばれる) を作成してメッセージを識別し、スパム信頼レベル (SCL) を設定できます。 SCL の詳細については、「EOP の [スパム信頼レベル (SCL)」を参照してください](spam-confidence-levels.md)。

## <a name="what-do-you-need-to-know-before-you-begin"></a>始める前に把握しておくべき情報

- この記事の手順を実行するには、Exchange OnlineまたはExchange Online Protectionにアクセス許可を割り当てる必要があります。 具体的には、既定では、組織の管理、コンプライアンス管理 **(グローバル** 管理者)、レコード管理の役割グループに割り当てられているトランスポート ルールの役割が必要です。 

  詳細については、次のトピックをご覧ください。

  - [Exchange Online のアクセス許可](/exchange/permissions-exo/permissions-exo)
  - [スタンドアロン EOP のアクセス許可](feature-permissions-in-eop.md)
  - [役割グループ内のメンバーの一覧を変更する EAC を使用する](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- EAC を開く方法については、「Exchange Onlineの管理[Exchange」を参照Exchange Online。](/Exchange/exchange-admin-center) スタンドアロン EOP で EAC を開く方法については、「スタンドアロン[EOP Exchange管理センター」を参照してください](exchange-admin-center-in-exchange-online-protection-eop.md)。

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。 スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。

- メール フロー ルールの詳細については、「Exchange Online および Exchange Online Protection」の「メール フロー ルール (トランスポート[ルール)」を参照Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

## <a name="use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message"></a>EAC を使用して、メッセージの SCL を設定するメール フロー ルールを作成する

1. EAC で、 **[メール フロー]** \> **[ルール]** に移動します。

2. [追加 **] アイコン** ![ をクリックし ](../../media/ITPro-EAC-AddIcon.png) 、[新しいルール **の作成] を選択します**。

3. **[新しいルール]** のページが開いたら、以下の設定を行ってください:

   - **名前**: ルールの一意でわかりやすい名前を入力します。

   - [**その他のオプション**] をクリックします。

   - **[ メッセージを識別する** 1 つ以上の条件を選択する] の場合は、このルールを適用します。 詳細については、「メール フロー ルールの条件と例外[(述語)」](/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)を参照Exchange Online。

   - **[メッセージのプロパティを** 変更 **する] を選択** \> **して、スパム信頼レベル (SCL) を設定します**。 表示される **[SCL の指定** ] ダイアログで、次のいずれかの値を構成します。

   - **[スパム フィルターのバイパス**] : メッセージはスパム フィルター処理をスキップします。

     > [!CAUTION]
     > メッセージでスパム フィルター処理をスキップできるように注意してください。 攻撃者はこの脆弱性を利用して、フィッシングなどの悪意のあるメッセージを組織に送信できます。 メール フロー ルールには、送信者の電子メール アドレスまたはドメイン以上の情報が必要です。 詳細については、「EOP で差出人 [セーフ リストを作成する」を参照してください](create-safe-sender-lists-in-office-365.md)。

   - **0 ~ 4**: メッセージはスパム フィルターを介して送信され、追加の処理が行います。

   - **5 または 6**: メッセージはスパムとしてマーク **されます**。 スパム対策ポリシーでスパム フィルターの評決に対して構成したアクションがメッセージに適用されます (既定値は [メッセージを迷惑メール フォルダーに移動する]**です**)。

   - **7 ~ 9**: メッセージは高信頼スパム **としてマークされます**。 スパム対策ポリシーで信頼度の高いスパム フィルターの評決を構成したアクションがメッセージに適用されます (既定値は [メッセージを迷惑メール フォルダーに移動 **する]** です)。

4. ルールに必要な追加のプロパティを指定します。 完了したら、**[保存]** をクリックします。

## <a name="how-do-you-know-this-worked"></a>正常な動作を確認する方法

この処理が正常に動作することを確認するには、組織内のユーザーに電子メール メッセージを送信し、必要なアクションがメッセージに対して実行されたかどうかを確認します。 たとえば、 **[SCL (Spam Confidence Level) の設定]** を **[スパム対策フィルターのバイパス]** に設定した場合、メッセージは指定された受信者の受信トレイに送信される必要があります。 ただし、スパム信頼レベル **(SCL)** を **9** に設定し、該当するスパム対策ポリシーの [高信頼スパム] アクションが [迷惑メール] フォルダーにメッセージを移動する場合は、メッセージを指定した受信者の迷惑メール フォルダーに送信する必要があります。