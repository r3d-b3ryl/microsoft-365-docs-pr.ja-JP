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
description: EOP と Office 365 が、電子メールの上部に安全のヒントを追加して、スパム、フィッシング、マルウェアの防止によってユーザーを保護する方法について学習します。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c37eba07b306ff47e14640e494e468b63b358726
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166617"
---
# <a name="safety-tips-in-email-messages"></a>電子メール メッセージの安全性に関するヒント

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Exchange Online Protection (EOP) と Microsoft 365 は、スパム、フィッシング、マルウェアの防止によってユーザーを保護します。 現在、これらの攻撃の一部は、正当に見える程度に十分に作成されています。 [迷惑メール] フォルダーへのメッセージの送信では、必ずしも十分ではありません。 Outlook または Outlook on the web または任意の電子メール クライアントでメールを確認すると、EOP は自動的に送信者をチェックし、電子メールの上部に安全のヒントを追加します。

安全のヒントは、安全のヒントが開き、メッセージ本文に直接挿入されるので、使用している Outlook のバージョンには依存されません。 つまり、安全のヒントは、使用している電子メール クライアントに表示されます。 これは電子メール フィルター レベルで実行され、メール クライアント レベルではレンダリングされないので、どのバージョンの Outlook でも表示されるだけでなく、すべての電子メール クライアントにも表示されます。

安全性のヒント (色分けされたメッセージ) は、有害な可能性のあるメッセージについて警告します。 受信トレイ内のほとんどのメッセージには、安全性に関するヒントが表示されません。 EOP と Microsoft 365 にスパム、フィッシング、マルウェア攻撃の防止に必要な情報がある場合にのみ表示されます。 安全のヒントが受信トレイに表示される場合は、次の例を使用して、各種類の安全のヒントの詳細を確認できます。

- 不審なメール (赤い安全性のヒント)。

    ![赤い安全性のヒントを示すスクリーンショット。](../../media/5078a0be-e556-44a1-b169-09d780d26898.png)

    電子メールの赤い安全性のヒントは、受信したメッセージにフィッシング詐欺などの疑わしい情報が含まれていることを意味します。 この種類のメール メッセージは、開かなくても受信トレイから削除することをお勧めします。

- 安全なメール (緑色の安全性のヒント)。

    ![緑色の安全性のヒントを示すスクリーンショット。](../../media/acbc11d0-f626-4848-9fbf-66eeeda3f803.png)

    安全でないメッセージに加えて、信頼できる送信者からの有効なメッセージについて、緑色の安全のヒントも示します。 メールの緑色の安全性のヒントは、メッセージの送信者をチェックし、安全な状態を確認したという意味です。 Microsoft では、この信頼できる差出人の一覧を保持しています。これには、金融機関や、なりすましや偽装が頻繁に行われるその他の送信者が含まれます。

## <a name="working-with-safety-tips"></a>安全に関するヒントを操作する

すべてのメッセージが Outlook on the web を受け取る場合でも、安全のヒントは常に有効になります。 管理者は、Outlook などの他の電子メール クライアントの安全性のヒントをオフにできます。 詳細については、「[Office 365 でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。

EOP がメッセージを分類した方法 (つまり、メッセージがスパムではないか、スパムとしてマークされている必要がある) に同意しない場合は、分析のためにメッセージを Microsoft に送信して、エクスペリエンスを向上できます。 手順については、「メッセージとファイル [を Microsoft に報告する」を参照してください](report-junk-email-messages-to-microsoft.md)。 また、安全に関するヒントの [フィードバック] リンクをクリックして、改善に役立つコメントを直接 Microsoft に送信することもできます。
