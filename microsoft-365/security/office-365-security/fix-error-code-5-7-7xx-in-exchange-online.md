---
title: Exchange Online でエラーコード 5.7.7 xx のメール配信の問題を修正する
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Exchange Online でエラーコード 5.7.7 xx の電子メールの問題を解決する方法について説明します (テナントがメールの送信をブロックされた場合)。
ms.openlocfilehash: 831efac29bb2e878585f97419dfd9dca67c67409
ms.sourcegitcommit: cf7b0fd80ecfb7a216111a801269c5322794795e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/09/2020
ms.locfileid: "40995231"
---
# <a name="fix-email-delivery-issues-for-error-code-577xx-in-exchange-online"></a>Exchange Online でエラーコード 5.7.7 xx のメール配信の問題を修正する

このトピックでは、配信不能レポート (NDR、バウンスメッセージ、配信状態通知、または DSN とも呼ばれる) に状態コード 550 5.7.7 xx が表示される場合に実行できる操作について説明します。 この自動通知は、テナントが1つまたは別の方法で電子メールの送信を制限されている場合に表示されます。 これらのエラーコードは通常、705または750として表示されます。

## <a name="57705-tenant-has-exceeded-threshold-restriction-what-you-need-to-know"></a>5.7.705: テナントがしきい値制限を超過しました: 知っておくべきこと

ユーザーが特定の量の疑わしい電子メールをサービス経由で送信すると、その問題が解決されるまで、すべてのユーザーが電子メールを送信できなくなります。 これは通常、侵害 (最も一般的) または大量のメールを送信した結果です。 ユーザーは、次のような状態の NDR を受信します。

`550 5.7.705 Access denied, tenant has exceeded threshold`

まれに、既に期限が切れた後にサブスクリプションを更新した場合にも発生する可能性があります。 サービスが新しいサブスクリプション情報 (通常は1日以内) を同期するのには時間がかかりますが、組織がメールを送信できないようにブロックされることがあります。 これを回避する最善の方法は、サブスクリプションの有効期限が切れないようにすることです。

## <a name="57750-unregistered-domain-email-restriction-what-you-need-to-know"></a>5.7.750: 登録が解除されるドメインの電子メール制限: 理解しておくべき情報

Office 365 では、テナントが Exchange Online Protection (EOP) を介して一部のメッセージを中継することが許可されています。 以下に例を示します。

- Office 365 メールボックスは、外部の送信者から電子メールを受信します。 メール転送は Office 365 メールボックスで構成されているため、メッセージはユーザーの外部の電子メールアドレスに戻されます。 このシナリオは、学生が自分の個人用メールアカウントを使用して学校関連のメッセージを表示する教育環境で最もよく見られます。

- EOP を介して送信メールを送信するオンプレミスの電子メールサーバーがあるハイブリッド環境。

### <a name="problems-with-unregistered-domains"></a>未登録のドメインに関する問題

問題は、社内のメールサーバーが危険にさらされた場合に、EOP を介して大量のスパムを中継することです。 ほとんどの場合、コネクタは正しく設定されていますが、未登録の (プロビジョニングされていない) ドメインからメールが送信されています。 Office 365 では、登録されていないドメインからの十分な量の電子メールを使用できますが、電子メールを承認済みドメインとして送信するために使用するすべてのドメインを構成する必要があります。

いったん侵害されると、テナントは未登録ドメインの送信電子メールを送信できなくなります。 ユーザーは、次のような状態の NDR を受信します。

`550 5.7.750 Service unavailable. Client blocked from sending from unregistered domains`

## <a name="how-to-unblocking-tenant-in-order-to-send-again"></a>再送信のためにテナントのブロックを解除する方法

テナントが電子メールの送信をブロックされている場合は、いくつかの作業を行う必要があります。

1. すべての電子メールドメインが登録されていることを確認します。 詳細については、「 [Office 365 へのドメインの追加](https://docs.microsoft.com/office365/admin/setup/add-domain)」および「 [Exchange Online で承認済みドメインを管理](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)する」を参照してください。

2. Office 365 組織内のすべての管理者に対して[MFA を有効に](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication)します。

3. すべての電子メールドメインが登録されていることを確認します。 詳細については、「 [Office 365 へのドメインの追加](https://docs.microsoft.com/office365/admin/setup/add-domain)」および「 [Exchange Online で承認済みドメインを管理](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)する」を参照してください。

4. 異常な[コネクタ](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)を探します。 悪意のある俳優は、スパムを送信するために Office 365 組織に新しい受信コネクタを作成することがよくあります。 既存のコネクタを表示するには、「 [Office 365 でコネクタを検証](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/validate-connectors)する」を参照してください。

5. 「 [Office 365 で侵害された電子メールアカウントに応答する](responding-to-a-compromised-email-account.md)」の説明に従って、侵害されたユーザーをチェックします。

6. オンプレミスの電子メールサーバーをロックし、侵害されていないことを確認します。

   > [!TIP]
   > 特にサードパーティ製サーバーを使用している場合は、多くの要因があります。 いずれにしても、すべての送信メールが正当であることを確認する必要があります。

7. Microsoft サポートに連絡して、再度電子メールを送信するようにテナントのブロック解除を取得するように依頼します。 エラーコードは役に立ちますが、環境がセキュリティで保護されており、スパムを送信することができないことを証明する必要があります。 サポート案件を開くには、「 [business products のサポートへのお問い合わせ-管理者向けヘルプ](https://docs.microsoft.com/office365/admin/contact-support-for-business-products)」を参照してください。

## <a name="for-more-information"></a>関連情報

[Office 365 メールのスパム対策保護](anti-spam-protection.md)

[Exchange Online サービスの説明の「送信制限」セクションのバルクメールガイダンス](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#receiving-and-sending-limits)

[Office 365 でのメール配信不能レポート](https://docs.microsoft.com/exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online)

[メールボックスへの電子メールの転送を構成する](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)

[Office 365 を使用してメールを送信するように多機能デバイスまたはアプリケーションをセット アップする方法](https://docs.microsoft.com/Exchange/mail-flow-best-practices/how-to-set-up-a-multifunction-device-or-application-to-send-email-using-office-3)

[Exchange Online で承認済みドメインを管理](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)します。
