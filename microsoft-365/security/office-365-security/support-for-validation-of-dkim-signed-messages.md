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
description: Exchange Online Protection と Exchange Online での DKIM 署名済みメッセージの検証について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9da41cc7918b36e1aa6a4a8cc48aea6cd2a865c6
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290263"
---
# <a name="support-for-validation-of-dkim-signed-messages"></a>DKIM 署名付きメッセージの検証をサポートする

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Exchange Online Protection (EOP) と Exchange Online はどちらも、ドメイン キー識別メール[(DKIM)](https://www.rfc-editor.org/rfc/rfc6376.txt)メッセージの受信検証をサポートしています。

DKIM は、電子メール メッセージが他のユーザーによってスプーフィングされたのではないと検証し、それが送信されたと言うドメインから送信されたと検証します。 電子メール メッセージを送信した組織に関連付けします。 DKIM 検証は、IPv6 と一緒に送信される全メッセージに対して自動的に使用されます。 Microsoft 365 は、IPv4 を使用してメールが送信される場合にも DKIM をサポートします。 (IPv6 サポートの詳細については、「IPv6 を使用した匿名受信電子メール メッセージ [の](support-for-anonymous-inbound-email-messages-over-ipv6.md)サポート」を参照してください)。

DKIM は、メッセージ ヘッダーの DKIM-Signatureに表示されるデジタル署名されたメッセージを検証します。 検証の結果DKIM-SignatureヘッダーにスタンプAuthentication-Resultsされます。 メッセージ ヘッダー テキストは次のように表示されます (contoso.com が送信者です)。

 `Authentication-Results: <contoso.com>; dkim=pass (signature was verified) header.d=example.com;`

> [!NOTE]
> このヘッダーの詳細についてはAuthentication-Results RFC 7001 ( Message[Header Field for Indicating Message Authentication Status](https://www.rfc-editor.org/rfc/rfc7001.txt). Microsoft の DKIM 実装は、この RFC に準拠しています。

管理者は、DKIM 検証の結果 [に対](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) して Exchange メール フロー ルール (トランスポート ルールとも呼ばれる) を作成できます。 これらのメール フロー ルールを使用すると、管理者は必要に応じてメッセージをフィルター処理またはルーティングできます。
