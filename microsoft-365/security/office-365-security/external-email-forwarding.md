---
title: 外部メール転送の構成と制御、自動転送、5.7.520 アクセス拒否、外部転送の無効化、管理者が外部転送を無効にした、送信スパム対策ポリシー
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: .
ms.openlocfilehash: 59e2c938c70dd8e3060fd85d084acbe8f79856ad
ms.sourcegitcommit: 04a43a146cb62a10b1a4555ec3bed49eb08fbb99
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2020
ms.locfileid: "48806632"
---
# <a name="control-automatic-external-email-forwarding-in-microsoft-365"></a>Microsoft 365 での自動外部電子メール転送の制御

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

管理者は、外部の受信者 (組織外の受信者) に自動的に転送されるメッセージを制限または制御するために、会社の要件を持つ場合があります。 メールの転送は便利ですが、情報が漏洩する可能性があるため、セキュリティ上のリスクが生じる可能性があります。 攻撃者は、この情報を使用して組織またはパートナーに攻撃を仕掛けることができます。

Microsoft 365 では、次の種類の自動転送を使用できます。

- ユーザーは、メッセージを外部の送信者に自動的に転送するように [受信トレイルール](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) を構成できます (故意または侵害されたアカウントの結果として)。

- 管理者は、外部の受信者にメッセージを自動的に転送するように、 [メールボックス転送](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) ( _SMTP 転送_ とも呼ばれます) を構成できます。

送信スパムフィルターポリシーを使用して、外部の受信者への自動転送を制御することができます。 次の3つの設定を使用できます。

- **Automatic** : 自動外部転送がブロックされます。 メッセージの内部自動転送は引き続き機能します。 これは、既定の設定です。

- **オン** : 外部の自動転送が許可されており、制限されていません。

- **Off** : 自動外部転送が無効になり、送信者に配信不能レポート (NDR またはバウンスメッセージとも呼ばれます) が発生します。

これらの設定を構成する方法については、「 [EOP で送信スパムフィルターを構成](configure-the-outbound-spam-policy.md)する」を参照してください。

> [!NOTE]
> 
> - 自動転送を無効にすると、メッセージを外部アドレスにリダイレクトする受信トレイルール (ユーザー) またはメールボックス転送 (管理者) が無効になります。
> 
> - 内部ユーザー間でのメッセージの自動転送は、送信スパムフィルターポリシーの設定の影響を受けません。
> 
> - 自動転送された [メッセージレポート](mfi-auto-forwarded-messages-report.md)で、外部の受信者にメッセージを自動的に転送するユーザーに関する情報を確認できます。

## <a name="how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls"></a>送信スパムフィルターポリシーの設定が他の自動メール転送コントロールとどのように機能するか

管理者は、電子メールの自動転送を許可またはブロックするように、既に他のコントロールを構成している場合があります。 以下に例を示します。

- [リモートドメイン](https://docs.microsoft.com/exchange/mail-flow-best-practices/remote-domains/remote-domains) によって、一部またはすべての外部ドメインへの自動電子メール転送を許可またはブロックすることができます。

- Exchange [メールフロールール](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (トランスポートルールとも呼ばれます) 内の条件とアクションは、外部の受信者に自動的に転送されるメッセージを検出してブロックします。

リモートドメインの設定とメールフロールールは、送信スパムフィルターポリシーの設定とは独立しています。 以下に例を示します。

- リモートドメインへの自動転送を許可するが、送信スパムフィルターポリシーの自動転送をブロックする。 この例では、自動的に転送されるメッセージがブロックされます。

- 送信スパムフィルターポリシーでの自動転送を許可しますが、自動的に転送された電子メールをブロックするには、メールフロールールまたはリモートドメイン設定を使用します。 この例では、メールフロールールまたはリモートドメインの設定は、自動的に転送されるメッセージをブロックします。

この機能の独立性により、送信スパムフィルターポリシーの自動転送を許可することができますが、リモートドメインを使用して、ユーザーがメッセージを転送できる外部ドメインを制御することができます。

## <a name="the-blocked-email-forwarding-message"></a>ブロックされたメール転送メッセージ

メッセージが自動的に転送されると検出され、組織のポリシーによってそのアクティビティが *ブロック* されると、次の情報を含む NDR でメッセージが送信者に返されます。

`5.7.520 Access denied, Your organization does not allow external forwarding. Please contact your administrator for further assistance. AS(7555)`
