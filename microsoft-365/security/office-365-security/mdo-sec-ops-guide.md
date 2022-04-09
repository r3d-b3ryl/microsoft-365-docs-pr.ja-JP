---
title: Defender for Office 365のセキュリティ操作ガイド
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.date: ''
ms.topic: conceptual
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
ms.custom: ''
description: SecOps 担当者がMicrosoft Defender for Office 365を管理するための規範的なプレイブック。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 01c857d96fe461c91c459704f4572191f37ef016
ms.sourcegitcommit: dd5fc139affb4cba4089cbdb2c478968b680699a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2022
ms.locfileid: "64747501"
---
# <a name="microsoft-defender-for-office-365-security-operations-guide"></a>Microsoft Defender for Office 365 セキュリティ操作ガイド

この記事では、組織内のMicrosoft Defender for Office 365を正常に運用するための要件とタスクの概要について説明します。 これらのタスクは、セキュリティオペレーション センター (SOC) が、電子メールおよびコラボレーション関連のセキュリティの脅威を保護、検出、および対応するための高品質で信頼性の高いアプローチを提供することを保証するのに役立ちます。

このガイドの残りの部分では、SecOps 担当者に必要なアクティビティについて説明します。 アクティビティは、規範的な毎日、毎週、毎月、およびアドホック タスクにグループ化されます。

このガイドのコンパニオン記事では、[Microsoft 365 Defender ポータルの [インシデント] ページのDefender for Office 365からインシデントとアラートを管理](mdo-sec-ops-manage-incidents-and-alerts.md)するための概要を説明します。

[Microsoft 365 Defenderセキュリティ操作ガイドには、](/microsoft-365/security/defender/integrate-microsoft-365-defender-secops)計画と開発に使用できる追加情報が含まれています。

## <a name="daily-activities"></a>毎日のアクティビティ

### <a name="monitor-the-microsoft-365-defender-incidents-queue"></a>Microsoft 365 Defenderインシデント キューを監視する

Microsoft 365 Defender ポータル<https://security.microsoft.com/incidents-queue>の [**インシデント**] ページ (インシデント _キュー_ とも呼ばれます) では、Defender for Office 365の次のソースからイベントを管理および監視できます。

- [アラート](../../compliance/alert-policies.md#default-alert-policies)。
- [自動調査と応答 (AIR)](automated-investigation-response-office.md)。

インシデント キューの詳細については、「[Microsoft 365 Defenderでのインシデントの優先順位付け](../defender/incident-queue.md)」を参照してください。

インシデント キューを監視するためのトリアージ 計画では、インシデントに対して次の優先順位を使用する必要があります。

1. **潜在的に悪意のある URL クリックが検出されました**。
2. **ユーザーが電子メールの送信を制限されている**。
3. **不審な電子メール送信パターンが検出されました**。
4. **ユーザーがマルウェアまたはフィッシングとして報告した電子メール** と、 **複数のユーザーがマルウェアまたはフィッシングとして電子メールを報告しました**。
5. **配信後に削除された悪意のあるファイルを含む電子****メール メッセージ、配信後に削除された悪意のある URL を含む電子メール メッセージ、配信後****に削除されたキャンペーンからのメール メッセージ**。
6. **ETR オーバーライドが原因で配信されたフィッシング**、 **ユーザーの迷惑メール フォルダーが無効になっているために配信されたフィッシング**、 **IP 許可ポリシーが原因で配信されたフィッシング**
7. **ZAP が無効になっていて、ZAP が無効****になっているため、フィッシング詐欺がザップされていないため、マルウェアはザップされません**。

インシデント キューの管理と責任あるペルソナについては、次の表で説明します。

|最新情報|頻度|説明|ペルソナ|
|---|---|---|---|
|インシデント キュー <https://security.microsoft.com/incidents-queue>内のインシデントのトリアージ|毎日|Defender for Office 365からのすべての **中** 重大度インシデントと **高** 重大度インシデントがトリアージされていることを確認します。|セキュリティ運用チーム|
|インシデントに対する対応アクションを調査して実行します。|毎日|すべてのインシデントを調査し、推奨または手動の応答アクションを積極的に実行します。|セキュリティ運用チーム|
|インシデントを解決します。|毎日|インシデントが修復された場合は、インシデントを解決します。 インシデントを解決すると、リンクされた関連するすべてのアクティブなアラートが解決されます。|セキュリティ運用チーム|
|インシデントを分類します。|毎日|インシデントを true または false として分類します。 真のアラートの場合は、脅威の種類を指定します。 この分類は、セキュリティ チームが脅威パターンを確認し、組織を防御するのに役立ちます。|セキュリティ運用チーム|

### <a name="manage-false-positive-and-false-negative-detections"></a>誤検知と誤検知の検出を管理する

Defender for Office 365では、次の場所で誤検知 (不正とマークされた良いメール) と誤ったメール (許可された不適切なメール) を管理します。

- [申請ポータル (管理者の申請)](admin-submission.md)。
- [テナント許可/ブロック一覧](tenant-allow-block-list.md)
- [脅威エクスプローラー](threat-explorer.md)

詳細については、この記事の後半の「 [誤検知と誤検知の管理](#manage-false-positive-and-false-negative-detections) 」セクションを参照してください。

次の表では、偽陽性と偽陰性の管理と責任あるペルソナについて説明します。

|最新情報|頻度|説明|ペルソナ|
|---|---|---|---|
|Microsoft <https://security.microsoft.com/reportsubmission>に false positives と false negatives を送信します。.|毎日|不適切な電子メール、URL、およびファイルの検出を報告して、Microsoft にシグナルを提供します。|セキュリティ運用チーム|
|管理者提出の詳細を分析します。|毎日|Microsoft に提出する際の次の要素について理解します。 <ul><li>false positive ofr false negative の原因。</li><li>送信時のDefender for Office 365構成の状態。</li><li>Defender for Office 365構成を変更する必要があるかどうか。</li></ul>|セキュリティ運用チーム <br/><br/> セキュリティ管理|
|テナント許可/ブロック 一覧にブロック エントリを追加します <https://security.microsoft.com/tenantAllowBlockList>。|毎日|テナント許可/ブロック リストを使用して、必要に応じて誤った URL、ファイル、または送信者の検出用のブロック エントリを追加します。|セキュリティ運用チーム|
|検疫から偽陰性を解放します。|毎日|受信者がメッセージが誤って検疫されたことを確認したら、ユーザーのリリース要求をリリースまたは承認できます。 <br/><br/> ユーザーが独自の検疫済みメッセージに対して実行できる操作 (リリースや要求のリリースを含む) を制御するには、「 [検疫ポリシー](quarantine-policies.md)」を参照してください。|セキュリティ運用チーム <br/><br/> メッセージング チーム|

### <a name="review-phishing-and-malware-campaigns-that-resulted-in-delivered-mail"></a>メールの配信につながったフィッシングやマルウェアのキャンペーンを確認する

|最新情報|頻度|説明|ペルソナ|
|---|---|---|---|
|メール キャンペーンを確認します。|毎日|組織<https://security.microsoft.com/campaigns>をターゲットにした[メール キャンペーンを確認](campaigns.md)します。 メッセージが受信者に配信されたキャンペーンに焦点を当てます。 <br/><br/> ユーザー メールボックスに存在するキャンペーンからメッセージを削除します。 このアクションは、インシデントからのアクション、 [ゼロ時間自動消去 (ZAP)](zero-hour-auto-purge.md)、手動修復によってまだ修復されていないメールがキャンペーンに含まれている場合にのみ必要です。|セキュリティ運用チーム|

## <a name="weekly-activities"></a>毎週のアクティビティ

### <a name="review-email-detection-trends-in-defender-for-office-365-reports"></a>Defender for Office 365 レポートの電子メール検出の傾向を確認する

Defender for Office 365では、次のレポートを使用して、組織内の電子メール検出の傾向を確認できます。

- [Mailflow 状態レポート](view-mail-flow-reports.md#mailflow-status-report)
- [Threat Protection の状態レポート](view-email-security-reports.md#threat-protection-status-report)

|最新情報|頻度|説明|ペルソナ|
|---|---|---|---|
|電子メール検出レポートを次の時点で確認します。 <ul><li><https://security.microsoft.com/reports/TPSAggregateReportATP></li><li><https://security.microsoft.com/mailflowStatusReport?viewid=type></li></ul>|週次|適切なメールと比較して、マルウェア、フィッシング、スパムの電子メール検出の傾向を確認します。 時間の経過と共に観察することで、脅威パターンを確認し、Defender for Office 365 ポリシーを調整する必要があるかどうかを判断できます。|セキュリティ管理 <br/><br/> セキュリティ運用チーム|

### <a name="track-and-respond-to-emerging-threats-using-threat-analytics"></a>脅威分析を使用して、新たな脅威を追跡して対応する

[脅威分析](/microsoft-365/security/defender-endpoint/threat-analytics)を使用して、アクティブで傾向がある脅威を確認します。

|最新情報|頻度|説明|ペルソナ|
|---|---|---|---|
|脅威分析で脅威を確認する<https://security.microsoft.com/threatanalytics3>|週次|脅威分析では、次の項目を含む詳細な分析が提供されます。 <ul><li>Iocs。</li><li>アクティブな脅威アクターとそのキャンペーンに関する検索クエリ。</li><li>一般的で新しい攻撃手法。</li><li>重大な脆弱性。</li><li>一般的な攻撃面。</li><li>一般的なマルウェア。</li></ul>|セキュリティ運用チーム <br/><br/> 脅威ハンティング チーム|

### <a name="review-top-targeted-users-for-malware-and-phishing"></a>マルウェアとフィッシングの対象ユーザーの上位を確認する

脅威エクスプローラーの [ **[対象ユーザーの上位](threat-explorer.md#top-targeted-users)** ] タブを使用して、マルウェアとフィッシングメールの上位ターゲットであるユーザーを検出または確認します。

|最新情報|頻度|説明|ペルソナ|
|---|---|---|---|
|脅威エクスプローラーの [ **対象ユーザーの上位** ] タブを <https://security.microsoft.com/threatexplorer>確認します。|週次|この情報を使用して、これらのユーザーのポリシーまたは保護を調整する必要があるかどうかを判断します。 影響を受けるユーザーを [Priority アカウント](/microsoft-365/admin/setup/priority-accounts) に追加して、次の利点を得ます。 <ul><li>インシデントがそれらに影響を与える場合の追加の可視性。</li><li>エグゼクティブ メール フロー パターン (優先度アカウント保護) 用にカスタマイズされたヒューリスティック。</li><li>[優先度アカウントレポートの電子メールの問題](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)</li></ul>|セキュリティ管理 <br/><br/> セキュリティ運用チーム|

### <a name="review-top-malware-and-phishing-campaigns-that-target-your-organization"></a>組織を対象とするマルウェアとフィッシングの上位キャンペーンを確認する

キャンペーン ビューでは、組織に対するマルウェアとフィッシング攻撃が明らかにされます。 詳細については、「[Microsoft Defender for Office 365のキャンペーン ビュー」を](campaigns.md)参照してください。

|最新情報|頻度|説明|ペルソナ|
|---|---|---|---|
|**キャンペーン ビュー** を<https://security.microsoft.com/campaigns>使用して、影響を与えるマルウェアやフィッシング攻撃を確認します。|週次|攻撃と手法と、Defender for Office 365が識別してブロックできたものについて説明します。 <br/><br/> キャンペーンの詳細については、キャンペーン ビューで **脅威レポートのダウンロード** を使用します。|セキュリティ運用チーム|

## <a name="ad-hoc-activities"></a>アドホック アクティビティ

### <a name="manual-investigation-and-removal-of-email"></a>手動による調査と電子メールの削除

|最新情報|頻度|説明|ペルソナ|
|---|---|---|---|
|ユーザー要求に基づいて、脅威エクスプローラーで <https://security.microsoft.com/threatexplorer> 不適切なメールを調査して削除します。|アドホック|脅威エクスプローラーの **トリガー調査** アクションを使用して、過去 30 日間の電子メールで自動調査と応答プレイブックを開始します。 調査を手動でトリガーすると、次のような一元的な時間と労力が節約されます。 <ul><li>ルート調査。</li><li>脅威を特定して関連付ける手順。</li><li>これらの脅威を軽減するための推奨されるアクション。</li></ul> <br/> 詳細については、「[例: ユーザーから報告されたフィッシング メッセージが調査プレイブックを起動する」を](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)参照してください。 <br/><br/> または、脅威エクスプローラーを使用して、強力な検索機能とフィルター処理機能を備えた [電子メールを手動で調査](investigate-malicious-email-that-was-delivered.md) し、同じ場所から直接 [手動応答アクションを実行](remediate-malicious-email-delivered-office-365.md) することもできます。 使用可能な手動アクション: <ul><li>受信トレイに移動する</li><li>迷惑メールに移動する</li><li>削除済みアイテムに移動する</li><li>論理的な削除</li><li>ハード削除。</li></ul>|セキュリティ運用チーム|

### <a name="proactively-hunt-for-threats"></a>積極的に脅威を捜索する

|最新情報|頻度|説明|ペルソナ|
|---|---|---|---|
|脅威に対する定期的なプロアクティブな捜索: <ul><li><https://security.microsoft.com/threatexplorer></li><li><https://security.microsoft.com/v2/advanced-hunting></li></ul>.|アドホック|[脅威エクスプローラー](threat-explorer.md)と[高度な捜索](../defender-endpoint/advanced-hunting-overview.md)を使用して脅威を検索します。|セキュリティ運用チーム <br/><br/> 脅威ハンティング チーム|
|検索クエリを共有します。|アドホック|頻繁に使用される便利なクエリをセキュリティ チーム内で積極的に共有し、手動での脅威の検出と修復を高速化します。 <br/><br/> [高度なハンティングでは](/microsoft-365/security/defender/advanced-hunting-shared-queries)[、脅威トラッカー](threat-trackers.md)と共有クエリを使用します。|セキュリティ運用チーム <br/><br/> 脅威ハンティング チーム|
|でカスタム検出ルールを <https://security.microsoft.com/custom_detection>作成します。|アドホック|事前捜索のDefender for Office 365 データに基づいて、イベント、パターン、脅威を事前に監視する[カスタム検出ルールを作成](../defender/advanced-hunting-overview.md#get-started-with-advanced-hunting)します。 検出ルールには、一致する条件に基づいてアラートを生成する高度なハンティング クエリが含まれています。|セキュリティ運用チーム <br/><br/> 脅威ハンティング チーム|

### <a name="review-defender-for-office-365-policy-configurations"></a>Defender for Office 365 ポリシー構成を確認する

|最新情報|頻度|説明|ペルソナ|
|---|---|---|---|
|Defender for Office 365 ポリシー<https://security.microsoft.com/configurationAnalyzer>の構成を確認します。|アドホック <br/><br/> 毎月|[構成アナライザー](configuration-analyzer-for-security-policies.md)を使用して、既存のポリシー設定を[、Defender for Office 365の推奨される Standard または Strict の値と](recommended-settings-for-eop-and-office365.md)比較します。 Configuration アナライザーは、組織のセキュリティ体制を低下させる可能性のある偶発的または悪意のある変更を識別します。 <br/><br/> または、Yu は PowerShell ベースの [ORCA ツールを](https://aka.ms/getorca)使用できます。|セキュリティ管理 <br/><br/> メッセージング チーム|
|Defender for Office 365で検出オーバーライドを確認する<https://security.microsoft.com/reports/TPSMessageOverrideReportATP>|アドホック <br/><br/> 毎月|**Threat Protection 状態レポート** の [システム [オーバーライド\>によるグラフの内訳を理由別に表示] ビュー](view-email-security-reports.md#view-data-by-system-override-and-chart-breakdown-by-reason)を使用して、フィッシングとして検出されたが、ポリシーまたはユーザーオーバーライドの設定が原因で配信された電子メールを確認します。 <br/><br/> 悪意があると判断された電子メールの配信を回避するために、オーバーライドを積極的に調査、削除、または微調整します。|セキュリティ管理 <br/><br/> メッセージング チーム|

### <a name="review-spoof-and-impersonation-detections"></a>スプーフィングと偽装の検出を確認する

|最新情報|頻度|説明|ペルソナ|
|---|---|---|---|
|**スプーフィング インテリジェンスの分析情報** と **偽装検出の分析情報を確認します**。 <ul><li><<https://security.microsoft.com/spoofintelligence>></li><li><https://security.microsoft.com/impersonationinsight></li></ul>.|アドホック <br/><br/> 毎月|[スプーフィング インテリジェンス分析情報](learn-about-spoof-intelligence.md)と[偽装分析情報](impersonation-insight.md)を使用して、スプーフィングと偽装の検出のフィルター処理を調整します。|セキュリティ管理 <br/><br/> メッセージング チーム|

### <a name="review-priority-account-membership"></a>優先度の高いアカウント メンバーシップを確認する

|最新情報|頻度|説明|ペルソナ|
|---|---|---|---|
|優先度アカウント <https://security.microsoft.com/securitysettings/userTags>として定義されているユーザーを確認します。.|アドホック|組織の変更に伴う [優先度アカウント](/microsoft-365/admin/setup/priority-accounts) のメンバーシップを最新の状態に保ち、それらのユーザーに対して次の利点を得ます。 <ul><li>レポートの可視性を向上します。</li><li>インシデントとアラートでのフィルター処理。</li><li>エグゼクティブ メール フロー パターン (優先度アカウント保護) 用にカスタマイズされたヒューリスティック。</li></ul> <br/> 他の [ユーザー](user-tags.md) が取得するには、カスタム ユーザー タグを使用します。 <ul><li>レポートの可視性を向上します。</li><li>インシデントとアラートでのフィルター処理。</li></ul>|セキュリティ運用チーム|

## <a name="appendix"></a>付録

### <a name="learn-about-microsoft-defender-for-office-365-tools-and-processes"></a>Microsoft Defender for Office 365ツールとプロセスについて学習する

セキュリティ運用と対応チーム のメンバーは、Defender for Office 365ツールと機能を既存の調査と対応プロセスに統合する必要があります。 新しいツールや機能に関するラーニングには時間がかかる場合がありますが、オンボーディング プロセスの重要な部分です。 SecOps と電子メール セキュリティ チーム のメンバーがDefender for Office 365について学ぶ最も簡単な方法は、Ninja トレーニング コンテンツの一部として使用できるトレーニング コンテンツ<https://aka.ms/mdoninja>を使用することです。

コンテンツは、レベルごとに複数のモジュールを使用して、さまざまな知識レベル (基礎、中間、および高度) 用に構成されています。

特定のタスクの短いビデオは[、Microsoft Defender for Office 365 YouTube チャネル](https://www.youtube.com/playlist?list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf)でも利用できます。

### <a name="permissions-for-defender-for-office-365-activities-and-tasks"></a>Defender for Office 365アクティビティとタスクのアクセス許可

Microsoft 365 Defender ポータルと PowerShell でDefender for Office 365を管理するためのアクセス許可は、ロールベースのアクセス制御 (RBAC) アクセス許可モデルに基づいています。 RBAC は、ほとんどのMicrosoft 365 サービスで使用されるのと同じアクセス許可モデルです。 詳細については、「[Microsoft 365 Defender ポータルのアクセス許可](permissions-microsoft-365-security-center.md)」を参照してください。

> [!NOTE]
> Azure ADのPrivileged Identity Management (PIM) は、SecOps 担当者に必要なアクセス許可を割り当てる方法でもあります。 詳細については、[Privileged Identity Management (PIM) とMicrosoft Defender for Office 365で使用する理由を](use-privileged-identity-management-in-defender-for-office-365.md)参照してください。

次のアクセス許可 (ロールと役割グループ) はDefender for Office 365で使用でき、セキュリティ チーム メンバーへのアクセスを許可するために使用できます。

- **Azure AD ロール**: Defender for Office 365を含 _むすべての_ Microsoft 365 サービスのアクセス許可を割り当てる一元化されたロール。 Microsoft 365 Defender ポータルでは、Azure AD ロールと割り当てられたユーザーを表示できますが、直接管理することはできません。 代わりに、Azure AD ロールとメンバー<https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/RolesAndAdministrators>を . セキュリティ チームで最も頻繁に使用されるロールは次のとおりです。
  - **セキュリティ管理者**
  - **セキュリティ オペレーター**
  - **セキュリティ閲覧者**

- **電子メール & コラボレーション ロール**: Microsoft Defender for Office 365に固有のアクセス許可を付与するロールと役割グループ。 次のロールはAzure ADでは使用できませんが、セキュリティ チームにとって重要な場合があります。

  - **プレビュー** ロール: 調査アクティビティの一環として電子メール メッセージをプレビューまたはダウンロードする必要があるチーム メンバーにこのロールを割り当てます。 ユーザーは、電子メール エンティティ ページを使用して、クラウド メールボックス内の[電子メール](mdo-email-entity-page.md#email-preview-for-cloud-mailboxes) メッセージを[プレビューおよびダウンロード](investigate-malicious-email-that-was-delivered.md#preview-role-permissions)できます。

    既定では、このロールは次の役割グループにのみ割り当てられます。

    - データ調査員
    - 電子情報開示マネージャー

    このロールを新規または既存の役割グループに割り当てるには、[Microsoft 365 Defender ポータルで電子メール &コラボレーション ロールメンバーシップを変更する方法に関するページを](permissions-microsoft-365-security-center.md#modify-email--collaboration-role-membership-in-the-microsoft-365-defender-portal)参照してください。

  - **検索ロールと消去** ロール: AIR が推奨する悪意のあるメッセージの削除を承認するか、脅威エクスプローラーなどのハンティング エクスペリエンスでメッセージに対して手動でアクションを実行します。

    既定では、このロールは次の役割グループにのみ割り当てられます。

    - データ調査員
    - 組織の管理

    このロールを新規または既存の役割グループに割り当てるには、[Microsoft 365 Defender ポータルで電子メール &コラボレーション ロールメンバーシップを変更する方法に関するページを](permissions-microsoft-365-security-center.md#modify-email--collaboration-role-membership-in-the-microsoft-365-defender-portal)参照してください。

  - **テナント AllowBlockList Manager: テナント** 許可 [/ブロック リスト](tenant-allow-block-list.md)の許可エントリとブロック エントリを管理します。 URL、ファイル (ファイル ハッシュを使用) または送信者をブロックすることは、配信された悪意のある電子メールを調査するときに実行する便利な応答アクションです。

    既定では、このロールは **セキュリティ オペレーター** の役割グループにのみ割り当てられます。 ただし、 **セキュリティ管理者** および **組織管理** 役割グループのメンバーは、テナント許可/ブロックリストのエントリを管理することもできます。

### <a name="siemsoar-integration"></a>SIEM/SOAR 統合

Defender for Office 365は、一連のプログラム API を使用してほとんどのデータを公開します。 これらの API は、ワークフローを自動化し、Defender for Office 365機能を最大限に活用するのに役立ちます。 データは[、Microsoft 365 Defender API を](/microsoft-365/security/defender/api-overview)使用して利用でき、Defender for Office 365を既存の SIEM/SOAR ソリューションに統合するために使用できます。

- [インシデント API](/microsoft-365/security/defender/api-incident): Defender for Office 365 アラートと自動調査は、Microsoft 365 Defenderのインシデントのアクティブな部分です。 セキュリティ チームは、完全な攻撃範囲と影響を受けるすべての資産をまとめてグループ化することで、重要な点に重点を置くことができます。

- [イベント ストリーミング API](/microsoft-365/security/defender/streaming-api): リアルタイム のイベントとアラートを 1 つのデータ ストリームに配信できます。 サポートされているDefender for Office 365イベントの種類は次のとおりです。
  - [EmailEvents](/microsoft-365/security/defender/advanced-hunting-emailevents-table)
  - [EmailUrlInfo](/microsoft-365/security/defender/advanced-hunting-emailurlinfo-table)
  - [EmailAttachmentInfo](/microsoft-365/security/defender/advanced-hunting-emailattachmentinfo-table)
  - [EmailPostDeliveryEvents](/microsoft-365/security/defender/advanced-hunting-emailpostdeliveryevents-table)

  イベントには、過去 30 日間のすべての電子メール (組織内メッセージを含む) を処理したデータが含まれています。

- [Advance Hunting API](/microsoft-365/security/defender/api-advanced-hunting): 製品間の脅威の検出を許可します。

- [脅威評価 API](/graph/api/resources/threatassessment-api-overview): スパム、フィッシング URL、またはマルウェアの添付ファイルを Microsoft に直接報告するために使用できます。

Microsoft Sentinel でDefender for Office 365インシデントと未加工データを接続するには、[Microsoft 365 Defender (M365D) コネクタ](/azure/sentinel/connect-microsoft-365-defender?tabs=MDO)を使用できます。

この単純な "Hello World" の例を使用して、Microsoft Defender API への API アクセスをテストできます。[Microsoft 365 Defender REST API のHello World](/microsoft-365/security/defender/api-hello-world)。

SIEM ツールの統合の詳細については、「[MICROSOFT 365 DEFENDERと SIEM ツールを統合する](/microsoft-365/security/defender/configure-siem-defender)」を参照してください。

## <a name="address-false-positives-and-false-negatives-in-defender-for-office-365"></a>Defender for Office 365の誤検知と誤検知に対処する

電子メール メッセージのユーザーの送信と管理者の送信は、機械学習検出システムにとって重要な肯定的な強化信号です。 提出は、攻撃のレビュー、トリアージ、迅速な学習、軽減に役立ちます。 誤検知と偽陰性を積極的に報告することは、検出中に間違いが発生したときにDefender for Office 365にフィードバックを提供する重要なアクティビティです。

組織には、ユーザー申請を構成するための複数のオプションがあります。 構成によっては、ユーザーが Microsoft に偽陽性または偽陰性を送信すると、セキュリティ チームが積極的に関与する可能性があります。

- ユーザーが [報告したメッセージ設定](user-submission.md) が次のいずれかの設定で構成されている場合、ユーザーの送信は分析のために Microsoft に送信されます。
  - 報告されたメッセージを Microsoft に送信します。
  - 報告されたメッセージを Microsoft と組織のメールボックスに送信します。

  セキュリティ チームのメンバーは、ユーザーによって報告されなかった誤検知または偽陰性が運用チームによって検出された場合に、アドホック [管理者の提出](admin-submission.md) を行う必要があります。

- ユーザーが報告したメッセージが組織のメールボックスにのみメッセージを送信するように構成されている場合、セキュリティ チームは管理者の提出を通じて、ユーザーが報告した誤検知と偽陰性を Microsoft に積極的に送信する必要があります。

ユーザーがフィッシングとしてメッセージを報告するたびに、Defender for Office 365アラートが生成され、アラートによって AIR プレイブックがトリガーされます。 インシデント ロジックは、この情報を可能な限り他のアラートやイベントに関連付けます。 この情報の統合は、セキュリティ チームがユーザーから報告された電子メールをトリアージ、調査、および応答するのに役立ちます。

ユーザーの提出と管理者の提出は、厳密に統合されたプロセスに従う Microsoft によって送信パイプラインによって処理されます。 このプロセスには、次のものが含まれます。

- ノイズリダクション。
- 自動トリアージ。
- セキュリティ アナリストと人間が提携する機械学習ベースのソリューションによる採点。

詳細については、「[Defender for Office 365の電子メールのレポート - Microsoft Tech Community](https://techcommunity.microsoft.com/t5/microsoft-defender-for-office/reporting-an-email-in-microsoft-defender-for-office-365/ba-p/2870231)」を参照してください。

セキュリティ チーム のメンバーは、Microsoft 365 Defender ポータルの複数の場所から次の場所で<https://security.microsoft.com>申請を行うことができます。

- [管理者の提出](admin-submission.md): 申請ポータルを使用して、疑わしいスパム、フィッシング、URL、ファイルを Microsoft に送信します。
- 次のいずれかのメッセージ アクションを使用して、脅威エクスプローラーから直接実行します。
  - クリーンなレポート
  - フィッシングを報告する
  - マルウェアを報告する
  - スパムを報告する

  最大 10 個のメッセージを選択して、一括送信を実行できます。 この方法で作成された管理者の申請は、申請ポータルにも表示されます。

誤検知の短期的な軽減策として、セキュリティ チームは[テナント許可/ブロック リスト](tenant-allow-block-list.md)内のファイル、URL、送信者の[ブロック エントリ](manage-tenant-blocks.md)を直接管理できます。

誤った負の短期的な軽減策として、セキュリティ チームはテナント許可/ブロックリストの [許可エントリ](manage-tenant-allows.md) を直接管理することはできません。 代わりに、 [管理者の提出](admin-submission.md) と **、[このオプションのようなメッセージを許可する]** を使用する必要があります。

Defender for Office 365の[検疫](manage-quarantined-messages-and-files.md)には、潜在的に危険なメッセージや不要なメッセージやファイルが保持されます。 セキュリティ チームは、すべてのユーザーのすべての種類の検疫済みメッセージを表示、リリース、削除できます。 この機能により、セキュリティ チームは、誤検知メッセージまたはファイルが検疫されたときに効果的に応答できます。

## <a name="integrate-third-party-reporting-tools-with-defender-for-office-365-user-submission"></a>サード パーティのレポート ツールとDefender for Office 365ユーザー申請を統合する

組織でサードパーティのレポート ツールを使用して、ユーザーが疑わしいメールを内部的に報告できる場合は、このツールをDefender for Office 365のユーザー提出機能と統合できます。 この統合は、セキュリティ チームに次の利点を提供します。

- Defender for Office 365の AIR 機能との統合。
- 簡略化されたトリアージ。
- 調査と応答時間を短縮しました。

Microsoft 365 Defender ポータル<https://security.microsoft.com/userSubmissionsReportMessage>の [ユーザー **申請**] ページで、ユーザーから報告されたメッセージが送信されるカスタム メールボックスを指定します。 詳細については、「 [ユーザーが報告したメッセージ設定](user-submission.md)」を参照してください。

> [!NOTE]
>
> - カスタム メールボックスは、Exchange Online メールボックスです。
> - サード パーティのレポート ツールには、元の報告されたメッセージを非圧縮として含める必要があります。EML または .カスタム メールボックスに送信されるメッセージの MSG 添付ファイル (元のメッセージをカスタム メールボックスに転送するだけではありません)。
> - カスタム メールボックスには、潜在的に不適切なメッセージの配信を許可するための特定の前提条件が必要です。 詳細については、「 [カスタム メールボックスの前提条件](user-submission.md#custom-mailbox-prerequisites)」を参照してください。

ユーザーが報告した電子メールがカスタム メールボックスに届くと、Defender for Office 365ユーザー **によってマルウェアまたはフィッシングとして報告された Email** という名前のアラートが自動的に生成されます。 このアラートは [、AIR プレイブック](automated-investigation-response-office.md#example-a-user-reported-phish-message-launches-an-investigation-playbook)を起動します。 プレイブックは、一連の自動調査手順を実行します。

- 指定したメールに関するデータを収集します。
- そのメールに関連する脅威とエンティティに関するデータを収集します。 エンティティには、ファイル、URL、受信者を含めることができます。
- 調査の結果に基づいて、SecOps チームに推奨されるアクションを提供します。

マルウェアやフィッシング アラート、自動調査、推奨されるアクション **としてユーザーによって報告された電子メール** は、Microsoft 365 Defenderのインシデントと自動的に関連付けられます。 この相関関係により、セキュリティ チームのトリアージと応答プロセスがさらに簡略化されます。 複数のユーザーが同じメッセージまたは類似のメッセージを報告する場合、すべてのユーザーとメッセージが同じインシデントに関連付けられます。

Defender for Office 365のアラートと調査からのデータは、他のMicrosoft 365 Defender製品のアラートや調査と自動的に比較されます。

- Microsoft Defender for Endpoint
- Microsoft Defender for Cloud Apps
- Microsoft Defender for Identity

リレーションシップが検出された場合、システムは、攻撃全体の可視性を提供するインシデントを作成します。
