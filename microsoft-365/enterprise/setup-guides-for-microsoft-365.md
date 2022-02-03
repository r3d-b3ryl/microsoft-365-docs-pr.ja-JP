---
title: Microsoft 365 および Office 365 サービスのセットアップ ガイド
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- Ent_O365
- M365-subscription-management
- SPO_Content
- m365initiative-coredeploy
f1.keywords:
- CSH
ms.custom: Adm_O365_Setup
search.appverid:
- MET150
- MET150
- BCS160
ms.assetid: 165f46e8-3533-4d76-be57-97f81ebd40f2
description: テナントのライセンスの機能を計画、移行、および実装するためのステップバイステップのツールを取得します。 サービスまたは実行する必要があるアプリをセットアップするガイドを見つける。
ms.openlocfilehash: 91b89eeaec3a9d0db5f191cbd10c797a633c633b
ms.sourcegitcommit: e3bff611439354e6339bb666a88682078f32ec13
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2022
ms.locfileid: "62354602"
---
# <a name="setup-guides-for-microsoft-365-and-office-365-services"></a>Microsoft 365 および Office 365 サービスのセットアップ ガイド

Microsoft 365およびOffice 365セットアップ ガイドでは、テナント、アプリ、およびサービスを計画および展開するために、カスタマイズされたガイダンスとリソースを提供します。 これらのガイドは、オンボーディング スペシャリストが個々のMicrosoft 365 FastTrack[](https://www.microsoft.com/fasttrack/microsoft-365)共有するのと同じベスト プラクティスを使用して作成され、Microsoft 365 管理センター 内のすべての管理者が利用できます。 製品のセットアップ、セキュリティ機能の有効化、コラボレーション ツールの展開に関する情報を提供し、高度な展開を高速化するためのスクリプトを提供します。

> [!NOTE]
> グローバル リーダーのような管理者ロールを割り当てる必要があります。この設定ガイドMicrosoft 365アクセスします。 グローバル管理者の役割を持つ管理者だけが、ガイドを使用してテナントの設定を変更できます。

## <a name="how-to-access-setup-guides-in-the-microsoft-365-admin-center"></a>ウィザードのセットアップ ガイドにアクセスするMicrosoft 365 管理センター

セットアップ ガイドは、このページの [[セットアップ](https://aka.ms/setupguidance) ガイダンス] ページからMicrosoft 365 管理センター。 進捗状況を追跡し、いつでも戻ってガイドを完成できます。 [セットアップ ガイダンス] **ページにアクセスするには、次の手順を実行** します。

1. [ホーム] [Microsoft 365 管理センター](https://admin.microsoft.com/)[ホーム] ページ **に移動** します。

2. トレーニング ガイド **カード&見** つける。

   ![トレーニング &ガイド カードのMicrosoft 365 管理センター](../media/setup-guides-for-microsoft-365/adminportal-trainingandguides.png)

3. [ **高度な展開ガイド] を選択** し、[すべての **ガイド] を選択します**。

   ![ページの [セットアップ ガイダンス] ページのスクリーンショットMicrosoft 365 管理センター](../media/setup-guides-for-microsoft-365/adminportal-setupguidance.png)

## <a name="guides-for-initial-setup"></a>初期セットアップのガイド

### <a name="prepare-your-environment"></a>環境を準備する

「[環境を準備する」](https://aka.ms/prepareyourenvironment)ガイドは、組織の環境を、サービスやサービスのMicrosoft 365するのにOffice 365します。 目標が何であれ、展開を成功するために完了する必要があるタスクがあります。 環境の準備中にエラーが発生しないようにするには、ドメインの接続、ユーザーの追加、ライセンスの割り当て、Exchange Online による電子メールのセットアップ、Office アプリのインストールまたは展開を行う手順が記載されています。

### <a name="email-setup-guide"></a>メールのセットアップ ガイド

電子[メールのセットアップ ガイド](https://aka.ms/office365setup)では、組織の構成に必要な手順Exchange Online説明します。 このガイダンスには、新しいメール アカウントの設定、メールの移行、および電子メール保護の構成が含まれます。 メールのセットアップを成功するには、このアドバイザーを使用して、組織の現在のメール システム、移行するメールボックスの数、およびユーザーとそのアクセスを管理する方法に基づいて、推奨される移行方法を受け取る必要があります。

### <a name="migrate-gmail-contacts-and-calendar-items"></a>Gmail の連絡先と予定表アイテムを移行する

Gmail ユーザーのメールボックスをユーザーのメールボックスに移行Microsoft 365メール メッセージは移行されますが、連絡先と予定表アイテムは移行されません。 Gmail の[連絡先](https://aka.ms/gmailcontactscalendar)と予定表アドバイザーは、Outlook.com、Outlook クライアント、または PowerShell を使用して、google 連絡先と Google 予定表アイテムを Microsoft 365 にインポートする手順を提供します。

### <a name="microsoft-365-setup-guide"></a>Microsoft 365 セットアップ ガイド

この[Microsoft 365ガイドでは](https://aka.ms/microsoft365setupguide)、生産性ツール、セキュリティ ポリシー、およびデバイス管理機能をセットアップする際のガイダンスを提供します。 Microsoft 365 Business Premium またはエンタープライズ サブスクリプション版 Microsoft 365 があれば、このアドバイザーを使用して組織のデバイスをセットアップし、構成できます。

クラウド サービスを有効にし、デバイスを最新のサポートされているバージョンの Windows 10 に更新し、デバイスを Azure Active Directory (Azure AD) に参加する、すべてのリソースへのガイダンスとアクセスを 1 つの中央の場所で受け取る。

### <a name="remote-work-setup-guide"></a>リモート ワーク セットアップ ガイド

リモート [作業セットアップ ガイド](https://aka.ms/remoteworksetup) では、ユーザーがリモートで正常に作業し、データが安全で、ユーザーの資格情報を保護するために必要なヒントとリソースを組織に提供します。

クラウド内の Microsoft 365 リソースと組織のネットワークの両方へのリモート ワーカーのデバイス トラフィックを最適化するためのガイダンスを受け取り、リモート アクセス VPN インフラストラクチャの負荷を軽減します。

### <a name="microsoft-edge-setup-guide"></a>Microsoft Edgeセットアップ ガイド

Microsoft Edgeは、世界クラスの互換性とパフォーマンス、セキュリティとプライバシー、および最高の Web を提供するように設計された新機能を提供するために、一から再構築されました。

[Microsoft Edge](https://aka.ms/edgeadvisoradmin) セットアップ ガイドは、組織でアクセスするサイトが IE モードを使用する必要がある場合を確認し、重要なセキュリティ機能を確認および構成し、組織の要件を満たしてプライバシー ポリシーとコンプライアンス ポリシーを構成し、デバイス上の Web アクセスを管理するために、Enterprise Site Discovery を構成するのに役立ちます。 個々のデバイスMicrosoft Edgeダウンロードするか、グループ ポリシー、Configuration Manager、またはグループ ポリシーを使用して組織の複数のユーザーに展開する方法をMicrosoft Intune。

### <a name="configure-ie-mode-for-microsoft-edge"></a>IE モードを構成Microsoft Edge

Microsoft Edge を既に展開し、IE モードのみを構成する場合は、[[Microsoft Edge 用の IE](https://aka.ms/configureiemodeadmin) モードの構成] ガイドでは、Enterprise Site Discovery の構成を自動化するためのスクリプトを提供します。 また、クラウド ベースのツールから IE モードの推奨事項を取得し、ユーザーに展開する Enterprise モード サイト 一覧を作成するのに役立ちます。

### <a name="microsoft-search-setup-guide"></a>Microsoft Search セットアップ ガイド

Microsoft Search作業を完了するために必要な情報を組織が見つけるのに役立ちます。 ユーザー、ファイル、組織のグラフ、サイト、または一般的な質問に対する回答を検索する場合でも、組織は、Microsoft Search を使用して回答を取得できます。

この[Microsoft Searchセットアップ ガイド](https://aka.ms/MicrosoftSearchSetup)は、Microsoft Searchにパイロットするか、組織のすべてのユーザーに展開するかの設定を構成するのに役立ちます。検索管理者と検索エディターを割り当て、Bing 拡張機能を Chrome に追加したり、既定の検索エンジンとして Bing を設定したりなど、回答などのオプションを使用してユーザーの検索エクスペリエンスをカスタマイズします。

## <a name="guides-for-authentication-and-access"></a>認証とアクセスのガイド

### <a name="configure-multi-factor-authentication-mfa"></a>多要素認証 (MFA) を構成する

多 [要素認証 (MFA) の構成ガイドでは](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/featureexplorer/security/ConditionalAccess) 、資格情報の紛失または盗難による違反から組織を保護するための情報を提供します。 MFA は、アプリまたは他の会社のリソースにサインインするときに、ユーザーの ID を証明する複数の形式の検証を求めるプロンプトを表示することで、アカウントのセキュリティを直ちに強化します。 このプロンプトは、ユーザーのモバイル デバイスにコードを入力するか、指紋スキャンを提供する場合があります。 MFA は、条件付きアクセス、セキュリティの既定値、またはユーザーごとの MFA を使用して有効になります。 このガイドでは、ライセンスと既存の構成に基づいて、組織に推奨される MFA オプションを提供します。

### <a name="identity-security-for-teams"></a>ユーザーの ID セキュリティTeams

チーム [の Id セキュリティ](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/teamsidentity) ガイドは、ユーザーが安全で、ユーザーが安全で、ユーザーを使用して最も生産性の高い時間を過ご **Teams。**

### <a name="add-or-sync-users-to-microsoft-365"></a>ユーザーをユーザーに追加または同期Microsoft 365

[このガイド](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/modernonboarding/identitywizard)は、ユーザー アカウントをユーザー アカウントでセットアップするプロセスを合理化 **Microsoft 365。** 環境とニーズに基づいて、ユーザーを個別に追加するか、Azure AD クラウド同期または Azure AD Connect を使用してオンプレミス ディレクトリを移行するか、必要に応じて既存の同期の問題のトラブルシューティングを行います。

### <a name="azure-ad-setup-guide"></a>Azure ADセットアップ ガイド

[Azure AD セットアップ ガイド](https://aka.ms/aadpguidance)には、組織の強固なセキュリティ基盤を確保するための情報が記載されています。 このガイドでは、管理者向け Azure Role ベースのアクセス制御 (Azure RBAC)、オンプレミス ディレクトリの Azure AD Connect、Azure AD Connect Health など、初期機能をセットアップして、自動同期中にハイブリッド ID の正常性を監視できます。

また、セルフサービス パスワードのリセット、条件付きアクセス、オプションの高度な ID 保護、ユーザー プロビジョニングの自動化を含む統合サード パーティ製サインオンの有効化に関する重要な情報も含まれています。

### <a name="sync-users-from-your-windows-server-active-directory"></a>ユーザーを自分のアカウントから同期Windows Server Active Directory

[[ユーザーの同期] ガイドWindows Server Active Directory](https://aka.ms/directorysyncsetup)、ディレクトリ同期を有効にする方法を示します。 ディレクトリ同期により、オンプレミス ID とクラウド ID が一緒になり、アクセスが容易になり、管理が簡素化されます。 シングル サインオン、セルフサービス オプション、自動アカウント プロビジョニング、条件付きアクセス制御、コンプライアンス ポリシーなど、新しい機能のロックを解除します。 これらの機能により、ユーザーはどこからでも必要なリソースにアクセスできます。

### <a name="plan-your-passwordless-deployment"></a>パスワードレス展開の計画

次のいずれかのパスワードレス認証方法を使用して、ユーザーがデバイスに安全にアクセスできる別のサインイン 方法にアップグレードします。

- Windows Hello for Business
- Microsoft Authenticator アプリ
- セキュリティ キー

「パスワード [レス展開を](https://aka.ms/passwordlesssetup) 計画する」ガイドを使用して、それらを展開する方法に関するガイダンスを使用して受け取る最適なパスワードレス認証方法を確認します。

### <a name="integrate-a-third-party-cloud-app-with-azure-ad"></a>サードパーティのクラウド アプリとクラウド アプリを統合Azure AD

[このガイドは](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/azureadappintegration) 、IT 管理者がアプリを選択して構成するのに役立ちます。

### <a name="plan-your-self-service-password-reset-sspr-deployment"></a>セルフサービス パスワード リセット (SSPR) の展開を計画する

ユーザーが自分のアカウントがロックされている場合、またはヘルプデスク のエンジニアに問い合わせることなくパスワードを忘れた場合は、ユーザーが自分のパスワードを個別に変更またはリセットできます。

環境 [での](https://aka.ms/SSPRSetupGuide) SSPR の展開に役立つ適切な Azure ポータル オプションを構成するための関連記事と手順を受け取る場合は、「セルフサービス のパスワード リセット展開の計画」の展開ガイドを使用します。

### <a name="active-directory-federation-services-ad-fs-deployment-advisor"></a>Active Directory フェデレーション サービス (AD FS) 展開アドバイザー

[AD FS 展開アドバイザー](https://aka.ms/adfsguidance)は、Microsoft 365 および Office 365 サービスのユーザーを認証するオンプレミス AD FS インフラストラクチャの展開に関する段階的なガイダンスを提供します。 このガイドを使用すると、組織は AD FS コンポーネントと要件を確認し、展開に必要な SSL 証明書を取得してインストールし、必要な Web アプリケーション プロキシ サーバーをインストールできます。

## <a name="guides-for-security-and-compliance"></a>セキュリティとコンプライアンスのガイド

### <a name="security-analyzer"></a>セキュリティ アナライザー

セキュリティ [アナライザーは、](https://aka.ms/securityanalyzer) セキュリティ アプローチを分析し、セキュリティ体制を改善できる Microsoft 統合セキュリティおよびコンプライアンス ソリューションを紹介します。 ID の管理や最新の攻撃から保護するための支援など、高度な機能について学習します。 その後、試用版サブスクリプションにサインアップし、各ソリューションの対応するセットアップ ガイダンスを参照できます。

### <a name="microsoft-intune-setup-guide"></a>Microsoft Intuneセットアップ ガイド

組織のMicrosoft Intune管理するデバイスを設定します。 企業のデバイスを完全に制御するには、Intune のモバイル デバイス管理 (MDM) 機能を使用します。 共有デバイスと個人用デバイスで組織のデータを管理するには、Intune のモバイル アプリケーション管理 (MAM) 機能を使用できます。

[Microsoft Intune[セットアップ](https://aka.ms/intunesetupguide) ガイドでは、デバイスとアプリのコンプライアンス ポリシーを設定し、アプリ保護ポリシーを割り当て、デバイスとアプリ保護の状態を監視します。

### <a name="microsoft-defender-for-endpoint-setup-guide"></a>Microsoft Defender for Endpoint セットアップ ガイド

[Microsoft Defender for Endpoint セットアップ ガイドには](https://aka.ms/mdatpsetup)、高度な脅威を防止、検出、調査、および対応するためのエンタープライズ ネットワークに役立つ手順が記載されています。 組織の脆弱性について十分な情報に基づいて評価し、どの展開パッケージと構成方法が最適かを判断します。

> [!NOTE]
> Microsoft Defender for Endpoint には、Microsoft ボリューム ライセンスが必要です。

### <a name="exchange-online-protection-setup-guide"></a>Exchange Online Protectionセットアップ ガイド

Microsoft Exchange Online Protection (EOP) は、スパムやマルウェアから保護するためのクラウドベースのメール フィルタリング サービスであり、メッセージング ポリシー違反から組織を保護する機能を備えています。

[Exchange Online Protection](https://aka.ms/EOPguidance) セットアップ ガイドを使用して、3 つの展開シナリオのオンプレミス メールボックス、ハイブリッド (オンプレミスとクラウドの組み合わせ)&mdash; メールボックス、またはすべてのクラウド メールボックスが組織に適したメールボックスを選択して EOP&mdash; を設定します。 このガイドでは、ユーザーのライセンスの設定と確認、Microsoft 365 管理センター でのアクセス許可の割り当て、セキュリティ & コンプライアンス センターでの組織のマルウェア対策ポリシーとスパム ポリシーの構成に関する情報とリソースを提供します。

### <a name="microsoft-defender-for-office-365-setup-guide"></a>Microsoft Defender for Office 365 のセットアップ ガイド

[Microsoft Defender for Office 365 セットアップ](https://aka.ms/oatpsetup) ガイドは、電子メール メッセージ、リンク、およびサード パーティ製のコラボレーション ツールを通じて、環境が検出する可能性のある悪意のある脅威から組織を保護します。 このガイドでは、組織のニーズに合わせて計画を立てOffice 365 Defender の準備と識別に役立つリソースと情報を提供します。

### <a name="microsoft-defender-for-identity-setup-guide"></a>Microsoft Defender for Identity セットアップ ガイド

[Microsoft Defender for Identity セットアップ ガイド](https://aka.ms/DefenderforIdentitysetup)には、ユーザー ID を侵害する可能性のある高度な脅威を特定、検出、および調査するためのセキュリティ ソリューションセットアップ ガイダンスが提供されています。 これには、不審なユーザーアクティビティの検出や、組織に向けられた悪意のあるインサイダーアクションが含まれます。 Defender for Identity インスタンスを作成し、組織の Active Directory に接続し、センサー、アラート、通知を設定し、独自のポータルの基本設定を構成します。

### <a name="insider-risk-solutions-setup-guide"></a>Insider リスク ソリューションのセットアップ ガイド

[Insider リスク ソリューションのセットアップ ガイドは](https://aka.ms/Insiderrisksetup)、組織を特定するのが困難で、軽減が困難なインサイダー リスクから組織を保護するのに役立ちます。 インサイダーリスクは、さまざまな分野で発生し、知的財産の喪失から職場での嫌がらせなど、組織にとって大きな問題を引き起こす可能性があります。

このガイドのソリューションは、組織全体からのネイティブシグナルやエンリッチメントとのユーザー アクティビティ、アクション、コミュニケーションを可視化するのに役立ちます。

* コミュニケーション コンプライアンス ソリューションを使用すると、職場での暴力、インサイダー取引、ハラスメント、行動規範、規制コンプライアンス違反など、コミュニケーション リスクを特定し、行動できます。
* インサイダー リスク管理ソリューションは、知的財産の盗難、機密性の高いデータ漏洩、セキュリティ違反、データ流出、機密性の侵害に対するリスクを特定、調査、および実行するのに役立ちます。

### <a name="microsoft-information-protection-setup-guide"></a>Microsoft Information Protection セットアップ ガイド

機密情報が保護されたと確信できるよう、情報保護戦略に適用できる機能の概要を確認します。 機密情報を発見、分類、保護、および監視する 4 段階のライフサイクル アプローチを使用します。 [Microsoft の情報保護のセットアップ ガイド](https://aka.ms/mipsetupguide) には、これらの各段階を完了するためのガイダンスが記載されています。

### <a name="microsoft-information-governance-setup-guide"></a>Microsoft 情報ガバナンスのセットアップ ガイド

[Microsoft 情報ガバナンスの設定ガイド](https://aka.ms/migsetupguide)には、設定した特定のライフサイクルのガイドラインに従ってデータを分類および管理するため、組織のガバナンス戦略の設定と管理に必要な情報が提供されています。 このガイドでは、組織の再利用可能なコンテンツおよびコンプライアンス レコードに適用されるラベル、ラベル ポリシー、アイテム保持ポリシーを作成、自動適用、公開する方法について説明します。 また、一括処理のシナリオ、または個々のドキュメントに手動で適用するために、ファイル計画を使用した CSV ファイルのインポートに関する情報を入手できます。

### <a name="microsoft-defender-for-cloud-apps-setup-guide"></a>Microsoft Defender for Cloud Apps セットアップ ガイド

[Microsoft Defender for Cloud Apps セットアップ ガイドでは](https://aka.ms/cloudappsecuritysetup)、展開と管理のガイダンスに従ってクラウド探索ソリューションをセットアップできます。 Cloud Discovery を使用すると、サポートされているセキュリティ アプリを統合し、トラフィック ログを使用して組織が使用するクラウド アプリを動的に検出および分析します。 また、危険度の高い使用を識別するための脅威検出ポリシー、アクセスを定義する情報保護ポリシー、アクティビティを監視するためのリアルタイム セッション制御など、Defender for Cloud Apps ソリューションで利用できる機能を設定します。 これらの機能を使用すると、環境の可視性が強化され、データの移動を制御し、分析を行って、Microsoft およびサード パーティのクラウド サービス全体でサイバー脅威を特定して対処できます。

## <a name="guides-for-collaboration"></a>コラボレーションのガイド

### <a name="build-your-employee-experience"></a>従業員エクスペリエンスの構築

従業員が従業員エクスペリエンス ダッシュボードと一緒に [作業する方法を変革します](https://aka.ms/EmployeeExperienceDashboard)。 シームレスなチームワークを実現するには、Microsoft 365を使用して生産性の高いチームを作成し、従業員がリーダーシップと組織の残りの部分に従事し続ける必要があります。 すべての作業活動で従業員が効果的に働く。 これらのガイドでは、SharePoint、Teams、Yammerを使用して組織全体のコラボレーションを構築して生産性を向上させる方法について説明します。

### <a name="microsoft-365-apps-setup-guide"></a>Microsoft 365 Appsセットアップ ガイド

この[Microsoft 365 Appsセットアップ](https://aka.ms/OPPquickstartguide) ガイドは、Word、Excel、PowerPoint、および OneNote など、最新バージョンの Office 製品を実行しているユーザーのデバイスを取得するのに役立ちます。 管理ツールを使用してエンタープライズ展開に対する簡単な自己インストール オプションを含むさまざまな展開方法に関するガイダンスを取得します。 この手順ではユーザーの環境評価、特定の展開要件の把握、必要なサポート ツールの実装を行うことができ、インストールを正常に完了できます。

### <a name="mobile-apps-setup-guide"></a>モバイル アプリのセットアップ ガイド

モバイル [アプリのセットアップ ガイドでは](https://aka.ms/officeappguidance)、Office、iOS、および Android モバイル デバイス上の Windowsアプリのダウンロードとインストールの手順について説明します。 このガイドでは、スマートフォンやタブレット デバイスにアプリをダウンロードしてインストールMicrosoft 365 Office 365詳細な情報を提供します。

### <a name="microsoft-teams-setup-guide"></a>Microsoft Teamsセットアップ ガイド

[Microsoft Teamsセットアップ](https://aka.ms/teamsguidance) ガイドでは、メッセージング、通話、およびチームとプライベートコミュニケーションの両方の音声会議またはビデオ会議を通じてリアルタイムの会話をホストするチーム ワークスペースをセットアップするガイダンスを組織に提供します。 このガイドのツールを使用して、PowerShell セッションを開く必要なく、ゲスト アクセスを構成し、チームを作成できるユーザーを設定し、.csv ファイルからチーム メンバーを追加します。 また、組織のネットワーク要件を決定し、組織のネットワーク展開を成功にTeamsします。

### <a name="sharepoint-setup-guide"></a>SharePointセットアップ ガイド

[SharePoint セットアップ ガイド](https://aka.ms/spoguidance)を使用して、SharePoint ドキュメント ストレージとコンテンツ管理のセットアップ、サイトの作成、外部共有の構成、データの移行と詳細設定の構成、および組織内でのユーザー エンゲージメントとコミュニケーションを促進することができます。 コンテンツ共有アクセス許可ポリシーを構成し、移行同期ツールを選択し、移行環境のセキュリティ設定を有効にする手順にSharePointします。

### <a name="onedrive-setup-guide"></a>OneDriveセットアップ ガイド

ファイル ストレージ[OneDrive共有、](https://aka.ms/ODfBquickstartguide)コラボレーション、同期機能OneDriveを開始するには、次のセットアップ ガイドを使用します。 OneDriveは、ユーザーが Microsoft 365 Apps ファイルを同期し、外部共有を構成し、ユーザー データを移行し、高度なセキュリティとデバイス アクセス設定を構成できる中央の場所を提供します。 このOneDriveのセットアップ ガイドは、サブスクリプションまたはスタンドアロン OneDriveプランを使用してOneDriveできます。

### <a name="yammer-deployment-advisor"></a>Yammer展開アドバイザー

Connectを使用して組織全体をYammer。 この[Yammer展開](https://aka.ms/yammerdeploymentguide)アドバイザーは、ドメインYammer、管理者の定義、およびネットワークの組み合わせによって、Yammerを準備します。 ユーザー設定を展開し、外観Yammer、セキュリティとコンプライアンスを構成し、設定を絞り込むガイダンスを取得します。

## <a name="advanced-guides"></a>高度なガイド

### <a name="in-place-upgrade-with-configuration-manager"></a>Configuration Manager を使用した一時アップグレード

Windows 7 と Windows 8.1 デバイスを最新バージョンの Windows 10 にアップグレードする場合は、[Configuration Manager を使用した一括アップグレードに関するガイド](https://aka.ms/win10upgradedemo)を使用します。 必要条件を確認して一括アップグレードを自動的に構成するために提供されるスクリプトを使用します。

### <a name="deploy-office-to-your-users"></a>Office をユーザーに展開する

Office 展開ツールを使用して、インストールをカスタマイズできる機能を備えた Office アプリをクラウドから展開します。 [[ユーザーにOffice](https://aka.ms/proplusodt)を展開する] ガイドでは、高度な設定を使用してカスタマイズOffice構成を作成したり、事前に構築された推奨構成を使用できます。 ユーザーが自己インストールを行う場合でも、ユーザーに対して個別または一括で展開する場合でも、この高度なガイドでは、組織に合わせてカスタマイズされた Office インストールをユーザーに提供する手順を詳細に説明します。

### <a name="deploy-office-to-remote-users"></a>リモート ユーザーに Office を展開する

リモートでの作業が標準になったので、ユーザーが内部ネットワークに接続されていない場合や、自分のデバイスを使用している場合は、組織の Office 設定を受け取る必要があります。

[リモート ユーザー[にOffice](https://aka.ms/officeremoteinstall)を展開する] ガイドを使用して、カスタマイズされた Office インストールを作成し、構成に合わせてユーザーをシームレスにインストールする生成された PowerShell スクリプトOffice送信します。

### <a name="deploy-and-update-microsoft-365-apps-with-configuration-manager"></a>Configuration Manager を使用してMicrosoft 365 Appsを展開および更新する

Configuration Manager を使用している組織では、「[Configuration Manager アドバイザーを使用して、Microsoft 365 Apps の展開と更新を行う](https://aka.ms/oppinstall)」に沿って、FastTrack エンジニアが推奨するベスト プラクティスを使用して、Microsoft 365 Apps の展開を自動的に構成するスクリプトを生成することができます。 このガイドを使用して、展開グループを作成し、Office のアプリと機能をカスタマイズし、動的またはリーン インストールを構成します。その後、スクリプトを実行して、展開を対象にする必要があるアプリケーション、自動展開ルール、デバイス コレクションを作成します。

### <a name="intune-configuration-manager-co-management-setup-guide"></a>Intune Configuration Manager の共同管理セットアップ ガイド

[Intune Configuration Manager](https://aka.ms/comanagementsetup) 共同管理セットアップ ガイドを使用して、組織が Microsoft Intune と Configuration Manager の両方と共同管理する既存の Configuration Manager クライアント デバイスと新しいインターネット ベースのデバイスをセットアップします。 共同管理を使用すると、Windows 10デバイスを管理し、組織のデバイスに新しい機能を追加しながら、両方のソリューションのメリットを受けることができます。
