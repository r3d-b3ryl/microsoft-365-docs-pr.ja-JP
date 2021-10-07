---
title: PerformancePoint Server 2007 のサポート終了ロードマップ
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
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
description: PerformancePoint Server 2007、ProClarity、および SharePoint Server 2007 はサポートの終了に達しました。 この記事を読んで、BI ソリューションのアップグレードを計画する方法についてお読みください。
ms.openlocfilehash: f4e0662109cc5bdbdfbf922086715a0de4d91c37
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60163314"
---
# <a name="performancepoint-server-2007-end-of-support-roadmap"></a>PerformancePoint Server 2007 のサポート終了ロードマップ

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

Office 2007 のサーバーとアプリケーションは、ビジネス インテリジェンス (BI) ソリューションの一部として使用する可能性があるサーバーやアプリケーションなど、サポートの最後に達しています。 次の表に、影響を受ける BI アプリケーションの一覧を示します。
  
|**Microsoft BI アプリケーション**|**サポートが終了した日付**|
|:-----|:-----|
|ProClarity Analytics Server 6.3 Service Pack 3  <br/> ProClarity Desktop Professional 6.3  <br/> ProClarity SharePoint ビューアー 6.3  <br/> |2017 年 7 月 11 日  <br/> |
|SharePointServer 2007 Service Pack 3  <br/> |2017 年 10 月 10 日  <br/> |
|PerformancePoint Server 2007 Service Pack 3  <br/> |2018 年 1 月 9 日  <br/> |
   
詳細については[、「2007 サーバー](upgrade-from-office-2007-servers-and-products.md)とクライアントからのアップグレードに役立つOffice」を参照してください。
  
## <a name="what-does-end-of-support-mean"></a>サポート終了 *とはどういう意味* ですか?

ほとんどの Microsoft 製品と同様に、PerformancePoint Server 2007 SP3、ProClarity ソフトウェア、および SharePoint Server 2007 SP3 にはサポート ライフサイクルがあります。その間、Microsoft は新機能、バグ修正、およびセキュリティ更新プログラムを提供します。 製品のライフサイクルは、通常、製品の最初のリリースから 10 年間続く。 そのライフサイクルの終了は、製品のサポートの終了と呼ばれる。 ProClarity、PerformancePoint Server、SharePoint Server 2007 がサポートの終了に達すると、Microsoft は次の機能を提供しなくなりました。
  
- 発生する可能性のある問題に対するテクニカル サポート。
    
- 検出され、サーバーの安定性と使いやすさに影響を与える可能性がある問題のバグ修正。
    
- 検出され、サーバーまたはアプリケーションがセキュリティ侵害に対して脆弱になる可能性がある脆弱性に対するセキュリティ修正。
    
- タイム ゾーンの更新。
    
ProClarity、SharePoint Server 2007 SP3、PerformancePoint Server 2007 SP3 のインストールは、サポートが終了した場合でも引き続き実行されます。 ただし、できるだけ早くこれらのアプリケーションから移行することを強く推奨します。
  
## <a name="what-are-my-options"></a>使用できるオプション

2007 以降、Microsoft BI アプリケーションには多くの変更が加え、次の表に示すいくつかのオプションを検討する必要があります。
  
|**この ... を使用していた場合。**|**これらのオプションについて説明します。.**|**そして、これを念頭に置いて...**|
|:-----|:-----|:-----|
| PerformancePoint Server 2007 Monitoring Analytics 機能(以下 &amp; を含む)<br/>- PerformancePoint 監視サーバー <br/>- PerformancePoint ダッシュボード デザイナー<br/>- ダッシュボード のダッシュボード ビューアー SharePoint Services (PerformancePoint ダッシュボード、スコアカード、レポートのレンダリングに使用)<br/> |**Excelブラウザー Excel (クラウドまたは** オンプレミス) で使用できます。 概要については、「BI の機能」を[参照ExcelおよびMicrosoft 365。](https://support.office.com/article/26c0548e-124c-4fd3-aab3-5f64568cb743.aspx)<br/><br/> **Power BI** (クラウドまたはオンプレミス)。 概要については、「What [is is Power BI?](https://go.microsoft.com/fwlink/?linkid=841341) <br/><br/> **SQL Server Reporting Services** (オンプレミス)。 概要については、「モバイル レポートと[ページ分割SQL Server Reporting Servicesレポートを作成、展開](/sql/reporting-services/create-deploy-and-manage-mobile-and-paginated-reports)、および管理する 」を参照してください。 <br/><br/> **PerformancePoint Services** (オンプレミス)。 概要については[、「What's new for PerformancePoint Services (SharePoint Server 2010)」を参照してください](/previous-versions/office/sharepoint-server-2010/ee661741(v=office.14))。 <br/> |Excel (クラウドベース) またはオンプレミス のソリューションとして利用できます。 多くのレポートとダッシュボードのニーズは、ユーザーのニーズExcel。  <br/><br/> Power BIは、オンラインまたはオンプレミスのソリューションとして利用できます。 Power BIに含まれていないMicrosoft 365。 ただし、無料でPower BIを開始できます。 後で、データの使用状況とビジネス ニーズに応じて、データを使用してPower BI ProにMicrosoft 365 E5。<br/> <br/> Reporting Services と PerformancePoint Servicesは、両方ともオンプレミス ソリューションです。 <br/><br/> PerformancePoint Servicesは、SharePoint Server 2010、SharePoint Server 2013、および SharePoint Server 2016 で使用できます。 <br/> <br/> PerformancePoint Server 2007 で使用できる一部の機能とレポートの種類は、Excel、Power BI、Reporting Services、または PerformancePoint Services で使用できません。 利用可能な機能を確認して、ビジネス ニーズに最適なソリューションを判断します。 <br/> |
| ProClarity ソフトウェア:<br/>- ProClarity デスクトップ Professional<br/> - ProClarity Analytics Server<br/>- ProClarity SharePoint ビューアー<br/> |**Microsoft パートナーと一緒に** 、ニーズに最適なソリューションを特定します。 Microsoft パートナー [センターにアクセスします](https://go.microsoft.com/fwlink/?linkid=841249)。 <br/><br/> ブラウザー、ブラウザー、Excel、Excelで、Power BI、SQL Server Reporting Services、またはPerformancePoint Services。  <br/> |ProClarity ソフトウェアの一部の機能は、Excel、Power BI、Reporting Services、PerformancePoint Services など、他の Microsoft 製品で利用できます。  <br/> |
|SharePointServer 2007 KPI (MOSS KPI とも呼ばれる)  <br/> |**Excel Excel Services**. 概要については、「ビジネス インテリジェンス in Excel と Excel Services [(SharePoint Server 2013)」を参照してください](https://support.office.com/article/2740f10c-579d-4b40-a1d9-7beb5d38547c.aspx)。 <br/> |SharePoint Server 2007 を使用して作成された MOSS KPI は、SharePoint Server 2010、SharePoint Server 2013、および SharePoint Server 2016 で使用できます。 ただし、新しい MOSS KPI は作成できない。  <br/> |
|Excel 2007  <br/> |**Excel** (クラウドまたはオンプレミス)。 概要については、「BI 機能の概要」[および「Excel」をOffice 365。](https://support.office.com/article/26c0548e-124c-4fd3-aab3-5f64568cb743.aspx) <br/><br/> **Power BI** (クラウドまたはオンプレミス)。 概要については、「What [is is Power BI?](https://go.microsoft.com/fwlink/?linkid=841341) <br/> |組織ExcelおよびPower BI、さまざまなデータ ソースをサポートして、組織のクラウドベースおよびオンプレミスのソリューションを提供します。  <br/> |
   
### <a name="help-selecting-a-solution"></a>ソリューションの選択に関するヘルプ

利用可能な BI の選択肢が非常に多い場合、最適なオプションを決定するには圧倒的に思えるかもしれません。 オンライン ガイドをご利用いただけます。 分析 [とレポート作成については、「Microsoft Business Intelligence (BI) ツールの選択」を参照してください](/sql/reporting-services/choosing-microsoft-business-intelligence-bi-tools-for-analysis-and-reporting)。
  
### <a name="what-if-i-dont-upgrade-now"></a>今すぐアップグレードしない場合は?

すぐにアップグレードしない選択が可能です。 既存のサーバーとアプリケーションは引き続き実行されます。 ただし、サポートが終了した後、セキュリティ更新プログラムを含むそれ以上の更新プログラムは受け取らない。 サーバー アプリケーションに問題がある場合は、Microsoft テクニカル サポートからヘルプを受け取る必要があります。
  
## <a name="how-do-i-plan-my-upgrade"></a>アップグレードを計画する方法

アップグレード オプションを確認した後、次にアップグレード 計画を準備します。 以下のセクションには、情報と役立つその他のリソースが含まれます。 クラウドまたはオンプレミスの両方で動作する 2 つのオプションと、オンプレミス専用の 2 つを含む 4 つの主なオプションがあります。
  
|**オプション**|**クラウドまたはオンプレミスの場合**|
|:-----|:-----|
|[Excel サーバー SharePoint (オンプレミス)](#excel-with-sharepoint-server-on-premises) <br/> |Both/フォーム/データシート  <br/> |
|[Power BI](#use-power-bi-in-the-cloud-or-on-premises)<br/> |Both/フォーム/データシート  <br/> |
|[レポート サービス](#use-reporting-services-on-premises) <br/> |オンプレミスのみ  <br/> |
|[PerformancePoint Services](#use-performancepoint-services-on-premises) <br/> |オンプレミスのみ  <br/> |
   
### <a name="use-excel-in-the-cloud-or-on-premises"></a>[Excelを使用する (クラウドまたはオンプレミス)

SharePoint Excel サーバーの *Excel Services* とも呼ばれる Excel を使用すると、Excel がコンピューターにインストールされていない場合でも、ブラウザー ウィンドウでブックを表示および使用できます。 レポート、スコアカードExcelダッシュボードを作成するには、このページを使用します。 次に、Microsoft 365 または SharePoint Server オンプレミスの一部として SharePoint Online を使用しているかに関係ない、ブラウザーで Excel を使用できる他のユーザーとブックを共有します。 オンプレミスまたはクラウドに保存されたデータを使用すると、さまざまなデータ ソースを使用できます。
  
次の表は、サーバーを使用する場合の主な利点Excel、Microsoft 365サーバーでのExcelをSharePointします。 詳細については、次の情報を参照してください。
  
|**ExcelとMicrosoft 365 (クラウド内)**|**Excel サーバー SharePoint (オンプレミス)**|
|:-----|:-----|
|**最新の最も偉大なバージョンのExcel。** このMicrosoft 365、強力な新しいグラフの種類、迅速かつ簡単にグラフとテーブルを作成する機能、およびより多くのデータ ソースのサポートを含む最新バージョンの Excel を取得できます。 <br/> <br/> **セットアップははるかに簡単です**。 ExcelはビジネスMicrosoft 365に含まれているので、重い持ち上げはありません。 サインアップしてサインインすると、オンプレミス サーバーをアップグレードする場合よりも高速かつ効率的に起動して実行できるようになります。 <br/> <br/> **ユーザーは、どこでも自分のブックにアクセスできます**。 ユーザーは、コンピューター、スマートフォン、タブレットを使用して、どこにいてもブックを安全に表示できます。 <br/> <br/> **他にもまだあります！** 「BI[の機能」を参照ExcelおよびOffice 365。](https://support.office.com/article/26c0548e-124c-4fd3-aab3-5f64568cb743.aspx) <br/> |**グローバル設定を管理します**。 管理者はSharePoint、セキュリティ、負荷分散、セッション管理、ブックキャッシュ、外部データ接続などのグローバル設定を指定できます。 <br/> <br/> **このコマンドは、Excel ServicesとPerformancePoint Servicesできます**。 Excel Servicesサーバー PerformancePoint Servicesの一部としてSharePointを構成し、PerformancePoint ダッシュボードにExcel Servicesレポートを含めさせることができます。 <br/> <br/> **他にもまだあります！** 「ビジネス インテリジェンス in Excel と Excel Services [」(SharePoint Server 2013) を参照してください](https://support.office.com/article/2740f10c-579d-4b40-a1d9-7beb5d38547c.aspx)。 <br/> |
   
#### <a name="excel-with-microsoft-365-in-the-cloud"></a>ExcelとMicrosoft 365 (クラウド内)

このサービスにMicrosoft 365、最新のサービスとアプリケーション (最新のサービスとアプリケーションを含む) がExcel 2016。 PerformancePoint Servicesでは使用できないMicrosoft 365、PerformancePoint ダッシュボード のコンテンツをブックや他のレポートExcel置き換えます。 良いニュースは、Excel 2016多くの新しいグラフの種類を持ち、新しいグラフで印象的なダッシュボードを作成する方がこれまで以上にExcel。 また、新しい機能は定期的に追加されます。 詳細については[、「What's New in Excel 2016」をWindows。](https://support.office.com/article/5fdb9208-ff33-45b6-9e08-1f5cdb3a6c73.aspx)
  
また、50 シート以上のシートを購入Microsoft 365、Microsoft FastTrackチームがセットアップを支援できます。 詳細については、「FastTrack」[を参照してください](https://www.microsoft.com/fasttrack/microsoft-365)。
  
#### <a name="excel-with-sharepoint-server-on-premises"></a>Excel サーバー SharePoint (オンプレミス)

新しいバージョンの SharePoint にアップグレードする場合は、Excelまたはブラウザー Excel Servicesを使用できます。
  
- SharePoint Server 2010 の Excel Services
    
- SharePoint Server 2013 の Excel Services
    
- Excelサーバー 2016 とは別にOffice Online Serverインストールされているサーバーの一部SharePoint。
    
新しいバージョンの PerformancePoint Services サーバーでもSharePoint構成し、サーバーと一緒に使用Excel。
  
アップグレード オプションの詳細については、「SharePoint SharePoint Server [2007 end of support Roadmap」を参照してください](sharepoint-2007-end-of-support.md)。
  
詳細については、「Excel Services概要[(Excel Services Server 2010](/previous-versions/office/sharepoint-server-2010/ee424405(v=office.14))SharePoint」を参照してください。
  
### <a name="use-power-bi-in-the-cloud-or-on-premises"></a>[Power BIを使用する (クラウドまたはオンプレミス)

Power BIは、データを分析し、分析情報を共有するためのビジネス分析ツールのスイートです。 このPower BI、オンプレミスまたはオンラインのデータ ソースを使用して、対話型のレポートとダッシュボードを作成できます。 ユーザーは、自分のコンピューターまたはモバイル デバイスでレポートとダッシュボードを表示および使用できます。
  
Power BIサーバーの一部Microsoft 365またはSharePointです。 これは、サービス、ゲートウェイ、Power BI Desktop、Power BIサービスを含むPower BIです。 Power BIオンラインと統合SharePointします。 無料でPower BI開始できます。 データの使用状況とビジネス ニーズに基づいて、後でデータを使用してPower BI ProにMicrosoft 365 E5。 詳細については、「What [is is Power BI?](https://go.microsoft.com/fwlink/?linkid=841341)
  
### <a name="use-reporting-services-on-premises"></a>レポート サービスの使用 (オンプレミス)

SQL Server Reporting Servicesは、堅牢なレポート ソリューションを提供します。 Reporting Services は、ネイティブ モードまたは統合モードSharePoint構成できます。 複数の異なるツールを使用してレポートを作成できます (レポート デザイナー、Report Builder、Power View。 最新のリリースのモバイル レポートSQL Server、モバイル レポート SQL ServerをPublisher、任意の画面サイズに合ったレポートを配信することもできます。 これにより、閲覧者はモバイル デバイスでレポートを使用できます。 詳細については、「モバイル およびページ[分割SQL Server Reporting Servicesレポートを作成、展開](/sql/reporting-services/create-deploy-and-manage-mobile-and-paginated-reports)、および管理する 」を参照してください。
  
### <a name="use-performancepoint-services-on-premises"></a>[PerformancePoint Servicesを使用する (オンプレミス)

PerformancePoint Server 2007 は、サーバー 2007 からSharePoint販売されました。 サーバー 2010 SharePointから、PerformancePoint Servicesサーバーのサービス アプリケーションSharePointします。 そのため、別のサーバー ライセンスまたはハードウェアを購入して、サーバー ライセンスを使用する必要PerformancePoint Services。
  
2007 PerformancePoint Server から PerformancePoint Services に移動するには、より新しいバージョンの SharePoint Server に移動し、PerformancePoint Services を構成します。 移動する SharePoint サーバーのバージョンは、2007 年から 2007 年の間に既存のダッシュボード コンテンツをインポートできるかどうかPerformancePoint Server決定PerformancePoint Services。
  
- SharePoint Server 2010 にアップグレードする場合は、PerformancePoint ダッシュボード コンテンツを PerformancePoint Server 2007 から PerformancePoint Services SharePoint Server 2010 にインポートできます。 詳細については、「Import [Wizard: PerformancePoint Server 2007 コンテンツから SharePoint Server 2010」を参照](/previous-versions/office/sharepoint-server-2010/ee681485(v=office.14))してください。
    
- SharePoint Server 2013 または SharePoint Server 2016 に移動する場合は、新しいダッシュボード コンテンツ (データ ソース、レポート、スコアカード、ダッシュボード ページ) を作成する必要があります。
    
アップグレード計画を開始するにはPerformancePoint Servicesリソースを参照してください。
  
- [SharePointServer 2007 のサポート終了ロードマップ](sharepoint-2007-end-of-support.md)
    
- 移行するバージョンがSharePoint場合は、対応する記事を参照PerformancePoint Services。
    
  - [プランのPerformancePoint Services (SharePoint Server 2010)](/previous-versions/office/sharepoint-server-2010/ee681486(v=office.14))
    
  - [PerformancePoint Services Server 2013 SharePointの概要](/sharepoint/administration/performancepoint-services-overview)
    
  - [SharePoint Server 2016 の PerformancePoint Services の概要](/sharepoint/administration/performancepoint-services-overview)
    
この機能にアップグレードPerformancePoint Services、いくつかの新機能と拡張機能が提供されます。 PerformancePoint Servicesスコアカードを提供しています。分解ツリーや KPI 詳細レポートなどの新しい視覚化。グラフの種類が多い。より優れたタイム インテリジェンス フィルター機能。アクセシビリティコンプライアンスの強化。 詳細については[、「What's new for PerformancePoint Services (SharePoint Server 2010)」を参照してください](/previous-versions/office/sharepoint-server-2010/ee661741(v=office.14))。
  
## <a name="where-can-i-get-help-with-my-upgrade"></a>アップグレードに関するヘルプはどこで受け取れるのですか?

オンプレミスにアップグレードする場合も、Microsoft 365に移行する場合も、Microsoft パートナーと一緒に作業することをお勧めします。 認定パートナーは、ビジネス ニーズに最適なソリューションを特定し、展開に役立ちます。 Microsoft パートナー [センターにアクセスし](https://go.microsoft.com/fwlink/?linkid=841249)、検索フィルターを使用してソリューション プロバイダーを検索します。
  
## <a name="related-topics"></a>関連トピック

[Office 2007 のサーバーとクライアントからのアップグレードに役立つリソース](upgrade-from-office-2007-servers-and-products.md)