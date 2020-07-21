---
title: Microsoft 365 でのエンドユーザースパム通知
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 56de4ed5-b0aa-4195-9f46-033d7cc086bc
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理者は、Exchange Online Protection (EOP) で検疫されたメッセージのエンドユーザースパム通知について知ることができます。
ms.openlocfilehash: 4c3275b6af1eb452ed420b8eb2f923dfbb1267d6
ms.sourcegitcommit: a08103bc120bdec7cfeaf67c1be4e221241e69ad
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2020
ms.locfileid: "45200018"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages"></a>ユーザースパム通知を使用して、検疫済みメッセージを解放して報告する

Exchange Online のメールボックスを使用している Microsoft 365 組織または Exchange Online のメールボックスを使用していないスタンドアロンの Exchange Online Protection (EOP) 組織では、危険な可能性があるメッセージまたは不要なメッセージは検疫済みメッセージとして保留されます。 詳細については、「 [EOP での検疫済みメッセージ](quarantine-email-messages.md)」を参照してください。

既定では、エンドユーザーのスパム通知はスパム対策ポリシーで無効になっています。 管理者が[エンドユーザーのスパム通知を有効](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications)にすると、受信者 (自動マッピングが有効になっている共有メールボックスを含む) は、スパム、バルクメール、または (2020 年4月の) フィッシングとして検疫されたメッセージに関する定期的な通知を受信します。

> [!NOTE]
> 高信頼フィッシング、マルウェア、またはメールフロールール (トランスポートルールとも呼ばれます) として検疫されたメッセージは、管理者のみが使用できます。 詳細については、「[EOP の管理者として検疫済みのメッセージやファイルを管理する](manage-quarantined-messages-and-files.md)」を参照してください。

エンドユーザーのスパム通知には、検疫済みメッセージごとに次の情報が含まれています。

- **Sender**: 検疫されたメッセージの送信者名と電子メールアドレス。

- **Subject**: 検疫されたメッセージの件名のテキスト。

- **日付**: メッセージが検疫された日付と時刻 (UTC)。

- [**送信者のブロック**]: このリンクをクリックして、受信拒否リストに送信者を追加します。 詳細については、「[メールの送信者をブロックする](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4)」を参照してください。

- **Release**: スパム (フィッシングではない) メッセージに対して、セキュリティ & コンプライアンスセンターの検疫を行わずに、ここでメッセージを解放することができます。

- **レビュー**: このリンクをクリックすると、セキュリティ & コンプライアンスセンターで、検疫済みメッセージのリリース、削除、またはレポート作成を行うことができます。 詳細については、「 [EOP でユーザーとして検疫済みメッセージを検索して解放する](find-and-release-quarantined-messages-as-a-user.md)」を参照してください。

![エンドユーザーのスパム通知の例](../../media/end-user-spam-notification.png)
