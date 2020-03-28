---
title: 迷惑メールとバルク メールの違い
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
ms.assetid: 8079f193-1b40-4081-9e5d-d0e50dfbcc59
ms.collection:
- M365-security-compliance
description: このトピックでは、迷惑メール (スパム) とバルクメールの違い、および Office 365 の関連するコントロールについて説明します。
ms.openlocfilehash: 56e997235a374ee9f56956be96458b46bffcdc21
ms.sourcegitcommit: d00efe6010185559e742304b55fa2d07127268fa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2020
ms.locfileid: "43033628"
---
# <a name="whats-the-difference-between-junk-email-and-bulk-email"></a>迷惑メールとバルク メールの違い

Office 365 exchange online またはスタンドアロン Exchange Online Protection (EOP) のお客様が Exchange online メールボックスを使用していない場合は、「迷惑メールとバルクメールの違いは何ですか」という質問があります。 このトピックでは、EOP で使用できるコントロールとその違いについて説明します。

- **迷惑メール**とは、迷惑メールで、未承諾のメッセージ (正しく識別された場合) をいいます。 既定では、EOP は、送信元の電子メールサーバーの評価に基づいてスパムを拒否します。 メッセージが送信元 IP 検査に合格した場合は、スパムフィルタリングに送信されます。 メッセージがスパムフィルター処理によってスパムとして分類されている場合、メッセージは (既定では) 目的の受信者に配信され、その迷惑メールフォルダーに移動されます。

  - スパムフィルタリング verdicts に対して実行するアクションを構成できます。 手順については、「 [Office 365 でスパム対策ポリシーを構成する](configure-your-spam-filter-policies.md)」を参照してください。

  - スパムフィルター verdict を使用していない場合は、「[レポートメッセージとファイル](report-junk-email-messages-to-microsoft.md)」で説明されているように、スパムとして、または迷惑メールではないと思われるメッセージをいくつかの方法で報告することができます。

- **バルクメール**(_灰色のメール_とも呼ばれます) では、分類がより困難です。 スパムは常に脅威ですが、バルクメールは1回限りの広告またはマーケティングメッセージであることがよくあります。 ユーザーによっては、バルクメールメッセージを必要としており (実際には、それらを受信するように故意にサインアップしている)、他のユーザーはバルクメールをスパムと考えています。 たとえば、一部のユーザーは、Contoso Corporation からの広告メッセージや、サイバーセキュリティに関する今後の会議への招待を受信したいと考えていますが、他のユーザーはこれらの同じメッセージをスパムと考えています。

  バルクメールを識別する方法の詳細については、「 [Office 365 のバルク苦情レベル (BCL)](bulk-complaint-level-values.md)」を参照してください。

## <a name="how-to-manage-bulk-email"></a>バルク メールの管理方法

バルクメールには反力が混在しているため、すべての組織に適用される一般的なガイダンスはありません。

スパム対策ポリシーには、バルクメールをスパムとして識別するために使用される既定の BCL しきい値があります。 管理者は、しきい値を増減できます。 詳細については、次のトピックをご覧ください。

- [Office 365 でスパム対策ポリシーを構成](configure-your-spam-filter-policies.md)します。

- [EOP スパム対策ポリシーの設定](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)

ユーザーがバルクメールの受信について苦情を受けているのに、EOP でスパムフィルター処理を通過する、よく知られた送信者からのメッセージであるという、見落としやすいもう1つのオプションは、ユーザーが一括メールメッセージの登録解除オプションを確認する必要がある場合です。
