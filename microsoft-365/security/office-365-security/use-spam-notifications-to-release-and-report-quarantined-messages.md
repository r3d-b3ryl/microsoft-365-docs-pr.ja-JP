---
title: Microsoft 365 での検疫通知 (エンド ユーザーのスパム通知)
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
description: 管理者は、Exchange Online Protection (EOP) で検疫されたメッセージのエンドユーザーのスパム通知について学ぶことができます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 44ed83a95fe8f588369f0a1bbae4809f32581f87
ms.sourcegitcommit: a7c1acfb3d2cbba913e32493b16ebd8cbfeee456
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/13/2022
ms.locfileid: "66043491"
---
# <a name="use-quarantine-notifications-to-release-and-report-quarantined-messages"></a>検疫通知を使用して検疫済みメッセージを解放および報告する

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Exchange Online のメールボックスを使用している Microsoft 365 組織または Exchange Online のメールボックスを使用していないスタンドアロンの Exchange Online Protection (EOP) 組織では、危険な可能性があるメッセージまたは不要なメッセージは検疫済みメッセージとして保留されます。 詳細については、「[EOP で検疫されたメッセージ](quarantine-email-messages.md)」を参照してください。

_検疫ポリシー_ により、(サポートされている機能で) メッセージが検疫された理由に基づいて、検疫済みメッセージに対してユーザーが実行できる操作を定義します。 詳細については、「[検疫ポリシー](quarantine-policies.md)」を参照してください。 また、検疫ポリシーは、影響を受ける受信者 (共有メールボックスを含む) が、検疫されたメッセージに関する定期的な _検疫通知_ を受け取るかどうかを制御します。 検疫通知は、サポートされているすべての保護機能 (迷惑メール対策ポリシーの評定には限りません) のエンドユーザーのスパム通知の代替措置になります。

検疫通知は、AdminOnlyAccessPolicy または DefaultFullAccessPolicy という名前の組み込みの検疫通知ではオンになっていません。 検疫通知は、NotificationEnabledPolicy という名前の組み込みの検疫ポリシーでオンになります ([組織で設定されている場合](quarantine-policies.md#full-access-permissions-and-quarantine-notifications))。 それ以外の場合、検疫ポリシーで検疫通知をオンにするには、[新しい検疫ポリシーを作成し、構成する](quarantine-policies.md#step-1-create-quarantine-policies-in-the-microsoft-365-defender-portal)必要があります。

また、検疫通知における '送信者をブロック' オプションが正しく機能するように、ユーザーがリモート Powershell を有効にする必要があります。 手順については、「[Exchange Online PowerShell へのアクセスを有効または無効にする](/powershell/exchange/disable-access-to-exchange-online-powershell)」を参照してください。

管理者は、検疫ポリシーのグローバル設定を使用して、送信者の表示名、さまざまな言語での免責事項テキスト、検疫通知で使用する企業ロゴをカスタマイズすることもできます。 手順については、「[グローバル検疫通知設定の構成](quarantine-policies.md#configure-global-quarantine-notification-settings-in-the-microsoft-365-defender-portal)」を参照してください。

共有メールボックスの場合、検疫通知は、共有メールボックスの FullAccess アクセス許可が付与されているユーザーのみサポートされています。 詳細については、「[EAC を使用して共有メールボックスの委任を編集する](/Exchange/collaboration-exo/shared-mailboxes#use-the-eac-to-edit-shared-mailbox-delegation)」を参照してください。

> [!NOTE]
> Defender for Office 365 で、メール フロー ルール (トランスポート ルールとも呼ばれます) または安全な添付ファイル ポリシーによって、高確度のフィッシング、マルウェアとして検疫されたメッセージは、既定では管理者のみが利用できます (既定では、AdminOnlyAccessPolicy 検疫ポリシーが使用されます)。 詳細については、「[EOP の管理者として検疫済みのメッセージやファイルを管理する](manage-quarantined-messages-and-files.md)」を参照してください。
>
> 配信グループまたはメール対応セキュリティ グループに送信されたメッセージの検疫通知は、すべてのグループ メンバーに送信されます。
>
> Microsoft 365 グループに送信されたメッセージの検疫通知は、「**グループの会話とイベントのコピーをグループ メンバーに送信する**」設定がオンになっている場合のみ、すべてのグループ メンバーに送信されます。

検疫通知を受信すると、検疫されたメッセージごとに次の情報が常に表示されます。

- **送信者**: 検疫されたメッセージの送信者名とメール アドレス。
- **件名**: 検疫されたメッセージの件名行のテキスト。
- **日付**: メッセージが検疫された日時 (UTC)。

検疫通知で使用できるアクションは、メッセージが検疫された理由と、関連する検疫ポリシーによって割り当てられたアクセス許可によって異なります。 詳細については、「[検疫ポリシーのアクセス許可の詳細](quarantine-policies.md#quarantine-policy-permission-details)」を参照してください。

既定では、迷惑メール、高確度迷惑メール、または一括で検疫されたメッセージの検疫通知で以下のアクションが利用可能です。

- **送信者のブロック**: このリンクをクリックして、_メールボックス_ の [ブロックされた送信者] リストに送信者を追加します。 詳細については、「[メール送信者をブロックする](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4)」を参照してください。
- **解放**: Microsoft 365 Defender ポータルの **[検疫]** に移動することなく、ここでメッセージを解放できます。
- **レビュー**: このリンクをクリックして Microsoft 365 Defender ポータルの **[検疫]** に移動し、(メッセージが検疫された理由に応じて) 検疫されたメッセージの表示、解放、削除、報告を行うことができます。 詳細については、「[EOP のユーザーによる検閲済みメッセージの検出と解放](find-and-release-quarantined-messages-as-a-user.md)」を参照してください。

:::image type="content" source="../../media/end-user-spam-notification.png" alt-text="検疫通知の例" lightbox="../../media/end-user-spam-notification.png":::

> [!NOTE]
> ブロックされた送信者は、引き続きメールを送信できます。 この送信者からのメッセージがメールボックスに届くと、すぐに迷惑メール フォルダーに移動されます。 今後、この送信者からのメッセージは、迷惑メール フォルダーまたは検疫に移動されます。 これらのメッセージを検疫するのではなく、到着時に削除したい場合は、[メール フロー ルール](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (トランスポート ルールとも呼ばれます) を使用して到着時にメッセージを削除します。
