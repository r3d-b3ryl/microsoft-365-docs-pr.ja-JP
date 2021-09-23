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
description: 管理者は、潜在的に危険なメッセージまたは望ましくないメッセージExchange Online Protection (EOP) の検疫について学習できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: cf9de0ba85c0e1612d29f7842da4bc74af14bf00
ms.sourcegitcommit: 0ed93816e2c1e6620e68bd1c0f00390062911606
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2021
ms.locfileid: "59483563"
---
# <a name="quarantined-email-messages-in-eop"></a>EOP で検疫された電子メール メッセージ

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Microsoft 365 Exchange Online またはスタンドアロン Exchange Online Protection (EOP) 組織に Exchange Online メールボックスがない組織では、潜在的に危険なメッセージや望ましくないメッセージを保持するために検疫を利用できます。

マルウェア対策ポリシーは、添付ファイルにマルウェアが含まれていると検出された場合、メッセージを自動的に検疫します。 詳細については [、「EOP でマルウェア対策ポリシーを構成する」を参照してください](configure-anti-malware-policies.md)。

既定では、スパム対策はフィッシングメッセージと高信頼フィッシング メッセージを検疫し、スパム、高信頼スパム、バルク メール メッセージをユーザーの迷惑メール フォルダーに配信します。 ただし、スパム対策ポリシーを作成およびカスタマイズして、スパム、高信頼スパム、バルク メール メッセージを検疫することもできます。 詳細については、「[EOP でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。

ユーザーと管理者の両方が検疫済みメッセージを処理できます。

- _検疫ポリシーは、_ メッセージが検疫された理由 (サポートされている機能の場合) に基づいて、検疫されたメッセージに対してユーザーが許可される操作または実行しない操作を定義します。 既定の検疫ポリシーは、以下で説明するように履歴機能を適用します。 管理者は、ユーザーの制限が少ない、または制限の厳しい機能を定義するカスタム検疫ポリシーを作成して適用できます。 詳細については、「検疫ポリシー [」を参照してください](quarantine-policies.md)。

- 管理者は、すべてのユーザーのすべての種類の検疫済みメッセージを処理できます。 既定では、マルウェア、高信頼フィッシング、またはメール フロー ルール (トランスポート ルールとも呼ばれる) の結果として検疫されたメッセージを管理者だけが処理できます。 詳細については、「[EOP の管理者として検疫済みのメッセージやファイルを管理する](manage-quarantined-messages-and-files.md)」を参照してください。

- 既定では、ユーザーは受信者であり、メッセージがスパム、バルク メール、またはフィッシング (高信頼フィッシングではない) として検疫された検疫済みメッセージを操作できます。 詳細については、「EOP で検疫済みメッセージをユーザーとして検索して解放する [」を参照してください](find-and-release-quarantined-messages-as-a-user.md)。

  ユーザーが検疫済みフィッシング メッセージを管理しきれなくするために、管理者はスパム対策ポリシーのフィッシングメール フィルターの評決に対して別のアクションを構成できます。 詳細については、「[EOP でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。

- 管理者とユーザーは、検疫中に誤検知を Microsoft に報告できます。

検疫の詳細については、「検疫に関するよく寄せられる質問 [」を参照してください](quarantine-faq.yml)。
