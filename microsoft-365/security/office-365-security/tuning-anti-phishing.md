---
title: フィッシング対策保護の調整
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
description: 管理者は、フィッシングメッセージが Microsoft 365 でどのように表示されるのか、および今後のフィッシングメッセージを回避するために何を行う必要があるかを特定する方法について説明します。
ms.openlocfilehash: ac416da714e30491f679e22909010a8c02fac843
ms.sourcegitcommit: 2acd9ec5e9d150389975e854c7883efc186a9432
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755054"
---
# <a name="tune-anti-phishing-protection"></a>フィッシング対策保護の調整

Microsoft 365 には、既定で有効になっているさまざまなフィッシング対策機能が付属していますが、一部のフィッシングメッセージは依然としてメールボックスに到達する可能性があります。 このトピックでは、フィッシングメッセージが通過した理由を検出するために実行できることと、誤って深刻な事態を発生さ_せず_に Microsoft 365 組織のフィッシング対策設定を調整する方法について説明します。

## <a name="first-things-first-deal-with-any-compromised-accounts-and-make-sure-you-block-any-more-phishing-messages-from-getting-through"></a>最初に、侵害されたアカウントを処理して、より多くのフィッシングメッセージを取得することを禁止していることを確認してください。

フィッシングメッセージの結果として受信者のアカウントが侵害された場合は、「 [Microsoft 365 で侵害された電子メールアカウントに応答する](responding-to-a-compromised-email-account.md)」の手順を実行します。

サブスクリプションに Advanced Threat Protection (ATP) が含まれている場合は、 [Office 365 脅威インテリジェンス](office-365-ti.md)を使用して、フィッシングメッセージを受信した他のユーザーを識別できます。 フィッシングメッセージをブロックするための追加のオプションがあります。

- [ATP の安全なリンク](set-up-atp-safe-links-policies.md)

- [ATP の安全な添付ファイル機能](set-up-atp-safe-attachments-policies.md)

- [Microsoft 365 の ATP のフィッシング対策ポリシー](configure-atp-anti-phishing-policies.md)。 ポリシーの**高度なフィッシングしきい値**は、**標準**から**アグレッシブ** **、アグレッシブ**、または**最も積極的**なものに一時的に増やすことができます。

これらの ATP 機能が有効になっていることを確認します。

## <a name="report-the-phishing-message-to-microsoft"></a>フィッシングメッセージを Microsoft に報告する

フィッシングメッセージの報告は、Microsoft 365 のすべてのお客様を保護するために使用されるフィルターを調整するのに役立ちます。 手順については、「 [Microsoft にメッセージとファイルを報告する](report-junk-email-messages-to-microsoft.md)」を参照してください。

## <a name="inspect-the-message-headers"></a>メッセージヘッダーを検査する

フィッシングメッセージのヘッダーを調べて、より多くのフィッシングメッセージが送られないようにすることができるかどうかを確認できます。 言い換えると、メッセージヘッダーを調べると、でフィッシングメッセージを許可する責任がある、組織内のすべての設定を識別するのに役立ちます。

具体的には、メッセージヘッダーの**スパム対策**ヘッダーフィールドを調べて、スパムフィルター Verdict (sfv) の値で、スキップされたスパムまたはフィッシングのフィルター処理が表示されることを確認する必要があります。 フィルター処理をスキップするメッセージには、のエントリがあり `SCL:-1` ます。これは、サービスによって決定されたスパムまたはフィッシング verdicts を上書きすることによって、このメッセージが許可される設定の1つになります。 メッセージヘッダーおよび使用可能なすべてのスパム対策およびフィッシングメッセージヘッダーの完全な一覧を取得する方法の詳細については、「 [Microsoft 365 のスパム対策メッセージヘッダー](anti-spam-message-headers.md)」を参照してください。

## <a name="best-practices-to-stay-protected"></a>保護を維持するためのベストプラクティス

- 組織のセキュリティ設定を評価するために、月単位で、[セキュリティで保護されたスコア](../mtp/microsoft-secure-score.md)を実行します。

- 誤って検疫されたメッセージ、またはから許可されたメッセージについては、[脅威エクスプローラおよびリアルタイム検出](threat-explorer.md)でこれらのメッセージを検索することをお勧めします。 送信者、受信者、またはメッセージ ID で検索できます。 メッセージが見つかったら、件名をクリックして [詳細] に移動します。 検疫済みメッセージの場合は、適切な方法で上書きするために、"検出テクノロジ" がどのようなものかを確認します。 許可されたメッセージについては、メッセージを許可するポリシーを確認してください。 

- スプーフィングされたメールには、ATP でフィッシングというタグが付きます。 場合によっては、スプーフィングに害がなく、ユーザーが検疫を望まないことがあります。 ユーザーへの影響を最小限に抑えるために、[スプーフィングインテリジェンスレポート](learn-about-spoof-intelligence.md)を定期的に確認してください。 必要な上書きを確認して必要な場合は、ユーザーの迷惑メールフォルダーに配信するのではなく、疑わしいメッセージを**検疫**するように[スプーフィングインテリジェンスを構成](set-up-anti-phishing-policies.md#spoof-settings)することができます。

- 偽装 (ドメインまたはユーザー) に対して上記の手順を繰り返すことができます。 偽装レポートは、[**脅威管理**] \> **ダッシュボード**Insights の下にあり \> **Insights**ます。

- [脅威保護状態レポート](view-reports-for-atp.md#threat-protection-status-report)を定期的に確認します。

- ユーザーによっては、スパム対策ポリシーの [送信者を許可する] または [ドメインを許可する] の一覧に独自のドメインを設定することで、フィッシングメッセージを誤って許可することがあります。 この構成では、一部の正当なメッセージが許可されますが、通常はスパムやフィッシングフィルターによってブロックされる悪意のあるメッセージも許可されます。 ドメインを許可する代わりに、根底にある問題を修正する必要があります。

  ドメイン内の送信者に365よってブロックされる正当なメッセージを処理するための最善の方法は、_すべて_の電子メールドメインについて、DNS の SPF、dkim、および DMARC レコードを完全に完全に構成することです。

  - SPF レコードが、ドメイン内の送信者の電子メールの_すべて_のソースを識別していることを確認します (サードパーティのサービスを忘れないでください)。

  - ハードフェールオーバー ( \- すべて) を使用して、承認されていない送信者が電子メールシステムによって拒否されるようにします。 [スプーフィングインテリジェンス](learn-about-spoof-intelligence.md)を使用すると、ドメインを使用している送信者を特定し、SPF レコードに承認されたサードパーティの送信者を含めることができます。

  構成手順については、以下を参照してください。
  
  - [SPF を設定して、スプーフィングを防止する](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

  - [DKIM を使用して、カスタム ドメインから送信される送信電子メールを検証する](use-dkim-to-validate-outbound-email.md)

  - [DMARC を使用してメールを検証する](use-dmarc-to-validate-email.md)

- 可能な限り、自分のドメインのメールを Microsoft 365 に直接配信することをお勧めします。 つまり、Microsoft 365 ドメインの MX レコードを Microsoft 365 に指定します。 Exchange Online Protection (EOP) は、メールが Microsoft 365 に直接配信される場合に、クラウドユーザーに最高の保護を提供することができます。 EOP の前にサードパーティの電子メールの検疫システムを使用する必要がある場合は、コネクタの拡張フィルターを使用します。 手順については、「 [Exchange Online のコネクタの拡張フィルター処理](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)」を参照してください。

- ユーザーが[メッセージ](enable-the-report-message-add-in.md)を Microsoft に報告して、システムをトレーニングできるようにする必要があります。 管理者は、[管理者送信](admin-submission.md)機能も利用する必要があります。

- 侵害されたアカウントを防止するには、多要素認証 (MFA) をお勧めします。 すべてのユーザーに対して MFA を有効にすることを強くお勧めします。 段階的なアプローチの場合は、すべてのユーザーに対して MFA を有効にする前に、最も機密性の高いユーザー (管理者、役員など) に対して MFA を有効にすることから始めます。 手順については、「[多要素認証をセットアップ](../../admin/security-and-compliance/set-up-multi-factor-authentication.md)する」を参照してください。

- 外部の受信者へのルールの転送は、多くの場合、攻撃者がデータを抽出するために使用します。 「 [Microsoft セキュリティスコア](../mtp/microsoft-secure-score.md)」の「**メールボックス転送ルールを確認**する」を使用して、外部の受信者に対する転送ルールを見つけて、それを防止します。 詳細については、「[セキュリティで保護されたスコアでクライアントの外部転送ルールを軽減](https://docs.microsoft.com/archive/blogs/office365security/mitigating-client-external-forwarding-rules-with-secure-score)する」を参照してください。
