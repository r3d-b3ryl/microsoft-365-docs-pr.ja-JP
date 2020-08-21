---
title: IPv6 経由の匿名受信メールのサポートを追加する
f1.keywords:
- NOCSH
author: chrisda
ms.author: chrisda
manager: chrisda
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: b68df621-0a5f-4824-8abc-41e0c4fd1398
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理者は、Exchange Online および Exchange Online Protection で IPv6 ソースからの匿名受信メールのサポートを構成する方法を学習できます。
ms.openlocfilehash: 7384c1044cc02ec20079dc03068c2ca99e68d2c2
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826779"
---
# <a name="add-support-for-anonymous-inbound-email-over-ipv6-in-microsoft-365"></a>Microsoft 365 で IPv6 経由の匿名受信メールのサポートを追加する

Exchange Online メールボックスを使用している Microsoft 365 組織や、Exchange Online メールボックスを使用していないスタンドアロン Exchange Online Protection (EOP) 組織は、IPv6 経由の匿名受信電子メールをサポートしています。 ソース IPv6 電子メール サーバーは、次の両方の要件を満たしている必要があります。

- 送信元 IPv6 アドレスには、宛先で IPv6 アドレスからドメイン名を検索できる有効な DNS 逆引き DNS 参照 (PTR) レコードが必要です。

- また、送信者は、SPF 検証 ([RFC 7208](https://tools.ietf.org/html/rfc7208) で既定されている) と [DKIM 検証](https://dkim.org/) ( [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt) で既定されている) のどちらかに合格する必要があります。

組織が IPv6 経由で匿名受信メールを受信するには、管理者が Microsoft サポートに連絡して、そのメールを要求する必要があります。 サポート要求を開く方法については、一次ビジネス製品のサポートに [問い合わせください - 管理者ヘルプ](../../admin/contact-support-for-business-products.md)。

組織で匿名受信 IPv6 メッセージのサポートが有効にされると、そのメッセージはサービスが提供する通常のメッセージ フィルタリングを通して行います。

## <a name="troubleshooting"></a>トラブルシューティング

- 送信元の電子メール サーバーに IPv6 逆引き DNS 参照レコードがない場合、メッセージは次のエラーにより拒否されます。

  > 450 4.7.25 サービスを利用できません。IPv6 アドレスを送信する [2a01:111:f200:2004::240] は逆引き DNS レコードを持つ必要があります。

- 送信者が SPF または DKIM 検証に合格しない場合、メッセージは次のエラーにより拒否されます。

  > 450 4.7.26 サービス不利用可能、IPv6 [2a01:111:f200:2004::240] を使って送信されたメッセージは、SPF または DKIM 検証に合格する必要があります。

- オプトインする前に匿名 IPv6 メッセージを受信しようとすると、次のエラーによりメッセージは拒否されます。

  > 550 5.2.1 Service unavailable, [contoso.com] は IPv6 経由の電子メールを受け付けません。

## <a name="related-topics"></a>関連トピック

[DKIM 署名付きメッセージの検証をサポートする](support-for-validation-of-dkim-signed-messages.md)