---
title: PerformancePoint Server 2007 のサポート終了ロードマップ
ms.author: kvice
author: kelleyvice-msft
manager: scotv
audience: ITPro
ms.topic: conceptual
ms.service: o365-solutions
ms.localizationpriority: medium
ms.collection: Ent_O365
search.appverid:
- PSV120
- PDD140
- MET150
ms.assetid: 89d9feee-2285-419c-8c14-0f7f583536e0
f1.keywords:
- NOCSH
description: PerformancePoint Server 2007、ProClarity、およびSharePoint Server 2007 はサポートの終了に達しました。 この記事を読んで、BI ソリューションのアップグレードを計画する方法について説明します。
ms.openlocfilehash: 381faab617828d3bb30106deaaae993ed8d2b786
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65096350"
---
# <a name="performancepoint-server-2007-end-of-support-roadmap"></a>PerformancePoint Server 2007 のサポート終了ロードマップ

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

Office 2007 サーバーとアプリケーションは、ビジネス インテリジェンス (BI) ソリューションの一部として使用する可能性があるサーバーやアプリケーションなど、サポートの終了に達しました。 次の表に、影響を受ける BI アプリケーションを示します。
  
|**Microsoft BI アプリケーション**|**サポートが終了した日付**|
|:-----|:-----|
|ProClarity Analytics Server 6.3 Service Pack 3  <br/> ProClarity Desktop Professional 6.3  <br/> ProClarity SharePoint Viewer 6.3  <br/> |2017 年 7 月 11 日  <br/> |
|SharePoint Server 2007 Service Pack 3  <br/> |2017 年 10 月 10 日  <br/> |
|PerformancePoint Server 2007 Service Pack 3  <br/> |2018 年 1 月 9 日  <br/> |
   
詳細については、[Office 2007 サーバーとクライアントからのアップグレードに役立つリソースに関する](upgrade-from-office-2007-servers-and-products.md)ページを参照してください。
  
## <a name="what-does-end-of-support-mean"></a>*サポート終了とは* どういう意味ですか?

ほとんどの Microsoft 製品と同様に、PerformancePoint Server 2007 SP3、ProClarity ソフトウェア、SharePoint Server 2007 SP3 にはサポート ライフサイクルがあり、その間、Microsoft は新機能、バグ修正、およびセキュリティ更新プログラムを提供します。 製品のライフサイクルは、通常、製品の最初のリリースから 10 年間続きます。 そのライフサイクルの終わりは、製品のサポート終了と呼ばれます。 ProClarity、PerformancePoint Server、SharePoint Server 2007 がサポート終了に達すると、Microsoft は次の機能を提供しなくなりました。
  
- 発生する可能性がある問題のテクニカル サポート。
    
- 検出され、サーバーの安定性と使いやすさに影響を与える可能性がある問題に関するバグ修正。
    
- 検出され、サーバーまたはアプリケーションがセキュリティ違反に対して脆弱になる可能性がある脆弱性に対するセキュリティ修正。
    
- タイム ゾーンの更新。
    
ProClarity、SharePoint Server 2007 SP3、PerformancePoint Server 2007 SP3 のインストールは、サポートが終了しても引き続き実行されます。 ただし、できるだけ早くこれらのアプリケーションから移行することを強くお勧めします。
  
## <a name="what-are-my-options"></a>使用できるオプション

2007 年以降、Microsoft BI アプリケーションには多くの変更があり、次の表に示すように、考慮すべきいくつかのオプションがあります。
  
|**この .... を使用していた場合。**|**これらのオプションを調べる ...**|**そして、これを念頭に置いて...**|
|:-----|:-----|:-----|
| PerformancePoint Server 2007 監視&amp;次のような分析機能。<br/>- PerformancePoint 監視サーバー <br/>- PerformancePoint ダッシュボード デザイナー<br/>- SharePoint Services 用ダッシュボード ビューアー (PerformancePoint ダッシュボード、スコアカード、レポートのレンダリングに使用)<br/> |ブラウザー (クラウドまたはオンプレミス) **でExcel** を使用してExcelします。 概要については、[ExcelとMicrosoft 365の BI 機能に関するページを参照](https://support.office.com/article/26c0548e-124c-4fd3-aab3-5f64568cb743.aspx)してください。<br/><br/> **Power BI** (クラウドまたはオンプレミス)。 概要については、「Power BIとは[」](https://go.microsoft.com/fwlink/?linkid=841341)を参照してください。 <br/><br/> **SQL Server Reporting Services** (オンプレミス)。 概要については、「[SQL Server Reporting Services (SSRS): モバイル レポートとページ分割されたレポートの作成、展開、管理](/sql/reporting-services/create-deploy-and-manage-mobile-and-paginated-reports)」を参照してください。 <br/><br/> **PerformancePoint Services** (オンプレミス)。 概要については、「[PerformancePoint Servicesの新機能 (SharePoint Server 2010)」](/previous-versions/office/sharepoint-server-2010/ee661741(v=office.14))を参照してください。 <br/> |Excelは、オンライン (クラウドベース) またはオンプレミス のソリューションとして利用できます。 多くのレポートとダッシュボードのニーズは、Excelで満たすことができます。  <br/><br/> Power BIは、オンラインまたはオンプレミスのソリューションとして使用できます。 Power BIはMicrosoft 365に含まれていません。 ただし、無料でPower BIの使用を開始できます。 後で、データの使用状況とビジネス ニーズに応じて、Microsoft 365 E5を使用してPower BI Proにアップグレードできます。<br/> <br/> Reporting ServicesとPerformancePoint Servicesはどちらもオンプレミス ソリューションです。 <br/><br/> PerformancePoint Servicesは、SharePoint Server 2010、SharePoint Server 2013、SharePoint Server 2016 で使用できます。 <br/> <br/> PerformancePoint Server 2007 で使用できた一部の機能とレポートの種類は、Excel、Power BI、Reporting Services、またはPerformancePoint Servicesでは使用できません。 使用可能な機能を確認して、ビジネス ニーズに最適なソリューションを決定します。 <br/> |
| ProClarity ソフトウェア(以下を含む):<br/>- ProClarity Desktop Professional<br/> - ProClarity Analytics Server<br/>- ProClarity SharePoint ビューアー<br/> |**Microsoft パートナーと協力** して、ニーズに最も適したソリューションを特定します。 [Microsoft パートナー センター](https://go.microsoft.com/fwlink/?linkid=841249)にアクセスします。 <br/><br/> ブラウザー、Power BI、SQL Server Reporting Services、またはPerformancePoint ServicesでExcelでExcelを使用することもできます。  <br/> |ProClarity ソフトウェアの一部の機能は、Excel、Power BI、Reporting Services、PerformancePoint Servicesなど、他の Microsoft 製品で利用できるわけではありません。  <br/> |
|SharePoint Server 2007 KPI (MOSS KPI とも呼ばれます)  <br/> |**Excel Servicesを使用してExcel** します。 概要については、「[ExcelとExcel Servicesのビジネス インテリジェンス (SharePoint Server 2013)」](https://support.office.com/article/2740f10c-579d-4b40-a1d9-7beb5d38547c.aspx)を参照してください。 <br/> |SharePoint Server 2007 を使用して作成された MOSS KPI は、SharePoint Server 2010、SharePoint Server 2013、および SharePoint Server 2016 で使用できます。 ただし、新しい MOSS KPI を作成することはできません。  <br/> |
|Excel 2007  <br/> |**Excel** (クラウドまたはオンプレミス)。 概要については、[ExcelとOffice 365の BI 機能に関するページを参照](https://support.office.com/article/26c0548e-124c-4fd3-aab3-5f64568cb743.aspx)してください。 <br/><br/> **Power BI** (クラウドまたはオンプレミス)。 概要については、「Power BIとは[」](https://go.microsoft.com/fwlink/?linkid=841341)を参照してください。 <br/> |ExcelとPower BIの両方が、さまざまなデータ ソースをサポートして、組織のクラウドベースとオンプレミスのソリューションを提供します。  <br/> |
   
### <a name="help-selecting-a-solution"></a>ソリューションの選択に関するヘルプ

非常に多くの BI の選択肢があるため、どのオプションが最適かを判断するのは非常に大きいと思われるかもしれません。 オンライン ガイドが用意されています。 [分析とレポート用の Microsoft Business Intelligence (BI) ツールの選択に関するページを](/sql/reporting-services/choosing-microsoft-business-intelligence-bi-tools-for-analysis-and-reporting)参照してください。
  
### <a name="what-if-i-dont-upgrade-now"></a>今アップグレードしないとどうなりますか?

すぐにアップグレードしないことを選択できます。 既存のサーバーとアプリケーションは引き続き実行されます。 ただし、サポートが終了したため、セキュリティ更新プログラムを含む追加の更新プログラムは受け取りません。 また、サーバー アプリケーションで問題が発生した場合は、Microsoft テクニカル サポートのサポートを受けることはできません。
  
## <a name="how-do-i-plan-my-upgrade"></a>アップグレードを計画操作方法?

アップグレード オプションを確認したら、次の手順ではアップグレード 計画を準備します。 次のセクションには、役立つ情報とその他のリソースが含まれています。 主に 4 つのオプションがあります。これには、クラウドとオンプレミスの両方で動作する 2 つのオプションと、オンプレミス専用の 2 つのオプションがあります。
  
|**オプション**|**クラウドまたはオンプレミスでは?**|
|:-----|:-----|
|[SharePoint Server (オンプレミス) を使用したExcel](#excel-with-sharepoint-server-on-premises) <br/> |Both/フォーム/データシート  <br/> |
|[Power BI](#use-power-bi-in-the-cloud-or-on-premises)<br/> |Both/フォーム/データシート  <br/> |
|[レポート サービス](#use-reporting-services-on-premises) <br/> |オンプレミスのみ  <br/> |
|[PerformancePoint Services](#use-performancepoint-services-on-premises) <br/> |オンプレミスのみ  <br/> |
   
### <a name="use-excel-in-the-cloud-or-on-premises"></a>Excelを使用する (クラウドまたはオンプレミスで)

SharePoint Server の *Excel Services* とも呼ばれるExcelを使用すると、コンピューターにExcelがインストールされていない場合でも、ブラウザー ウィンドウでブックを表示して使用できます。 Excelを使用して、レポート、スコアカード、ダッシュボードを作成できます。 次に、ブラウザーでExcelを使用できる他のユーザーとブックを共有SharePoint、オンプレミスのMicrosoft 365またはSharePoint サーバーの一部として使用しているかどうか。 オンプレミスまたはクラウドに格納されたデータを使用できます。これにより、さまざまなデータ ソースを使用できます。
  
次の表では、Microsoft 365でExcelを使用する主な利点と、SharePoint Server でExcelを使用することの主な利点を比較します。 詳細については、以下を参照してください。
  
|**Microsoft 365を使用したExcel (クラウド内)**|**SharePoint Server (オンプレミス) を使用したExcel**|
|:-----|:-----|
|**最新の最高バージョンのExcelを入手** できます。 Microsoft 365では、強力な新しいグラフの種類、グラフとテーブルをすばやく簡単に作成する機能、より多くのデータ ソースのサポートを含む最新バージョンのExcelを入手できます。 <br/> <br/> **セットアップははるかに簡単です**。 Excelはビジネス向けのMicrosoft 365に含まれているので、作業に大きな影響はありません。 サインアップしてサインインすると、オンプレミス サーバーをアップグレードする場合よりも迅速かつ効率的に起動して実行できるようになります。 <br/> <br/> **ユーザーは自分のブックにどこからでもアクセスできます**。 ユーザーは、コンピューター、スマートフォン、タブレットを使用して、どこからでもブックを安全に表示できます。 <br/> <br/> **他にもまだあります！** [ExcelとOffice 365の BI 機能](https://support.office.com/article/26c0548e-124c-4fd3-aab3-5f64568cb743.aspx)を参照してください。 <br/> |**グローバル設定を管理します**。 SharePoint管理者は、セキュリティ、負荷分散、セッション管理、ブック キャッシュ、外部データ接続などのグローバル設定を指定できます。 <br/> <br/> **PerformancePoint ServicesでExcel Servicesを使用できます**。 SharePoint サーバーのインストールの一環としてExcel ServicesとPerformancePoint Servicesを構成し、Excel Services レポートを PerformancePoint ダッシュボードに含めることができます。 <br/> <br/> **他にもまだあります！** [ExcelとExcel Servicesのビジネス インテリジェンス (SharePoint Server 2013)](https://support.office.com/article/2740f10c-579d-4b40-a1d9-7beb5d38547c.aspx) を参照してください。 <br/> |
   
#### <a name="excel-with-microsoft-365-in-the-cloud"></a>Microsoft 365を使用したExcel (クラウド内)

Microsoft 365に移行すると、Excel 2016を含む最新のサービスとアプリケーションが提供されます。 PerformancePoint ServicesはMicrosoft 365では使用できないため、PerformancePoint ダッシュボードのコンテンツをExcelブックやその他のレポートに置き換えます。 良いニュースは、Excel 2016には新しいグラフの種類が多数あり、Excelで印象的なダッシュボードを作成する方がこれまで以上に簡単です。 新機能は定期的に追加されます。 詳細については、「[WindowsのExcel 2016の新機能」を](https://support.office.com/article/5fdb9208-ff33-45b6-9e08-1f5cdb3a6c73.aspx)参照してください。
  
また、50 席以上のMicrosoft 365を購入すると、Microsoft FastTrack チームがセットアップを支援できます。 詳細については、[FastTrack](https://www.microsoft.com/fasttrack/microsoft-365)をご覧ください。
  
#### <a name="excel-with-sharepoint-server-on-premises"></a>SharePoint Server (オンプレミス) を使用したExcel

新しいバージョンのSharePointにアップグレードする場合は、次のようにExcel ServicesまたはブラウザーでExcelを使用できます。
  
- SharePoint Server 2010 の Excel Services
    
- SharePoint Server 2013 の Excel Services
    
- Office Online Serverの一部であるExcelは、SharePoint Server 2016 とは別にインストールされます
    
新しいバージョンの SharePoint Server でもPerformancePoint Servicesを構成し、Excelと共に使用できます。
  
SharePointアップグレード オプションの詳細については、「[SharePoint Server 2007 のサポート終了ロードマップ](sharepoint-2007-end-of-support.md)」を参照してください。
  
Excel Servicesの詳細については、「[Excel Services概要 (SharePoint Server 2010)」](/previous-versions/office/sharepoint-server-2010/ee424405(v=office.14))を参照してください。
  
### <a name="use-power-bi-in-the-cloud-or-on-premises"></a>Power BIを使用する (クラウドまたはオンプレミスで)

Power BIは、データを分析し、分析情報を共有するための一連のビジネス分析ツールです。 Power BIでは、オンプレミスまたはオンラインのデータ ソースを使用して、対話型のレポートとダッシュボードを作成できます。 ユーザーは、自分のコンピューターまたはモバイル デバイスでレポートとダッシュボードを表示して使用できます。
  
Power BIは、Microsoft 365または SharePoint Server の一部ではありません。 これは、Power BI Desktop、Power BI ゲートウェイ、Power BI サービスを含む別のオファリングです。 Power BIは、SharePoint Online とも統合されます。 Power BIを無料で使い始めることができます。 データ使用量とビジネス ニーズに基づいて、後でMicrosoft 365 E5を使用してPower BI Proにアップグレードできます。 詳細については、「[Power BIとは」](https://go.microsoft.com/fwlink/?linkid=841341)を参照してください。
  
### <a name="use-reporting-services-on-premises"></a>Reporting Servicesを使用する (オンプレミス)

SQL Server Reporting Servicesは、堅牢なレポート ソリューションを提供します。 Reporting Servicesは、ネイティブ モードまたはSharePoint統合モードのいずれかで構成できます。 レポート デザイナー、Report Builder、Power View など、さまざまなツールを使用してレポートを作成できます。 SQL Serverの最新リリースでは、SQL Serverモバイル レポート Publisherを使用して、任意の画面サイズにスケールするレポートを配信することもできます。 これにより、閲覧者は自分のモバイル デバイスでレポートを使用できるようになります。 詳細については、「[SQL Server Reporting Services (SSRS): モバイル レポートとページ分割されたレポートの作成、展開、管理](/sql/reporting-services/create-deploy-and-manage-mobile-and-paginated-reports)」を参照してください。
  
### <a name="use-performancepoint-services-on-premises"></a>PerformancePoint Servicesを使用する (オンプレミス)

PerformancePoint Server 2007 は、SharePoint Server 2007 とは別に販売されました。 SharePoint Server 2010 以降、PerformancePoint Servicesは SharePoint Server のサービス アプリケーションです。 そのため、PerformancePoint Servicesを使用するために個別のサーバー ライセンスまたはハードウェアを購入する必要はありません。
  
PerformancePoint Server 2007 から PerformancePoint Servicesに移行するには、SharePoint Server の最新バージョンに移行し、PerformancePoint Servicesを構成します。 移行先のSharePoint サーバーのバージョンによって、2007 年 PerformancePoint Server PerformancePoint Servicesに既存のダッシュボード コンテンツをインポートできるかどうかを決定します。
  
- SharePoint Server 2010 にアップグレードする場合は、PerformancePoint ダッシュボードのコンテンツを 2007 PerformancePoint Serverから SharePoint Server 2010 のPerformancePoint Servicesにインポートできます。 詳細については、「[インポート ウィザード: SharePoint Server 2010 に 2007 コンテンツをPerformancePoint Serverする」を参照](/previous-versions/office/sharepoint-server-2010/ee681485(v=office.14))してください。
    
- SharePoint Server 2013 または SharePoint Server 2016 に移行する場合は、新しいダッシュボード コンテンツ (データ ソース、レポート、スコアカード、ダッシュボード ページ) を作成する必要があります。
    
PerformancePoint Servicesアップグレード 計画を開始するには、次のリソースを参照してください。
  
- [SharePoint Server 2007 のサポート終了ロードマップ](sharepoint-2007-end-of-support.md)
    
- 移行先のSharePointのバージョンがわかっている場合は、PerformancePoint Servicesに関する対応する記事を参照してください。
    
  - [PerformancePoint Servicesの計画 (SharePoint Server 2010)](/previous-versions/office/sharepoint-server-2010/ee681486(v=office.14))
    
  - [SharePoint Server 2013 のPerformancePoint Servicesの概要](/sharepoint/administration/performancepoint-services-overview)
    
  - [SharePoint Server 2016 の PerformancePoint Services の概要](/sharepoint/administration/performancepoint-services-overview)
    
PerformancePoint Servicesにアップグレードすると、いくつかの新機能と機能強化が追加されます。 PerformancePoint Servicesでは、スコアカードの改善、分解ツリーや KPI の詳細レポートなどの新しい視覚化、グラフの種類の追加、タイム インテリジェンスのフィルター機能の向上、アクセシビリティ コンプライアンスの向上が提供されます。 詳細については、「[PerformancePoint Servicesの新機能 (SharePoint Server 2010)」](/previous-versions/office/sharepoint-server-2010/ee661741(v=office.14))を参照してください。
  
## <a name="where-can-i-get-help-with-my-upgrade"></a>アップグレードに関するヘルプはどこで入手できますか?

オンプレミスをアップグレードする場合でも、Microsoft 365に移行する場合でも、Microsoft パートナーと連携することをお勧めします。 資格のあるパートナーは、ビジネス ニーズに最も適したソリューションを特定し、デプロイに役立ちます。 [Microsoft パートナー センター](https://go.microsoft.com/fwlink/?linkid=841249)にアクセスし、検索フィルターを使用してソリューション プロバイダーを見つけます。
  
## <a name="related-topics"></a>関連項目

[Office 2007 のサーバーとクライアントからのアップグレードに役立つリソース](upgrade-from-office-2007-servers-and-products.md)