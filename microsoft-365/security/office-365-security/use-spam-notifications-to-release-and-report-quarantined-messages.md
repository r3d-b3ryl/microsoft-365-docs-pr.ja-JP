---
title: 検疫の通知 (エンド ユーザーのスパム通知) Microsoft 365
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
description: 管理者は、検疫済みメッセージのエンド ユーザースパム通知について、Exchange Online Protection (EOP) で確認できます。
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

Exchange Online のメールボックスを使用している Microsoft 365 組織または Exchange Online のメールボックスを使用していないスタンドアロンの Exchange Online Protection (EOP) 組織では、危険な可能性があるメッセージまたは不要なメッセージは検疫済みメッセージとして保留されます。 詳細については、「 [EOP の検疫済みメッセージ」を参照してください](quarantine-email-messages.md)。

_検疫ポリシーは、_ メッセージが検疫された理由 (サポートされている機能の場合) に基づいて、検疫されたメッセージに対してユーザーが実行できる操作を定義します。 詳細については、「[検疫ポリシー](quarantine-policies.md)」を参照してください。 検疫ポリシーは、影響を受ける受信者 (共有メールボックスを含む) が検疫済みメッセージに関する定期的な検疫通知を受け取るかどうかを制御します。 検疫通知は、サポートされている保護機能 (スパム対策ポリシーの評決だけではない) に対するエンド ユーザーのスパム通知に代わるものとなります。

AdminOnlyAccessPolicy または DefaultFullAccessPolicy という名前の組み込みの検疫通知では、検疫通知は有効にされません。 組織に検疫通知がある場合、NotificationEnabledPolicy という名前の組み込みの検疫ポリシー [で検疫通知が有効になります](quarantine-policies.md#full-access-permissions-and-quarantine-notifications)。 それ以外の場合は、検疫ポリシーで検疫通知を有効にするには、新しい検疫ポリシーを作成 [して構成する必要があります](quarantine-policies.md#step-1-create-quarantine-policies-in-the-microsoft-365-defender-portal)。

さらに、検疫通知の [送信者をブロックする] オプションを正しく機能するには、リモート Powershell でユーザーを有効にする必要があります。 手順については、「[PowerShell へのアクセスを](/powershell/exchange/disable-access-to-exchange-online-powershell)有効または無効にするExchange Online参照してください。

管理者は、検疫ポリシーのグローバル設定を使用して、送信者の表示名、さまざまな言語の免責事項のテキスト、検疫通知で使用される会社のロゴをカスタマイズすることもできます。 手順については、「グローバル検疫通知 [の設定を構成する」を参照してください](quarantine-policies.md#configure-global-quarantine-notification-settings-in-the-microsoft-365-defender-portal)。

共有メールボックスの検疫通知は、共有メールボックスに対する FullAccess アクセス許可が付与されているユーザーにのみサポートされます。 詳細については、「 [EAC を使用して共有メールボックスの委任を編集する」を参照してください](/Exchange/collaboration-exo/shared-mailboxes#use-the-eac-to-edit-shared-mailbox-delegation)。

> [!NOTE]
> 既定では、信頼度の高いフィッシング、マルウェア、メール フロー ルール (トランスポート ルールとも呼ばれる)、または Office 365 用 Defender の セーフ 添付ファイル ポリシーとして検疫されたメッセージは、管理者のみ使用できます (既定では、AdminOnlyAccessPolicy 検疫ポリシーが使用されます)。 詳細については、「[EOP の管理者として検疫済みのメッセージやファイルを管理する](manage-quarantined-messages-and-files.md)」を参照してください。
>
> 現在、検疫通知は、グループや高信頼のフィッシング メッセージではサポートされていません。 

検疫通知を受信すると、検疫されたメッセージごとに次の情報を常に使用できます。

- **送信者**: 検疫済みメッセージの送信名と電子メール アドレス。
- **件名**: 検疫済みメッセージの件名テキスト。
- **日付**: メッセージが検疫された日付と時刻 (UTC)。

検疫通知で使用できるアクションは、メッセージが検疫された理由と、関連付けられた検疫ポリシーによって割り当てられたアクセス許可によって異なる。 詳細については、「検疫ポリシーの [アクセス許可の詳細」を参照してください](quarantine-policies.md#quarantine-policy-permission-details)。

既定では、スパム、高信頼スパム、またはバルクとして検疫されたメッセージの検疫通知で、次のアクションを使用できます。

- **[送信者のブロック**]: メールボックスの [受信拒否] リストに送信者を追加するには、このリンク _をクリック_ します。 詳細については、「[メール送信者をブロックする](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4)」を参照してください。
- **リリース**: メッセージは、このポータルの [検疫]  に移動せずに、ここでMicrosoft 365 Defenderできます。
- **レビュー**: このリンクをクリックすると、Microsoft 365 Defender ポータルの [検疫] に移動し、検疫済みメッセージの表示、リリース、削除、レポートを実行できます (メッセージが検疫された理由に応じて)。 詳細については、「 [EOP で検疫済みメッセージをユーザーとして検索して解放する」を参照してください](find-and-release-quarantined-messages-as-a-user.md)。

:::image type="content" source="../../media/end-user-spam-notification.png" alt-text="検疫通知の例" lightbox="../../media/end-user-spam-notification.png":::

> [!NOTE]
> 送信者がブロックされた場合でも、メールを送信できます。 この送信者からメールボックスに送信されたメッセージは、直ちに迷惑メール フォルダーに移動されます。 この送信者からの今後のメッセージは、迷惑メール フォルダーまたは検疫に移動します。 これらのメッセージを quarantining ではなく、到着時に削除する場合は、メール フロー [ルール (トランスポート](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) ルールとも呼ばれる) を使用して、到着時にメッセージを削除します。
