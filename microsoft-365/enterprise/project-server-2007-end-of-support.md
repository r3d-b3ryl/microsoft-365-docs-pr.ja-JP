---
title: Project Server 2007 のサポート終了ロードマップ
ms.author: efrene
author: efrene
manager: scotv
ms.date: 1/31/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
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
description: 2017 年 10 月 10 日に、Project Server 2007、Project ポートフォリオ サーバー、Project 2007 のサポートが終了しました。 この記事を使用して、今すぐアップグレードを計画します。
ms.openlocfilehash: 1c46a0c422a0eb66b4991589a0996092c40f5fba
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65090189"
---
# <a name="project-server-2007-end-of-support-roadmap"></a>Project Server 2007 のサポート終了ロードマップ

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

Office 2017 年に 2007 台のサーバーとアプリケーションのサポートが終了しました。移行の計画を検討する必要があります。 現在、Project Server 2007 および関連製品を使用している場合は、次のサポート終了日に注意してください。
  
|**製品**|**サポート終了日**|
|:-----|:-----|
|Project Server 2007  <br/> |2017 年 10 月 10 日  <br/> |
|Project ポートフォリオ サーバー 2007  <br/> |2017 年 10 月 10 日  <br/> |
|Project 2007 Standard  <br/> |2017 年 10 月 10 日  <br/> |
|Project 2007 Professional  <br/> |2017 年 10 月 10 日  <br/> |
   
Office 2007 サーバーの廃止に向けた詳細については、「[Office 2007 サーバーとクライアント製品からのアップグレード](upgrade-from-office-2007-servers-and-products.md)」を参照してください。
  
## <a name="what-does-end-of-support-mean"></a>*サポート終了とは* どういう意味ですか?

ほとんどの Microsoft 製品には、新機能、バグ修正、セキュリティ修正などのサポート ライフサイクルがあります。 このライフサイクルは通常、製品の初期リリースから 10 年間続きます。 このライフサイクルの終了は、製品のサポート終了と呼ばれます。 Project Server 2007 は 2017 年 10 月 10 日にサポートの終了に達したため、Microsoft では次の機能は提供されなくなりました。
  
- 発生する可能性がある問題のテクニカル サポート。
    
- サーバーの安定性と使いやすさに影響を与える可能性がある問題に関するバグ修正。
    
- サーバーがセキュリティ違反に対して脆弱になる可能性がある脆弱性に対するセキュリティ修正。
    
- タイム ゾーンの更新。
    
Project Server 2007 のインストールは、この日以降も引き続き実行されます。 ただし、前述の変更のため、できるだけ早くProject Server 2007 から移行することを強くお勧めします。
  
## <a name="what-are-my-options"></a>使用できるオプション

Project Server 2007 を使用している場合は、次の移行オプションを調べる必要があります。
  
- Project Onlineに移行する
    
- 新しいオンプレミス バージョンの Project Server に移行する (できればProject Server 2016)
    
|**Project Onlineに移行する理由**|**Project Server 2016に移行する理由**|
|:-----|:-----|
| モバイル ユーザーがいます。  <br/> <br/>移行にかかるコストは大きな懸念事項です (ハードウェア、ソフトウェア、時間、実装にかかる労力)。 <br/><br/>  移行後、環境を維持するためのコストは大きな懸念事項です (自動更新、稼働時間の保証など)。  <br/> | ビジネス ルールを使用すると、クラウドでのビジネスの運用が制限されます。<br/><br/>  環境の更新を制御する必要があります。  |
   
> [!NOTE]
> Office 2007 サーバーから移行するためのオプションの詳細については、[Office 2007 サーバーとクライアントからのアップグレードに役立つリソース](upgrade-from-office-2007-servers-and-products.md)に関するページを参照してください。 Project サーバーとProject Onlineは同じリソース プールを共有できないため、Project Server はハイブリッド構成をサポートしていません。 
  
## <a name="important-considerations-when-you-migrate-from-project-server-2007"></a>Project Server 2007 から移行する場合の重要な考慮事項

Project Server 2007 から移行する場合は、次の点を考慮してください。
  
- **Microsoft パートナーのサポートを受ける** - Project Server 2007 からのアップグレードは困難な場合があり、多くの準備と計画が必要です。 最初に Server 2007 を設定したユーザーでない場合は、特に困難Project可能性があります。 幸いにも、Project Server 2016に移行するか、Project Onlineに移行するかを問わず、Microsoft パートナーがサポートを提供しています。 Microsoft パートナー センターでの移行に役立つ [Microsoft パートナー](https://go.microsoft.com/fwlink/p/?linkid=841249)を検索します。 *Gold Project とポートフォリオ管理* という用語を検索して、Projectに関する専門知識を持つすべての Microsoft パートナーの一覧を表示します。 
    
- **カスタマイズを計画する** - Project Server 2007 環境で行ったカスタマイズの多くは、Project Server 2016またはProject Onlineに移行しても機能しない可能性があります。 Project サーバー アーキテクチャには、バージョン間で大きな違いがあります。 サポートされている必要なオペレーティング システム、データベース サーバー、およびクライアント Web ブラウザーも異なります。 新しい環境のカスタマイズをテストまたは再構築する方法を計画します。 計画では、各カスタマイズがまだ必要かどうかを検討する良い機会も提供されます。 詳細については、「[Create a plan for current customizations during upgrade to SharePoint 2013](/SharePoint/upgrade-and-update/create-a-communication-plan-for-the-upgrade-to-sharepoint-2013)」を参照してください。 
    
- **時間と忍耐** - アップグレードの計画、実行、テストには時間と労力がかかります。特にProject Server 2016にアップグレードする場合。 たとえば、Project Server 2007 から Project Server 2016に移行する場合は、最初に Project Server 2010 に移行し、データを確認してから、後続の各バージョンに移行するときに同じ操作を行う必要があります。 Microsoft パートナーに問い合わせて、所要時間とコストの見積もりを取得することもできます。
    
## <a name="migrate-to-project-online"></a>Project Onlineに移行する

Project Server 2007 から Project Onlineに移行することを選択した場合は、次の操作を行ってプロジェクト 計画データを手動で移行できます。
  
1. プロジェクト プランを Project Server 2003 から .mpp 形式に保存します。
    
2. Project Professional 2013、Project Professional 2016、またはProject Online デスクトップ クライアントで、各 .mpp ファイルを開き、それを保存してProject Onlineに発行します。
    
Project Onlineで、Microsoft Project Web アプリ (PWA) 構成を手動で作成できます。 たとえば、必要なユーザー設定フィールドやエンタープライズ カレンダーを再作成します。 Microsoft パートナーは、このプロセスを支援することもできます。
  
主なリソース:
  
|**Resource**|**説明**|
|:-----|:-----|
|[Project Online の使用を開始する](https://support.office.com/article/e3e5f64f-ada5-4f9d-a578-130b2d4e5f11) <br/> |Project Onlineを設定して使用する方法 <br/> |
|[Project Online サービスの説明](/office365/servicedescriptions/project-online-service-description/project-online-service-description) <br/> |利用可能なさまざまなProject Onlineプランに関する情報 <br/> |
   
## <a name="migrate-to-a-newer-on-premises-version-of-project-server"></a>新しいオンプレミス バージョンの Project Server に移行する

Project Onlineに移行することで、お客様が最高の価値とユーザー エクスペリエンスを得られると強く信じています。 ただし、一部の組織では、オンプレミス環境でプロジェクト データを保持する必要があることを理解しています。 プロジェクト データをオンプレミスに保持する場合は、Project Server 2007 環境を Project Server 2010、Project Server 2013、またはProject Server 2016に移行できます。
  
Project Onlineに移行できない場合は、Project Server 2016に移行することをお勧めします。 Project Server 2016には、Project Server の以前のリリースのすべての機能が含まれています。 Project Onlineで利用できるエクスペリエンスと最もよく一致しますが、一部の機能はProject Onlineでのみ使用できます。
  
移行のたびに、データが正常に移行されたことを確認する必要があります。
  
> [!NOTE]
>
  
### <a name="how-do-i-migrate-to-project-server-2016"></a>Project Server 2016に移行操作方法?

Project Server 2007 と Project Server 2016のアーキテクチャ上の違いにより、直接移行パスが回避されます。 そのため、Project Server 2016に到達するまで、Project Server 2007 データをProject Server の後続の各バージョンに移行する必要があります。
  
次の手順に従ってProject Server 2016します。
  
1. Project Server 2007 から Project Server 2010 に移行します。
    
2. Project Serve 2010 から Project Server 2013 に移行します。
    
3. Project Server 2013 から Project Server 2016に移行します。
    
各移行後、データが正常に移行されたことを確認します。
  
### <a name="step-1-migrate-from-project-server-2007-to-project-server-2010"></a>手順 1: Project Server 2007 から Project Server 2010 に移行する

Project Server 2007 から Project Server 2010 にアップグレードするために必要な操作の包括的な説明については、「[Project Server 2010 へのアップグレード](/previous-versions/office/project-server-2010/gg502590(v=office.14))」を参照してください。
  
主なリソース:
  
|**Resource**|**説明**|
|:-----|:-----|
|[Project Server 2010 アップグレードの概要](/previous-versions/office/project-server-2010/ee662496(v=office.14)) <br/> |Project Server 2007 から Project Server 2010 にアップグレードするために必要な操作の概要 <br/> |
|[Project Server 2010 へのアップグレードを計画する](/previous-versions/office/project-server-2010/ff603505(v=office.14)) <br/> |Project Server 2007 から Project Server 2010 にアップグレードするときの計画に関する考慮事項 (システム要件を含む)  <br/> |
   
#### <a name="how-do-i-upgrade"></a>アップグレード操作方法?

詳細については、「[Project Server 2010 へのアップグレード](/previous-versions/office/project-server-2010/gg502590(v=office.14))」を参照してください。 ただし、アップグレードに使用できる 2 つの異なる方法があることを理解しておくことが重要です。
  
- **データベースアタッチアップグレード:** この方法では、構成設定ではなく、環境のコンテンツのみがアップグレードされます。 32 ビット サーバー オペレーティング システムのみをサポートするハードウェアに展開されている Office Project Server 2007 からアップグレードする場合に必要です。 データベース接続アップグレード方法には、次の 2 種類があります。
    
  - **データベースアタッチ *の完全アップグレード*** - Office Project Server 2007 データベースに格納されているプロジェクト データと、SharePoint コンテンツ データベースに格納されているMicrosoft Project Web アプリ サイト データを移行します。
    
  - **データベースアタッチ *コア アップグレード*** - Project Server データベースに格納されているプロジェクト データのみを移行します。
    
- **インプレース アップグレード**: ファームの構成データとファーム上のすべてのコンテンツは、固定順序で既存のハードウェアでアップグレードされます。 アップグレード プロセスを開始すると、セットアップによってファーム全体がオフラインになります。 Web サイトとMicrosoft Project Web アプリ サイトは、アップグレードが完了し、サーバーを再起動するまで使用できません。 インプレース アップグレードを開始した後は、アップグレードを一時停止したり、以前のバージョンにロールバックしたりすることはできません。 運用環境のミラー化されたイメージを作成し、運用環境ではなく、この環境へのインプレース アップグレードを行うことをお勧めします。 
    
追加情報:
  
- [Microsoft Project Server 2010 アップグレード用 SuperFlow](/samples/browse/?redirectedfrom=TechNet-Gallery)
    
- [Project Server 2007 から Project Server 2010 への移行](/samples/browse/?redirectedfrom=TechNet-Gallery)
    
- [Project Web App Web パーツのアップグレードに関する考慮事項](/previous-versions/office/project-server-2010/gg314581(v=office.14))
    
- [Project ソフトウェア開発キット (SDK)](/previous-versions/office/developer/office-2010/ms481966(v=office.14))
    
### <a name="step-2-migrate-to-project-server-2013"></a>手順 2: Project Server 2013 に移行する

データが正常に移行されたことを確認したら、次の手順では Project Server 2013 に移行します。
  
Project Server 2010 から Project Server 2013 にアップグレードするために必要な操作の包括的な説明については、「[Project Server 2013 へのアップグレード](/project/upgrade-to-project-server-2016)」を参照してください。 
  
主なリソース:
  
|**Resource**|**説明**|
|:-----|:-----|
|[Project Server 2013 のアップグレード プロセスの概要](/project/upgrade-to-project-server-2016) <br/> |Project Server 2010 から Project Server 2013 へのアップグレードに必要な操作の概要  <br/> |
|[Project Server 2013 へのアップグレードを計画する](/project/plan-for-upgrade-to-project-server-2016) <br/> |Project Server 2010 から Project Server 2013 にアップグレードするときの計画に関する考慮事項 (システム要件を含む) <br/> |
   
#### <a name="things-to-know-about-upgrading-to-this-version"></a>このバージョンへのアップグレードについて知っておくべきこと

[Project Server 2013 のアップグレードの新機能](/project/what-s-new-in-project-server-2013-upgrade)では、このバージョンのアップグレードに関する重要な変更について説明します。 最も注目すべきは次のとおりです。 
  
- Project Server 2013 へのインプレース アップグレードはありません。 データベースアタッチメソッドは、Project Server 2010 から Project Server 2013 にアップグレードするためにサポートされている唯一の方法です。
    
- アップグレード プロセスでは、Project Server 2010 データを Project Server 2013 形式に変換するだけでなく、4 つのProject Server 2010 データベースを単一のProject Web App データベースに統合します。
    
- 2013 バージョンでは、SharePoint サーバーとProject サーバーの両方が要求ベースの認証に変更されました。 クラシック認証を使用している場合は、アップグレードにこの要因を考慮する必要があります。 詳細については、「[SharePoint 2013 でクラシックモードからクレームベース認証に移行する](/sharepoint/security-for-sharepoint-server/security-for-sharepoint-server)」を参照してください。
    
追加情報:
  
- [Project Server 2013 へのアップグレード プロセスの概要](/project/overview-of-the-project-server-2016-upgrade-process)
    
- [データベースおよび Project Web App サイト コレクションをアップグレードする (Project Server 2013)](/project/upgrading-to-project-server-2016)
    
- [Microsoft Project サーバーアップグレード プロセスの図](https://go.microsoft.com/fwlink/p/?linkid=841270)
    
- [優れたデータベース統合、Project Server 2010 から 2013 への移行 (8 つの簡単な手順)](https://go.microsoft.com/fwlink/p/?linkid=841271)
    
### <a name="step-3-migrate-to-project-server-2016"></a>手順 3: Project Server 2016に移行する

データが正常に移行されたことを確認したら、次の手順ではProject Server 2016に移行します。
  
Project Server 2013 から Project Server 2016にアップグレードするために必要な操作の包括的な説明については、「[Project Server 2016へのアップグレード」を](//project/upgrading-to-project-server-2016)参照してください。
  
主なリソース:
  
|**Resource**|**説明**|
|:-----|:-----|
|[Project Server 2016 のアップグレード プロセスの概要](/previous-versions/office/project-server-2010/ee662104(v=office.14)) <br/> |Project Server 2013 から Project Server 2016にアップグレードするために必要な操作の概要 <br/> |
|[Project Server 2016 へのアップグレードを計画する](/project/plan-for-upgrade-to-project-server-2016) <br/> |Project Server 2013 から Project Server 2016 にアップグレードする計画に関する考慮事項 <br/> |
   
#### <a name="things-to-know-about-upgrading-to-this-version"></a>このバージョンへのアップグレードについて知っておくべきこと

[Project Server 2016アップグレードについて知](/project/plan-for-upgrade-to-project-server-2016)っておくべきことは、このバージョンのアップグレードに関するいくつかの重要な変更を示しています。これには次のものが含まれます。
  
- Project Server 2013 データを移行するProject Server 2016環境を作成すると、Project Server 2016 インストール ファイルが SharePoint Server 2016 に含まれます。 詳細については、「[Project Server 2016のデプロイ」を](/project/deploy-project-server-2016)参照してください。
    
- リソース プランは、Project Server 2016で非推奨になりました。 Project Server 2013 リソース プランは、Project Server 2016およびProject Onlineの Resource Engagements に移行されます。 詳細については、「 [概要: リソースエンゲージメント](https://support.office.com/article/73eefb5a-81fe-42bf-980e-9532b1bdc870) 」を参照してください。 
    
## <a name="migrate-from-portfolio-server-2007"></a>ポートフォリオ サーバー 2007 から移行する

Projectポートフォリオ サーバー 2007 は、ポートフォリオ戦略、優先順位付け、最適化のためにProject Server 2007 と共に使用されました。 このバージョン以降、Project ポートフォリオ サーバーの追加バージョンは作成されませんでした。 ただし、ポートフォリオ管理機能は、Project Server 2016およびProject Onlineのプレミアム バージョンで使用できます。 ただし、ポートフォリオ サーバー 2007 Projectからのデータは、どちらのデータにも移行できません。 ビジネス ドライバーなどのデータを再作成する必要があります。
  
その他のリソース：
  
- [Project Online サービスの説明:](/office365/servicedescriptions/project-online-service-description/project-online-service-description) Project Server 2016とProject Online Premiumに含まれるポートフォリオ管理機能を参照してください。
    
- [ポートフォリオ サーバー 2007 移行ガイドMicrosoft Office Project。](https://go.microsoft.com/fwlink/p/?linkid=841279)
    
## <a name="related-topics"></a>関連項目

[SharePoint Server 2007 のサポート終了ロードマップ](sharepoint-2007-end-of-support.md)
  
[Office 2007 のサーバーとクライアントからのアップグレードに役立つリソース](upgrade-from-office-2007-servers-and-products.md)
