---
title: SharePoint、Exchange、Skype for Business、Lync のアーキテクチャ モデル
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
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
description: アーキテクチャ モデル、展開、およびプラットフォーム オプションを説明する IT ポスターを取得し、SharePoint、Exchange、Skype for Business、Lync に関する情報を取得します。
ms.openlocfilehash: 813a143d281f85e6cbc9c0456dceaf20c674d13b
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60178973"
---
# <a name="architectural-models-for-sharepoint-exchange-skype-for-business-and-lync"></a>SharePoint、Exchange、Skype for Business、Lync のアーキテクチャ モデル

この記事の IT ポスターでは、SharePoint、Exchange、Skype for Business、Lync のアーキテクチャ モデルと展開オプションについて説明します。 また、アプリケーションを展開する設計情報もSharePoint提供Microsoft Azure。
  
この機能をMicrosoft 365、クラウド経由で使い慣れたコラボレーションサービスやコミュニケーション サービスを提供できます。 いくつかの例外を除き、ユーザー エクスペリエンスは、オンプレミスの展開を維持する場合でも、ユーザー エクスペリエンスを使用する場合でも同Microsoft 365。 

この統合されたユーザー エクスペリエンスは、各ワークロードの配置場所を決定する際に複雑になります。 また、次の質問も発生します。
  
- 個々のワークロードのプラットフォームを選択する方法
    
- オンプレミスのサービスを残すことに意味はあるか。
    
- ハイブリッド展開が適切なシナリオは何ですか?
    
- Azure は図に収まる方法を説明します。
    
- Azure でサポートされるOfficeサーバー ワークロードの構成は何ですか?
    
> [!TIP]
> この記事のほとんどのポスターは、複数の言語で利用できます。 使用可能な言語には、中国語、英語、フランス語、ドイツ語、イタリア語、日本語、韓国語、ポルトガル語、ロシア語、スペイン語が含まれます。 これらの言語の 1 つでポスターをダウンロードするには、ポスターのサムネイル画像の下にある [その他の言語] **を選択します**。
  
ご意見を電子メールで [cloudadopt@microsoft.com](mailto:cloudadopt@microsoft.com) 宛てにお送りください。 
  
必要なポスターを取得するには、次のリンクを使用します。
  
- **アーキテクチャ モデル**: これらのリソースを使用して、2016 年および 2015 年のSharePointプラットフォームSkype for Businessします。
    
  - [Microsoft SharePoint 2016 アーキテクチャ モデル](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#SP2016_ArchModel)
    
  - [SharePointServer 2016 データベース](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#SP2016_Databases)
    
  - [Microsoft Skype for Business 2015 アーキテクチャ モデル](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#SfB2015_ArchModel)
    
- **プラットフォーム**: これらのリソースを使用して、SharePoint 2013、Exchange、Lync 2013 に最適なプラットフォームと構成を決定します。
    
  - [SharePoint 2013 プラットフォーム オプション](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#SP2013_Options)
    
  - [Exchange 2013 プラットフォーム オプション](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#Exch2013_options)
    
  - [Lync 2013 プラットフォーム のオプション](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#Lync2013_Options)
    
- **SharePoint Server 2013**: Azure インフラストラクチャ サービスの SharePoint Server 2013 ワークロードを設計および構成するには、次の IT ポスターを使用します。
    
  - [Azure のインターネット サイトでサーバー 2013 SharePointを使用する](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#Azure_sharepoint2013)
    
  - [デザイン サンプル: Azure のインターネット サイト for SharePoint 2013](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#DesignSampleInternetSites)
    
  - [SharePoint障害復旧を Azure に追加する](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#sharepoint_recovery_Azure)
    
## <a name="architectural-models-posters"></a>アーキテクチャ モデルのポスター

SharePoint 2016 および Skype for Business 2015 の IT ポスターは、印刷しやすい形式で展開方法を比較する方法を提供します。 ポスターには、すべての構成オプションまたはプラットフォーム オプションが一覧表示されます。 各オプションについて、次の情報を提供します。
  
- **概要**: 概念図を含むプラットフォームの簡単な概要。
    
- **ベスト:** プラットフォームに最適な一般的なシナリオ。
    
- **ライセンス要件**: 展開に必要なライセンス。
    
- **アーキテクチャタスク**: アーキテクトとして行う必要がある決定。
    
- **IT プロのタスクまたは責任**: IT スタッフが計画する必要がある毎日の責任。
    
<a name="SP2016_ArchModel"> </a>
### <a name="microsoft-sharepoint-server-2016-architectural-models"></a>Microsoft SharePoint Server 2016 のアーキテクチャ モデル

|アイテム|説明|
|---|---|
|[![[サーバー 2016 SharePointモデル] ポスターのサムネイル。](../media/7d3e590c-1f3b-42cf-920d-9edac8fa3e04.png)          ](https://www.microsoft.com/download/details.aspx?id=52650) <br/> [PDF](https://download.microsoft.com/download/4/F/A/4FA0F94B-EE2F-41DB-A047-D9864FEF41E9/SharePoint2016ArchitecturalModels.pdf)  \| [Visio](https://download.microsoft.com/download/4/F/A/4FA0F94B-EE2F-41DB-A047-D9864FEF41E9/SharePoint2016ArchitecturalModels.vsdx)  \| [その他の言語](https://www.microsoft.com/download/details.aspx?id=52650)|この IT ポスターでは、ビジネス意思決定者SharePointソリューション アーキテクトが知る必要SharePointオンライン、Azure、および SharePointオンプレミス構成について説明します。 <br/><br/> - **SharePoint (SaaS)**: サービスとしてSharePoint (SaaS) サブスクリプション モデルを使用してユーザーを使用します。 <br/> - **SharePointハイブリッド**: サイトSharePointアプリを自分のペースでクラウドに移動します。 <br/> - **SharePoint (IaaS) :** オンプレミス環境を Azure に拡張し、2016 SharePoint展開します。 (このモデルは、高可用性環境または障害復旧環境および開発/テスト環境に推奨されます)。 <br/> - **SharePointオンプレミス**: 保守するデータセンターで、SharePoint環境を計画、展開、保守、およびカスタマイズします。|
   
<a name="SP2016_Databases"> </a>
### <a name="sharepoint-server-2016-databases"></a>SharePoint Server 2016 Database

|アイテム|説明|
|---|---|
|[![サーバー 2016 SharePointポスターのサムネイル。](../media/c53e9de7-3bf8-446d-8766-e6700c8dd8e1.png)](https://www.microsoft.com/download/details.aspx?id=55041) <br/> [PDF](https://download.microsoft.com/download/D/5/D/D5DC1121-8BC5-4953-834F-1B5BB03EB691/DBrefguideSPS2016_tabloid.pdf)  \| [Visio](https://download.microsoft.com/download/D/5/D/D5DC1121-8BC5-4953-834F-1B5BB03EB691/DBrefguideSPS2016_tabloid.vsdx)  \| [その他の言語](https://www.microsoft.com/download/details.aspx?id=55041)|この IT ポスターは、サーバー 2016 データベースSharePoint参照です。 各データベースの詳細が表示されます。 <br/><br/> - サイズ <br/> - 拡大縮小のガイド <br/> - I/O パターン <br/> - 要件 <br/><br/>  最初のページには、SharePointデータベースと複数のデータベースを持つサービス アプリケーションが表示されます。 2 番目のページには、1 つのデータベースを持つサービス アプリケーションのすべてが表示されます。 <br/><br/>  詳細については、「データベースの種類と説明」[を参照してください(SharePoint Server 2016)。](/SharePoint/technical-reference/database-types-and-descriptions)|
   
<a name="SfB2015_ArchModel"> </a>
### <a name="microsoft-skype-for-business-2015-architectural-models"></a>Microsoft Skype for Business 2015 のアーキテクチャ モデル

|アイテム|説明|
|---|---|
|[![[アーキテクチャ モデル] Skype for Businessのサムネイル。](../media/132288c0-6ae4-4394-88ab-b57dae367714.png)](https://www.microsoft.com/download/details.aspx?id=55022) <br/> [PDF](https://download.microsoft.com/download/7/7/4/7741262C-A60D-41F7-863B-99BF5964FBFE/Skype%20for%20Business%20Architectural%20Models.pdf)  \| [Visio](https://download.microsoft.com/download/7/7/4/7741262C-A60D-41F7-863B-99BF5964FBFE/Skype%20for%20Business%20Architectural%20Models.vsd)  \| [その他の言語](https://www.microsoft.com/download/details.aspx?id=55022)|このポスターでは、Skype for Business、オンプレミス、ハイブリッド、クラウドのプライベート ブランチ 交換 (PBX) について説明します。 また、ビジネス上の意思決定者やExchange設計者SharePointが知る必要があるさまざまな構成との統合について説明します。 <br/><br/> このポスターは、IT のプロが、Skype for Business およびオンプレミスのSkype for Business使用できる基本的なアーキテクチャ モデルに対する認識を高めることを目的としています。 <br/><br/>組織のニーズと計画に最も適した構成から始める。 必要に応じて、他の構成を検討して使用します。 たとえば、Microsoft クラウド PBX の提供を利用する Exchangeおよび SharePointソリューションとの統合を検討する場合があります。|
   
## <a name="platform-options-posters"></a>プラットフォーム オプションのポスター

SharePoint 2013、Exchange 2013、Lync 2013 の IT ポスターでは、展開方法を一目で比較できます。 各ポスターには、すべての構成またはプラットフォーム オプションが一覧表示されます。 各オプションについて、次の情報を提供します。
  
- **概要**: 概念図を含むプラットフォームの簡単な概要。
    
- **ベスト:** プラットフォームに最適な一般的なシナリオ。
    
- **ライセンス要件**: 展開に必要なライセンス。
    
- **アーキテクチャタスク**: アーキテクトとして行う必要がある決定。
    
- **IT プロのタスクまたは責任**: IT スタッフが計画する必要がある毎日の責任。
    
<a name="SP2013_Options"> </a>
## <a name="sharepoint-2013-platform-options"></a>SharePoint 2013 プラットフォーム オプション

|アイテム|説明|
|---|---|
|[![2013 プラットフォーム SharePointポスターのサムネイル画像。](../media/SP-PlatformOptions.jpg)](https://www.microsoft.com/download/details.aspx?id=40332) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkId=324594)  \| [Visio](https://go.microsoft.com/fwlink/p/?LinkId=324593)  \| [その他の言語](https://www.microsoft.com/download/details.aspx?id=40332)|ビジネス上の意思決定者とアーキテクトの場合、このポスターには、SharePoint 2013、Microsoft 365 の SharePoint、Microsoft 365、Azure、オンプレミス専用の展開を備えたオンプレミス ハイブリッドのプラットフォーム オプションが示されています。 各アーキテクチャ、推奨事項、ライセンス要件、各プラットフォームのアーキテクトタスクと IT プロ タスクのリストの概要が含まれます。 このポスターでは、Azure 上のいくつかのSharePointソリューションについて説明します。|
   
<a name="Exch2013_options"> </a>
## <a name="exchange-2013-platform-options"></a>Exchange 2013 プラットフォーム オプション

|アイテム|説明|
|---|---|
|[![[プラットフォーム オプション] ポスター Exchangeサムネイル画像。](../media/ITPro-Other-Exchange2013PlatformOptions.jpg)          ](https://www.microsoft.com/download/details.aspx?id=42676) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkID=398740)  \| [Visio](https://go.microsoft.com/fwlink/p/?LinkID=398742)  \| [その他の言語](https://www.microsoft.com/download/details.aspx?id=42676)|ビジネス上の意思決定者とアーキテクトの場合、このポスターでは、2013 年のプラットフォーム オプションExchange説明します。 お客様は、Exchange Online、Microsoft 365、Exchange、Exchange ServerホストされたExchange。 ポスターでは、それぞれの理想的なシナリオ、ライセンス要件、IT プロの責任など、各アーキテクチャ オプションについて詳しくは説明します。|
   
<a name="Lync2013_Options"> </a>
## <a name="lync-2013-platform-options"></a>Lync 2013 プラットフォーム オプション

|アイテム|説明|
|---|---|
|[![Lync 2013 プラットフォーム オプションポスターのサムネイル 画像。](../media/Lync-PlatformOptions.jpg)          ](https://www.microsoft.com/download/details.aspx?id=41677) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkID=391837)  \| [Visio](https://go.microsoft.com/fwlink/p/?LinkID=391839)  \| [その他の言語](https://www.microsoft.com/download/details.aspx?id=41677)|ビジネス上の意思決定者とアーキテクトの場合、このポスターでは Lync 2013 のプラットフォーム オプションについて説明します。 顧客は、Lync Online から、Microsoft 365 Lync、Lync Server オンプレミス、ホスト型 Lync を選択できます。 IT ポスターでは、それぞれの理想的なシナリオ、ライセンス要件、IT プロの責任など、各アーキテクチャ オプションについて詳しくは説明します。|
   
<a name="Lync2013_Options"> </a>
## <a name="sharepoint-in-azure-solutions-posters"></a>Azure の SharePoint のソリューションのポスター

Azure の IT ポスターには、SharePoint Server 2013 を使用する Azure ベースのソリューションSharePoint示しています。
  
<a name="Azure_sharepoint2013"> </a>
### <a name="internet-sites-in-microsoft-azure-using-sharepoint-server-2013"></a>サーバー 2013 Microsoft Azure使用SharePointインターネット サイト

|アイテム|説明|
|---|---|
|[![サーバー 2013 のポスターを使用SharePoint Azure のインターネット サイトのイメージ。](../media/MS-AZ-SPInternetSites.jpg)          ](https://www.microsoft.com/download/details.aspx?id=41992) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkId=392552)  \| [Visio](https://go.microsoft.com/fwlink/p/?LinkId=392551)  \| [その他の言語](https://www.microsoft.com/download/details.aspx?id=41992)|このポスターでは、Azure のインターネット向けサイトの主要な設計アクティビティと推奨アーキテクチャの概要を示します。  <br/><br/> 詳細については、次の資料を参照してください。  <br/><br/> - [Azure のインターネット サイトでサーバー 2013 SharePointを使用する](internet-sites-in-microsoft-azure-using-sharepoint-server-2013.md) <br/> - [2013 年SharePoint Azure アーキテクチャ](microsoft-azure-architectures-for-sharepoint-2013.md)|
   
<a name="DesignSampleInternetSites"> </a>
### <a name="internet-sites-in-azure-for-sharepoint-2013"></a>Azure のインターネット サイト for SharePoint 2013

|アイテム|説明|
|---|---|
|[![サーバー 2013 ポスターのMicrosoft AzureのSharePointイメージ。](../media/MS-AZ-InternetSitesDesignSample.jpg)          ](https://www.microsoft.com/download/details.aspx?id=41991) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkId=392549)  \| [Visio](https://go.microsoft.com/fwlink/p/?LinkId=392548)  \| [その他の言語](https://www.microsoft.com/download/details.aspx?id=41991)|この設計サンプルは、Azure のインターネットに接続するサイトの独自のアーキテクチャの開始点として、SharePoint Server 2013 を使用します。 <br/><br/> 詳細については、次の資料を参照してください。  <br/><br/> - [Azure のインターネット サイトでサーバー 2013 SharePointを使用する](internet-sites-in-microsoft-azure-using-sharepoint-server-2013.md) <br/> - [2013 年SharePoint Azure アーキテクチャ](microsoft-azure-architectures-for-sharepoint-2013.md)|
   
<a name="sharepoint_recovery_Azure"> </a>
### <a name="sharepoint-disaster-recovery-to-microsoft-azure"></a>Microsoft Azure に対する SharePoint の障害復旧

|アイテム|説明|
|---|---|
|[![障害復旧プロセスを Azure にSharePointポスターのイメージ。](../media/SP-DR-Azure.png)          ](https://www.microsoft.com/download/details.aspx?id=41993) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkId=392555)  \| [Visio](https://go.microsoft.com/fwlink/p/?LinkId=392554)  \| [その他の言語](https://www.microsoft.com/download/details.aspx?id=41993)|この IT ポスターは、Azure の障害復旧環境のためのアーキテクチャ原則を示しています。 <br/><br/> 詳細については、次の記事を参照してください。  <br/><br/> - [SharePointAzure の Server 2013 障害復旧](sharepoint-server-2013-disaster-recovery-in-microsoft-azure.md) <br/> - [2013 年SharePoint Azure アーキテクチャ](microsoft-azure-architectures-for-sharepoint-2013.md)|
   
## <a name="see-also"></a>関連項目

- [Microsoft 365 ソリューションおよびアーキテクチャ センター](../solutions/index.yml)
  
- [Microsoft クラウド アーキテクチャ モデル](../solutions/cloud-architecture-models.md)
  
- [Microsoft 365ラボ ガイド](m365-enterprise-test-lab-guides.md)
  
- [ハイブリッド ソリューション](hybrid-solutions.md)