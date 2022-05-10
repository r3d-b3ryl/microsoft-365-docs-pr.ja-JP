---
title: Project Server 2010 のサポート終了ロードマップ
ms.author: efrene
author: efrene
manager: pamg
ms.date: 04/14/2020
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
description: Project Server 2010 のサポートは、2021 年 4 月 13 日に終了します。 この記事は、オンプレミスの Project Online または新しいバージョンの Project Server にアップグレードするためのガイドとして使用します。
ms.openlocfilehash: 9d04df22af0a0614270907f4ad4026324b026211
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60213327"
---
# <a name="project-server-2010-end-of-support-roadmap"></a>Project Server 2010 のサポート終了のロードマップ

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

Project Server 2010 は、**2021 年 4 月 13** 日にサポートを終了します。 この日付は、2020 年 10 月 13 日のサポート終了日から延長されました。 Project Server 2010 を現在使用している場合は、これらの関連製品のサポート終了日は次のとおりです。

|製品 |サポート終了日|
|---|---|
|Project 2010 Standard|2020 年 10 月 13 日|
|Project 2010 Professional|2020 年 10 月 13 日|

サポート終了までの詳細については、「[Office 2010 サーバーとクライアント製品からのアップグレード](plan-upgrade-previous-versions-office.md)」を参照してください。

## <a name="what-does-end-of-support-mean"></a>*サポート終了とは* どういう意味ですか?

ほぼすべての Microsoft 製品にはサポート ライフサイクルがあり、その間に新機能、バグ修正、およびセキュリティ更新プログラムが提供されます。 このライフサイクルは通常、製品の初期リリースから 10 年間続きます。 このライフサイクルの終了は、製品のサポート終了と呼ばれます。 Project Server 2010 が 2021 年 4 月 13 日にサポートの終了に達すると、Microsoft は次の情報を提供しなくなります。

- 発生する可能性がある問題のテクニカル サポート。

- 検出され、サーバーの安定性と使いやすさに影響を与える可能性がある問題に対するバグ修正。

- 検出され、サーバーがセキュリティ違反に対して脆弱になる可能性がある脆弱性に対するセキュリティ修正。

- タイム ゾーンの更新。

Project Server 2010 のインストールは、この日以降も引き続き実行されます。 ただし、前述の変更のため、できるだけ早く Project Server 2010 から移行することを強くお勧めします。

## <a name="what-are-my-options"></a>使用できるオプション

移行オプションは次のとおりです。

- Project Onlineに移行する

- 新しいオンプレミス バージョンの Project Server に移行する (できればサーバー 2019 Project)

Project Server 2010 のサポートが終了しないようにするために使用できる 2 つのパスを次に示します。

![Project Server 2010 のアップグレード パス。](../media/project-server-2010-end-of-support/project-server-2010-end-of-support-timeline.png)

|Project Server 2019 に移行する必要があるのはなぜですか?|Project Onlineに移行する必要があるのはなぜですか?|
|---|---|
|ビジネス ルールを使用すると、クラウドでのビジネスの運用が制限されます。  <br/><br/>  環境の更新を制御する必要があります。|モバイル ユーザーまたはリモート ユーザーがいます。<br/><br/>  オンプレミス サーバーを移行するためのコストは、大きな懸念事項 (ハードウェア、ソフトウェア、実装にかかる時間と労力など) です。 <br/><br/>  移行後、環境を維持するためのコストが懸念されます (自動更新、稼働時間の保証など)。|

> [!NOTE]
> 移行オプションの詳細については、「[Office 2010 サーバーとクライアントからのアップグレードに役立つリソース](upgrade-from-office-2010-servers-and-products.md)」を参照してください。 Project サーバーとProject Onlineは同じリソース プールを共有できないため、Project Server はハイブリッド構成をサポートしていません。

### <a name="what-are-my-options-for-project-client"></a>Project クライアントのオプションは何ですか?

Project Professional 2010 または 2010 Project Standardを使用している場合、オプションは次のとおりです。

- 新しいバージョンのProject ProfessionalまたはProject Standardに移動する
- Web のProject OnlineやProjectなど、オンライン ソリューションに移動する

#### <a name="move-to-a-newer-version-of-project-client"></a>新しいバージョンのProject クライアントに移行する

2010 Project Standardから移行する場合は、新しいバージョンの Project Standard (Project Standard 2016 または 2019 Project Standard) に移行できます。 最新の機能を利用するには、最新バージョンに移行することをお勧めします。 また、最新バージョン (Project Standard 2016) に移行する場合は、もう一度すぐに移行する必要があります。

同様に、Project Professional 2010 から移行する場合は、新しいバージョン (Project Professional 2019 または Project Professional 2016) に移行できます。 もう一度、可能であれば最新バージョンに移動します。 Project Professionalを使用してProject サーバーに接続する場合は、使用するProject サーバーのバージョンに接続するProject Professionalのバージョンに移行していることを確認します。

Project Professional 2010 ユーザーは、Project Online デスクトップ クライアントに移行することもできます。これは、サブスクリプションベースのバージョンの Project Professional 2019 です。 Project Plan 3サブスクリプションとProject Plan 5 サブスクリプションに含まれています。

#### <a name="move-to-an-online-solution"></a>オンライン ソリューションに移動する

Project Professional 2010 または 2010 Project Standardから、Project サブスクリプション ベースのオンライン ソリューションに移行することもできます。 Project Plan 3とプラン 5 の両方に、Project Onlineと最新のクラウド オファリング [(web 向けのProject) が](https://support.office.com/article/what-can-you-do-with-project-for-the-web-b30f5442-be5f-43d2-9072-c95bff778ea1)含まれます。 どちらも、探索する価値のある新機能と利点を提供します。

機能とライセンスの詳細については、[サービスの説明Microsoft Project](/office365/servicedescriptions/project-online-service-description/project-online-service-description)参照してください。

## <a name="important-considerations-for-migrating-from-project-server-2010"></a>Project Server 2010 からの移行に関する重要な考慮事項

Project Server 2010 から移行する場合は、次の点を考慮してください。

- **Microsoft ソリューション プロバイダーからヘルプを受ける** - Project Server 2010 からのアップグレードは困難な場合があります。 多くの準備と計画が必要です。 最初にサーバー 2010 をセットアップしたユーザーでない場合は、特に困難Project可能性があります。 Microsoft ソリューション プロバイダーは、Project Server 2019 に移行する場合でも、Project Onlineに移行する場合でも、役立ちます。 Microsoft ソリューション プロバイダー [センターでソリューション プロバイダー](https://go.microsoft.com/fwlink/p/?linkid=841249)を検索します。

- **カスタマイズを計画する** - Project Server 2010 環境のカスタマイズは、Project Server 2019 またはProject Onlineに移行すると機能しない可能性があります。 Project サーバー アーキテクチャには、バージョン間で大きな違いがあります。 また、必要なオペレーティング システム、データベース サーバー、およびバージョンで動作する Web ブラウザーも異なります。 新しい環境でカスタマイズをテストまたは再構築する方法について計画を立てる。 この機会に、特定のカスタマイズがまだ必要かどうかを判断します。 詳細については、「[Create a plan for current customizations during upgrade to SharePoint 2013](/SharePoint/upgrade-and-update/create-a-plan-for-current-customizations-during-upgrade-to-sharepoint-2013)」を参照してください。

- **時間と忍耐** - アップグレードの計画、実行、テストには、特にProject Server 2019 へのアップグレードにかなりの時間と労力がかかります。 Project Server 2010 から Project Server 2019 に移行する場合は、まず Project Server 2013 に移行し、データを確認してからProject Server 2016に移行してから、サーバー 2019 をProjectする必要があります。 Microsoft ソリューション プロバイダーに対して、期間とコストの見積もりを確認することをお勧めします。

## <a name="migrate-to-project-online"></a>Project Onlineに移行する

Project Server 2010 から Project Onlineに移行することを選択した場合は、次の手順に従ってプロジェクト計画データを手動で移行できます。

1. プロジェクト プランを Project Server 2010 から .mpp 形式に保存します。

2. Project Professional 2016、Project Professional 2019、またはProject Online デスクトップ クライアントを使用して、各 .mpp ファイルを開き、Project Onlineに保存して発行します。

Project OnlineでPWA構成を手動で作成できます (たとえば、必要なユーザー設定フィールドやエンタープライズ カレンダーを再作成します)。 Microsoft ソリューション プロバイダーは、このプロセスにも役立ちます。

主なリソース:

|関連情報|説明|
|---|---|
|[Project Online の使用を開始する](https://support.office.com/article/e3e5f64f-ada5-4f9d-a578-130b2d4e5f11)|Project Onlineを設定して使用する方法|
|[Project Online サービスの説明](/office365/servicedescriptions/project-online-service-description/project-online-service-description)|利用可能なさまざまなProject Onlineプランに関する情報|

## <a name="migrate-to-a-newer-on-premises-version-of-project-server"></a>新しいオンプレミス バージョンの Project Server に移行する

Project Onlineに移行することで、お客様が最高の価値とユーザー エクスペリエンスを得られると強く信じています。 ただし、一部の組織では、プロジェクト データをオンプレミスに保持する必要があることも理解しています。 プロジェクト データをオンプレミスに保持する場合は、Project Server 2010 環境を Project Server 2013、Project Server 2016、または Project Server 2019 に移行できます。

Project Onlineに移行できない場合は、Project Server 2019 に移行することをお勧めします。 Project Server 2019 には、以前のリリースの Project Server の主な機能のほとんどが含まれています。 また、Project Onlineで使用できるエクスペリエンスと最もよく一致しますが、一部の機能はProject Onlineでのみ使用できます。

各移行が完了したら、データが正常に移行されたことを確認します。

> [!NOTE]
> オンプレミス ソリューションに限定されており、Project Server 2013 への移行のみを検討している場合は、このバージョンに残されたサポート期間があと数年しかないことに注意してください。 Project Server 2013 と Service Pack 2 のサポート終了日(2023 年 10 月 13 日)。 サポート終了日の詳細については、「 [Microsoft 製品ライフサイクル ポリシー」を](/lifecycle/)参照してください。

### <a name="how-do-i-migrate-to-project-server-2019"></a>Project Server 2019 に移行操作方法?

Project Server 2010 と Project Server 2019 のアーキテクチャ上の違いにより、直接移行パスが回避されます。 そのため、Project Server 2019 に到達するまで、Project Server 2010 データをProject Server の後続の各バージョンに移行する必要があります。 Project Server 2010 を Project Server 2019 にアップグレードする手順:

1. Project Server 2013 に移行します。

2. Project Serve 2013 から Project Server 2016に移行します。

3. Project Server 2016から Project Server 2019 に移行します。

各移行が完了したら、データが正常に移行されたことを確認します。

### <a name="step-1-migrate-to-project-server-2013"></a>手順 1: Project Server 2013 に移行する

Project Server 2010 から Project Server 2013 へのアップグレードに関する包括的な情報については、「[Project Server 2013 へのアップグレード](/project/upgrade-to-project-server-2016)」を参照してください。

主なリソース:

- [Project Server 2013 のアップグレード プロセスの概要](/project/upgrade-to-project-server-2016)

  Project Server 2010 から Project Server 2013 にアップグレードする方法の概要について説明します。
- [Project Server 2013 へのアップグレードを計画する](/project/plan-for-upgrade-to-project-server-2016)

  システム要件を含め、Project Server 2010 から Project Server 2013 にアップグレードする際の計画に関する考慮事項を確認します。

- [Project Server 2013 のアップグレードの新機能](/project/what-s-new-in-project-server-2013-upgrade)には、次のようなこのバージョンの重要な変更が含まれています。

  - Project Server 2013 へのインプレース アップグレードはありません。 データベースアタッチ方法は、Project Server 2010 から Project Server 2013 にアップグレードする唯一の方法です。

  - アップグレード プロセスでは、Project Server 2010 データを Project Server 2013 形式に変換するだけでなく、4 つのProject Server 2010 データベースを単一のProject Web App データベースに統合します。

  - SharePoint Server 2013 と Project Server 2013 の両方が、以前のバージョンから要求ベースの認証に変更されました。 クラシック認証を使用している場合は、アップグレード時にこれを考慮する必要があります。 詳細については、「[SharePoint 2013 でクラシックモードからクレームベース認証に移行する](/sharepoint/upgrade-and-update/migrate-from-classic-mode-to-claims-based-authentication-in-sharepoint-2013)」を参照してください。

主なリソース:

- [Project Server 2013 へのアップグレード プロセスの概要](/project/overview-of-the-project-server-2016-upgrade-process)

- [データベースおよび Project Web App サイト コレクションをアップグレードする (Project Server 2013)](/project/upgrading-to-project-server-2016)

- [Microsoft Project サーバーアップグレード プロセスの図](https://go.microsoft.com/fwlink/p/?linkid=841270)

- [優れたデータベース統合、Project Server 2010 から 2013 への移行 (8 つの簡単な手順)](https://go.microsoft.com/fwlink/p/?linkid=841271)

### <a name="step-2-migrate-to-project-server-2016"></a>手順 2: Project Server 2016に移行する

Project Server 2013 に移行し、データが正常に移行されたことを確認した後、次の手順ではProject Server 2016に移行します。

詳細については、「[Project Server 2016へのアップグレード」を](/Project/upgrade-to-project-server-2016)参照してください。

主なリソース:

- [Project Server 2016 のアップグレード プロセスの概要](/Project/overview-of-the-project-server-2016-upgrade-process)

  Project Server 2013 から Project Server 2016にアップグレードするために必要な操作について説明します。

- [Project Server 2016 へのアップグレードを計画する](/Project/plan-for-upgrade-to-project-server-2016)

  Project Server 2013 から Project Server 2016にアップグレードする際の計画に関する考慮事項を確認します。

[Project Server 2016アップグレードについて知](/project/plan-for-upgrade-to-project-server-2016#thingknow)っておくべきことには、このバージョンへのアップグレードに関する重要な変更が含まれます。

- Project Server 2016環境を作成するときは、Project Server 2016 インストール ファイルが SharePoint Server 2016 に含まれていることに注意してください。 詳細については、「[Project Server 2016のデプロイ」を](/project/deploy-project-server-2016)参照してください。

- リソース プランは、Project Server 2016で非推奨になりました。 Project Server 2013 リソース プランは、Project Server 2016およびProject Onlineの Resource Engagements に移行されます。 詳細については、「 [概要: リソースエンゲージメント](https://support.office.com/article/73eefb5a-81fe-42bf-980e-9532b1bdc870) 」を参照してください。

### <a name="step-3-migrate-to-project-server-2019"></a>手順 3: Project Server 2019 に移行する

Project Server 2016に移行し、データが正常に移行されたことを確認したら、次の手順では、データを Project Server 2019 に移行します。

Project Server 2016から Project Server 2019 にアップグレードするために必要な操作については、「[Project Server 2019 へのアップグレード](/Project/upgrade-to-project-server-2016)」を参照してください。

主なリソース:

- [Project Server 2019 アップグレード プロセスの概要](/project/overview-of-the-project-server-2019-upgrade-process)

  Project Server 2013 から Project Server 2016 にアップグレードするために必要な作業について、高度な理解を得ます。

- [Project Server 2019 へのアップグレードを計画する](/project/plan-for-upgrade-to-project-server-2019)

  Project Server 2016から Project Server 2019 へのアップグレードに関する計画に関する考慮事項を確認してください。

- [Project Server 2019 のアップグレードについて知っておくべきこと](/project/plan-for-upgrade-to-project-server-2016)<br/><br/>このバージョンにアップグレードするための重要な変更について説明します。これには次のものが含まれます。

  - アップグレード プロセスによって、Project Server 2016 データベースから SharePoint Server 2019 Content データベースにデータが移行されます。  Project Server 2019 では、SharePoint サーバー ファームに独自のProject サーバー データベースが作成されなくなります。

  - アップグレード後、Project Web Appのいくつかの変更に注意してください。  詳細については、「[Project Server 2019 の新機能](/project/what-s-new-for-it-pros-in-project-server-2019#PWAChanges)」を参照してください。

**その他のリソース**:

- [Project Onlineサービスの説明](/office365/servicedescriptions/project-online-service-description/project-online-service-description): Project Server 2016とProject Online Premiumに含まれるポートフォリオ管理機能を参照してください。

- [Microsoft Office Project ポートフォリオ サーバー 2010 移行ガイド](https://go.microsoft.com/fwlink/p/?linkid=841279)

## <a name="summary-of-options-for-office-2010-client-and-servers-and-windows-7"></a>Office 2010 クライアントとサーバー、Windows 7 のオプションの概要

Office 2010 サーバー/クライアント、および Windows 7のアップグレード、移行、およびクラウドへの移行オプションを視覚的にまとめた概要は、[サポート終了ポスター](../downloads/Office2010Windows7EndOfSupport.pdf) をご覧ください。

[![Office 2010 クライアントとサーバー、Windows 7 ポスターのサポート終了。](../media/upgrade-from-office-2010-servers-and-products/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)

このポスターでは、Office 2010 クライアントおよびサーバー製品と Windows 7 のサポートが終了しないようにするために実行できるさまざまなパスを示します。Microsoft 365 Enterpriseの優先パスとオプションのサポートが強調表示されています。

また、このポスターを [ダウンロード](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Office2010Windows7EndOfSupport.pdf) し、レター、リーガル、または Tabloid (11 x 17) 形式で印刷することもできます。

## <a name="related-topics"></a>関連項目

[SharePoint 2010 からのアップグレード](upgrade-from-sharepoint-2010.md)

[Office 2010 サーバー/クライアントからアップグレードする](upgrade-from-office-2010-servers-and-products.md)
