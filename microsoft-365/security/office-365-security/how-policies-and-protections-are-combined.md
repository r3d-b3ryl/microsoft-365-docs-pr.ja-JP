---
title: 電子メール保護の順序と優先順位
keywords: セキュリティ、マルウェア、Microsoft 365、M365、セキュリティ センター、Microsoft 365 Defender ポータル、Microsoft Defender for Endpoint、Microsoft Defender for Office 365、Microsoft Defender for Identity
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理者は、Exchange Online Protection (EOP) の保護のアプリケーションの順序と、保護ポリシーの優先度の値によって適用されるポリシーがどのように決定されるのかについて説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9dea01324e37a56fbff049e4e46cd5882f1fabad
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59164670"
---
# <a name="order-and-precedence-of-email-protection"></a>電子メール保護の順序と優先順位

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Microsoft 365 Exchange Online またはスタンドアロン Exchange Online Protection (EOP) 組織に Exchange Online メールボックスがない組織では、受信メールに複数の形式の保護のフラグが設定される場合があります。 たとえば、すべての Microsoft 365 のお客様が利用できる EOP の組み込みのフィッシング対策ポリシー、および Office 365 のお客様に対して Microsoft Defender が利用できるより堅牢なフィッシング対策ポリシーを示します。 メッセージは、マルウェア、スパム、フィッシングなどの複数の検出スキャンも通過します。このすべてのアクティビティを考えると、どのポリシーが適用されるのかという混乱が生じる可能性があります。

一般に、メッセージに適用されるポリシーは **、CAT (Category)** プロパティの **X-Forefront-Antispam-Report** ヘッダーで識別されます。 詳細については、「[スパム対策メッセージ ヘッダー](anti-spam-message-headers.md)」を参照してください。

メッセージに適用されるポリシーを決定する主な要因は次の 2 つがあります。

- **電子メール保護の種類の優先度**: この順序は構成できません。次の表で説明します。

  <br>

  ****

  |優先度|電子メールの保護|カテゴリ|管理する場所|
  |---|---|---|---|
  |1|マルウェア|CAT:MALW|[EOP でマルウェア対策ポリシーを構成する](configure-anti-malware-policies.md)|
  |2|フィッシング|CAT:PHSH|[EOP でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)|
  |3|高確度スパム|CAT:HSPM|[EOP でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)|
  |4 |スプーフィング|CAT:スプーフィング|[EOP でのスプーフィング インテリジェンスの分析情報](learn-about-spoof-intelligence.md)|
  |5<sup>\*</sup>|ユーザー偽装 (保護されたユーザー)|UIMP|[Microsoft Defender でフィッシング対策ポリシーを構成Office 365](configure-mdo-anti-phishing-policies.md)|
  |6<sup>\*</sup>|ドメイン偽装 (保護されたドメイン)|DIMP|[Microsoft Defender でフィッシング対策ポリシーを構成Office 365](configure-mdo-anti-phishing-policies.md)|
  |7 |スパム|CAT:SPM|[EOP でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)|
  |8 |バルク|CAT:BULK|[EOP でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)|
  |

  <sup>\*</sup>これらの機能は、Microsoft Defender のフィッシング対策ポリシーでのみOffice 365。

- **ポリシー** の優先度 : ポリシーの種類 (スパム対策、マルウェア対策、フィッシング対策など) ごとに、すべてのユーザーに適用される既定のポリシーがありますが、特定のユーザーに適用されるカスタム ポリシーを作成できます。 各カスタム ポリシーには、ポリシーが適用される順序を決定する優先度の値があります。 既定のポリシーは常に最後に適用されます。

  > [!IMPORTANT]
  > ユーザーが同じ種類の複数のポリシーで定義されている場合、優先度が最も高いポリシーだけが適用されます。 その種類の残りのポリシーは、ユーザーに対して評価されません (既定のポリシーを含む)。

たとえば、同じユーザーに適用される Office 365 の Microsoft Defender の次のフィッシング対策ポリシーと、ユーザー偽装とスプーフィングの両方として識別されるメッセージを検討します。

<br>

****

|ポリシー名|優先度|ユーザー偽装|スプーフィング対策|
|---|---|---|---|
|ポリシー A|1|オン|オフ|
|ポリシー B|2|オフ|オン|
|

1. スプーフィングの優先度がユーザー偽装 (5) よりも高い (4) ため、メッセージはスプーフィングとしてマークされ、処理されます。
2. ポリシー A はポリシー B よりも優先度が高いので、ユーザーに適用されます。
3. ポリシー A の設定に基づいて、ポリシーでスプーフィング対策がオフになっているため、メッセージに対してアクションは実行されません。
4. ポリシー処理が停止し、ポリシー B はユーザーに適用されません。

同じユーザーが意図的または意図せずに同じ種類の複数のカスタム ポリシーに含まれている可能性がある場合は、カスタム ポリシーに次の設計ガイドラインを使用します。

- 少人数のユーザーに適用されるポリシーに高い優先度を割り当て、多数のユーザーに適用されるポリシーに対する優先度を低くします。 既定のポリシーは常に最後に適用されます。
- 優先度の高いポリシーを構成して、優先度の低いポリシーよりも厳密な設定またはより特殊な設定を設定します。
- 使用するカスタム ポリシーの数を少なくします (より厳密な設定またはより特殊な設定が必要なユーザーに対してカスタム ポリシーのみを使用してください)。
