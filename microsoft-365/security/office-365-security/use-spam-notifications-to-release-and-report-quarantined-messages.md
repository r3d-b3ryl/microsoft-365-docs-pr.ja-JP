---
title: Microsoft 365 のエンドユーザー スパム通知
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: conceptual
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
description: 管理者は、Exchange Online Protection (EOP) で検疫済みメッセージに対するエンド ユーザーのスパム通知について学習できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: bb347f7fd3d3793b563714e8116316b30165ef9a
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287547"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages"></a>ユーザーのスパム通知を使用して検疫済みメッセージを解放および報告する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Exchange Online のメールボックスを使用している Microsoft 365 組織または Exchange Online のメールボックスを使用していないスタンドアロンの Exchange Online Protection (EOP) 組織では、危険な可能性があるメッセージまたは不要なメッセージは検疫済みメッセージとして保留されます。 詳細については [、「EOP での検疫済みメッセージ」を参照してください](quarantine-email-messages.md)。

既定では、エンドユーザーのスパム通知はスパム対策ポリシーで無効になっています。 管理者がエンド[](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications)ユーザーのスパム通知を有効にすると、受信者 (自動マッピングが有効な共有メールボックスを含む) は、スパム、バルク メール、または (2020 年 4 月の現在) フィッシングとして検疫されたメッセージに関する定期的な通知を受信します。

共有メールボックスの場合、エンド ユーザーのスパム通知は、共有メールボックスに対する FullAccess アクセス許可が付与されているユーザーにのみサポートされます。 詳細については [、「EAC を使用して共有メールボックスの委任を編集する」を参照してください](https://docs.microsoft.com/Exchange/collaboration-exo/shared-mailboxes#use-the-eac-to-edit-shared-mailbox-delegation)。

エンド ユーザーのスパム通知は、グループではサポートされていません。

> [!NOTE]
> 信頼度の高いフィッシング、マルウェア、またはメール フロー ルール (トランスポート ルールとも呼ばれる) によって検疫されたメッセージは、管理者だけが使用できます。 詳細については、「[EOP の管理者として検疫済みのメッセージやファイルを管理する](manage-quarantined-messages-and-files.md)」を参照してください。

エンド ユーザーのスパム通知には、検疫済みメッセージごとに次の情報が含まれます。

- **Sender**: 検疫済みメッセージの送信名と電子メール アドレスです。

- **件名**: 検疫済みメッセージの件名テキスト。

- **日付**: メッセージが検疫された日時 (UTC)。

- **[受信拒否** リスト]: このリンクをクリックして、受信拒否リストに送信者を追加します。 詳細については、「メール送信者 [をブロックする」を参照してください](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4)。

- **リリース**: スパム (フィッシングではない) メッセージの場合は、セキュリティ/コンプライアンス センターを検疫せずに、ここでメッセージ&できます。

- **Review**: Click this link to go to Quarantine in the Security & Compliance Center, where you can (depending on why the message was quarantined) view, release, delete or report your quarantined messages. 詳細については [、「EOP でユーザーとして検疫済みメッセージを検索して解放する」を参照してください](find-and-release-quarantined-messages-as-a-user.md)。

![エンド ユーザーのスパム通知の例](../../media/end-user-spam-notification.png)

> [!NOTE]
> ブロックされた送信者は、引き続きメールを送信できます。 この送信者からメールボックスに送信されたメッセージは、すぐに [迷惑メール] フォルダーに移動されます。 この送信者からの今後のメッセージは、[迷惑メール] フォルダーまたはエンド ユーザーの検疫に移動します。 これらのメッセージを確認するのではなく、到着時に削除する場合は、メール フロー ルール [(トランスポート](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) ルールとも呼ばれる) を使用して、到着時にメッセージを削除します。
