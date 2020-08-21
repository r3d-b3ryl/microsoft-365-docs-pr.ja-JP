---
title: フィッシング対策保護の調整
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
description: 管理者は、フィッシング メッセージが Microsoft 365 でやり取りされる理由とその方法、今後フィッシング メッセージを防ぐ方法を学習できます。
ms.openlocfilehash: b0fbb29489cece6d708811c5c8d8d60450938f0c
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825211"
---
# <a name="tune-anti-phishing-protection"></a>フィッシング対策保護の調整

Microsoft 365 には既定で有効になっているさまざまなフィッシング対策機能が用いられるものの、一部のフィッシング メッセージがまだメールボックスにアクセスされる可能性があります。 このトピックでは、フィッシング メッセージが通通る理由を確認する方法と、間を考慮せずに Microsoft 365 組織でフィッシング対策の設定を調整するためにできること _について説明します_。

## <a name="first-things-first-deal-with-any-compromised-accounts-and-make-sure-you-block-any-more-phishing-messages-from-getting-through"></a>最初に、侵害されたアカウントを処理し、フィッシング メッセージが取得されるのをすべてブロックします。

フィッシング メッセージの結果として受信者のアカウントが侵害された場合は、侵害された Microsoft 365 電子メール アカウントに対する [対応手順を実行します](responding-to-a-compromised-email-account.md)。

サブスクリプションに Advanced Threat Protection (ATP) が含まれている場合 [、Office 365 脅威インテリジェンスを使用してフィッ](office-365-ti.md) シングのメッセージを受け取った他のユーザーを特定できます。 フィッシング メッセージをブロックする追加オプションがあります。

- [ATP の安全なリンク](set-up-atp-safe-links-policies.md)

- [ATP の安全な添付ファイル機能](set-up-atp-safe-attachments-policies.md)

- [Microsoft 365 の ATP フィッシング対策ポリシー](configure-atp-anti-phishing-policies.md)。 ポリシーの高度なフィッシング**し**きい値を**Standard**から**Aggressive、Aggressive、** または Most が要求中のものに**増やすことができる点に注意してください**。 **More aggressive**

これらの ATP 機能が有効になっていることを確認します。

## <a name="report-the-phishing-message-to-microsoft"></a>フィッシング メッセージを Microsoft に報告する

フィッシング メッセージの報告は、Microsoft 365 のすべての顧客を保護するために使用されるフィルターのチューニングに役立ちます。 手順については、「メッセージと [ファイルを Microsoft に報告する」を参照してください](report-junk-email-messages-to-microsoft.md)。

## <a name="inspect-the-message-headers"></a>メッセージ ヘッダーを検かする

フィッシング メッセージのヘッダーを調べ、フィッシング メッセージがより多くならないようにします。 つまり、メッセージ ヘッダーを調べながら、フィッシング メッセージの許可を行った組織内の設定を特定することができます。

具体的には、メッセージ ヘッダー **の X-Forefront-Antispam-Report** ヘッダー フィールドで、Spam Filtering Verdict (SFV) 値のスキップされたスパムまたはフィッシング フィルター処理のインピクションを確認する必要があります。 フィルター処理をスキップするメッセージには、エントリが含まれます。これは、サービスで判別されたスパムまたはフィッシング判フの判別をオーバーライドしてこのメッセージが `SCL:-1` 許可された設定のいずれかのエントリを意味します。 メッセージ ヘッダーを取得する方法と、利用可能なすべてのスパム対策およびフィッシング メッセージ ヘッダーの完全なリストについては [、Microsoft 365 のスパム対策メッセージ ヘッダーを参照してください](anti-spam-message-headers.md)。

## <a name="best-practices-to-stay-protected"></a>保護された情報を取得するためのベスト プラクティス

- 毎月、セキュア [スコアを実行](../mtp/microsoft-secure-score.md) して組織のセキュリティ設定を評価します。

- 間で検疫で終わったメッセージや、許可されたメッセージに対しては、それらのメッセージを脅威エクスプローラーおよびリアル [タイムの検出で検索する必要があります](threat-explorer.md)。 送信者、受信者、メッセージ ID で検索できます。 メッセージを見つけ、件名をクリックして詳細に移動します。 検疫されたメッセージの場合は、適切な方法を上書きできるように、"検出テクノロジ" が何か確認できるかどうかを確認します。 許可されたメッセージについては、メッセージが許可されたポリシーを確認します。 

- スプーフィングされたメールには、ATP でフィッシングとしてタグ付けされます。 スプーフィングのベンダイトペーンを使用し、検疫を行う必要のない場合があります。 ユーザーへの影響を最小限に抑えるには、スプーフィング インテリジェンス [レポートを定期的に確認してください](learn-about-spoof-intelligence.md)。 必要なオーバーライドを確認して作成すると、ユーザーの [迷惑メール] フォルダーに[configure spoof intelligence](set-up-anti-phishing-policies.md#spoof-settings)偽のインテリジェンスを配信する代わりに、**検**疫に対するスプーフィング インテリジェンスを構成できます。

- 偽装 (ドメインまたはユーザー) については、上記の手順を繰り返します。 偽装レポートは、脅威 **管理** \> **ダッシュボードの** \> **インサイトの下に表示されます**。

- 脅威保護状態レポート [を定期的に確認します](view-reports-for-atp.md#threat-protection-status-report)。

- 一部の顧客は、自分のドメインをスパム対策ポリシーの [送信者の許可] または [ドメインのリストを許可] に含め、フィッシング メッセージを間接的に許可していません。 この構成では、正当なメッセージの一部が許可されますが、通常はスパム フィルターやフィッシング フィルターによってブロックされる悪意のあるメッセージも許可されます。 ドメインを許可する代わりに、基になる問題を修正する必要があります。

  ドメイン内の送信者を含む Microsoft 365 によってブロックされる正当なメッセージ (誤検知) を処理する最善の方法は、すべてのメール ドメイン用に DNS の SPF、DKIM、および DMARC レコードを _完全に構成_ することで、次の方法です。

  - SPF レコードが、ドメイン内 _の送信者の_ メールの送信元をすべて識別します (第サード パーティ サービスを使いつなけないでください)。

  - ハード障害を使用して、承認されていない送信者が、承認されていない送信者が、そのように構成された電子メール システム \- によって確実に拒否されていることを確認します。 スプー [フィング インテリジェンス](learn-about-spoof-intelligence.md) を使用して、ドメインを使用している送信者を識別し、サード パーティの許可されたサード パーティの送信者を SPF レコードに含めることができるようにすることができます。

  構成の手順については、以下を参照してください。
  
  - [SPF を設定して、スプーフィングを防止する](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

  - [DKIM を使用して、カスタム ドメインから送信される送信電子メールを検証する](use-dkim-to-validate-outbound-email.md)

  - [DMARC を使用してメールを検証する](use-dmarc-to-validate-email.md)

- ドメインのメールを可能な限り Microsoft 365 に直接配信配信しておくことをお勧めします。 つまり、Microsoft 365 ドメインの MX レコードで Microsoft 365 をポイントします。 Exchange Online Protection (EOP) は、メールが Microsoft 365 に直接配信される場合に、クラウド ユーザーに対して最高の保護機能を提供することができます。 EOP の前にサード パーティの電子メール ハイジェンシング システムを使用する必要がある場合は、コネクタの拡張フィルターを使用してください。 手順については [、「Exchange Online のコネクタ用の拡張フィルター処理」を参照してください](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)。

- ユーザーは [、システムをト](enable-the-report-message-add-in.md) レーニングできる Microsoft に報告する必要があります。 管理者も管理の申請機能 [を活用する必要](admin-submission.md) があります。

- 多要素認証 (MFA) は、アカウントの侵害を防ぐための優れた方法です。 すべてのユーザーに対して MFA を有効にするかどうかを強く検討する必要があります。 段階的なアプローチの場合は、すべてのユーザーに対して MFA を有効にする前に、最も機密性の高いユーザー (管理者、経営幹部など) の MFA を有効にしてから開始します。 手順については、「多要素 [認証のセットアップ」をご覧ください](../../admin/security-and-compliance/set-up-multi-factor-authentication.md)。

- 外部受信者への転送ルールは、多くの場合、攻撃者がデータを抽出するために使用します。 Microsoft セキ **ュア スコアのメールボックス転送** ルール [情報を確認して、](../mtp/microsoft-secure-score.md) 外部の受信者への転送ルールを検索して実行しないようにします。 詳細については、「セキ [ュア スコアを使用してクライアント外部転送ルールを軽減する」を参照してください](https://docs.microsoft.com/archive/blogs/office365security/mitigating-client-external-forwarding-rules-with-secure-score)。
