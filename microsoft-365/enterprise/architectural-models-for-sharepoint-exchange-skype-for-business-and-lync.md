---
title: SharePoint、Exchange、Skype for Business、Lync のアーキテクチャ モデル
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/16/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- SPO_Content
f1.keywords:
- CSH
ms.custom:
- Ent_Architecture
ms.assetid: 5b49fa68-f8f2-4705-af96-5f5475e8539a
search.appverid:
- MET150
description: SharePoint、Exchange、Skype for Business、Lync のアーキテクチャモデル、展開、およびプラットフォームのオプションについて説明している IT ポスターを取得します。
ms.openlocfilehash: 6d5cda89fb67f5c41dcf161abe7258c4600ee8ce
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/05/2020
ms.locfileid: "48919822"
---
# <a name="architectural-models-for-sharepoint-exchange-skype-for-business-and-lync"></a>SharePoint、Exchange、Skype for Business、Lync のアーキテクチャ モデル

この記事の IT ポスターでは、SharePoint、Exchange、Skype for Business、Lync のアーキテクチャモデルと展開オプションについて説明しています。 また、Microsoft Azure に SharePoint を展開するための設計情報も提供します。
  
Microsoft 365 を使用すると、クラウドを通じて、一般的なコラボレーションとコミュニケーションサービスを提供できます。 いくつかの例外を除き、オンプレミスの展開を維持している場合も、Microsoft 365 を使用している場合も、ユーザーの利便性は変わりません。 

この統合されたユーザーの環境では、それぞれのワークロードをどこに配置するかが決定されます。 また、次の質問も発生します。
  
- 個々のワークロードのプラットフォームを選択するには、どうすればよいですか?
    
- オンプレミスのサービスを残すことに意味はあるか。
    
- ハイブリッド展開の適切なシナリオは何ですか。
    
- Azure が画像にどのように適合するか
    
- Azure がサポートしている Office server ワークロードの構成
    
> [!TIP]
> この記事のほとんどのポスターは、複数の言語で提供されています。 利用可能な言語には、中国語、英語、フランス語、ドイツ語、イタリア語、日本語、韓国語、ポルトガル語、ロシア語、スペイン語があります。 これらの言語のいずれかでポスターをダウンロードするには、ポスターのサムネイル画像の下で、[ **その他の言語** ] を選択します。
  
ご意見をお知らせください。 [Cloudadopt@microsoft.com](mailto:cloudadopt@microsoft.com)で電子メールを送信します。 
  
必要なポスターを取得するには、次のリンクを使用します。
  
- **アーキテクチャモデル** : これらのリソースを使用して、SharePoint 2016 と Skype for business 2015 の理想的なプラットフォームと構成を決定します。
    
  - [Microsoft SharePoint 2016 アーキテクチャモデル](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#SP2016_ArchModel)
    
  - [SharePoint Server 2016 データベース](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#SP2016_Databases)
    
  - [Microsoft Skype for Business 2015 アーキテクチャモデル](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#SfB2015_ArchModel)
    
- **プラットフォーム** : これらのリソースを使用して、SharePoint 2013、Exchange 2013、Lync 2013 の理想的なプラットフォームと構成を決定します。
    
  - [SharePoint 2013 プラットフォームオプション](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#SP2013_Options)
    
  - [Exchange 2013 プラットフォームオプション](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#Exch2013_options)
    
  - [Lync 2013 プラットフォームオプション](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#Lync2013_Options)
    
- **Azure の Sharepoint server 2013** : これらの IT ポスターを使用して、azure インフラストラクチャサービスの sharepoint server 2013 ワークロードを設計および構成します。
    
  - [SharePoint Server 2013 を使用した Azure のインターネットサイト](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#Azure_sharepoint2013)
    
  - [設計サンプル: SharePoint 2013 用の Azure のインターネットサイト](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#DesignSampleInternetSites)
    
  - [Azure に対する SharePoint の障害復旧](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#sharepoint_recovery_Azure)
    
## <a name="architectural-models-posters"></a>アーキテクチャ モデルのポスター

SharePoint 2016 および Skype for Business 2015 の IT ポスターは、展開方法を簡単に印刷形式で比較する方法を提供します。 [ポスター] の一覧には、すべての構成オプションまたはプラットフォームオプションが表示されます。 各オプションには、次の情報が提供されます。
  
- **概要** : 概念図を含む、プラットフォームの簡単な概要。
    
- **ベスト** : プラットフォームに最適な一般的なシナリオ。
    
- **ライセンス要件** : 展開に必要なライセンス。
    
- **アーキテクチャタスク** : アーキテクトとして行う必要のある決定。
    
- It 担当者の **タスクまたは責任** : it スタッフが計画する必要がある日常業務。
    
<a name="SP2016_ArchModel"> </a>
### <a name="microsoft-sharepoint-server-2016-architectural-models"></a>Microsoft SharePoint Server 2016 のアーキテクチャ モデル

|アイテム|説明|
|---|---|
|[![SharePoint Server 2016 アーキテクチャモデルポスターのサムネイル。](../media/7d3e590c-1f3b-42cf-920d-9edac8fa3e04.png)          ](https://www.microsoft.com/download/details.aspx?id=52650) <br/> [PDF](https://download.microsoft.com/download/4/F/A/4FA0F94B-EE2F-41DB-A047-D9864FEF41E9/SharePoint2016ArchitecturalModels.pdf)  \| [Visio](https://download.microsoft.com/download/4/F/A/4FA0F94B-EE2F-41DB-A047-D9864FEF41E9/SharePoint2016ArchitecturalModels.vsdx)  \| [その他の言語](https://www.microsoft.com/download/details.aspx?id=52650)|この IT ポスターでは、ビジネスの意思決定者とソリューション設計担当者が知っておく必要のある SharePoint Online、Azure、および SharePoint のオンプレミスの構成について説明します。 <br/><br/> - **Sharepoint Online (saas)** : サービスとしてのソフトウェア (saas) サブスクリプションモデルを使用して sharepoint を使用します。 <br/> - **Sharepoint ハイブリッド** : 自分のペースで sharepoint サイトとアプリをクラウドに移行します。 <br/> - **Azure の SharePoint (IaaS)** : オンプレミス環境を azure に拡張し、sharepoint 2016 サーバーを展開します。 (高可用性または障害復旧環境、および開発/テスト環境では、このモデルをお勧めします)。 <br/> - **Sharepoint オンプレミス** : 管理するデータセンターで sharepoint 環境を計画、展開、保守、およびカスタマイズします。|
   
<a name="SP2016_Databases"> </a>
### <a name="sharepoint-server-2016-databases"></a>SharePoint Server 2016 Database

|アイテム|説明|
|---|---|
|[![SharePoint Server 2016 データベースのポスターのサムネイル。](../media/c53e9de7-3bf8-446d-8766-e6700c8dd8e1.png)](https://www.microsoft.com/download/details.aspx?id=55041) <br/> [PDF](https://download.microsoft.com/download/D/5/D/D5DC1121-8BC5-4953-834F-1B5BB03EB691/DBrefguideSPS2016_tabloid.pdf)  \| [Visio](https://download.microsoft.com/download/D/5/D/D5DC1121-8BC5-4953-834F-1B5BB03EB691/DBrefguideSPS2016_tabloid.vsdx)  \| [その他の言語](https://www.microsoft.com/download/details.aspx?id=55041)|この IT ポスターは、SharePoint Server 2016 データベースのクイックリファレンスです。 各データベースの詳細については、以下を参照してください。 <br/><br/> - サイズ <br/> - 拡大縮小のガイド <br/> - I/O パターン <br/> - 要件 <br/><br/>  最初のページには、SharePoint システムデータベースと、複数のデータベースを持つサービスアプリケーションが表示されます。 2 番目のページには、1 つのデータベースを持つサービス アプリケーションのすべてが表示されます。 <br/><br/>  詳細については、「 [データベースの種類と説明 (SharePoint Server 2016](https://docs.microsoft.com/SharePoint/technical-reference/database-types-and-descriptions))」を参照してください。|
   
<a name="SfB2015_ArchModel"> </a>
### <a name="microsoft-skype-for-business-2015-architectural-models"></a>Microsoft Skype for Business 2015 のアーキテクチャ モデル

|アイテム|説明|
|---|---|
|[![Skype for Business アーキテクチャモデルポスターのサムネイル。](../media/132288c0-6ae4-4394-88ab-b57dae367714.png)](https://www.microsoft.com/download/details.aspx?id=55022) <br/> [PDF](https://download.microsoft.com/download/7/7/4/7741262C-A60D-41F7-863B-99BF5964FBFE/Skype%20for%20Business%20Architectural%20Models.pdf)  \| [Visio](https://download.microsoft.com/download/7/7/4/7741262C-A60D-41F7-863B-99BF5964FBFE/Skype%20for%20Business%20Architectural%20Models.vsd)  \| [その他の言語](https://www.microsoft.com/download/details.aspx?id=55022)|このポスターでは、Skype for Business Online、オンプレミス、ハイブリッド、およびクラウド構内交換 (PBX) について説明します。 また、ビジネスの意思決定者とソリューション設計担当者が知っておく必要のある Exchange と SharePoint の構成との統合についても説明します。 <br/><br/> このポスターは、IT 担当者が、オンプレミスの Skype for business Online と Skype for business を使用することによって、基本的なアーキテクチャモデルを認識することを目的としています。 <br/><br/>組織のニーズと計画に最適な構成を開始します。 必要に応じて他の構成を検討し、使用します。 たとえば、Exchange と SharePoint との統合、または Microsoft クラウド PBX オファーリングを活用するソリューションについて検討したいと考えている場合があります。|
   
## <a name="platform-options-posters"></a>プラットフォーム オプションのポスター

SharePoint 2013、Exchange 2013、Lync 2013 の IT ポスターは、展開方法を一目で比較できるようになります。 各ポスターには、すべての構成またはプラットフォームオプションが一覧表示されます。 各オプションに関する次の情報が提供されます。
  
- **概要** : 概念図を含む、プラットフォームの簡単な概要。
    
- **ベスト** : プラットフォームに最適な一般的なシナリオ。
    
- **ライセンス要件** : 展開に必要なライセンス。
    
- **アーキテクチャタスク** : アーキテクトとして行う必要のある決定。
    
- It 担当者の **タスクまたは責任** : it スタッフが計画する必要がある日常業務。
    
<a name="SP2013_Options"> </a>
## <a name="sharepoint-2013-platform-options"></a>SharePoint 2013 プラットフォーム オプション

|アイテム|説明|
|---|---|
|[![SharePoint 2013 プラットフォームオプションポスターのサムネイル画像。](../media/SP-PlatformOptions.jpg)](https://www.microsoft.com/download/details.aspx?id=40332) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkId=324594)  \| [Visio](https://go.microsoft.com/fwlink/p/?LinkId=324593)  \| [その他の言語](https://www.microsoft.com/download/details.aspx?id=40332)|ビジネス意思決定者およびアーキテクトにとって、このポスターは、microsoft 365、Azure、およびオンプレミスの展開を使用したオンプレミスハイブリッドの SharePoint 2013 の sharepoint 365 のプラットフォームオプションを示しています。 各アーキテクチャ、推奨事項、ライセンス要件、および各プラットフォームのアーキテクトおよび IT 担当者向けタスクの概要を示しています。 ポスターには、Azure のいくつかの SharePoint ソリューションが強調表示されています。|
   
<a name="Exch2013_options"> </a>
## <a name="exchange-2013-platform-options"></a>Exchange 2013 プラットフォーム オプション

|アイテム|説明|
|---|---|
|[![Exchange プラットフォームオプションポスターのサムネイルイメージ。](../media/ITPro-Other-Exchange2013PlatformOptions.jpg)          ](https://www.microsoft.com/download/details.aspx?id=42676) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkID=398740)  \| [Visio](https://go.microsoft.com/fwlink/p/?LinkID=398742)  \| [その他の言語](https://www.microsoft.com/download/details.aspx?id=42676)|ビジネス意思決定者およびアーキテクトにとって、このポスターでは Exchange 2013 のプラットフォームオプションについて説明します。 お客様は、Microsoft 365、ハイブリッド Exchange、オンプレミス、およびホストされた Exchange を使用して、Exchange Online から選択できます。 ポスターには、それぞれのアーキテクチャオプション、ライセンス要件、および IT 担当者の責任についての詳細が含まれています。|
   
<a name="Lync2013_Options"> </a>
## <a name="lync-2013-platform-options"></a>Lync 2013 プラットフォーム オプション

|アイテム|説明|
|---|---|
|[![Lync 2013 プラットフォームオプションポスターのサムネイルイメージ。](../media/Lync-PlatformOptions.jpg)          ](https://www.microsoft.com/download/details.aspx?id=41677) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkID=391837)  \| [Visio](https://go.microsoft.com/fwlink/p/?LinkID=391839)  \| [その他の言語](https://www.microsoft.com/download/details.aspx?id=41677)|ビジネス意思決定者およびアーキテクトにとって、このポスターでは Lync 2013 のプラットフォームオプションについて説明します。 お客様は、Microsoft 365、ハイブリッド Lync、Lync Server オンプレミス、およびホストされている Lync で Lync Online から選択できます。 IT ポスターには、各アーキテクチャオプションの詳細が含まれています。これには、それぞれの理想的なシナリオ、ライセンス要件、および IT 担当者の責任があります。|
   
<a name="Lync2013_Options"> </a>
## <a name="sharepoint-in-azure-solutions-posters"></a>Azure の SharePoint のソリューションのポスター

Azure の SharePoint 用の IT ポスターは、SharePoint Server 2013 を使用する Azure ベースのソリューションを示しています。
  
<a name="Azure_sharepoint2013"> </a>
### <a name="internet-sites-in-microsoft-azure-using-sharepoint-server-2013"></a>SharePoint Server 2013 を使用した Microsoft Azure のインターネットサイト

|アイテム|説明|
|---|---|
|[![SharePoint Server 2013 ポスターを使用した Azure のインターネットサイトのイメージ。](../media/MS-AZ-SPInternetSites.jpg)          ](https://www.microsoft.com/download/details.aspx?id=41992) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkId=392552)  \| [Visio](https://go.microsoft.com/fwlink/p/?LinkId=392551)  \| [その他の言語](https://www.microsoft.com/download/details.aspx?id=41992)|このポスターは、Azure でのインターネットに接続されたサイトの主要な設計作業と推奨されるアーキテクチャについて概説します。  <br/><br/> 詳細については、次の記事を参照してください。  <br/><br/> - [SharePoint Server 2013 を使用した Azure のインターネットサイト](internet-sites-in-microsoft-azure-using-sharepoint-server-2013.md) <br/> - [SharePoint 用 Azure アーキテクチャ2013](microsoft-azure-architectures-for-sharepoint-2013.md)|
   
<a name="DesignSampleInternetSites"> </a>
### <a name="internet-sites-in-azure-for-sharepoint-2013"></a>SharePoint 用の Azure のインターネットサイト2013

|アイテム|説明|
|---|---|
|[![Microsoft Azure for SharePoint Server 2013 ポスターのインターネットサイトのイメージ。](../media/MS-AZ-InternetSitesDesignSample.jpg)          ](https://www.microsoft.com/download/details.aspx?id=41991) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkId=392549)  \| [Visio](https://go.microsoft.com/fwlink/p/?LinkId=392548)  \| [その他の言語](https://www.microsoft.com/download/details.aspx?id=41991)|この設計サンプルは、SharePoint Server 2013 を使用した Azure のインターネットに直接接続されたサイトの独自のアーキテクチャの開始点として使用します。 <br/><br/> 詳細については、次の記事を参照してください。  <br/><br/> - [SharePoint Server 2013 を使用した Azure のインターネットサイト](internet-sites-in-microsoft-azure-using-sharepoint-server-2013.md) <br/> - [SharePoint 用 Azure アーキテクチャ2013](microsoft-azure-architectures-for-sharepoint-2013.md)|
   
<a name="sharepoint_recovery_Azure"> </a>
### <a name="sharepoint-disaster-recovery-to-microsoft-azure"></a>Microsoft Azure に対する SharePoint の障害復旧

|アイテム|説明|
|---|---|
|[![Azure に対する SharePoint の障害復旧プロセスのポスターのイメージ。](../media/SP-DR-Azure.png)          ](https://www.microsoft.com/download/details.aspx?id=41993) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkId=392555)  \| [Visio](https://go.microsoft.com/fwlink/p/?LinkId=392554)  \| [その他の言語](https://www.microsoft.com/download/details.aspx?id=41993)|この IT ポスターは、Azure の障害復旧環境のためのアーキテクチャ原則を示しています。 <br/><br/> 詳細については、次の記事を参照してください。  <br/><br/> - [Azure での SharePoint Server 2013 の障害復旧](sharepoint-server-2013-disaster-recovery-in-microsoft-azure.md) <br/> - [SharePoint 用 Azure アーキテクチャ2013](microsoft-azure-architectures-for-sharepoint-2013.md)|
   
## <a name="see-also"></a>関連項目

- [Microsoft 365 ソリューションおよびアーキテクチャ センター](../solutions/solution-architecture-center.md)
  
- [Microsoft クラウド アーキテクチャ モデル](../solutions/cloud-architecture-models.md)
  
- [Microsoft 365 テストラボガイド](m365-enterprise-test-lab-guides.md)
  
- [ハイブリッド ソリューション](hybrid-solutions.md)

