---
title: Backscatter and EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: この記事では、バック散布と Microsoft Exchange Online Protection (EOP) について説明します。
ms.openlocfilehash: 14460b75920b053461722b5a129d785fb6952a5a
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035594"
---
# <a name="backscatter-and-eop"></a>Backscatter and EOP

*Backscatter*は、送信していないメッセージに対して受信する配信不能レポート (ndr またはバウンスメッセージとも呼ばれます) です。 スパム発信者 (なりすまし) は、メッセージの宛先アドレスであり、多くの場合、実際の電子メールアドレスを使用してメッセージに信頼を貸します。 そのため、スパム送信者が、存在しない受信者にメッセージを送信した (スパムは大量の操作である) 場合、送信先の電子メールサーバーは本質的に、NDR 内の配信不能メッセージを From: アドレスの偽造された送信者に返すようになります。

Exchange Online Protection (EOP) は、NDR を生成せずに、不審なソースからのメッセージを特定して暗黙的に削除することをすべての努力を行います。 しかし、サービスを通過する膨大なボリュームの電子メールに基づいて、EOP が誤って backscatter を送信する可能性は常にあります。

Backscatterer.org は、backscatter の送信を担当するメールサーバーのブロックリスト (DNS ブロック一覧または DNSBL とも呼ばれます) を維持します。このリストには、EOP サーバーが表示されることがあります。 ただし、スパムのリストではないので、Backscatterer.org block リストから自分自身を削除しようとしているわけではありません (独自の受付による)。

> [!TIP]
> Backscatter.org web サイト (<http://www.backscatterer.org/?target=usage>) は、サービスを使用して、拒否モードではなく、セーフモードで電子メールをチェックすることをお勧めします (大部分の電子メールサービスでは、ほとんどの場合、何らかの散布が送信されます)。
