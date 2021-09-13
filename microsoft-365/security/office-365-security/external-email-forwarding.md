---
title: 外部メール転送の構成と制御、自動転送、5.7.520 Access Denied、外部転送の無効化、管理者が外部転送、送信スパム対策ポリシーを無効にしました
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: .
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6b96d3d656a89e7102550d09a2f5052fdb5ae818
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59214434"
---
# <a name="control-automatic-external-email-forwarding-in-microsoft-365"></a>外部メールの自動転送を制御Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

管理者として、自動的に転送されるメッセージを外部受信者 (組織外の受信者) に制限または制御する会社の要件がある場合があります。 電子メールの転送は便利ですが、情報の漏えいによるセキュリティ リスクを引き起す可能性があります。 攻撃者は、この情報を使用して組織またはパートナーを攻撃する可能性があります。

自動転送の次の種類は、次のMicrosoft 365。

- ユーザーは受信 [トレイ ルールを](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) 構成して、メッセージを外部の送信者に自動的に転送できます (意図的に、またはアカウントが侵害された結果)。
- 管理者は、メールボックス転送 _(SMTP_[転送](/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)とも呼ばれる) を構成して、メッセージを外部受信者に自動的に転送できます。 管理者は、単にメッセージを転送するか、転送されたメッセージのコピーをメールボックスに保持するか選択できます。

送信スパム フィルター ポリシーを使用して、外部受信者への自動転送を制御できます。 次の 3 つの設定を使用できます。

- **自動 - システム制御**: 外部自動転送がブロックされます。 メッセージの内部自動転送は引き続き機能します。 これは、既定の設定です。
- **On**: 自動外部転送は許可され、制限されません。
- **Off**: 自動外部転送が無効になり、送信者に配信不可レポート (NDR またはバウンス メッセージとも呼ばれる) が発生します。

これらの設定を構成する方法については、「EOP で送信スパム フィルターを構成する」 [を参照してください](configure-the-outbound-spam-policy.md)。

> [!NOTE]
>
> - 自動転送を無効にすると、メッセージを外部アドレスにリダイレクトする受信トレイ ルール (ユーザー) またはメールボックス転送 (管理者) が無効になります。
>
> - 内部ユーザー間のメッセージの自動転送は、送信スパム フィルター ポリシーの設定の影響を受け取らない。
>
> - メッセージを外部受信者に自動的に転送するユーザーに関する情報は、自動転送メッセージ レポート [で確認できます](mfi-auto-forwarded-messages-report.md)。

## <a name="how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls"></a>送信スパム フィルター ポリシー設定が他の自動メール転送コントロールとどのように機能する

管理者は、電子メールの自動転送を許可またはブロックするように他のコントロールを既に構成している可能性があります。 以下に例を示します。

- [一部またはすべての](/exchange/mail-flow-best-practices/remote-domains/remote-domains) 外部ドメインへの自動メール転送を許可またはブロックするリモート ドメイン。
- メール フロー ルール (トランスポート[Exchangeとも](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)呼ばれる) で、自動的に転送されたメッセージを検出して外部受信者にブロックする条件とアクション。

リモート ドメイン設定とメール フロー ルールは、送信スパム フィルター ポリシーの設定とは独立しています。 以下に例を示します。

- リモート ドメインの自動転送を許可しますが、送信スパム フィルター ポリシーでの自動転送をブロックします。 この例では、自動的に転送されたメッセージがブロックされます。
- 送信スパム フィルター ポリシーで自動転送を許可しますが、メール フロー ルールまたはリモート ドメイン設定を使用して、自動的に転送されるメールをブロックします。 この例では、メール フロー ルールまたはリモート ドメイン設定によって、自動的に転送されるメッセージがブロックされます。

この機能の独立性により、(たとえば) 送信スパム フィルター ポリシーでの自動転送を許可できますが、リモート ドメインを使用して、ユーザーがメッセージを転送できる外部ドメインを制御できます。

## <a name="blocked-email-forwarding-messages"></a>ブロックされたメール転送メッセージ

メッセージが自動的に転送されると検出され、送信スパム フィルター[](configure-the-outbound-spam-policy.md)ポリシーによってそのアクティビティがブロックされると、次の情報を含む NDR の送信者にメッセージが返されます。

`5.7.520 Access denied, Your organization does not allow external forwarding. Please contact your administrator for further assistance. AS(7555)`
