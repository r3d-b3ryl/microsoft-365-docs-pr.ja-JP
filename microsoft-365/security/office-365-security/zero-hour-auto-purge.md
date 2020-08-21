---
title: ゼロアハンド消去 (ZAP)
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
description: 管理者は、ゼロア自動消去 (ZAP) が、Exchange Online メールボックス内の配信メッセージを、スパムやフィッシングとして再アクティブに見つかった [迷惑メール] フォルダーまたは検疫に、どのように再トロビードで移動できるかを学習できます。
ms.openlocfilehash: 9096486ed98657fede7927089592c92fffdad70e
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826699"
---
# <a name="zero-hour-auto-purge-zap-in-exchange-online"></a>Exchange Online のゼロアハル自動消去 (ZAP)

## <a name="basic-features-of-zap"></a>ZAP の基本機能

Exchange Online にメールボックスがある Microsoft 365 組織では、ゼロアフォージョン自動消去 (ZAP) は、Exchange Online のメールボックスに配信済みの悪意のあるフィッシング、スパム、またはマルウェアのメッセージを再期的に検出して neutralizeするメール保護機能です。

ZAP は、オンプレミスの Exchange メールボックスを保護するスタンドアロン Exchange Online Protection (EOP) 環境では機能しません。

## <a name="how-zap-works"></a>ZAP のしくみ

スパムとマルウェアのシグネチャは、サービスのリアルタイムで日単位で更新されます。 ただし、ユーザーに配信された後にコンテンツが統合されている場合など、さまざまな理由で悪意のあるメッセージをユーザーが受信する可能性があります。 ZAP は、サービスのスパムシグネチャとマルウェア シグネチャの更新をさらに監視して、この問題に対し対応します。 ZAP は、ユーザーのメールボックスに既に存在するメッセージを検索して削除できます。

ZAP アクションは、ユーザーに対してシームレスです。メッセージが検出され、移動された場合は通知されません。

[差出人セ](create-safe-sender-lists-in-office-365.md)ーフ リスト、メール フロー ルール (トランスポート ルールとも呼ばれる)、受信トレイ ルール、または他のフィルターは ZAP より優先されます。 これはメール フローで起きうのと同様に、サービスで配信されたメッセージが ZAP を必要であると判断しても、信頼できる差出人の構成が原因でメッセージが処理されなけれないことを意味します。 フィルター処理をバイパスするメッセージの構成に関しては、このエラーが発生する可能性があります。

### <a name="malware-zap"></a>マルウェア ZAP

配信 **後にマルウェアを含むことが** 検出される読み取りまたは未読メッセージについては、ZAP がマルウェア添付ファイルを含むメッセージを検疫します。 検疫からマルウェア メッセージを表示および管理できるのは管理者のみです。

マルウェア対策ポリシーでは、マルウェア ZAP が既定で有効になっています。 詳細については [、EOP でマルウェア対策ポリシーを構成する」を参照してください](configure-anti-malware-policies.md)。

### <a name="phish-zap"></a>フィッシング ZAP

配信 **後フィッシング** として識別される開かれていたメッセージまたは未読メッセージの ZAP の結果は、適用可能なスパム対策ポリシーで **フィ** ッシングメール フィルターしか diinct に構成されるアクションによって異なります。 フィッシングに使用できるフィルターしきい値と ZAP 結果に対して使用可能なフィルター操作を次の一覧に示します。

- **X-Header、件****名行の前にテキストを追加**します。ZAP がメッセージに対して何もアクションを実行しなけれない。

- **迷惑メールにメッセージを移動**: ZAP は、メールボックスで迷惑メール ルールが有効になっている (既定では有効になっている) ので、メッセージを [迷惑メール] フォルダーに移動します。 詳細については [、「Microsoft 365 の Exchange Online メールボックスで迷惑メール設定を構成する」を参照してください](configure-junk-email-settings-on-exo-mailboxes.md)。

- **メール アドレス、メッセージの削除**、**検疫メッセージ****:** ZAP でメッセージを検疫します。

既定では、フィッシング対策ポリシーではフィッシング ZAP が有効になっており、 **フ** ィッシング メール フィルタリングの詳細に対する既定のアクションは **Quarantine メッセージです**。これは、フィッシング ZAP が既定でメッセージを検疫するという意味です。

スパム フィルターの詳細の構成の詳細については [、「Microsoft 365 でスパム対策ポリシーを構成する」を参照してください](configure-your-spam-filter-policies.md)。

### <a name="spam-zap"></a>スパム ZAP

配信 **後にスパム** として識別される未読メッセージについては、適用されるスパム対策ポリシーで **スパム** フィルター常ーディシングに構成されているアクションによって ZAP 結果が異なります。 次の一覧に、使用可能なスパムに対するフィルター指定アクションと ZAP 結果の例を示します。

- **X-Header、件****名行の前にテキストを追加**します。ZAP がメッセージに対して何もアクションを実行しなけれない。

- **迷惑メールにメッセージを移動**: ZAP は、メールボックスで迷惑メール ルールが有効になっている (既定では有効になっている) ので、メッセージを [迷惑メール] フォルダーに移動します。 詳細については [、「Microsoft 365 の Exchange Online メールボックスで迷惑メール設定を構成する」を参照してください](configure-junk-email-settings-on-exo-mailboxes.md)。

- **メール アドレス、メッセージの削除**、**検疫メッセージ****:** ZAP でメッセージを検疫します。 エンドユーザーは、自分のスパム検疫済みメッセージを表示および管理できます。

既定では、スパム対策ポリシーではスパム ZAP が有効になっています。スパム 対策フィルター**Spam**解読の既定のアクションは **[迷惑メール] フォルダーに移動**されます。これは、スパム ZAP が既定で未**読**メッセージを [迷惑メール] フォルダーに移動することを意味します。

スパム フィルターの詳細の構成の詳細については [、「Microsoft 365 でスパム対策ポリシーを構成する」を参照してください](configure-your-spam-filter-policies.md)。

### <a name="zap-considerations-for-office-365-advanced-threat-protection-office-365-atp"></a>Office 365 Advanced Threat Protection (Office 365 ATP) の ZAP に関する考慮事項

ZAP は動的配信スキャンの過中であるメッセージ [を検](dynamic-delivery-and-previewing.md) 疫しないか、マルウェア フィルター処理によって添付ファイルが既にマルウェア警告およびファイル ファイル **で置きText.txt** されません。 これらの種類のメッセージに対してフィッシングまたはスパム信号が受信され、スパム対策ポリシーのフィルター確認方法がメッセージに対して処理 ([迷惑メール、リダイレクト、削除、検疫に移動] に移動) を行うように設定されている場合、ZAP は既定で「迷惑メールに移動する」アクションに設定されます。

## <a name="how-to-see-if-zap-moved-your-message"></a>ZAP がメッセージを移動したかを確認する方法

ZAP がメッセージを移動したかどうかを確認するには、脅威保護の [状態](view-email-security-reports.md#threat-protection-status-report) レポートまたは [脅威エクスプローラー (およびリアルタイムの検出) のどちらかを使用します](threat-explorer.md)。 システム動作として、ZAP は Exchange メールボックス監査ログに記録されない点に注意してください。

## <a name="zap-faq"></a>ZAP FAQ

### <a name="what-happens-if-a-legitimate-message-is-moved-to-the-junk-email-folder"></a>[迷惑メール] フォルダーに移動するとどうなりうりますか?

誤検知の通常の報告 [プロセスに従う必要があります](report-junk-email-messages-to-microsoft.md)。 メッセージが、メッセージがスパムか悪意のあるものであるとサービスによって判別されたため、メッセージが受信トレイから迷惑メール フォルダーに移動される理由は、そののみです。

### <a name="what-if-i-use-the-quarantine-folder-instead-of-the-junk-mail-folder"></a>迷惑メール フォルダーの代わりに [検疫] フォルダーを使用した場合の処理

前述のとおり、ZAP はスパム対策ポリシーに基づいてメッセージに対してアクションを実行します。

### <a name="what-if-im-using-safe-senders-mail-flow-rules-or-allowedblocked-sender-lists"></a>信頼できる送信者、メール フロー ルール、許可/受信拒否リストを使用している場合はどうですか。

差出人セーフ リスト、メール フロー ルール、組織の設定のブロック、および組織の設定の許可優先順位。 これらのメッセージは、サービスが構成内容を実行しているため、ZAP から除外されます。 フィルター処理をバイパスするメッセージの構成に関しては、このエラーが発生する可能性があります。

### <a name="what-if-a-message-is-moved-to-another-folder-eg-inbox-rules"></a>メッセージが別のフォルダー (受信トレイのルールなど) に移動した場合、どうなりますか?

ZAP は、メッセージが削除されていない場合、または同じ操作または強力なアクションが適用されていない場合に機能します。 たとえば、フィッシング ポリシーが検疫に設定されている場合、ユーザーまたは管理者が既にメールを迷惑メールにしている場合は、検疫を行ってファイルを検疫します。

### <a name="how-does-zap-affect-mailboxes-on-hold"></a>ZAP はメールボックスの保持にどのような影響を与えるでしょうか。

ZAP は、保留中のメールボックスからのメッセージを検疫しません。 ZAP は、スパム対策ポリシーのスパムまたはフィッシングの頂点として構成されているアクションに基づいて、メッセージを [迷惑メール] フォルダーに移動できます。

Exchange Online でのホールドの詳細については、Exchange Online [のインプレース保持と訴訟ホールドを参照してください](https://docs.microsoft.com/Exchange/security-and-compliance/in-place-and-litigation-holds)。
