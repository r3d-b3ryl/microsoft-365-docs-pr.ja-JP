---
title: 迷惑メールとバルク メールの違い
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: 8079f193-1b40-4081-9e5d-d0e50dfbcc59
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理者は、Exchange Online Protection (EOP) の迷惑メール (スパム) と一括メール (灰色のメール) の違いについて学習できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: dd876b522a0d565b84e8bb9043e277cd3bc34495
ms.sourcegitcommit: 61bdfa84f2d6ce0b61ba5df39dcde58df6b3b59d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2022
ms.locfileid: "65940450"
---
# <a name="whats-the-difference-between-junk-email-and-bulk-email-in-eop"></a>EOP での迷惑メールと一括メールの違いは何ですか?

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Exchange Online のメールボックスを持つ Microsoft 365 組織、または Exchange Online メールボックスのないスタンドアロンの Exchange Online Protection (EOP) 組織では、"迷惑メールと一括メールの違いは何ですか? このトピックでは、その違いと、EOP で使用できるコントロールについて説明します。

- **迷惑メール** はスパムです。これは、迷惑なメッセージで、普遍的に必要とされないメッセージ (正常に識別される) です。 既定では、EOP は、ソースメールサーバーの評価に基づいてスパムを拒否します。 メッセージが送信元 IP の検査を通過した場合は、スパムフィルタリングに送信されます。 迷惑メールフィルターによってメッセージがスパムとして分類された場合、メッセージは (既定では) 対象の受信者に配信されて、[迷惑メール] フォルダーに移動します。

  - 迷惑メールフィルター の判定を実行するアクションを構成できます。 手順については、「 [EOP でスパム対策ポリシーを構成する](configure-your-spam-filter-policies.md)」を参照してください。

  - また、スパム分類の判定に同意できない場合は、「[メッセージとファイルを Microsoft に報告する](report-junk-email-messages-to-microsoft.md)」に記載されているように、いくつかの方法でスパムまたは非スパムであると思われるメッセージを Microsoft に報告することができます。

- **バルクメール** (_グレーメール_ としても知られています) は、もう少し分類が困難です。 迷惑メールは常に脅威であるのに対し、多くの場合、バルクメールは1回限りの広告、またはマーケティングメッセージです。 バルクメールメッセージを必要としている (実際に、あえてサインアップしてバルクメールを受信する）ユーザもいます。一方、バルクメールをスパムだと感じるユーザもいます。 たとえば、一部のユーザーは Contoso Corporation からの広告メールまたは次回のサイバー セキュリティに関するカンファレンスの招待状を受信したいと思っているのに対して、その他のユーザーはこれらのメッセージをスパムと見なしている場合です。

  一括メールの識別方法の詳細については、 [EOP の一括苦情レベル (BCL) に](bulk-complaint-level-values.md)関するページを参照してください。

## <a name="how-to-manage-bulk-email"></a>バルク メールの管理方法

バルクメールへの反応が多様であるため、すべての組織に適用される汎用的なガイダンスはありません。

スパム対策ポリシーには、バルクメールを迷惑メールとして識別するために使用される既定の BCL しきい値があります。 管理者はしきい値を増減できます。 詳細については、次のトピックをご覧ください。

- [EOP でスパム対策ポリシーを構成します](configure-your-spam-filter-policies.md)。

- 「[EOP のスパム対策ポリシーの設定](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings)」

見落としがちなもう１つの対策オプションとして、ユーザーがバルクメールを受信することについて苦情をしていても、スパムフィルタリングを通過する信頼できる送信者からのメッセージを EOP にしている場合は、ユーザーはバルクメールのメッセージに配信停止オプションがあるかどうかを確認するようにしてください。
