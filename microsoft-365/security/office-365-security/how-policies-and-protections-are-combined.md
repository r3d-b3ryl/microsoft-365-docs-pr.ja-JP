---
title: 電子メール保護の順序と優先順位
keywords: セキュリティ、マルウェア、Microsoft 365、M365、セキュリティセンター、ATP、Microsoft Defender ATP、Office 365 ATP、Azure ATP
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
description: 管理者は、Exchange Online Protection (EOP) での保護の順序、および保護ポリシーの優先度の値によってどのようなポリシーが適用されるかを調べることができます。
ms.openlocfilehash: 9bff44a0c9964c60f5b8b5c0afdfe6d29ee6da93
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "48843614"
---
# <a name="order-and-precedence-of-email-protection"></a>電子メール保護の順序と優先順位

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Exchange online またはスタンドアロンの exchange Online Protection (EOP) 組織にメールボックスがあり、Exchange online メールボックスを使用していない場合、受信電子メールに複数の形式の保護によるフラグが設定されることがあります。365 たとえば、EOP の組み込みのフィッシング対策ポリシーは、すべての Microsoft 365 ユーザーが利用でき、Microsoft Defender for Office 365 のお客様が利用できる、より堅牢なフィッシング対策ポリシーです。 メッセージも、マルウェア、スパム、フィッシングなどの複数の検出スキャンを通過します。このアクティビティがすべて与えられた場合、どのポリシーが適用されるかについて混乱が生じることがあります。

一般に、メッセージに適用されるポリシーは、 **CAT (Category)** プロパティの **スパム対策** ヘッダー内で識別されます。 詳細については、「[スパム対策メッセージ ヘッダー](anti-spam-message-headers.md)」を参照してください。

メッセージに適用されるポリシーを決定する主な要因は2つあります。

- **電子メール保護の種類の優先度** : この順序は構成できず、次の表に記載されています。

  ****

  |Priority|電子メール保護|カテゴリ|管理対象|
  |---|---|---|---|
  |1-d|マルウェア|CAT: 男性 W|[EOP でマルウェア対策ポリシーを構成する](configure-anti-malware-policies.md)|
  |pbm-2|フィッシング|CAT: PHSH|[EOP でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)|
  |1/3|高確度スパム|CAT: HSPM|[EOP でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)|
  |4 |スプーフィング|CAT: スプーフィング|[EOP でスプーフィングインテリジェンスを構成する](learn-about-spoof-intelligence.md)|
  |5<sup>\*</sup>|ユーザー偽装 (保護されたドメイン)|UIMP|[Office 365 の Microsoft Defender でフィッシング対策ポリシーを構成する](configure-atp-anti-phishing-policies.md)|
  |シックス<sup>\*</sup>|ドメイン偽装 (保護されたユーザー)|DIMP|[Office 365 の Microsoft Defender でフィッシング対策ポリシーを構成する](configure-atp-anti-phishing-policies.md)|
  |7 |スパム|CAT: SPM|[EOP でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)|
  |8 |バルク|CAT: BULK|[EOP でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)|
  |

  <sup>\*</sup> これらの機能は、Microsoft Defender for Office 365 のフィッシング対策ポリシーでのみ利用可能です。

- **ポリシーの優先度** : 各保護の種類 (スパム対策、マルウェア対策、フィッシング詐欺対策など) について、すべてのユーザーに適用される既定のポリシーがありますが、特定のユーザーに適用するカスタムポリシーを作成することもできます。 各カスタムポリシーには、ポリシーが適用される順序を決定する優先順位の値があります。 既定のポリシーは常に最後に適用されます。

  ユーザーが同じ種類の複数のポリシーで定義されている場合、優先度の高いポリシーのみが適用されます。 その種類の残りのポリシーは、ユーザーに対して評価されません (既定のポリシーを含む)。

たとえば、 **同じユーザーに適用される** Microsoft Defender for Office 365 の次のフィッシング対策ポリシーと、ユーザーの偽装とスプーフィングの両方として識別されるメッセージを考えてみます。

  ****

  |[ポリシー名]|Priority|ユーザー偽装|スプーフィング対策|
  |---|---|---|---|
  |ポリシー A|1-d|オン|オフ|
  |ポリシー B|pbm-2|オフ|オン|
  |

1. スプーフィングは、ユーザー偽装 (8) よりも優先度が高いため、メッセージはスプーフィングとしてマークされ、スプーフィングとして扱われます。
2. ポリシー A は、ポリシー B よりも優先度が高いため、ユーザーに適用されます。
3. ポリシーでスプーフィング対策がオフになっているため、ポリシー A の設定に基づいて、メッセージに対してアクションは何も実行されません。
4. ポリシーの処理は停止するため、ポリシー B がユーザーに適用されることはありません。

同じユーザーが同じ種類の複数のカスタムポリシーに故意または誤って含まれている可能性があるので、次のようなカスタムポリシーの設計ガイドラインを使用します。

- 少数のユーザーに適用されるポリシーにより高い優先度を割り当て、多数のユーザーに適用されるポリシーに対する優先順位を低くします。 既定のポリシーは常に最後に適用されることに注意してください。
- より優先度の高いポリシーを構成して、優先度の低いポリシーよりも厳密に特殊化された設定にします。
- より少ないカスタムポリシーを使用することを検討してください (厳密な設定を必要とするユーザーにはカスタムポリシーのみを使用します)。
