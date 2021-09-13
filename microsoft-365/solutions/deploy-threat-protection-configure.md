---
title: 脅威保護機能を全体にわたって構成するMicrosoft 365
description: この記事は、脅威保護ソリューションを実装するためのガイドとして使用します。 脅威保護サービスと機能をすべてのユーザーに展開Microsoft 365 E5。
keywords: セキュリティ ソリューション, セットアップ, 構成, Microsoft 365 E5, 高度な脅威保護, Defender
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: m365-security
ms.technology: m365d
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-threatprotection
- m365solution-scenario
ms.custom: ''
f1.keywords: NOCSH
ms.openlocfilehash: a372ae3b15b35c03449973fba2b1181a8ed68ac2
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59177312"
---
# <a name="configure-threat-protection-capabilities-across-microsoft-365"></a>脅威保護機能を全体にわたって構成Microsoft 365

次の手順に従って、脅威の保護を構成Microsoft 365。

## <a name="step-1-set-up-multi-factor-authentication-and-conditional-access-policies"></a>手順 1: 多要素認証と条件付きアクセス ポリシーを設定する

[多要素認証](/azure/active-directory/authentication/concept-mfa-howitworks) (MFA) では、ユーザーが電話または認証アプリで ID を確認する必要があります。 [条件付きアクセス ポリシーは、](/azure/active-directory/conditional-access/overview)ユーザーがアプリやデータにアクセスするために満たす必要がある特定の要件を定義Microsoft 365。 MFA ポリシーと条件付きアクセス ポリシーは、組織を保護するために一緒に機能します。 たとえば、MFA が有効になっていないアカウントを使用してモバイル デバイスからサインインしようとすると、条件付きアクセス ポリシーで MFA を有効にする必要がある場合、そのユーザーはサインインできません。  

Microsoft は、すべての SaaS アプリケーションへのアクセスを保護するための条件付きアクセスと関連するポリシーの特定のセットをテストし、推奨Microsoft 365。 ポリシーは、ベースライン保護、機密性の高い保護、および高度に規制された保護に推奨されます。 まず、ベースライン保護のポリシーを実装します。

[ ![ ID とデバイス アクセスを構成するための一般的なポリシー。](../media/microsoft-365-policies-configurations/identity-device-access-policies-byplan.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-device-access-policies-byplan.png) 
[このイメージのより大きなバージョンを表示する](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-device-access-policies-byplan.png)

### <a name="to-implement-baseline-protection-for-microsoft-365"></a>ユーザーのベースライン保護を実装Microsoft 365

![ベースライン保護を展開するプロセス。](../media/deploy-threat-protection/deploy-threat-protection-identity-access-steps.png) 

1. [Azure id Protection を含む前提条件AD構成します](../security/office-365-security/identity-access-prerequisites.md)。
2. [ベースライン保護用に共通の ID および](../security/office-365-security/identity-access-policies.md) デバイス アクセス ポリシーを構成します。
3. ゲスト ユーザー、ゲスト[ユーザー、Microsoft Teams、Exchange Online、](../security/office-365-security/identity-access-policies-guest-access.md)および SharePoint[](../security/office-365-security/teams-access-policies.md)のポリシー[を構成](../security/office-365-security/sharepoint-file-access-policies.md)OneDrive。 [](../security/office-365-security/secure-email-recommended-policies.md)

### <a name="more-information-about-protecting-identities"></a>ID の保護の詳細

- [ID とデバイスのアクセス構成](../security/office-365-security/microsoft-365-policies-configurations.md)
- [Azure MFA のセキュリティ ガイダンス](/azure/active-directory/authentication/multi-factor-authentication-security-best-practices)

## <a name="step-2-configure-microsoft-defender-for-identity"></a>手順 2: Microsoft Defender for Identity を構成する

[Microsoft Defender for Identity](/defender-for-identity/what-is) は、オンプレミスの Active Directory ドメイン サービス (AD DS) 信号と一緒に動作するクラウドベースのセキュリティ ソリューションで、高度な脅威、侵害された ID、組織に向けられた悪意のあるインサイダーアクションを特定、検出、および調査します。

Microsoft Defender for Identity を使用すると、ハイブリッド環境での高度な攻撃の検出に苦労しているセキュリティ操作 (SecOps) アナリストやセキュリティ 専門家は、次の作業を行えます。

- 学習ベースの分析を使用して、ユーザー、エンティティの動作、アクティビティを監視します。
- Active Directory に保存されているユーザーの ID と認証情報の保護。
- キル チェーン全体で疑わしいユーザー アクティビティや高度な攻撃を特定し、調査する。
- 迅速なトリアージのために、簡潔なタイムラインで示された明確なインシデント情報を提供する。

### <a name="to-set-up-microsoft-defender-for-identity"></a>Microsoft Defender for Identity をセットアップするには

![Microsoft Defender for Identity を展開するプロセス。](../media/deploy-threat-protection/deploy-azure-atp-steps.png) 

1. [プライマリ環境を保護するために Microsoft Defender for Identity](/azure-advanced-threat-protection/install-atp-step1) をセットアップします。
2. すべてのドメイン コントローラー[とフォレストを](/azure-advanced-threat-protection/atp-sensor-monitoring)[保護します](/azure-advanced-threat-protection/atp-multi-forest)。
3. [Microsoft Defender for Identity アラートをセキュリティ](/azure-advanced-threat-protection/suspicious-activity-guide?tabs=external)操作 (SecOps) ワークフローに統合します。

### <a name="more-information-about-microsoft-defender-for-identity"></a>Microsoft Defender for Identity の詳細

- [Microsoft Defender for Identity とは?](/azure-advanced-threat-protection/what-is-atp)
- [ビデオ: Id 用 Microsoft Defender の概要](https://www.youtube.com/watch?reload=9&v=EGY2m8yU_KE)
- [Microsoft Defender for Identity の展開](/azure-advanced-threat-protection/what-is-atp#whats-next)

## <a name="step-3-turn-on-microsoft-365-defender"></a>手順 3: デバイスを有効Microsoft 365 Defender

[Microsoft 365 Defender](../security/defender/microsoft-365-defender.md)を組み合わせ、機能を 1 つのソリューションに調整します。 統合されたMicrosoft 365 Defenderソリューションを使用すると、セキュリティ専門家は、これらの各製品が受け取る脅威信号を一緒にまとめ、脅威の全範囲と影響を特定できます。環境に入った方法、影響を受けるもの、組織に現在どのように影響を与えています。 Microsoft 365 Defender攻撃を防止または停止し、影響を受けるメールボックス、エンドポイント、およびユーザー ID を自己回復する自動アクションを実行します。

Microsoft 365 Defenderは、アラート、インシデント、自動調査と応答、およびワークロード全体の高度な検出 (Microsoft Defender for Identity、Office 365、Microsoft Defender for Endpoint、および Microsoft Cloud App Security) を単一のウィンドウに統合します。 新しい機能は、ユーザーに継続的にMicrosoft 365 Defender。プレビュー機能の受信をオプトインすることを検討してください。

### <a name="to-set-up-microsoft-365-defender"></a>ファイルを設定Microsoft 365 Defender

![サーバーを展開するMicrosoft 365 Defender。](../media/deploy-threat-protection/deploy-mtp-steps.png) 

1. [前提条件を確認します](../security/defender/prerequisites.md)。
2. [[設定] をオンMicrosoft 365 Defender。](../security/defender/m365d-enable.md)
3. [プレビュー機能をオプトインします](../security/defender/preview.md)。

### <a name="more-information-about-microsoft-365-defender"></a>詳細については、Microsoft 365 Defender

- [Microsoft 365 Defender とは](../security/defender/microsoft-365-defender.md)
- [Microsoft 365 Defender の新機能](../security/defender/whats-new.md)

## <a name="step-4-configure-microsoft-defender-for-office-365"></a>手順 4: Microsoft Defender for Office 365

[Microsoft Defender for Office 365](../security/office-365-security/defender-for-office-365.md)メール メッセージ (添付ファイルと URL)、ドキュメント、およびコラボレーション ツールの悪意のあるOffice組織を保護します。 次の表に、Microsoft Defender Office 365に含まれている機能の一覧を示Microsoft 365 E5。

<br>

****

|構成、保護、および検出機能|自動化、調査、修復、および教育機能|
|---|---|
|[添付ファイル保護](../security/office-365-security/safe-attachments.md) <p> [リンク保護](../security/office-365-security/safe-links.md) <p> [安全なドキュメント](../security/office-365-security/safe-docs.md) <p> [SharePoint、OneDrive、Microsoft Teams 用の安全な添付ファイル](../security/office-365-security/mdo-for-spo-odb-and-teams.md) <p> [アプリ内のフィッシング対策Microsoft 365](../security/office-365-security/anti-phishing-protection.md)|[脅威トラッカー](../security/office-365-security/threat-trackers.md) <p> [脅威エクスプローラー](../security/office-365-security/threat-explorer.md) <p> [自動調査および対応](../security/office-365-security/office-365-air.md) <p> [攻撃シミュレーション トレーニング](../security/office-365-security/attack-simulation-training.md)|
|

Microsoft Defender for Office 365を使用すると、組織全体のユーザーは、電子メール コンテンツとドキュメントに対する脅威の保護を利用して、より安全にコミュニケーションとOfficeできます。

### <a name="to-set-up-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365

![Microsoft Defender for Office 365。](../media/deploy-threat-protection/deploy-office365-atp-steps.png) 

1. [Microsoft Defender のポリシーを設定および構成Office 365します](../security/office-365-security/protect-against-threats.md)。
2. [Microsoft Defender を表示して使用して、レポートOffice 365します](../security/office-365-security/view-reports-for-mdo.md)。
3. [脅威の調査と対応機能を使用します](../security/office-365-security/office-365-ti.md)。

### <a name="more-information-about-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365

- [Microsoft Defender for Office 365概要](../security/office-365-security/defender-for-office-365.md)
- [Microsoft Defender for Office 365 の新機能](../security/office-365-security/whats-new-in-defender-for-office-365.md)

## <a name="step-5-configure-microsoft-defender-for-endpoint"></a>手順 5: エンドポイント用の Microsoft Defender を構成する

[Microsoft Defender for Endpoint](/windows/security/threat-protection) は、組織のデバイス (エンドポイントとも呼ばれます) をサイバー脅威、高度な攻撃、およびデータ侵害から保護します。 セキュリティ チームは、エンドポイントのセキュリティを管理する方が効率的です。 堅牢なツールは、脅威と脆弱性の管理を使用して脆弱性検出を使用して、組織がパッチされていないシステムに対応 [するのに役立ちます](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)。 攻撃表面の縮小、次世代保護、エンドポイントの[](/windows/security/threat-protection/microsoft-defender-atp/overview-attack-surface-reduction)検出と応答、[](/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10)自動調査と修復などの[](/windows/security/threat-protection/microsoft-defender-atp/overview-endpoint-detection-response)自動検出および修復機能は、デバイスをマルウェアから安全に保つのに役立ちます。 [](/windows/security/threat-protection/microsoft-defender-atp/automated-investigations) これらの機能の上に、オプトイン管理ハンティング サービスの一環として、お客様はプロアクティブな通知を受け取り、Microsoft 脅威エキスパートオンデマンドで問い合わせできます。

### <a name="set-up-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint のセットアップ

![Microsoft Defender for Endpoint を展開するプロセス。](../media/deploy-threat-protection/deploy-mdatp-steps.png) 

1. [Microsoft Defender for Endpoint の環境を準備します](../security/defender-endpoint/deployment-phases.md)。
2. [エンドポイント用 Microsoft Defender を展開します](../security/defender-endpoint/production-deployment.md)。
3. [Microsoft Defender for Endpoint サービスにオンボードします](../security/defender-endpoint/onboarding.md)。
4. [上位のセキュリティ管理タスクを完了します](../security/defender-endpoint/tvm-security-recommendation.md)。

### <a name="more-information-about-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint の詳細

- [エンドポイント向け Microsoft Defender の詳細については、「Microsoft Defender for Endpoint」を参照してください](../security/defender-endpoint/microsoft-defender-endpoint.md)。
- [Microsoft Defender for Endpoint 評価ラボを試してみてください](../security/defender-endpoint/evaluation-lab.md)。

## <a name="step-6-configure-microsoft-cloud-app-security"></a>手順 6: 構成Microsoft Cloud App Security

[Microsoft Cloud App Security](/cloud-app-security)は、ログ コレクション、API コネクタ、リバース プロキシをサポートするクラウド アクセス セキュリティ ブローカーです。 Microsoft Cloud App Security、豊富な可視性、データ移動の制御、高度な分析を提供し、すべてのクラウド サービスでサイバー脅威を特定し、対処します。 Microsoft Cloud App Security を使用すると、セキュリティ操作によって組織の機密情報を保護し、サイバー脅威や異常から保護し、組織のデータにアクセスするアプリを検出および監視し、組織のクラウド アプリがコンプライアンス要件を満たしていることを確認できます。

### <a name="set-up-microsoft-cloud-app-security"></a>設定Microsoft Cloud App Security

![サーバーを展開するMicrosoft Cloud App Security。](../media/deploy-threat-protection/deploy-mcas-steps.png) 

1. [ポータルと他の基本的な要件を設定します](/cloud-app-security/general-setup)。
2. [クラウド検出をセットアップし、](/cloud-app-security/set-up-cloud-discovery) アプリ [を接続します](/cloud-app-security/enable-instant-visibility-protection-and-governance-actions-for-your-apps)。
3. [おすすめアプリの条件付きアクセス アプリ制御を展開します](/cloud-app-security/proxy-deployment-aad)。
4. [調査ツールとダッシュボードを使用します](/cloud-app-security/investigate)。

### <a name="more-information-about-microsoft-cloud-app-security"></a>Microsoft Cloud App Security の詳細情報

- [新機能と機能を確認します](/cloud-app-security/release-notes)。
- [詳細については、「Microsoft Cloud App Security」 を参照してください](/cloud-app-security/what-is-cloud-app-security)。

## <a name="step-7-monitor-status-and-take-actions"></a>手順 7: 状態を監視し、アクションを実行する

脅威保護サービスと機能をセットアップして展開した後、次に、脅威検出を監視し、適切なアクションを実行します。 最適な開始点は、Microsoft 365 セキュリティ センター ( ) で、Microsoft ID、データ、デバイス、アプリ、インフラストラクチャ全体でセキュリティを監視および [https://security.microsoft.com](https://security.microsoft.com) 管理できます。

![Microsoft 365セキュリティ センター。](../media/solutions-architecture-center/m365-security-center.png)

セキュリティ Microsoft 365は、セキュリティ管理者とセキュリティ運用チームを対象とします。 セキュリティ センター Microsoft 365次の機能を使用できます。

- Secure Score を使用して組織の全体的なセキュリティ正常性 [を表示します](/microsoft-365/security/defender/microsoft-secure-score)。
- [ID、データ、](../security/defender-endpoint/threat-protection-reports.md) デバイス、アプリ、インフラストラクチャの状態に関するレポートを監視および表示します。
- Connectを通じてアラートにドットを[表示します](/microsoft-365/security/defender/incident-queue)。
- 自動化 [された調査と修復を使用して](../security/defender/m365d-autoir.md) 、脅威に対処します。
- [電子メール、データ、デバイス](/microsoft-365/security/defender/advanced-hunting-overview)、および ID に影響を与える侵入の試みや侵害アクティビティなど、脅威を積極的に探します。
- [脅威分析を使用して、最新の](/microsoft-365/security/defender/latest-attack-campaigns) 攻撃キャンペーンと手法を理解します。
- ...その他!

### <a name="more-information-about-the-microsoft-365-security-center"></a>セキュリティ センターのMicrosoft 365詳細

- [セキュリティ センターのMicrosoft 365を開始します](../security/defender/overview-security-center.md)。
- [レポートを監視および表示します](../security/defender/overview-security-center.md)。
- [「セキュリティ ポータル」を参照Microsoft 365。](../security/defender/portals.md)

## <a name="step-8-train-users"></a>手順 8: ユーザーのトレーニング

トレーニング ユーザーは、ユーザーとセキュリティ運用チームに多くの時間と不満を保存できます。 精通したユーザーは、疑わしい電子メール メッセージで添付ファイルを開く、またはリンクをクリックする可能性が低く、疑わしい Web サイトを避ける可能性が高い。 

Harvard Kennedy School [Cybersecurity キャンペーン](https://go.microsoft.com/fwlink/?linkid=2015598&amp;clcid=0x409) ハンドブックは、フィッシング攻撃を識別するためのユーザーのトレーニングなど、組織内のセキュリティ意識の強い文化を確立するための優れたガイダンスを提供します。 

Microsoft 365、組織内のユーザーに通知するための次のリソースを提供します。

<br>

****

|概念|リソース|
|---|---|
|Microsoft 365|[カスタマイズ可能な学習経路](/office365/customlearning/) <p> これらのリソースは、組織内のエンド ユーザー向けトレーニングをまとめるのに役立ちます。|
|Microsoft 365 セキュリティ|[ラーニングモジュール: 組み込みのインテリジェント なセキュリティで組織をセキュリティで保護Microsoft 365](/learn/modules/security-with-microsoft-365) <p> このモジュールを使用すると、セキュリティ機能Microsoft 365機能を説明し、これらのセキュリティ機能の利点を明確にできます。|
|多要素認証|[2 段階認証: 追加の検証ページとは](/azure/active-directory/user-help/multi-factor-authentication-end-user-first-time) <p> この記事は、エンド ユーザーが多要素認証とは何か、および組織で使用される理由を理解するのに役立ちます。|
|

このガイダンスに加えて、Microsoft では、この記事で説明されているアクションをユーザーが実行するようにお勧めします。アカウントとデバイスをハッカーやマルウェアから [保護します](https://support.office.com/article/066d6216-a56b-4f90-9af3-b3a1e9a327d6.aspx)。 それらの操作を次に示します。

- 強力なパスワードの使用
- デバイスの保護
- デバイス PC および Mac pc Windows 10セキュリティ機能の有効化 (非管理対象デバイスの場合)

Microsoft では、次の記事で推奨されるアクションを実行して、ユーザーが個人の電子メール アカウントを保護することもできます。

- [Outlook.com メール アカウントの保護に役立つ](https://support.microsoft.com/office/help-protect-your-outlook-com-email-account-a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)
- [2 段階認証で Gmail アカウントを保護する](https://go.microsoft.com/fwlink/?linkid=2015688&amp;clcid=0x409)
