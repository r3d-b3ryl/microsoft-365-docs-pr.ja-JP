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
description: 管理者は、Microsoft 365 でフィッシング メッセージを受け取った理由と方法、および今後より多くのフィッシング メッセージを防ぐために行う方法を特定できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 283abe4f7a62bf5d1c21e4ea480ca2889fcd474d
ms.sourcegitcommit: d09eb780dc41a01796eb8137fbe9267231af6746
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2022
ms.locfileid: "67385123"
---
# <a name="tune-anti-phishing-protection"></a>フィッシング対策保護を調整する

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Microsoft 365 には、既定で有効になっているさまざまなフィッシング対策機能が用意されていますが、一部のフィッシング メッセージがメールボックスに届く可能性があります。 このトピックでは、フィッシング メッセージが経由した理由と、 _誤って事態を悪化させずに_ Microsoft 365 組織のフィッシング対策設定を調整するために実行できる操作について説明します。

## <a name="first-things-first-deal-with-any-compromised-accounts-and-make-sure-you-block-any-more-phishing-messages-from-getting-through"></a>まず最初に、侵害されたアカウントに対処し、フィッシング メッセージの通過をブロックすることを確認します

フィッシング メッセージの結果として受信者のアカウントが侵害された場合は、「 [Microsoft 365 で侵害された電子メール アカウントに応答する」の手順に](responding-to-a-compromised-email-account.md)従います。

サブスクリプションにMicrosoft Defender for Office 365が含まれている場合は、[Office 365脅威インテリジェンス](office-365-ti.md)を使用して、フィッシング メッセージも受信した他のユーザーを特定できます。 フィッシング メッセージをブロックする追加のオプションがあります。

- [Microsoft Defender for Office 365 の安全なリンク](set-up-safe-links-policies.md)

- [Microsoft Defender for Office 365の安全な添付ファイル](set-up-safe-attachments-policies.md)

- [Microsoft Defender for Office 365のフィッシング対策ポリシー](configure-mdo-anti-phishing-policies.md)。 ポリシーの **高度なフィッシングのしきい値は** 、 **Standard** から **アグレッシブ**、 **より攻撃的**、または **最も攻撃** 的に一時的に増やすことができることに注意してください。

これらのDefender for Office 365機能が有効になっていることを確認します。

## <a name="report-the-phishing-message-to-microsoft"></a>フィッシング メッセージを Microsoft に報告する

フィッシング メッセージの報告は、Microsoft 365 のすべてのお客様を保護するために使用されるフィルターの調整に役立ちます。 手順については、「 [メッセージとファイルを Microsoft に報告する」を参照してください](report-junk-email-messages-to-microsoft.md)。

## <a name="inspect-the-message-headers"></a>メッセージ ヘッダーを調べる

フィッシング メッセージのヘッダーを調べて、より多くのフィッシング メッセージの受信を防ぐために自分でできることがあるかどうかを確認できます。 つまり、メッセージ ヘッダーを調べることは、フィッシング メッセージを許可する役割を担っていた組織内の設定を特定するのに役立ちます。

具体的には、メッセージ ヘッダーの **X-Forefront-Antispam-Report** ヘッダー フィールドで、スパム フィルター判定 (SFV) 値でスパムまたはフィッシングのフィルター処理がスキップされたことを示す情報を確認する必要があります。 フィルター処理をスキップするメッセージにはエントリ `SCL:-1`が含まれます。つまり、サービスによって決定されたスパムまたはフィッシングの判定をオーバーライドすることで、このメッセージを許可した設定の 1 つを意味します。 メッセージ ヘッダーと、使用可能なすべてのスパム対策およびフィッシング詐欺対策メッセージ ヘッダーの完全な一覧を取得する方法の詳細については、 [Microsoft 365 のスパム対策メッセージ ヘッダーに](anti-spam-message-headers.md)関するページを参照してください。

## <a name="best-practices-to-stay-protected"></a>保護を維持するためのベスト プラクティス

- 毎月、 [セキュリティ スコア](../defender/microsoft-secure-score.md) を実行して、組織のセキュリティ設定を評価します。

- 誤って検疫に入るメッセージ、または許可されているメッセージの場合は、 [脅威エクスプローラーとリアルタイムの検出](threat-explorer.md)でそれらのメッセージを検索することをお勧めします。 送信者、受信者、またはメッセージ ID で検索できます。 メッセージを見つけたら、件名をクリックして詳細に移動します。 検疫されたメッセージについては、適切な方法を使用してオーバーライドできるように、"検出テクノロジ" が何であったかを確認します。 許可されているメッセージについては、メッセージを許可したポリシーを確認します。

- スプーフィングされた送信者からのEmail (メッセージの送信元アドレスがメッセージのソースと一致しない) は、Defender for Office 365ではフィッシングとして分類されます。 スプーフィングが無害な場合もあれば、特定のスプーフィングされた送信者からのメッセージを検疫したくない場合もあります。 ユーザーへの影響を最小限に抑えるには、[スプーフィング インテリジェンスの分析情報](learn-about-spoof-intelligence.md)、[テナント許可/ブロック一覧](manage-tenant-allow-block-list.md)の **[スプーフィングされた送信者**] タブ、および [[スプーフィング検出] レポート](view-email-security-reports.md#spoof-detections-report)を定期的に確認します。 スプーフィングされた送信者の許可とブロックを確認し、必要なオーバーライドを行ったら、フィッシング [対策ポリシーでスプーフィング インテリジェンスを構成](set-up-anti-phishing-policies.md#spoof-settings)し、疑わしいメッセージをユーザーの迷惑Email フォルダーに配信するのではなく、疑わしいメッセージを **検疫** することができます。

- Microsoft Defender for Office 365で、偽装 (ドメインまたはユーザー) に対して上記の手順を繰り返すことができます。 偽装レポートは、 **脅威管理** \> **ダッシュボード** \> **Insights** の下にあります。

- [Threat Protection の状態レポート](view-reports-for-mdo.md#threat-protection-status-report)を定期的に確認します。

- 一部の顧客は、スパム対策ポリシーの [送信者の許可] または [ドメインの許可] ボックスの一覧に独自のドメインを配置することで、誤ってフィッシング メッセージを許可します。 この構成では一部の正当なメッセージが許可されますが、通常はスパムやフィッシング フィルターによってブロックされる悪意のあるメッセージも許可されます。 ドメインを許可する代わりに、基になる問題を修正する必要があります。

  ドメイン内の送信者を含む Microsoft 365 (偽陽性) によってブロックされる正当なメッセージを処理する最善の方法は、 _すべての_ 電子メール ドメインに対して DNS で SPF、DKIM、DMARC レコードを完全かつ完全に構成することです。

  - SPF レコードがドメイン内の送信者 _のすべての_ 電子メール ソースを識別することを確認します (サードパーティのサービスを忘れないでください)。

  - ハード フェール (\-すべて) を使用して、許可されていない送信者が、そのように構成された電子メール システムによって拒否されるようにします。 [スプーフィング インテリジェンス分析情報](learn-about-spoof-intelligence.md)を使用すると、ドメインを使用している送信者を識別し、承認されたサードパーティの送信者を SPF レコードに含めることができます。

  構成手順については、次を参照してください。

  - [SPF を設定して、スプーフィングを防止する](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

  - [DKIM を使用して、カスタム ドメインから送信される送信電子メールを検証する](use-dkim-to-validate-outbound-email.md)

  - [DMARC を使用してメールを検証する](use-dmarc-to-validate-email.md)

- 可能な限り、ドメインの電子メールを Microsoft 365 に直接配信することをお勧めします。 つまり、Microsoft 365 ドメインの MX レコードを Microsoft 365 にポイントします。 Exchange Online Protection (EOP) は、メールが Microsoft 365 に直接配信されるときに、クラウド ユーザーに最適な保護を提供できます。 EOP の前でサード パーティ製の電子メールの検疫システムを使用する必要がある場合は、コネクタの拡張フィルター処理を使用します。 手順については、「Exchange Onlineの[コネクタの拡張フィルター処理](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)」を参照してください。

- ユーザーは [、レポート メッセージ アドイン](enable-the-report-message-add-in.md) または [フィッシングレポート アドインを](enable-the-report-phish-add-in.md) 使用して Microsoft にメッセージを報告する必要があります。これにより、システムをトレーニングできます。 管理者は、[管理申請](admin-submission.md)機能も利用する必要があります。

- 多要素認証 (MFA) は、侵害されたアカウントを防ぐ優れた方法です。 すべてのユーザーに対して MFA を有効にすることを強くお検討ください。 段階的なアプローチでは、すべてのユーザーに対して MFA を有効にする前に、最も機密性の高いユーザー (管理者、エグゼクティブなど) に対して MFA を有効にすることから始めます。 手順については、「 [多要素認証を設定する](../../admin/security-and-compliance/set-up-multi-factor-authentication.md)」を参照してください。

- 外部受信者への転送ルールは、多くの場合、攻撃者がデータを抽出するために使用されます。 [Microsoft Secure Score](../defender/microsoft-secure-score.md) の **メールボックス転送ルールの確認** 情報を使用して、外部受信者への転送ルールを見つけて防止します。 詳細については、「 [セキュリティで保護されたスコアを使用したクライアント外部転送ルールの軽減](/archive/blogs/office365security/mitigating-client-external-forwarding-rules-with-secure-score)」を参照してください。
