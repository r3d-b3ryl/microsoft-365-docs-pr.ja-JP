---
title: Outlook の誤検出と検出漏れを報告する
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: Admin
ms.topic: how-to
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
description: レポート メッセージ機能を使用して、Outlookで誤検知と誤検知を報告する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8f52b4d085c13f2e1e1a48c2a8a12e6782f13960
ms.sourcegitcommit: 45bc65972d4007b2aa7760d4457a0d2699f81926
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2022
ms.locfileid: "64974105"
---
# <a name="report-false-positives-and-false-negatives-in-outlook"></a>Outlook の誤検出と検出漏れを報告する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
> Exchange Onlineメールボックスを持つMicrosoft 365組織の管理者の場合は、Microsoft 365 Defender ポータルの **[申請]** ページを使用することをお勧めします。 詳細については、「 [申請ポータルを使用して、疑わしいスパム、フィッシング、URL、およびファイルを Microsoft に送信する」を参照してください](admin-submission.md)。

ハイブリッドモダン認証を使用して、Exchange Onlineまたはオンプレミスのメールボックスにメールボックスを含むMicrosoft 365組織では、偽陽性 (ブロックまたは迷惑メール フォルダーに送信された適切なメール) と偽陰性 (受信トレイに配信された不要なメールまたはフィッシング) をExchange Online Protection (EOP) に送信できます。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- 最適なユーザー申請エクスペリエンスを得るには、レポート メッセージ アドインまたはレポート フィッシング アドインを使用します。

- レポート メッセージ アドインとレポート フィッシング アドインは、すべてのプラットフォーム (Outlook on the web、iOS、Android、デスクトップ) のOutlookに対して機能します。

- Exchange Online メールボックスを持つ組織内の管理者の場合は、Microsoft 365 Defender ポータルの申請ポータルを使用します。 詳細については、「 [管理者申請を使用して、疑わしいスパム、フィッシング、URL、およびファイルを Microsoft に送信する」を参照してください](admin-submission.md)。

- Microsoft、指定したメールボックス、またはその両方にメッセージを直接送信するように構成できます。 詳細については、「 [ユーザー申請ポリシー](user-submission.md)」を参照してください。

- レポート メッセージまたはレポート フィッシング アドインを取得して有効にする方法の詳細については、「 [レポート メッセージまたはレポート フィッシング アドインを有効にする](enable-the-report-message-add-in.md)」を参照してください。

- Microsoft にメッセージを報告する方法の詳細については、「メッセージ [とファイルを Microsoft に報告する」を参照してください](report-junk-email-messages-to-microsoft.md)。

### <a name="turn-off-the-built-in-reporting-experience"></a>組み込みのレポート エクスペリエンスを無効にする

[Outlookでは、ユーザー送信ポリシー](./user-submission.md)を使用できないため、組み込みのレポート エクスペリエンスはお勧めしません。 代わりに、レポート メッセージ アドインまたはレポート フィッシング アドインを使用することをお勧めします。

このコマンドレットを実行する際には、あらかじめアクセス許可を割り当てる必要があります。 コマンドレットを組織内で実行するために必要になるアクセス許可とパラメーターを調べるには、「 [Find the permissions required to run any Exchange cmdlet](/powershell/exchange/find-exchange-cmdlet-permissions)」を参照してください。

次の PowerShell コマンドを実行して、Outlook on the webの組み込みのレポート エクスペリエンスを無効にします。

```powershell
Set-OwaMailboxPolicy -Identity OwaMailboxPolicy-Default -ReportJunkEmailEnabled $false
```

## <a name="use-the-report-message-feature"></a>レポート メッセージ機能を使用する

### <a name="report-junk-and-phishing-messages"></a>迷惑メールとフィッシング メッセージを報告する

受信トレイまたは迷惑メールを除くその他のメール フォルダー内のメッセージの場合は、次の方法を使用してスパムメッセージとフィッシング メッセージを報告します。

1. 選択したメッセージの右上隅にある **[その他のアクション** ] 省略記号を選択し、ドロップダウン メニューから [ **メッセージの報告** ] を選択して、[ **迷惑メール]** または [ **フィッシング]** を選択します。

   :::image type="content" source="../../media/report-message-more-actions.png" alt-text="[その他のアクション] アイコン" lightbox="../../media/report-message-more-actions.png":::

   :::image type="content" source="../../media/report-message-junk-phishing.png" alt-text="[レポート メッセージ] ウィンドウの [迷惑メールとフィッシング] オプション" lightbox="../../media/report-message-junk-phishing.png":::

2. 選択したメッセージは、分析のために Microsoft に送信され、次のようになります。
   - 迷惑メールとして報告された場合は、[迷惑メール] フォルダーに移動しました。
   - フィッシングとして報告された場合は削除されます。

### <a name="report-messages-that-are-not-junk"></a>迷惑メールではないメッセージを報告する

1. 選択したメッセージの右上隅にある **[その他のアクション** ] 省略記号を選択し、ドロップダウン メニューから **[レポート メッセージ** ] を選択して、[ **迷惑メール]** を選択します。

   :::image type="content" source="../../media/report-message-more-actions.png" alt-text="より多くのアクションを提供するアイコン" lightbox="../../media/report-message-more-actions.png":::

   :::image type="content" source="../../media/report-message-not-junk.png" alt-text="[レポート メッセージ] ウィンドウの [迷惑ではない] オプション" lightbox="../../media/report-message-not-junk.png":::

2. 選択したメッセージは分析のために Microsoft に送信され、受信トレイまたはその他の指定されたフォルダーに移動されます。

## <a name="view-and-review-reported-messages"></a>報告されたメッセージを表示および確認する

ユーザーが Microsoft に報告するメッセージを確認するには、次のオプションがあります。

- Microsoft 365 Defender ポータルの **[申請]** ページを使用します。 詳細については、「 [Microsoft へのユーザー申請を表示する」を参照してください](admin-submission.md#view-user-submissions-to-microsoft)。
- 報告されたメッセージのコピーを送信するメール フロー ルール (トランスポート ルールとも呼ばれます) を作成します。 手順については、「 [メール フロー ルールを使用して、Microsoft に報告しているユーザーを確認する」を参照してください](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-see-what-users-are-reporting-to-microsoft)。
