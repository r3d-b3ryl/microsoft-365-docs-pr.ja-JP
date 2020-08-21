---
title: メール保護の順序と優先順位
keywords: セキュリティ、マルウェア、Microsoft 365、M365、セキュリティ センター、ATP、Microsoft Defender ATP、Office 365 ATP、Azure ATP
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
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理者は、Exchange Online Protection (EOP) における保護のアプリケーションの順序について学習できます。また、保護ポリシーの優先順位の値で、どのポリシーが適用されるかがどのように決定されるかについて学習できます。
ms.openlocfilehash: 9556d2262eb59224357e20027a1f0e63404081f2
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827411"
---
# <a name="order-and-precedence-of-email-protection"></a>メール保護の順序と優先順位

Exchange Online にメールボックスがある Microsoft 365 組織や、Exchange Online のメールボックスを使用しないスタンドアロン Exchange Online Protection (EOP) 組織では、受信電子メールに複数の保護が設定される場合があります。 たとえば、組み込みの EOP フィッシング対策ポリシー (すべての Microsoft 365 ユーザーが利用可能) と、より堅牢な ATP フィッシング対策ポリシー (Office 365 Advanced Threat Protection (Office 365 ATP) ユーザーも利用できます。 また、メッセージはマルウェア、スパム、フィッシングなどについて複数の検出スキャンにパスします。このアクティビティをすべて完了すると、どのポリシーが適用されるかについて、多く問題が発生する可能性があります。

通常、メッセージに適用されるポリシーは **、X-Forefront-Antispam-Report** ヘッダーの **CAT (Category) プロパティで特定** できます。 詳細については、「[スパム対策メッセージ ヘッダー](anti-spam-message-headers.md)」を参照してください。

メッセージに適用されるポリシーを決定する主な要因は 2 つです。

- **電子メール保護タイプの優先度**: この順序は構成できません。次の表に、その順序を示します。

  ****

  |優先度|電子メール保護|カテゴリ|管理する場所|
  |---|---|---|---|
  |1 |マルウェア|CAT:MALW|[EOP でマルウェア対策ポリシーを構成する](configure-anti-malware-policies.md)|
  |2 |フィッシング|CAT:PHSH|[EOP でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)|
  |3 |高確度スパム|CAT:HSPM|[EOP でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)|
  |4 |スプーフィング|CAT:SPOOF|[EOP でスプーフィング インテリジェンスを構成する](learn-about-spoof-intelligence.md)|
  |5 |スパム|CAT:SPM|[EOP でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)|
  |6 |バルク|CAT:BULK|[EOP でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)|
  |7<sup>\*</sup>|ドメイン偽装 (保護されたユーザー)|DIMP|[ATP フィッシング詐欺対策ポリシーを設定する](configure-atp-anti-phishing-policies.md)|
  |8<sup>\*</sup>|ユーザー偽装 (保護されたドメイン)|UIMP|[ATP フィッシング詐欺対策ポリシーを設定する](configure-atp-anti-phishing-policies.md)|
  |

  <sup>\*</sup> これらの機能は、ATP フィッシング対策ポリシーでのみ使用可能です。

- **ポリシーの優先度**: 各保護の種類 (スパム対策、マルウェア対策、フィッシング対策など) ごとに、すべてのユーザーに適用される既定のポリシーが用意されていますが、特定のユーザーに適用されるカスタム ポリシーを作成することができます。 各カスタム ポリシーには、ポリシーの適用順序を決定する優先順位の値があります。 既定のポリシーは、常に最後に適用されます。

  ユーザーが同じ種類の複数のポリシーで定義されている場合は、最も優先度の高いポリシーのみがポリシーに適用されます。 その種類の残りのポリシーはユーザーには評価されません (既定のポリシーを含む)。

たとえば、同じユーザーに適用される次の ATP フィ**that apply to the same users**ッシング対策ポリシーと、ユーザー偽装およびスプーフィングとして識別されるメッセージについて検討します。

  ****

  |ATP フィッシング対策ポリシー|優先度|ユーザー偽装|スプーフィング対策|
  |---|---|---|---|
  |ポリシー A|1 |オン|オフ|
  |ポリシー B|2 |オフ|オン|
  |

1. スプーフィングはユーザー偽装より優先度が高い (4) ため、メッセージはスプーフィングとしてマークおよび処理されます。
2. ポリシー B よりも高い優先順位を持つポリシー A がユーザーに適用されます。
3. ポリシー A の設定に基づいて、ポリシーでスプーフィング対策がオフになっているため、メッセージに対してアクションは実行されません。
4. ポリシーの処理が停止されるため、ポリシー B はユーザーに一度も適用されません。

同じユーザーが、同じ種類の複数のカスタム ポリシーに意図的または意図的に含まれている可能性があるため、カスタム ポリシーに関しては以下の設計ガイドラインに従ってください。

- 割り当てる優先度を割り当てるには、ユーザーの数を小さくし、多数のユーザーに適用するポリシーには低い優先度を割り当てます。 既定のポリシーは常に最後に適用されますので注意してください。
- 優先度の高いポリシーを、優先度の低いポリシーよりも厳密かつ特殊な設定を設定する構成。
- より少ないカスタム ポリシーの使用を検討します (より高くてすみ、またはより高い特殊な設定が必要なユーザーに対してのみカスタム ポリシーを使用します)。
