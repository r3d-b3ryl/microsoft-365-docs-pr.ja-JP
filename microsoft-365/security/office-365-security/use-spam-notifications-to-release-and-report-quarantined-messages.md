---
title: Microsoft 365の検疫通知 (エンド ユーザースパム通知)
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.localizationpriority: medium
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 56de4ed5-b0aa-4195-9f46-033d7cc086bc
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理者は、Exchange Online Protection (EOP) で検疫されたメッセージのエンドユーザースパム通知について学習できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 706303e7bdab7297fbc1dd353238db3542c28177
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64465841"
---
# <a name="use-quarantine-notifications-to-release-and-report-quarantined-messages"></a>検疫通知を使用して検疫済みメッセージを解放および報告する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Exchange Online のメールボックスを使用している Microsoft 365 組織または Exchange Online のメールボックスを使用していないスタンドアロンの Exchange Online Protection (EOP) 組織では、危険な可能性があるメッセージまたは不要なメッセージは検疫済みメッセージとして保留されます。 詳細については、「 [EOP の検疫済みメッセージ](quarantine-email-messages.md)」を参照してください。

_検疫ポリシーは、_ メッセージが検疫された理由 (サポートされている機能の場合) に基づいて、検疫されたメッセージに対してユーザーが許可する操作を定義します。 詳細については、「[検疫ポリシー](quarantine-policies.md)」を参照してください。 また、検疫ポリシーは、影響を受ける受信者 (共有メールボックスを含む) が検疫されたメッセージに関する定期的な _検疫通知_ を受け取るかどうかを制御します。 検疫通知は、サポートされているすべての保護機能 (スパム対策ポリシーの判定だけでなく) のエンドユーザースパム通知の代わりです。

AdminOnlyAccessPolicy または DefaultFullAccessPolicy という名前の組み込みの検疫通知では、検疫通知は有効になりません。 組織に検疫通知がある場合は、NotificationEnabledPolicy という名前の組み込みの検疫ポリシーで検疫通知 [が](quarantine-policies.md#full-access-permissions-and-quarantine-notifications)有効になります。 それ以外の場合は、検疫ポリシーで検疫通知を有効にするには、 [新しい検疫ポリシーを作成して構成する必要があります](quarantine-policies.md#step-1-create-quarantine-policies-in-the-microsoft-365-defender-portal)。

さらに、検疫通知の [送信者をブロックする] オプションを正しく機能させるには、ユーザーがリモート PowerShell に対して有効になっている必要があります。 手順については、「[Exchange Online PowerShell へのアクセスを有効または無効にする](/powershell/exchange/disable-access-to-exchange-online-powershell)」を参照してください。

管理者は、検疫ポリシーのグローバル設定を使用して、送信者の表示名、異なる言語の免責事項テキスト、検疫通知で使用される会社のロゴをカスタマイズすることもできます。 手順については、「 [グローバル検疫通知設定の構成](quarantine-policies.md#configure-global-quarantine-notification-settings-in-the-microsoft-365-defender-portal)」を参照してください。

共有メールボックスの場合、検疫通知は、共有メールボックスに対する FullAccess アクセス許可が付与されているユーザーに対してのみサポートされます。 詳細については、「 [EAC を使用して共有メールボックスの委任を編集する」を](/Exchange/collaboration-exo/shared-mailboxes#use-the-eac-to-edit-shared-mailbox-delegation)参照してください。

> [!NOTE]
> 既定では、信頼度の高いフィッシング、マルウェア、メール フロー ルール (トランスポート ルールとも呼ばれます)、または Defender for Office 365のセーフ添付ファイル ポリシーとして検疫されるメッセージは、管理者のみが使用できます (既定では、AdminOnlyAccessPolicy 検疫ポリシーが使用されます)。 詳細については、「[EOP の管理者として検疫済みのメッセージやファイルを管理する](manage-quarantined-messages-and-files.md)」を参照してください。
>
> 現在、検疫通知は、グループまたは高信頼フィッシング メッセージではサポートされていません。 

検疫通知を受け取ると、検疫されたメッセージごとに常に次の情報を使用できます。

- **送信者**: 検疫されたメッセージの送信名と電子メール アドレス。
- **件名**: 検疫されたメッセージの件名行テキスト。
- **日付**: メッセージが検疫された日時 (UTC)。

検疫通知で使用できるアクションは、メッセージが検疫された理由と、関連付けられた検疫ポリシーによって割り当てられたアクセス許可によって異なります。 詳細については、「 [検疫ポリシーのアクセス許可の詳細」を参照してください](quarantine-policies.md#quarantine-policy-permission-details)。

既定では、スパム、信頼度の高いスパム、または一括として検疫されたメッセージの検疫通知では、次のアクションを使用できます。

- **送信者をブロック** する: メールボックスの [受信拒否] リストに送信者を追加するには、このリンク _を_ クリックします。 詳細については、「[メール送信者をブロックする](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4)」を参照してください。
- **リリース**: Microsoft 365 Defender ポータルで **検疫** に移動せずに、ここでメッセージをリリースできます。
- **確認**: このリンクをクリックすると、Microsoft 365 Defender ポータルの **[検疫]** に移動します。ここで、検疫されたメッセージの表示、リリース、削除、または報告を行うことができます (メッセージが検疫された理由によって異なります)。 詳細については、「 [EOP で検疫されたメッセージを検索してユーザーとして解放する」を](find-and-release-quarantined-messages-as-a-user.md)参照してください。

:::image type="content" source="../../media/end-user-spam-notification.png" alt-text="検疫通知の例" lightbox="../../media/end-user-spam-notification.png":::

> [!NOTE]
> ブロックされた送信者は引き続きメールを送信できます。 メールボックスに送信されたこの送信者からのメッセージは、直ちに迷惑メール フォルダーに移動されます。 この送信者からの今後のメッセージは、迷惑メール フォルダーまたは検疫に移動します。 これらのメッセージを検疫するのではなく、到着時に削除する場合は、 [メール フロー ルール](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (トランスポート ルールとも呼ばれます) を使用して、到着時にメッセージを削除します。
