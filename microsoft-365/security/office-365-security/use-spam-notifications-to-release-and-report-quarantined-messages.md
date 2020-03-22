---
title: Office 36 でのエンドユーザースパム通知
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
ms.openlocfilehash: 6cde4681d7ea3ef5795201e9a2816b7224ad36f6
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895061"
---
# <a name="end-user-spam-notifications-in-office-365"></a>Office 365 でのエンドユーザースパム通知

検疫は、exchange online またはスタンドアロンの exchange online Protection (EOP) 組織内のメールボックスを使用する Office 365 組織で潜在的に危険または不要なメッセージを保持します。 exchange online メールボックスはありません。 詳細については、「 [Quarantine In Office 365](quarantine-email-messages.md)」を参照してください。

既定では、エンドユーザーのスパム通知はスパム対策ポリシーで無効になっています。 管理者が[エンドユーザーのスパム通知を有効](configure-your-spam-filter-policies.md)にした場合、メッセージの受信者は、スパム、バルクメール、または (4 月 2020) フィッシングとして検疫されたメッセージに関する定期的な通知を受信します。

> [!NOTE]
> 2019年10月に、検疫済みメッセージをエンドユーザーのスパム通知から直接解放する機能が削除されました。 その代わりに、ユーザーは Office 365 セキュリティ & コンプライアンスセンターに移動して、検疫済みメッセージを (直接、または通知で [**レビュー** ] をクリックすることで) 解放できるようになります。 詳細については、「 [Office 365 のユーザーとして、検疫済みメッセージを検索して解放する](find-and-release-quarantined-messages-as-a-user.md)」を参照してください。 <br/><br/> 高信頼フィッシング、マルウェア、またはメールフロールール (トランスポートルールとも呼ばれます) として検疫されたメッセージは、管理者のみが使用できます。 詳細については、「 [Office 365 での管理者としての検疫済みメッセージとファイルの管理](manage-quarantined-messages-and-files.md)」を参照してください。

エンドユーザーのスパム通知には、検疫済みメッセージごとに次の情報が含まれています。

- **Sender**: 検疫されたメッセージの送信者名と電子メールアドレス。

- **Subject**: 検疫されたメッセージの件名のテキスト。

- **日付**: メッセージが検疫された日付と時刻 (UTC)。

- [**送信者のブロック**]: このリンクをクリックして、受信拒否リストに送信者を追加します。

- **レビュー**: このリンクをクリックすると、セキュリティ & コンプライアンスセンターの検疫に移動し、検疫済みメッセージをリリース、削除、または報告することができます。

![エンドユーザーのスパム通知の例](../../media/end-user-spam-notification.png)
