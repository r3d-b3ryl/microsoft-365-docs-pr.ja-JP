---
title: IPv6 経由の匿名受信メールのサポートを追加する
f1.keywords:
- NOCSH
author: chrisda
ms.author: chrisda
manager: chrisda
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: b68df621-0a5f-4824-8abc-41e0c4fd1398
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理者は、IPv6 ソースから匿名受信メールのサポートを構成する方法について、Exchange OnlineおよびExchange Online Protection。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 80fdcc9dcfe3006ef8b21aa19856fe8c0ea3ff70
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59164623"
---
# <a name="add-support-for-anonymous-inbound-email-over-ipv6-in-microsoft-365"></a>IPv6 を使用して匿名受信メールのサポートを追加Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Microsoft 365メールボックスExchange Onlineスタンドアロン Exchange Online Protection (EOP) 組織を持つ組織では、Exchange Online IPv6 を使用した匿名の受信メールがサポートされます。 送信元 IPv6 メール サーバーは、次の両方の要件を満たしている必要があります。

- 送信元 IPv6 アドレスには、宛先が IPv6 アドレスからドメイン名を検索できる有効な逆引き DNS 参照 (PTR) レコードが必要です。

- また、送信者は、SPF 検証 ([RFC 7208](https://tools.ietf.org/html/rfc7208) で既定されている) と [DKIM 検証](http://dkim.org/) ( [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt) で既定されている) のどちらかに合格する必要があります。

組織が IPv6 を使用して匿名の受信メールを受け取る前に、管理者は Microsoft サポートに問い合わせ、そのメールを求める必要があります。 サポート要求を開く方法については、「ビジネス製品のサポートに問い合わせ- 管理者ヘルプ」 [を参照してください](../../business-video/get-help-support.md)。

組織内で匿名の受信 IPv6 メッセージのサポートが有効になると、サービスによって提供される通常のメッセージ フィルター処理を通過します。

## <a name="troubleshooting"></a>トラブルシューティング

- 送信元電子メール サーバーに IPv6 逆引き DNS 参照レコードが存在しない場合、メッセージは次のエラーで拒否されます。

  > 450 4.7.25 サービスを使用できません。IPv6 アドレス [2a01:111:f200:2004::240] を送信するには、逆 DNS レコードが必要です。

- 送信者が SPF または DKIM 検証に合格しない場合、メッセージは次のエラーで拒否されます。

  > 450 4.7.26 サービスが利用できない場合、IPv6 [2a01:111:f200:2004::240] で送信されるメッセージは、SPF または DKIM 検証に合格する必要があります。

- オプトインする前に匿名の IPv6 メッセージを受信しようとする場合、メッセージは次のエラーで拒否されます。

  > 550 5.2.1 サービスは利用できません。[contoso.com] は IPv6 を超える電子メールを受け入れできません。

## <a name="related-topics"></a>関連項目

[DKIM 署名付きメッセージの検証をサポートする](support-for-validation-of-dkim-signed-messages.md)
