---
title: 検疫済み電子メールメッセージ
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 4c234874-015e-4768-8495-98fcccfc639b
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理者は、潜在的な危険または望ましくないメッセージを保持する Exchange Online Protection (EOP) の検疫について知ることができます。
ms.openlocfilehash: 71a5f32fe6888d751bf2c4020fca4df671ac96d1
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208284"
---
# <a name="quarantined-email-messages-in-eop"></a>EOP で検疫された電子メールメッセージ

Exchange online またはスタンドアロンの exchange Online Protection (EOP) 組織にメールボックスがあり、Exchange online メールボックスを使用していない場合は、潜在的な危険または望ましくないメッセージを保持するために検疫を利用できます。365

マルウェア対策ポリシーは、マルウェアが含まれて*いる添付ファイル*が見つかった場合に、自動的にメッセージを検疫します。 詳細については、「 [EOP でマルウェア対策ポリシーを構成する](configure-anti-malware-policies.md)」を参照してください。

既定では、スパム対策ポリシーはフィッシングメッセージを検疫し、スパムおよびバルクメールメッセージをユーザーの迷惑メールフォルダーに配信します。 ただし、スパムや電子メールメッセージを検疫するスパム対策ポリシーを作成およびカスタマイズすることもできます。 詳細については、「 [EOP でスパム対策ポリシーを構成する](configure-your-spam-filter-policies.md)」を参照してください。

ユーザーと管理者の両方が、検疫済みメッセージを操作できます。

- 管理者は、すべてのユーザーに対してすべての種類の検疫済みメッセージを操作できます。 マルウェア、精度の高いフィッシング、またはメールフロールール (トランスポートルールとも呼ばれる) の結果として検疫されたメッセージを操作できるのは、管理者だけです。 詳細については、「 [EOP で管理者として検疫済みメッセージおよびファイルを管理する](manage-quarantined-messages-and-files.md)」を参照してください。

- メッセージがスパム、バルクメール、または (2020 年4月の) フィッシングとして検疫された場合、ユーザーは検疫済みメッセージを使用して受信することができます。 詳細については、「 [EOP でユーザーとして検疫済みメッセージを検索して解放する](find-and-release-quarantined-messages-as-a-user.md)」を参照してください。

  ユーザーが自分で検疫されたフィッシングメッセージを管理できないようにするために、管理者は、スパム対策ポリシーで**フィッシング詐欺メール**フィルター verdict に対して別のアクションを構成することができます。 詳細については、「 [EOP でスパム対策ポリシーを構成する](configure-your-spam-filter-policies.md)」を参照してください。

- 管理者とユーザーは、検疫中に誤検知を Microsoft に報告できます。

検疫の詳細については、「検疫に関する[FAQ](quarantine-faq.md)」を参照してください。
