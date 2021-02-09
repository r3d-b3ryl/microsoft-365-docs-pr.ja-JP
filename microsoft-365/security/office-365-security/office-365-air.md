---
title: Microsoft Defender for Office 365 での自動調査と対応
keywords: AIR, autoIR, ATP, 自動化, 調査, 対応, 修復, 脅威, 高度, 脅威, 保護
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 01/29/2021
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Microsoft Defender for Office 365 の自動調査および対応機能の使用を開始します。
ms.custom:
- air
- seo-marvel-mar2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 43728db417e13dfc785731a1ee7b5f596013d6d4
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150197"
---
# <a name="automated-investigation-and-response-air-in-microsoft-defender-for-office-365"></a>Microsoft Defender での自動調査と対応 (AIR) for Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[Microsoft Defender for Office 365](office-365-atp.md) には、セキュリティ運用チームの時間と労力を節約できる強力な自動調査および対応 (AIR) 機能が含まれています。 アラートがトリガーされると、セキュリティ運用チームがそれらのアラートを確認、優先順位付け、対応する必要があります。 受信通知の量に関する情報は、大き過大になる可能性があります。 これらのタスクの一部を自動化すると役立ちます。

AIR を使用すると、セキュリティ運用チームが効率的かつ効果的に運用できます。 AIR 機能には、現在存在する既知の脅威に対応する自動調査プロセスが含まれます。 適切な修復アクションは承認を待ち、セキュリティ運用チームが検出された脅威に効果的に対応できます。 AIR を使用すると、セキュリティ運用チームは、トリガーされる重要なアラートを見失わずに、優先度の高いタスクに集中できます。

この記事の内容

- [AIR の全体的な流れ](#the-overall-flow-of-air)。
- [AIR を取得する方法](#how-to-get-air)そして 
- AIR [機能を構成または](#required-permissions-to-use-air-capabilities) 使用するために必要なアクセス許可。 
- セキュリティ センターに近日公開される変更

この記事には、次 [の手順と](#next-steps)詳細を確認するためのリソースも含まれています。

## <a name="the-overall-flow-of-air"></a>AIR の全体的な流れ

アラートがトリガーされ、セキュリティ プレイブックによって自動調査が開始され、結果として結果が見つまり、推奨されるアクションが実行されます。 次に、AIR の全体的なフローをステップバイステップで示します。

1. 自動調査は、次のいずれかの方法で開始されます。 
   - メール [内の不審](#which-alert-policies-trigger-automated-investigations) な情報 (メッセージ、添付ファイル、URL、侵害されたユーザー アカウントなど) によってアラートがトリガーされます。 インシデントが作成され、自動調査が開始されます。または
   - セキュリティ アナリストは [、脅威エクスプローラーの使用中](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer) に自動調査 [を開始します](threat-explorer.md)。
2. 自動調査を実行すると、該当する電子メールと、その電子メールに関連するエンティティに関するデータが収集されます。 このようなエンティティには、ファイル、URL、および受信者を含めることもできます。 新しいアラートや関連するアラートがトリガーされると、調査の範囲が広がる可能性があります。
3. 自動調査の実行中および実行後は、[詳細情報と結果](air-view-investigation-results.md)を表示することができます。 結果には [、検出された](air-remediation-actions.md) 脅威に対応して修復するために実行できる推奨アクションが含まれます。
4. セキュリティ運用チームは、調査結果 [と推奨事項を](air-view-investigation-results.md)確認し、修復 [アクションを承認または拒否します](air-review-approve-pending-completed-actions.md)。
5. 保留中の修復アクションが承認 (または拒否) されると、自動調査が完了します。

Microsoft Defender for Office 365 では、修復アクションは自動的に実行されません。 修復処理は、組織のセキュリティ チームが承認した場合にのみ実行されます。 AIR 機能は、修復アクションを識別し、情報に基づいた意思決定に必要な詳細を提供することで、セキュリティ運用チームの時間を節約します。

自動調査を行うごとに、セキュリティ運用チームは次の操作を実行できます。

- [調査に関連するアラートの詳細を表示する](air-view-investigation-results.md#view-details-about-an-alert-related-to-an-investigation)
- [調査の結果の詳細を表示する](air-view-investigation-results.md#view-details-of-an-investigation)
- [調査の結果としてアクションを確認および承認する](air-review-approve-pending-completed-actions.md)

> [!TIP]
> 詳細については [、「AIR](automated-investigation-response-office.md)のしくみ」を参照してください。

## <a name="how-to-get-air"></a>AIR の入手方法

ポリシーとアラートが構成されている場合、AIR 機能は [Office 365](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2)用の Microsoft Defender に含まれています。 サポートが必要な場合 「脅威から保護 [する」のガイダンスに従](protect-against-threats.md) って、次の保護設定を設定または構成します。

- [監査ログ](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off) (有効にする必要があります)
- [マルウェア対策ポリシー](protect-against-threats.md#part-1---anti-malware-protection)
- [フィクション対策保護](protect-against-threats.md#part-2---anti-phishing-protection)
- [スパム対策保護](protect-against-threats.md#part-3---anti-spam-protection)
- [フィクション対策保護](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?part-2---anti-phishing-protection)
- [スパム対策保護](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?part-3---anti-spam-protection)
- [安全なリンクと安全な添付ファイル](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365)
- [SPO、OneDrive、Teams 用の安全な添付ファイル機能](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?part-5---verify-atp-for-sharepoint-onedrive-and-microsoft-teams-is-turned-on)
- [電子メールの 0 時間自動消去](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?zero-hour-auto-purge-for-email-in-eop)
- [SPO、OneDrive、Teams 用の安全な添付ファイル機能](protect-against-threats.md#part-5---verify-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams-is-turned-on)
- [電子メールのゼロアワー自動消去](protect-against-threats.md#zero-hour-auto-purge-for-email-in-eop)。

さらに、組織の警告ポリシー [](https://docs.microsoft.com/microsoft-365/compliance/alert-policies)、特に脅威管理カテゴリの既定のポリシーを必ず[確認してください](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?default-alert-policies)。

## <a name="which-alert-policies-trigger-automated-investigations"></a>自動調査をトリガーするアラート ポリシーは何ですか?

Microsoft 365 には、Exchange 管理者のアクセス許可の不正使用、マルウェアアクティビティ、外部および内部の潜在的脅威、および情報ガバナンスのリスクを特定するのに役立つ、多くの組み込みのアラート ポリシーが提供されています。 既定のアラート [ポリシーの中には、自動](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#default-alert-policies) 調査をトリガーできるものがあります。 次の表では、自動調査をトリガーするアラート、Microsoft 365 セキュリティ センターでの重大度、および生成方法について説明します。

|アラート|重要度|アラートの生成方法|
|:---|:---|:---|
|悪意のある可能性がある URL のクリックが検出されました|**High**|この警告は、次の場合に生成されます。 <ul><li>組織内の安全なリンク [によって保護](atp-safe-links.md) されているユーザーが悪意のあるリンクをクリックする</li><li>URL の Verdict の変更は、Microsoft Defender によって 365 Office識別されます。</li><li>ユーザーは、安全なリンクに関する警告ページ (組織の安全なリンク ポリシーに基づく) [を上書きします](set-up-atp-safe-links-policies.md)。</li></ul> <p> このアラートをトリガーするイベントの詳細については、「安全なリンク ポリシーの [設定」を参照してください](set-up-atp-safe-links-policies.md)。|
|電子メール メッセージがマルウェアまたはフィッシングとしてユーザーによって報告される|**情報提供**|この警告は、組織内のユーザーが、レポート メッセージ アドインまたは Report [](enable-the-report-message-add-in.md) Phishing アドインを使用して、メッセージをフィッシングメールとして[報告するときに生成されます](enable-the-report-phish-add-in.md)。|
|マルウェアを含む電子メール メッセージが配信後に削除される|**情報提供**|この警告は、マルウェアを含む電子メール メッセージが組織内のメールボックスに配信されると生成されます。 このイベントが発生した場合、Microsoft はゼロアワー自動消去を使用して、感染したメッセージを Exchange Online メールボックス [から削除します](zero-hour-auto-purge.md)。|
|フィッシング URL を含む電子メール メッセージは配信後に削除されます|**情報提供**|この警告は、フィッシングを含むメッセージが組織内のメールボックスに配信されると生成されます。 このイベントが発生した場合、Microsoft はゼロアワー自動消去を使用して、感染したメッセージを Exchange Online メールボックス [から削除します](zero-hour-auto-purge.md)。|
|不審な電子メール送信パターンが検出される|**Medium**|この警告は、組織内の誰かが不審なメールを送信し、電子メールの送信が制限される危険性がある場合に生成されます。 この警告は、アカウントが侵害されているが、ユーザーを制限するほど重大でなかった可能性がある動作に関する早期警告です。 <p> まれですが、このポリシーによって生成されるアラートは異常である可能性があります。 ただし、ユーザー アカウントが侵害されているかどうかを確認[してください。](responding-to-a-compromised-email-account.md)|
|ユーザーがメールの送信を制限されている|**High**|この警告は、組織内のユーザーが送信メールの送信を制限されている場合に生成されます。 この警告は、通常、メール アカウント [が侵害された場合に発生します](responding-to-a-compromised-email-account.md)。 <p> 制限されたユーザーの詳細については [、「Microsoft 365](removing-user-from-restricted-users-portal-after-spam.md)の制限付きユーザー ポータルからブロックされたユーザーを削除する」を参照してください。|
|

> [!TIP]
> アラート ポリシーの詳細や既定の設定の編集については [、Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/alert-policies)コンプライアンス センターのアラート ポリシーを参照してください。

## <a name="required-permissions-to-use-air-capabilities"></a>AIR 機能を使用するために必要なアクセス許可

アクセス許可は、次の表に示すロールなど、特定のロールによって付与されます。

|Task|Role(s) required|
|---|---|
|AIR 機能のセットアップ|次のいずれかの役割: <ul><li>グローバル管理者</li><li>セキュリティ管理者</li></ul> <p> これらのロールは [、Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) またはセキュリティ/コンプライアンス センター [&割り当てることができます](permissions-in-the-security-and-compliance-center.md)。|
|自動調査を開始する <p> --- または --- <p> 推奨されるアクションを承認または拒否する|[Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)またはセキュリティ/コンプライアンス センターで割り当てられている次[&の 1 つ](permissions-in-the-security-and-compliance-center.md)。 <ul><li>グローバル管理者</li><li>セキュリティ管理者</li><li>セキュリティ オペレーター</li><li>セキュリティ閲覧者 <br> --- さらに --- </li><li>検索と消去 (この役割は、セキュリティ/コンプライアンス センター [&割り当てられます](permissions-in-the-security-and-compliance-center.md)。 そこで新しい役割グループを作成し、その新しい役割グループに "Search and Purge/検索と消去" 役割を追加する必要がある場合があります。</li></ul>|

## <a name="required-licenses"></a>必要なライセンス

[Microsoft Defender for Office 365 プラン 2](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2) ライセンスを割り当てる必要があります。

- セキュリティ管理者 (グローバル管理者を含む)
- 組織のセキュリティ運用チーム (セキュリティ 閲覧者と検索と消去の役割を持 **つユーザーを含** む)
- エンド ユーザー


## <a name="changes-are-coming-soon-in-your-security-center"></a>セキュリティ センターで変更が近日公開される予定です

microsoft Defender for Office 365 で既に AIR 機能を使用している場合は、強化された [Microsoft 365](../mtp/overview-security-center.md)セキュリティ センターにいくつかの変更が加わります。 

:::image type="content" source="../../media/m3d-action-center-unified.png" alt-text="統合アクション センター":::

新しく強化されたセキュリティ センターでは [、Microsoft Defender for Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) と Microsoft Defender for Endpoint の AIR 機能が [統合されています](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)。 これらの更新と機能強化により、セキュリティ運用チームは、電子メール、コラボレーション コンテンツ、ユーザー アカウント、デバイス全体にわたる自動調査と修復アクションに関する詳細を 1 か所で表示できます。

> [!TIP]
> 新しい Microsoft 365 セキュリティ センター ( ) は、次 [https://security.microsoft.com](https://security.microsoft.com) のセンターに置き換わるものです。
> - Office 365 セキュリティ & コンプライアンス センター ( [https://protection.office.com](https://protection.office.com) )
> - Microsoft Defender セキュリティ センター ( [https://securitycenter.windows.com](https://securitycenter.windows.com) )
>
> URL の変更に加えて、新しい外観が追加され、セキュリティ チームのエクスペリエンスを効率化し、脅威の検出を 1 か所で確認できます。 

### <a name="what-to-expect"></a>期待される問題

次の表に、Microsoft Defender for Office 365 で AIR に加わる変更点と機能強化を示します。

|アイテム  |変更された情報  |
|---------|---------|
|**[調査]** ページ     | 更新された [ **調査] ページ** は、Microsoft Defender for Endpoint に表示される [調査とより一貫性があります](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)。 新しい統合された調査ビューに合わせて、一般的な形式とスタイルの変更 **が表示** されます。 たとえば、調査グラフの形式は統一されています。        |
|**[ユーザー]** タブ |[ **ユーザー]** タブが [メールボックス **] タブに移動** しました。ユーザーに関する詳細が [メールボックス] タブ **に表示** されます。 |
|**[電子メール** ] タブ |[ **メール]** タブが削除されました。[エンティティ **] タブに** アクセスして、電子メールと電子メール クラスター アイテムの一覧を表示します。 |
|**[エンティティ]** タブ | [ **エンティティ]** タブには、すべての概要ビューとエンティティの種類でフィルター処理する機能を含むタブインタブ スタイルがあります。 [ **エンティティ] タブ** には、[エクスプローラーで開く] オプションに **加** えて、[検索 **の実行] オプションが追加** されています。 脅威エクスプローラーまたは高度な検索 [を](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer) 使用 [して、エンティティ](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview) と脅威を検索し、結果をフィルター処理できます。 | 
|**[操作]** タブ |更新された [操作 **]** タブには、[ **保留中の操作]** タブと [操作履歴 **] タブが含** まれる状態になります。保留中のアクションを選択すると開く作業ウィンドウで、アクションを承認 (または拒否) できます。 |
|**[エビデンス]** タブ | 新しい **[エビデンス]** タブには、アクションに関連する主要なエンティティの結果が表示されます。 各証拠に関連するアクションは、保留中のアクションを選択すると開く作業ウィンドウで承認 (または拒否) できます。 |
|**アクション センター** |更新されたアクション **センター** ( ) は、電子メール、デバイス、ID 間で保留中のアクションと完了したアクション [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) をまとめます。 詳細については、「アクション センター」を参照してください。 (詳細については、アクション センター [を参照してください](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center))。
|**[インシデント]** ページ |[ **インシデント] ページ** では、複数の調査を相互に関連付け、調査の統合されたビューを向上できます。 ([インシデントの詳細については、次を参照](https://docs.microsoft.com/microsoft-365/security/mtp/incidents-overview)してください)。


## <a name="next-steps"></a>次の手順

- [自動調査の詳細と結果を表示する](air-view-investigation-results.md#view-details-of-an-investigation)
- [保留中のアクションを確認および承認する](air-remediation-actions.md)
