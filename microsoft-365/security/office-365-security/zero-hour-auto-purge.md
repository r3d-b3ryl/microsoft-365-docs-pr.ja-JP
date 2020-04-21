---
title: ゼロ時間自動削除 (ZAP)-スパム、マルウェア、フィッシングからの retroactive 保護。
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
- MBS150
- MET150
ms.assetid: 96deb75f-64e8-4c10-b570-84c99c674e15
ms.collection:
- M365-security-compliance
description: ゼロ時間自動削除 (ZAP) は、Microsoft 365 の電子メール保護機能であり、Exchange Online に既に配信されているスパム、マルウェア、またはフィッシングメッセージを検出します。 これは、検出された悪意のあるコンテンツの種類によってどのような違いがありますか。
ms.openlocfilehash: a819269d8596f12e76cbd17b5d1302cd56837f14
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43630811"
---
# <a name="zero-hour-auto-purge-zap---protection-against-spam-and-malware-in-microsoft-365"></a>ゼロ時間自動削除 (ZAP)-Microsoft 365 でのスパムおよびマルウェアからの保護

## <a name="overview"></a>概要

ゼロ時間自動削除 (ZAP) は、Microsoft 365 の電子メール保護機能で、Exchange Online メールボックスに既に配信されている悪意のあるフィッシング、スパム、またはマルウェアメッセージをさかのぼって検出し、neutralizes します。

ZAP は、Exchange Online メールボックスを含む Microsoft 365 サブスクリプションに含まれている既定の Exchange Online Protection (EOP) で使用できます。 ZAP は、オンプレミスの Exchange メールボックスを保護するスタンドアロンの EOP 環境では機能しません。

## <a name="how-zap-works"></a>ZAP のしくみ

Microsoft 365 は、毎日リアルタイムでスパムおよびマルウェアの署名を更新します。 ただし、ユーザーが配信された後にコンテンツが weaponized されているかどうかなど、さまざまな理由で、ユーザーが悪意のあるメッセージを引き続き受信できます。 ZAP は、Microsfot 365 スパムおよびマルウェア署名の更新を継続的に監視することによって、この問題に対処します。 ZAP は、ユーザーのメールボックスに既に存在するメッセージを見つけて削除することができます。

ZAP アクションはユーザーにとってシームレスです。メッセージが検出され、移動された場合は通知されません。

[信頼できる差出人のリスト](create-safe-sender-lists-in-office-365.md)、メールフロールール (トランスポートルールとも呼ばれる)、受信トレイルール、または追加フィルターは、ZAP より優先されます。

### <a name="malware-zap"></a>マルウェアの ZAP

配信後にマルウェアが含まれていることが検出された**開封済みメッセージまたは未読メッセージ**の場合、ZAP 検疫は、マルウェアの添付ファイルを含むメッセージを検出します。 管理者のみが、検疫からマルウェアメッセージを表示および管理できます。

マルウェア対策ポリシーでは、既定でマルウェアの ZAP が有効になっています。 詳細については、「 [Microsoft 365 でマルウェア対策ポリシーを構成する](configure-anti-malware-policies.md)」を参照してください。

### <a name="phish-zap"></a>フィッシング ZAP

配信後にフィッシングとして識別される**開封済みメッセージまたは未読メッセージ**の場合、ZAP の結果は、該当するスパム対策ポリシーで**フィッシング電子メール**フィルター verdict に対して構成されているアクションによって決まります。 フィッシングの使用可能なフィルター処理の verdict アクションと、その可能性のある ZAP の結果については、次の一覧で説明します。

- **X-ヘッダー**、**先頭に件名行**を追加する: ZAP はメッセージに対してアクションを実行しません。

- **迷惑メールにメッセージを移動する**: 迷惑メールルールがメールボックスで有効になっていれば (既定で有効になっている場合)、メッセージは迷惑メールフォルダーに移動されます。 詳細については、「 [Microsoft 365 の「Exchange Online メールボックスの迷惑メール設定を構成する](configure-junk-email-settings-on-exo-mailboxes.md)」を参照してください。

- メッセージ**を電子メールアドレス**、**削除メッセージ**、**検疫メッセージ**: ZAP 検疫メッセージにリダイレクトします。 管理者のみが、フィッシング検疫済みメッセージを表示および管理できます。

既定では、スパム対策ポリシーではフィッシング ZAP が有効になっており、**フィッシング電子メール**フィルター verdict の既定のアクションは**検疫メッセージ**で、既定ではフィッシング ZAP 検疫メッセージを示します。

スパムフィルター verdicts の構成の詳細については、「 [Microsoft 365 でスパム対策ポリシーを構成する](configure-your-spam-filter-policies.md)」を参照してください。

### <a name="spam-zap"></a>スパム ZAP

配信後にスパムとして識別される**未開封のメッセージ**の場合、ZAP の結果**は、該当**するスパム対策ポリシーの verdict に対して構成されているアクションによって決まります。 スパムに対して使用可能なフィルター処理の verdict アクションと、ZAP の結果については、次の一覧で説明します。

- **X-ヘッダー**、**先頭に件名行**を追加する: ZAP はメッセージに対してアクションを実行しません。

- **迷惑メールにメッセージを移動する**: 迷惑メールルールがメールボックスで有効になっていれば (既定で有効になっている場合)、メッセージは迷惑メールフォルダーに移動されます。 詳細については、「 [Microsoft 365 の「Exchange Online メールボックスの迷惑メール設定を構成する](configure-junk-email-settings-on-exo-mailboxes.md)」を参照してください。

- メッセージ**を電子メールアドレス**、**削除メッセージ**、**検疫メッセージ**: ZAP 検疫メッセージにリダイレクトします。 エンドユーザーは、自分のスパム検疫済みメッセージを表示および管理できます。

既定では、スパム対策ポリシーでスパム ZAP が有効になっており、**スパム**フィルター verdict の既定のアクションが **[迷惑メール] フォルダーに移動**します。この場合、スパム ZAP は**未読**メッセージを迷惑メールフォルダーに既定で移動します。

スパムフィルター verdicts の構成の詳細については、「 [Microsoft 365 でスパム対策ポリシーを構成する](configure-your-spam-filter-policies.md)」を参照してください。

### <a name="zap-considerations-for-office-365-advanced-threat-protection-atp"></a>Office 365 Advanced Threat Protection (ATP) に関する ZAP に関する考慮事項

ZAP は、[動的配信](dynamic-delivery-and-previewing.md)スキャンのプロセス内のメッセージを検疫しません。または、マルウェアフィルターによって添付ファイルが既に**マルウェアアラートテキスト .txt**ファイルに置き換えられています。 これらの種類のメッセージに対してフィッシングまたはスパムのシグナルを受信し、スパム対策ポリシーのフィルター verdict がメッセージに対して何らかのアクションを実行するように設定されている場合 ([迷惑メールに移動] に移動します)、ZAP は既定で [迷惑メールに移行] アクションになります。

## <a name="how-to-see-if-zap-moved-your-message"></a>ZAP がメッセージを移動したかどうかを確認する方法

ZAP がメッセージを移動したかどうかを確認するには、[脅威保護状態レポート](view-email-security-reports.md#threat-protection-status-report)または[脅威エクスプローラー (およびリアルタイム検出)](threat-explorer.md)のいずれかを使用できます。 システムアクションとして、ZAP が Exchange メールボックス監査ログに記録されないことに注意してください。

## <a name="zap-faq"></a>ZAP FAQ

### <a name="q-what-happens-if-a-legitimate-message-is-moved-to-the-junk-email-folder"></a>Q: 正当なメッセージが迷惑メールフォルダーに移動された場合はどうなりますか。

A: 誤[検知](report-junk-email-messages-to-microsoft.md)に対して通常のレポートプロセスに従う必要があります。 メッセージが [受信トレイ] から [迷惑メール] フォルダーに移動されるのは、サービスがスパムまたは悪意のあるメッセージであると判断した場合のみです。

### <a name="q-what-if-i-use-the-quarantine-folder-instead-of-the-junk-mail-folder"></a>Q: 迷惑メールフォルダーではなく、検疫フォルダーを使用している場合はどうすればよいですか。

A: ZAP は、このトピックで前述したように、スパム対策ポリシーの構成に基づいてメッセージに対してアクションを実行します。

### <a name="q-what-if-im-using-mail-flow-rules-or-allowedblocked-sender-lists"></a>Q: メールフロールールまたは許可/ブロックされた送信者の一覧を使用している場合はどうすればよいですか。

A: メールフロールールまたは [組織設定の禁止] と [許可] が優先されます。 これらのメッセージは ZAP から除外されます。

### <a name="q-what-if-a-message-is-moved-to-another-folder-eg-inbox-rules"></a>Q: メッセージが別のフォルダー (たとえば、受信トレイルールなど) に移動した場合はどうなりますか?

A: 問題なく、メッセージが削除されていない場合、または同じまたはより強力なアクションがまだ適用されていない場合に限り、このまま動作します。 たとえば、フィッシングポリシーが [検疫] に設定されており、ユーザーまたは管理者が既に電子メールを junked している場合、検疫はファイルを検疫する処理を実行します。

### <a name="q-does-zap-change-the-message-header"></a>Q: メッセージヘッダーは ZAP によって変更されますか?

A: ZAP アクションは、メッセージヘッダーに変更を加えません。

### <a name="q-how-does-zap-affect-mailboxes-on-hold"></a>Q: どのようにして、ZAP がメールボックスを保留にするのですか?

A: ZAP は、保留中のメールボックスからメッセージを検疫しません。 ZAP は、スパム対策ポリシーでスパムまたはフィッシング verdict に対して構成されたアクションに基づいて、メッセージを [迷惑メール] フォルダーに移動できます。

Exchange Online のホールドの詳細については、「[インプレース保持と訴訟ホールド (Exchange online](https://docs.microsoft.com/Exchange/security-and-compliance/in-place-and-litigation-holds))」を参照してください。
