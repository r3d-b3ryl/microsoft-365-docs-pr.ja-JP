---
title: EOP の一般的な FAQ
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
localization_priority: Normal
ms.assetid: 9dbff00a-474e-4452-aeb5-5be9a6b8c6d5
ms.custom:
- seo-marvel-apr2020
description: Exchange Online Protection (EOP) クラウドホスト型メール フィルター サービスに関する最も一般的な質問に対する回答を取得します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 04246b7c0a241c672328febd1584a56aa11becf2
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206800"
---
# <a name="eop-general-faq"></a>EOP の一般的な FAQ

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
-  [Exchange Online Protection スタンドアロン](exchange-online-protection-overview.md)

ここでは、Exchange Online Protection (EOP) クラウドホスト型メール フィルター サービスに関する最も一般的な質問に答えます。 その他のよく寄せられる質問 (FAQ) については、以下のリンクを参照してください。

- [EOP のキューイング、保留、返送されるメッセージに関する FAQ](eop-queued-deferred-and-bounced-messages-faq.md)

- [代理管理に関する FAQ](delegated-administration-faq.md)

- [スパム対策保護に関してよく寄せられる質問](anti-spam-protection-faq.md)

- [検疫に関する FAQ](quarantine-faq.md)

- [マルウェア対策保護のよく寄せられる質問](anti-malware-protection-faq-eop.md)

- [メッセージ追跡の FAQ](/exchange/monitoring/trace-an-email-message/message-trace-faq)

## <a name="what-is-eop"></a>EOP とは何ですか?

EOP とは、クラウド ホスト型の電子メール フィルター サービスで、ユーザーをスパムやマルウェアから保護し、カスタム ポリシー ルールを適用するために構築されます。 EOP は、Exchange Online メールボックスを含む Microsoft 365 サブスクリプションに含まれています。 EOP は、オンプレミスの電子メール環境の保護に役立つスタンドアロンの製品としても利用できます。

## <a name="how-do-i-sign-up-for-an-eop-trial-or-purchase-eop"></a>EOP の無料試用版に新規登録する、または EOPを購入するにはどうすればよいですか?

EOP の無料試用版に新規登録する、または EOP を購入するには、「[Exchange Online Protection ホーム ページ](https://products.office.com/exchange/exchange-email-security-spam-protection)」にアクセスしてください。 試用版の機能は、有料版のサブスクリプションと同じですが、「[Exchange Online Protection サービスの説明](https://products.office.com/exchange/microsoft-exchange-server-licensing-licensing-overview)」サブスクリプション プランで提供されている追加機能も含まれています。

## <a name="how-is-eop-priced"></a>EOP はどのような価格設定になっていますか?

EOP はユーザーごとにライセンスが付与されます。 最新の価格情報については、「[Exchange Online Protection ホーム ページ](https://products.office.com/exchange/exchange-email-security-spam-protection)」を参照してください。

## <a name="how-long-does-it-take-to-put-eop-into-production"></a>EOP を稼働させるまでにどの程度の時間がかかりますか?

「[EOP サービスを設定する](set-up-your-eop-service.md)」の手順に従って MX レコードを変更すると、メールが EOP を経由するようになり、すぐにフィルター処理が開始されます。 MX レコードが DNS 経由で送信されるまで 24 ～ 48 時間かかる場合があります。 このプロセス中は、いつでも保護設定を微調整できます。

## <a name="do-i-have-to-use-all-features-of-microsoft-365-to-use-eop-what-if-i-just-want-eop-protection-and-thats-all"></a>EOP を使用するには、Microsoft 365 のすべての機能を使用する必要がありますか? EOP 保護が必要で、それがすべてである場合は、

EOP を使用すると、Microsoft 365 の他の機能を使用せずに、オンプレミスのメールボックスを保護できます。 これをスタンドアロン サブスクリプションといいます。 EOP 機能のリストは、「[Exchange Online Protection サービスの説明](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)」で確認できます。

## <a name="why-do-i-need-a-microsoft-365-tenant-when-signing-up-for-email-filtering-through-eop"></a>EOP による電子メール フィルターにサインアップするときに Microsoft 365 テナントが必要な理由

Microsoft 365 は、Microsoft 365 テナントを通じてアクセスできる製品とサービスのコレクションに与えられる名前です。 Microsoft 365 テナントは、電子メール フィルターのライセンスを追加する開始点と考えて下さい。

## <a name="does-eop-have-a-communication-portal-where-i-can-find-out-about-known-issues-and-expected-resolutions-what-about-new-features"></a>EOP には、既知の問題や想定される解決策を見つけることのできる通信ポータルがありますか。 新機能についてはどうですか。

Microsoft 365 管理センターには、この情報の一部があります。 サービス レベル イベントの影響を受け取った場合は、Microsoft 365 管理センターにサインインした後、通信アラート (通常はベル アイコンが付きます) が表示されます。 その項目を参照して、適切に対応することをお勧めします。

新しい EOP 機能に関して [、Microsoft 365 for business ロードマップ](https://www.microsoft.com/microsoft-365/roadmap?filters=O365) は、今後の新機能に関する情報を見つけ出す良いリソースです。 また、Microsoft [365](https://www.microsoft.com/microsoft-365/blog/) ブログ Web サイトに新機能に関するブログ記事を投稿します。

## <a name="does-the-service-work-with-legacy-exchange-versions-such-as-exchange-server-2010-and-non-exchange-environments"></a>このサービスは Exchange の旧バージョン (Exchange Server 2010 など) や Exchange 以外の環境で使用できますか?

はい、このサービスはサーバーに依存せず、すべての SMTP メール転送エージェントで使用できます。

## <a name="what-size-organization-can-use-the-service"></a>このサービスは、どの程度の規模の組織が対象ですか?

組織の規模に関わらずご利用いただけます。 EOP ネットワークは、どのような速度で成長する組織であっても十分対応可能です。

## <a name="what-permissions-do-i-need-to-set-up-eop"></a>EOP を設定するのに必要なアクセス許可はどのようなものですか?

EOP を構成するには、グローバル管理者または Exchange Company Administrator (組織の管理役割グループ) である必要があります。

## <a name="how-do-i-know-my-data-and-private-information-are-safe"></a>個人データや個人情報が安全に保護されていることを確認できますか?

サービス レベル アグリーメント (SLA) などの個人データや個人情報を安全に保護するための手順の詳細については、「[Office 365 セキュリティ センター](https://www.microsoft.com/trust-center)」を参照してください。

## <a name="are-there-any-limits-i-should-be-aware-of-such-as-message-size-limitations"></a>メッセージ サイズの制限などの注意すべき制限がありますか。

はい。 EOP の制限の詳細については [、「Exchange Online Protection Limits」を参照してください](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-limits)。

## <a name="does-eop-support-powershell"></a>EOP は PowerShell をサポートしていますか?

はい、完全な EOP 機能は PowerShell 経由で利用できます。 Exchange Online メールボックスを使用する組織向け Exchange Online PowerShell。スタンドアロン EOP 組織向けスタンドアロン EOP PowerShell。 詳細については [、「Exchange Online PowerShell」](/powershell/exchange/exchange-online-powershell) および [「Exchange Online Protection PowerShell」を参照してください](/powershell/exchange/exchange-online-protection-powershell)。