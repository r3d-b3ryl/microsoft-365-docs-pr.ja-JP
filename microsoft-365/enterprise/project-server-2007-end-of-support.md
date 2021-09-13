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
description: 2017 年 10 月 10 日、Project Server 2007、Project ポートフォリオ サーバー、および Project 2007 のサポートが終了しました。 この記事を使用して、今すぐアップグレードを計画します。
ms.openlocfilehash: 12447eb2a021b3f92e3557b2c3ea87e859841346
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59220710"
---
# <a name="project-server-2007-end-of-support-roadmap"></a>Project Server 2007 のサポート終了ロードマップ

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

2017 年Office 2007 サーバーとアプリケーションのサポートは終了し、移行の計画を検討する必要があります。 現在、サーバー 2007 およびProject製品を使用している場合は、次のサポート終了日に注意してください。
  
|**Product**|**サポート終了日**|
|:-----|:-----|
|Project Server 2007  <br/> |2017 年 10 月 10 日  <br/> |
|ProjectPortfolio Server 2007  <br/> |2017 年 10 月 10 日  <br/> |
|Project 2007 Standard  <br/> |2017 年 10 月 10 日  <br/> |
|Project 2007 Professional  <br/> |2017 年 10 月 10 日  <br/> |
   
2007 サーバーのOfficeについては[、「Upgrade from Office 2007 サーバー](upgrade-from-office-2007-servers-and-products.md)とクライアント製品」を参照してください。
  
## <a name="what-does-end-of-support-mean"></a>サポート終了 *とはどういう意味* ですか?

ほとんどの Microsoft 製品には、新機能、バグ修正、セキュリティ修正など、サポート ライフサイクルがあります。 このライフサイクルは、通常、製品の最初のリリースから 10 年間続く。 このライフサイクルの終了は、製品のサポート終了と呼ばれる。 2017 Project Server 2007 が 2017 年 10 月 10 日にサポートの終了に達したため、Microsoft は次の機能を提供しなくなりました。
  
- 発生する可能性のある問題に対するテクニカル サポート。
    
- サーバーの安定性と使いやすさに影響を与える可能性がある問題のバグ修正。
    
- サーバーがセキュリティ侵害に対して脆弱になる可能性のある脆弱性に対するセキュリティ修正。
    
- タイム ゾーンの更新。
    
サーバー 2007 Projectのインストールは、この日付以降も実行されます。 ただし、前に示した変更のため、Project Server 2007 からすぐに移行することを強く推奨します。
  
## <a name="what-are-my-options"></a>使用できるオプション

サーバー 2007 Projectを使用している場合は、次の移行オプションを確認する必要があります。
  
- 移行してProject Online
    
- 新しいオンプレミス バージョンの Project サーバーに移行する (Project Server 2016)
    
|**移行先に移行する理由Project Online**|**移行先に移行する理由Project Server 2016**|
|:-----|:-----|
| モバイル ユーザーがいます。  <br/> <br/>移行のコストは大きな懸念事項です (ハードウェア、ソフトウェア、時間、実装の労力)。 <br/><br/>  移行後、環境を維持するためのコストは大きな懸念事項です (自動更新、保証されたアップタイムなど)。  <br/> | ビジネス ルールは、クラウドでのビジネスの運用を制限します。<br/><br/>  環境の更新を制御する必要があります。  |
   
> [!NOTE]
> Office 2007 サーバーから移行するためのオプションの詳細については、「Office [2007](upgrade-from-office-2007-servers-and-products.md)サーバーとクライアントからのアップグレードに役立つリソース」を参照してください。 Projectサーバーとサーバーは同じリソース プールを共有できないProjectサーバーはハイブリッド構成をサポートProject Online注意してください。 
  
## <a name="important-considerations-when-you-migrate-from-project-server-2007"></a>サーバー 2007 から移行する際Project考慮事項

サーバー 2007 から移行する予定の場合は、次Project検討してください。
  
- **Microsoft パートナーのサポートを受** ける - サーバー 2007 Projectアップグレードは困難な場合があります。多くの準備と計画が必要です。 サーバー 2007 を最初にセットアップしたユーザーでなかった場合は、Project難しい場合があります。 幸いなことに、Microsoft パートナーは、移行を計画している場合も、Project Server 2016に移行Project Online。 Microsoft パートナー センターでの移行に役立つ Microsoft パートナー [を検索します](https://go.microsoft.com/fwlink/p/?linkid=841249)。 「Gold *Project」および「* ポートフォリオ管理」という用語を検索して、Microsoft パートナーの専門知識を持つすべてのパートナーの一覧をProject。 
    
- **カスタマイズを計画する**- Project Server 2007 環境で行ったカスタマイズの多くは、Project Server 2016 または Project Online に移行するときに機能しない可能性があります。 バージョン間でサーバー アーキテクチャProject大きな違いがあります。 サポートされる必要なオペレーティング システム、データベース サーバー、およびクライアント Web ブラウザーも異なります。 新しい環境のカスタマイズをテストまたは再構築する方法を計画します。 計画は、各カスタマイズがまだ必要かどうかを検討する良い機会を提供します。 詳細については、「[Create a plan for current customizations during upgrade to SharePoint 2013](/SharePoint/upgrade-and-update/create-a-communication-plan-for-the-upgrade-to-sharepoint-2013)」を参照してください。 
    
- **時間と忍耐**- アップグレードの計画、実行、およびテストには時間と労力が必要です(特に、アップグレードを実行する場合はProject Server 2016。 たとえば、Project Server 2007 から Project Server 2016 に移行する場合は、最初に Project Server 2010 に移行し、データを確認してから、連続する各バージョンに移行するときに同じ操作を行う必要があります。 Microsoft パートナーに確認して、かかる時間とコストの見積もりを取得できます。
    
## <a name="migrate-to-project-online"></a>移行してProject Online

サーバー 2007 から Projectへの移行をProject Online場合は、次の操作を行って、プロジェクト 計画データを手動で移行できます。
  
1. プロジェクト 計画をサーバー 2003 Project .mpp 形式に保存します。
    
2. 2013 Project Professional、Project Professional 2016、または Project Online デスクトップ クライアントで、各 .mpp ファイルを開き、そのファイルを保存し、Project Online に発行します。
    
Web App (Microsoft Project) 構成は、PWAで手動でProject Online。 たとえば、必要なユーザー設定フィールドやエンタープライズ カレンダーを再作成します。 Microsoft パートナーは、このプロセスにも役立ちます。
  
主なリソース:
  
|**Resource**|**説明**|
|:-----|:-----|
|[Project Online の使用を開始する](https://support.office.com/article/e3e5f64f-ada5-4f9d-a578-130b2d4e5f11) <br/> |ユーザー設定と使用方法Project Online <br/> |
|[Project Onlineサービスの説明](/office365/servicedescriptions/project-online-service-description/project-online-service-description) <br/> |利用可能なさまざまなProject Onlineプランに関する情報 <br/> |
   
## <a name="migrate-to-a-newer-on-premises-version-of-project-server"></a>新しいオンプレミス バージョンの Project サーバーに移行する

お客様が最適な価値とユーザー エクスペリエンスを得たと強く信じています。Project Online。 ただし、一部の組織では、プロジェクト データをオンプレミス環境に保持する必要がある場合もあります。 プロジェクト データをオンプレミスに保持する場合は、Project Server 2007 環境を Project Server 2010、Project Server 2013、または Project Server 2016 に移行できます。
  
移行できない場合は、Project Onlineに移行することをお勧Project Server 2016。 Project Server 2016サーバーの以前のリリースのすべての機能がProjectされます。 この機能は、Project Onlineで使用できるエクスペリエンスと最も密接に一致しますが、一部の機能はProject Online。
  
移行の後、データが正常に移行されたことを確認する必要があります。
  
> [!NOTE]
>
  
### <a name="how-do-i-migrate-to-project-server-2016"></a>移行方法をProject Server 2016?

サーバー 2007 Projectのアーキテクチャの違いは、Project Server 2016移行パスを妨げる可能性があります。 そのため、サーバー 2007 のデータをProjectサーバーの連続する各バージョンに移行し、Projectに到達するまでProject Server 2016。
  
次の手順に従って、次Project Server 2016。
  
1. サーバー 2007 Projectサーバー 2010 Project移行します。
    
2. サービス 2010 Projectサーバー 2013 に移行Project移行します。
    
3. サーバー 2013 Projectからサーバー 2013 へのProject Server 2016。
    
移行が完了したら、データが正常に移行されたことを確認します。
  
### <a name="step-1-migrate-from-project-server-2007-to-project-server-2010"></a>手順 1: サーバー 2007 Projectサーバー 2010 Project移行する

Project Server 2007 から Project Server 2010 へのアップグレードに必要な操作の包括的な説明については、「upgrade [to Project Server 2010」](/previous-versions/office/project-server-2010/gg502590(v=office.14))を参照してください。
  
主なリソース:
  
|**Resource**|**説明**|
|:-----|:-----|
|[ProjectServer 2010 アップグレードの概要](/previous-versions/office/project-server-2010/ee662496(v=office.14)) <br/> |サーバー 2007 からサーバー 2010 へのアップグレードに必要ProjectのProjectビュー <br/> |
|[サーバー 2010 へのProject計画](/previous-versions/office/project-server-2010/ff603505(v=office.14)) <br/> |システム要件を含む、Project Server 2007 から Project Server 2010 へのアップグレード時の計画に関する考慮事項  <br/> |
   
#### <a name="how-do-i-upgrade"></a>アップグレードの方法

詳細については[、「Upgrade to Project Server 2010」を参照してください](/previous-versions/office/project-server-2010/gg502590(v=office.14))。 ただし、アップグレードに使用できる 2 つの異なる方法を理解することが重要です。
  
- **データベース接続アップグレード:** このメソッドは、構成設定ではなく、環境のコンテンツのみをアップグレードします。 32 ビット サーバー オペレーティング システムのみをサポートするハードウェアOffice Projectサーバー 2007 からアップグレードする場合に必要です。 データベース接続アップグレード方法には、次の 2 種類があります。
    
  - **データベース接続フル** アップグレード - Office Project Server 2007 データベースに格納されているプロジェクト データと、SharePoint コンテンツ データベースに格納されている Microsoft Project Web App サイト データを移行します。
    
  - **データベース接続コア *アップグレード***- サーバー データベースに格納されているプロジェクト データProject移行します。
    
- **インプレイス アップグレード**: ファームとファーム上のすべてのコンテンツの構成データは、既存のハードウェア上で一定の順序でアップグレードされます。 アップグレード プロセスを開始すると、セットアップによってファーム全体がオフラインになります。 アップグレードが完了するまでMicrosoft Project Web アプリ サイトと Web アプリ サイトは使用できません。その後、セットアップによってサーバーが再起動されます。 インプレイス アップグレードを開始した後、アップグレードを一時停止したり、以前のバージョンにロールバックしたりできない。 実稼働環境のミラーイメージを作成し、実稼働環境ではなく、この環境への一時アップグレードを行うのが最善です。 
    
追加情報:
  
- [SuperFlow for Microsoft Project Server 2010 アップグレード](/samples/browse/?redirectedfrom=TechNet-Gallery)
    
- [サーバー 2007 Projectサーバー 2010 へのProject移行](/samples/browse/?redirectedfrom=TechNet-Gallery)
    
- [アップグレードに関する考慮事項Project Web App Web パーツ](/previous-versions/office/project-server-2010/gg314581(v=office.14))
    
- [Projectソフトウェア開発キット (SDK)](/previous-versions/office/developer/office-2010/ms481966(v=office.14))
    
### <a name="step-2-migrate-to-project-server-2013"></a>手順 2: サーバー 2013 Projectに移行する

データが正常に移行されたことを確認したら、次の手順では、サーバー 2013 Projectします。
  
Project Server 2010 から Project Server 2013 へのアップグレードに必要な操作の包括的な説明については、「upgrade [to Project Server 2013」](/project/upgrade-to-project-server-2016)を参照してください。 
  
主なリソース:
  
|**Resource**|**説明**|
|:-----|:-----|
|[Project Server 2013 のアップグレード プロセスの概要](/project/upgrade-to-project-server-2016) <br/> |サーバー 2010 からサーバー 2013 へのアップグレードにProject必要Project概要  <br/> |
|[サーバー 2013 へのProject計画](/project/plan-for-upgrade-to-project-server-2016) <br/> |システム要件を含む、Project Server 2010 から Project Server 2013 へのアップグレード時の計画に関する考慮事項 <br/> |
   
#### <a name="things-to-know-about-upgrading-to-this-version"></a>このバージョンへのアップグレードに関する情報

[サーバー 2013 のアップグレードProject、](/project/what-s-new-in-project-server-2013-upgrade)このバージョンのアップグレードに関する重要な変更点について説明します。 最も重要なのは次のとおりです。 
  
- サーバー 2013 への一Projectはありません。 データベース接続メソッドは、サーバー 2010 からサーバー 2013 へのアップグレードProject唯一のProject方法です。
    
- アップグレード プロセスは、Project Server 2010 データを Project Server 2013 形式に変換するだけでなく、4 つの Project Server 2010 データベースを単一の Project Web App データベースに統合します。
    
- 2013 バージョンでは、サーバーとサーバー SharePointサーバー Projectクレーム ベース認証に変更されました。 従来の認証を使用している場合は、アップグレードにこの要素を考慮する必要があります。 詳細については、「[SharePoint 2013 でクラシックモードからクレームベース認証に移行する](/sharepoint/security-for-sharepoint-server/security-for-sharepoint-server)」を参照してください。
    
追加情報:
  
- [Project Server 2013 へのアップグレード プロセスの概要](/project/overview-of-the-project-server-2016-upgrade-process)
    
- [データベースおよび Project Web App サイト コレクションをアップグレードする (Project Server 2013)](/project/upgrading-to-project-server-2016)
    
- [Microsoft Projectサーバーのアップグレード プロセス図](https://go.microsoft.com/fwlink/p/?linkid=841270)
    
- [8 つの簡単な手順でサーバー 2010 Project 2013 への移行に関する大きなデータベース統合](https://go.microsoft.com/fwlink/p/?linkid=841271)
    
### <a name="step-3-migrate-to-project-server-2016"></a>手順 3: サーバーに移行Project Server 2016

データが正常に移行されたことを確認したら、次の手順では、データを移行Project Server 2016。
  
Project Server 2013 から Project Server 2016 にアップグレードするために必要な操作の詳細については、「upgrade to Project Server 2016」[を参照してください](//project/upgrading-to-project-server-2016)。
  
主なリソース:
  
|**Resource**|**説明**|
|:-----|:-----|
|[Project Server 2016 のアップグレード プロセスの概要](/previous-versions/office/project-server-2010/ee662104(v=office.14)) <br/> |サーバー 2013 からサーバー 2013 へのアップグレードにProject必要Project Server 2016 <br/> |
|[Project Server 2016 へのアップグレードを計画する](/project/plan-for-upgrade-to-project-server-2016) <br/> |サーバー 2013 からサーバー 2013 Projectアップグレードする計画に関するProject Server 2016 <br/> |
   
#### <a name="things-to-know-about-upgrading-to-this-version"></a>このバージョンへのアップグレードに関する情報

[アップグレードについて知る必要があるProject Server 2016、](/project/plan-for-upgrade-to-project-server-2016)このバージョンのアップグレードに関する重要な変更点を示します。これには次のものが含まれます。
  
- Project Server 2013 データを移行する Project Server 2016 環境を作成すると、Project Server 2016 インストール ファイルが SharePoint Server 2016 に含まれます。 詳細については、「Deploy [Project Server 2016」 を参照してください](/project/deploy-project-server-2016)。
    
- リソース 計画は、Project Server 2016。 サーバー Project 2013 リソース プランは、リソース 契約に移行され、Project Server 2016に移行Project Online。 詳細については [、「概要: リソースエンゲージメント](https://support.office.com/article/73eefb5a-81fe-42bf-980e-9532b1bdc870) 」を参照してください。 
    
## <a name="migrate-from-portfolio-server-2007"></a>ポートフォリオ サーバー 2007 からの移行

Projectポートフォリオ サーバー 2007 は、ポートフォリオ戦略、Project最適化のために、Project Server 2007 と一緒に使用されました。 このバージョンの後にProjectポートフォリオ サーバーの追加バージョンは作成されません。 ただし、ポートフォリオ管理機能は、Project Server 2016およびプレミアムバージョンでProject Online。 ただし、Projectポートフォリオ サーバー 2007 からのデータはどちらに移行できません。 ビジネス ドライバーなどのデータを再作成する必要があります。
  
その他のリソース：
  
- [Project Onlineサービスの説明:](/office365/servicedescriptions/project-online-service-description/project-online-service-description)詳細および管理に含まれるポートフォリオ管理機能をProject Server 2016 Project Online Premium。
    
- [Microsoft Office Project 2007 移行ガイドを参照してください。](https://go.microsoft.com/fwlink/p/?linkid=841279)
    
## <a name="related-topics"></a>関連項目

[SharePointServer 2007 のサポート終了ロードマップ](sharepoint-2007-end-of-support.md)
  
[Office 2007 のサーバーとクライアントからのアップグレードに役立つリソース](upgrade-from-office-2007-servers-and-products.md)
