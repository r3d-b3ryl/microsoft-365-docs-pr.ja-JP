---
title: 電子メール保護の順序と優先順位
keywords: セキュリティ, マルウェア, Microsoft 365, M365, セキュリティ センター, Microsoft 365 Defender ポータル, Microsoft Defender for Endpoint, Microsoft Defender for Office 365,Microsoft Defender for Identity
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理者は、Exchange Online Protection (EOP) の保護のアプリケーションの順序と、保護ポリシーの優先度の値が適用されるポリシーを決定する方法について学習できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1debec0d2f8ca1498fd674f3d5a2d5a4681196eb
ms.sourcegitcommit: b3530441288b2bc44342e00e9025a49721796903
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/20/2022
ms.locfileid: "63679788"
---
# <a name="order-and-precedence-of-email-protection"></a>電子メール保護の順序と優先順位

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Exchange Onlineまたはスタンドアロン Exchange Online Protection (EOP) 組織にメールボックスを含むMicrosoft 365組織では、Exchange Onlineメールボックスがない場合、受信電子メールに複数の保護の形式でフラグが設定される場合があります。 たとえば、EOP の組み込みのフィッシング対策ポリシーは、すべてのMicrosoft 365顧客が利用でき、Microsoft Defender for Office 365顧客が使用できるより堅牢なフィッシング対策ポリシーです。 メッセージは、マルウェア、スパム、フィッシングなどの複数の検出スキャンも通過します。このすべてのアクティビティを考えると、どのポリシーが適用されているかに関して混乱が生じる可能性があります。

一般に、メッセージに適用されるポリシーは、**CAT (Category)** プロパティの **X-Forefront-Antispam-Report** ヘッダーで識別されます。 詳細については、「[スパム対策メッセージ ヘッダー](anti-spam-message-headers.md)」を参照してください。

メッセージに適用されるポリシーを決定する主な要因は 2 つあります。

- **電子メール保護の種類の優先順位**: この順序は構成できません。次の表に説明します。

  |優先度|電子メール保護|カテゴリ|管理する場所|
  |---|---|---|---|
  |1|マルウェア|CAT:MALW|[EOP のマルウェア対策ポリシーを構成する](configure-anti-malware-policies.md)|
  |2|フィッシング|CAT:PHSH|[EOP でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)|
  |3|高確度スパム|CAT:HSPM|[EOP でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)|
  |4|スプーフィング|CAT:SPOOF|詳細については、「[EOP のスプーフィング インテリジェンス分析](learn-about-spoof-intelligence.md)」を参照してください。|
  |5<sup>\*</sup>|ユーザー権限借用 (保護されたユーザー)|UIMP|[詳細については、「Microsoft Defender for Office 365 のフィッシング対策ポリシーを構成する」を参照してください。](configure-mdo-anti-phishing-policies.md)|
  |6<sup>\*</sup>|ドメインの偽装 (保護されたドメイン)|DIMP|[詳細については、「Microsoft Defender for Office 365 のフィッシング対策ポリシーを構成する」を参照してください。](configure-mdo-anti-phishing-policies.md)|
  |7 |スパム|CAT:SPM|[EOP でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)|
  |8 |バルク|CAT:BULK|[EOP でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)|

  <sup>\*</sup>これらの機能は、Microsoft Defender for Office 365のフィッシング対策ポリシーでのみ使用できます。

- **ポリシーの優先度**: ポリシーの種類 (スパム対策、マルウェア対策、フィッシング詐欺対策など) ごとに、すべてのユーザーに適用される既定のポリシーがありますが、特定のユーザーに適用されるカスタム ポリシーを作成できます。 各カスタム ポリシーには、ポリシーが適用される順序を決定する優先度の値があります。 既定のポリシーは常に最後に適用されます。

  > [!IMPORTANT]
  > ユーザーが同じ種類の複数のポリシーで定義されている場合は、優先度が最も高いポリシーのみが適用されます。 その種類の残りのポリシーは、(既定のポリシーを含む) ユーザーに対して評価されません。

たとえば、**同じユーザーに適用される** Microsoft Defender for Office 365の次のフィッシング対策ポリシーと、ユーザーの偽装とスプーフィングの両方として識別されるメッセージについて考えてみましょう。

|ポリシー名|優先度|ユーザー偽装|スプーフィング対策|
|---|---|---|---|
|ポリシー A|1|オン|オフ|
|ポリシー B|2|オフ|オン|

1. スプーフィングはユーザー偽装 (5) よりも優先順位が高いため、メッセージはスプーフィングとしてマークされ、扱われます。
2. ポリシー A はポリシー B よりも優先度が高いため、ユーザーに適用されます。
3. ポリシー A の設定に基づいて、ポリシーでスプーフィング対策がオフになっているため、メッセージに対してアクションは実行されません。
4. ポリシー処理が停止するため、ポリシー B はユーザーに適用されません。

同じユーザーが同じ種類の複数のカスタム ポリシーに意図的または意図せずに含まれている可能性があるため、カスタム ポリシーには次の設計ガイドラインを使用します。

- 少数のユーザーに適用されるポリシーに高い優先度を割り当て、多数のユーザーに適用されるポリシーに優先順位を低くします。 既定のポリシーは常に最後に適用されます。
- 優先度の高いポリシーを構成して、優先度の低いポリシーよりも厳密な設定またはより特殊な設定を行います。
- より少ないカスタム ポリシーの使用を検討してください (より厳密な、またはより特殊な設定を必要とするユーザーに対してのみカスタム ポリシーを使用します)。
