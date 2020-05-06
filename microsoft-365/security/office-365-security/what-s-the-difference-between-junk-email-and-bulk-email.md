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
ms.custom:
- seo-marvel-apr2020
description: 迷惑 & バルクメールの違いについて説明します。 また、exchange online & Exchange Online Protection (EOP) で使用できるさまざまなオプションについても説明します。
ms.openlocfilehash: 5d9d3b513de64d2a150d9e0a1c94bc5ca746b617
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "44036598"
---
# <a name="whats-the-difference-between-junk-email-and-bulk-email"></a>迷惑メールとバルク メールの違い

メールボックスが Exchange Online またはスタンドアロン Exchange online Protection (EOP) のお客様に Exchange Online メールボックスを使用していない場合は、「迷惑メールとバルクメールの違い」を確認してください。365 このトピックでは、その違いと、EOP で使用できるコントロールについて説明します。

- **迷惑メール** はスパムです。これは、迷惑なメッセージで、普遍的に必要とされないメッセージ (正常に識別される) です。 既定では、EOP は、ソースメールサーバーの評価に基づいてスパムを拒否します。 メッセージが送信元 IP の検査を通過した場合は、スパムフィルタリングに送信されます。 迷惑メールフィルターによってメッセージがスパムとして分類された場合、メッセージは (既定では) 対象の受信者に配信されて、[迷惑メール] フォルダーに移動します。

  - 迷惑メールフィルター の判定を実行するアクションを構成できます。 手順については、「[Office 365 でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。

  - また、スパム分類の判定に同意できない場合は、「[メッセージとファイルを Microsoft に報告する](report-junk-email-messages-to-microsoft.md)」に記載されているように、いくつかの方法でスパムまたは非スパムであると思われるメッセージを Microsoft に報告することができます。

- **バルクメール** (_グレーメール_としても知られています) は、もう少し分類が困難です。 迷惑メールは常に脅威であるのに対し、多くの場合、バルクメールは1回限りの広告、またはマーケティングメッセージです。 バルクメールメッセージを必要としている (実際に、あえてサインアップしてバルクメールを受信する）ユーザもいます。一方、バルクメールをスパムだと感じるユーザもいます。 たとえば、一部のユーザーは Contoso Corporation からの広告メールまたは次回のサイバー セキュリティに関するカンファレンスの招待状を受信したいと思っているのに対して、その他のユーザーはこれらのメッセージをスパムと見なしている場合です。

  バルクメールを特定する方法の詳細については、「[Office365 のバルク通知レベル (BCL)](bulk-complaint-level-values.md)」をご覧ください。

## <a name="how-to-manage-bulk-email"></a>バルク メールの管理方法

バルクメールへの反応が多様であるため、すべての組織に適用される汎用的なガイダンスはありません。

スパム対策ポリシーには、バルクメールを迷惑メールとして識別するために使用される既定の BCL しきい値があります。 管理者はしきい値を増減できます。 詳細については、次のトピックをご覧ください。

- 「[Office 365 でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」。

- 「[EOP のスパム対策ポリシーの設定](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)」

見落としがちなもう１つの対策オプションとして、ユーザーがバルクメールを受信することについて苦情をしていても、スパムフィルタリングを通過する信頼できる送信者からのメッセージを EOP にしている場合は、ユーザーはバルクメールのメッセージに配信停止オプションがあるかどうかを確認するようにしてください。
