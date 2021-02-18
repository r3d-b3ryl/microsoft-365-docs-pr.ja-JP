---
title: フィッシング対策保護を調整する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
- MET150
description: 管理者は、フィッシング メッセージが Microsoft 365 で受信した理由と方法、および今後さらに多くのフィッシング メッセージを防ぐために何を行うのかを確認できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d3abbafce36c589f60eb164fb29c714c980f8b98
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286491"
---
# <a name="tune-anti-phishing-protection"></a>フィッシング対策保護を調整する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Microsoft 365 には、既定で有効になっているさまざまなフィッシング対策機能が付属しますが、一部のフィッシング メッセージがメールボックスに引き続き送信される可能性があります。 このトピックでは、フィッシング メッセージが通過した理由を見つめ、誤って事態を悪化させずに Microsoft 365 組織のフィッシング対策設定を調整する方法について説明 _します。_

## <a name="first-things-first-deal-with-any-compromised-accounts-and-make-sure-you-block-any-more-phishing-messages-from-getting-through"></a>まず、侵害されたアカウントを処理し、それ以上のフィッシング メッセージの受信をブロックする

フィッシング メッセージの結果として受信者のアカウントが侵害された場合は [、「Microsoft 365](responding-to-a-compromised-email-account.md)で侵害されたメール アカウントに対応する」の手順に従います。

サブスクリプションに Office 365 用の Microsoft Defender が含まれる場合は、Office [365](office-365-ti.md) 脅威インテリジェンスを使用して、フィッシング メッセージも受信した他のユーザーを特定できます。 フィッシング メッセージをブロックする追加のオプションがあります。

- [Microsoft Defender for Office 365 の安全なリンク](set-up-atp-safe-links-policies.md)

- [Microsoft Defender for Office 365 の安全な添付ファイル](set-up-atp-safe-attachments-policies.md)

- [Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md)のフィッシング対策ポリシー。 ポリシーの [高度なフィッシングのしきい値] を [**標準**]から[積極的]、[より積極的]、**または**[最も積極的] に一時的に **増やします**。

これらの Defender で 365 Officeが有効になっていることを確認します。

## <a name="report-the-phishing-message-to-microsoft"></a>フィッシング メッセージを Microsoft に報告する

フィッシング メッセージの報告は、Microsoft 365 のすべての顧客を保護するために使用されるフィルターの調整に役立ちます。 手順については、「メッセージとファイル [を Microsoft に報告する」を参照してください](report-junk-email-messages-to-microsoft.md)。

## <a name="inspect-the-message-headers"></a>メッセージ ヘッダーを検査する

フィッシング メッセージのヘッダーを調べて、より多くのフィッシング メッセージが受信されるのを防ぐために自分で行える操作が存在しないかを確認できます。 つまり、メッセージ ヘッダーを調べることで、組織内でフィッシング メッセージの許可を担当していた設定を特定するのに役立ちます。

具体的には、メッセージ ヘッダーの **X-Forefront-Antispam-Report** ヘッダー フィールドで、SFV (Spam Filtering Verdict) 値でスパムまたはフィッシングのフィルター処理がスキップされた可能性を確認する必要があります。 フィルター処理をスキップするメッセージにはエントリが含まれます。つまり、サービスによって決定されたスパムまたはフィッシングの判定を上書きして、このメッセージを許可した設定の 1 つを `SCL:-1` 意味します。 メッセージ ヘッダーを取得する方法と、使用可能なすべてのスパム対策およびフィッシング対策メッセージ ヘッダーの完全な一覧の詳細については [、Microsoft 365](anti-spam-message-headers.md)のスパム対策メッセージ ヘッダーを参照してください。

## <a name="best-practices-to-stay-protected"></a>保護を守るベスト プラクティス

- 毎月、セキュリティ スコア [を実行して](../mtp/microsoft-secure-score.md) 組織のセキュリティ設定を評価します。

- 誤って検疫されるメッセージ、または許可されているメッセージについては、脅威エクスプローラーでそれらのメッセージを検索し、リアルタイムで検出することをお [勧めします](threat-explorer.md)。 送信者、受信者、またはメッセージ ID で検索できます。 メッセージを見つけ、件名をクリックして詳細に移動します。 検疫済みメッセージの場合は、適切な方法を使用して上書きできるよう、"検出テクノロジ" が何かを確認します。 許可されたメッセージについては、メッセージを許可したポリシーを確認します。

- スプーフィングされたメールは、Defender でフィッシングとしてタグ付けされ、365 Officeされます。 スプーフィングが良性である場合や、ユーザーが検疫したくない場合があります。 ユーザーへの影響を最小限に抑えるために、スプーフィング インテリジェンス レポート [を定期的に確認してください](learn-about-spoof-intelligence.md)。 確認して必要なオーバーライドを行った後は、疑わしいメッセージをユーザーの[](set-up-anti-phishing-policies.md#spoof-settings)迷惑メール フォルダーに配信するのではなく、疑わしいメッセージを検疫するスプーフィング インテリジェンスを構成できます。

- 偽装 (ドメインまたはユーザー) に対して上記の手順を繰り返します。 偽装レポートは、脅威管理ダッシュボード **の分析** \> **情報** \> **の下に表示されます**。

- 脅威保護の状態 [レポートを定期的に確認します](view-reports-for-atp.md#threat-protection-status-report)。

- 一部のユーザーは、スパム対策ポリシーの [送信者の許可] または [ドメインの許可] の一覧に自分のドメインを入れて、フィッシング メッセージを誤って許可します。 この構成では一部の正当なメッセージが許可されます。ただし、通常はスパムフィルターやフィッシング フィルターによってブロックされる悪意のあるメッセージも許可されます。 ドメインを許可する代わりに、根底にある問題を修正する必要があります。

  ドメイン内の送信者が関与する Microsoft 365 (誤検知) によってブロックされる正当なメッセージを処理する最善の方法は、すべての電子メール ドメインに対して DNS の SPF、DKIM、および DMARC レコードを完全かつ完全に構成する方法です。 

  - SPF レコードが、ドメイン内の送信者のすべてのメールソースを識別することを確認します (サード パーティ製のサービスを忘れないでください)。

  - ハード フェール (すべて) を使用して、許可されていない送信者が、許可するように構成された電子メール システム \- によって拒否されていることを確認します。 スプーフィング [インテリジェンスを](learn-about-spoof-intelligence.md) 使用すると、ドメインを使用している送信者を識別し、許可されたサード パーティの送信者を SPF レコードに含めることができます。

  構成手順については、以下を参照してください。

  - [SPF を設定して、スプーフィングを防止する](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

  - [DKIM を使用して、カスタム ドメインから送信される送信電子メールを検証する](use-dkim-to-validate-outbound-email.md)

  - [DMARC を使用してメールを検証する](use-dmarc-to-validate-email.md)

- 可能な限り、ドメインのメールを Microsoft 365 に直接配信することをお勧めします。 つまり、Microsoft 365 ドメインの MX レコードを Microsoft 365 にポイントします。 Exchange Online Protection (EOP) は、メールが Microsoft 365 に直接配信される場合に、クラウド ユーザーに最適な保護を提供できます。 EOP の前にサードパーティの電子メールの検査システムを使用する必要がある場合は、コネクタの拡張フィルタリングを使用します。 手順については [、「Exchange Online のコネクタの拡張フィルター処理」を参照してください](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)。

- ユーザーは、メッセージの報告 [アドイン](enable-the-report-message-add-in.md) または [フィッシング](enable-the-report-phish-add-in.md) 報告アドインを使用してメッセージを Microsoft に報告し、システムをトレーニングする必要があります。 管理者は、管理者の提出機能 [も利用](admin-submission.md) する必要があります。

- 多要素認証 (MFA) は、アカウントが侵害されるのを防ぐ良い方法です。 すべてのユーザーに対して MFA を有効に強く検討する必要があります。 段階的なアプローチでは、まず最も機密性の高いユーザー (管理者、役員など) の MFA を有効にしてから、すべてのユーザーに対して MFA を有効にします。 手順については、「多要素認証 [をセットアップする」を参照してください](../../admin/security-and-compliance/set-up-multi-factor-authentication.md)。

- 外部受信者への転送ルールは、攻撃者がデータを抽出するためによく使用されます。 [Microsoft](../mtp/microsoft-secure-score.md)セキュア **スコアのメールボックス転送ルール** 情報の確認を使用して、外部受信者への転送ルールを検索して防止します。 詳細については、「セキュア スコア [によるクライアント外部転送ルールの軽減」を参照してください](https://docs.microsoft.com/archive/blogs/office365security/mitigating-client-external-forwarding-rules-with-secure-score)。
