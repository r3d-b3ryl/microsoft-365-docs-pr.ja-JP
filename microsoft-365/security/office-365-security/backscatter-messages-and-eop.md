---
title: EOP のバックスキャッター
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: この記事では、バックスcatter と Microsoft Exchange Online Protection (EOP) について学習します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3cdc556a8cc193466d150fc82298796779841cca
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165957"
---
# <a name="backscatter-in-eop"></a>EOP のバックスキャッター

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

*バックスカター* は、送信しなかったメッセージに対して受信する配信以外のレポート (NDRs またはバウンス メッセージとも呼ばれる) です。 スパム送信者は、メッセージの From: アドレスを偽造 (なりすまし) し、多くの場合、実際の電子メール アドレスを使用してメッセージに信用を与えます。 そのため、スパム送信者が存在しない受信者に必ずメッセージを送信する場合 (スパムは高ボリュームの操作です)、送信先の電子メール サーバーは基本的に、NDR 内の配信不能なメッセージを差出人: アドレスの偽造された送信者に返すようだまされます。

Exchange Online または Exchange Online メールボックスのないスタンドアロンの Exchange Online Protection (EOP) 組織にメールボックスがある Microsoft 365 組織では、EOP は NDR を生成せずに、疑わしいソースからのメッセージを識別してサイレント ドロップするあらゆる努力を行います。 ただし、サービスを通過するボリューム メールの量の多いメールに基づいて、EOP が意図せずにバックスカターを送信する可能性は常にあります。

Backscatterer.orgバックスカターの送信を担当する電子メール サーバーのブロック リスト (DNS ブロック リストまたは DNSBL とも呼ばれる) が保持され、EOP サーバーがこの一覧に表示される場合があります。 ただし、Backscatterer.org ブロック リストはスパム送信者の一覧 (独自の受付により) ではないので、削除は試みなされません。

> [!TIP]
> Backscatter.org Web サイト ( ) では、拒否モードではなくセーフ モードで受信メールをチェックするためにサービスを使用することを推奨しています (大きなメール サービスは、ほとんど常にバック <http://www.backscatterer.org/?target=usage> スカターを送信します)。
