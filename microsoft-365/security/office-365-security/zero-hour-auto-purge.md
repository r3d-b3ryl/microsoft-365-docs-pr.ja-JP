---
title: Microsoft Defender for Office 365でのゼロ時間の自動消去
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
- MBS150
- MET150
ms.assetid: 96deb75f-64e8-4c10-b570-84c99c674e15
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: ゼロ時間自動消去 (ZAP) は、Exchange Online メールボックス内の配信されたメッセージを、スパム、フィッシング、または配信後にマルウェアが含まれていると検出された迷惑メール フォルダーまたは検疫にさかのぼって移動します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: bd9bb3f231e42c625c87669417210281d1d5a3df
ms.sourcegitcommit: a8fbaf4b441b5325004f7a2dacd9429ec9d80534
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/26/2022
ms.locfileid: "65739463"
---
# <a name="zero-hour-auto-purge-zap-in-exchange-online"></a>Exchange Onlineのゼロ時間自動消去 (ZAP)

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

## <a name="zero-hour-auto-purge-zap-basics"></a>ゼロ時間自動消去 (ZAP) の基本

Exchange Onlineにメールボックスを含むMicrosoft 365組織では、ゼロ時間自動消去 (ZAP) は、既にExchange Onlineメールボックスに配信されている悪意のあるフィッシング、スパム、またはマルウェア メッセージをさかのぼって検出して除去する電子メール保護機能です。

ZAP は、オンプレミスのExchangeメールボックスを保護するスタンドアロン Exchange Online Protection (EOP) 環境では機能しません。

## <a name="how-zap-works"></a>ZAP のしくみ

スパムとマルウェアのシグネチャは、サービス内で毎日リアルタイムで更新されます。 ただし、ユーザーは引き続き、ユーザーに配信された後にコンテンツが武器化される場合など、さまざまな理由で悪意のあるメッセージを受信できます。 ZAP は、サービス内のスパムとマルウェアのシグネチャの更新を継続的に監視することで、この問題に対処します。 ZAP は、ユーザーのメールボックスに既に存在するメッセージを検索して削除できます。

ZAP アクションは、ユーザーにとってシームレスです。メッセージが検出されて移動された場合、通知されません。

[セーフ送信者リスト](create-safe-sender-lists-in-office-365.md)、メール フロー ルール (トランスポート ルールとも呼ばれます)、受信トレイ ルール、または追加のフィルターが ZAP よりも優先されます。 メール フローでの動作と同様に、これは、配信されたメッセージに ZAP が必要であるとサービスが判断した場合でも、メッセージは安全な送信者の構成のために処理されないことを意味します。 これは、フィルター処理をバイパスするようにメッセージを構成することに注意するもう 1 つの理由です。

この短いビデオでは、Microsoft Defender for Office 365の ZAP が電子メール内の脅威を自動的に検出して無力化する方法について説明します。 
> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWGrLg]

### <a name="zero-hour-auto-purge-zap-for-malware"></a>マルウェアのゼロ時間自動消去 (ZAP)

配信後にマルウェアが含まれていることが検出された **読み取りメッセージまたは未読メッセージ** の場合、ZAP はマルウェアの添付ファイルを含むメッセージを検疫します。 既定では、管理者のみが検疫されたマルウェア メッセージを表示および管理できます。 ただし、管理者は _検疫ポリシー_ を作成して使用して、マルウェアとして検疫されたメッセージに対してユーザーが許可する操作を定義できます。 詳細については、「[検疫ポリシー](quarantine-policies.md)」を参照してください。

マルウェア対策ポリシーでは、マルウェアの ZAP は既定で有効になっています。 詳細については、「 [EOP でマルウェア対策ポリシーを構成する](configure-anti-malware-policies.md)」を参照してください。

### <a name="zero-hour-auto-purge-zap-for-phishing"></a>フィッシングのゼロ時間自動消去 (ZAP)

配信後にフィッシングとして識別される **読み取りメッセージまたは未読メッセージ** の場合、ZAP の結果は、該当するスパム対策ポリシーの **フィッシングメール** フィルターの判定に対して構成されたアクションによって異なります。 フィッシングに対して使用可能なフィルター処理の判定アクションとその可能な ZAP の結果については、次の一覧で説明します。

- **X ヘッダーの追加**、 **テキストを含む件名行の先頭への追加**、 **メール アドレスへのメッセージのリダイレクト**、 **メッセージの削除**: ZAP はメッセージに対してアクションを実行しません。

- **メッセージを迷惑メールに移動する**: ZAP はメッセージを迷惑メール フォルダーに移動します。 詳細については、「[Microsoft 365のExchange Online メールボックスで迷惑メール設定を構成](configure-junk-email-settings-on-exo-mailboxes.md)する」を参照してください。

- **検疫メッセージ**: ZAP はメッセージを検疫します。

既定では、フィッシング詐欺の ZAP はスパム対策ポリシーで有効になっており、 **フィッシングメール** フィルターの判定の既定のアクションは **検疫メッセージです。** つまり、フィッシング詐欺の ZAP は既定でメッセージを検疫します。

スパム フィルターの判定の構成の詳細については、「[Microsoft 365でスパム対策ポリシーを構成](configure-your-spam-filter-policies.md)する」を参照してください。

### <a name="zero-hour-auto-purge-zap-for-high-confidence-phishing"></a>ゼロ時間の自動消去 (ZAP) による高信頼フィッシング

配信後に信頼度の高いフィッシングとして識別される **読み取りメッセージまたは未読メッセージ** の場合、ZAP はメッセージを検疫します。 既定では、検疫された信頼度の高いフィッシング メッセージを表示および管理できるのは管理者のみです。 ただし、管理者は _検疫ポリシー_ を作成して使用して、信頼度の高いフィッシングとして検疫されたメッセージに対してユーザーが許可する操作を定義できます。 詳細については、「[検疫ポリシー](quarantine-policies.md)」を参照してください。

信頼度の高いフィッシングの ZAP は、既定で有効になっています。 詳細については、[Office 365の「既定でセキュリティで保護](secure-by-default.md)する」を参照してください。

### <a name="zero-hour-auto-purge-zap-for-spam"></a>スパムのゼロ時間自動消去 (ZAP)

配信後にスパムとして識別される **未読メッセージ** の場合、ZAP の結果は、該当するスパム対策ポリシーの **スパム** フィルターの判定に対して構成されているアクションによって異なります。 スパムに対して使用可能なフィルター処理の判定アクションとその考えられる ZAP の結果については、次の一覧で説明します。

- **X ヘッダーの追加**、 **テキストを含む件名行の先頭への追加**、 **メール アドレスへのメッセージのリダイレクト**、 **メッセージの削除**: ZAP はメッセージに対してアクションを実行しません。

- **メッセージを迷惑メールに移動する**: ZAP はメッセージを迷惑メール フォルダーに移動します。 詳細については、「[Microsoft 365のExchange Online メールボックスで迷惑メール設定を構成](configure-junk-email-settings-on-exo-mailboxes.md)する」を参照してください。

- **検疫メッセージ**: ZAP はメッセージを検疫します。 既定では、エンドユーザーは受信者であるスパム検疫済みメッセージを表示および管理できます。 ただし、管理者は _検疫ポリシー_ を作成して使用して、スパムとして検疫されたメッセージに対してユーザーが許可する操作を定義できます。 詳細については、「[検疫ポリシー](quarantine-policies.md)」を参照してください。

既定では、スパム ZAP はスパム対策ポリシーで有効になっており、 **スパム** フィルターの判定の既定のアクションは迷惑 **メール フォルダーにメッセージを移動** します。これは、スパム ZAP が既定で **未読** メッセージを迷惑メール フォルダーに移動することを意味します。

スパム フィルターの判定の構成の詳細については、「[Microsoft 365でスパム対策ポリシーを構成](configure-your-spam-filter-policies.md)する」を参照してください。

### <a name="zero-hour-auto-purge-zap-considerations-for-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365のゼロ時間自動消去 (ZAP) に関する考慮事項

ZAP は、セーフ添付ファイル ポリシー スキャンで [動的配信](safe-attachments.md#dynamic-delivery-in-safe-attachments-policies)の処理中のメッセージ、または EOP マルウェア フィルターが既に添付ファイルを **マルウェア アラート Text.txt** ファイルに置き換えたメッセージを検疫しません。 このような種類のメッセージに対してフィッシングまたはスパムシグナルが受信され、スパム対策ポリシーのフィルター処理の判定がメッセージに対して何らかのアクションを実行するように設定されている場合 (迷惑メールに移動、リダイレクト、削除、または検疫) すると、ZAP は既定で [迷惑メールに移動] アクションに設定されます。

## <a name="how-to-see-if-zap-moved-your-message"></a>ZAP がメッセージを移動したかどうかを確認する方法

ZAP がメッセージを移動したかどうかを確認するには、次のオプションがあります。

- **メッセージ数**: [メールフロー状態レポートの [メールフロー] ビューを](view-email-security-reports.md#mailflow-view-for-the-mailflow-status-report) 使用して、指定した日付範囲の ZAP 影響を受けるメッセージの数を確認します。
- **メッセージの詳細**: [脅威エクスプローラー (およびリアルタイム検出)](threat-explorer.md) を使用して、[**追加アクション**] 列の値 **ZAP** ですべての **電子メール** イベントをフィルター処理します。

> [!NOTE]
> ZAP は、システム アクションとしてExchangeメールボックス監査ログに記録されません。

## <a name="zero-hour-auto-purge-zap-faq"></a>ゼロ時間自動消去 (ZAP) に関する FAQ

### <a name="what-happens-if-a-legitimate-message-is-moved-to-the-junk-email-folder"></a>正当なメッセージが迷惑メール フォルダーに移動された場合はどうなりますか?

[誤検知](report-junk-email-messages-to-microsoft.md)については、通常の報告プロセスに従う必要があります。 メッセージが受信トレイから迷惑メール フォルダーに移動される唯一の理由は、メッセージがスパムまたは悪意のあるメッセージであるとサービスが判断したためです。

### <a name="what-if-i-use-the-quarantine-folder-instead-of-the-junk-mail-folder"></a>迷惑メール フォルダーの代わりに検疫フォルダーを使用した場合はどうなりますか?

ZAP は、この記事で前述したように、スパム対策ポリシーの構成に基づいてメッセージに対してアクションを実行します。

### <a name="what-if-im-using-safe-senders-mail-flow-rules-or-allowedblocked-sender-lists"></a>差出人セーフ リスト、メール フロー ルール、または許可/ブロックされた送信者リストを使用している場合はどうなりますか?

セーフ送信者、メール フロー ルール、またはブロックと許可の組織設定が優先されます。 これらのメッセージは、サービスが構成した操作を実行しているため、ZAP から除外されます。 これは、フィルター処理をバイパスするようにメッセージを構成することに注意するもう 1 つの理由です。

### <a name="what-are-the-licensing-requirements-for-zero-hour-auto-purge-zap-to-work"></a>ゼロ時間自動消去 (ZAP) のライセンス要件は何ですか?

ライセンスに制限はありません。 ZAP は、オンラインExchangeでホストされているすべてのメールボックスで動作します。 ZAP は、オンプレミスのExchangeメールボックスを保護するスタンドアロン Exchange Online Protection (EOP) 環境では機能しません。

### <a name="what-if-a-message-is-moved-to-another-folder-eg-inbox-rules"></a>メッセージが別のフォルダー (受信トレイルールなど) に移動された場合はどうなりますか?

0 時間の自動消去は、メッセージが削除されていない限り、または同じ、またはより強力なアクションがまだ適用されていない限り、引き続き機能します。 たとえば、フィッシング対策ポリシーが検疫に設定されていて、メッセージが迷惑メールに既に含まれている場合、ZAP はメッセージを検疫するアクションを実行します。

### <a name="how-does-zap-affect-mailboxes-on-hold"></a>ZAP は保留中のメールボックスにどのような影響を与えるのですか?

0 時間の自動消去では、保留中のメールボックスからメッセージが検疫されます。 ZAP は、スパム対策ポリシーでスパムまたはフィッシングの判定用に構成されたアクションに基づいて、迷惑メール フォルダーにメッセージを移動できます。

Exchange Onlineの保留の詳細については、「インプレース [ホールドと訴訟ホールド in Exchange Online](/Exchange/security-and-compliance/in-place-and-litigation-holds)」を参照してください。
