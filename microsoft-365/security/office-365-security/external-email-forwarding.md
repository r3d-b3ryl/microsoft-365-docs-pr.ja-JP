---
title: 外部メール転送の構成と制御を行Microsoft 365。
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/17/2021
audience: ITPro
ms.topic: overview
ms.collection: M365-security-compliance
ms.localizationpriority: medium
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: この記事では、外部メール転送、自動転送、5.7.520 Access Denied メッセージ、外部転送の無効化、"管理者が外部転送を無効にしました" メッセージ、および送信スパム対策ポリシーなどのトピックについて説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8df0ff9902fe22fd44a0d15f7f01e13e791c7b12
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64473609"
---
# <a name="control-automatic-external-email-forwarding-in-microsoft-365"></a>外部メールの自動転送を制御Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

管理者として、自動的に転送されるメッセージを外部受信者 (組織外の受信者) に制限または制御する会社の要件がある場合があります。 電子メールの転送は便利ですが、情報の漏えいによるセキュリティ リスクを引き起す可能性があります。 攻撃者は、この情報を使用して組織またはパートナーを攻撃する可能性があります。

自動転送の次の種類は、次のMicrosoft 365。

- ユーザーは受信 [トレイ ルールを](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) 構成して、メッセージを外部の送信者に自動的に転送できます (意図的に、またはアカウントが侵害された結果)。
- 管理者は、メールボックス転送 (_SMTP_ [転送](/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)とも呼ばれる) を構成して、メッセージを外部受信者に自動的に転送できます。 管理者は、単にメッセージを転送するか、転送されたメッセージのコピーをメールボックスに保持するか選択できます。

> [!NOTE]
> オンプレミスの電子メール システムから電子メール システムMicrosoft 365ユーザーは、今後の更新プログラムでクラウド メールボックスと同じポリシー制御の対象になります。 この更新プログラムは、メッセージ センターの投稿を介して伝達されます。

送信スパム フィルター ポリシーを使用して、外部受信者への自動転送を制御できます。 次の 3 つの設定を使用できます。

- **自動 - システム制御**: これは既定の設定です。 この設定は、Off と同 **じです**。 この設定が最初に導入された場合は、On と同等 **でした**。 時間がたつ間に、既定では [](secure-by-default.md)セキュリティ保護の原則のおかげで、この設定は、すべての顧客に対して徐々に **Off** に変更されました。 詳細については、このブログ [投稿を参照してください](https://techcommunity.microsoft.com/t5/exchange-team-blog/all-you-need-to-know-about-automatic-email-forwarding-in/ba-p/2074888)。 
- **On**: 自動外部転送は許可され、制限されません。
- **オフ**: 自動外部転送は無効になり、送信者に配信不可レポート (NDR またはバウンス メッセージとも呼ばれる) が発生します。

これらの設定を構成する方法については、「EOP で送信スパム フィルターを [構成する」を参照してください](configure-the-outbound-spam-policy.md)。

> [!NOTE]
>
> - 自動転送を無効にすると、メッセージを外部アドレスにリダイレクトする受信トレイ ルール (ユーザー) またはメールボックス転送 (管理者) が無効になります。
>
> - 内部ユーザー間のメッセージの自動転送は、送信スパム フィルター ポリシーの設定の影響を受け取らない。


## <a name="how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls"></a>送信スパム フィルター ポリシー設定が他の自動メール転送コントロールとどのように機能する

管理者は、電子メールの自動転送を許可またはブロックするように他のコントロールを既に構成している可能性があります。 次に例を示します。

- [一部またはすべての](/exchange/mail-flow-best-practices/remote-domains/remote-domains) 外部ドメインへの自動メール転送を許可またはブロックするリモート ドメイン。
- メール フロー ルール ([トランスポート Exchangeとも](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)呼ばれる) で、自動的に転送されたメッセージを検出して外部受信者にブロックする条件とアクション。

1 つの設定で外部転送が許可されているが、別の設定が外部転送をブロックすると、通常、ブロックは勝ちます。 例については、次の表で説明します。

|シナリオ|結果|
|---|---|
|<ul><li>自動転送を許可するリモート ドメイン設定を構成します。</li><li>送信スパム フィルター ポリシーの自動転送は Off に設定 **されます**。</li></ul>|影響を受けるドメイン内の受信者に自動的に転送されたメッセージはブロックされます。|
|<ul><li>自動転送を許可するリモート ドメイン設定を構成します。</li><li>送信スパム フィルター ポリシーの自動転送は、自動 **- システム制御に設定されます**。</li></ul>|影響を受けるドメイン内の受信者に自動的に転送されたメッセージはブロックされます。 <p> 前述したように、**Automatic - System-controlled** は On を意味するために使用されましたが、設定は時間の長い間、すべての組織で **Off** を意味するように変更されています。 <p> 明確にするために、送信スパム フィルター ポリシーを [オン] または [オフ] **に構成する** 必要 **があります**。|
|<ul><li>送信スパム フィルター ポリシーの自動転送が [オン] に設定 **されている**</li><li>メール フロー ルールまたはリモート ドメインを使用して、自動的に転送されるメールをブロックします。</li></ul>|影響を受ける受信者に自動的に転送されたメッセージは、メール フロー ルールまたはリモート ドメインによってブロックされます。|

この動作 (たとえば) を使用して、送信スパム フィルター ポリシーでの自動転送を許可しますが、リモート ドメインを使用して、ユーザーがメッセージを転送できる外部ドメインを制御できます。

## <a name="how-to-find-users-that-are-automatically-forwarding"></a>自動的に転送されるユーザーを検索する方法

メッセージを外部受信者に自動的に転送するユーザーに関する情報は、クラウドベース[](/exchange/monitoring/mail-flow-reports/mfr-auto-forwarded-messages-report)のアカウントの自動転送メッセージ レポートで確認できます。 オンプレミスの電子メール システムから Microsoft 365 経由で自動的に転送するオンプレミス ユーザーの場合は、これらのユーザーを追跡するメール フロー ルールを作成する必要があります。 メール フロー ルールを作成する方法については、「EAC を使用してメール フロー ルールを作成する [」を参照してください](/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#use-the-eac-to-create-a-mail-flow-rule)。

管理センター (EAC) でメール フロー ルールを作成するにはExchange情報が必要です。

- **(条件): メッセージ ヘッダーが** これらのテキスト パターンと **一**\>致する場合は **、このルールを適用します**。 このオプションを表示するには、[その他の **オプション] をクリック** する必要があります。
  - **ヘッダー名**: `X-MS-Exchange-Inbox-Rules-Loop`
  - **ヘッダー値**: `.`

  この条件は、'**X-MS-Exchange-Inbox-Rules-Loop'** ヘッダーが **'.' と一致します。**

  この条件は、ヘッダーの値と一致します。

- (省略可能) **次の操作** (アクション): オプションのアクションを構成できます。 たとえば、[メッセージのプロパティの変更\>] アクションを使用して、メッセージ ヘッダーを設定し、ヘッダー名 **X-Forwarded** と値 True を指定 **できます**。 ただし、アクションを構成する必要はありません。
- 重大度 **レベルを使用してこの rue を監査する値** を **Low**、 **Medium、または High に** 設定 **します**。 この設定を使用すると、転送Exchange[の](view-email-security-reports.md#exchange-transport-rule-report)詳細を取得するために、トランスポート ルール レポートを使用できます。

:::image type="content" source="../../media/mail-flow-rule-for-forwarded-messages.png" alt-text="転送されたメッセージを識別するルールの EAC のメール フロー ルールプロパティ" lightbox="../../media/mail-flow-rule-for-forwarded-messages.png":::


## <a name="blocked-email-forwarding-messages"></a>ブロックされたメール転送メッセージ

メッセージが自動的に転送されると検出され、送信スパム フィルター ポリシー[](configure-the-outbound-spam-policy.md)によってそのアクティビティがブロックされると、次の情報を含む NDR の送信者にメッセージが返されます。

`5.7.520 Access denied, Your organization does not allow external forwarding. Please contact your administrator for further assistance. AS(7555)`
