---
title: Project Server 2007 のサポート終了ロードマップ
ms.author: efrene
author: efrene
manager: laurawi
ms.date: 1/31/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: IT_ProjectAdmin
search.appverid:
- MET150
- ZPJ120
- PJU120
- PJW120
ms.assetid: d379018f-72b7-4284-b40a-6c23c8ae38fe
description: 2017年10月10日に、Project Server 2007、Project ポートフォリオサーバー、および Project 2007 のサポートが終了しました。 この記事を使用して、今すぐアップグレードを計画します。
ms.openlocfilehash: f59b319ec39c6b2d1df0876c916332491f1bb0f6
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519801"
---
# <a name="project-server-2007-end-of-support-roadmap"></a>Project Server 2007 のサポート終了ロードマップ

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

2017で Office 2007 サーバーおよびアプリケーションのサポートが終了し、移行の計画を検討する必要があります。 現在 Project Server 2007 および関連製品を使用している場合は、次のサポート終了日に注意してください。
  
|**製品**|**サポート終了日**|
|:-----|:-----|
|Project Server 2007  <br/> |2017 年 10 月 10 日  <br/> |
|Project ポートフォリオサーバー2007  <br/> |2017 年 10 月 10 日  <br/> |
|Project 2007 Standard  <br/> |2017 年 10 月 10 日  <br/> |
|Project 2007 Professional  <br/> |2017 年 10 月 10 日  <br/> |
   
退職に到達する Office 2007 サーバーの詳細については、「 [Upgrade From office 2007 servers and client products](upgrade-from-office-2007-servers-and-products.md)」を参照してください。
  
## <a name="what-does-end-of-support-mean"></a>*サポート終了の* 意味

ほとんどの Microsoft 製品には、新機能、バグ修正、セキュリティ修正プログラムを入手するためのライフサイクルが用意されています。 このライフサイクルは通常、製品の最初のリリースから10年間続きます。 このライフサイクルの終了は、製品のサポート終了と呼ばれます。 Project Server 2007 は、2017年10月10日にサポート終了に達したため、Microsoft は提供しなくなりました。
  
- 発生する可能性のある問題のテクニカルサポート。
    
- サーバーの安定性と有用性に影響を与える可能性がある問題について、バグ修正が行われます。
    
- セキュリティ侵害に対してサーバーが脆弱になる可能性がある脆弱性に対するセキュリティ修正。
    
- タイム ゾーンの更新。
    
Project Server 2007 のインストールは、この日付以降も引き続き実行されます。 しかし、前述の変更点のため、できるだけ早く Project Server 2007 から移行することを強くお勧めします。
  
## <a name="what-are-my-options"></a>使用できるオプション

Project Server 2007 を使用している場合は、次のような移行オプションを調べる必要があります。
  
- Project Online への移行
    
- 新しいオンプレミスバージョンの Project Server に移行する (Project Server 2016 を推奨)
    
|**Project Online への移行を希望する理由**|**Project Server 2016 への移行を希望する理由**|
|:-----|:-----|
| モバイルユーザーがいます。  <br/> <br/>移行のコストは、重要な懸念事項 (ハードウェア、ソフトウェア、時間、および実装の労力) です。 <br/><br/>  移行後は、環境を維持するためのコストが大きな懸念事項になります (たとえば、自動更新、稼働状態の保証など)。  <br/> | ビジネスルールは、クラウドでのビジネスの運営から制限されています。<br/><br/>  環境に対して更新プログラムを制御する必要がある。  |
   
> [!NOTE]
> Office 2007 サーバーから移行するためのオプションの詳細については、「 [office 2007 サーバーおよびクライアントからのアップグレードに役立つリソース](upgrade-from-office-2007-servers-and-products.md)」を参照してください。 Project server と Project Online は同じリソース共有元を共有できないため、Project Server はハイブリッド構成をサポートしていないことに注意してください。 
  
## <a name="important-considerations-when-you-migrate-from-project-server-2007"></a>Project Server 2007 から移行する場合の重要な考慮事項

Project Server 2007 からの移行を計画する場合は、次の点を考慮してください。
  
- **Microsoft パートナーからのヘルプを取得** する-Project Server 2007 からのアップグレードは困難で、多くの準備と計画が必要になることがあります。 Project Server 2007 を最初にセットアップしたユーザーがいない場合は、特に難しいことがあります。 幸いなことに、Project Server 2016 への移行または Project Online への移行を計画しているかどうかを判断できる Microsoft パートナーがあります。 Microsoft パートナーを検索して、 [Microsoft パートナーセンター](https://go.microsoft.com/fwlink/p/?linkid=841249)での移行に役立てることができます。 「  *ゴールドプロジェクトとポートフォリオ管理」と* いう用語を検索して、project の専門知識を持つすべての Microsoft パートナーの一覧を表示します。 
    
- **カスタマイズを計画** する-project server 2016 または project Online に移行する場合、project server 2007 環境で行ったカスタマイズの多くが機能しない可能性があります。 バージョン間の Project Server アーキテクチャには大きな違いがあります。 必要なオペレーティングシステム、データベースサーバー、およびサポートされているクライアント web ブラウザーも異なる。 新しい環境のカスタマイズをテストまたは再構築する方法を計画します。 また、計画によって、各カスタマイズが依然として必要かどうかを検討することもできます。 詳細については、「[Create a plan for current customizations during upgrade to SharePoint 2013](https://go.microsoft.com/fwlink/p/?linkid=842061)」を参照してください。 
    
- **時間および** アップグレードの計画、実行、およびテストは、特に Project Server 2016 にアップグレードする場合は、時間と労力を要します。 たとえば、Project Server 2007 から Project Server 2016 に移行する場合は、最初に Project Server 2010 に移行し、データをチェックして、以降の各バージョンに移行するときに同じ操作を実行する必要があります。 Microsoft パートナーに確認して、どのくらいの時間とコストがかかるかについての予測を得ることができます。
    
## <a name="migrate-to-project-online"></a>Project Online への移行

Project Server 2007 から Project Online に移行することを選択した場合は、次の操作を実行して、プロジェクト計画のデータを手動で移行できます。
  
1. プロジェクト計画を Project Server 2003 から .mpp 形式で保存します。
    
2. Project Professional 2013、Project Professional 2016、または Project Online デスクトップクライアントで、各 .mpp ファイルを開き、を保存して Project Online に発行します。
    
Project Online で Microsoft Project Web App (PWA) 構成を手動で作成できます。 たとえば、必要なユーザー設定フィールドまたはエンタープライズカレンダーを再作成します。 Microsoft パートナーもこのプロセスに役立てることができます。
  
主なリソース:
  
|**Resource**|**説明**|
|:-----|:-----|
|[Project Online の使用を開始する](https://support.office.com/article/e3e5f64f-ada5-4f9d-a578-130b2d4e5f11) <br/> |Project Online をセットアップして使用する方法 <br/> |
|[Project Online サービスの説明](https://go.microsoft.com/fwlink/p/?linkid=829088) <br/> |利用可能なさまざまな Project Online プランに関する情報 <br/> |
   
## <a name="migrate-to-a-newer-on-premises-version-of-project-server"></a>新しいオンプレミスバージョンの Project Server に移行する

Project Online に移行することによって、最高の価値とユーザーの利便性を得られるというのは強く信じられません。 また、一部の組織では、オンプレミス環境にプロジェクトデータを保持する必要があることも理解しています。 プロジェクトデータをオンプレミスで保持することを選択した場合は、project server 2007 環境を Project server 2010、Project Server 2013、または Project Server 2016 に移行できます。
  
Project Online に移行できない場合は、Project Server 2016 に移行することをお勧めします。 Project Server 2016 には、以前のリリースの Project Server のすべての機能が含まれています。 Project Online で利用できる機能に最も近いものがありますが、一部の機能は Project online でのみ利用可能です。
  
移行のたびに、データが正常に移行されたことを確認する必要があります。
  
> [!NOTE]
>
  
### <a name="how-do-i-migrate-to-project-server-2016"></a>Project Server 2016 に移行する方法

Project Server 2007 と Project Server 2016 のアーキテクチャ上の相違点は、直接移行パスを回避できます。 そのため、project server 2016 に到達するまで、project server の各バージョンの project Server に Project Server 2007 データを移行する必要があります。
  
Project Server 2016 について、次の手順を実行します。
  
1. Project Server 2007 から Project Server 2010 に移行します。
    
2. プロジェクトサービス2010から Project Server 2013 に移行します。
    
3. Project Server 2013 から Project Server 2016 に移行します。
    
移行のたびに、データが正常に移行されたことを確認してください。
  
### <a name="step-1-migrate-from-project-server-2007-to-project-server-2010"></a>手順 1: Project Server 2007 から Project Server 2010 に移行する

Project Server 2007 から Project Server 2010 にアップグレードするために必要な作業についての包括的な説明については、「 [upgrade To Project server 2010](https://go.microsoft.com/fwlink/p/?linkid=841812)」を参照してください。
  
主なリソース:
  
|**Resource**|**説明**|
|:-----|:-----|
|[Project Server 2010 アップグレードの概要](https://go.microsoft.com/fwlink/p/?linkid=841813) <br/> |Project Server 2007 から Project Server 2010 にアップグレードするために必要な作業の概要を説明します。 <br/> |
|[Project Server 2010 へのアップグレードを計画する](https://go.microsoft.com/fwlink/p/?linkid=841815) <br/> |Project Server 2007 から Project Server 2010 (システム要件を含む) にアップグレードするときの計画に関する考慮事項  <br/> |
   
#### <a name="how-do-i-upgrade"></a>アップグレードする方法

詳細については、「 [Upgrade To Project Server 2010](https://go.microsoft.com/fwlink/p/?linkid=841812)」を参照してください。 ただし、アップグレードに使用できる2つの異なる方法があることを理解しておくことが重要です。
  
- **データベース接続アップグレード:** この方法では、構成設定ではなく、環境のコンテンツのみがアップグレードされます。 Office Project Server 2007 から、32ビットのサーバーオペレーティングシステムのみをサポートするハードウェアに展開されている場合は、アップグレードする必要があります。 データベース接続アップグレードには、次の2種類の方法があります。
    
  - **データベース-アタッチ *完全アップグレード*** -Office project Server 2007 データベースに格納されているプロジェクトデータ、および SharePoint コンテンツデータベースに格納されている Microsoft project Web App サイトデータを移行します。
    
  - **データベース接続 *コアアップグレード*** -project Server データベースに格納されているプロジェクトデータのみを移行します。
    
- **一括アップグレード**: ファームの構成データとファームのすべてのコンテンツは、既存のハードウェアの固定の順序でアップグレードされます。 アップグレードプロセスを開始すると、セットアップはファーム全体をオフラインにします。 Web サイトと Microsoft Project Web App サイトは、アップグレードが完了するまで使用できません。セットアップはサーバーを再起動します。 一括アップグレードを開始した後は、アップグレードを一時停止したり、以前のバージョンにロールバックしたりすることはできません。 運用環境ではなく、運用環境のミラー化されたイメージを作成し、この環境への一括アップグレードを実行することをお勧めします。 
    
追加情報:
  
- [Microsoft Project Server 2010 アップグレードの SuperFlow](https://go.microsoft.com/fwlink/p/?linkid=841277)
    
- [Project Server 2007 から Project Server 2010 への移行](https://go.microsoft.com/fwlink/p/?linkid=841278)
    
- [Project Web App Web パーツのアップグレードに関する考慮事項](https://go.microsoft.com/fwlink/p/?linkid=841276)
    
- [Project Software Development Kit (SDK)](https://go.microsoft.com/fwlink/p/?linkid=841275)
    
### <a name="step-2-migrate-to-project-server-2013"></a>手順 2: Project Server 2013 に移行する

データが正常に移行されたことを確認したら、次の手順は Project Server 2013 に移行することです。
  
Project Server 2010 から Project Server 2013 にアップグレードするために必要な作業についての包括的な説明については、「 [upgrade To Project server 2013](https://go.microsoft.com/fwlink/p/?linkid=841822)」を参照してください。 
  
主なリソース:
  
|**Resource**|**説明**|
|:-----|:-----|
|[Project Server 2013 のアップグレード プロセスの概要](https://go.microsoft.com/fwlink/p/?linkid=841822) <br/> |Project Server 2010 から Project Server 2013 にアップグレードするために必要な作業の概要  <br/> |
|[Project Server 2013 へのアップグレードを計画する](https://go.microsoft.com/fwlink/p/?linkid=841823) <br/> |Project Server 2010 から Project Server 2013 (システム要件を含む) にアップグレードするときの計画に関する考慮事項 <br/> |
   
#### <a name="things-to-know-about-upgrading-to-this-version"></a>このバージョンへのアップグレードに関する注意事項

[Project Server 2013 アップグレードの新機能](https://go.microsoft.com/fwlink/p/?linkid=841824) このバージョンでのアップグレードに関する重要な変更点について説明します。 最も注目すべき点は次のとおりです。 
  
- Project Server 2013 への一括アップグレードはありません。 Project Server 2010 から Project Server 2013 へのアップグレードでサポートされている唯一の方法は、データベース接続方式です。
    
- アップグレードプロセスでは、Project Server 2010 のデータを Project server 2013 形式に変換するだけでなく、4つの Project Server 2010 データベースを1つの Project Web App データベースに統合することもできます。
    
- 2013のバージョンでは、SharePoint Server と Project Server の両方がクレームベース認証に変更されました。 従来の認証を使用している場合は、アップグレードのためにこの要因を考慮する必要があります。 詳細については、「[SharePoint 2013 でクラシックモードからクレームベース認証に移行する](https://go.microsoft.com/fwlink/p/?linkid=841825)」を参照してください。
    
追加情報:
  
- [Project Server 2013 へのアップグレード プロセスの概要](https://go.microsoft.com/fwlink/p/?linkid=841274)
    
- [データベースおよび Project Web App サイト コレクションをアップグレードする (Project Server 2013)](https://go.microsoft.com/fwlink/p/?linkid=841272)
    
- [Microsoft Project Server のアップグレードプロセスの図](https://go.microsoft.com/fwlink/p/?linkid=841270)
    
- [高度なデータベース統合、Project Server 2010 から2013への移行は、簡単な手順で8つ](https://go.microsoft.com/fwlink/p/?linkid=841271)
    
### <a name="step-3-migrate-to-project-server-2016"></a>手順 3: Project Server 2016 に移行する

データが正常に移行されたことを確認したら、次の手順は Project Server 2016 に移行することです。
  
Project Server 2013 から Project Server 2016 にアップグレードするために必要な作業についての包括的な説明については、「 [upgrade To Project server 2016](https://docs.microsoft.com//project/upgrading-to-project-server-2016)」を参照してください。
  
主なリソース:
  
|**Resource**|**説明**|
|:-----|:-----|
|[Project Server 2016 のアップグレード プロセスの概要](https://go.microsoft.com/fwlink/p/?linkid=841260) <br/> |Project Server 2013 から Project Server 2016 にアップグレードするために必要な作業の概要 <br/> |
|[Project Server 2016 へのアップグレードを計画する](https://go.microsoft.com/fwlink/p/?linkid=841826) <br/> |Project Server 2013 から Project Server 2016 へのアップグレードを計画する際の考慮事項 <br/> |
   
#### <a name="things-to-know-about-upgrading-to-this-version"></a>このバージョンへのアップグレードに関する注意事項

[Project Server 2016 アップグレードに関して知っておく必要のある](https://go.microsoft.com/fwlink/p/?linkid=841827) ことは、このバージョンのアップグレードに関する重要な変更点を示しています。次のようにします。
  
- Project server の2013データを移行する Project Server 2016 環境を作成すると、Project server の2016インストールファイルが SharePoint Server 2016 に含まれます。 詳細については、「 [Deploy Project Server 2016](https://go.microsoft.com/fwlink/p/?linkid=841829)」を参照してください。
    
- Project Server 2016 では、リソース計画は廃止されました。 Project Server 2013 のリソース計画は、project Server 2016 および Project Online のリソース予約に移行されます。 詳細については、「 [概要: リソース予約](https://support.office.com/article/73eefb5a-81fe-42bf-980e-9532b1bdc870) 」を参照してください。 
    
## <a name="migrate-from-portfolio-server-2007"></a>ポートフォリオサーバーからの移行2007

プロジェクトポートフォリオサーバー2007は、ポートフォリオ戦略、優先度設定、および最適化のために Project Server 2007 で使用されていました。 このバージョン以降、プロジェクトポートフォリオサーバーの追加バージョンは作成されていません。 ただし、ポートフォリオ管理機能は project Server 2016 および Project Online の Premium バージョンで利用できます。 しかし、プロジェクトポートフォリオサーバー2007からのデータは、どちらかに移行できません。 ビジネスドライバーなどのデータは再作成する必要があります。
  
その他のリソース：
  
- [Project Online サービスの説明:](https://go.microsoft.com/fwlink/p/?linkid=841280) Project Server 2016 および Project Online Premium に含まれているポートフォリオ管理機能を参照してください。
    
- [Microsoft Office Project ポートフォリオサーバー2007移行ガイド。](https://go.microsoft.com/fwlink/p/?linkid=841279)
    
## <a name="related-topics"></a>関連トピック

[SharePoint Server 2007 サポート終了ロードマップ](sharepoint-2007-end-of-support.md)
  
[Office 2007 のサーバーとクライアントからのアップグレードに役立つリソース](upgrade-from-office-2007-servers-and-products.md)
  
