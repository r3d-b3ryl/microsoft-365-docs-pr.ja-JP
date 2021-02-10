---
title: 外部電子メール転送の構成と制御, 自動転送, 5.7.520 アクセスが拒否されました, 外部転送を無効にする, 管理者が外部転送を無効にしました, 送信スパム対策ポリシー
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
ms.openlocfilehash: e578cadf6687e02c900299a75bdd00a9d6e5b2ee
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166149"
---
# <a name="control-automatic-external-email-forwarding-in-microsoft-365"></a>Microsoft 365 で外部メールの自動転送を制御する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

管理者として、自動的に転送されるメッセージを外部の受信者 (組織外の受信者) に制限または制御する会社の要件がある場合があります。 電子メールの転送は便利ですが、情報が開示される可能性のためにセキュリティ上のリスクが生じ得る場合があります。 攻撃者はこの情報を使用して、組織やパートナーを攻撃する可能性があります。


Microsoft 365 では、次の種類の自動転送を利用できます。

- ユーザー [は、(](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) 意図的に、またはアカウントが侵害された結果として) メッセージを外部の送信者に自動的に転送する受信トレイ ルールを構成できます。

- 管理者は、メッセージを外部 [の受信者に](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) 自動的に転送するメールボックス転送 _(SMTP_ 転送とも呼ばれる) を構成できます。 管理者は、単にメッセージを転送するか、転送されたメッセージのコピーをメールボックスに保持するか選択できます。

送信スパム フィルター ポリシーを使用して、外部受信者への自動転送を制御できます。 次の 3 つの設定を使用できます。

- **自動**: 外部自動転送がブロックされます。 メッセージの内部自動転送は引き続き機能します。 これは、既定の設定です。
- **オン**: 外部自動転送は許可され、制限されません。
- **オフ**: 外部自動転送が無効になり、送信者に配信不可レポート (NDR またはバウンス メッセージとも呼ばれる) が生成されます。

これらの設定を構成する方法については [、「EOP](configure-the-outbound-spam-policy.md)で送信スパム フィルターを構成する」を参照してください。

> [!NOTE]
>
> - 自動転送を無効にすると、メッセージを外部アドレスにリダイレクトする受信トレイ ルール (ユーザー) またはメールボックス転送 (管理者) が無効になります。
>
> - 内部ユーザー間のメッセージの自動転送は、送信スパム フィルター ポリシーの設定の影響を受けしません。
>
> - 自動転送されたメッセージ レポートで、外部の受信者に自動的にメッセージを転送するユーザーに関する情報 [を確認できます](mfi-auto-forwarded-messages-report.md)。

## <a name="how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls"></a>送信スパム フィルター ポリシー設定と他の自動電子メール転送コントロールの動作方法

管理者として、メールの自動転送を許可またはブロックする他のコントロールが既に構成されている可能性があります。 次に例を示します。

- [一部またはすべての](https://docs.microsoft.com/exchange/mail-flow-best-practices/remote-domains/remote-domains) 外部ドメインへの電子メールの自動転送を許可またはブロックするリモート ドメイン。

- Exchange メール フロー [ルール](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (トランスポート ルールとも呼ばれる) の条件とアクション。外部の受信者に自動的に転送されるメッセージを検出してブロックします。

リモート ドメイン設定とメール フロー ルールは、送信スパム フィルター ポリシーの設定とは独立しています。 次に例を示します。

- リモート ドメインの自動転送は許可しますが、送信スパム フィルター ポリシーでは自動転送をブロックします。 この例では、自動的に転送されるメッセージがブロックされます。

- 送信スパム フィルター ポリシーでは自動転送を許可しますが、メール フロー ルールまたはリモート ドメイン設定を使用して、自動的に転送される電子メールをブロックします。 この例では、メール フロー ルールまたはリモート ドメイン設定によって、自動的に転送されるメッセージがブロックされます。

この機能の独立性により、送信スパム フィルター ポリシーでの自動転送を許可する (たとえば) が、リモート ドメインを使用して、ユーザーがメッセージを転送できる外部ドメインを制御できます。

## <a name="the-blocked-email-forwarding-message"></a>ブロックされた電子メール転送メッセージ

メッセージが自動的に転送されると検出され、組織のポリシーによってそのアクティビティがブロックされると、メッセージは次の情報を含む NDR 内の送信者に返されます。

`5.7.520 Access denied, Your organization does not allow external forwarding. Please contact your administrator for further assistance. AS(7555)`
