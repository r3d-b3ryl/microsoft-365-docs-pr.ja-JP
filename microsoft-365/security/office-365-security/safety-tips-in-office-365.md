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
description: 電子メールの上部にメール Office 365を追加して、EOP とメールがスパム、フィッシング、マルウェア安全性のヒント保護する方法について学習します。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 659a83c73b4fef9097aa317332c9951d53b09a33
ms.sourcegitcommit: f000358c01a8006e5749a86b256300ee3a73174c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/24/2021
ms.locfileid: "51994987"
---
# <a name="safety-tips-in-email-messages"></a>電子メール メッセージの安全性に関するヒント

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Exchange Online Protection (EOP) とMicrosoft 365スパム、フィッシング、マルウェア防止で保護します。 今日、これらの攻撃の中には、正当に見える程度に巧妙に作られたものがあります。 迷惑メール フォルダーにメッセージを送信すると、必ずしも十分ではありません。 これで、web または任意のメール クライアントで Outlook または Outlook でメールをチェックすると、EOP は自動的に送信者をチェックし、電子メールの上部に 安全性のヒント を追加します。

Outlook の安全に関するヒントは、安全性のヒント が開いてメッセージ本文に直接挿入されるので、使用している Outlook のバージョンに依存しない。 つまり、ユーザー安全性のヒントメール クライアントに表示されます。 これはメール フィルター レベルで行われ、メール クライアント レベルではレンダリングされません。Outlook の任意のバージョンに表示されるだけでなく、どのメール クライアントにも表示されます。

この安全性のヒント -- 色分けされたメッセージで、有害な可能性のあるメッセージについて警告します。 受信トレイ内のほとんどのメッセージには、安全性のヒント。 EOP とユーザーがスパム、フィッシングMicrosoft 365マルウェア攻撃を防止するために必要な情報を持っている場合にのみ、これらの情報が表示されます。 安全に関するヒントが受信トレイに表示される場合は、次の例を使用して、各種類のセキュリティ 情報の詳細を安全性のヒント。

- 不審なメール (赤い安全性のヒント)。

    ![赤い画像を示す安全性のヒント。](../../media/5078a0be-e556-44a1-b169-09d780d26898.png)

    電子メール安全性のヒント赤いメッセージは、受信したメッセージにフィッシング詐欺などの疑わしい情報が含まれていることを意味します。 この種類の電子メール メッセージは、受信トレイを開かなくても削除することをお勧めします。

- セーフメール (緑色の安全性のヒント)。

    ![緑色の画像を示す安全性のヒント。](../../media/acbc11d0-f626-4848-9fbf-66eeeda3f803.png)

    安全でないメッセージに加えて、信頼できる送信者からの有効なメッセージについて、緑色のメッセージを使用安全性のヒント。 メール内安全性のヒント緑色のメッセージは、メッセージの送信者を確認し、安全な状態を確認したという意味です。 Microsoft は、この信頼できる送信者の一覧を保持しています。これには、金融機関や、頻繁にスプーフィングや偽装が行われるその他の送信者が含まれます。

## <a name="working-with-safety-tips"></a>安全に関するヒントを操作する

管理者は、スパム対策ポリシーで安全に関するヒントをオンまたはオフにできます。 詳細については、「[Office 365 でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。

EOP でメッセージを分類する方法 (つまり、メッセージがスパムではないか、スパムとしてマークされている必要がある) に同意しない場合は、分析のために Microsoft にメッセージを送信して、エクスペリエンスを向上できます。 手順については、「メッセージと [ファイルを Microsoft に報告する」を参照してください](report-junk-email-messages-to-microsoft.md)。 また、Microsoft にコメントを直接送信するには、安全性のヒントの [フィードバック] リンクをクリックして、改善を支援することもできます。
