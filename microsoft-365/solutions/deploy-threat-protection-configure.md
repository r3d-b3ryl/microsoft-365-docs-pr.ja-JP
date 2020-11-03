---
title: Microsoft 365 で脅威保護機能を構成するための手順
description: Microsoft 365 E5 に脅威保護のサービスと機能を展開する方法について説明します。
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-threatprotection
- m365solution-scenario
ms.custom: ''
f1.keywords: NOCSH
ms.openlocfilehash: f3fa5c82efad0a51adf5e798bd89860e78256e15
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "48845314"
---
# <a name="configure-threat-protection-capabilities-across-microsoft-365"></a>Microsoft 365 で脅威保護機能を構成する

次の手順に従って、Microsoft 365 全体の脅威保護を構成します。


## <a name="step-1-set-up-multi-factor-authentication-and-conditional-access-policies"></a>手順 1: 多要素認証および条件付きアクセスポリシーを設定する

[多要素認証](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks) (MFA) では、ユーザーが電話またはオーセンティケータアプリで自分の身元を確認する必要があります。 [条件付きアクセスポリシー](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) は、ユーザーが Microsoft 365 でアプリとデータにアクセスするために満たす必要のある特定の要件を定義します。 MFA および条件付きアクセスポリシーは、組織を保護するために連携して機能します。 たとえば、ユーザーが MFA を有効にしていないアカウントを使用してモバイルデバイスからサインインしようとした場合、条件付きアクセスポリシーを有効にする必要がある場合、そのユーザーはサインインできません。  

Microsoft は、すべての SaaS アプリケーション (特に Microsoft 365) へのアクセスを保護するために、特定の条件付きアクセスと関連ポリシーのセットをテストし、推奨しています。 ポリシーは、ベースライン、機密、および高度な規制保護に対して推奨されます。 最初に、ベースライン保護のポリシーを実装します。 


[ ![ Id とデバイスのアクセスを構成するための一般的なポリシー](../media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png) 
 [この画像の大規模なバージョンの表示](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)

### <a name="to-implement-baseline-protection-for-microsoft-365"></a>Microsoft 365 のベースライン保護を実装するには

![ベースライン保護を展開するためのプロセス](../media/solutions-architecture-center/deploy-threat-protection-identity-access-steps.png) 

1. [Azure Id 保護を含む、前提条件を構成](../security/office-365-security/identity-access-prerequisites.md)します。
2. ベースライン保護用の[一般的な id およびデバイスアクセスポリシーを構成](../security/office-365-security/identity-access-policies.md)します。
3. [ゲストユーザー](../security/office-365-security/identity-access-policies-guest-access.md)、 [Microsoft Teams](../security/office-365-security/teams-access-policies.md)、 [Exchange Online](../security/office-365-security/secure-email-recommended-policies.md)、および[SharePoint online と OneDrive](../security/office-365-security/sharepoint-file-access-policies.md)のポリシーを構成します。

### <a name="more-information-about-protecting-identities"></a>Id の保護に関する詳細情報

- [ID とデバイスのアクセス構成](../security/office-365-security/microsoft-365-policies-configurations.md)
- [Azure MFA のセキュリティガイダンス](https://docs.microsoft.com/azure/active-directory/authentication/multi-factor-authentication-security-best-practices)

## <a name="step-2-configure-microsoft-defender-for-identity"></a>手順 2: Id 用に Microsoft Defender を構成する

[Microsoft Defender For Identity](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) は、クラウドベースのセキュリティソリューションであり、オンプレミスの [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) と連携して、高度な脅威、侵害された id、および組織に向けた悪意のある insider 操作を識別、検出、調査します。

Id 用の Microsoft Defender により、セキュリティ操作 (SecOps) アナリストとセキュリティ担当者は、ハイブリッド環境での高度な攻撃を検出するのに苦労して次のことを行うことができます。
- 学習ベースの分析を使用して、ユーザー、エンティティの動作、アクティビティを監視します。
- Active Directory に保存されているユーザーの ID と認証情報の保護。
- キル チェーン全体で疑わしいユーザー アクティビティや高度な攻撃を特定し、調査する。
- 迅速なトリアージのために、簡潔なタイムラインで示された明確なインシデント情報を提供する。

### <a name="to-set-up-microsoft-defender-for-identity"></a>Id に対して Microsoft Defender をセットアップするには

![Id の Microsoft Defender を展開するためのプロセス](../media/solutions-architecture-center/deploy-azure-atp-steps.png) 

1. プライマリ環境を保護するために、 [Microsoft Defender For Identity を設定](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step1)します。
2. すべての [ドメインコントローラー](https://docs.microsoft.com/azure-advanced-threat-protection/atp-sensor-monitoring) と [フォレスト](https://docs.microsoft.com/azure-advanced-threat-protection/atp-multi-forest)を保護します。
3. [Id 通知用の Microsoft Defender](https://docs.microsoft.com/azure-advanced-threat-protection/suspicious-activity-guide?tabs=external)をセキュリティ操作 (secops) ワークフローに統合します。

### <a name="more-information-about-microsoft-defender-for-identity"></a>Id の Microsoft Defender に関するその他の情報

- [Id の Microsoft Defender とは](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [ビデオ: Id の Microsoft Defender の概要](https://www.youtube.com/watch?reload=9&v=EGY2m8yU_KE)
- [Id 展開のための Microsoft Defender](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp#whats-next)

## <a name="step-3-turn-on-microsoft-365-defender"></a>手順 3: Microsoft 365 Defender をオンにする

[Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) は、シグナルを結合し、機能を調整して1つのソリューションにします。 統合された Microsoft 365 Defender ソリューションを使用することにより、セキュリティ担当者は、これらの各製品が脅威のすべての範囲と影響を受信して判断することを伝える脅威について協力することができます。環境にどのように対応したか、どのような影響を受けるか、どのように組織にどのように影響しているか。 Microsoft 365 Defender は、攻撃を阻止または停止する、または影響を受けるメールボックス、エンドポイント、ユーザー id を自己回復させるための自動操作を行います。

Microsoft 365 Defender は、アラート、インシデント、自動化された調査と応答を統合し、ワークロード全体にわたる高度な検索を行います (Microsoft Defender for Identity、microsoft Defender for Office 365、Microsoft defender for Endpoint、および Microsoft Cloud App Security) は、1つのウィンドウのガラス環境に統合されています。 Office 365 サービス用の1つ以上の Defender を構成した後、Microsoft 365 Defender を有効にします。 新機能は、絶えず Microsoft 365 Defender に追加されます。プレビュー機能を受信するには、をオプトインすることを検討してください。

### <a name="to-set-up-microsoft-365-defender"></a>Microsoft 365 Defender をセットアップするには

![Microsoft 365 Defender を展開するためのプロセス](../media/solutions-architecture-center/deploy-mtp-steps.png) 

1. [前提条件を確認](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites)します。
2. [Microsoft 365 Defender をオンに](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable)します。
3. [プレビュー機能のオプトイン](https://docs.microsoft.com/microsoft-365/security/mtp/preview)。

### <a name="more-information-about-microsoft-365-defender"></a>Microsoft 365 Defender の詳細情報

- [Microsoft 365 Defender とは](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection)
- [Microsoft 365 Defender の新機能](https://docs.microsoft.com/microsoft-365/security/mtp/whats-new)

## <a name="step-4-configure-microsoft-defender-for-office-365"></a>手順 4: Microsoft Defender for Office 365 を構成する

[Microsoft Defender For Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) 電子メールメッセージ (添付ファイルと url)、Office ドキュメント、コラボレーションツールの悪意のある脅威から組織を保護します。 次の表に、microsoft Defender for Office 365 の機能と、Microsoft 365 E5 に含まれる機能を示します。

|構成、保護、および検出の各機能|自動化、調査、修復、教育機能|
|---|---|
|[添付ファイル保護](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-attachments)<br/>[リンク保護](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links)<br/>[安全なドキュメント](https://docs.microsoft.com/microsoft-365/security/office-365-security/safe-docs)<br/>[SharePoint、OneDrive、Microsoft Teams 用の ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams)<br/>[Office 365 保護のための Defender でのフィッシング対策](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies#exclusive-settings-in-atp-anti-phishing-policies)|[脅威トラッカー](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-trackers)<br/>[脅威エクスプローラー](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer)<br/>[自動調査および対応](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)<br/>[攻撃シミュレータ](https://docs.microsoft.com/microsoft-365/security/office-365-security/attack-simulator)|
|

Office 365 用 Microsoft Defender を使用すると、組織内のユーザーは、電子メールコンテンツと Office ドキュメントの脅威を保護することで、より安全に通信および共同作業を行うことができます。

### <a name="to-set-up-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 をセットアップするには

![Office 365 の Microsoft Defender を展開するためのプロセス](../media/solutions-architecture-center/deploy-office365-atp-steps.png) 

1. [Microsoft Defender For Office 365 ポリシーをセットアップして構成し](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats)ます。
2. [Microsoft Defender For Office 365 レポートを表示して使用](https://docs.microsoft.com/microsoft-365/security/office-365-security/view-reports-for-atp)します。
3. [脅威の調査と応答の機能を使用](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-ti)します。

### <a name="more-information-about-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 の詳細情報

- [Microsoft Defender for Office 365 の概要](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)
- [Microsoft Defender for Office 365 の新機能](https://docs.microsoft.com/microsoft-365/security/office-365-security/whats-new-in-office-365-atp)

## <a name="step-5-configure-microsoft-defender-for-endpoint"></a>手順 5: エンドポイントの Microsoft Defender を構成する

[エンドポイントの Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection) は、脅威、高度な攻撃、データ侵害から組織のデバイス (エンドポイントとも呼ばれます) を保護します。 セキュリティチームは、エンドポイントのセキュリティをより効率的に管理することができます。 堅牢なツールにより、組織は脆弱性検出を使用して unpatched システムを [脅威と脆弱性を管理](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)していくことができます。 [攻撃対象領域の削減](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/overview-attack-surface-reduction)、[次世代の保護](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10)、[エンドポイントの検出と応答](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/overview-endpoint-detection-response)、自動化された[調査と修復](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)などの自動化された検出および修復の機能により、デバイスはマルウェアから安全に保持されます。 これらの機能の上に、お客様は事前の通知を受け取り、オプトイン管理対象のサービスの一部として、必要に応じて Microsoft の脅威の専門家に問い合わせることができます。 


### <a name="set-up-microsoft-defender-for-endpoint"></a>エンドポイントの Microsoft Defender をセットアップする

![エンドポイントの Microsoft Defender を展開するためのプロセス](../media/solutions-architecture-center/deploy-mdatp-steps.png) 

1. [エンドポイント展開用の Microsoft Defender を準備](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/deployment-phases)します。
2. [エンドポイント展開用に Microsoft Defender をセットアップする](https://docs.microsoft.com/windows/security/threat-protection/micros.oft-defender-atp/production-deployment)
3. [エンドポイントサービスの Microsoft Defender にオンボード](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/onboarding)。
4. [最上位のセキュリティ管理タスクを完了](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation)します。

### <a name="more-information-about-microsoft-defender-for-endpoint"></a>エンドポイントの Microsoft Defender に関する詳細情報

- [エンドポイントの Microsoft Defender の詳細について説明](https://docs.microsoft.com/windows/security/threat-protection)します。
- [エンドポイント評価ラボの Microsoft Defender をお試しください](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/evaluation-lab)。

## <a name="step-6-configure-microsoft-cloud-app-security"></a>手順 6: Microsoft Cloud App Security を構成する

[Microsoft Cloud App security](https://docs.microsoft.com/cloud-app-security) は、ログ収集、API コネクタ、リバースプロキシをサポートするクラウドアクセスセキュリティブローカーです。 Microsoft Cloud App Security は、豊富な可視性、データ移動の制御、および高度な分析を提供して、すべてのクラウドサービス全体にわたる脅威を識別して対処します。 Microsoft Cloud App Security を使用すると、セキュリティ操作によって組織の機密情報の保護、脅威および異常に対する保護、組織のデータにアクセスするアプリの検出と監視、組織のクラウドアプリがコンプライアンス要件を満たしていることの確認に役立ちます。

### <a name="set-up-microsoft-cloud-app-security"></a>Microsoft Cloud App Security をセットアップする

![Microsoft Cloud App Security を展開するためのプロセス](../media/solutions-architecture-center/deploy-mcas-steps.png) 

1. [ポータルおよびその他の基本的な要件を設定](https://docs.microsoft.com/cloud-app-security/general-setup)します。
2. [クラウド検出を設定](https://docs.microsoft.com/cloud-app-security/set-up-cloud-discovery) し、 [アプリを接続](https://docs.microsoft.com/cloud-app-security/enable-instant-visibility-protection-and-governance-actions-for-your-apps)します。
3. [おすすめのアプリに対して条件付きアクセスアプリコントロールを展開](https://docs.microsoft.com/cloud-app-security/proxy-deployment-aad)します。
4. [調査ツールおよびダッシュボードを使用](https://docs.microsoft.com/cloud-app-security/investigate)します。

### <a name="more-information-about-microsoft-cloud-app-security"></a>Microsoft Cloud App Security の詳細情報

- [新しい機能を確認](https://docs.microsoft.com/cloud-app-security/release-notes)します。
- [詳細については、「Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)」を参照してください。

## <a name="step-7-monitor-status-and-take-actions"></a>手順 7: 状態を監視し、アクションを実行する

脅威保護のサービスと機能を設定して展開した後、次の手順として、脅威の検出を監視し、適切な操作を行います。 最適な出発点は、microsoft 365 セキュリティセンター () を使用して、 [https://security.microsoft.com](https://security.microsoft.com) microsoft id、データ、デバイス、アプリ、およびインフラストラクチャ全体のセキュリティを監視および管理できます。 

![Microsoft 365 セキュリティ センター](../media/solutions-architecture-center/m365-security-center.png)

Microsoft 365 セキュリティセンターは、特にセキュリティ管理者およびセキュリティ運用チームを対象としています。 Microsoft 365 セキュリティセンターでは、次のことを行うことができます。
- セキュリティ [で保護さ](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score)れたスコアを使用して、組織の全体的なセキュリティの状態を表示します。
- Id、データ、デバイス、アプリ、およびインフラストラクチャの状態に関する[レポートを監視および表示し](https://docs.microsoft.com/microsoft-365/security/mtp/monitoring-and-reporting)ます。
- 警告のドットを [インシデント](https://docs.microsoft.com/microsoft-365/security/mtp/incident-queue)で接続します。
- 自動化された [調査と修復](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir) を使用して脅威に対処します。
- 侵入の試行、電子メール、データ、デバイス、および id に影響する侵入行為など[の脅威を事前に探し](https://docs.microsoft.com/microsoft-365/security/mtp/advanced-hunting-overview)ます。
- 脅威分析に関する[最新の攻撃キャンペーン](https://docs.microsoft.com/microsoft-365/security/mtp/latest-attack-campaigns)および手法を理解します。
- ...その他

### <a name="more-information-about-the-microsoft-365-security-center"></a>Microsoft 365 セキュリティセンターの詳細情報

- [Microsoft 365 セキュリティセンターを使用して作業を開始](https://docs.microsoft.com/microsoft-365/security/mtp/overview-security-center)します。
- [レポートを監視および表示](https://docs.microsoft.com/microsoft-365/security/mtp/monitoring-and-reporting)します。
- [「Microsoft 365 のセキュリティポータル」を参照してください](https://docs.microsoft.com/microsoft-365/security/mtp/portals)。

## <a name="step-8-train-users"></a>手順 8: ユーザーをトレーニングする

トレーニングユーザーは、ユーザーおよびセキュリティ運用チームの時間とイライラを大幅に節約できます。 経験豊富なユーザーは、添付ファイルを開いたり、疑わしい電子メールメッセージ内のリンクをクリックしたりする可能性が低くなり、疑わしい web サイトを避けられる可能性が高くなります。 

Harvard ケネディ School [Cybersecurity キャンペーンハンドブック](https://go.microsoft.com/fwlink/?linkid=2015598&amp;clcid=0x409) は、フィッシング攻撃を識別するユーザーのトレーニングを含む、組織内でのセキュリティの認知度の強力な文化を確立するための優れたガイダンスを提供します。 

Microsoft 365 には、組織内のユーザーに通知するための以下のリソースが用意されています。

|概念  |リソース  |
|---------|---------|
|Microsoft 365     |[カスタマイズ可能な学習経路](https://docs.microsoft.com/office365/customlearning/) <p>これらのリソースは、組織内のエンドユーザーのトレーニングをまとめる際に役立ちます。        |
|Microsoft 365 セキュリティ |[学習モジュール: Microsoft 365 からの組み込みのインテリジェントセキュリティを使用して組織を保護します。](https://docs.microsoft.com/learn/modules/security-with-microsoft-365) <p>このモジュールでは、Microsoft 365 のセキュリティ機能がどのように連携するかを説明し、これらのセキュリティ機能の利点を明確に示すことができます。 |
|多要素認証     | [2段階認証: 追加の検証ページとは](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-first-time) <p>この記事では、エンドユーザーが多要素認証の内容と、組織で使用されている理由を理解するのに役立てることができます。    |

このガイダンスに加えて、次の操作を実行することをお勧めします。この記事では、 [ハッカーやマルウェアからのアカウントとデバイスの保護](https://support.office.com/article/066d6216-a56b-4f90-9af3-b3a1e9a327d6.aspx)について説明します。 それらの操作を次に示します。
- 強力なパスワードの使用
- デバイスを保護する 
- Windows 10 および Mac Pc でセキュリティ機能を有効にする (管理されていないデバイスの場合)
    
また、次の記事で推奨されている操作を実行して、ユーザーが個人のメールアカウントを保護することをお勧めします。
- [Outlook.com メールアカウントを保護する](https://support.microsoft.com/office/help-protect-your-outlook-com-email-account-a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)
- [2段階認証を使用して Gmail アカウントを保護する](https://go.microsoft.com/fwlink/?linkid=2015688&amp;clcid=0x409)
