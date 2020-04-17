---
title: Office 365 での電子メール保護の順序と優先順位
keywords: セキュリティ、マルウェア、Microsoft 365、M365、セキュリティセンター、ATP、Microsoft Defender ATP、Office 365 ATP、Azure ATP
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
ms.collection:
- M365-security-compliance
description: Office 365 の保護の適用順序、および保護ポリシーの優先度の値によって、どのポリシーが適用されるかを決定する方法について説明します。
ms.openlocfilehash: 6a95c59a5cd629b704753c6c05c9b8069d9240b1
ms.sourcegitcommit: db8702cf578b02c6fd6a2670c177b456efae4748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2020
ms.locfileid: "43537415"
---
# <a name="order-and-precedence-of-email-protection-in-office-365"></a>Office 365 での電子メール保護の順序と優先順位

Office 365 では、受信メールはによって評価されるため、複数の形式の保護 (マルウェア、スパム、フィッシングなど) を使用してフラグが付けられる場合があります。 このアクティビティがすべて与えられた場合、どのポリシーが適用されたかを判断するのが困難になることがあります。

一般に、メッセージに適用されるポリシーは、 **CAT (Category)** プロパティの**スパム対策**ヘッダー内で識別されます。 詳細については、「[スパム対策メッセージ ヘッダー](anti-spam-message-headers.md)」を参照してください。

メッセージに適用されるポリシーを決定する主な要因は2つあります。

- **電子メール保護の種類の優先度**: この順序は構成できず、次の表に記載されています。

  |||||
  |---|---|---|---|
  |**Priority**|**電子メール保護**|**カテゴリ**|**管理対象**|
  |1-d|マルウェア|CAT: 男性 W|[Office 365 でマルウェア対策ポリシーを構成する](configure-anti-malware-policies.md)|
  |2|フィッシング|CAT: PHSH|[Office 365 でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)|
  |1/3|高確度スパム|CAT: HSPM|[Office 365 でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)|
  |4 |スプーフィング|CAT: スプーフィング|[Office 365 でスプーフィングインテリジェンスを構成する](learn-about-spoof-intelligence.md)|
  |5 |スパム|CAT: SPM|[Office 365 でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)|
  |6 |バルク|CAT: BULK|[Office 365 でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)|
  |7<sup>\*</sup>|ドメイン偽装 (保護されたユーザー)|DIMP|[Office 365 で ATP のフィッシング対策ポリシーを構成する](configure-atp-anti-phishing-policies.md)|
  |~<sup>\*</sup>|ユーザー偽装 (保護されたドメイン)|UIMP|[Office 365 で ATP のフィッシング対策ポリシーを構成する](configure-atp-anti-phishing-policies.md)|
  |

  <sup>\*</sup>これらの機能は、ATP のフィッシング対策ポリシーでのみ利用可能です。

- **ポリシーの優先度**: 各保護の種類 (スパム対策、マルウェア対策、フィッシング詐欺対策など) について、すべてのユーザーに適用される既定のポリシーがありますが、多くの場合、特定のユーザーに適用するカスタムポリシーを作成することができます。 各カスタムポリシーには、ポリシーが適用される順序を決定する優先順位の値があります。 既定のポリシーは常に最後に適用されます。

  ユーザーが同じ種類の複数のポリシーで定義されている場合、優先度の高いポリシーのみが適用されます。 その種類の残りのポリシーは、ユーザーに対して評価されません (既定のポリシーを含む)。

たとえば、**同じユーザーに適用される**次の ATP のフィッシング対策ポリシーと、ユーザーの偽装とスプーフィングの両方として識別されるメッセージを考えてみます。

  |||||
  |---|---|---|---|
  |**ATP のフィッシング対策ポリシー**|**Priority**|**ユーザー偽装**|**スプーフィング対策**|
  |ポリシー A|1-d|オン|オフ|
  |ポリシー B|2|オフ|オン|
  |

1. スプーフィングは、ユーザー偽装 (8) よりも優先度が高いため、メッセージはスプーフィングとしてマークされ、スプーフィングとして扱われます。
2. ポリシー A は、ポリシー B よりも優先度が高いため、ユーザーに適用されます。
3. ポリシーでスプーフィング対策がオフになっているため、ポリシー A の設定に基づいて、メッセージに対してアクションは何も実行されません。
4. ポリシーの処理は停止するため、ポリシー B がユーザーに適用されることはありません。

同じユーザーが同じ種類の複数のカスタムポリシーに故意または誤って含まれている可能性があるので、次のようなカスタムポリシーの設計ガイドラインを使用します。

- 少数のユーザーに適用されるポリシーにより高い優先度を割り当て、多数のユーザーに適用されるポリシーに対する優先順位を低くします。 既定のポリシーは常に最後に適用されることに注意してください。
- より優先度の高いポリシーを構成して、優先度の低いポリシーよりも厳密に特殊化された設定にします。
- より少ないカスタムポリシーを使用することを検討してください (厳密な設定を必要とするユーザーにはカスタムポリシーのみを使用します)。
