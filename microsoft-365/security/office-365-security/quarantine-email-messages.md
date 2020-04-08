---
title: Office 365 の検疫
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
description: Office 365 での検疫は、潜在的に危険または不要なメッセージを保持します。 管理者とエンドユーザーは検疫にアクセスできます。
ms.openlocfilehash: a11b4a0d86cfc5f74636d3a9f89cf598320d1ebf
ms.sourcegitcommit: 053d42480d8aa3792ecb0027ddd53d383a029474
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/07/2020
ms.locfileid: "42940959"
---
# <a name="quarantine-in-office-365"></a>Office 365 の検疫

Exchange Online または exchange online メールボックスのないスタンドアロンの Exchange Online Protection (EOP) のお客様の場合、Office 365 をご利用のお客様は、潜在的な危険または不要なメッセージを保持するために検疫を利用できます。

マルウェア対策ポリシーは、マルウェアが含まれて*いる添付ファイル*が見つかった場合に、自動的にメッセージを検疫します。 詳細については、「 [Office 365 でマルウェア対策ポリシーを構成する](configure-anti-malware-policies.md)」を参照してください。

既定では、スパム対策ポリシーはフィッシングメッセージを検疫し、スパムおよびバルクメールメッセージをユーザーの迷惑メールフォルダーに配信します。 ただし、スパムや電子メールメッセージを検疫するスパム対策ポリシーを作成およびカスタマイズすることもできます。 詳細については、「[Office 365 でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。

ユーザーと管理者の両方が、検疫済みメッセージを操作できます。

- 管理者は、すべてのユーザーに対してすべての種類の検疫済みメッセージを操作できます。 マルウェア、精度の高いフィッシング、またはメールフロールール (トランスポートルールとも呼ばれる) の結果として検疫されたメッセージを操作できるのは、管理者だけです。 詳細については、「[Office 365 の管理者として検疫済みのメッセージやファイルを管理する](manage-quarantined-messages-and-files.md)」を参照してください。

- メッセージがスパム、バルクメール、または (4 月 2020) フィッシングとして検疫された場合、ユーザーは検疫済みメッセージを処理できます。 詳細については、「 [Office 365 のユーザーとして、検疫済みメッセージを検索して解放する](find-and-release-quarantined-messages-as-a-user.md)」を参照してください。

  ユーザーが自分で検疫されたフィッシングメッセージを管理できないようにするために、管理者は、スパム対策ポリシーで**フィッシング詐欺メール**フィルター verdict に対して別のアクションを構成することができます。 詳細については、「[Office 365 でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。

- 管理者とユーザーは、検疫中に誤検知を Microsoft に報告できます。

検疫の詳細については、「検疫に関する[FAQ](quarantine-faq.md)」を参照してください。
