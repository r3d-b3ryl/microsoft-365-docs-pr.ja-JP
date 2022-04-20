---
title: Microsoft 365での外部メール転送の構成と制御。
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
description: この記事では、外部メール転送、自動転送、5.7.520 アクセス拒否メッセージ、外部転送の無効化、"管理者が外部転送を無効にしました" メッセージ、送信スパム対策ポリシーなどのトピックについて説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 672e6af3d2aef76a0c944a05c438061861e20060
ms.sourcegitcommit: 45bc65972d4007b2aa7760d4457a0d2699f81926
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2022
ms.locfileid: "64971905"
---
# <a name="control-automatic-external-email-forwarding-in-microsoft-365"></a>Microsoft 365 で外部メールの自動転送を制御する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

管理者として、外部の受信者 (組織外の受信者) に自動的に転送されるメッセージを制限または制御する会社の要件がある場合があります。 電子メール転送は役に立ちますが、情報の漏えいの可能性があるため、セキュリティ 上のリスクを引き起こす可能性もあります。 攻撃者は、この情報を使用して組織またはパートナーを攻撃する可能性があります。

Microsoft 365では、次の種類の自動転送を使用できます。

- ユーザーは、外部の送信者にメッセージを自動的に転送するように [受信トレイ ルール](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) を構成できます (意図的に、または侵害されたアカウントの結果として)。
- 管理者は、外部受信者にメッセージを自動的に転送するように [メールボックス](/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)_転送 (SMTP 転送_ とも呼ばれます) を構成できます。 管理者は、メッセージを単に転送するか、転送されたメッセージのコピーをメールボックスに保持するかを選択できます。

> [!NOTE]
> オンプレミスの電子メール システムからMicrosoft 365への自動転送を使用するユーザーは、今後の更新プログラムでクラウド メールボックスと同じポリシー制御の対象になります。 この更新プログラムは、メッセージ センターの投稿を介して通信されます。

送信スパム フィルター ポリシーを使用して、外部受信者への自動転送を制御できます。 次の 3 つの設定を使用できます。

- **自動 - システム制御**: これは既定の設定です。 この設定は **オフ** と同じになりました。 この設定が最初に導入されたときは、 **On** と同等でした。 時間の経過と共に、 [既定ではセキュリティ保護](secure-by-default.md)の原則のおかげで、この設定は、すべての顧客に対して徐々に **[オフ]** に変更されました。 詳細については、 [このブログ投稿](https://techcommunity.microsoft.com/t5/exchange-team-blog/all-you-need-to-know-about-automatic-email-forwarding-in/ba-p/2074888)を参照してください。
- **オン**: 自動外部転送は許可され、制限されません。
- **オフ**: 自動外部転送が無効になり、配信不能レポート (NDR またはバウンス メッセージとも呼ばれます) が送信者に送信されます。

これらの設定を構成する方法については、「 [EOP で送信スパム フィルターを構成する](configure-the-outbound-spam-policy.md)」を参照してください。

> [!NOTE]
>
> - 自動転送を無効にすると、メッセージを外部アドレスにリダイレクトするすべての受信トレイ ルール (ユーザー) またはメールボックス転送 (管理者) が無効になります。
> - 内部ユーザー間でのメッセージの自動転送は、送信スパム フィルター ポリシーの設定の影響を受けられません。

## <a name="how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls"></a>送信スパム フィルター ポリシー設定が他の自動メール転送制御とどのように連携するか

管理者は、自動メール転送を許可またはブロックする他のコントロールを既に構成している可能性があります。 次に例を示します。

- [一](/exchange/mail-flow-best-practices/remote-domains/remote-domains) 部またはすべての外部ドメインへの自動メール転送を許可またはブロックするリモート ドメイン。
- 外部受信者に自動的に転送されたメッセージを検出してブロックする[Exchangeメール フロー](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) ルール (トランスポート ルールとも呼ばれます) の条件とアクション。

1 つの設定で外部転送が許可されているが、別の設定が外部転送をブロックする場合、通常はブロックが優先されます。 次の表に例を示します。

|シナリオ|結果|
|---|---|
|<ul><li>自動転送を許可するようにリモート ドメイン設定を構成します。</li><li>送信スパム フィルター ポリシーの自動転送は **[オフ]** に設定されています。</li></ul>|影響を受けるドメイン内の受信者に自動的に転送されたメッセージはブロックされます。|
|<ul><li>自動転送を許可するようにリモート ドメイン設定を構成します。</li><li>送信スパム フィルター ポリシーの自動転送は、[ **自動 - システム制御]** に設定されます。</li></ul>|影響を受けるドメイン内の受信者に自動的に転送されたメッセージはブロックされます。 <p> 前述のように、 **自動 - システム制御は** **On** を意味するために使用されましたが、設定は時間の経過と共に変更され、すべての組織で **オフ** を意味します。 <p> 明確にするために、送信スパム フィルター ポリシーを **[オン]** または **[オフ]** に構成する必要があります。|
|<ul><li>送信スパム フィルター ポリシーの自動転送が **[オン]** に設定されている</li><li>メール フロー ルールまたはリモート ドメインを使用して、自動的に転送された電子メールをブロックします。</li></ul>|影響を受ける受信者に自動的に転送されたメッセージは、メール フロー ルールまたはリモート ドメインによってブロックされます。|

この動作 (たとえば) を使用して、送信スパム フィルター ポリシーでの自動転送を許可できますが、リモート ドメインを使用して、ユーザーがメッセージを転送できる外部ドメインを制御できます。

## <a name="how-to-find-users-that-are-automatically-forwarding"></a>自動的に転送されるユーザーを検索する方法

メッセージを外部の受信者に自動的に転送するユーザーに関する情報は、クラウドベースのアカウントの [自動転送メッセージ レポート](/exchange/monitoring/mail-flow-reports/mfr-auto-forwarded-messages-report) で確認できます。 Microsoft 365を介してオンプレミスの電子メール システムから自動的に転送するオンプレミス ユーザーの場合は、これらのユーザーを追跡するメール フロー ルールを作成する必要があります。 メール フロー ルールを作成する方法については、「 [EAC を使用してメール フロー ルールを作成する](/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#use-the-eac-to-create-a-mail-flow-rule)」を参照してください。

Exchange管理センター (EAC) でメール フロー ルールを作成するには、次の情報が必要です。

- (条件): **メッセージ ヘッダー**\>が **これらのテキスト パターンと一致する場合は、****この規則を適用** します。 このオプションを表示するには、[ **その他のオプション** ] をクリックする必要がある場合があります。
  - **ヘッダー名**: `X-MS-Exchange-Inbox-Rules-Loop`
  - **ヘッダーの値**: `.`

  条件は次のようになります。 **'X-MS-Exchange-Inbox-Rules-Loop'** ヘッダーは **'.' と** 一致します。

  この条件は、ヘッダーの任意の値と一致します。

- (省略可能) **次の操作** (アクション): オプションのアクションを構成できます。 たとえば、メッセージ **プロパティ**\>を変更するアクションを使用して、ヘッダー名 **X-Forwarded** と値 True を使用して、メッセージ ヘッダーを **設定****できます**。 ただし、アクションを構成する必要はありません。
- **重大度レベルでこのrueを監査** する値を **[低**]、[**中]**、または **[高]** の値に設定します。 この設定を使用すると、[Exchange トランスポート ルール レポート](view-email-security-reports.md#exchange-transport-rule-report)を使用して、転送しているユーザーの詳細を取得できます。

:::image type="content" source="../../media/mail-flow-rule-for-forwarded-messages.png" alt-text="転送されたメッセージを識別するルールの EAC のメール フロー ルールプロパティ" lightbox="../../media/mail-flow-rule-for-forwarded-messages.png":::

## <a name="blocked-email-forwarding-messages"></a>ブロックされた電子メール転送メッセージ

メッセージが自動的に転送されると検出され、 [送信スパム フィルター](configure-the-outbound-spam-policy.md) ポリシーによってそのアクティビティが *ブロック* されると、メッセージは次の情報を含む NDR 内の送信者に返されます。

`5.7.520 Access denied, Your organization does not allow external forwarding. Please contact your administrator for further assistance. AS(7555)`
