---
title: ゼロ時間自動削除 (ZAP)
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
ms.custom:
- seo-marvel-apr2020
description: 管理者は、ゼロ時間自動削除 (ZAP) を使用して、Exchange Online メールボックス内の配信されたメッセージを迷惑メールフォルダーに移動する方法、またはスパムまたはフィッシングとして検出された検疫について調べることができます。
ms.openlocfilehash: 643063139f5d65b0271fd14ee5a2d1ca1f42ad1a
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208442"
---
# <a name="zero-hour-auto-purge-zap-in-exchange-online"></a>Exchange Online でのゼロ時間自動削除 (ZAP)

## <a name="overview"></a>概要

Exchange Online のメールボックスを使用する Microsoft 365 組織では、ゼロ時間自動削除 (ZAP) は電子メール保護機能の1つであり、Exchange Online メールボックスに既に配信されている悪意のあるフィッシング、スパム、またはマルウェアメッセージを neutralizes が検出し、それを検出します。

オンプレミスの Exchange メールボックスを保護するスタンドアロンの Exchange Online Protection (EOP) 環境では、ZAP は機能しません。

## <a name="how-zap-works"></a>ZAP のしくみ

スパムとマルウェアの署名は、日単位でサービスのリアルタイムで更新されます。 ただし、ユーザーが配信された後にコンテンツが weaponized されているかどうかなど、さまざまな理由で、ユーザーが悪意のあるメッセージを引き続き受信できます。 ZAP は、スパムおよびマルウェア署名の更新を継続的に監視することによって、この問題に対処します。 ZAP は、ユーザーのメールボックスに既に存在するメッセージを見つけて削除することができます。

ZAP アクションはユーザーにとってシームレスです。メッセージが検出され、移動された場合は通知されません。

[信頼できる差出人のリスト](create-safe-sender-lists-in-office-365.md)、メールフロールール (トランスポートルールとも呼ばれる)、受信トレイルール、または追加フィルターは、ZAP より優先されます。 メールフローの場合と同様に、配信されたメッセージが ZAP する必要があると判断された場合でも、安全な送信者の構成が原因でメッセージが処理されないことを意味します。 これは、フィルター処理をバイパスするようにメッセージを構成するためのもう1つの理由です。

### <a name="malware-zap"></a>マルウェアの ZAP

配信後にマルウェアが含まれていることが検出された**開封済みメッセージまたは未読メッセージ**の場合、ZAP 検疫は、マルウェアの添付ファイルを含むメッセージを検出します。 管理者のみが、検疫からマルウェアメッセージを表示および管理できます。

マルウェア対策ポリシーでは、既定でマルウェアの ZAP が有効になっています。 詳細については、「 [EOP でマルウェア対策ポリシーを構成する](configure-anti-malware-policies.md)」を参照してください。

### <a name="phish-zap"></a>フィッシング ZAP

配信後にフィッシングとして識別される**開封済みメッセージまたは未読メッセージ**の場合、ZAP の結果は、該当するスパム対策ポリシーで**フィッシング電子メール**フィルター verdict に対して構成されているアクションによって決まります。 フィッシングの使用可能なフィルター処理の verdict アクションと、その可能性のある ZAP の結果については、次の一覧で説明します。

- **X-ヘッダー**、**先頭に件名行**を追加する: ZAP はメッセージに対してアクションを実行しません。

- **迷惑メールにメッセージを移動する**: 迷惑メールルールがメールボックスで有効になっていれば (既定で有効になっている場合)、メッセージは迷惑メールフォルダーに移動されます。 詳細については、「 [Microsoft 365 の「Exchange Online メールボックスの迷惑メール設定を構成する](configure-junk-email-settings-on-exo-mailboxes.md)」を参照してください。

- メッセージ**を電子メールアドレス**、**削除メッセージ**、**検疫メッセージ**: ZAP 検疫メッセージにリダイレクトします。

既定では、スパム対策ポリシーではフィッシング ZAP が有効になっており、**フィッシング電子メール**フィルター verdict の既定のアクションは**検疫メッセージ**で、既定ではフィッシング ZAP 検疫メッセージを示します。

スパムフィルター verdicts の構成の詳細については、「 [Microsoft 365 でスパム対策ポリシーを構成する](configure-your-spam-filter-policies.md)」を参照してください。

### <a name="spam-zap"></a>スパム ZAP

配信後にスパムとして識別される**未開封のメッセージ**の場合、ZAP の結果**は、該当**するスパム対策ポリシーの verdict に対して構成されているアクションによって決まります。 スパムに対して使用可能なフィルター処理の verdict アクションと、ZAP の結果については、次の一覧で説明します。

- **X-ヘッダー**、**先頭に件名行**を追加する: ZAP はメッセージに対してアクションを実行しません。

- **迷惑メールにメッセージを移動する**: 迷惑メールルールがメールボックスで有効になっていれば (既定で有効になっている場合)、メッセージは迷惑メールフォルダーに移動されます。 詳細については、「 [Microsoft 365 の「Exchange Online メールボックスの迷惑メール設定を構成する](configure-junk-email-settings-on-exo-mailboxes.md)」を参照してください。

- メッセージ**を電子メールアドレス**、**削除メッセージ**、**検疫メッセージ**: ZAP 検疫メッセージにリダイレクトします。 エンドユーザーは、自分のスパム検疫済みメッセージを表示および管理できます。

既定では、スパム対策ポリシーでスパム ZAP が有効になっており、**スパム**フィルター verdict の既定のアクションが **[迷惑メール] フォルダーに移動**します。この場合、スパム ZAP は**未読**メッセージを迷惑メールフォルダーに既定で移動します。

スパムフィルター verdicts の構成の詳細については、「 [Microsoft 365 でスパム対策ポリシーを構成する](configure-your-spam-filter-policies.md)」を参照してください。

### <a name="zap-considerations-for-office-365-advanced-threat-protection-office-365-atp"></a>Office 365 Advanced Threat Protection の ZAP に関する考慮事項 (Office 365 ATP)

ZAP は、[動的配信](dynamic-delivery-and-previewing.md)スキャンのプロセス内のメッセージを検疫しません。または、マルウェアフィルターによって添付ファイルが既に**マルウェアアラートテキスト .txt**ファイルに置き換えられています。 これらの種類のメッセージに対してフィッシングまたはスパムのシグナルを受信し、スパム対策ポリシーのフィルター verdict がメッセージに対して何らかのアクションを実行するように設定されている場合 ([迷惑メールに移動] に移動します)、ZAP は既定で [迷惑メールに移行] アクションになります。

## <a name="how-to-see-if-zap-moved-your-message"></a>ZAP がメッセージを移動したかどうかを確認する方法

ZAP がメッセージを移動したかどうかを確認するには、[脅威保護状態レポート](view-email-security-reports.md#threat-protection-status-report)または[脅威エクスプローラー (およびリアルタイム検出)](threat-explorer.md)のいずれかを使用できます。 システムアクションとして、ZAP が Exchange メールボックス監査ログに記録されないことに注意してください。

## <a name="zap-faq"></a>ZAP FAQ

### <a name="what-happens-if-a-legitimate-message-is-moved-to-the-junk-email-folder"></a>正当なメッセージが迷惑メールフォルダーに移動された場合はどうなりますか。

誤[検知](report-junk-email-messages-to-microsoft.md)には通常のレポートプロセスに従う必要があります。 メッセージが [受信トレイ] から [迷惑メール] フォルダーに移動されるのは、サービスがスパムまたは悪意のあるメッセージであると判断した場合のみです。

### <a name="what-if-i-use-the-quarantine-folder-instead-of-the-junk-mail-folder"></a>迷惑メールフォルダーではなく、検疫フォルダーを使用している場合はどうなりますか?

ZAP は、このトピックの前半で説明したように、スパム対策ポリシーの構成に基づいてメッセージに対してアクションを実行します。

### <a name="what-if-im-using-safe-senders-mail-flow-rules-or-allowedblocked-sender-lists"></a>差出人セーフリスト、メールフロールール、許可/ブロックされる送信者リストを使用している場合は、どうすればよいですか?

信頼できる差出人、メールフロールール、またはブロックと許可の組織設定が優先されます。 これらのメッセージは、サービスが設定した内容を実行しているため、ZAP から除外されます。 これは、フィルター処理をバイパスするようにメッセージを構成するためのもう1つの理由です。

### <a name="what-if-a-message-is-moved-to-another-folder-eg-inbox-rules"></a>メッセージが別のフォルダー (たとえば、受信トレイルールなど) に移動した場合はどうなりますか。

ZAP は、メッセージが削除されていない場合、または同じまたはより強力なアクションがまだ適用されていない限り、引き続き機能します。 たとえば、フィッシングポリシーが [検疫] に設定されており、ユーザーまたは管理者が既に電子メールを junked している場合、検疫はファイルを検疫する処理を実行します。

### <a name="does-zap-change-the-message-header"></a>メッセージヘッダーを ZAP に変更しますか?

ZAP アクションでは、メッセージヘッダーに対して変更は行われません。

### <a name="how-does-zap-affect-mailboxes-on-hold"></a>ZAP がメールボックスを保留にする方法

ZAP は、保留中のメールボックスからのメッセージを検疫しません。 ZAP は、スパム対策ポリシーでスパムまたはフィッシング verdict に対して構成されたアクションに基づいて、メッセージを [迷惑メール] フォルダーに移動できます。

Exchange Online のホールドの詳細については、「[インプレース保持と訴訟ホールド (Exchange online](https://docs.microsoft.com/Exchange/security-and-compliance/in-place-and-litigation-holds))」を参照してください。
