---
title: フィッシング対策保護を調整する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.localizationpriority: medium
search.appverid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
- MET150
description: 管理者は、Microsoft 365 でフィッシング メッセージが通過した理由と方法、および今後のフィッシング メッセージを防ぐための対策について学習できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 299488a7ed8a891d870efb3ace618178c36552f1
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60206471"
---
# <a name="tune-anti-phishing-protection"></a>フィッシング対策保護を調整する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

既定Microsoft 365さまざまなフィッシング対策機能が付属しますが、一部のフィッシング メッセージが引き続きメールボックスに送信される可能性があります。 このトピックでは、フィッシング メッセージが通過した理由と、誤って事態を悪化させずに Microsoft 365 組織のフィッシング対策設定を調整するために実行できる操作について説明します。

## <a name="first-things-first-deal-with-any-compromised-accounts-and-make-sure-you-block-any-more-phishing-messages-from-getting-through"></a>まず、侵害されたアカウントに対処し、フィッシング メッセージの受信をブロックする

フィッシング メッセージの結果として受信者のアカウントが侵害された場合は、「セキュリティで保護されたメール アカウントに応答する」の手順に[従](responding-to-a-compromised-email-account.md)Microsoft 365。

サブスクリプションに Microsoft Defender for Office 365が含まれる場合は[](office-365-ti.md)、Office 365脅威インテリジェンスを使用して、フィッシング メッセージも受信した他のユーザーを特定できます。 フィッシング メッセージをブロックする追加のオプションがあります。

- [セーフMicrosoft Defender for Office 365](set-up-safe-links-policies.md)

- [セーフMicrosoft Defender の添付ファイル (Office 365](set-up-safe-attachments-policies.md)

- [Microsoft Defender のフィッシング対策ポリシーを](configure-mdo-anti-phishing-policies.md)Office 365。 ポリシーの [高度なフィッシングのしきい値] を一時的に [**標準**]から [アグレッシブ] 、[攻撃的] 、または [最も攻撃的] に **増やします**。

これらの Defender が有効になっているOffice 365確認します。

## <a name="report-the-phishing-message-to-microsoft"></a>フィッシング メッセージを Microsoft に報告する

フィッシング メッセージの報告は、すべてのユーザーを保護するために使用されるフィルターの調整に役立Microsoft 365。 手順については、「メッセージと [ファイルを Microsoft に報告する」を参照してください](report-junk-email-messages-to-microsoft.md)。

## <a name="inspect-the-message-headers"></a>メッセージ ヘッダーの検査

フィッシング メッセージのヘッダーを調べて、フィッシング メッセージの受け取りを防ぐために、自分で実行できる操作が何かあるかを確認できます。 つまり、メッセージ ヘッダーを調べることは、フィッシング メッセージを許可する組織の設定を特定するのに役立ちます。

具体的には、メッセージ ヘッダーの **X-Forefront-Antispam-Report** ヘッダー フィールドで、スパムまたはフィッシングに対するスキップされたフィルター処理がスパム フィルター (SFV) 値で示されているのを確認する必要があります。 フィルター処理をスキップするメッセージには、サービスによって決定されたスパムまたはフィッシングの判定を上書きして、このメッセージを許可した設定の 1 つが含 `SCL:-1` まれます。 メッセージ ヘッダーを取得する方法と、使用可能なすべてのスパム対策およびフィッシング対策メッセージ ヘッダーの完全な一覧の詳細については、「Microsoft 365 のスパム対策メッセージ ヘッダー」を[参照してください](anti-spam-message-headers.md)。

## <a name="best-practices-to-stay-protected"></a>保護された環境を保護するためのベスト プラクティス

- 毎月、Secure Score を実行 [して](../defender/microsoft-secure-score.md) 組織のセキュリティ設定を評価します。

- 誤って検疫に終わるメッセージ、または許可されているメッセージの場合は、Threat Explorer でそれらのメッセージを検索し、リアルタイム検出することをお [勧めします](threat-explorer.md)。 送信者、受信者、またはメッセージ ID で検索できます。 メッセージを見つけると、件名をクリックして詳細に移動します。 検疫済みメッセージの場合は、適切なメソッドを使用して上書きできるよう、「検出テクノロジ」が何だったかを確認します。 許可されているメッセージについては、メッセージを許可したポリシーを確認します。

- スプーフィングされた送信者からのメール (メッセージの差出人アドレスがメッセージの送信元と一致しない) は、Defender for Office 365 でフィッシングとして分類されます。 スプーフィングは良性であり、ユーザーが特定のスプーフィングされた送信者からのメッセージを検疫したくない場合があります。 ユーザーへの影響を最小限に抑えるために、スプー[](learn-about-spoof-intelligence.md)フィング インテリジェンスの分析情報、テナント許可[/](tenant-allow-block-list.md)ブロック 一覧の [スプーフィング] タブ、および [スプーフィング検出] レポートを定期的に[確認します](view-email-security-reports.md#spoof-detections-report)。 スプーフィングされた送信者の許可とブロックを確認し、必要な上書きを行った後は、ユーザーの[](set-up-anti-phishing-policies.md#spoof-settings)迷惑メール フォルダーに配信するのではなく、疑わしいメッセージを検疫するフィッシング対策ポリシーでスプーフィング インテリジェンスを構成できます。

- Microsoft Defender の偽装 (ドメインまたはユーザー) の場合は、上記の手順を繰り返Office 365。 偽装レポートは、[脅威 **管理ダッシュボード]** の下 \>  \> インサイト。

- 脅威保護の状態 [レポートを定期的に確認します](view-reports-for-mdo.md#threat-protection-status-report)。

- 一部の顧客は、スパム対策ポリシーの [送信者の許可] または [ドメインの許可] リストに独自のドメインを入れて、フィッシング メッセージを誤って許可します。 この構成では、一部の正当なメッセージを通過することができますが、通常はスパムやフィッシング フィルターによってブロックされる悪意のあるメッセージも許可されます。 ドメインを許可する代わりに、基になる問題を修正する必要があります。

  ドメイン内の送信者を含む Microsoft 365 (誤検知) によってブロックされる正当なメッセージに対処する最善の方法は、すべての電子メール ドメインの SPF、DKIM、および DMARC レコードを DNSで完全かつ完全に構成する方法です。

  - SPF レコードがドメイン内の送信者のすべての電子メール ソースを識別することを確認します (サード パーティのサービスを忘れないでください)。

  - ハード フェール (すべて) を使用して、未承認の送信者が拒否される電子メール システムによって拒否 \- されていることを確認します。 スプーフィング [インテリジェンスの](learn-about-spoof-intelligence.md) 分析情報を使用して、ドメインを使用している送信者を識別し、承認されたサード パーティの送信者を SPF レコードに含めることができます。

  構成手順については、以下を参照してください。

  - [SPF を設定して、スプーフィングを防止する](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

  - [DKIM を使用して、カスタム ドメインから送信される送信電子メールを検証する](use-dkim-to-validate-outbound-email.md)

  - [DMARC を使用してメールを検証する](use-dmarc-to-validate-email.md)

- 可能な限り、ドメインのメールをドメインに直接配信することをお勧Microsoft 365。 つまり、ドメインの MX レコードMicrosoft 365、ドメインの MX レコードを指定Microsoft 365。 Exchange Online Protection (EOP) は、クラウド ユーザーのメールが直接メールに配信される際に、クラウド ユーザーに最適な保護をMicrosoft 365。 EOP の前でサード パーティ製の電子メールの衛生システムを使用する必要がある場合は、コネクタの拡張フィルターを使用します。 手順については、「拡張フィルタリング[for Connectors in Exchange Online」 を参照してください](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)。

- ユーザーは、Microsoft に[メッセージ](enable-the-report-message-add-in.md)を報告するために、[](enable-the-report-phish-add-in.md)レポート メッセージ アドインまたはレポート フィッシング アドインを使用する必要があります。システムをトレーニングできます。 管理者は、管理者申請機能 [も](admin-submission.md) 利用する必要があります。

- 多要素認証 (MFA) は、侵害されたアカウントを防ぐ良い方法です。 すべてのユーザーに対して MFA を有効に強く検討する必要があります。 段階的なアプローチでは、最も機密性の高いユーザー (管理者、役員など) に対して MFA を有効にしてから、すべてのユーザーに MFA を有効にします。 手順については、「多要素認証のセットアップ [」を参照してください](../../admin/security-and-compliance/set-up-multi-factor-authentication.md)。

- 外部受信者へのルールの転送は、多くの場合、攻撃者がデータを抽出するために使用されます。 [Microsoft Secure Score](../defender/microsoft-secure-score.md) **の [メールボックス転送ルール** の確認] 情報を使用して、外部受信者へのルールの転送を見つけて防止します。 詳細については、「Secure [Score を使用したクライアント外部転送ルールの緩和」を参照してください](/archive/blogs/office365security/mitigating-client-external-forwarding-rules-with-secure-score)。
