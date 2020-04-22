---
title: ユーザースパム通知を使用して、検疫済みメッセージを解放して報告する
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
description: 管理者がスパム対策ポリシーでエンドユーザーのスパム通知を有効にすると、メッセージの受信者は検疫済みメッセージに関する定期的な通知を受信します。
ms.openlocfilehash: 641efc024a2842f30f7754c52f624a9f668851de
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636418"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages"></a>ユーザースパム通知を使用して、検疫済みメッセージを解放して報告する

検疫は、exchange online またはスタンドアロンの exchange online Protection (EOP) 組織内のメールボックスを使用して、Microsoft 365 組織で潜在的に危険または不要なメッセージを保持します。 exchange online のメールボックスはありません。 詳細については、「[Office 365 での検疫](quarantine-email-messages.md)」を参照してください。

既定では、エンドユーザーのスパム通知はスパム対策ポリシーで無効になっています。 管理者が[エンドユーザーのスパム通知を有効](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications)にすると、受信者はスパム、バルクメール、または (4 月 2020) フィッシングとして検疫されたメッセージに関する定期的な通知を受信します。

> [!NOTE]
> 高信頼フィッシング、マルウェア、またはメールフロールール (トランスポートルールとも呼ばれます) として検疫されたメッセージは、管理者のみが使用できます。 詳細については、「[Office 365 の管理者として検疫済みのメッセージやファイルを管理する](manage-quarantined-messages-and-files.md)」を参照してください。

エンドユーザーのスパム通知には、検疫済みメッセージごとに次の情報が含まれています。

- **Sender**: 検疫されたメッセージの送信者名と電子メールアドレス。

- **Subject**: 検疫されたメッセージの件名のテキスト。

- **日付**: メッセージが検疫された日付と時刻 (UTC)。

- [**送信者のブロック**]: このリンクをクリックして、受信拒否リストに送信者を追加します。 詳細については、「 [Outlook でメール送信者をブロックする](https://support.office.com/article/b29fd867-cac9-40d8-aed1-659e06a706e4)」を参照してください。

- **Release**: スパム (フィッシングではない) メッセージに対して、セキュリティ & コンプライアンスセンターの検疫を行わずに、ここでメッセージを解放することができます。

- **レビュー**: このリンクをクリックすると、セキュリティ & コンプライアンスセンターで、検疫済みメッセージのリリース、削除、またはレポート作成を行うことができます。 詳細については、「 [Office 365 のユーザーとして、検疫済みメッセージを検索して解放する](find-and-release-quarantined-messages-as-a-user.md)」を参照してください。

![エンドユーザーのスパム通知の例](../../media/end-user-spam-notification.png)
