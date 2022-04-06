---
title: 試Microsoft Defender for Office 365
description: ''
keywords: ''
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
ms.custom: ''
ms.technology: mdo
ms.prod: m365-security
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: bda7d0cc95132f1f421fc49e5fc6e7453267c4b0
ms.sourcegitcommit: bcbcbd4ddc72ad2fed629619d23fac5827d072bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/29/2022
ms.locfileid: "64507260"
---
# <a name="try-microsoft-defender-for-office-365"></a>試Microsoft Defender for Office 365

> [!NOTE]
> この記事で説明する機能はプレビューで、すべての組織で使用できるとは言え、変更される可能性があります。

Microsoft 365 Defender ポータルの統合試用版ポータルは、以前は別の試用版と評価エクスペリエンスの 1 つのエントリ ポイントを提供Microsoft Defender for Office 365。 この目的は、完全にコミットする前Defender for Office 365プラン 2 の機能を 30 日間試し込む方法です。 ただし、評価エクスペリエンスには、組織の性質に基づくMicrosoft 365があります。

- 既にメールボックスMicrosoft 365持っていますが、現在、メール保護のためにサードパーティのサービスまたはデバイスを使用しています。 インターネットからのメールは、組織に配信する前に保護サービスMicrosoft 365されます。 Microsoft 365可能な限り低い保護です (完全にオフになったことはありません。たとえば、マルウェア保護は常に適用されます)。

  ![メールは、サードパーティの保護サービスまたはデバイスを介してインターネットから配信された後、Microsoft 365。](../../media/mdo-migration-before.png)

  これらの環境では、監査モードでのみDefender for Office 365 *試* してください。 メール フロー (MX レコード) を変更して、メール フローを試すDefender for Office 365。

- 既に組織にMicrosoft 365があります。 インターネットからのメールは直接Microsoft 365流れますが、現在のサブスクリプションには Exchange Online Protection [(EOP)](exchange-online-protection-overview.md) または Defender for Office 365[プラン 1](overview.md#microsoft-defender-for-office-365-plan-1-vs-plan-2-cheat-sheet) のみです。

  ![メールはインターネットからインターネットにMicrosoft 365、EOP やプラン 1 からのDefender for Office 365保護されます。](../../media/mdo-trial-mail-flow.png)

  これらの環境では、監査モードDefender for Office 365 *ブロック* モードでテストを *実行できます*。

ポータルでさまざまな機能の場所で試用版Defender for Office 365開始Microsoft 365 Defender招待されています<https://security.microsoft.com>。 試用版を開始する一元的な場所は、 **の [試用版** ] ページです <https://security.microsoft.com/atpEvaluation>。

この記事の残りの部分では、監査モードのブロック モード、評価の構成方法、その他の詳細の違いについて説明します。

## <a name="overview-of-defender-for-office-365"></a>概要 Defender for Office 365

Defender for Office 365機能の包括的なスレートを提供することで、組織が企業をセキュリティで保護するのに役立ちます。 詳細については、「Microsoft Defender for Office 365」[を参照してください](defender-for-office-365.md)。

この対話型ガイドでは、Defender for Office 365の詳細を[確認できます](https://aka.ms/MS365D.InteractiveGuide)。

![Microsoft Defender for Office 365概念図を参照してください。](../../media/microsoft-defender-for-office-365.png)

## <a name="policies-in-blocking-mode-or-audit-mode"></a>ブロック モードまたは監査モードのポリシー

ポリシーを評価Defender for Office 365、ユーザーの保護機能を制御するポリシー Microsoft 365存在します。

- **Exchange Online Protection (EOP)**: 新しいポリシーや特別なポリシーは作成されません。 既存の EOP ポリシーは、メッセージに対して動作できます (たとえば、迷惑メール フォルダーへのメッセージの送信や検疫など)。

  - [マルウェア対策ポリシー](anti-malware-protection.md)
  - [受信スパム対策保護](anti-spam-protection.md)
  - [フィッシング対策ポリシーのスプーフィング対策保護](set-up-anti-phishing-policies.md#spoof-settings)

  これらの機能の既定のポリシーは常にオンであり、すべての受信者に適用され、常に最後に適用されます (カスタム ポリシーの後)。

- **Defender for Office 365**: ポリシーの評価のために、Defender for Office 365に排他的なポリシーがDefender for Office 365。

  - [フィッシング対策ポリシーにおける、なりすまし保護](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
  - [セーフメール メッセージの添付ファイル](safe-attachments.md)
  - [セーフ メール メッセージとメール メッセージのリンクMicrosoft Teams](safe-links.md)

  ただし、これらのポリシーの性質は、ブロック モードと監査モードでは異なります。

  - **監査モード**: 通常のポリシーが作成されますが、ポリシーは脅威を検出するために *のみ構成* されます。 Defender for Office 365に有害なメッセージが検出されますが、メッセージは処理されません (たとえば、検出されたメッセージは検疫されません)。

  - **ブロック モード**: ポリシーは、事前設定されたセキュリティ ポリシーの標準テンプレート [を使用して作成されます](preset-security-policies.md)。 Defender for Office 365 *メッセージを**検出し*、アクションを実行します (たとえば、検出されたメッセージは検疫されます)。

  既定と推奨される選択は、これらのポリシーを組織Defender for Office 365ユーザーに限定します。 ただし、セットアップ中またはセットアップ後に、ポリシーの割り当てを特定のユーザー、グループ、または電子メール ドメインに変更できます。

**注**:

- セーフリンクはメール フロー内の URL をデトナレートします。 特定の URL が削除されるのを防ぐには、テナント許可/ブロック一覧を使用します。 詳細については、「Manage [the Tenant Allow/Block List」を参照してください](tenant-allow-block-list.md)。
- セーフリンクは、電子メール メッセージのボディ内の URL リンクをラップしない。
- 評価ポリシーの設定については、この記事の後半の [「評価ポリシー設定](#evaluation-policy-settings) 」セクションで説明します。

## <a name="set-up-an-evaluation-in-audit-mode"></a>監査モードでの評価のセットアップ

1. [評価 **の開始] をクリックします**。

2. [保護 **を有効にする] ダイアログで** 、[いいえ] を **選択し、レポートのみを作成し**、[続行] を **クリックします**。

3. [含 **めるユーザーの選択] ダイアログで** 、次の設定を構成します。

   - **すべてのユーザー**: これは既定の推奨オプションです。
   - **ユーザーの選択**: このオプションを選択する場合は、評価を適用するユーザーを選択する必要があります。
     - **ユーザー**: 組織内で指定された 1 つ以上のメールボックス、メール ユーザー、またはメール連絡先。
     - **グループ**: 組織内で指定された配布グループ、メール対応セキュリティ グループ、または Microsoft 365 グループ。
     - **ドメイン**: 組織内で指定された [承認済みドメイン](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)のすべての受信者。

     適正なボックスをクリックし、値の入力を開始し、結果で希望する値を選択します。 必要な回数だけこの処理を繰り返します。 既存の値を削除するには、削除をクリックします ![[削除] アイコン](../../media/m365-cc-sc-remove-selection-icon.png) 値の隣。

     ユーザーやグループには、ほとんどの識別子 (名前、表示名、エイリアス、メールアドレス、アカウント名など) を使用できますが、対応する表示名が結果に表示されます。ユーザーの場合、アスタリスク (\*) を単独で入力すると、使用可能なすべての値が表示されます。

   > [!NOTE]
   > これらの選択は、評価の設定が完了した後で変更できます。

   完了したら、[続行] を **クリックします**。

4. [メール **フローの理解に役立つ] ダイアログで** 、次のオプションを構成します。

   - **Microsoft とデータを共有** する: このオプションは既定で選択されますが、必要に合う場合はチェック ボックスをオフにできます。

   - ドメインの MX レコードの検出に基づいて、次のいずれかのオプションが自動的に選択されます。

     - **サードパーティやオンプレミス** のサービス プロバイダーを使用しています。ドメインの MX レコードは、他の場所をMicrosoft 365。 この選択には、[次へ] をクリックした後に次の追加設定が **必要です**。

       1. [サード パーティ **またはオンプレミスの設定** ] ダイアログで、次の設定を構成します。

          - **サード パーティのサービス プロバイダーを選択** する: 次のいずれかの値を選択します。
            - **バラクーダ**
            - **IronPort**
            - **Mimecast**
            - **Proofpoint**
            - **Sophos**
            - **Symantec**
            - **Trend Micro**
            - **その他**

          - **この評価を適用するコネクタ**: メール フローに使用するコネクタを選択して、Microsoft 365。

            [コネクタの拡張フィルター](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) (スキップ *リストとも呼* ばれる) は、指定したコネクタで自動的に構成されます。

            サード パーティのサービスまたはデバイスが Microsoft 365 の場所に存在する場合、コネクタの拡張フィルター処理はインターネット メッセージのソースを正しく識別し、Microsoft フィルター スタック (特にスプーフィング インテリジェンス、および脅威エクスプローラーと自動[](anti-spoofing-protection.md)調査 [& 応答 (AIR)](automated-investigation-response-office.md) の侵害後の機能) [](threat-explorer.md) の精度を大幅に向上します。

          - **メッセージが通過する各ゲートウェイ IP** アドレスを一覧表示する: この設定は、[サード パーティのサービス プロバイダーの選択] で [その他] を選択した場合 **にのみ使用できます**。 サードパーティの保護サービスまたはデバイスがメールを送信するために使用する IP アドレスのコンマ区切りリストを入力Microsoft 365。

          完了したら、**[次へ]** をクリックします。

       2. **[Exchange** メール フロー ルール] ダイアログで、サード パーティの保護サービスまたはデバイスからの受信メッセージに対するスパム フィルター処理をスキップする Exchange Online メール フロー ルール (トランスポート ルールとも呼ばれる) が必要かを決定します。

          Exchange Online に SCL=-1 メール フロー ルールが既に存在し、保護サービスからのすべての受信メールがフィルター処理をバイパスする (ほとんどの) Microsoft 365可能性があります。 多くの保護サービスでは、サービスを使用しているユーザーに対して、このスパム信頼レベル (SCL) メール フロー Microsoft 365方法を推奨しています。

          前の手順で説明したように、コネクタの拡張フィルターは、保護サービスからのメールの送信元として指定したコネクタで自動的に構成されます。

          保護サービスからの受信メールに対して SCL=-1 ルールを使用しないコネクタの拡張フィルター処理を有効にすると、スプーフィング インテリジェンスなどの EOP 保護機能の[](anti-spoofing-protection.md)検出機能が大幅に向上し、新しく検出されたメッセージ (迷惑メール フォルダーへの移動や検疫など) の配信に影響を与える可能性があります。 この影響は EOP ポリシーに限定されます。前に説明したように、Defender for Office 365ポリシーは監査モードで作成されます。

          SCL=-1 メール フロー ルールを作成したり、既存のルールを確認したりするには、ページの  [管理センター Exchangeに移動] ボタンをクリックします。 詳細については、「メール フロー ルールを使用して、メール フローのメッセージでスパム信頼度 [(SCL) を設定する」を参照](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl)Exchange Online。

          完了したら、 **[完了]** をクリックします。

     - **ドメイン ポイントの** Yhe MX レコードMicrosoft Exchange Onlineを使用しているMicrosoft 365。 構成する必要は何も残っていないので、[完了] を **クリックします**。

5. 評価のセットアップ時に進行状況ダイアログが表示されます。 セットアップが完了したら、[完了] を **クリックします**。

## <a name="set-up-an-evaluation-in-blocking-mode"></a>ブロック モードでの評価のセットアップ

1. [評価 **の開始] をクリックします**。

2. [保護を **有効にする] ダイアログで** 、[ **はい] を選択し、** 脅威をブロックして組織を保護し、[続行] をクリック **します**。

3. [含 **めるユーザーの選択] ダイアログで** 、次の設定を構成します。

   - **すべてのユーザー**: これは既定の推奨オプションです。
   - **ユーザーの選択**: このオプションを選択する場合は、評価を適用するユーザーを選択する必要があります。
     - **ユーザー**: 組織内で指定された 1 つ以上のメールボックス、メール ユーザー、またはメール連絡先。
     - **グループ**: 組織内で指定された配布グループ、メール対応セキュリティ グループ、または Microsoft 365 グループ。
     - **ドメイン**: 組織内で指定された [承認済みドメイン](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)のすべての受信者。

     適正なボックスをクリックし、値の入力を開始し、結果で希望する値を選択します。 必要な回数だけこの処理を繰り返します。 既存の値を削除するには、削除をクリックします ![[削除] アイコン](../../media/m365-cc-sc-remove-selection-icon.png) 値の隣。

     ユーザーやグループには、ほとんどの識別子 (名前、表示名、エイリアス、メールアドレス、アカウント名など) を使用できますが、対応する表示名が結果に表示されます。ユーザーの場合、アスタリスク (\*) を単独で入力すると、使用可能なすべての値が表示されます。

   > [!NOTE]
   > これらの選択は、評価の設定が完了した後で変更できます。

   完了したら、[続行] を **クリックします**。

4. 評価のセットアップ時に進行状況ダイアログが表示されます。 セットアップが完了したら、[完了] を **クリックします**。

## <a name="reporting-in-audit-mode"></a>監査モードでのレポート

- 脅威[保護の状態レポートには、](view-email-security-reports.md#threat-protection-status-report)次のビュー Defender for Office 365の検出が表示されます。
  - [検出テクノロジによってメール マルウェアと \> グラフの内訳でデータを表示する](view-email-security-reports.md#view-data-by-email--malware-and-chart-breakdown-by-detection-technology)
  - [検出テクノロジによってメール スパムと \> グラフの内訳でデータを表示する](view-email-security-reports.md#view-data-by-email--spam-and-chart-breakdown-by-detection-technology)
  - [検出テクノロジによってメールフィッシングと \> グラフの内訳でデータを表示する](view-email-security-reports.md#view-data-by-email--phish-and-chart-breakdown-by-detection-technology)

- Threat [Explorer では、](threat-explorer.md)ユーザー評価によって検出されたDefender for Office 365、エントリの詳細に次のバナーが表示されます。

  ![評価者が悪意のある電子メール メッセージDefender for Office 365検出したメッセージの詳細の通知バナー。](../../media/evalv2-detection-banner.png)

<!--- This stuff is likely not applicable for V2 reporting --->

[**Microsoft Defender for Office 365]** ページでは<https://security.microsoft.com/atpEvaluation>、評価のポリシーのレポートを統合します。

- フィッシング対策ポリシーにおける、なりすまし保護
- 安全なリンク
- 安全な添付ファイル

既定では、グラフには過去 30 日間のデータが表示されますが、予定表アイコンをクリックして日付範囲をフィルター ![処理できます。](../../media/m365-cc-sc-add-internal-icon.png) **30 日間、30** 日未満の追加の値を次から選択します。

- 24 時間
- 7 日間
- 14 日
- カスタム日付範囲

[ダウンロード] アイコン ![をクリックできます。](../../media/m365-cc-sc-download-icon.png) **グラフ** データをダウンロードして、グラフ データを .csvします。

## <a name="required-permissions"></a>必要なアクセス許可

次の一覧 **では、Azure AD** の Defender の評価を設定するためにMicrosoft 365アクセス許可について説明します。

- **評価の作成、変更、または削除**:セキュリティ管理者またはグローバル管理者。
- **評価ポリシーとレポートを表示する**: セキュリティ管理者またはセキュリティ リーダー。

Azure AD ポータルのAzure AD詳細については、「Microsoft 365 DefenderポータルAzure AD[ロール」をMicrosoft 365 Defenderしてください。](permissions-microsoft-365-security-center.md#azure-ad-roles-in-the-microsoft-365-defender-portal)

## <a name="evaluation-policy-settings"></a>評価ポリシーの設定

評価用に特別Defender for Office 365作成された設定については、次の表で説明します。

**フィッシング対策評価ポリシーの設定**:

|設定|値|
|---|---|
|AdminDisplayName|評価ポリシー|
|AuthenticationFailAction|MoveToJmf|
|Enabled|True|
|EnableFirstContactSafetyTips|False|
|EnableMailboxIntelligence|True|
|EnableMailboxIntelligenceProtection|True|
|EnableOrganizationDomainsProtection|False|
|EnableSimilarDomainsSafetyTips|False|
|EnableSimilarUsersSafetyTips|False|
|EnableSpoofIntelligence|True|
|EnableSuspiciousSafetyTip|False|
|EnableTargetedDomainsProtection|False|
|EnableTargetedUserProtection|False|
|EnableUnauthenticatedSender|True|
|EnableUnusualCharactersSafetyTips|False|
|EnableViaTag|True|
|Guid|GUID 値|
|ImpersonationProtectionState|Manual|
|IsDefault|False|
|MailboxIntelligenceProtectionAction|NoAction|
|MailboxIntelligenceProtectionActionRecipients|{}|
|MailboxIntelligenceQuarantineTag|DefaultFullAccessPolicy|
|名前|評価ポリシー|
|PhishThresholdLevel|1|
|RecommendedPolicyType|評価|
|SpoofQuarantineTag|DefaultFullAccessPolicy|
|TargetedDomainActionRecipients|{}|
|TargetedDomainProtectionAction|NoAction|
|TargetedDomainQuarantineTag|DefaultFullAccessPolicy|
|TargetedUserActionRecipients|{}|
|TargetedUserProtectionAction|NoAction|
|TargetedUserQuarantineTag|DefaultFullAccessPolicy|
|||
|AntiPhishPolicyLevelDataList|空白|
|AntiSpoofEnforcementType|高|
|AuthenticationSafetyTipText|空白|
|AuthenticationSoftPassSafetyTipText|空白|
|EnableAuthenticationSafetyTip|False|
|EnableAuthenticationSoftPassSafetyTip|False|
|PolicyTag|空白|
|SimilarUsersSafetyTipsCustomText|空白|
|TreatSoftPassAsAuthenticated|True|
|UnusualCharactersSafetyTipsCustomText|空白|
|||
|ExcludedDomains|{}|
|ExcludedSenders|{}|
|TargetedDomainsToProtect|{}|
|TargetedUsersToProtect|{}|

**セーフ添付ファイルの評価ポリシー設定**:

|設定|値|
|---|---|
|Action|許可|
|ActionOnError|True|
|AdminDisplayName|評価ポリシー|
|ConfidenceLevelThreshold|80|
|有効にする|True|
|EnableOrganizationBranding|False|
|Guid|GUID 値|
|IsBuiltInProtection|False|
|IsDefault|False|
|名前|評価ポリシー|
|OperationMode|Delay|
|QuarantineTag|AdminOnlyAccessPolicy|
|RecommendedPolicyType|評価|
|Redirect|False|
|RedirectAddress|{}|
|ScanTimeout|30|

**セーフの評価ポリシー設定**:

|設定|値|
|---|---|
|AdminDisplayName|評価ポリシー|
|AllowClickThrough|False|
|CustomNotificationText|空白|
|DeliverMessageAfterScan|True|
|DisableUrlRewrite|True|
|DoNotRewriteUrls|{}|
|EnableForInternalSenders|False|
|EnableOrganizationBranding|False|
|EnableSafeLinksForTeams|True|
|Guid|GUID 値|
|IsBuiltInProtection|False|
|IsDefault|False|
|IsEnabled|True|
|LocalizedNotificationTextList|{}|
|名前|"EvaluationPolicy"|
|RecommendedPolicyType|評価|
|ScanUrls|True|
|TrackClicks|True|
|||
|DoNotAllowClickThrough|空白|
|DoNotTrackUserClicks|False|
|EnableSafeLinksForEmail|True|
|EnableSafeLinksForOffice|True|
|ExcludedUrls|{}|
|WhiteListedUrls|空白|
