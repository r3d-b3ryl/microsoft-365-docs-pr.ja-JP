---
title: Microsoft 365 および Office 365 サービスのセットアップ ガイド
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
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
description: セットアップ ガイドを使用して、Microsoft 365 または Office 365 の計画と構成を加速します。
ms.openlocfilehash: 6ad00819b172d7cb0cfb5b63a93c0910df5517e6
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2021
ms.locfileid: "50454149"
---
# <a name="setup-guides-for-microsoft-365-and-office-365-services"></a>Microsoft 365 および Office 365 サービスのセットアップ ガイド

Microsoft 365 および Office 365 セットアップ ガイドでは、テナント、アプリ、およびサービスを計画および展開するために、カスタマイズされたガイダンスとリソースを提供します。 これらのガイドは [、Microsoft 365 FastTrack](https://www.microsoft.com/fasttrack/microsoft-365) オンボーディング スペシャリストが個々のやり取りで共有するのと同じベスト プラクティスを使用して作成され、Microsoft 365 管理センター内のすべての管理者が利用できます。 製品のセットアップ、セキュリティ機能の有効化、コラボレーション ツールの展開に関する情報を提供し、高度な展開を高速化するためのスクリプトを提供します。

## <a name="how-to-access-setup-guides-in-the-microsoft-365-admin-center"></a>Microsoft 365 管理センターのセットアップ ガイドにアクセスする方法

セットアップ ガイドは、Microsoft 365 管理センターの [セットアップ ガイダンス] ページからアクセスできます。 [](https://aka.ms/setupguidance) 進捗状況を追跡し、ガイドを完了するためにいつでも戻るオプションがあります。 [セットアップ ガイダンス] **ページにアクセスするには、次の手順を実行** します。

1. Microsoft [365 管理センターで](https://admin.microsoft.com/)、[ホーム] ページに **移動** します。

2. トレーニング ガイド **カード&見** つける。 

   ![Microsoft 365 &センターでのトレーニング ガイド カード](../media/setup-guides-for-microsoft-365/adminportal-trainingandguides.png)

3. [カスタマイズ **されたセットアップ ガイダンス] を選択します**。

   ![Microsoft 365 管理センターの [セットアップ ガイダンス] ページのスクリーンショット](../media/setup-guides-for-microsoft-365/adminportal-setupguidance.png)

>[!NOTE]
>Microsoft 365 管理センターにアクセスするには、テナント管理者のアクセス許可が必要です。

## <a name="how-do-setup-guides-work-in-the-microsoft-365-admin-center"></a>セットアップ ガイドは、Microsoft 365 管理センターでどのように機能しますか?

各ガイドには、手順、リソース、記事、および必要に応じて構成変更に使用できるスクリプトが記載されています。 これらのガイドでは、小規模組織と大規模組織の両方の特定のニーズを反映した選択肢を提供します。 さらに、ガイダンスには、新しい管理者と経験豊富な管理者の両方のサポートが含まれています。

![セットアップ ガイドの例](../media/setup-guides-for-microsoft-365/m365-setupguide-example.png)

このガイドを使用して、計画フェーズ、展開およびロールアウト中に特定の Microsoft 365 および Office 365 機能の詳細を確認したり、展開を完了して設定を変更した後に再訪することができます。

## <a name="guides-for-initial-setup"></a>初期セットアップのガイド

### <a name="prepare-your-environment"></a>環境を準備する

「 [環境の準備」ガイド](https://aka.ms/prepareyourenvironment) は、Microsoft 365 および 365 サービス用に組織の環境Office役立ちます。 目的に関係なく、展開を正常に行うには、完了する必要があるタスクがあります。 環境の準備中にエラーが発生しないようにするには、ドメインの接続、ユーザーの追加、ライセンスの割り当て、Exchange Online による電子メールのセットアップ、Office アプリのインストールまたは展開を行う手順が記載されています。 

### <a name="email-setup-advisor"></a>電子メール セットアップ アドバイザー

電子 [メール セットアップ アドバイザーでは](https://aka.ms/office365setup) 、組織の Exchange Online の構成に必要な手順を説明します。 これには、新しいメール アカウントの設定、メールの移行、電子メール保護の構成が含まれます。 電子メールを正常にセットアップするには、このアドバイザーを使用して、組織の現在のメール システム、移行するメールボックスの数、およびユーザーとそのアクセスを管理する方法に基づいて、推奨される移行方法を受け取る必要があります。

### <a name="migrate-gmail-contacts-and-calendar-items"></a>Gmail の連絡先と予定表アイテムを移行する

Gmail ユーザーのメールボックスを Microsoft 365 に移行すると、電子メール メッセージは移行されますが、連絡先と予定表アイテムは移行されません。 Gmail の [連絡先と](https://aka.ms/gmailcontactscalendar) 予定表アドバイザーは、Outlook.com、Outlook クライアント、または PowerShell を使用してインポートおよびエクスポートの方法を使用して、Google 連絡先と Google 予定表アイテムを Microsoft 365 にインポートする手順を提供します。

### <a name="microsoft-365-deployment-advisor"></a>Microsoft 365 展開アドバイザー

[Microsoft 365 展開アドバイザーは](https://aka.ms/microsoft365setupguide)、生産性ツール、セキュリティ ポリシー、およびデバイス管理機能をセットアップする際のガイダンスを提供します。 Microsoft 365 Business Premium またはエンタープライズ サブスクリプション版 Microsoft 365 があれば、このアドバイザーを使用して組織のデバイスをセットアップし、構成できます。 

クラウド サービスを有効にし、デバイスを最新のサポートバージョンの Windows 10 に更新し、デバイスを Azure Active Directory (Azure AD) に参加するガイダンスとリソースへのアクセスを、すべて 1 つの中央の場所で受け取る予定です。


### <a name="remote-work-setup-guide"></a>リモート ワーク セットアップ ガイド

リモート [作業セットアップ ガイド](https://aka.ms/remoteworksetup) では、ユーザーがリモートで正常に作業し、データが安全で、ユーザーの資格情報を保護するために必要なヒントとリソースを組織に提供します。 

クラウド内の Microsoft 365 リソースと組織のネットワークの両方へのリモート ワーカーのデバイス トラフィックを最適化するためのガイダンスを受け取り、リモート アクセス VPN インフラストラクチャの負荷を軽減します。 

### <a name="windows-virtual-desktop-setup-guide"></a>Windows Virtual Desktop セットアップ ガイド

Windows Virtual Desktop は、クラウドで実行されている包括的なデスクトップおよびアプリの仮想化サービスです。 シンプルな管理、マルチセッション Windows 10、Microsoft 365 Apps の最適化、およびリモート デスクトップ サービス (RDS) 環境のサポートを提供する唯一の仮想デスクトップ インフラストラクチャ (VDI) です。 Azure に Windows デスクトップとアプリを数分で展開および拡張し、組み込みのセキュリティとコンプライアンス機能を利用できます。 

[Windows Virtual Desktop セットアップ ガイド](https://aka.ms/wvdsetupguide)は、管理者に計画リソースと、展開の前提条件、セットアップ ガイダンス、および追加リソースを提供します。 

### <a name="microsoft-edge-setup-guide"></a>Microsoft Edge セットアップ ガイド

Microsoft Edge は、世界クラスの互換性とパフォーマンス、セキュリティとプライバシー、Web の最高の機能を提供するように設計された新機能を提供するために、一から再構築されました。

[Microsoft Edge](https://aka.ms/edgeadvisor)セットアップ ガイドは、組織でアクセスするサイトが IE モードを使用する必要がある場合を確認し、重要なセキュリティ機能を確認および構成し、組織の要件を満たしたプライバシー ポリシーと追加ポリシーを構成し、デバイス上の Web アクセスを管理するために、エンタープライズ サイト探索を構成するのに役立ちます。 Microsoft Edge を個々のデバイスにダウンロードするか、Configuration Manager または Microsoft Intune を使用して組織の複数のユーザーに展開する方法を説明します。 

### <a name="microsoft-search-setup-guide"></a>Microsoft Search セットアップ ガイド

Microsoft Search は、組織が作業している作業を完了するために必要な情報を見つけるのに役立ちます。 ユーザー、ファイル、組織のグラフ、サイト、または一般的な質問に対する回答を検索する場合でも、組織は仕事中 Microsoft Search を使用して回答を取得できます。

[Microsoft Search セットアップ ガイド](https://aka.ms/MicrosoftSearchSetup)を使用すると、Microsoft Search をユーザーグループにパイロットするか、組織のすべてのユーザーに展開するかの構成に役立ちます。検索管理者と検索エディターを割り当て、ユーザーの検索エクスペリエンスをカスタマイズし、回答や追加オプション (Chrome に Bing 拡張機能を追加する、Bing を既定の検索エンジンとして設定するなど) を使用します。

### <a name="intune-configuration-manager-co-management-setup-guide"></a>Intune Configuration Manager の共同管理セットアップ ガイド

組織が Microsoft Intune と Configuration Manager の両方と共同管理する必要がある既存の Configuration Manager クライアント デバイスと新しいインターネット ベースのデバイスについては [、Intune](https://aka.ms/comanagementsetup) Configuration Manager 共同管理セットアップ ガイドを使用します。 この共同管理展開ガイドでは、両方のソリューションの利点を受け取りながら、Windows 10 デバイスを管理し、組織のデバイスに新しい機能を追加できます。

## <a name="guides-for-authentication-and-access"></a>認証とアクセスのガイド

### <a name="azure-ad-setup-guide"></a>Azure ADセットアップ ガイド

[Azure AD セットアップ ガイド](https://aka.ms/aadpguidance)には、組織の強固なセキュリティ基盤を確保するための情報が記載されています。 このガイドでは、管理者向け Azure ロールベースのアクセス制御 (Azure RBAC)、オンプレミス ディレクトリ用の Azure AD Connect、Azure AD Connect Health など、初期機能を設定して、自動同期中にハイブリッド ID の正常性を監視できます。 

また、セルフサービス パスワードのリセット、条件付きアクセス、オプションの高度な ID 保護やユーザー プロビジョニングの自動化を含むサードパーティの統合サインオンの有効化に関する重要な情報も含まれています。

### <a name="sync-users-from-your-orgs-directory"></a>組織のディレクトリからユーザーを同期する

組織 [のディレクトリからユーザー](https://aka.ms/directorysyncsetup) を同期するウィザードでは、ディレクトリ同期を有効にする手順を示します。 これにより、オンプレミス ID とクラウド ID が一緒になり、アクセスが容易になり、管理が簡素化されます。 シングル サインオン、セルフサービス オプション、自動アカウント プロビジョニング、条件付きアクセス制御、コンプライアンス ポリシーなど、新しい機能のロックを解除します。 これにより、ユーザーはどこからでも必要なリソースにアクセスできます。

### <a name="plan-your-passwordless-deployment"></a>パスワードレス展開を計画する

次のいずれかのパスワードレス認証方法を使用して、ユーザーがデバイスに安全にアクセスできる別のサインイン 方法にアップグレードします。 

- Windows Hello for Business
- Microsoft Authenticator アプリ
- セキュリティ キー 

[パスワード [レス展開の計画] ウィザード](https://aka.ms/passwordlesssetup) を使用して、それらを展開する方法に関するガイダンスを使用して受け取る最適なパスワードレス認証方法を検出します。 

### <a name="plan-your-self-service-password-reset-sspr-deployment"></a>セルフサービス パスワード リセット (SSPR) の展開を計画する

ユーザーが自分のアカウントがロックされている場合、またはヘルプデスク のエンジニアに問い合わせることなくパスワードを忘れた場合は、ユーザーが自分のパスワードを個別に変更またはリセットできます。 

環境での[](https://aka.ms/SSPRSetupGuide) SSPR の展開に役立つ適切な Azure Portal オプションを構成するための関連記事と手順を受け取る場合は、「セルフサービスパスワードリセット展開の計画」ウィザードを使用します。

### <a name="active-directory-federation-services-ad-fs-deployment-advisor"></a>Active Directory フェデレーション サービス (AD FS) 展開アドバイザー

[AD FS 展開アドバイザー](https://aka.ms/adfsguidance)は、Microsoft 365 および Office 365 サービスのユーザーを認証するオンプレミス AD FS インフラストラクチャの展開に関する段階的なガイダンスを提供します。 このガイドを使用すると、組織は AD FS コンポーネントと要件を確認し、展開に必要な SSL 証明書を取得してインストールし、必要な Web アプリケーション プロキシ サーバーをインストールできます。 

## <a name="guides-for-security-and-compliance"></a>セキュリティとコンプライアンスのガイド

### <a name="microsoft-intune-setup-guide"></a>Microsoft Intune セットアップ ガイド 

組織内のデバイスを管理するために Microsoft Intune を設定します。 企業のデバイスを完全に制御するには、Intune のモバイル デバイス管理 (MDM) 機能を使用します。 共有デバイスと個人用デバイスで組織のデータを管理するには、Intune のモバイル アプリケーション管理 (MAM) 機能を使用できます。 

Microsoft [Intune セットアップ](https://aka.ms/intunesetupguide)ガイドでは、デバイスとアプリのコンプライアンス ポリシーを設定し、アプリ保護ポリシーを割り当て、デバイスとアプリ保護の状態を監視します。 

### <a name="microsoft-defender-for-endpoint-advisor"></a>エンドポイント アドバイザー用 Microsoft Defender

[Microsoft Defender for Endpoint アドバイザー](https://aka.ms/mdatpsetup)は、エンタープライズ ネットワークが高度な脅威を防止、検出、調査、および対応するのに役立つ手順を提供します。 組織の脆弱性について十分な情報に基づいて評価し、どの展開パッケージと構成方法が最適かを判断します。 

>[!NOTE]
>Microsoft Defender for Endpoint には、Microsoft ボリューム ライセンスが必要です。

### <a name="exchange-online-protection-setup-guide"></a>Exchange Online Protection セットアップ ガイド

Microsoft Exchange Online Protection (EOP) は、スパムやマルウェアから保護するためのクラウドベースのメール フィルタリング サービスであり、メッセージング ポリシー違反から組織を保護する機能を備えています。 

Exchange [Online Protection](https://aka.ms/EOPguidance)セットアップ ガイドを使用して、オンプレミスメールボックス、ハイブリッド (オンプレミスとクラウドの混在) メールボックス、またはすべてのクラウド メールボックスが組織に適合する 3 つの展開シナリオの中から選択して EOP を設定します。 &mdash; &mdash; このガイドでは、ユーザーのライセンスの設定と確認、Microsoft 365 管理センターでのアクセス許可の割り当て、セキュリティ & コンプライアンス センターでの組織のマルウェア対策ポリシーとスパム ポリシーの構成に関する情報とリソースを提供します。 

### <a name="microsoft-defender-for-office-365-advisor"></a>Microsoft Defender for Office 365 アドバイザー

[Microsoft Defender for Office 365](https://aka.ms/oatpsetup)アドバイザーは、電子メール メッセージ、リンク、およびサード パーティ製のコラボレーション ツールを通じて、環境が発生する可能性のある悪意のある脅威から組織を保護します。 このガイドでは、組織のニーズに合わせて、Office 365 プランの Defender の準備と識別に役立つリソースと情報を提供します。 

### <a name="microsoft-information-protection-setup-guide"></a>Microsoft 情報保護セットアップ ガイド

機密情報が保護されたと確信できるよう、情報保護戦略に適用できる機能の概要を確認します。 機密情報を発見、分類、保護、および監視する 4 段階のライフサイクル アプローチを使用します。 [Microsoft 情報保護セットアップ ガイドでは、](https://aka.ms/mipsetupguide)これらの各ステージを完了するためのガイダンスを提供します。

### <a name="microsoft-information-governance-setup-guide"></a>Microsoft 情報ガバナンスのセットアップ ガイド

[Microsoft 情報ガバナンスの設定ガイド](https://aka.ms/migsetupguide)には、設定した特定のライフサイクルのガイドラインに従ってデータを分類および管理するため、組織のガバナンス戦略の設定と管理に必要な情報が提供されています。 このガイドでは、組織の再利用可能なコンテンツおよびコンプライアンス レコードに適用されるラベル、ラベル ポリシー、アイテム保持ポリシーを作成、自動適用、公開する方法について説明します。 また、一括処理のシナリオ、または個々のドキュメントに手動で適用するために、ファイル計画を使用した CSV ファイルのインポートに関する情報を入手できます。 

## <a name="guides-for-collaboration"></a>コラボレーションのガイド

### <a name="microsoft-365-apps-deployment-advisor"></a>Microsoft 365 Apps 展開アドバイザー

[Microsoft 365 Apps](https://aka.ms/OPPquickstartguide)展開アドバイザーは、Word、Excel、PowerPoint、OneNote など、Office 製品の最新バージョンを実行しているユーザーのデバイスを取得するのに役立ちます。 管理ツールを使用してエンタープライズ展開に対する簡単な自己インストール オプションを含むさまざまな展開方法に関するガイダンスを取得します。 この手順は、環境を評価し、特定の展開要件を把握し、インストールを成功するために必要なサポート ツールを実装するのに役立ちます。 

### <a name="mobile-apps-setup-guide"></a>モバイル アプリのセットアップ ガイド

モバイル [アプリのセットアップ ガイドでは](https://aka.ms/officeappguidance) 、Windows、iOS、および Android モバイル デバイスOfficeアプリのダウンロードとインストールの手順について説明します。 このガイドでは、Microsoft 365 および Office 365 アプリを携帯電話およびタブレット デバイスにダウンロードしてインストールする手順に従って説明します。

### <a name="microsoft-teams-setup-guide"></a>Microsoft Teams セットアップ ガイド

[Microsoft Teams セットアップ](https://aka.ms/teamsguidance)ガイドでは、メッセージング、通話、およびチームとプライベートの両方の通信のための音声会議またはビデオ会議を通じてリアルタイムの会話をホストするチーム ワークスペースをセットアップするガイダンスを組織に提供します。 組織のネットワーク要件を決定する手順については、ネットワーク プランナー ツールと Teams 管理センター内の Teams アドバイザーを使用して受け取る必要があります。 展開が完了した後も、ガイドには Teams の使用開始に役立つリソースが含まれています。

### <a name="sharepoint-setup-guide"></a>SharePoint セットアップ ガイド

[SharePoint セットアップ ガイド](https://aka.ms/spoguidance)を使用して、SharePoint ドキュメント ストレージとコンテンツ管理のセットアップ、サイトの作成、外部共有の構成、データの移行と詳細設定の構成、および組織内でのユーザー エンゲージメントとコミュニケーションを促進することができます。 コンテンツ共有アクセス許可ポリシーを構成する手順に従い、移行同期ツールを選択し、SharePoint 環境のセキュリティ設定を有効にします。 

### <a name="onedrive-setup-guide"></a>OneDrive セットアップ ガイド

[OneDrive のセットアップ ガイドを使用](https://aka.ms/ODfBquickstartguide)して、OneDrive ファイルストレージ、共有、コラボレーション、同期機能の使用を開始します。 OneDrive は、ユーザーが Microsoft 365 Apps ファイルを同期し、外部共有を構成し、ユーザー データを移行し、高度なセキュリティとデバイス アクセス設定を構成できる中央の場所を提供します。 OneDrive セットアップ ガイドは、OneDrive サブスクリプションまたはスタンドアロンの OneDrive プランを使用して展開できます。 

### <a name="yammer-deployment-advisor"></a>Yammer展開アドバイザー

組織全体に接続し、組織全体にYammer。 この [Yammer展開](https://aka.ms/yammerdeploymentguide) アドバイザーは、ドメインYammer、管理者の定義、およびネットワークの組み合わせによって、Yammerを準備します。 ユーザー設定を展開し、外観Yammer、セキュリティとコンプライアンスを構成し、設定を絞り込むガイダンスを取得します。

## <a name="advanced-wizards"></a>高度なウィザード

### <a name="in-place-upgrade-with-configuration-manager"></a>Configuration Manager を使用した一時アップグレード

Windows 7 と Windows 8.1 デバイスを最新バージョンの Windows 10 にアップグレードする場合は、[Configuration Manager を使用した一括アップグレードに関するガイド](https://aka.ms/win10upgradedemo)を使用します。 必要条件を確認して一括アップグレードを自動的に構成するために提供されるスクリプトを使用します。

### <a name="deploy-office-to-your-users"></a>ユーザー Officeに展開する

Office 展開ツールを使用して、インストールをカスタマイズできる機能を備えた Office アプリをクラウドから展開します。 [ [ユーザーにOffice ](https://aka.ms/proplusodt) を展開する] ガイドでは、高度な設定を使用してカスタマイズOffice構成を作成したり、事前に構築された推奨構成を使用できます。 ユーザーがセルフ インストールを実行している場合でも、お客様がユーザーに個別または一括で展開している場合でも、この詳細設定ウィザードは、組織に合わせた Office インストールをユーザーに提供するための詳しい手順を提供します。

### <a name="deploy-office-to-remote-users"></a>リモート Officeに展開する

リモートでの作業が標準になったので、ユーザーは内部ネットワークに接続されていない場合や、自分のデバイスを使用する場合に、組織の Office 設定を受け取る必要があります。 

[リモート ユーザー [にOffice](https://aka.ms/officeremoteinstall) を展開する] ガイドを使用して、カスタマイズされた Office インストールを作成し、構成に合わせてユーザーをシームレスにインストールする生成された PowerShell スクリプトOffice送信します。

### <a name="deploy-and-update-microsoft-365-apps-with-configuration-manager"></a>Configuration Manager を使用して Microsoft 365 Apps を展開および更新する

Configuration Manager を使用している組織では、「[Configuration Manager アドバイザーを使用して、Microsoft 365 Apps の展開と更新を行う](https://aka.ms/oppinstall)」に沿って、FastTrack エンジニアが推奨するベスト プラクティスを使用して、Microsoft 365 Apps の展開を自動的に構成するスクリプトを生成することができます。 このガイドを使用して、展開グループを作成し、Office のアプリと機能をカスタマイズし、動的またはリーン インストールを構成します。その後、スクリプトを実行して、展開を対象にする必要があるアプリケーション、自動展開ルール、デバイス コレクションを作成します。 

### <a name="integrate-a-third-party-cloud-app-with-azure-ad"></a>サードパーティのクラウド アプリを Azure アプリと統合AD

Improve the user experience and provide an additional layer of security by integrating your third-party app with ‎Azure Active Directory (Azure AD). このエンドツーエンドのエクスペリエンスを使用すると、このウィザードから直接ほとんどの構成を実行できます。 必要に応じて、対応する構成ページにリダイレクトします。

サード パーティ [製クラウド アプリの統合ウィザードを使用](https://admin.microsoft.com/Adminportal/Home?#/azureadappintegration) して、サードパーティのクラウド アプリを Azure クラウド アプリと統合AD。
