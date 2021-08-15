---
title: Microsoft Defender で 0 時間の自動削除を実行Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 06/22/2021
audience: Admin
ms.topic: conceptual
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
description: ゼロ時間自動削除 (ZAP) は、Exchange Online メールボックス内の配信されたメッセージを迷惑メール フォルダーまたは検疫にさかのぼって移動し、配信後にスパムやフィッシングと見なされます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 50dddd695181cb3069d517cdc6bea4d5a0ef80580f0703907c821082069b7152
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "56884522"
---
# <a name="zero-hour-auto-purge-zap-in-exchange-online"></a>ゼロ時間自動削除 (ZAP) (Exchange Online

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

## <a name="zero-hour-auto-purge-zap-basics"></a>ゼロ時間自動削除 (ZAP) の基本

Exchange Online のメールボックスを持つ Microsoft 365 組織では、ゼロ時間自動削除 (ZAP) は、Exchange Online メールボックスに既に配信されている悪意のあるフィッシング、スパム、マルウェア メッセージをさかのぼって検出し、中和する電子メール保護機能です。

ZAP は、オンプレミスのメールボックスを保護するスタンドアロン Exchange Online Protection (EOP) 環境Exchangeしません。

## <a name="how-zap-works"></a>ZAP のしくみ

スパムやマルウェアの署名は、サービス内で毎日リアルタイムで更新されます。 ただし、ユーザーに配信された後にコンテンツが武器化される場合など、さまざまな理由で悪意のあるメッセージを受け取る可能性があります。 ZAP は、サービス内のスパムとマルウェアの署名に対する更新プログラムを継続的に監視することで、この問題に取り組む。 ZAP は、ユーザーのメールボックスに既に存在するメッセージを見つけて削除できます。

ZAP アクションはユーザーにシームレスです。メッセージが検出および移動された場合は、通知されません。

[セーフリスト、](create-safe-sender-lists-in-office-365.md)メール フロー ルール (トランスポート ルールとも呼ばれる)、受信トレイ ルール、または追加のフィルターが ZAP よりも優先されます。 メール フローで発生する処理と同様に、これは、サービスが配信されたメッセージに ZAP が必要と判断した場合でも、差出人セーフ リストの構成のためにメッセージが処理されないことを意味します。 これは、フィルター処理をバイパスするメッセージの構成に注意するもう 1 つの理由です。

### <a name="zero-hour-auto-purge-zap-for-malware"></a>マルウェアのゼロ時間自動削除 (ZAP)

配信 **後にマルウェアが含まれている** と判明した読み取りメッセージまたは未読メッセージの場合、ZAP はマルウェア添付ファイルを含むメッセージを検疫します。 検疫からマルウェア メッセージを表示および管理できるのは管理者のみです。

マルウェアに対する ZAP は、マルウェア対策ポリシーで既定で有効になっています。 詳細については [、「EOP でマルウェア対策ポリシーを構成する」を参照してください](configure-anti-malware-policies.md)。

### <a name="zero-hour-auto-purge-zap-for-phishing"></a>フィッシングのゼロ時間自動削除 (ZAP)

配信後 **に** フィッシングとして識別される読み取りメッセージまたは未読メッセージの場合、ZAP の結果は、該当するスパム対策ポリシーのフィッシングメール フィルターの評決に対して構成されたアクションによって異なります。 フィッシングに対して使用可能なフィルター処理の評決アクションと、可能な ZAP 結果については、次の一覧で説明します。

- **X-Header**、テキスト付 **き** 件名行の先頭に追加 **する、メッセージ** を電子メール アドレスにリダイレクト **する、メッセージ** を削除する: ZAP はメッセージに対してアクションを実行しない。

- **メッセージを迷惑メールに** 移動する: ZAP は、メールボックスで迷惑メール ルールが有効になっている限り、メッセージを迷惑メール フォルダーに移動します (既定で有効になっています)。 詳細については、「迷惑メールの[設定を構成する」を参照Exchange OnlineのメールボックスMicrosoft 365。](configure-junk-email-settings-on-exo-mailboxes.md)

- **検疫メッセージ**: ZAP はメッセージを検疫します。

既定では、スパム対策ポリシーでフィッシングの ZAP が有効にされ、フィッシングメール フィルターの既定のアクションは検疫メッセージです。つまり、フィッシング検疫の ZAP は既定でメッセージを検疫します。

スパム フィルターの評決を構成する方法の詳細については、「[スパム](configure-your-spam-filter-policies.md)対策ポリシーを構成する」を参照Microsoft 365。

### <a name="zero-hour-auto-purge-zap-for-high-confidence-phishing"></a>信頼性の高いフィッシングのためのゼロ時間自動削除 (ZAP)

配信 **後に高信頼** フィッシングとして識別される読み取りメッセージまたは未読メッセージの場合、ZAP はメッセージを検疫します。 検疫からの信頼度の高いフィッシング メッセージを表示および管理できるのは管理者のみです。

信頼度の高いフィッシングの ZAP は既定で有効になっています。 詳細については、「Secure [by Default in Office 365」を参照してください](secure-by-default.md)。

### <a name="zero-hour-auto-purge-zap-for-spam"></a>スパムのゼロ時間自動削除 (ZAP)

配信 **後に** スパムとして識別される未読メッセージの場合、ZAP の結果は、該当するスパム対策ポリシーのスパムフィルターの評決に対して構成されているアクションによって異なります。 スパムに対して使用可能なフィルター処理の評決アクションと、その可能な ZAP 結果については、次の一覧で説明します。

- **X-Header**、テキスト付 **き** 件名行の先頭に追加 **する、メッセージ** を電子メール アドレスにリダイレクト **する、メッセージ** を削除する: ZAP はメッセージに対してアクションを実行しない。

- **メッセージを迷惑メールに** 移動する: ZAP は、メールボックスで迷惑メール ルールが有効になっている限り、メッセージを迷惑メール フォルダーに移動します (既定で有効になっています)。 詳細については、「迷惑メールの[設定を構成する」を参照Exchange OnlineのメールボックスMicrosoft 365。](configure-junk-email-settings-on-exo-mailboxes.md)

- **検疫メッセージ**: ZAP はメッセージを検疫します。 エンド ユーザーは、独自のスパム検疫済みメッセージを表示および管理できます。

既定では、スパム ZAP はスパム対策ポリシーで有効にされ、スパム フィルターの評決の既定のアクションは[メッセージを迷惑メール フォルダーに移動する]です。つまり、スパム ZAP は既定で未読メッセージを迷惑メール フォルダーに移動します。 

スパム フィルターの評決を構成する方法の詳細については、「[スパム](configure-your-spam-filter-policies.md)対策ポリシーを構成する」を参照Microsoft 365。

### <a name="zero-hour-auto-purge-zap-considerations-for-microsoft-defender-for-office-365"></a>Microsoft Defender のゼロ時間自動削除 (ZAP) に関する考慮事項 (Office 365

ZAP は、セーフ 添付ファイルのスキャンで動的配信 [](safe-attachments.md#dynamic-delivery-in-safe-attachments-policies)の過程にあるメッセージや、EOP マルウェア フィルターによって既に添付ファイルをマルウェア アラート Text.txtファイル **に置き** 換えたメッセージは検疫されません。 このような種類のメッセージに対してフィッシングまたはスパム信号が受信され、スパム対策ポリシーのフィルター処理の評決がメッセージに対して何らかのアクション (迷惑メールへの移動、リダイレクト、削除、または検疫) に設定されている場合、ZAP は既定で [迷惑メールに移動] アクションに設定されます。

## <a name="how-to-see-if-zap-moved-your-message"></a>ZAP がメッセージを移動した場合の確認方法

ZAP がメッセージを移動したかどうかを確認するには、脅威保護[](view-email-security-reports.md#threat-protection-status-report)状態レポートまたは脅威エクスプローラー (およびリアルタイムの検出) を[使用します](threat-explorer.md)。 システム アクションとして、ZAP はメールボックス監査ログのExchangeされません。

## <a name="zero-hour-auto-purge-zap-faq"></a>ゼロ時間自動削除 (ZAP) FAQ

### <a name="what-happens-if-a-legitimate-message-is-moved-to-the-junk-email-folder"></a>正当なメッセージが迷惑メール フォルダーに移動された場合は、どうなるでしょうか。

誤検知については、通常の報告プロセス [に従う必要があります](report-junk-email-messages-to-microsoft.md)。 メッセージが受信トレイから迷惑メール フォルダーに移動される唯一の理由は、サービスがメッセージがスパムまたは悪意のあると判断したためです。

### <a name="what-if-i-use-the-quarantine-folder-instead-of-the-junk-mail-folder"></a>迷惑メール フォルダーの代わりに検疫フォルダーを使用する場合は、

ZAP は、この記事で前述したように、スパム対策ポリシーの構成に基づいてメッセージに対してアクションを実行します。

### <a name="what-if-im-using-safe-senders-mail-flow-rules-or-allowedblocked-sender-lists"></a>差出人セーフ リスト、メール フロー ルール、許可またはブロックされた送信者リストを使用している場合は、

セーフ、メール フロー ルール、またはブロックし、組織の設定が優先されます。 これらのメッセージは、サービスが構成した処理を実行しているから ZAP から除外されます。 これは、フィルター処理をバイパスするメッセージの構成に注意するもう 1 つの理由です。

### <a name="what-are-the-licensing-requirements-for-zero-hour-auto-purge-zap-to-work"></a>ゼロ時間自動削除 (ZAP) のライセンス要件は何ですか?

ライセンスに制限はありません。 ZAP は、オンライン上でホストされているExchange動作します。 ZAP は、オンプレミスのメールボックスを保護するスタンドアロン Exchange Online Protection (EOP) 環境Exchangeしません。

### <a name="what-if-a-message-is-moved-to-another-folder-eg-inbox-rules"></a>メッセージが別のフォルダー (受信トレイ ルールなど) に移動された場合は、どうしますか。

ゼロ時間自動削除は、メッセージが削除されていない限り、または同じ、またはより強力なアクションがまだ適用されていない限り、引き続き機能します。 たとえば、フィッシング対策ポリシーが検疫に設定され、メッセージが既に迷惑メール内にある場合、ZAP はメッセージを検疫するアクションを実行します。

### <a name="how-does-zap-affect-mailboxes-on-hold"></a>ZAP は、保留メールボックスにどのような影響を与えるのですか?

0 時間の自動削除では、保留のメールボックスからメッセージが検疫されます。 ZAP は、スパム対策ポリシーでスパムまたはフィッシングの評決用に構成されたアクションに基づいて、メッセージを迷惑メール フォルダーに移動できます。

インプレイス 保持と訴訟ホールドの詳細Exchange Online、インプレイス保持と訴訟ホールドを参照[Exchange Online。](/Exchange/security-and-compliance/in-place-and-litigation-holds)
