---
title: ProjectServer 2010 のサポート終了ロードマップ
ms.author: efrene
author: efrene
manager: pamg
ms.date: 04/14/2020
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
description: Project Server 2010 のサポートは 2021 年 4 月 13 日に終了します。 この記事をガイドとして使用して、Project Onlineまたは新しいバージョンの Projectサーバーにアップグレードします。
ms.openlocfilehash: 1c5b942e50a137c1ecc32f08c481811ef4edf779
ms.sourcegitcommit: c2d752718aedf958db6b403cc12b972ed1215c00
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58567858"
---
# <a name="project-server-2010-end-of-support-roadmap"></a>Project Server 2010 のサポート終了のロードマップ

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

Projectサーバー 2010 は **、2021** 年 4 月 13 日にサポートの終了に達します。 この日付は、2020 年 10 月 13 日の以前のサポート終了日から延長されました。 現在、サーバー 2010 Projectを使用している場合、これらの関連製品のサポート終了日は次のとおりです。

|製品 |サポート終了日|
|---|---|
|Project 2010 Standard|2020 年 10 月 13 日|
|Project 2010 Professional|2020 年 10 月 13 日|

サポートの終了に達する方法の詳細については[、「Upgrade from Office 2010 サーバーとクライアント製品」を参照してください](plan-upgrade-previous-versions-office.md)。

## <a name="what-does-end-of-support-mean"></a>サポート終了 *とはどういう意味* ですか?

ほとんどすべての Microsoft 製品にはサポート ライフサイクルが含まれています。その間、新機能、バグ修正、セキュリティ更新プログラムが提供されます。 このライフサイクルは、通常、製品の最初のリリースから 10 年間続く。 このライフサイクルの終了は、製品のサポート終了と呼ばれる。 2010 Project 2010 が 2021 年 4 月 13 日にサポートの終了に達すると、Microsoft は次の情報を提供しなくなりました。

- 発生する可能性のある問題に対するテクニカル サポート。

- 検出され、サーバーの安定性と使いやすさに影響を与える可能性がある問題のバグ修正。

- 検出され、サーバーがセキュリティ侵害に対して脆弱になる可能性がある脆弱性に対するセキュリティ修正。

- タイム ゾーンの更新。

サーバー 2010 Projectのインストールは、この日付以降も実行されます。 ただし、前に示した変更のため、できるだけ早く Project Server 2010 から移行することを強く推奨します。

## <a name="what-are-my-options"></a>使用できるオプション

移行オプションは次のとおりです。

- 移行してProject Online

- 新しいオンプレミス バージョンの Project サーバーに移行する (Project Server 2019)

サーバー 2010 のサポートが終了しないようにするために使用できる 2 Projectを示します。

![Projectサーバー 2010 のアップグレード パス。](../media/project-server-2010-end-of-support/project-server-2010-end-of-support-timeline.png)

|サーバー 2019 への移行Projectする理由|移行先に移行する理由Project Online。|
|---|---|
|ビジネス ルールは、クラウドでのビジネスの運用を制限します。  <br/><br/>  環境の更新を制御する必要があります。|モバイル ユーザーまたはリモート ユーザーがいます。<br/><br/>  オンプレミス サーバーを移行するためのコストは重要な懸念事項です (ハードウェア、ソフトウェア、実装の時間と労力など)。 <br/><br/>  移行後、環境を維持するためのコストが懸念されます (自動更新、保証されたアップタイムなど)。|

> [!NOTE]
> 移行オプションの詳細については[、「2010](upgrade-from-office-2010-servers-and-products.md)サーバーとクライアントからのアップグレードに役立つリソースOfficeを参照してください。 Projectサーバーとサーバーは同じリソース プールをProjectできないのでProject Onlineハイブリッド構成はサポートされません。

### <a name="what-are-my-options-for-project-client"></a>クライアントのオプションは何Projectですか?

2010 年または 2010 年Project Professional 2010 年Project Standard使用している場合は、次のオプションを使用できます。

- 新しいバージョンの Project Professional または Project Standard
- Web 用のオンライン ソリューション (Project OnlineやProjectに移動する

#### <a name="move-to-a-newer-version-of-project-client"></a>新しいバージョンのクライアントにProjectする

Project Standard 2010 から移行する場合は、新しいバージョンの Project Standard (Project Standard 2016 または Project Standard 2019) に移行できます。 最新の機能を利用するには、最新バージョンに移行することをお勧めします。 現在より少ないバージョン (Project Standard 2016) に移行すると、もう一度早く移行する必要があります。

同様に、Project Professional 2010 から移行する場合は、新しいバージョン (Project Professional 2019 または Project Professional 2016) に移行できます。 繰り返しますが、可能な場合は最新バージョンに移動します。 Project Professional を使用して Project Server に接続する場合は、使用する Project Professional サーバーのバージョンに接続する Project Project Professional のバージョンに移行してください。

Project Professional 2010 ユーザーは、Project Online デスクトップ クライアント (サブスクリプション ベースのバージョンの Project Professional 2019) にも移行できます。 これは、サブスクリプションとProject Plan 3にProject Plan 5されます。

#### <a name="move-to-an-online-solution"></a>オンライン ソリューションに移動する

2010 年または 2010 Project Professional 2010 Project Standardサブスクリプション ベースのオンライン Projectに移行できます。 このProject Plan 3プラン 5 には、Project Onlineと最新のクラウド サービスが含まれます。Project[をサポートします](https://support.office.com/article/what-can-you-do-with-project-for-the-web-b30f5442-be5f-43d2-9072-c95bff778ea1)。 どちらも、探索する価値のある新機能と利点を提供します。

機能とライセンスの詳細については、「サービスの説明Microsoft Project[参照してください](/office365/servicedescriptions/project-online-service-description/project-online-service-description)。

## <a name="important-considerations-for-migrating-from-project-server-2010"></a>サーバー 2010 から移行する際Project考慮事項

サーバー 2010 から移行する予定の場合はProject検討してください。

- **Microsoft ソリューション プロバイダーからのヘルプを取得** する - サーバー 2010 Projectアップグレードは難しい場合があります。 多くの準備と計画が必要です。 サーバー 2010 で最初にセットアップしたユーザーでなかった場合は、特にProjectがあります。 Microsoft ソリューション プロバイダーは、サーバー 2019 への移行を計画している場合でも、Projectに移行する場合Project Online。 Microsoft ソリューション プロバイダー センターでソリューション プロバイダー [を検索します](https://go.microsoft.com/fwlink/p/?linkid=841249)。

- **カスタマイズを計画する**- Project Server 2010 環境でのカスタマイズは、Project Server 2019 または Project Online に移行するときに機能しない可能性があります。 バージョン間でサーバー アーキテクチャProject大きな違いがあります。 また、バージョンで動作する必要なオペレーティング システム、データベース サーバー、および Web ブラウザーも異なります。 新しい環境でカスタマイズをテストまたは再構築する方法を計画します。 この機会に、特定のカスタマイズがまだ必要かどうかを判断してください。 詳細については、「[Create a plan for current customizations during upgrade to SharePoint 2013](/SharePoint/upgrade-and-update/create-a-plan-for-current-customizations-during-upgrade-to-sharepoint-2013)」を参照してください。

- **時間と忍耐**- アップグレードの計画、実行、およびテストには、特にサーバー 2019 へのアップグレードにかなりの時間と労力Projectされます。 Project Server 2010 から Project Server 2019 に移行する場合は、最初に Project Server 2013 に移行し、データを確認してから Project Server 2016 に移行してから、Project Server 2019 に移行する必要があります。 Microsoft ソリューション プロバイダーに時間と見積もりコストを確認して支援する必要がある場合があります。

## <a name="migrate-to-project-online"></a>移行してProject Online

サーバー 2010 から Project への移行をProject Online場合は、次の手順に従って、プロジェクト 計画データを手動で移行できます。

1. プロジェクト プランをサーバー 2010 Project .mpp 形式に保存します。

2. Project Professional 2016、Project Professional 2019、または Project Online デスクトップ クライアントを使用して、各 .mpp ファイルを開き、そのファイルを保存して Project Online に発行します。

ユーザー設定は、PWA手動Project Online作成できます (たとえば、必要なユーザー設定フィールドやエンタープライズ カレンダーを再作成します)。 Microsoft ソリューション プロバイダーは、このプロセスにも役立ちます。

主なリソース:

|関連情報|説明|
|---|---|
|[Project Online の使用を開始する](https://support.office.com/article/e3e5f64f-ada5-4f9d-a578-130b2d4e5f11)|ユーザー設定と使用方法Project Online|
|[Project Online サービスの説明](/office365/servicedescriptions/project-online-service-description/project-online-service-description)|利用可能なさまざまなプランProject Online情報|

## <a name="migrate-to-a-newer-on-premises-version-of-project-server"></a>新しいオンプレミス バージョンの Project サーバーに移行する

お客様が最適な価値とユーザー エクスペリエンスを得たと強く信じています。Project Online。 ただし、一部の組織では、プロジェクト データをオンプレミスに保持する必要がある場合もあります。 プロジェクト データをオンプレミスに保持する場合は、Project Server 2010 環境を Project Server 2013、Project Server 2016、または Project Server 2019 に移行できます。

サーバーに移行できないProject Online、サーバー 2019 Projectすることをお勧めします。 ProjectServer 2019 には、以前のリリースのサーバーの主要な機能のほとんどがProjectされています。 また、一部の機能はProject Onlineでしか使用できないが、Project Online。

各移行が完了したら、データが正常に移行されたことを確認します。

> [!NOTE]
> オンプレミス ソリューションに限定され、Project Server 2013 への移行のみを検討している場合は、このバージョンのサポート期間が数年しか残っていない点に注意してください。 Service Pack 2 2023 Project Server 2013 のサポート終了日。 サポート終了日の詳細については、「Microsoft 製品ライフサイクル ポリシー [」を参照してください](/lifecycle/)。

### <a name="how-do-i-migrate-to-project-server-2019"></a>サーバー 2019 へのProject方法

サーバー 2010 Projectサーバー 2019 Projectのアーキテクチャ上の違いは、直接移行パスを防止します。 そのため、Project Server 2019 に到達するまで、Project Server の連続する各バージョンに Project Server 2010 データを移行する必要があります。 サーバー 2010 Projectサーバー 2019 にアップグレードProject手順を実行します。

1. サーバー 2013 Projectに移行します。

2. [サービス 2013 Project 2013 から移行Project Server 2016。

3. サーバー 2019 Project Server 2016から Projectに移行します。

各移行が完了したら、データが正常に移行されたことを確認します。

### <a name="step-1-migrate-to-project-server-2013"></a>手順 1: サーバー 2013 Projectに移行する

Project Server 2010 から Project Server 2013 へのアップグレードの詳細については、「upgrade [to Project Server 2013」](/project/upgrade-to-project-server-2016)を参照してください。

主なリソース:

- [Project Server 2013 のアップグレード プロセスの概要](/project/upgrade-to-project-server-2016)

  サーバー 2010 からサーバー 2013 へのアップグレードProject概要をProjectします。
- [サーバー 2013 へのProject計画](/project/plan-for-upgrade-to-project-server-2016)

  システム要件を含め、Project Server 2010 から Project Server 2013 にアップグレードする際の計画上の考慮事項を確認します。

- [サーバー 2013 のアップグレードProject、](/project/what-s-new-in-project-server-2013-upgrade)このバージョンの重要な変更点について説明します。

  - サーバー 2013 への一Projectはありません。 データベース接続方法は、サーバー 2010 からサーバー 2013 へのアップグレードProject唯一Project方法です。

  - アップグレード プロセスは、Project Server 2010 データを Project Server 2013 形式に変換するだけでなく、4 つの Project Server 2010 データベースを単一の Project Web App データベースに統合します。

  - サーバー 2013 SharePointサーバー 2013 Projectサーバー 2013 の両方が、以前のバージョンからクレーム ベース認証に変更されました。 従来の認証を使用している場合は、アップグレード時にこれを考慮する必要があります。 詳細については、「[SharePoint 2013 でクラシックモードからクレームベース認証に移行する](/sharepoint/upgrade-and-update/migrate-from-classic-mode-to-claims-based-authentication-in-sharepoint-2013)」を参照してください。

主なリソース:

- [Project Server 2013 へのアップグレード プロセスの概要](/project/overview-of-the-project-server-2016-upgrade-process)

- [データベースおよび Project Web App サイト コレクションをアップグレードする (Project Server 2013)](/project/upgrading-to-project-server-2016)

- [Microsoft Projectサーバーのアップグレード プロセス図](https://go.microsoft.com/fwlink/p/?linkid=841270)

- [8 つの簡単な手順でサーバー 2010 Project 2013 への移行に関する大きなデータベース統合](https://go.microsoft.com/fwlink/p/?linkid=841271)

### <a name="step-2-migrate-to-project-server-2016"></a>手順 2: サーバーに移行Project Server 2016

サーバー 2013 Projectに移動し、データが正常に移行されたことを確認した後、次の手順では、サーバーに移行Project Server 2016。

詳細については、「Upgrade [to Project Server 2016」 を参照してください](/Project/upgrade-to-project-server-2016)。

主なリソース:

- [Project Server 2016 のアップグレード プロセスの概要](/Project/overview-of-the-project-server-2016-upgrade-process)

  サーバー 2013 からサーバー 2013 へのアップグレードProjectを理解Project Server 2016。

- [Project Server 2016 へのアップグレードを計画する](/Project/plan-for-upgrade-to-project-server-2016)

  サーバー 2013 からサーバー 2013 へのアップグレード時にProject検討事項をProject Server 2016。

[アップグレードに関して知る必要Project Server 2016、](/project/plan-for-upgrade-to-project-server-2016#thingknow)このバージョンへのアップグレードに関する重要な変更点が含まれます。

- サーバー環境を作成Project Server 2016、インストール ファイルProject Server 2016サーバー 2016 に含SharePoint注意してください。 詳細については、「Deploy [Project Server 2016」 を参照してください](/project/deploy-project-server-2016)。

- リソース 計画は、Project Server 2016。 サーバー Project 2013 リソース プランは、リソース 契約に移行され、Project Server 2016に移行Project Online。 詳細については [、「概要: リソースエンゲージメント](https://support.office.com/article/73eefb5a-81fe-42bf-980e-9532b1bdc870) 」を参照してください。

### <a name="step-3-migrate-to-project-server-2019"></a>手順 3: サーバー 2019 Projectに移行する

データを移行してProject Server 2016正常に移行されたことを確認したら、次に、データをサーバー 2019 に移行Projectします。

Project Server 2016 から Project Server 2019 へのアップグレードに必要な操作については、「Upgrade to Project [Server 2019」](/Project/upgrade-to-project-server-2016)を参照してください。

主なリソース:

- [サーバー 2019 Projectプロセスの概要](/project/overview-of-the-project-server-2019-upgrade-process)

  サーバー 2013 からサーバー 2013 へのアップグレードに必要なProjectのProject Server 2016。

- [サーバー 2019 へのアップグレードProject計画する](/project/plan-for-upgrade-to-project-server-2019)

  サーバー 2019 からサーバー 2019 へのアップグレードProject Server 2016計画Project検討してください。

- [サーバー 2019 Projectについて知る必要がある点](/project/plan-for-upgrade-to-project-server-2016)<br/><br/>このバージョンへのアップグレードに関する重要な変更点については、以下を参照してください。

  - アップグレード プロセスでは、データをデータ データベースから Project Server 2016コンテンツ データベースSharePoint Server 2019移行します。  Projectサーバー 2019 は、サーバー ファームProjectサーバー データベースをSharePointしません。

  - アップグレード後、アップグレードの変更点に注意Project Web App。  詳細については[、「What's new in Project Server 2019」を参照してください](/project/what-s-new-for-it-pros-in-project-server-2019#PWAChanges)。

**その他のリソース**:

- [Project Onlineサービスの説明](/office365/servicedescriptions/project-online-service-description/project-online-service-description): 詳細と説明に含まれるポートフォリオ管理機能Project Server 2016参照Project Online Premium。

- [Microsoft Office Project Portfolio Server 2010 移行ガイド](https://go.microsoft.com/fwlink/p/?linkid=841279)

## <a name="summary-of-options-for-office-2010-client-and-servers-and-windows-7"></a>2010 クライアントとサーバー Office 7 のオプションWindows概要

Office 2010 サーバー/クライアント、および Windows 7のアップグレード、移行、およびクラウドへの移行オプションを視覚的にまとめた概要は、[サポート終了ポスター](../downloads/Office2010Windows7EndOfSupport.pdf) をご覧ください。

[![2010 年のクライアントOfficeサーバーと 7 ポスターのWindows終了します。](../media/upgrade-from-office-2010-servers-and-products/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)

このポスターは、Office 2010 クライアントおよびサーバー製品と Windows 7 のサポートが終了しないようにするために使用できるさまざまなパスを示しています。Microsoft 365 Enterprise での優先パスとオプションのサポートが強調表示されています。

また、この [ポスター](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Office2010Windows7EndOfSupport.pdf) をダウンロードして、レター、リーガル、またはタブロイド (11 x 17) 形式で印刷することもできます。

## <a name="related-topics"></a>関連項目

[SharePoint 2010 からのアップグレード](upgrade-from-sharepoint-2010.md)

[Office 2010 サーバー/クライアントからアップグレードする](upgrade-from-office-2010-servers-and-products.md)
