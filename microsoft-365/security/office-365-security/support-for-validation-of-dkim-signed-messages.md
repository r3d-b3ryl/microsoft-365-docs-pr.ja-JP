---
title: ドメイン キー識別メール (DKIM) 署名済みメッセージの検証のサポート
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: a4c95148-a00c-4d12-85ed-88520b547d97
ms.collection:
- M365-security-compliance
description: Exchange Online ProtectionとExchange Onlineでの DKIM 署名済みメッセージの検証について説明します
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: dcdd251ba1266033671ac524426d1ac3d2f56a10
ms.sourcegitcommit: fdd0294e6cda916392ee66f5a1d2a235fb7272f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/29/2022
ms.locfileid: "65130716"
---
# <a name="support-for-validation-of-dkim-signed-messages"></a>DKIM 署名付きメッセージの検証をサポートする

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Exchange Online Protection (EOP) とExchange Onlineはどちらも、ドメイン キー識別メール ([DKIM](https://www.rfc-editor.org/rfc/rfc6376.txt)) メッセージの受信検証をサポートします。

DKIM は、電子メール メッセージが他のユーザーによって *スプーフィング* されておらず、それが送信されたドメインから送信されたことを検証します。 電子メール メッセージを送信した組織に関連付けます。 DKIM 検証は、IPv6 で送信されたすべてのメッセージに対して自動的に使用されます。 Microsoft 365は、IPv4 経由でメールが送信されるときにも DKIM をサポートします。 (IPv6 サポートの詳細については、「 [IPv6 経由の匿名受信電子メール メッセージのサポート」を](support-for-anonymous-inbound-email-messages-over-ipv6.md)参照してください)。

DKIM は、メッセージ ヘッダーのDKIM-Signatureヘッダーに表示されるデジタル署名されたメッセージを検証します。 DKIM-Signature検証の結果は、Authentication-Results ヘッダーにスタンプされます。 メッセージ ヘッダー テキストは次のように表示されます (contoso.com が送信者です)。

 `Authentication-Results: <contoso.com>; dkim=pass (signature was verified) header.d=example.com;`

> [!NOTE]
> Authentication-Results ヘッダーの詳細については、「RFC 7001 ([メッセージ認証状態を示すメッセージ ヘッダー フィールド](https://www.rfc-editor.org/rfc/rfc7001.txt)」を参照してください。 Microsoft の DKIM 実装は、この RFC に準拠しています。

管理者は、DKIM 検証の結果にExchange[メール フロー ルール](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (トランスポート ルールとも呼ばれます) を作成できます。 これらのメール フロー ルールを使用すると、管理者は必要に応じてメッセージをフィルター処理またはルーティングできます。
