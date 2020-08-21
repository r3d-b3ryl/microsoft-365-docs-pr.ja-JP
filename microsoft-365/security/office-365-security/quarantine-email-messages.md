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
description: 管理者は、危害を行う可能性のあるメッセージや望ましくないメッセージを保持する Exchange Online Protection (EOP) の検疫について学習できます。
ms.openlocfilehash: d2ccf174ae929c6db14f2a5319e9594495c0778e
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826803"
---
# <a name="quarantined-email-messages-in-eop"></a>EOP の検疫済み電子メール メッセージ

Exchange Online にメールボックスがある Microsoft 365 組織や、Exchange Online メールボックスを使用しないスタンドアロン Exchange Online Protection (EOP) 組織では、検疫を利用して危害を行う可能性のあるメッセージや望ましくないメッセージを保持できます。

マルウェア対策ポリシーは、マルウェアを含む添付ファイルが見つ *かった場合* 、メッセージを自動的に検疫します。 詳細については [、EOP でマルウェア対策ポリシーを構成する」を参照してください](configure-anti-malware-policies.md)。

既定では、スパム対策ポリシーはフィッシング メッセージを検疫して、スパム メッセージとバルク メール メッセージをユーザーの迷惑メール フォルダーに配信します。 しかし、スパムおよびバルク メール メッセージを検疫するスパム対策ポリシーを作成し、カスタマイズすることもできます。 詳細については、「[EOP でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。

ユーザーと管理者の両方が、検疫済みメッセージを操作できます。

- 管理者は、すべてのユーザーのすべての種類の検疫済みメッセージを操作できます。 マルウェア、高度フィッシング、メール フロー ルール (別名: トランスポート ルール) の結果として検疫されたメッセージに対してのみ管理者が操作できます。 詳細については、「[EOP の管理者として検疫済みのメッセージやファイルを管理する](manage-quarantined-messages-and-files.md)」を参照してください。

- メッセージがスパム、バルク メール、(2020 年 4 月の後) フィッシングとして検疫された場合、ユーザーは検疫済みメッセージを受信者とし、操作できます。 詳細については、「EOP でユーザーとして [検疫済みメッセージを検索して解放する」を参照してください](find-and-release-quarantined-messages-as-a-user.md)。

  ユーザーが独自の検疫済みフィッシング メッセージを管理できないようにするために、管理者は、フィッシング **メール** フィルターの詳細に対する別のアクションをスパム対策ポリシーで構成できます。 詳細については、「[EOP でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。

- 管理者とユーザーは、検疫で誤検知を Microsoft に報告できます。

検疫の詳細については、「検疫 [」FAQ を参照してください](quarantine-faq.md)。
