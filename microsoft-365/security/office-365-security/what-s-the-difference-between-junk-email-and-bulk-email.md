---
title: 迷惑 &apos; メールとバルク メールの違いは何ですか?
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
ms.assetid: 8079f193-1b40-4081-9e5d-d0e50dfbcc59
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理者は、Exchange Online Protection (EOP) の迷惑メール (スパム) とバルク メール (グレー メール) の違いについて学習できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c656ed1807b451ae03ecfeb0f220f5d7b902c7ac
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290647"
---
# <a name="whats-the-difference-between-junk-email-and-bulk-email-in-eop"></a>EOP での迷惑メールとバルク メールの違いは何ですか?

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Exchange Online または Exchange Online メールボックスのないスタンドアロンの Exchange Online Protection (EOP) 組織にメールボックスがある Microsoft 365 組織では、"迷惑メールとバルク メールの違いは何ですか?" という質問を受け取る場合があります。 このトピックでは、その違いと、EOP で使用できるコントロールについて説明します。

- **迷惑メール** はスパムです。これは、迷惑なメッセージで、普遍的に必要とされないメッセージ (正常に識別される) です。 既定では、EOP は、ソースメールサーバーの評価に基づいてスパムを拒否します。 メッセージが送信元 IP の検査を通過した場合は、スパムフィルタリングに送信されます。 迷惑メールフィルターによってメッセージがスパムとして分類された場合、メッセージは (既定では) 対象の受信者に配信されて、[迷惑メール] フォルダーに移動します。

  - 迷惑メールフィルター の判定を実行するアクションを構成できます。 手順については [、「EOP でスパム対策ポリシーを構成する」を参照してください](configure-your-spam-filter-policies.md)。

  - また、スパム分類の判定に同意できない場合は、「[メッセージとファイルを Microsoft に報告する](report-junk-email-messages-to-microsoft.md)」に記載されているように、いくつかの方法でスパムまたは非スパムであると思われるメッセージを Microsoft に報告することができます。

- **バルクメール** (_グレーメール_ としても知られています) は、もう少し分類が困難です。 迷惑メールは常に脅威であるのに対し、多くの場合、バルクメールは1回限りの広告、またはマーケティングメッセージです。 バルクメールメッセージを必要としている (実際に、あえてサインアップしてバルクメールを受信する）ユーザもいます。一方、バルクメールをスパムだと感じるユーザもいます。 たとえば、一部のユーザーは Contoso Corporation からの広告メールまたは次回のサイバー セキュリティに関するカンファレンスの招待状を受信したいと思っているのに対して、その他のユーザーはこれらのメッセージをスパムと見なしている場合です。

  バルク メールの識別方法の詳細については、EOP の「バルク苦情レベル [(BCL)」を参照してください](bulk-complaint-level-values.md)。

## <a name="how-to-manage-bulk-email"></a>バルク メールの管理方法

バルクメールへの反応が多様であるため、すべての組織に適用される汎用的なガイダンスはありません。

スパム対策ポリシーには、バルクメールを迷惑メールとして識別するために使用される既定の BCL しきい値があります。 管理者はしきい値を増減できます。 詳細については、次のトピックをご覧ください。

- [EOP でスパム対策ポリシーを構成します](configure-your-spam-filter-policies.md)。

- 「[EOP のスパム対策ポリシーの設定](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)」

見落としがちなもう１つの対策オプションとして、ユーザーがバルクメールを受信することについて苦情をしていても、スパムフィルタリングを通過する信頼できる送信者からのメッセージを EOP にしている場合は、ユーザーはバルクメールのメッセージに配信停止オプションがあるかどうかを確認するようにしてください。
