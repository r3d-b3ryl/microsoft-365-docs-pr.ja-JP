---
title: Microsoft 365 Lighthouseの新機能
f1.keywords: CSH
ms.author: sharik
author: SKjerland
manager: scotv
ms-reviewer: crimora
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: Microsoft 365 Lighthouseを使用するマネージド サービス プロバイダー (MSP) の場合は、毎月Microsoft 365 Lighthouseで追加、変更、および修正された内容を確認します。
ms.openlocfilehash: d7538cf55feaf4adc6d0d741f21b13c4a9e19b80
ms.sourcegitcommit: 7e551fa4e9b8b25ed62b5f406143b6b1dae08cbf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2022
ms.locfileid: "67106451"
---
# <a name="whats-new-in-microsoft-365-lighthouse"></a>Microsoft 365 Lighthouseの新機能

Microsoft 365 Lighthouse[に新機能](m365-lighthouse-overview.md)を継続的に追加し、学習した問題を修正し、フィードバックに基づいて変更を加えています。 この記事を確認して、取り組んでいることを確認してください。

> [!NOTE]
> 一部の機能は、お客様に対して異なる速度でロールアウトされます。 まだ機能が表示されていない場合は、すぐに表示されます。

## <a name="july-2022"></a>2022 年 7 月

### <a name="enhanced-baseline-deployment"></a>強化されたベースラインデプロイ

Microsoft 365 Lighthouse、次の方法で、すべてのマネージド テナントへのベースラインのデプロイを迅速かつ簡単にできるようになりました。

- 割り当てられた各タスクの状態を自動的に検出して報告する
- 状態レポートを統合し、デプロイの状態を決定するロジックを簡略化する
- どのタスクが完了し、どのタスクに注意が必要かを報告する
- 該当するタスクのユーザー レベルの展開状態を報告する
- テナント内から既存の構成を検出し、それらをベースラインと比較する
- 無視されたタスクに関する詳細を指定する
- 割り当てられたタスクを完了するために追加のライセンスが必要な場所を特定する

## <a name="june-2022"></a>2022 年 6 月

### <a name="support-for-microsoft-365-e5-customers"></a>Microsoft 365 E5のお客様のサポート

オンボーディング要件を変更し、Microsoft 365 E5顧客をMicrosoft 365 Lighthouseにオンボードできるようにしました。 オンボードにサポートMicrosoft 365 Lighthouseライセンスの拡張リストには、Microsoft 365 Business Premium、Microsoft 365 E3、Microsoft 365 E5、ビジネス向けのMicrosoft Defender for BusinessとWindows 365。 これらのライセンスのいずれかを少なくとも 1 つ持ち、委任されたアクセス許可の要件を満たしており、ライセンスされたユーザーの最大数を超えないお客様は、Microsoft 365 Lighthouseで管理できます。  

要件の完全な一覧については、「[Microsoft 365 Lighthouseの要件」を](m365-lighthouse-requirements.md)参照してください。

### <a name="microsoft-defender-for-business-integration"></a>Microsoft Defender for Business統合

Microsoft 365 LighthouseがMicrosoft Defender for Businessと統合され、Microsoft Defender for Businessを持つすべての顧客テナントに関連する分析情報と管理機能が提供されるようになりました。 Microsoft Defender for Businessにオンボードされた顧客デバイスの一覧を表示するには、Microsoft 365 Lighthouseの左側のナビゲーション ウィンドウで [**デバイス**] を選択します。 顧客テナント全体でフラグが設定されたインシデントとアラートの一覧を表示するには、[ **デバイス** > **デバイス セキュリティ**] に移動し、[ **インシデントとアラート** ] タブを選択します。  

また、顧客テナントのMicrosoft Defender for Businessを設定するのに役立つ手順を既定のベースラインに追加しました。 この手順を表示するには、Microsoft 365 Lighthouseの左側のナビゲーション ウィンドウで **[基準計画**] を選択するか、いずれかの顧客テナントの展開計画を表示します。

### <a name="status-of-quarantined-email-messages"></a>検疫された電子メール メッセージの状態

マネージド テナントの電子メール検疫データに関する新機能が追加されました。 この機能は、Microsoft 365 Lighthouseの左側のナビゲーション ウィンドウで **[データ保護**] を選択してアクセスできるため、顧客テナント全体で検疫された電子メール メッセージの状態を確認できます。 操作が必要なテナントに優先順位を付ける際に役立つ、検疫量の合計と各マネージド テナントの詳細情報の統合情報を確認できます。

### <a name="increase-in-maximum-license-limit"></a>ライセンスの上限の引き上げ

お客様のオンボードの最大ライセンス制限をもう一度引き上げることで、Microsoft 365 Lighthouseの顧客の数を増やすことができます。 最大 2,500 のユーザー ライセンスをお持ちのお客様は、Microsoft 365 Lighthouseにオンボードできるようになりました。 今後のMicrosoft 365 Lighthouseリリースでは、この要件を引き続き評価します。 

詳細については、「[Microsoft 365 Lighthouseの要件」を](m365-lighthouse-requirements.md)参照してください。

## <a name="may-2022"></a>2022 年 5 月

### <a name="redesigned-left-navigation-pane"></a>再設計された左側のナビゲーション ウィンドウ

新しい外観Microsoft 365 Lighthouse左側のナビゲーション ウィンドウが表示されました。 テナント、ユーザー、デバイスなどの最上位ノードが展開され、危険なユーザー、デバイスコンプライアンス、脅威管理などの関連サブノードが表示される、洗練されたデザインに気付きます。 このナビゲーション モデルは、他の Microsoft 365 管理センターで使用されるモデルと一致します。

### <a name="enriched-user-details-pane"></a>エンリッチされたユーザーの詳細ウィンドウ

ユーザーの詳細ウィンドウを再設計し、より多くのユーザー情報と、ユーザーをより適切に管理するために実行できるより多くのアクションを含めます。 これで、Microsoft 365 管理センターのユーザーの詳細ウィンドウと同じ外観になりました。 Microsoft 365 Lighthouseのユーザーの詳細ウィンドウにアクセスするには、左側のナビゲーション ウィンドウで **[ユーザー**] を選択し、[ユーザーの **検索**] または [**危険なユーザー**] を選択します。 任意のユーザーを選択して詳細ウィンドウを開きます。

## <a name="april-2022"></a>2022 年 4 月

### <a name="delegated-access-type-and-roles-on-tenants-page"></a>[テナント] ページの委任されたアクセスの種類とロール

テナント **ページが** 更新され、マネージド サービス プロバイダー (MSP) の委任されたアクセスの種類 (None、DAP、GDAP、または両方の DAP & GDAP) が、お客様ごとに **[委任されたアクセス** ] 列に一覧表示されました。 また、サインインしているユーザーの顧客ごとの DAP ロールと GDAP ロールを一覧表示する [ **ロール** ] というタイトルの新しい列も追加されました。 テナント **ページに** 対するこれら 2 つの機能強化により、パートナー技術者は、各顧客で使用できる委任された管理アクセス許可の種類と、どの委任されたロールが明示的に付与されているかを理解しやすくなります。

詳細については、「[Microsoft 365 Lighthouseのアクセス許可の概要](m365-lighthouse-overview-of-permissions.md)」を参照してください。

## <a name="march-2022"></a>2022 年 3 月

### <a name="windows-365-business-integration-and-management-actions"></a>Windows 365 Business統合アクションと管理アクション

ユーザーからのフィードバックに基づいて、Windows 365 BusinessをMicrosoft 365 Lighthouseに統合しました。 この統合により、すべての顧客のクラウド PC を 1 つの場所から管理および監視できます。 

Microsoft 365 LighthouseでWindows 365 Businessクラウド PC と統合するだけでなく、次の管理アクションを実行できるようになりました。

- Restart
- 再プロビジョニング
- 名前の変更
 
新機能の詳細については、[Microsoft 365 LighthouseのWindows 365 (クラウド PC) ページの概要に](m365-lighthouse-win365-page-overview.md)関するページを参照してください。

### <a name="microsoft-365-lighthouse-partner-amendment"></a>Microsoft 365 Lighthouse パートナーの修正

Microsoft 365 Lighthouseが一般公開されたので、現在のパートナーは更新されたMicrosoft 365 Lighthouseパートナーの修正に署名する必要があります。 プレビュー期間中にサインアップしたすべてのMicrosoft 365 Lighthouseパートナーは、今後数週間でこの新しい契約を完了するよう求められます。 完了にはパートナー テナントのグローバル管理者権限が必要であり、Microsoft 365 Lighthouse ポータルに引き続きアクセスするには 90 日以内に完了する必要があります。

## <a name="february-2022"></a>2022 年 2 月

### <a name="granular-delegated-access-permissions-gdap-roles"></a>詳細な委任アクセス許可 (GDAP) ロール

Microsoft 365 Lighthouse、MSP が詳細委任された管理特権 (GDAP) ロールを使用する機能が含まれるようになりました。 最新の更新プログラムにより、MSP は、Microsoft 365 Lighthouseでの最小限の特権アクセスの原則を有効にする技術者に対して GDAP ロールを活用できます。 この機能により、各技術者が操作できる顧客のデータと設定を細かく制御できるため、管理 エージェントの委任アクセス許可 (DAP) ロールの広範なアクセス許可に固有のリスクが軽減されます。

Microsoft 365 Lighthouseの GDAP の詳細については、「[ポータル セキュリティMicrosoft 365 Lighthouse構成する](m365-lighthouse-configure-portal-security.md)」を参照してください。

### <a name="capability-to-notify-users-to-act-on-noncompliant-devices"></a>非準拠デバイスで動作するようにユーザーに通知する機能

デバイスコンプライアンスベースラインステップの一環として、顧客テナント内のユーザーに非準拠デバイスで動作するように通知する機能を追加しました。 この変更により、顧客テナントにデバイス コンプライアンスの展開手順を適用すると、そのテナントで作成されたデバイス コンプライアンス ポリシーは、デバイスが非準拠になったときに自動的に通知を送信し、デバイスをコンプライアンスに戻すための適切なアクションを実行するように通知します。

### <a name="deployment-validation-and-reporting"></a>デプロイの検証とレポート

Microsoft 365 Lighthouse、条件付きアクセス ポリシーを使用して、展開手順のテナント構成をテストできるようになりました。  

この新機能は、管理する顧客テナント内の既存のポリシーを検出し、展開計画と比較します。 Microsoft 365 Lighthouseは、デプロイ 手順と展開手順プロセスの状態指定を提供し、どの展開プロセスが既に完了しているか、どのプロセスに対処する必要があるか、展開計画で規定されている設定が、既存のポリシーに含まれる設定と等しいか、不足しているか、競合しているかについて理解するのに役立ちます。 この情報を知ることで、ポリシーの競合の特定、優先順位付け、解決が迅速かつ簡単になり、より効果的になります。

### <a name="deployment-step-to-configure-microsoft-defender-firewall"></a>Microsoft Defender ファイアウォールを構成するための展開手順

Microsoft 365 Lighthouseは、既定のベースラインに Microsoft Defender ファイアウォールの展開の構成手順を追加しました。 この手順は、MSP がWindows 10 (以降) デバイスの既定のファイアウォール構成を使用して顧客テナント デバイスをセキュリティで保護するのに役立ちます。 Microsoft Defender Firewall は、顧客のテナント デバイスに出入りする未承認のネットワーク トラフィックをブロックし、ネットワーク セキュリティの脅威のリスクを軽減します。 Microsoft Defender ファイアウォール規則機能は現在開発中です。

Microsoft Defender Firewall は、Windows 10 (以降) デバイスで既定で有効になっています。 顧客テナントにこの構成がない場合は、次の手順に従います。

1. Microsoft 365 Lighthouseの **[テナント**] ページで、顧客テナントを選択してテナントの **[概要]** ページを開きます。
2. [ **展開計画]** タブを選択します。
3. 展開手順の一覧から、[ **Microsoft Defender ファイアウォールの構成**] を選択します。
4. [ **確認とデプロイ** ] を選択して、この構成を顧客テナントにデプロイします。 

### <a name="increase-in-maximum-license-limit"></a>ライセンスの上限の引き上げ

お客様のオンボーディングの最大ライセンス制限を引き上げることで、Microsoft 365 Lighthouseでより多くの顧客を管理できるようにしています。 最大 1,000 個のユーザー ライセンスをお持ちのお客様は、Microsoft 365 Lighthouseにオンボードできるようになりました。 今後のMicrosoft 365 Lighthouseリリースでは、この要件を引き続き評価します。

詳細については、「[Microsoft 365 Lighthouseの要件」を](m365-lighthouse-requirements.md)参照してください。

### <a name="support-for-advisor-customers"></a>アドバイザーのお客様のサポート

アドバイザーリレーションシップを持つ既存の顧客テナントをMicrosoft 365 Lighthouseにオンボードできるように、オンボード要件を変更しました。 代理アクセス許可の要件を満たし、必要なライセンスを持ち、最大ユーザー数を超えない場合、リセラーとアドバイザーの両方の契約をお持ちのお客様は、Microsoft 365 Lighthouseに参加できます。

詳細については、「[Microsoft 365 Lighthouseの要件」を](m365-lighthouse-requirements.md)参照してください。

## <a name="january-2022"></a>2022 年 1 月

### <a name="capability-to-view-audit-logs-in-microsoft-365-lighthouse"></a>Microsoft 365 Lighthouseで監査ログを表示する機能

Microsoft 365 Lighthouse監査ログを表示する機能が含まれるようになりました。 過去のアクションを確認して、修復、プロセスとセキュリティの調査をサポートし、従業員をトレーニングし、コンプライアンスと監査の要件を満たすための不適切な構成と危険なアクションを見つけることができます。 最新の更新プログラムを使用すると、次のことができます。

- 監査ログを表示して、顧客テナントの変更、変更日時、変更者など、Microsoft 365 Lighthouse内で実行されたすべてのアクションを確認します。
- 監査ログを検索してフィルター処理して、特定の情報を検索します。
- ログを分析して保持できるようにログをエクスポートします。
 
Microsoft 365 Lighthouseの左側のナビゲーション ウィンドウで、[**監査ログ**] を選択します。 または、 [監査ログ ページに直接移動](https://lighthouse.microsoft.com/#blade/Microsoft_Intune_MTM/Audit.ReactView) して確認します。

## <a name="november-2021"></a>2021 年 11 月

### <a name="microsoft-365-services-usage-data"></a>Microsoft 365 サービスの使用状況データ

これで、Microsoft 365 Lighthouse内から Microsoft 365 サービスの使用状況データを表示できるようになりました。 お客様が Microsoft 365 サービスをどのように使用しているかを理解することは、IT 投資を最大限に活用するうえで非常に重要です。 複数のリソースを使用して、顧客のさまざまな生産性、セキュリティ、コンプライアンス サービス全体の情報を表示する代わりに、それらを 1 つのシンプルで強力なビューに集約Microsoft 365 Lighthouse。  

これらの分析情報は、ユーザーが積極的に使用するサービスと、セキュリティや生産性を向上させる機会がある可能性がある場所を理解できるように支援することで、顧客のエンゲージメントを通知し、顧客により多くの価値を提供するのに役立ちます。 

詳細については、「[Microsoft 365 Lighthouse: Microsoft 365 サービスの使用状況」セクションの「テナントの概要」ページを参照](m365-lighthouse-tenants-page-overview.md#microsoft-365-services-usage-section)してください。

### <a name="exchange-online-protection-and-microsoft-365-defender-for-office-365-default-baseline-step"></a>既定のベースライン ステップのExchange Online ProtectionとMicrosoft 365 Defender Office 365

既定のベースラインに新しい手順を追加し、Exchange Online Protection (EOP) と Microsoft Defender for Office 365 (MDO) のセキュリティ ポリシーを有効にするためのガイダンスを含めます。 EOP と MDO は、ユーザーの検疫または迷惑メール フォルダー (近日公開予定) に電子メールを送信することで、スパム、フィッシング、マルウェアのメールからユーザーを保護するのに役立ちます。 展開計画では、EOP と MDO の設定について説明し、次の顧客テナント展開計画のレビューでセキュリティに関する考え方をさらに拡張します。

### <a name="default-tenant-tags"></a>既定のテナント タグ

[**テナント**] ページの [**タグの管理**] ウィンドウから *、既定* で特定のテナント タグを指定できるようになりました。そのため、次回Microsoft 365 Lighthouseにサインインすると、既定ですべてのビューと分析情報がフィルター処理され、既定のタグを持つテナントのみが表示されます。 既定のタグは、優先度の高い顧客テナントの分析情報に焦点を当てるのに役立ちます。

## <a name="october-2021"></a>2021 年 10 月

### <a name="capability-to-filter-by-multiple-tenant-tags"></a>複数のテナント タグでフィルター処理する機能

複数のテナント タグで同時にデータをフィルター処理できるようになりました。 この機能は、関連する顧客テナントを表示するためにMicrosoft 365 Lighthouseで使用できる既存のビューと分析情報をより簡単にフィルター処理するのに役立ちます。

### <a name="capability-to-assign-baseline-configurations-to-specific-azure-active-directory-groups"></a>特定の Azure Active Directory グループにベースライン構成を割り当てる機能

Microsoft 365 Lighthouse内から顧客テナントの特定の Azure Active Directory (Azure AD) グループにベースライン構成を割り当てる機能を追加しました。 任意のデプロイ 手順ページで、含めるまたは除外する特定の Azure AD グループを参照して選択し、その構成をカスタマー テナントにデプロイします。

### <a name="improvements-to-risky-users-page"></a>[危険なユーザーの機能強化] ページ

Microsoft 365 Lighthouse内からユーザーのリスクの理由を簡単に表示して理解できるようになりました。 Microsoft 365 Lighthouseの左側のナビゲーション ウィンドウで、[**ユーザー**] を選択し、[**危険なユーザー**] タブを選択します。任意のユーザーの [**詳細**] 列の **[リスク検出の表示**] を選択します。 ここから、リスクの詳細を確認し、[ **ユーザーの侵害の確認** ] または [ **ユーザー リスクの却下]** を選択できます。 [危険なユーザー] ページから、同時に複数のユーザーの **リスク** を確認または却下することもできます。 ユーザーのリスクを無視する機能は、パスワード リセットがオプションではない場合や、影響を受けるユーザーが危険にさらされなくなったと思われる場合に役立ちます。

### <a name="capability-to-provide-feedback-on-microsoft-365-lighthouse"></a>Microsoft 365 Lighthouseに関するフィードバックを提供する機能

お客様のフィードバックは重要であり、重要であるため、フィードバックの提供を求める新しいフィードバック機能が追加されました。この機能は、(月に 1 回を超えない) 場合があります。 Microsoft 365 Lighthouseの右上隅にあるフィードバック アイコンを選択して、いつでもフィードバックを提供することもできます。

## <a name="september-2021"></a>2021 年 9 月

### <a name="tenant-filter-changes"></a>テナント フィルターの変更

Microsoft 365 Lighthouse内の任意のページからテナントとタグをすばやく表示および管理できるように、テナント フィルター 処理エクスペリエンスにいくつかの変更を加えています。 任意のページの上部にある **[テナント** ] フィルターを選択し、フィルター処理するテナントまたはタグ名を参照または入力します。

## <a name="august-2021"></a>2021 年 8 月

### <a name="in-product-email-workflows-to-communicate-with-users"></a>ユーザーと通信するための製品内電子メール ワークフロー 

お客様のテナント内のユーザーと、実行する必要があるアクションについて簡単に通信できるようになりました。 多要素認証 (MFA) またはセルフサービス パスワード リセットに登録されていないユーザーの一覧から、1 人以上のユーザーを選択し、ダウンロード可能な電子メール テンプレートを使用して電子メール メッセージを送信できるようになりました。

### <a name="capability-to-take-action-on-noncompliant-devices"></a>非準拠デバイスでアクションを実行する機能

複数の顧客テナント間で 1 つ以上のデバイスを同期または再起動する機能が導入されました。 この機能は、顧客のデバイスがリスクから保護されるようにするのに役立ちます。 この機能を確認するには、Microsoft 365 Lighthouseの左側のナビゲーション ウィンドウで [**デバイス**] を選択し、[**デバイス**] タブを選択します。デバイスの一覧の上にある **[同期** と **再起動]** オプションを探します。 これらのオプションには、任意のデバイスのデバイスの詳細ウィンドウからアクセスすることもできます。

### <a name="capability-to-monitor-and-manage-windows-365-cloud-pcs"></a>Windows 365クラウド PC を監視および管理する機能

オンプレミス接続を監視し、すべての顧客テナントでクラウド PC Windows 365プロビジョニングおよび管理する機能が追加されました。 新しい **Windows 365** ページには、テナントのすべてのクラウド PC に関する詳細情報が 1 つの便利な場所に表示されます。 

### <a name="support-for-microsoft-365-e3-customers"></a>Microsoft 365 E3のお客様のサポート

お客様がMicrosoft 365 Lighthouseに顧客をオンボードできるように、オンボーディング要件Microsoft 365 E3変更しました。 Microsoft 365 Lighthouseで管理される資格を得るには、各顧客が次の要件を満たしている必要があります。

- MSP が顧客テナントを管理できるように、委任されたアクセスを設定している必要があります
- 少なくとも 1 つのMicrosoft 365 Business PremiumまたはMicrosoft 365 E3 ライセンスが必要です
- ライセンスを持つユーザーが 500 人以下である必要があります

要件の詳細については、「[Microsoft 365 Lighthouseの要件」を](m365-lighthouse-requirements.md)参照してください。

## <a name="june-2021"></a>2021 年 6 月

### <a name="capability-to-add-custom-tags-to-customer-tenants"></a>顧客テナントにカスタム タグを追加する機能

これで、Microsoft 365 Lighthouseで管理する顧客テナントにカスタム タグを作成して適用できるようになりました。 これらのタグを使用してテナントを整理したり、テナント一覧をフィルター処理して、関連する顧客テナント のセットの分析情報を表示したりするのに役立ちます。 

### <a name="baselines-to-standardize-your-customer-tenant-deployments"></a>顧客テナントのデプロイを標準化するためのベースライン

新しいベースライン機能を使用すると、標準構成をデプロイして、顧客テナント内のユーザー、デバイス、データをセキュリティで保護できるようになりました。 既定のベースラインには、現在、次のデプロイ手順が含まれています (近日公開予定)。 

- 管理者に MFA を要求する 
- ユーザーに MFA を要求する 
- レガシ認証をブロックする 
- Microsoft エンドポイント マネージャーに Windows デバイスを登録する – Azure AD Join 
- Windows デバイス用の Defender AV ポリシーを構成する 
- Windows デバイスのコンプライアンス ポリシーを構成する 

これらの展開手順を実行するには、Microsoft 365 Lighthouse の左側のナビゲーション ウィンドウで [ **テナント** ] を選択し、テナントの一覧からテナントを選択してから、[ **展開計画** ] タブを選択します。 

## <a name="may-2021"></a>2021 年 5 月

### <a name="enhancements-to-tenants-page"></a>[テナントの機能強化] ページ

テナント ページに対して次の機能強化 **が** 行われました。

- 問題別の合計数の一覧をページの上部に追加しました 
- テナントの一覧の **[状態]** 列の状態にマウス ポインターを合わせて制限の詳細を表示する機能を提供しました 
- 状態ラベルを改善しました