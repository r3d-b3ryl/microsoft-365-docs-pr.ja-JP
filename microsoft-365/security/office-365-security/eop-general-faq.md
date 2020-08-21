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
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 9dbff00a-474e-4452-aeb5-5be9a6b8c6d5
ms.custom:
- seo-marvel-apr2020
description: Exchange Online Protection (EOP) のクラウド ホスト型電子メール フィルタリング サービスに関してよく寄せられる質問に対する回答を示します。
ms.openlocfilehash: 42162ea841f876fc5e958d67fab61dbe4bffe9de
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827763"
---
# <a name="eop-general-faq"></a>EOP の一般的な FAQ

ここでは、Exchange Online Protection (EOP) のクラウド ホスト型電子メール フィルタリング サービスについてよく寄せられる質問を示します。 その他のよく寄せられる質問 (FAQ) については、以下のリンクを参照してください。

- [EOP のキューイング、保留、返送されるメッセージに関する FAQ](eop-queued-deferred-and-bounced-messages-faq.md)

- [代理管理に関する FAQ](delegated-administration-faq.md)

- [スパム対策保護に関してよく寄せられる質問](anti-spam-protection-faq.md)

- [検疫に関する FAQ](quarantine-faq.md)

- [マルウェア対策保護のよく寄せられる質問](anti-malware-protection-faq-eop.md)

- [メッセージ追跡の FAQ](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/message-trace-faq)

## <a name="what-is-eop"></a>EOP とは何ですか?

EOP とは、クラウド ホスト型の電子メール フィルター サービスで、ユーザーをスパムやマルウェアから保護し、カスタム ポリシー ルールを適用するために構築されます。 EOP は、Exchange Online メールボックスを含むすべての Microsoft 365 サブスクリプションに含まれます。 EOP は、オンプレミスの電子メール環境の保護に役立つスタンドアロンサービスとしても利用できます。

## <a name="how-do-i-sign-up-for-an-eop-trial-or-purchase-eop"></a>EOP の無料試用版に新規登録する、または EOPを購入するにはどうすればよいですか?

EOP の無料試用版に新規登録する、または EOP を購入するには、「[Exchange Online Protection ホーム ページ](https://products.office.com/exchange/exchange-email-security-spam-protection)」にアクセスしてください。 試用版の機能は、有料版のサブスクリプションと同じですが、「[Exchange Online Protection サービスの説明](https://products.office.com/exchange/microsoft-exchange-server-licensing-licensing-overview)」サブスクリプション プランで提供されている追加機能も含まれています。

## <a name="how-is-eop-priced"></a>EOP はどのような価格設定になっていますか?

EOP はユーザーごとにライセンスが付与されます。 最新の価格情報については、「[Exchange Online Protection ホーム ページ](https://products.office.com/exchange/exchange-email-security-spam-protection)」を参照してください。

## <a name="how-long-does-it-take-to-put-eop-into-production"></a>EOP を稼働させるまでにどの程度の時間がかかりますか?

「[EOP サービスを設定する](set-up-your-eop-service.md)」の手順に従って MX レコードを変更すると、メールが EOP を経由するようになり、すぐにフィルター処理が開始されます。 MX レコードが DNS 経由で送信されるまで 24 ～ 48 時間かかる場合があります。 このプロセスの間いつでも保護設定を詳細に変更できます。

## <a name="do-i-have-to-use-all-features-of-microsoft-365-to-use-eop-what-if-i-just-want-eop-protection-and-thats-all"></a>EOP を使用するために、Microsoft 365 のすべての機能を使用する必要がありますか? EOP 保護が必要で、それだけの場合はどうでしょうか?

EOP によるオンプレミス メールボックスの保護は、Microsoft 365 のその他の機能を使用しなくても可能です。 これをスタンドアロン サブスクリプションといいます。 EOP 機能のリストは、「[Exchange Online Protection サービスの説明](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)」で確認できます。

## <a name="why-do-i-need-a-microsoft-365-tenant-when-signing-up-for-email-filtering-through-eop"></a>EOP を介した電子メール フィルタリングにサインアップする際に Microsoft 365 テナントが必要なのはなぜですか?

Microsoft 365 は、Microsoft 365 テナントを通じてアクセスできる一コレクションの製品およびサービスのコレクションに付けされる名前です。 Microsoft 365 テナントは、電子メール フィルタリングのライセンスを追加する開始点と考えてください。

## <a name="does-eop-have-a-communication-portal-where-i-can-find-out-about-known-issues-and-expected-resolutions-what-about-new-features"></a>EOP には、既知の問題や想定される解決策を見つけることのできる通信ポータルがありますか。 新機能についてはどうですか。

Microsoft 365 管理センターにこの情報の一部があります。 サービス レベル イベントの影響を受け取る場合は、Microsoft 365 の管理センターにサインインした後に通信アラートが (通常はベルのアイコンとなって) 表示されます。 その項目を参照して、適切に対応することをお勧めします。

EOP の新機能については [、Microsoft 365 for business ロードマップを](https://www.microsoft.com/microsoft-365/roadmap?filters=O365) 参照してください。 [Microsoft 365 ブログ](https://www.microsoft.com/microsoft-365/blog/)Web サイトには、新機能に関するブログ記事も投稿されています。

## <a name="does-the-service-work-with-legacy-exchange-versions-such-as-exchange-server-2010-and-non-exchange-environments"></a>このサービスは Exchange の旧バージョン (Exchange Server 2010 など) や Exchange 以外の環境で使用できますか?

はい、このサービスはサーバーに依存せず、すべての SMTP メール転送エージェントで使用できます。

## <a name="what-size-organization-can-use-the-service"></a>このサービスは、どの程度の規模の組織が対象ですか?

組織の規模に関わらずご利用いただけます。 EOP ネットワークは、どのような速度で成長する組織であっても十分対応可能です。

## <a name="what-permissions-do-i-need-to-set-up-eop"></a>EOP を設定するのに必要なアクセス許可はどのようなものですか?

EOP を構成するには、グローバル管理者か、Exchange 会社の管理者 (Organization Management 役割グループ) である必要があります。

## <a name="how-do-i-know-my-data-and-private-information-are-safe"></a>個人データや個人情報が安全に保護されていることを確認できますか?

サービス レベル アグリーメント (SLA) などの個人データや個人情報を安全に保護するための手順の詳細については、「[Office 365 セキュリティ センター](https://www.microsoft.com/trust-center)」を参照してください。

## <a name="are-there-any-limits-i-should-be-aware-of-such-as-message-size-limitations"></a>メッセージ サイズの制限などの注意すべき制限がありますか。

はい。 EOP の制限の詳細については、「Exchange Online Protection の [制限」を参照してください](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-limits)。

## <a name="does-eop-support-powershell"></a>EOP は PowerShell をサポートしていますか?

はい、すべての EOP 機能は PowerShell で利用できます。Exchange Online メールボックスを使用している組織の場合は Exchange Online PowerShellスタンドアロン EOP 組織用のスタンドアロン EOP PowerShell。 詳細については [、「Exchange Online の PowerShell と](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell) [Exchange Online Protection の PowerShell」を参照してください](https://docs.microsoft.com/powershell/exchange/exchange-online-protection-powershell)。
