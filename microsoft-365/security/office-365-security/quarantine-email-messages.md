---
title: 検疫済み電子メール メッセージ
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: overview
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 4c234874-015e-4768-8495-98fcccfc639b
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: 管理者は、危険または望ましくない可能性のあるメッセージを保持する Exchange Online Protection (EOP) の検疫について学習できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 47742008af9c1cd0a0a17df9e43ebc0228a825b0
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288767"
---
# <a name="quarantined-email-messages-in-eop"></a>EOP での検疫済み電子メール メッセージ

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Exchange Online または Exchange Online メールボックスのないスタンドアロンの Exchange Online Protection (EOP) 組織にメールボックスがある Microsoft 365 組織では、検疫を使用して危険なメッセージや不要なメッセージを保持できます。

マルウェア対策ポリシーは、添付ファイルにマルウェアが含まれていると検出された場合、メッセージを自動的に検疫します。 詳細については [、「EOP でマルウェア対策ポリシーを構成する」を参照してください](configure-anti-malware-policies.md)。

既定では、スパム対策ポリシーはフィッシング メッセージを検疫し、スパムメッセージとバルク メール メッセージをユーザーの迷惑メール フォルダーに配信します。 ただし、スパム対策ポリシーを作成およびカスタマイズして、スパム メッセージとバルク メール メッセージを検疫することもできます。 詳細については、「[EOP でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。

ユーザーと管理者の両方が検疫済みメッセージを処理できます。

- 管理者は、すべてのユーザーのすべての種類の検疫済みメッセージを処理できます。 マルウェア、信頼度の高いフィッシング詐欺、またはメール フロー ルール (トランスポート ルールとも呼ばれる) の結果として検疫されたメッセージを処理できるのは管理者だけです。 詳細については、「[EOP の管理者として検疫済みのメッセージやファイルを管理する](manage-quarantined-messages-and-files.md)」を参照してください。

- メッセージがスパム、バルク メール、または (2020 年 4 月の現在) フィッシングとして検疫された場合、ユーザーは受信者である検疫済みメッセージを操作できます。 詳細については [、「EOP でユーザーとして検疫済みメッセージを検索して解放する」を参照してください](find-and-release-quarantined-messages-as-a-user.md)。

  ユーザーが自分の検疫済みフィッシング メッセージを管理するのを防ぐために、管理者はスパム対策ポリシーのフィッシングメール フィルターの条件に対して別のアクションを構成できます。 詳細については、「[EOP でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。

- 管理者とユーザーは、検疫で誤検知を Microsoft に報告できます。

検疫の詳細については、「検疫に関する [FAQ」を参照してください](quarantine-faq.md)。
