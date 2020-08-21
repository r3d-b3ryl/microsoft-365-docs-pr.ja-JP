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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: この記事では、バックスキャターと保護 (EOP) Microsoft Exchange Online について説明します。
ms.openlocfilehash: f1705fd7fc30c9a8cde5f6acfaf145861de3af08
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827787"
---
# <a name="backscatter-in-eop"></a>EOP のバックスキャッター

*バックスキャターは* 、送信していないメッセージに対して受信した配信不能レポート (NDR またはバウンス メッセージとも呼ばれる) です。 スパム送信者は、メッセージの From: アドレスを偽の対象として偽のメール アドレスを偽用 (なりすまし) 代わりとして使用します。多くの場合、実際のメール アドレスは、メッセージに対する分かりにくい状態のためです。 したがって、スパム送信者が存在しない受信者に間でメッセージを送信すると (スパムは大量の操作)、送信先メール サーバーは基本的に、NDR 内の配信不可能なメッセージが From: アドレスの差出人に返されるのを試みます。

Exchange Online にメールボックスを含む Microsoft 365 組織や、Exchange Online メールボックスを使用しないスタンドアロン Exchange Online Protection (EOP) 組織では、EOP はすべての取り組みを行い、NDR を生成することなく、その不正な送信元からのメッセージを自動的に識別して通知なしに削除します。 しかし、サービスを介した流れを経由するボリュームの電子メールに基づいて、EOP が意図しないバックスキャターを送信する可能性は常に存在します。

Backscatterer.orgはバックスキャターの送信を行う電子メール サーバーの禁止一覧 (DNS 禁止リストまたは DNSBL とも呼ばれる) を維持し、この一覧に EOP サーバーが表示される可能性があります。 しかし、Backscatterer.org のブロック リストから (独自の導入によって) そのものを削除しようとはしません。

> [!TIP]
> 大Backscatter.org Web サイト <http://www.backscatterer.org/?target=usage> () は、受信メールを拒否モードではなくセーフ モードで確認するようにお勧めします (大きなメール サービスでは、ほぼ常にバックスキャターが送信されます)。
