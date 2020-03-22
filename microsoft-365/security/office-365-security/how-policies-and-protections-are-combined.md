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
ms.openlocfilehash: 9f2033b1ec066c1f8501ce019b8f8c7f3748fd15
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895337"
---
# <a name="order-and-precedence-of-email-protection-in-office-365"></a>Office 365 での電子メール保護の順序と優先順位

Office 365 ユーザーとして、受信メールに複数の形式の保護によるフラグが設定されている場合があります。 たとえば、すべての Office 365 ユーザーが使用できる組み込みの EOP マルウェア対策ポリシー、および Office 365 Advanced Threat Protection のお客様が利用できる、より堅牢な ATP のフィッシング対策ポリシーがあります。 メッセージも、マルウェア、スパム、フィッシングなどの複数の検出スキャンを通過します。このアクティビティがすべて与えられた場合、どのポリシーが適用されるかについて混乱が生じることがあります。

一般に、メッセージに適用されるポリシーは、 **CAT (Category)** プロパティの**スパム対策**ヘッダー内で識別されます。 詳細については、「[スパム対策メッセージ ヘッダー](anti-spam-message-headers.md)」を参照してください。

メッセージに適用されるポリシーを決定する主な要因は2つあります。

- **電子メール保護の種類の優先度**: この順序は構成できず、次の表に記載されています。

  |||||
  |---|---|---|---|
  |**[優先度]**|**電子メール保護**|**分類**|**管理対象**|
  |1-d|マルウェア|CAT: 男性 W|[Office 365 でマルウェア対策ポリシーを構成する](configure-anti-malware-policies.md)|
  |pbm-2|フィッシング|CAT: PHSH|[Office 365 でスパム対策ポリシーを構成する](configure-your-spam-filter-policies.md)|
  |1/3|高確度スパム|CAT: HSPM|[Office 365 でスパム対策ポリシーを構成する](configure-your-spam-filter-policies.md)|
  |4 |スプーフィング|CAT: スプーフィング|[Office 365 の ATP フィッシング対策とフィッシング対策ポリシーをセットアップする](set-up-anti-phishing-policies.md) <Br/><br/> [スプーフィング インテリジェンスの詳細情報](learn-about-spoof-intelligence.md)|
  |5 |スパム|CAT: SPM|[Office 365 でスパム対策ポリシーを構成する](configure-your-spam-filter-policies.md)|
  |6 |バルク|CAT: BULK|[Office 365 でスパム対策ポリシーを構成する](configure-your-spam-filter-policies.md)|
  |7<sup>\*</sup>|ドメイン偽装|DIMP|[Office 365 の ATP フィッシング対策とフィッシング対策ポリシーをセットアップする](set-up-anti-phishing-policies.md)|
  |~<sup>\*</sup>|ユーザー偽装|UIMP|[Office 365 の ATP フィッシング対策とフィッシング対策ポリシーをセットアップする](set-up-anti-phishing-policies.md)|
  |

  <sup>\*</sup>これらの機能は ATP でのみ使用できます。

- **ポリシーの優先度**: 各保護の種類 (スパム対策、マルウェア対策、フィッシング詐欺対策など) について、すべてのユーザーに適用される既定のポリシーがありますが、特定のユーザーに適用するカスタムポリシーを作成することもできます。 各カスタムポリシーには、ポリシーが適用される順序を決定する優先順位の値があります。 既定のポリシーは常に最後に適用されます。

  ユーザーが複数のカスタムポリシーで定義されている場合、優先度が最も高いポリシーのみが適用されます。 その他のポリシーは、ユーザーに対して評価されません (既定のポリシーを含みます)。

たとえば、**同じユーザーに適用される**次のフィッシング対策ポリシーと、ユーザーの偽装とスプーフィングの両方として識別されるメッセージを考えてみます。

  |||||
  |---|---|---|---|
  |**スパム対策ポリシー**|**[優先度]**|**ユーザー偽装 (ATP)**|**スプーフィング対策 (EOP)**|
  |ポリシー A|1-d|オン|オフ|
  |ポリシー B|pbm-2|オフ|オン|
  |

1. スプーフィングは、ユーザー偽装 (8) よりも優先度が高いため、メッセージはスプーフィングとしてマークされ、スプーフィングとして扱われます。
2. ポリシー A は、優先度 B より高い優先度を持つため、ユーザーに適用されます。
3. ポリシーでスプーフィング対策がオフになっているため、ポリシー A の設定に基づいて、メッセージに対してアクションは何も実行されません。
4. スパム対策ポリシーの処理は停止するため、ポリシー B がユーザーに適用されることはありません。

同じ種類のカスタムポリシーに多数のユーザーが存在する可能性があるため、次のようなカスタムポリシーの設計ガイドラインを検討してください。

- 少数のユーザーに適用されるポリシーにより高い優先度を割り当て、多数のユーザーに適用されるポリシーに対する優先順位を低くします。 既定のポリシーは常に最後に適用されることに注意してください。
- より優先度の高いポリシーを構成して、優先度の低いポリシーよりも厳密に特殊化された設定にします。
- より少ないカスタムポリシーを使用することを検討してください (厳密な設定を必要とするユーザーにはカスタムポリシーのみを使用します)。
