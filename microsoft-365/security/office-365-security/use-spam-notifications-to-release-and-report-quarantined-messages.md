---
title: Microsoft 365 でのエンドユーザー スパム通知
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: conceptual
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
description: 管理者は、Exchange Online Protection (EOP) の検疫済みメッセージに対するエンドユーザー スパム通知について学習できます。
ms.openlocfilehash: 9e9c95fafe3610e0ad945f18aa85ff13342d8d65
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827363"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages"></a>ユーザーのスパム通知を使って検疫済みメッセージを解放して報告する

Exchange Online のメールボックスを使用している Microsoft 365 組織または Exchange Online のメールボックスを使用していないスタンドアロンの Exchange Online Protection (EOP) 組織では、危険な可能性があるメッセージまたは不要なメッセージは検疫済みメッセージとして保留されます。 詳細については [、EOP の検疫済みメッセージを参照してください](quarantine-email-messages.md)。

既定では、エンドユーザーのスパム通知はスパム対策ポリシーで無効になっています。 管理者がエンド [ユーザー向けスパム通知を有効にすると、](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications)受信者 (自動マッピングが有効になっている共有メールボックスを含む) は、スパム、バルク メール、(2020 年 4 月に) フィッシングとして検疫されたメッセージに関する定期的な通知を受信します。

共有メールボックスでは、エンド ユーザーのスパム通知は、共有メールボックスへの FullAccess アクセス許可が付与されたユーザーに対してのみサポートされます。 詳細については [、「EAC を使用して共有メールボックスの委任を編集する」を参照してください](https://docs.microsoft.com/Exchange/collaboration-exo/shared-mailboxes#use-the-eac-to-edit-shared-mailbox-delegation)。

エンド ユーザー スパム通知は、グループではサポートされていません。

> [!NOTE]
> 高信頼フィッシング、マルウェア、またはメール フロー ルール (別名: トランスポート ルール) によって検疫されたメッセージは、管理者のみが使用できます。 詳細については、「[EOP の管理者として検疫済みのメッセージやファイルを管理する](manage-quarantined-messages-and-files.md)」を参照してください。

エンド ユーザー向けスパム通知には、検疫された各メッセージについて次の情報が含まれます。

- **送信者**: 検疫されたメッセージの送信名と電子メール アドレス。

- **件**名: 検疫済みメッセージの件名行テキスト。

- **日付**: メッセージが検疫された日付と時刻 (UTC)。

- **[受信拒否**] : このリンクをクリックして、その送信者を受信拒否リストに追加します。 詳細については、「メールの送信者 [をブロックする」を参照してください](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4)。

- **リリース**: スパム (フィッシングでない) メッセージに関しては、セキュリティ センターのセキュリティ センターを検疫しなくても、メッセージ&解放できます。

- **[Review](** 確認): このリンクをクリックしてセキュリティ & コンプライアンス センターの [検疫] に移動します。このセンターは、(メッセージが検疫された理由によって異なる) ビュー、解放、または報告できます。 詳細については、「EOP でユーザーとして [検疫済みメッセージを検索して解放する」を参照してください](find-and-release-quarantined-messages-as-a-user.md)。

![エンド ユーザー向けスパム通知の例](../../media/end-user-spam-notification.png)
