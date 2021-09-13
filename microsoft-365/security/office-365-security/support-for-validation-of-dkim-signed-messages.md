---
title: ドメイン キー識別メール (DKIM) 署名済みメッセージの検証のサポート
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a4c95148-a00c-4d12-85ed-88520b547d97
ms.collection:
- M365-security-compliance
description: DKIM 署名済みメッセージの検証について、Exchange Online ProtectionおよびExchange Online
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8695e25000390cf6c5d58adf63db1984c873d75b
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59192271"
---
# <a name="support-for-validation-of-dkim-signed-messages"></a>DKIM 署名付きメッセージの検証をサポートする

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Exchange Online Protection (EOP) Exchange Onlineは、ドメイン キー識別メール ([DKIM](https://www.rfc-editor.org/rfc/rfc6376.txt)) メッセージの受信検証をサポートします。

DKIM は、電子メール メッセージが他のユーザーによってスプーフィングされ、それが送信されたと言うドメインから送信されたと検証します。 電子メール メッセージを送信した組織に結び付きます。 DKIM 検証は、IPv6 で送信されるすべてのメッセージに対して自動的に使用されます。 Microsoft 365 IPv4 を使用してメールが送信される場合にも DKIM がサポートされます。 (IPv6 サポートの詳細については [、「IPv6](support-for-anonymous-inbound-email-messages-over-ipv6.md)を使用した匿名受信メール メッセージのサポート」を参照してください。

DKIM は、メッセージ ヘッダーの DKIM-Signatureに表示されるデジタル署名されたメッセージを検証します。 検証の結果はDKIM-SignatureヘッダーにAuthentication-Resultsされます。 メッセージ ヘッダー テキストは次のように表示されます (contoso.com が送信者です)。

 `Authentication-Results: <contoso.com>; dkim=pass (signature was verified) header.d=example.com;`

> [!NOTE]
> ヘッダーの詳細については、「Authentication-Results RFC 7001 ( メッセージ認証の状態を示すメッセージ ヘッダー フィールド」[を参照してください](https://www.rfc-editor.org/rfc/rfc7001.txt)。 Microsoft の DKIM 実装は、この RFC に準拠しています。

管理者は、Exchange[の結果](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)にメール フロー ルール (トランスポート ルールとも呼ばれる) を作成できます。 これらのメール フロー ルールを使用すると、管理者は必要に応じてメッセージをフィルター処理またはルーティングできます。