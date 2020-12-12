---
title: ゼロアワー自動消去 (ZAP)
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
- MBS150
- MET150
ms.assetid: 96deb75f-64e8-4c10-b570-84c99c674e15
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理者は、ゼロアワー自動消去 (ZAP) を使用して、Exchange Online メールボックス内の配信済みメッセージを迷惑メール フォルダーまたは検疫 (スパムまたはフィッシングとして検出された検疫) にさかのぼって移動する方法について説明します。
ms.openlocfilehash: 7b43fb46adacfe1e9f1e7e622122df90e747ff44
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659431"
---
# <a name="zero-hour-auto-purge-zap-in-exchange-online"></a>Exchange Online でのゼロアワー自動消去 (ZAP)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


## <a name="basic-features-of-zap"></a>ZAP の基本的な機能

Exchange Online にメールボックスを持つ Microsoft 365 組織では、ゼロアワー自動消去 (ZAP) は、Exchange Online メールボックスに既に配信されている悪意のあるフィッシング、スパム、またはマルウェア メッセージを検出し、それを防除する電子メール保護機能です。

ZAP は、オンプレミスの Exchange メールボックスを保護するスタンドアロンの Exchange Online Protection (EOP) 環境では動作しません。

## <a name="how-zap-works"></a>ZAP のしくみ

スパムとマルウェアの署名は、サービスで毎日リアルタイムで更新されます。 ただし、ユーザーに配信された後にコンテンツが武器化された場合など、さまざまな理由で悪意のあるメッセージを受け取る可能性があります。 ZAP では、サービス内のスパムおよびマルウェアの署名に対する更新を継続的に監視することで、この問題に取り組まれています。 ZAP は、ユーザーのメールボックスに既に存在するメッセージを検索および削除できます。

ZAP アクションはユーザーにシームレスです。メッセージが検出され、移動された場合は通知されません。

[差出人セーフ](create-safe-sender-lists-in-office-365.md)リスト、メール フロー ルール (トランスポート ルールとも呼ばれる)、受信トレイ ルール、または追加フィルターが ZAP よりも優先されます。 メール フローでの処理と同様に、これは、サービスが配信されたメッセージに ZAP が必要と判断した場合でも、差出人セーフ リストの構成のためにメッセージが処理されないという意味です。 これは、フィルター処理をバイパスするメッセージの構成に注意するもう 1 つの理由です。

### <a name="malware-zap"></a>マルウェア ZAP

配信 **後にマルウェア** が含まれていると見つかった読み取りメッセージまたは未読メッセージの場合、ZAP はマルウェアの添付ファイルを含むメッセージを検疫します。 管理者だけが検疫からのマルウェア メッセージを表示および管理できます。

マルウェア ZAP は、マルウェア対策ポリシーで既定で有効になっています。 詳細については [、「EOP でマルウェア対策ポリシーを構成する」を参照してください](configure-anti-malware-policies.md)。

### <a name="phish-zap"></a>フィッシング ZAP

配信 **後** にフィッシングとして識別される読み取りメッセージまたは未読メッセージの場合、ZAP の結果は、該当するスパム対策ポリシーのフィッシング メール フィルターの決定に対して構成されているアクションによって異なります。 フィッシングに対して使用可能なフィルター処理の決定アクションと、それらの ZAP の結果について、次の一覧で説明します。

- **X-Header を追加** し **、件名行の先頭にテキストを** 追加します。ZAP はメッセージに対してアクションを実行します。

- **[迷惑メールに** メッセージを移動する]: ZAP は、メールボックスで迷惑メール ルールが有効になっている限り (既定で有効になっている) 限り、メッセージを [迷惑メール] フォルダーに移動します。 詳細については [、「Microsoft 365 の Exchange Online メールボックスで迷惑メール](configure-junk-email-settings-on-exo-mailboxes.md)設定を構成する」を参照してください。

- **電子メール アドレスへのメッセージのリダイレクト**、 **メッセージの削除**、 **メッセージの検疫**: ZAP はメッセージを検疫します。

既定では、フィッシング ZAP はスパム対策ポリシーで有効にされ、フィッシング メールフィルターの条件に対する既定のアクションは検疫メッセージです。これは、フィッシング ZAP が既定でメッセージを検疫します。

スパム フィルターの条件の構成の詳細については [、「Microsoft 365](configure-your-spam-filter-policies.md)でスパム対策ポリシーを構成する」を参照してください。

### <a name="spam-zap"></a>スパム ZAP

配信 **後** にスパムとして識別される未読メッセージの場合、ZAP の結果は、該当するスパム対策ポリシーのスパムフィルターの決定に対して構成されているアクションによって異なります。 スパムに対して使用可能なフィルター処理の決定アクションと、それらの ZAP の結果について、次の一覧で説明します。

- **X-Header を追加** し **、件名行の先頭にテキストを** 追加します。ZAP はメッセージに対してアクションを実行します。

- **メッセージを [** 迷惑メール] に移動する : ZAP は、メールボックスで迷惑メール ルールが有効になっている限り、メッセージを [迷惑メール] フォルダーに移動します (既定では有効になっています)。 詳細については [、「Microsoft 365 の Exchange Online メールボックスで迷惑メール](configure-junk-email-settings-on-exo-mailboxes.md)設定を構成する」を参照してください。

- **電子メール アドレスへのメッセージのリダイレクト**、 **メッセージの削除**、 **メッセージの検疫**: ZAP はメッセージを検疫します。 エンドユーザーは、独自のスパム検疫済みメッセージを表示および管理できます。

既定では、スパム ZAP はスパム対策ポリシーで有効にされ、スパム フィルターの条件の既定のアクションは[迷惑メール] フォルダーにメッセージを移動します。つまり、スパム ZAP は既定で未読のメッセージを [迷惑メール] フォルダーに移動します。 

スパム フィルターの条件の構成の詳細については [、「Microsoft 365](configure-your-spam-filter-policies.md)でスパム対策ポリシーを構成する」を参照してください。

### <a name="zap-considerations-for-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 の ZAP に関する考慮事項

ZAP は、安全な添付ファイルのスキャンで動的配信 [](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies)の過程にあるメッセージや、EOP マルウェア フィルター処理によって添付ファイルが既に **Malware Alert Text.txt** ファイルに置き換えられたメッセージは検疫されません。 これらの種類のメッセージに対してフィッシングまたはスパムシグナルが受信され、スパム対策ポリシーのフィルター処理の条件がメッセージに対して何らかのアクション ([迷惑メールへの移動]、[リダイレクト]、[削除]、または [検疫]) に設定されている場合、ZAP は既定で [迷惑メールに移動] アクションに設定されます。

## <a name="how-to-see-if-zap-moved-your-message"></a>ZAP がメッセージを移動したのか確認する方法

ZAP がメッセージを移動したかどうかを確認するには [、Threat Protection の](view-email-security-reports.md#threat-protection-status-report) 状態レポートまたは脅威エクスプローラー (およびリアルタイムの検出) [を使用します](threat-explorer.md)。 システム操作として、ZAP は Exchange メールボックス監査ログに記録されません。

## <a name="zap-faq"></a>ZAP FAQ

### <a name="what-happens-if-a-legitimate-message-is-moved-to-the-junk-email-folder"></a>正当なメッセージが迷惑メール フォルダーに移動された場合は、どうなるでしょうか。

誤検知については、通常の報告 [プロセスに従う必要があります](report-junk-email-messages-to-microsoft.md)。 メッセージが受信トレイから迷惑メール フォルダーに移動される唯一の理由は、サービスがメッセージがスパムまたは悪意のあるメッセージと判断したためです。

### <a name="what-if-i-use-the-quarantine-folder-instead-of-the-junk-mail-folder"></a>迷惑メール フォルダーの代わりに検疫フォルダーを使用した場合

ZAP は、この記事で前述したスパム対策ポリシーの構成に基づいて、メッセージに対してアクションを実行します。

### <a name="what-if-im-using-safe-senders-mail-flow-rules-or-allowedblocked-sender-lists"></a>差出人セーフ リスト、メール フロー ルール、許可/受信拒否リストを使用している場合は、どうなるでしょうか。

差出人セーフ リスト、メール フロー ルール、または組織の設定のブロックと許可が優先されます。 これらのメッセージは、サービスが構成した処理を行っているので、ZAP から除外されます。 これは、フィルター処理をバイパスするメッセージの構成に注意するもう 1 つの理由です。

### <a name="what-if-a-message-is-moved-to-another-folder-eg-inbox-rules"></a>メッセージが別のフォルダー (受信トレイ ルールなど) に移動された場合は、どうでしょうか。

ZAP は、メッセージが削除されていない限り、または同じ、またはより強力なアクションがまだ適用されていない限り、引き続き機能します。 たとえば、フィッシング対策ポリシーが検疫に設定され、メッセージが既に迷惑メール内にある場合、ZAP はメッセージを検疫するアクションを実行します。

### <a name="how-does-zap-affect-mailboxes-on-hold"></a>ZAP が保持中のメールボックスに与える影響

ZAP は、保持中のメールボックスからメッセージを検疫しません。 ZAP は、スパム対策ポリシーでスパムまたはフィッシングの確認に対して構成されたアクションに基づいて、メッセージを [迷惑メール] フォルダーに移動できます。

Exchange Online の保留の詳細については、「Exchange Online のインホールドと訴訟ホールド」を [参照してください](https://docs.microsoft.com/Exchange/security-and-compliance/in-place-and-litigation-holds)。
