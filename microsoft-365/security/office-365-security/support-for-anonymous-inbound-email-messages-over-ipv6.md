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
description: 管理者は、Exchange Online および Exchange Online Protection で IPv6 ソースからの匿名受信電子メールのサポートを構成する方法について学習できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 63c9434fbd1f69c0cbd3145717b712857eb17e28
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290275"
---
# <a name="add-support-for-anonymous-inbound-email-over-ipv6-in-microsoft-365"></a>Microsoft 365 で IPv6 を使用して匿名受信メールのサポートを追加する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Exchange Online メールボックスを持つ Microsoft 365 組織と、Exchange Online メールボックスのないスタンドアロンの Exchange Online Protection (EOP) 組織は、IPv6 を使用した匿名受信電子メールをサポートしています。 送信元 IPv6 電子メール サーバーは、次の両方の要件を満たしている必要があります。

- 送信元 IPv6 アドレスには、宛先が IPv6 アドレスからドメイン名を検索できる有効な逆引き DNS 参照 (PTR) レコードが必要です。

- また、送信者は、SPF 検証 ([RFC 7208](https://tools.ietf.org/html/rfc7208) で既定されている) と [DKIM 検証](http://dkim.org/) ( [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt) で既定されている) のどちらかに合格する必要があります。

組織が IPv6 を使用して匿名の受信メールを受信するには、管理者が Microsoft サポートに問い合わせ、それを求める必要があります。 サポートリクエストを開く方法については、「一部のビジネス製品のサポートに問い合わせ - 管理者向け [ヘルプ」を参照してください](../../admin/contact-support-for-business-products.md)。

組織で匿名受信 IPv6 メッセージのサポートが有効になると、メッセージはサービスによって提供される通常のメッセージ フィルター処理を通過します。

## <a name="troubleshooting"></a>トラブルシューティング

- 送信元の電子メール サーバーに IPv6 逆引き DNS 参照レコードが存在しない場合、メッセージは次のエラーで拒否されます。

  > 450 4.7.25 サービスが利用できません。IPv6 アドレス [2a01:111:f200:2004::240] を送信するには、逆引き DNS レコードが必要です。

- 送信者が SPF または DKIM 検証に合格しない場合、メッセージは次のエラーで拒否されます。

  > 450 4.7.26 サービスが利用できません。IPv6 を通して送信されるメッセージ [2a01:111:f200:2004::240] は、SPF または DKIM 検証に合格する必要があります。

- オプトインする前に匿名 IPv6 メッセージを受信すると、メッセージは次のエラーで拒否されます。

  > 550 5.2.1 サービスは利用できません。[contoso.com] は IPv6 を使用した電子メールを受け入れできません。

## <a name="related-topics"></a>関連項目

[DKIM 署名付きメッセージの検証をサポートする](support-for-validation-of-dkim-signed-messages.md)
