---
title: SharePoint、Exchange、Skype for Business、Lync のアーキテクチャ モデル
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 05/16/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-solutions
ms.localizationpriority: medium
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
description: SharePoint、Exchange、Skype for Business、Lync のアーキテクチャ モデル、デプロイ、およびプラットフォーム オプションを説明する IT ポスターを入手します。
ms.openlocfilehash: 859d952fc9a2e4e9315c7fef3e56b4e59d0f60d6
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65096878"
---
# <a name="architectural-models-for-sharepoint-exchange-skype-for-business-and-lync"></a>SharePoint、Exchange、Skype for Business、Lync のアーキテクチャ モデル

この記事の IT ポスターでは、SharePoint、Exchange、Skype for Business、Lync のアーキテクチャ モデルと展開オプションについて説明します。 また、Microsoft AzureにSharePointをデプロイするための設計情報も提供されます。
  
Microsoft 365を使用すると、クラウドを通じて使い慣れたコラボレーションサービスとコミュニケーション サービスを提供できます。 いくつかの例外を除き、ユーザー エクスペリエンスは、オンプレミスのデプロイを維持している場合でも、Microsoft 365を使用している場合でも変わりません。 

この統合されたユーザー エクスペリエンスにより、各ワークロードを配置する場所の決定が複雑になります。 また、次の質問も発生します。
  
- 個々のワークロードのプラットフォームを選択するにはどうすればよいですか?
    
- オンプレミスのサービスを残すことに意味はあるか。
    
- ハイブリッドデプロイはどのようなシナリオで適切ですか?
    
- Azure は画像にどのように適合しますか?
    
- Office サーバー ワークロードの構成はAzure サポート?
    
> [!TIP]
> この記事のほとんどのポスターは、複数の言語で使用できます。 利用可能な言語には、中国語、英語、フランス語、ドイツ語、イタリア語、日本語、韓国語、ポルトガル語、ロシア語、スペイン語が含まれます。 これらの言語のいずれかでポスターをダウンロードするには、ポスターサムネイル画像の下にある **[その他の言語**] を選択します。
  
ご意見を電子メールで [cloudadopt@microsoft.com](mailto:cloudadopt@microsoft.com) 宛てにお送りください。 
  
次のリンクを使用して、必要なポスターを取得します。
  
- **アーキテクチャ モデル**: これらのリソースを使用して、SharePoint 2016 および Skype for Business 2015 の理想的なプラットフォームと構成を決定します。
    
  - [Microsoft SharePoint 2016 アーキテクチャ モデル](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#SP2016_ArchModel)
    
  - [SharePoint Server 2016 データベース](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#SP2016_Databases)
    
  - [Microsoft Skype for Business 2015 アーキテクチャ モデル](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#SfB2015_ArchModel)
    
- **プラットフォーム**: これらのリソースを使用して、SharePoint 2013、Exchange 2013、Lync 2013 の理想的なプラットフォームと構成を決定します。
    
  - [SharePoint 2013 プラットフォーム オプション](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#SP2013_Options)
    
  - [Exchange 2013 プラットフォーム オプション](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#Exch2013_options)
    
  - [Lync 2013 プラットフォーム オプション](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#Lync2013_Options)
    
- **Azure SharePoint Server 2013**: これらの IT ポスターを使用して、Azure インフラストラクチャ サービスで SharePoint Server 2013 ワークロードを設計および構成します。
    
  - [SharePoint Server 2013 を使用した Azure のインターネット サイト](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#Azure_sharepoint2013)
    
  - [設計サンプル: SharePoint 2013 用 Azure のインターネット サイト](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#DesignSampleInternetSites)
    
  - [Azure へのディザスター リカバリーをSharePointする](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#sharepoint_recovery_Azure)
    
## <a name="architectural-models-posters"></a>アーキテクチャ モデルのポスター

SharePoint 2016 および Skype for Business 2015 の IT ポスターは、展開方法を印刷しやすい形式で比較する方法を提供します。 ポスターには、すべての構成オプションまたはプラットフォーム オプションが一覧表示されます。 オプションごとに次の情報が提供されます。
  
- **概要**: 概念図を含む、プラットフォームの簡単な概要。
    
- **最適な用途**: プラットフォームに最適な一般的なシナリオ。
    
- **ライセンス要件**: デプロイに必要なライセンス。
    
- **アーキテクチャ タスク**: アーキテクトとして行う必要がある決定。
    
- **IT 担当者のタスクまたは責任**: IT スタッフが計画する必要がある毎日の責任。
    
<a name="SP2016_ArchModel"> </a>
### <a name="microsoft-sharepoint-server-2016-architectural-models"></a>Microsoft SharePoint Server 2016 のアーキテクチャ モデル

|アイテム|説明|
|---|---|
|[![SharePoint Server 2016 アーキテクチャ モデルポスターのサムネイル。](../media/7d3e590c-1f3b-42cf-920d-9edac8fa3e04.png)          ](https://www.microsoft.com/download/details.aspx?id=52650) <br/> [PDF](https://download.microsoft.com/download/4/F/A/4FA0F94B-EE2F-41DB-A047-D9864FEF41E9/SharePoint2016ArchitecturalModels.pdf)  \| [Visio](https://download.microsoft.com/download/4/F/A/4FA0F94B-EE2F-41DB-A047-D9864FEF41E9/SharePoint2016ArchitecturalModels.vsdx)  \| [その他の言語](https://www.microsoft.com/download/details.aspx?id=52650)|この IT ポスターでは、ビジネス意思決定者やソリューションアーキテクトが知る必要がある、オンライン、Azure、SharePointのオンプレミス構成のSharePointについて説明します。 <br/><br/> - **SharePoint Online (SaaS)**: サービスとしてのソフトウェア (SaaS) サブスクリプション モデルを使用してSharePointを使用します。 <br/> - **SharePointハイブリッド**: SharePoint サイトとアプリを自分のペースでクラウドに移動します。 <br/> - **Azure (IaaS)のSharePoint**: オンプレミス環境を Azure に拡張し、2016 サーバー SharePointデプロイします。 (このモデルは、高可用性環境またはディザスター リカバリー環境および開発/テスト環境に推奨されます)。 <br/> - **オンプレミスSharePoint**: 管理するデータセンターでSharePoint環境を計画、デプロイ、保守、カスタマイズします。|
   
<a name="SP2016_Databases"> </a>
### <a name="sharepoint-server-2016-databases"></a>SharePoint Server 2016 Database

|アイテム|説明|
|---|---|
|[![SharePoint Server 2016 データベース ポスターのサムネイル。](../media/c53e9de7-3bf8-446d-8766-e6700c8dd8e1.png)](https://www.microsoft.com/download/details.aspx?id=55041) <br/> [PDF](https://download.microsoft.com/download/D/5/D/D5DC1121-8BC5-4953-834F-1B5BB03EB691/DBrefguideSPS2016_tabloid.pdf)  \| [Visio](https://download.microsoft.com/download/D/5/D/D5DC1121-8BC5-4953-834F-1B5BB03EB691/DBrefguideSPS2016_tabloid.vsdx)  \| [その他の言語](https://www.microsoft.com/download/details.aspx?id=55041)|この IT ポスターは、SharePoint Server 2016 データベースのクイック リファレンスです。 各データベースの詳細が表示されます。 <br/><br/> - サイズ <br/> - 拡大縮小のガイド <br/> - I/O パターン <br/> - 要件 <br/><br/>  最初のページには、SharePoint システム データベースと、複数のデータベースを持つサービス アプリケーションが表示されます。 2 番目のページには、1 つのデータベースを持つサービス アプリケーションのすべてが表示されます。 <br/><br/>  詳細については、「[SharePoint Server 2016 のデータベースの種類と説明」を参照してください](/SharePoint/technical-reference/database-types-and-descriptions)。|
   
<a name="SfB2015_ArchModel"> </a>
### <a name="microsoft-skype-for-business-2015-architectural-models"></a>Microsoft Skype for Business 2015 のアーキテクチャ モデル

|アイテム|説明|
|---|---|
|[![Skype for Businessアーキテクチャ モデルポスターのサムネイル。](../media/132288c0-6ae4-4394-88ab-b57dae367714.png)](https://www.microsoft.com/download/details.aspx?id=55022) <br/> [PDF](https://download.microsoft.com/download/7/7/4/7741262C-A60D-41F7-863B-99BF5964FBFE/Skype%20for%20Business%20Architectural%20Models.pdf)  \| [Visio](https://download.microsoft.com/download/7/7/4/7741262C-A60D-41F7-863B-99BF5964FBFE/Skype%20for%20Business%20Architectural%20Models.vsd)  \| [その他の言語](https://www.microsoft.com/download/details.aspx?id=55022)|このポスターでは、オンライン、オンプレミス、ハイブリッド、クラウドプライベートブランチエクスチェンジ (PBX) Skype for Businessについて説明します。 また、ビジネスの意思決定者やソリューションアーキテクトが知る必要があるExchangeおよびSharePoint構成との統合についても説明します。 <br/><br/> このポスターは、IT 担当者が、オンプレミスでSkype for Business Online とSkype for Businessを使用できる基本的なアーキテクチャ モデルに対する認識を高めることを目的としています。 <br/><br/>まず、組織のニーズと計画に最も適した構成から始めます。 必要に応じて、他の構成を検討して使用します。 たとえば、ExchangeやSharePointとの統合、または Microsoft クラウド PBX オファリングを利用するソリューションを検討できます。|
   
## <a name="platform-options-posters"></a>プラットフォーム オプションのポスター

SharePoint 2013、Exchange 2013、Lync 2013 の IT ポスターは、展開方法を一目で比較する方法を提供します。 各ポスターには、すべての構成またはプラットフォーム オプションが一覧表示されます。 オプションごとに次の情報が提供されます。
  
- **概要**: 概念図を含む、プラットフォームの簡単な概要。
    
- **最適な用途**: プラットフォームに最適な一般的なシナリオ。
    
- **ライセンス要件**: デプロイに必要なライセンス。
    
- **アーキテクチャ タスク**: アーキテクトとして行う必要がある決定。
    
- **IT 担当者のタスクまたは責任**: IT スタッフが計画する必要がある毎日の責任。
    
<a name="SP2013_Options"> </a>
## <a name="sharepoint-2013-platform-options"></a>SharePoint 2013 プラットフォーム オプション

|アイテム|説明|
|---|---|
|[![SharePoint 2013 プラットフォーム オプション ポスターのサムネイル画像。](../media/SP-PlatformOptions.jpg)](https://www.microsoft.com/download/details.aspx?id=40332) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkId=324594)  \| [Visio](https://go.microsoft.com/fwlink/p/?LinkId=324593)  \| [その他の言語](https://www.microsoft.com/download/details.aspx?id=40332)|ビジネスの意思決定者とアーキテクトの場合、このポスターでは、SharePoint 2013、Microsoft 365のSharePoint、Microsoft 365を使用したオンプレミス ハイブリッド、Azure、オンプレミス専用デプロイのプラットフォーム オプションを示します。 これには、各アーキテクチャの概要、推奨事項、ライセンス要件、および各プラットフォームのアーキテクトタスクと IT 担当者タスクの一覧が含まれます。 ポスターには、Azure 上のいくつかのSharePointソリューションが強調表示されています。|
   
<a name="Exch2013_options"> </a>
## <a name="exchange-2013-platform-options"></a>Exchange 2013 プラットフォーム オプション

|アイテム|説明|
|---|---|
|[![Exchange プラットフォーム オプションポスターのサムネイル画像。](../media/ITPro-Other-Exchange2013PlatformOptions.jpg)          ](https://www.microsoft.com/download/details.aspx?id=42676) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkID=398740)  \| [Visio](https://go.microsoft.com/fwlink/p/?LinkID=398742)  \| [その他の言語](https://www.microsoft.com/download/details.aspx?id=42676)|ビジネスの意思決定者とアーキテクト向けに、このポスターでは、Exchange 2013 のプラットフォーム オプションについて説明します。 お客様は、Microsoft 365、ハイブリッド Exchange、オンプレミスExchange ServerホストされたExchangeを使用して、Exchange Onlineから選択できます。 ポスターでは、それぞれの理想的なシナリオ、ライセンス要件、IT 担当者の責任など、各アーキテクチャ オプションについて詳しく説明します。|
   
<a name="Lync2013_Options"> </a>
## <a name="lync-2013-platform-options"></a>Lync 2013 プラットフォーム オプション

|アイテム|説明|
|---|---|
|[![Lync 2013 プラットフォーム オプション ポスターのサムネイル画像。](../media/Lync-PlatformOptions.jpg)          ](https://www.microsoft.com/download/details.aspx?id=41677) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkID=391837)  \| [Visio](https://go.microsoft.com/fwlink/p/?LinkID=391839)  \| [その他の言語](https://www.microsoft.com/download/details.aspx?id=41677)|ビジネスの意思決定者とアーキテクトの場合、このポスターでは、Lync 2013 のプラットフォーム オプションについて説明します。 お客様は、Microsoft 365、ハイブリッド Lync、オンプレミスの Lync Server、ホストされている Lync を使用して Lync Online から選択できます。 IT ポスターでは、それぞれの理想的なシナリオ、ライセンス要件、IT 担当者の責任など、各アーキテクチャ オプションについて詳しく説明しています。|
   
<a name="Lync2013_Options"> </a>
## <a name="sharepoint-in-azure-solutions-posters"></a>Azure の SharePoint のソリューションのポスター

Azure のSharePointの IT ポスターには、SharePoint Server 2013 を使用する Azure ベースのソリューションが示されています。
  
<a name="Azure_sharepoint2013"> </a>
### <a name="internet-sites-in-microsoft-azure-using-sharepoint-server-2013"></a>SharePoint Server 2013 を使用したMicrosoft Azureのインターネット サイト

|アイテム|説明|
|---|---|
|[![SharePoint Server 2013 ポスターを使用した Azure のインターネット サイトの画像。](../media/MS-AZ-SPInternetSites.jpg)          ](https://www.microsoft.com/download/details.aspx?id=41992) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkId=392552)  \| [Visio](https://go.microsoft.com/fwlink/p/?LinkId=392551)  \| [その他の言語](https://www.microsoft.com/download/details.aspx?id=41992)|このポスターでは、Azure のインターネットに接続するサイトの主要な設計アクティビティと推奨アーキテクチャについて説明します。  <br/><br/> 詳細については、次の記事を参照してください。  <br/><br/> - [SharePoint Server 2013 を使用した Azure のインターネット サイト](internet-sites-in-microsoft-azure-using-sharepoint-server-2013.md) <br/> - [SharePoint 2013 の Azure アーキテクチャ](microsoft-azure-architectures-for-sharepoint-2013.md)|
   
<a name="DesignSampleInternetSites"> </a>
### <a name="internet-sites-in-azure-for-sharepoint-2013"></a>azure for SharePoint 2013 のインターネット サイト

|アイテム|説明|
|---|---|
|[![SharePoint Server 2013 ポスターのMicrosoft Azureのインターネット サイトの画像。](../media/MS-AZ-InternetSitesDesignSample.jpg)          ](https://www.microsoft.com/download/details.aspx?id=41991) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkId=392549)  \| [Visio](https://go.microsoft.com/fwlink/p/?LinkId=392548)  \| [その他の言語](https://www.microsoft.com/download/details.aspx?id=41991)|この設計サンプルは、SharePoint Server 2013 を使用して Azure のインターネットに接続するサイトの独自のアーキテクチャの開始点として使用します。 <br/><br/> 詳細については、次の記事を参照してください。  <br/><br/> - [SharePoint Server 2013 を使用した Azure のインターネット サイト](internet-sites-in-microsoft-azure-using-sharepoint-server-2013.md) <br/> - [SharePoint 2013 の Azure アーキテクチャ](microsoft-azure-architectures-for-sharepoint-2013.md)|
   
<a name="sharepoint_recovery_Azure"> </a>
### <a name="sharepoint-disaster-recovery-to-microsoft-azure"></a>Microsoft Azure に対する SharePoint の障害復旧

|アイテム|説明|
|---|---|
|[![azure へのディザスター リカバリー プロセスSharePointポスターの画像。](../media/SP-DR-Azure.png)          ](https://www.microsoft.com/download/details.aspx?id=41993) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkId=392555)  \| [Visio](https://go.microsoft.com/fwlink/p/?LinkId=392554)  \| [その他の言語](https://www.microsoft.com/download/details.aspx?id=41993)|この IT ポスターは、Azure の障害復旧環境のためのアーキテクチャ原則を示しています。 <br/><br/> 詳細については、次の記事を参照してください。  <br/><br/> - [Azure での SharePoint Server 2013 ディザスター リカバリー](sharepoint-server-2013-disaster-recovery-in-microsoft-azure.md) <br/> - [SharePoint 2013 の Azure アーキテクチャ](microsoft-azure-architectures-for-sharepoint-2013.md)|
   
## <a name="see-also"></a>関連項目

- [Microsoft 365 ソリューションおよびアーキテクチャ センター](../solutions/index.yml)
  
- [Microsoft クラウド アーキテクチャ モデル](../solutions/cloud-architecture-models.md)
  
- [Microsoft 365テスト ラボ ガイド](m365-enterprise-test-lab-guides.md)
  
- [ハイブリッド ソリューション](hybrid-solutions.md)