---
title: Microsoft Defender for Office 365での自動調査と対応
keywords: AIR, autoIR, Microsoft Defender for Endpoint, 自動化, 調査, 対応, 修復, 脅威, 高度, 脅威, 保護
f1.keywords:
- NOCSH
author: dansimp
ms.author: dansimp
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 01/29/2021
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Microsoft Defender for Office 365で自動調査と応答機能を使用概要。
ms.custom:
- air
- seo-marvel-mar2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ca64509321ff43bbe8b7baf7ec7dfa270d9afdc4
ms.sourcegitcommit: 52eea2b65c0598ba4a1b930c58b42dbe62cdaadc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2022
ms.locfileid: "64941525"
---
# <a name="automated-investigation-and-response-air-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365の自動調査と対応 (AIR)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[Microsoft Defender for Office 365](defender-for-office-365.md)には、セキュリティ運用チームの時間と労力を節約できる強力な自動調査と対応 (AIR) 機能が含まれています。 アラートがトリガーされると、セキュリティ運用チームがそれらのアラートを確認、優先順位付け、および対応する必要があります。 受信アラートの量に追いつくことは、非常に大きい場合があります。 これらのタスクの一部を自動化すると役に立ちます。

AIR を使用すると、セキュリティ運用チームがより効率的かつ効果的に運用できるようになります。 AIR 機能には、現在存在する既知の脅威に対応する自動調査プロセスが含まれます。 適切な修復アクションが承認を待ち、セキュリティ運用チームが検出された脅威に効果的に対応できるようにします。 AIR を使用すると、セキュリティ運用チームは、トリガーされる重要なアラートを見失うことなく、優先度の高いタスクに集中できます。

この記事の内容

- [AIR の全体的なフロー](#the-overall-flow-of-air)。
- [AIR を取得する方法](#how-to-get-air);そして
- AIR 機能を構成または使用するために [必要なアクセス許可](#required-permissions-to-use-air-capabilities) 。
- Microsoft 365 Defender ポータルに近日公開予定の変更

この記事には、 [次の手順](#next-steps)と、詳細を確認するためのリソースも含まれています。

## <a name="the-overall-flow-of-air"></a>AIR の全体的な流れ

アラートがトリガーされ、セキュリティ プレイブックによって自動調査が開始され、結果と推奨されるアクションが生成されます。 AIR の全体的なフローを次に示します。手順を追って説明します。

1. 自動調査は、次のいずれかの方法で開始されます。
   - [アラートは、](#which-alert-policies-trigger-automated-investigations)電子メール (メッセージ、添付ファイル、URL、侵害されたユーザー アカウントなど) で疑わしいものによってトリガーされます。 インシデントが作成され、自動調査が開始されます。または
   - セキュリティ アナリストは[、エクスプローラー](threat-explorer.md)[の使用中に自動調査を開始](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)します。
2. 自動調査の実行中に、問題の電子メールとその電子メールに関連するエンティティに関するデータが収集されます。 このようなエンティティには、ファイル、URL、受信者を含めることができます。 新しいアラートと関連するアラートがトリガーされると、調査の範囲が広がる可能性があります。
3. 自動調査の実行中および実行後は、[詳細情報と結果](air-view-investigation-results.md)を表示することができます。 結果には、検出された脅威に対応して修復するために実行できる [推奨されるアクション](air-remediation-actions.md) が含まれます。
4. セキュリティ運用チームは、 [調査結果と推奨事項](air-view-investigation-results.md)を確認し、 [修復アクションを承認または拒否します](air-review-approve-pending-completed-actions.md)。
5. 保留中の修復アクションが承認 (または拒否) されると、自動調査が完了します。

Microsoft Defender for Office 365では、修復アクションは自動的に実行されません。 修復処理は、組織のセキュリティ チームが承認した場合にのみ実行されます。 AIR 機能は、修復アクションを特定し、情報に基づいた意思決定に必要な詳細を提供することで、セキュリティ運用チームの時間を節約します。

各自動調査の間と後、セキュリティ運用チームは次のことができます。

- [調査に関連するアラートの詳細を表示する](air-view-investigation-results.md#view-details-about-an-alert-related-to-an-investigation)
- [調査の結果の詳細を表示する](air-view-investigation-results.md#view-details-of-an-investigation)
- [調査の結果としてアクションを確認して承認する](air-review-approve-pending-completed-actions.md)

> [!TIP]
> 詳細な概要については、「 [AIR](automated-investigation-response-office.md) のしくみ」を参照してください。

## <a name="how-to-get-air"></a>AIR の入手方法

ポリシーとアラートが構成されている場合、AIR 機能は[Microsoft Defender for Office 365](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2)に含まれます。 ヘルプが必要ですか? [「脅威から保護する](protect-against-threats.md)」のガイダンスに従って、次の保護設定を設定または構成します。

- [監査ログ](../../compliance/turn-audit-log-search-on-or-off.md) (オンにする必要があります)
- [マルウェア対策保護](protect-against-threats.md#part-1---anti-malware-protection-in-eop)
- [フィッシング対策保護](../office-365-security/protect-against-threats.md#part-2---anti-phishing-protection-in-eop-and-defender-for-office-365)
- [スパム対策保護](protect-against-threats.md#part-3---anti-spam-protection-in-eop)
- [安全なリンク、安全な添付ファイル](protect-against-threats.md#part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365)

さらに、 [組織のアラート ポリシー](../../compliance/alert-policies.md)、特に [脅威管理カテゴリの既定のポリシーを](../../compliance/alert-policies.md#default-alert-policies)確認してください。

## <a name="which-alert-policies-trigger-automated-investigations"></a>自動調査をトリガーするアラート ポリシーはどれですか?

Microsoft 365には、管理者のアクセス許可の悪用、マルウェア アクティビティ、潜在的な外部および内部の脅威、および情報ガバナンス のリスクExchange識別するのに役立つ、多くの組み込みのアラート ポリシーが用意されています。 [既定のアラート ポリシー](../../compliance/alert-policies.md#default-alert-policies)の一部では、自動調査をトリガーできます。 次の表では、自動調査をトリガーするアラート、Microsoft 365 Defender ポータルでの重大度、および生成方法について説明します。

|通知|重要度|アラートの生成方法|
|---|---|---|
|悪意のある可能性がある URL のクリックが検出されました|**High**|このアラートは、次のいずれかが発生したときに生成されます。 <ul><li>組織内の [セーフ リンク](safe-links.md)によって保護されているユーザーが悪意のあるリンクをクリックする</li><li>URL の判定の変更は、Microsoft Defender for Office 365によって識別されます</li><li>ユーザーはセーフリンクの警告ページをオーバーライドします (組織の[セーフリンク ポリシー](set-up-safe-links-policies.md)に基づいています。</li></ul> <p> このアラートをトリガーするイベントの詳細については、「[セーフリンク ポリシーの設定](set-up-safe-links-policies.md)」を参照してください。|
|ユーザーがマルウェアまたはフィッシングとして電子メール メッセージを報告する|**情報**|このアラートは、組織内のユーザーがレポート メッセージ [アドインまたはレポート](enable-the-report-message-add-in.md) フィッシング アドインを使用してフィッシング メールとしてメッセージ [を報告](enable-the-report-phish-add-in.md)するときに生成されます。|
|マルウェアを含む電子メール メッセージは、配信後に削除されます|**情報**|このアラートは、マルウェアを含む電子メール メッセージが組織内のメールボックスに配信されるときに生成されます。 このイベントが発生した場合、Microsoft は [0 時間の自動消去 (ZAP)](zero-hour-auto-purge.md) を使用して、Exchange Onlineメールボックスから感染したメッセージを削除します。|
|フィッシング URL を含む電子メール メッセージは、配信後に削除されます|**情報**|このアラートは、フィッシングを含むメッセージが組織内のメールボックスに配信されたときに生成されます。 このイベントが発生した場合、[Microsoft は ZAP](zero-hour-auto-purge.md) を使用してExchange Onlineメールボックスから感染したメッセージを削除します。|
|不審な電子メール送信パターンが検出される|**Medium**|このアラートは、組織内のユーザーが疑わしいメールを送信し、電子メールの送信を制限される危険性がある場合に生成されます。 このアラートは、アカウントが侵害されたが、ユーザーを制限するのに十分なほど重大ではない可能性がある動作の早期警告です。 <p> まれですが、このポリシーによって生成されるアラートは異常である可能性があります。 ただし、[ユーザー アカウントが侵害されていないかどうか](responding-to-a-compromised-email-account.md)を確認することをお勧めします。|
|ユーザーが電子メールの送信を制限されている|**High**|このアラートは、組織内のユーザーが送信メールの送信を制限されたときに生成されます。 このアラートは通常、 [電子メール アカウントが侵害](responding-to-a-compromised-email-account.md)されたときに発生します。 <p> 制限付きユーザーの詳細については、「[Microsoft 365の制限付きユーザーポータルからブロックされたユーザーを削除](removing-user-from-restricted-users-portal-after-spam.md)する」を参照してください。|

> [!TIP]
> アラート ポリシーの詳細または既定の設定の編集については、 [Microsoft Purview コンプライアンス ポータルのアラート ポリシーに関するページを](../../compliance/alert-policies.md)参照してください。

## <a name="required-permissions-to-use-air-capabilities"></a>AIR 機能を使用するために必要なアクセス許可

アクセス許可は、次の表で説明されているロールなど、特定のロールを通じて付与されます。

|タスク|ロールが必要です|
|---|---|
|AIR 機能を設定する|次のいずれかのロール。 <ul><li>グローバル管理者</li><li>セキュリティ管理者</li></ul> <p> これらのロールは、[Azure Active Directory](/azure/active-directory/roles/permissions-reference)または[Microsoft 365 Defender ポータル](permissions-microsoft-365-security-center.md)で割り当てることができます。|
|自動調査の開始 <p> --- または --- <p> 推奨されるアクションを承認または拒否する|[Azure Active Directory](/azure/active-directory/roles/permissions-reference)または[Microsoft 365 Defender ポータル](permissions-microsoft-365-security-center.md)で割り当てられた次のいずれかのロール。 <ul><li>グローバル管理者</li><li>セキュリティ管理者</li><li>セキュリティ オペレーター</li><li>セキュリティ閲覧者 <br> --- さらに --- </li><li>検索と消去 (このロールは[、Microsoft 365 Defender ポータル](permissions-microsoft-365-security-center.md)でのみ割り当てられます。 そこで新しい **電子メール &コラボレーション** 役割グループを作成し、検索ロールと消去ロールをその新しい役割グループに追加することが必要になる場合があります。</li></ul>|

## <a name="required-licenses"></a>必要なライセンス

[プラン 2 ライセンスMicrosoft Defender for Office 365](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2)割り当てる必要があります。

- セキュリティ管理者 (グローバル管理者を含む)
- 組織のセキュリティ運用チーム (セキュリティ リーダーと **、検索ロールと消去** ロールを持つユーザーを含む)
- エンド ユーザー

## <a name="changes-are-coming-soon-in-your-microsoft-365-defender-portal"></a>Microsoft 365 Defender ポータルで変更が間もなく行われる予定です

Microsoft Defender for Office 365で AIR 機能を既に使用している場合は、[改善されたMicrosoft 365 Defender ポータル](../defender/microsoft-365-defender.md#the-microsoft-365-defender-portal)にいくつかの変更が表示されます。

:::image type="content" source="../../media/m3d-action-center-unified.png" alt-text="統合アクション センター" lightbox="../../media/m3d-action-center-unified.png":::

新しく強化されたMicrosoft 365 Defender ポータル<https://security.microsoft.com>には、[Microsoft Defender for Office 365とMicrosoft Defender for Endpoint](defender-for-office-365.md)の AIR 機能[が](../defender-endpoint/automated-investigations.md)統合されています。 これらの更新プログラムと改善により、セキュリティ運用チームは、メール、共同作業のコンテンツ、ユーザー アカウント、デバイスに対する自動調査と修復処理に関する詳細を 1 か所で確認できます。

> [!TIP]
> 新しいMicrosoft 365 Defender ポータルでは、次の管理センターが置き換えられます。
>
> - セキュリティ & コンプライアンス センター (<https://protection.office.com>)
> - Microsoft 365 Defender (<https://security.microsoft.com>)
>
> URL の変更に加えて、セキュリティ チームがより効率的なエクスペリエンスを提供し、より多くの脅威検出を 1 か所で可視化できるように設計された新しい外観があります。

### <a name="what-to-expect"></a>想定される変化

次の表に、Microsoft Defender for Office 365の AIR に関する変更点と改善点を示します。

|アイテム|何が変わるのですか?|
|---|---|
|**[調査]** ページ|更新された **[調査]** ページは、[Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)に表示される内容と一致しています。 新しい統合 **された調査** ビューに合わせて、一般的な形式とスタイルの変更がいくつか表示されます。 たとえば、調査グラフの形式は統一されています。|
|**[ユーザー]** タブ|[ **ユーザー]** タブが [ **メールボックス** ] タブになりました。ユーザーに関する詳細は、[ **メールボックス** ] タブに一覧表示されます。|
|**[電子メール** ] タブ|[ **電子メール** ] タブが削除されました。[ **エンティティ]** タブにアクセスして、電子メールと電子メール クラスターの項目の一覧を表示します。|
|**[エンティティ** ] タブ|[ **エンティティ]** タブには、すべての概要ビューとエンティティの種類でフィルター処理する機能を含むタブ内タブ スタイルがあります。 [**エンティティ]** タブに、[**エクスプローラーで開く**] オプションに加えて [**Go hunting**] オプションが含まれるようになりました。 [エクスプローラー](threat-explorer.md)または[高度な捜索](../defender-endpoint/advanced-hunting-overview.md)を使用して、エンティティと脅威を検索し、結果をフィルター処理できるようになりました。|
|**[アクション]** タブ|更新された **[アクション]** タブに、[ **保留中のアクション** ] タブと [ **アクション履歴** ] タブが含まれるようになりました。保留中のアクションを選択すると開くサイド ウィンドウで、アクションを承認 (または拒否) できます。|
|**[証拠** ] タブ|新しい **[証拠** ] タブには、アクションに関連するキー エンティティの結果が表示されます。 保留中のアクションを選択すると開くサイド ウィンドウで、各証拠に関連するアクションを承認 (または拒否) できます。|
|**アクション センター**|更新された **アクション センター** (<https://security.microsoft.com/action-center>) は、電子メール、デバイス、ID の間で保留中のアクションと完了済みのアクションをまとめます。 詳細については、「アクション センター」を参照してください。 (詳細については、「 [アクション センター](../defender/m365d-action-center.md)」を参照してください)。|
|**[インシデント]** ページ|[ **インシデント] ページでは、** 複数の調査が相互に関連付けられるようになり、調査の統合ビューが向上しました。 ([インシデントの詳細については、こちらを参照してください](../defender/incidents-overview.md))。|

## <a name="next-steps"></a>次の手順

- [自動調査の詳細と結果を表示する](air-view-investigation-results.md#view-details-of-an-investigation)
- [保留中のアクションを確認して承認する](air-remediation-actions.md)
