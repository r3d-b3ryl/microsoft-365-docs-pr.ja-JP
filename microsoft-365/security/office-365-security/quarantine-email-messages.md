---
title: Office 365 でメール メッセージを検疫する
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
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
description: Office 365 で受信メールメッセージの検疫を設定することができます。これは、スパム、バルク、フィッシングメール、マルウェアとしてフィルター処理された受信メールメッセージを後で確認するために保持することができます。
ms.openlocfilehash: 280421457662dd30cdcc3c7985feaad7ba0d16f2
ms.sourcegitcommit: 4986032867b8664a215178b5e095cbda021f3450
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/12/2020
ms.locfileid: "41957432"
---
# <a name="quarantine-email-messages-in-office-365"></a>Office 365 でメール メッセージを検疫する

Office 365 で受信メールメッセージの検疫を設定することができます。これは、スパム、バルクメール、フィッシングメール、マルウェアを含むメール、および指定されたメールフロールール (trasport ルールとも呼ばれる) に一致するメールを後で保持することができます。中.
  
既定では、フィッシング、マルウェア、およびメールフロールールに対してフィルター処理されたメッセージは検疫に送信されますが、スパムとしてフィルター処理されたメッセージとバルクメールは、受信者の迷惑メールフォルダーに送信されます。 管理者は、スパムフィルターポリシー (コンテンツフィルターポリシーとも呼ばれます) を設定して、スパムやバルクメールメッセージを検疫に送信することができます。 詳細については、「[スパム フィルター ポリシーを構成する](configure-your-spam-filter-policies.md)」 を参照してください。
  
ユーザーと管理者の両方が、検疫済みメッセージを操作できます。 ユーザーは、隔離された独自のフィルター処理されたメッセージのみを操作できます。 管理者は、すべてのユーザーの検疫済みメッセージを検索し、管理することができます。

> [!NOTE]
> マルウェア、高信頼フィッシングメッセージ、およびメールフロールールアクションによって検疫されたメッセージは、管理者検疫でのみ使用できます。 ユーザーは、自分のフィッシング、スパム、およびバルクメールメッセージにアクセスできます。 
  
検疫済みメッセージの使用の詳細については、次を参照してください。
  
- [管理者として検疫済みメッセージを管理する](manage-quarantined-messages-and-files.md)

- [ユーザーが検閲済みメッセージを検出して解放する](find-and-release-quarantined-messages-as-a-user.md)

- [ユーザースパム通知を使用してスパム検疫済みメッセージを解放して報告する](use-spam-notifications-to-release-and-report-quarantined-messages.md)

- [検疫に関する FAQ](quarantine-faq.md)
