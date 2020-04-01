---
title: IPv6 経由の匿名受信電子メールのサポートを追加する
f1.keywords:
- NOCSH
author: chrisda
ms.author: chrisda
manager: chrisda
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: b68df621-0a5f-4824-8abc-41e0c4fd1398
ms.collection:
- M365-security-compliance
description: 管理者は、Exchange Online および Exchange Online Protection の IPv6 ソースからの匿名受信電子メールのサポートを構成する方法について説明します。
ms.openlocfilehash: 67e839249d41381be22bbccf6b09d1616c387c66
ms.sourcegitcommit: 748bc3484b7ccbd65b558f495b6fa42196c3c571
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2020
ms.locfileid: "43083643"
---
# <a name="add-support-for-anonymous-inbound-email-over-ipv6-in-office-365"></a>Office 365 で IPv6 による匿名受信電子メールのサポートを追加する

Exchange online メールボックスを使用しない exchange online メールボックスおよびスタンドアロンの Exchange Online Protection (EOP) 組織を使用している Office 365 組織は、IPv6 経由の匿名受信電子メールをサポートしています。 ソース IPv6 電子メールサーバーは、次の両方の要件を満たしている必要があります。

- 送信元 IPv6 アドレスには、宛先が IPv6 アドレスからドメイン名を検索できる有効な逆引き DNS 参照 (PTR) レコードが含まれている必要があります。

- また、送信者は、SPF 検証 ([RFC 7208](https://tools.ietf.org/html/rfc7208) で既定されている) と [DKIM 検証](https://dkim.org/) ( [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt) で既定されている) のどちらかに合格する必要があります。

組織が IPv6 経由で匿名受信電子メールを受信できるようにするには、管理者が Microsoft サポートに連絡して、そのことを要求する必要があります。

1. Microsoft 365 管理センター <https://admin.microsoft.com/adminportal/home>を開き、[**ヘルプ**] (?) をクリックします。

2. [**ヘルプが必要ですか?]** ポップアップが表示されたら、検索ボックスにわかりやすい名前 (「匿名受信 IPv6 電子メールを要求する」など) を入力し、enter キーを押します。

3. ページの下部にある [サポートに**お問い合わせ**ください] をクリックします。

4. 表示される [ **contact support** ] ページで、情報を入力して確認し (必要に応じてスクロールします)、[**自分の連絡先**] をクリックします。

組織で匿名受信 IPv6 メッセージのサポートが有効になると、メッセージはサービスによって提供される通常のメッセージフィルタリングを通過します。

## <a name="troubleshooting"></a>トラブルシューティング

- 送信元の電子メールサーバーに IPv6 逆引き DNS 参照レコードがない場合は、次のエラーが発生してメッセージが拒否されます。

  > 450 4.7.25 サービスは利用できません。送信 IPv6 アドレス [2a01: 111: f200: 2004:: 240] には逆引き DNS レコードが必要です。

- 送信者が SPF または DKIM 検証に合格しない場合、メッセージは次のエラーで拒否されます。

  > 450 4.7.26 サービスを使用できません。 IPv6 経由で送信されるメッセージ [2a01: 111: f200: 2004:: 240] は、SPF または DKIM 検証に合格する必要があります。

- 匿名の IPv6 メッセージを受信しようとすると、次のエラーが発生して、メッセージが拒否されます。

  > 550 5.2.1 サービスを使用できません。 [contoso.com] は IPv6 経由の電子メールを受け入れません。

## <a name="for-more-information"></a>関連情報

[DKIM 署名付きメッセージの検証をサポートする](support-for-validation-of-dkim-signed-messages.md)
