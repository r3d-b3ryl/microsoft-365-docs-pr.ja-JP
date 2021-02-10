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
ms.openlocfilehash: 4b111ea0d07453ef4280ec9e57247c8215420074
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167409"
---
# <a name="quarantined-email-messages-in-eop"></a>EOP での検疫済み電子メール メッセージ

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
-   [Microsoft Defender for Office 365 プラン 1 およびプラン 2](https://go.microsoft.com/fwlink/?linkid=2148715)
-   [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Exchange Online または Exchange Online メールボックスのないスタンドアロンの Exchange Online Protection (EOP) 組織にメールボックスがある Microsoft 365 組織では、検疫を使用して危険なメッセージや不要なメッセージを保持できます。

マルウェア対策ポリシーは、添付ファイルにマルウェアが含まれていると検出された場合、メッセージを自動的に検疫します。 詳細については [、「EOP でマルウェア対策ポリシーを構成する」を参照してください](configure-anti-malware-policies.md)。

既定では、スパム対策ポリシーはフィッシング メッセージを検疫し、スパムメッセージとバルク メール メッセージをユーザーの迷惑メール フォルダーに配信します。 ただし、スパム対策ポリシーを作成およびカスタマイズして、スパム メッセージとバルク メール メッセージを検疫することもできます。 詳細については、「[EOP でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。

ユーザーと管理者の両方が検疫済みメッセージを処理できます。

- 管理者は、すべてのユーザーのすべての種類の検疫済みメッセージを処理できます。 マルウェア、信頼度の高いフィッシング詐欺、またはメール フロー ルール (トランスポート ルールとも呼ばれる) の結果として検疫されたメッセージを処理できるのは管理者のみです。 詳細については、「[EOP の管理者として検疫済みのメッセージやファイルを管理する](manage-quarantined-messages-and-files.md)」を参照してください。

- ユーザーは、メッセージがスパム、バルク メール、または (2020 年 4 月の現在) フィッシングとして検疫された場合、受信者である検疫済みメッセージを操作できます。 詳細については [、「EOP でユーザーとして検疫済みメッセージを検索して解放する」を参照してください](find-and-release-quarantined-messages-as-a-user.md)。

  ユーザーが独自の検疫済みフィッシング メッセージを管理するのを防ぐために、管理者はスパム対策ポリシーのフィッシングメール フィルターの条件に対して別のアクションを構成できます。 詳細については、「[EOP でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。

- 管理者とユーザーは、検疫で誤検知を Microsoft に報告できます。

検疫の詳細については、「検疫に関する [FAQ」を参照してください](quarantine-faq.md)。
