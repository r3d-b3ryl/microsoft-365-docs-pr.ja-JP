---
title: IPv6 経由の匿名受信メールのサポートを追加する
f1.keywords:
- NOCSH
author: chrisda
ms.author: chrisda
manager: chrisda
audience: ITPro
ms.topic: how-to
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: b68df621-0a5f-4824-8abc-41e0c4fd1398
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理は、Exchange OnlineとExchange Online Protectionで IPv6 ソースからの匿名受信メールのサポートを構成する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 093ab458e8894105536e1c3dd46d2c911de440fd
ms.sourcegitcommit: 725a92b0b1555572b306b285a0e7a7614d34e5e5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/24/2022
ms.locfileid: "65649101"
---
# <a name="add-support-for-anonymous-inbound-email-over-ipv6-in-microsoft-365"></a>Microsoft 365で IPv6 経由の匿名受信メールのサポートを追加する

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Exchange Online メールボックスとスタンドアロン Exchange Online Protection (EOP) 組織を持つMicrosoft 365組織では、Exchange Online メールボックスを使用しない組織では、IPv6 経由の匿名受信メールがサポートされます。 ソース IPv6 電子メール サーバーは、次の要件の両方を満たしている必要があります。

- ソース IPv6 アドレスには、宛先が IPv6 アドレスからドメイン名を検索できるようにする有効な逆引き DNS ルックアップ (PTR) レコードが必要です。

- また、送信者は、SPF 検証 ([RFC 7208](https://tools.ietf.org/html/rfc7208) で既定されている) と [DKIM 検証](http://dkim.org/) ( [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt) で既定されている) のどちらかに合格する必要があります。

組織が IPv6 経由で匿名受信メールを受信するには、管理者が Microsoft サポートに問い合わせて要求する必要があります。 サポート リクエストを開く方法については、「[ビジネス製品のサポートにお問い合わせください - 管理 ヘルプ」を参照してください](../../admin/get-help-support.md)。

組織で匿名受信 IPv6 メッセージのサポートが有効になると、メッセージはサービスによって提供される通常のメッセージ フィルター処理を通過します。

## <a name="troubleshooting"></a>トラブルシューティング

- ソース電子メール サーバーに IPv6 逆引き DNS 参照レコードがない場合、メッセージは拒否され、次のエラーが発生します。

  > 450 4.7.25 サービスは使用できません。IPv6 アドレスを送信する [2a01:111:f200:2004::240] には逆引き DNS レコードが必要です。

- 送信者が SPF または DKIM の検証に合格しない場合、メッセージは拒否され、次のエラーが発生します。

  > 450 4.7.26 サービスは使用できません。IPv6 経由で送信されたメッセージ [2a01:111:f200:2004::240] は SPF または DKIM 検証に合格する必要があります。

- オプトインする前に匿名の IPv6 メッセージを受信しようとすると、次のエラーでメッセージが拒否されます。

  > 550 5.2.1 サービスは使用できません。[contoso.com] は IPv6 経由のメールを受け付けません。

## <a name="related-topics"></a>関連項目

[DKIM 署名付きメッセージの検証をサポートする](support-for-validation-of-dkim-signed-messages.md)
