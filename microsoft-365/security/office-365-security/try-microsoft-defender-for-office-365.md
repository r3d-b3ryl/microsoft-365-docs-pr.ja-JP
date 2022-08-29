---
title: Defender for Office 365を試して評価する
description: 既存のメール フローに影響を与えずに、Microsoft Defender for Office 365の機能を評価して試す方法について説明します。
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
ROBOTS: ''
ms.openlocfilehash: e46e5f3af06cc94cea4ff2e76208f3ccadc53586
ms.sourcegitcommit: d09eb780dc41a01796eb8137fbe9267231af6746
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2022
ms.locfileid: "67385619"
---
# <a name="try-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365を試す

Microsoft 365 Defender ポータルの統合 **試用版** ポータルでは、Microsoft Defender for Office 365に対する以前の個別の試用版と評価エクスペリエンスの 1 つのエントリ ポイントが提供されます。 目的は、完全にコミットする前に、Defender for Office 365 プラン 2 の機能を 90 日間試してみることです。 ただし、Microsoft 365 組織の性質に基づく評価エクスペリエンスには違いがあります。

- Microsoft 365 メールボックスは既にありますが、現在、電子メール保護にサードパーティのサービスまたはデバイスを使用しています。 インターネットからのメールは、Microsoft 365 組織に配信される前に保護サービスを経由します。 Microsoft 365 の保護は可能な限り低くなっています (完全にオフになることはありません。マルウェア保護は常に適用されます)。

  ![メールは、Microsoft 365 に配信される前に、サード パーティの保護サービスまたはデバイスを介してインターネットから送信されます。](../../media/mdo-migration-before.png)

  これらの環境では、*監査* モードでのみDefender for Office 365を試すことができます。 メール フロー (MX レコード) を変更してDefender for Office 365を試す必要はありません。

- Microsoft 365 組織が既にあります。 インターネットからのメールは Microsoft 365 に直接送信されますが、現在のサブスクリプションには[Exchange Online Protection (EOP)](exchange-online-protection-overview.md) または[Defender for Office 365プラン 1](overview.md#microsoft-defender-for-office-365-plan-1-vs-plan-2-cheat-sheet) のみが含まれます。

  ![メールはインターネットから Microsoft 365 に送信され、EOP やDefender for Office 365プラン 1 からの保護が適用されます。](../../media/mdo-trial-mail-flow.png)

  これらの環境では、*監査* モードまたは *ブロック* モードでDefender for Office 365を試すことができます。

Microsoft 365 Defender ポータル<https://security.microsoft.com>のさまざまなDefender for Office 365機能の場所で試用版を開始するよう招待されます。 試用版を開始するための一元的な場所は、[ **試用版** ] ページの [ <https://security.microsoft.com/atpEvaluation>.

この短いビデオでは、Microsoft Defender for Office 365を使用して短時間でより多くの作業を行う方法について詳しく説明します。
> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWMmIe]

この記事の残りの部分では、監査モードのブロック モード、評価の構成方法、およびその他の詳細の違いについて説明します。

試用版の使用方法に関するコンパニオン ガイドについては、「[試用版プレイブック: Microsoft Defender for Office 365](trial-playbook-defender-for-office-365.md)」を参照してください。

## <a name="overview-of-defender-for-office-365"></a>Defender for Office 365の概要

Defender for Office 365は、組織が包括的な機能を提供することで、企業をセキュリティで保護するのに役立ちます。 詳細については、「[Microsoft Defender for Office 365](defender-for-office-365.md)」を参照してください。

Defender for Office 365の詳細については、この[対話型ガイド](https://aka.ms/MS365D.InteractiveGuide)を参照してください。

![概念図Microsoft Defender for Office 365。](../../media/microsoft-defender-for-office-365.png)

## <a name="policies-in-blocking-mode-or-audit-mode"></a>ブロック モードまたは監査モードのポリシー

Defender for Office 365を評価すると、Microsoft 365 の保護機能を制御するポリシーが存在します。

- **Exchange Online Protection (EOP)**: 新しいポリシーや特別なポリシーは作成されません。 既存の EOP ポリシーは、メッセージに対して動作できます (たとえば、迷惑メール Email フォルダーにメッセージを送信したり、検疫したりできます)。

  - [マルウェア対策ポリシー](anti-malware-protection.md)
  - [受信スパム対策保護](anti-spam-protection.md)
  - [フィッシング対策ポリシーでのスプーフィング対策保護](set-up-anti-phishing-policies.md#spoof-settings)

  これらの機能の既定のポリシーは常にオンであり、すべての受信者に適用され、常に最後に適用されます (カスタム ポリシーの後)。

- **Defender for Office 365**: Defender for Office 365専用のポリシーは、Defender for Office 365を評価するために作成されます。

  - [フィッシング対策ポリシーにおける、なりすまし保護](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
  - [電子メール メッセージの安全な添付ファイル](safe-attachments.md)
  - [電子メール メッセージと Microsoft Teams の安全なリンク](safe-links.md)

  ただし、これらのポリシーの性質は、ブロック モードと監査モードでは異なります。

  - **監査モード**: 通常のポリシーが作成されますが、ポリシーは脅威を *検出* するためにのみ構成されます。 Defender for Office 365はレポート用に有害なメッセージを検出しますが、メッセージは処理されません (検出されたメッセージは検疫されません)。

  - **ブロック モード**: ポリシーは、 [事前設定されたセキュリティ ポリシー](preset-security-policies.md)の Standard テンプレートを使用して作成されます。 Defender for Office 365有害なメッセージを *検出* して *アクションを実行します* (検出されたメッセージは検疫されるなど)。

  既定の選択と推奨される選択は、組織内のすべてのユーザーに対してこれらのDefender for Office 365 ポリシーのスコープを設定することです。 ただし、セットアップ中またはセットアップ後に、ポリシーの割り当てを特定のユーザー、グループ、または電子メール ドメインに変更できます。

**注**:

- 安全なリンクは、メール フロー内の URL をデトネーションします。 特定の URL がデトネーションされないようにするには、テナント許可/ブロック リストを使用します。 詳細については、「 [テナント許可/ブロック リストの管理」を参照してください](manage-tenant-allow-block-list.md)。
- 安全なリンクは、メール メッセージ本文で URL リンクをラップしません。
- 評価ポリシーの設定については、この記事の後半の [「評価ポリシー設定](#evaluation-policy-settings) 」セクションで説明します。

## <a name="set-up-an-evaluation-in-audit-mode"></a>監査モードで評価を設定する

1. [ **評価の開始]** をクリックします。

2. [ **保護を有効にする** ] ダイアログで、[ **いいえ]、[レポートのみ必要**] の順に選択し、[ **続行**] をクリックします。

3. [ **含めるユーザーの選択]** ダイアログで、次の設定を構成します。

   - **すべてのユーザー**: これが既定の推奨オプションです。
   - **ユーザーの選択**: このオプションを選択した場合は、評価が適用される内部受信者を選択する必要があります。
     - **ユーザー**: 指定されたメールボックス、メール ユーザー、またはメール連絡先。
     - **グループ**: 
       - 指定された配布グループまたはメールが有効なセキュリティ グループのメンバー。
       - 指定した Microsoft 365 グループ。
       - **ドメイン**: 組織内で指定された [承認済みドメイン](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)のすべての受信者。

     適正なボックスをクリックし、値の入力を開始し、結果で希望する値を選択します。 必要な回数だけこの処理を繰り返します。 既存の値を削除するには、削除をクリックします ![[削除] アイコン](../../media/m365-cc-sc-remove-selection-icon.png) 値の隣。

     ユーザーやグループには、ほとんどの識別子 (名前、表示名、エイリアス、メールアドレス、アカウント名など) を使用できますが、対応する表示名が結果に表示されます。ユーザーの場合、アスタリスク (\*) を単独で入力すると、使用可能なすべての値が表示されます。

   > [!NOTE]
   > これらの選択は、評価の設定が完了したら変更できます。

   完了したら、[ **続行**] をクリックします。

4. **[メール フローの理解に関するヘルプ**] ダイアログで、次のオプションを構成します。

   - **Microsoft とデータを共有** する: このオプションは既定で選択されていますが、必要に応じてチェック ボックスをオフにすることができます。

   - ドメインの MX レコードの検出に基づいて、次のいずれかのオプションが自動的に選択されます。

     - **サードパーティまたはオンプレミスのサービス プロバイダーを使用しています**。ドメインの MX レコードは、Microsoft 365 以外の場所を指しています。 [ **次へ**] をクリックした後、この選択には次の追加設定が必要です。

       1. [ **サード パーティまたはオンプレミスの設定** ] ダイアログで、次の設定を構成します。

          - **サード パーティのサービス プロバイダーを選択** する: 次のいずれかの値を選択します。
            - **バラクーダ**
            - **IronPort**
            - **Mimecast**
            - **Proofpoint**
            - **ソフォス**
            - **Symantec**
            - **Trend Micro**
            - **その他**

          - **この評価を適用するコネクタ**: Microsoft 365 へのメール フローに使用するコネクタを選択します。

            [コネクタの拡張フィルター処理](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) ( *スキップ リスト* とも呼ばれます) は、指定したコネクタで自動的に構成されます。

            サード パーティのサービスまたはデバイスが Microsoft 365 の前に配置されている場合、コネクタの強化されたフィルター処理によってインターネット メッセージのソースが正しく識別され、Microsoft フィルター スタックの精度が大幅に向上します (特に、ス [プーフィング インテリジェンス](anti-spoofing-protection.md)、 [脅威エクスプローラー](threat-explorer.md) での違反後の機能、および自動 [調査&応答 (AIR)](automated-investigation-response-office.md))。

          - **メッセージが通過する各ゲートウェイ IP アドレスを一覧表示** する: この設定は、[**サード パーティのサービス プロバイダーの選択**] で **[その他]** を選択した場合にのみ使用できます。 サードパーティの保護サービスまたはデバイスが Microsoft 365 にメールを送信するために使用する IP アドレスのコンマ区切りリストを入力します。

          完了したら、**[次へ]** をクリックします。

       2. **[Exchange メール フロー ルール**] ダイアログで、サード パーティの保護サービスまたはデバイスからの受信メッセージのスパム フィルター処理をスキップするExchange Onlineメール フロー ルール (トランスポート ルールとも呼ばれます) が必要かどうかを決定します。

          保護サービスからのすべての受信メールが (ほとんどの) Microsoft 365 フィルター処理をバイパスできるようにする SCL=-1 メール フロー ルールが既にExchange Onlineにある可能性があります。 多くの保護サービスは、サービスを使用している Microsoft 365 のお客様に対して、このスパム信頼レベル (SCL) メール フロー ルール方法を推奨しています。

          前の手順で説明したように、コネクタの拡張フィルター処理は、保護サービスからのメールの送信元として指定したコネクタで自動的に構成されます。

          保護サービスからの受信メールに対して SCL=-1 ルールを使用せずにコネクタの拡張フィルター処理を有効にすると、[スプーフィング インテリジェンス](anti-spoofing-protection.md)などの EOP 保護機能の検出機能が大幅に向上し、新しく検出されたメッセージの配信 (迷惑 Emailメール フォルダーへの移動や検疫など) に影響を与える可能性があります。 この影響は EOP ポリシーに限定されます。前述のように、Defender for Office 365 ポリシーは監査モードで作成されます。

          SCL=-1 メール フロー ルールを作成したり、既存のルールを確認したりするには、ページの **[Exchange 管理センターに移動** ] ボタンをクリックします。 詳細については、「[メール フロー ルールを使用して、Exchange Online内のメッセージでスパム信頼レベル (SCL) を設定](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl)する」を参照してください。

          完了したら、 **[完了]** をクリックします。

     - **Microsoft Exchange Onlineのみを使用** しています。ドメインの MX レコードは Microsoft 365 をポイントします。 構成する必要は残っていないので、[ **完了]** をクリックします。

5. 評価が設定されると、進行状況ダイアログが表示されます。 セットアップが完了したら、[完了] をクリック **します**。

## <a name="set-up-an-evaluation-in-blocking-mode"></a>ブロック モードで評価を設定する

1. [ **評価の開始]** をクリックします。

2. [ **保護を有効にする** ] ダイアログで、[はい] を選択し **、脅威をブロックして組織を保護** し、[ **続行**] をクリックします。

3. [ **含めるユーザーの選択]** ダイアログで、次の設定を構成します。

   - **すべてのユーザー**: これが既定の推奨オプションです。
   - **ユーザーの選択**: このオプションを選択した場合は、評価が適用される内部受信者を選択する必要があります。
     - **ユーザー**: 指定されたメールボックス、メール ユーザー、またはメール連絡先。
     - **グループ**: 
       - 指定された配布グループまたはメールが有効なセキュリティ グループのメンバー。
       - 指定した Microsoft 365 グループ。
     - **ドメイン**: 組織内で指定された [承認済みドメイン](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)のすべての受信者。

     適正なボックスをクリックし、値の入力を開始し、結果で希望する値を選択します。 必要な回数だけこの処理を繰り返します。 既存の値を削除するには、削除をクリックします ![[削除] アイコン](../../media/m365-cc-sc-remove-selection-icon.png) 値の隣。

     ユーザーやグループには、ほとんどの識別子 (名前、表示名、エイリアス、メールアドレス、アカウント名など) を使用できますが、対応する表示名が結果に表示されます。ユーザーの場合、アスタリスク (\*) を単独で入力すると、使用可能なすべての値が表示されます。

   > [!NOTE]
   > これらの選択は、評価の設定が完了したら変更できます。

   完了したら、[ **続行**] をクリックします。

4. 評価が設定されると、進行状況ダイアログが表示されます。 セットアップが完了したら、[完了] をクリック **します**。

## <a name="reporting-in-audit-mode"></a>監査モードでのレポート

- [脅威の保護状態レポート](view-email-security-reports.md#threat-protection-status-report)には、次のビューにDefender for Office 365による検出が表示されます。
  - [Email マルウェアとグラフの内訳を\>検出テクノロジ別に表示する](view-email-security-reports.md#view-data-by-email--malware-and-chart-breakdown-by-detection-technology)
  - [Emailフィッシングとグラフの内訳を\>検出テクノロジ別に表示する](view-email-security-reports.md#view-data-by-email--phish-and-chart-breakdown-by-detection-technology)

- [脅威エクスプローラーでは](threat-explorer.md)、Defender for Office 365評価によって検出されたメッセージに、エントリの詳細に次のバナーが表示されます。

  ![Defender for Office 365評価で悪意のある電子メール メッセージが検出されたことを示すメッセージの通知バナー。](../../media/evalv2-detection-banner.png)

<!--- This stuff is likely not applicable for V2 reporting --->

**Microsoft Defender for Office 365評価** ページには<https://security.microsoft.com/atpEvaluation>、評価のポリシーのレポートが統合されます。

- フィッシング対策ポリシーにおける、なりすまし保護
- 安全なリンク
- 安全な添付ファイル

既定では、グラフには過去 30 日間のデータが表示されますが、[予定表] アイコンをクリック ![して日付範囲をフィルター処理できます。](../../media/m365-cc-sc-add-internal-icon.png) **30 日間、30 日** 未満の次の追加の値から選択します。

- 24 時間
- 7 日間
- 14 日
- カスタム日付範囲

[ダウンロード] アイコンをクリック ![できます。](../../media/m365-cc-sc-download-icon.png) グラフ データを.csv ファイルに **ダウンロードしてダウンロード** します。

## <a name="required-permissions"></a>必要なアクセス許可

**Azure AD** で Defender for Microsoft 365 の評価を設定するために必要なアクセス許可については、次の一覧で説明します。

- **評価の作成、変更、または削除:** セキュリティ管理者またはグローバル管理者。
- **評価ポリシーとレポートを表示する**: セキュリティ管理者またはセキュリティ 閲覧者。

Microsoft 365 Defender ポータルでの Azure AD のアクセス許可の詳細については、Microsoft 365 Defender [ポータルの Azure AD ロールに関するページを](permissions-microsoft-365-security-center.md#azure-ad-roles-in-the-microsoft-365-defender-portal)参照してください。

## <a name="evaluation-policy-settings"></a>評価ポリシーの設定

評価用に特別に作成されるDefender for Office 365の設定については、次の表で説明します。

**フィッシング対策評価ポリシーの設定**:

|設定|値|
|---|---|
|AdminDisplayName|評価ポリシー|
|AuthenticationFailAction|MoveToJmf|
|Enabled|はい|
|EnableFirstContactSafetyTips|不正解|
|EnableMailboxIntelligence|はい|
|EnableMailboxIntelligenceProtection|はい|
|EnableOrganizationDomainsProtection|不正解|
|EnableSimilarDomainsSafetyTips|不正解|
|EnableSimilarUsersSafetyTips|不正解|
|EnableSpoofIntelligence|はい|
|EnableSuspiciousSafetyTip|不正解|
|EnableTargetedDomainsProtection|不正解|
|EnableTargetedUserProtection|不正解|
|EnableUnauthenticatedSender|はい|
|EnableUnusualCharactersSafetyTips|不正解|
|EnableViaTag|はい|
|Guid|GUID 値|
|ImpersonationProtectionState|Manual|
|IsDefault|不正解|
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
|EnableAuthenticationSafetyTip|不正解|
|EnableAuthenticationSoftPassSafetyTip|不正解|
|PolicyTag|空白|
|SimilarUsersSafetyTipsCustomText|空白|
|TreatSoftPassAsAuthenticated|はい|
|UnusualCharactersSafetyTipsCustomText|空白|
|||
|ExcludedDomains|{}|
|ExcludedSenders|{}|
|TargetedDomainsToProtect|{}|
|TargetedUsersToProtect|{}|

**安全な添付ファイルの評価ポリシー設定**:

|設定|値|
|---|---|
|アクション|許可|
|ActionOnError|はい|
|AdminDisplayName|評価ポリシー|
|ConfidenceLevelThreshold|80|
|有効にする|はい|
|EnableOrganizationBranding|不正解|
|Guid|GUID 値|
|IsBuiltInProtection|不正解|
|IsDefault|不正解|
|名前|評価ポリシー|
|OperationMode|Delay|
|QuarantineTag|AdminOnlyAccessPolicy|
|RecommendedPolicyType|評価|
|Redirect|不正解|
|RedirectAddress|{}|
|ScanTimeout|30|

**セーフ リンク評価ポリシーの設定**:

|設定|値|
|---|---|
|AdminDisplayName|評価ポリシー|
|AllowClickThrough|不正解|
|CustomNotificationText|空白|
|DeliverMessageAfterScan|はい|
|DisableUrlRewrite|はい|
|DoNotRewriteUrls|{}|
|EnableForInternalSenders|不正解|
|EnableOrganizationBranding|不正解|
|EnableSafeLinksForTeams|はい|
|Guid|GUID 値|
|IsBuiltInProtection|不正解|
|IsDefault|不正解|
|IsEnabled|はい|
|LocalizedNotificationTextList|{}|
|名前|"EvaluationPolicy"|
|RecommendedPolicyType|評価|
|ScanUrls|はい|
|TrackClicks|はい|
|||
|DoNotAllowClickThrough|空白|
|DoNotTrackUserClicks|不正解|
|EnableSafeLinksForEmail|はい|
|EnableSafeLinksForOffice|はい|
|ExcludedUrls|{}|
|WhiteListedUrls|空白|
