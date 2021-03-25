---
title: 電子メール メッセージの安全性に関するヒント
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- BCS160
ms.assetid: fb4f8e49-0468-4be2-8fa6-99501f1ad9d5
ms.collection:
- M365-security-compliance
description: EOP と Office 365 が、電子メールの上部に安全ヒントを追加して、スパム、フィッシング、マルウェア対策で保護する方法について学習します。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a1820cab63abbbac09aa60a9c1684f3672882451
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205662"
---
# <a name="safety-tips-in-email-messages"></a>電子メール メッセージの安全性に関するヒント

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Exchange Online Protection (EOP) と Microsoft 365 は、スパム、フィッシング、マルウェア防止でユーザーを保護します。 今日、これらの攻撃の中には、正当に見える程度に巧妙に作られたものがあります。 迷惑メール フォルダーにメッセージを送信すると、必ずしも十分ではありません。 これで、Outlook または Outlook on the web または任意のメール クライアントでメールをチェックすると、EOP は送信者を自動的にチェックし、電子メールの上部に安全ヒントを追加します。

Outlook の安全ヒントは、安全ヒントが開いて、メッセージ本文に直接挿入されるので、使用している Outlook のバージョンに依存しない。 つまり、安全上のヒントは、使用しているメール クライアントに表示されます。 これは、メール フィルター レベルで行われ、メール クライアント レベルではレンダリングされません。したがって、Outlook の任意のバージョンに表示されるだけでなく、すべての電子メール クライアントにも表示されます。

安全上のヒント (色分けされたメッセージ) は、潜在的に有害なメッセージについて警告します。 受信トレイ内のほとんどのメッセージには安全上のヒントが含まれます。 EOP と Microsoft 365 にスパム、フィッシング、マルウェア攻撃の防止に必要な情報がある場合にのみ表示されます。 安全に関するヒントが受信トレイに表示される場合は、次の例を使用して、各種類の安全ヒントの詳細を確認できます。

- 不審なメール (赤い安全ヒント)。

    ![赤い安全ヒントを示すスクリーンショット。](../../media/5078a0be-e556-44a1-b169-09d780d26898.png)

    電子メールの赤い安全上のヒントは、受信したメッセージにフィッシング詐欺などの疑わしい情報が含まれていることを意味します。 この種類の電子メール メッセージは、受信トレイを開かなくても削除することをお勧めします。

- セーフ メール (緑色の安全ヒント)。

    ![緑色の安全ヒントを示すスクリーンショット。](../../media/acbc11d0-f626-4848-9fbf-66eeeda3f803.png)

    安全でないメッセージに加えて、信頼できる送信者からの有効なメッセージについて、緑色の安全上のヒントも提供します。 メールの緑色の安全上のヒントは、メッセージの送信者を確認し、安全な状態を確認したという意味です。 Microsoft は、この信頼できる送信者の一覧を保持しています。これには、金融機関や、頻繁にスプーフィングや偽装が行われるその他の送信者が含まれます。

## <a name="working-with-safety-tips"></a>安全に関するヒントを操作する

安全に関するヒントは、すべてのメッセージが受信されるとは限らなくても、Outlook on the web で常に有効になります。 管理者は、Outlook などの他の電子メール クライアントの安全に関するヒントをオフにできます。 詳細については、「[Office 365 でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。

EOP でメッセージを分類する方法 (つまり、メッセージがスパムではないか、スパムとしてマークされている必要がある) に同意しない場合は、分析のために Microsoft にメッセージを送信して、エクスペリエンスを向上できます。 手順については、「メッセージと [ファイルを Microsoft に報告する」を参照してください](report-junk-email-messages-to-microsoft.md)。 また、安全上のヒントにある [フィードバック] リンクをクリックして、Microsoft にコメントを直接送信して、改善を支援することもできます。
