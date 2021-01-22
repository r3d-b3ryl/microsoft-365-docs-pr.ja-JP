---
title: Microsoft 365 全体で脅威保護機能を構成する手順
description: Microsoft 365 E5 全体に脅威保護サービスと機能を展開する方法について説明します。
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.audience: ITPro
ms.topic: article
ms.prod: m365-security
ms.technology: m365d
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-threatprotection
- m365solution-scenario
ms.custom: ''
f1.keywords: NOCSH
ms.openlocfilehash: 492db78c9aea881ae05dbc66f5e84ad98629b923
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931988"
---
# <a name="configure-threat-protection-capabilities-across-microsoft-365"></a>Microsoft 365 全体の脅威保護機能を構成する

Microsoft 365 全体の脅威保護を構成するには、次の手順に従います。


## <a name="step-1-set-up-multi-factor-authentication-and-conditional-access-policies"></a>手順 1: 多要素認証と条件付きアクセス ポリシーを設定する

[多要素認証](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks) (MFA) では、ユーザーは通話または認証アプリで ID を確認する必要があります。 [条件付きアクセス ポリシーは、](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) ユーザーが Microsoft 365 のアプリとデータにアクセスするために満たす必要がある特定の要件を定義します。 MFA と条件付きアクセス ポリシーが一緒に機能し、組織を保護します。 たとえば、MFA が有効になっていないアカウントを使用してモバイル デバイスからサインインしようとして、条件付きアクセス ポリシーで MFA を有効にする必要がある場合、そのユーザーはサインインできません。  

Microsoft では、すべての SaaS アプリケーション (特に Microsoft 365) へのアクセスを保護するための特定の条件付きアクセスと関連ポリシーのセットをテストし、推奨しています。 ベースライン、機密、および厳しく規制された保護には、ポリシーをお勧めします。 まず、ベースライン保護のポリシーを実装します。 


[ ![ ID とデバイス アクセスを構成するための一般的な](../media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)ポリシー 
 [このイメージのより大きなバージョンを表示する](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)

### <a name="to-implement-baseline-protection-for-microsoft-365"></a>Microsoft 365 のベースライン保護を実装するには

![ベースライン保護を展開するプロセス](../media/solutions-architecture-center/deploy-threat-protection-identity-access-steps.png) 

1. [Azure Identity Protection を含む前提条件を構成します](../security/office-365-security/identity-access-prerequisites.md)。
2. [ベースライン保護用に共通の ID およびデバイス](../security/office-365-security/identity-access-policies.md) アクセス ポリシーを構成します。
3. ゲスト ユーザー [、Microsoft Teams、Exchange](../security/office-365-security/teams-access-policies.md) [Online、](../security/office-365-security/secure-email-recommended-policies.md)および[SharePoint Online と OneDrive のポリシーを構成します](../security/office-365-security/sharepoint-file-access-policies.md)。 [](../security/office-365-security/identity-access-policies-guest-access.md)

### <a name="more-information-about-protecting-identities"></a>ID の保護に関する詳細

- [ID とデバイスのアクセス構成](../security/office-365-security/microsoft-365-policies-configurations.md)
- [Azure MFA のセキュリティ ガイダンス](https://docs.microsoft.com/azure/active-directory/authentication/multi-factor-authentication-security-best-practices)

## <a name="step-2-configure-microsoft-defender-for-identity"></a>手順 2: Id 用に Microsoft Defender を構成する

[Microsoft Defender for Identity](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) は、オンプレミス [の Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) シグナルと一緒に動作し、高度な脅威、侵害された ID、組織に向けられた悪意のあるインサイダー アクションを特定、検出、調査するクラウドベースのセキュリティ ソリューションです。

Microsoft Defender for Identity を使用すると、セキュリティ操作 (SecOps) アナリストやセキュリティ担当者は、ハイブリッド環境での高度な攻撃の検出に取り組み、次の作業を行えます。
- 学習ベースの分析を使用して、ユーザー、エンティティの動作、アクティビティを監視します。
- Active Directory に保存されているユーザーの ID と認証情報の保護。
- キル チェーン全体で疑わしいユーザー アクティビティや高度な攻撃を特定し、調査する。
- 迅速なトリアージのために、簡潔なタイムラインで示された明確なインシデント情報を提供する。

### <a name="to-set-up-microsoft-defender-for-identity"></a>Id 用に Microsoft Defender をセットアップするには

![Id 用 Microsoft Defender を展開するプロセス](../media/solutions-architecture-center/deploy-azure-atp-steps.png) 

1. [プライマリ環境を保護するために Id](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step1) 用に Microsoft Defender をセットアップします。
2. すべてのドメイン コントローラー [とフォレストを](https://docs.microsoft.com/azure-advanced-threat-protection/atp-sensor-monitoring) 保護 [します](https://docs.microsoft.com/azure-advanced-threat-protection/atp-multi-forest)。
3. Id [に関する Microsoft Defender の警告を](https://docs.microsoft.com/azure-advanced-threat-protection/suspicious-activity-guide?tabs=external) セキュリティ操作 (SecOps) ワークフローに統合します。

### <a name="more-information-about-microsoft-defender-for-identity"></a>Microsoft Defender for Identity の詳細

- [Microsoft Defender for Identity とは](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [ビデオ: Id 用 Microsoft Defender の概要](https://www.youtube.com/watch?reload=9&v=EGY2m8yU_KE)
- [Id の展開用 Microsoft Defender](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp#whats-next)

## <a name="step-3-turn-on-microsoft-365-defender"></a>手順 3: Microsoft 365 Defender を有効にする

[Microsoft 365 Defender は](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) 信号を組み合わせ、機能を統合して 1 つのソリューションに統合します。 統合された Microsoft 365 Defender ソリューションにより、セキュリティ担当者は、これらの各製品が受け取る脅威シグナルをまとめ、脅威の全範囲と影響を特定できます。環境に入った方法、影響を受けるもの、組織に現在どのような影響を与えています。 Microsoft 365 Defender は、攻撃を防止または停止し、影響を受けるメールボックス、エンドポイント、ユーザー ID を自己回復する自動アクションを実行します。

Microsoft 365 Defender は、アラート、インシデント、自動調査と対応、ワークロード間の高度な捜ティング (Microsoft Defender for Identity、Office 365 用 Microsoft Defender、エンドポイント用 Microsoft Defender、Microsoft Cloud App Security) を 1 つのウィンドウに統合します。 365 サービス用に 1 つ以上の Defender をOffice、Microsoft 365 Defender を有効にしてください。 Microsoft 365 Defender に新機能が継続的に追加されます。プレビュー機能を受け取るオプトインを検討してください。

### <a name="to-set-up-microsoft-365-defender"></a>Microsoft 365 Defender をセットアップするには

![Microsoft 365 Defender を展開するプロセス](../media/solutions-architecture-center/deploy-mtp-steps.png) 

1. [前提条件を確認します](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites)。
2. [Microsoft 365 Defender を有効にする](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable)。
3. [プレビュー機能をオプトインします](https://docs.microsoft.com/microsoft-365/security/mtp/preview)。

### <a name="more-information-about-microsoft-365-defender"></a>Microsoft 365 Defender の詳細

- [Microsoft 365 Defender とは](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection)
- [Microsoft 365 Defender の新機能](https://docs.microsoft.com/microsoft-365/security/mtp/whats-new)

## <a name="step-4-configure-microsoft-defender-for-office-365"></a>手順 4: Microsoft Defender を Office 365 用に構成する

[Microsoft Defender for Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) は、電子メール メッセージ (添付ファイルと URL)、Office ドキュメント、コラボレーション ツールの悪意のある脅威から組織を保護します。 次の表に、Microsoft 365 E5 にOffice 365 の機能を提供する Microsoft Defender の一覧を示します。

|構成、保護、および検出の機能|自動化、調査、修復、および教育機能|
|---|---|
|[添付ファイル保護](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-attachments)<br/>[リンク保護](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links)<br/>[安全なドキュメント](https://docs.microsoft.com/microsoft-365/security/office-365-security/safe-docs)<br/>[SharePoint、OneDrive、Microsoft Teams 用の ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams)<br/>[Defender for Office 365 保護のフィッシング詐欺対策](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies#exclusive-settings-in-atp-anti-phishing-policies)|[脅威トラッカー](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-trackers)<br/>[脅威エクスプローラー](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer)<br/>[自動調査および対応](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)<br/>[攻撃シミュレータ](https://docs.microsoft.com/microsoft-365/security/office-365-security/attack-simulator)|
|

Office 365 用 Microsoft Defender を使用すると、組織全体のユーザーは、電子メール コンテンツとドキュメントの脅威保護を使用して、より安全に通信および共同作業Officeできます。

### <a name="to-set-up-microsoft-defender-for-office-365"></a>Microsoft Defender を Office 365 用にセットアップするには

![Microsoft Defender for Office 365 の展開プロセス](../media/solutions-architecture-center/deploy-office365-atp-steps.png) 

1. [365 ポリシー用に Microsoft Defender Office構成します](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats)。
2. [Microsoft Defender を 365 レポートOfficeして使用します](https://docs.microsoft.com/microsoft-365/security/office-365-security/view-reports-for-atp)。
3. [脅威の調査と対応の機能を使用します](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-ti)。

### <a name="more-information-about-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 の詳細

- [Microsoft Defender for Office 365 の概要](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)
- [Microsoft Defender for Office 365 の新機能](https://docs.microsoft.com/microsoft-365/security/office-365-security/whats-new-in-office-365-atp)

## <a name="step-5-configure-microsoft-defender-for-endpoint"></a>手順 5: エンドポイント用に Microsoft Defender を構成する

[Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) は、組織のデバイス (エンドポイントとも呼ばれます) をサイバー脅威、高度な攻撃、データ侵害から保護します。 セキュリティ チームは、エンドポイントのセキュリティを管理する効率を高くすることができます。 堅牢なツールは、脅威と脆弱性管理による脆弱性検出を使用して、未修正のシステムに関する組織 [の対応を支援します](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)。 攻撃表面の縮小、次世代の保護、エンドポイント[](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/overview-attack-surface-reduction)の検出と対応[](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10)、自動調査と修復[](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/overview-endpoint-detection-response)などの自動検出と修復機能により、デバイスをマルウェアから保護できます。 [](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations) これらの機能の上に、オプトインマネージ ハンティング サービスの一環として、お客様は事前通知を受け取り、Microsoft Threat Experts にオンデマンドで問い合わせできます。 


### <a name="set-up-microsoft-defender-for-endpoint"></a>エンドポイント用に Microsoft Defender をセットアップする

![Microsoft Defender for Endpoint を展開するプロセス](../media/solutions-architecture-center/deploy-mdatp-steps.png) 

1. [Microsoft Defender for Endpoint の展開を準備します](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/deployment-phases)。
2. [Microsoft Defender for Endpoint の展開をセットアップする](https://docs.microsoft.com/windows/security/threat-protection/micros.oft-defender-atp/production-deployment)
3. [Microsoft Defender for Endpoint サービスにオンボードします](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/onboarding)。
4. [上位のセキュリティ管理タスクを完了します](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation)。

### <a name="more-information-about-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint の詳細

- [Microsoft Defender for Endpoint について詳しくは、次をご覧ください](https://docs.microsoft.com/windows/security/threat-protection)。
- [Microsoft Defender for Endpoint 評価ラボをお試しください](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/evaluation-lab)。

## <a name="step-6-configure-microsoft-cloud-app-security"></a>手順 6: Microsoft Cloud App Security を構成する

[Microsoft Cloud App Security は](https://docs.microsoft.com/cloud-app-security) 、ログ収集、API コネクタ、リバース プロキシをサポートするクラウド アクセス セキュリティ ブローカーです。 Microsoft Cloud App Security は、すべてのクラウド サービスでサイバー脅威を特定して対処するための、豊富な可視性、データ移動の制御、高度な分析機能を提供します。 Microsoft Cloud App Security を使用すると、セキュリティ操作によって組織の機密情報を保護し、サイバー脅威や異常から保護し、組織のデータにアクセスするアプリを検出して監視し、組織のクラウド アプリがコンプライアンス要件を満たしていることを確認できます。

### <a name="set-up-microsoft-cloud-app-security"></a>Microsoft Cloud App Security のセットアップ

![Microsoft Cloud App Security を展開するプロセス](../media/solutions-architecture-center/deploy-mcas-steps.png) 

1. [ポータルと他の基本的な要件を設定します](https://docs.microsoft.com/cloud-app-security/general-setup)。
2. [クラウド検出をセットアップし、](https://docs.microsoft.com/cloud-app-security/set-up-cloud-discovery) アプリ [を接続します](https://docs.microsoft.com/cloud-app-security/enable-instant-visibility-protection-and-governance-actions-for-your-apps)。
3. [おすすめアプリの条件付きアクセス アプリ制御を展開します](https://docs.microsoft.com/cloud-app-security/proxy-deployment-aad)。
4. [調査ツールとダッシュボードを使用します](https://docs.microsoft.com/cloud-app-security/investigate)。

### <a name="more-information-about-microsoft-cloud-app-security"></a>Microsoft Cloud App Security の詳細情報

- [新しい機能を確認します](https://docs.microsoft.com/cloud-app-security/release-notes)。
- [Microsoft Cloud App Security について詳しくは、次をご覧ください](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)。

## <a name="step-7-monitor-status-and-take-actions"></a>手順 7: 状態を監視してアクションを実行する

脅威保護サービスと機能をセットアップして展開した後、次の手順では、脅威の検出を監視し、適切なアクションを実行します。 最適な開始点は、Microsoft 365 セキュリティ センター ( ) です。Microsoft ID、データ、デバイス、アプリ、インフラストラクチャ全体のセキュリティを監視および [https://security.microsoft.com](https://security.microsoft.com) 管理できます。 

![Microsoft 365 セキュリティ センター](../media/solutions-architecture-center/m365-security-center.png)

Microsoft 365 セキュリティ センターは、セキュリティ管理者とセキュリティ運用チームを対象にしています。 Microsoft 365 セキュリティ センターでは、次の方法を実行できます。
- セキュリティ スコアで組織の全体的なセキュリティ正常性 [を表示します](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score)。
- [ID、データ、](https://docs.microsoft.com/microsoft-365/security/mtp/monitoring-and-reporting) デバイス、アプリ、インフラストラクチャの状態に関するレポートを監視および表示します。
- インシデントを通じてアラートのドット [を接続します](https://docs.microsoft.com/microsoft-365/security/mtp/incident-queue)。
- 脅威 [に対処するには、自動調査と修復](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir) を使用します。
- [メール、データ、デバイス](https://docs.microsoft.com/microsoft-365/security/mtp/advanced-hunting-overview)、ID に影響を与える侵入の試み、違反アクティビティなどの脅威を事前に検出します。
- [脅威分析を使用して、最新の](https://docs.microsoft.com/microsoft-365/security/mtp/latest-attack-campaigns) 攻撃キャンペーンと手法を理解します。
- ...その他

### <a name="more-information-about-the-microsoft-365-security-center"></a>Microsoft 365 セキュリティ センターの詳細

- [Microsoft 365 セキュリティ センターの使用を開始します](https://docs.microsoft.com/microsoft-365/security/mtp/overview-security-center)。
- [レポートを監視および表示します](https://docs.microsoft.com/microsoft-365/security/mtp/monitoring-and-reporting)。
- [Microsoft 365 のセキュリティ ポータルを参照してください](https://docs.microsoft.com/microsoft-365/security/mtp/portals)。

## <a name="step-8-train-users"></a>手順 8: ユーザーをトレーニングする

ユーザーをトレーニングすると、ユーザーとセキュリティ運用チームに多くの時間と不満を感じさせ、作業を行う時間を節約できます。 精通しているユーザーは、疑わしい電子メール メッセージで添付ファイルを開く、またはリンクをクリックする可能性が低く、疑わしい Web サイトを回避する可能性が高い。 

H phish School [Cybersecurity キャンペーン](https://go.microsoft.com/fwlink/?linkid=2015598&amp;clcid=0x409) ハンドブックは、フィッシング攻撃を識別するためのユーザーのトレーニングなど、組織内のセキュリティ認識の強力な文化を確立するための優れたガイダンスを提供します。 

Microsoft 365 には、組織内のユーザーに通知するのに役立つ次のリソースが提供されています。

|概念  |リソース  |
|---------|---------|
|Microsoft 365     |[カスタマイズ可能な学習経路](https://docs.microsoft.com/office365/customlearning/) <p>これらのリソースは、組織内のエンド ユーザー向けトレーニングをまとめるのに役立ちます。        |
|Microsoft 365 セキュリティ |[学習モジュール: Microsoft 365 の組み込みのインテリジェント なセキュリティで組織を保護する](https://docs.microsoft.com/learn/modules/security-with-microsoft-365) <p>このモジュールでは、Microsoft 365 のセキュリティ機能がどのように機能するのかについて説明し、これらのセキュリティ機能の利点を明確に示します。 |
|多要素認証     | [2 段階認証: 追加の確認ページとは](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-first-time) <p>この記事は、多要素認証の意味と、それが組織で使用されている理由をエンド ユーザーが理解するのに役立ちます。    |

このガイダンスに加えて、Microsoft では、「アカウントとデバイスをハッカーやマルウェアから保護する」で説明されているアクションをユーザーが実行 [するようにお勧めします](https://support.office.com/article/066d6216-a56b-4f90-9af3-b3a1e9a327d6.aspx)。 それらの操作を次に示します。
- 強力なパスワードの使用
- デバイスの保護 
- Windows 10 および Mac PC でセキュリティ機能を有効にする (非管理対象デバイスの場合)
    
また、次の記事で推奨されるアクションを実行して、ユーザーが個人の電子メール アカウントを保護することもできます。
- [メール アカウントをOutlook.comする](https://support.microsoft.com/office/help-protect-your-outlook-com-email-account-a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)
- [2 段階認証による Gmail アカウントの保護](https://go.microsoft.com/fwlink/?linkid=2015688&amp;clcid=0x409)
