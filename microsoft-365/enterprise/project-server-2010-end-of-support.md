---
title: Project Server 2010 のサポート終了ロードマップ
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
description: Project Server 2010 のサポートは 2021 年 4 月 13 日に終了します。 この記事は、Project Online またはオンプレミスの新しいバージョンの Project Server にアップグレードするガイドとして使用します。
ms.openlocfilehash: 807c09bff0cb6331b872474acc22f8d2c622a6c6
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927374"
---
# <a name="project-server-2010-end-of-support-roadmap"></a>Project Server 2010 のサポート終了のロードマップ

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

Project Server 2010 は 2021 年 4 月 **13** 日にサポートが終了します。 この日付は、2020 年 10 月 13 日の以前のサポート終了日から延長されました。 現在 Project Server 2010 を使用している場合、これらの関連製品には次のサポート終了日があります。

|製品 |サポート終了日|
|---|---|
|Project 2010 Standard|2020 年 10 月 13 日|
|Project 2010 Professional|2020 年 10 月 13 日|

サポートの終了に達する方法の詳細については [、「Upgrade from Office 2010 サーバーとクライアント製品」を参照してください](plan-upgrade-previous-versions-office.md)。

## <a name="what-does-end-of-support-mean"></a>サポート終了 *とはどういう意味* ですか?

ほとんどすべての Microsoft 製品にはサポート ライフサイクルが含まれています。その間、新機能、バグ修正、セキュリティ更新プログラムが提供されます。 このライフサイクルは、通常、製品の最初のリリースから 10 年間続く。 このライフサイクルの終了は、製品のサポート終了と呼ばれる。 Project Server 2010 が 2021 年 4 月 13 日にサポートの終了に達すると、Microsoft は次の情報を提供しなくなりました。

- 発生する可能性のある問題に対するテクニカル サポート。

- 検出され、サーバーの安定性と使いやすさに影響を与える可能性がある問題のバグ修正。

- 検出され、サーバーがセキュリティ侵害に対して脆弱になる可能性がある脆弱性に対するセキュリティ修正。

- タイム ゾーンの更新。

Project Server 2010 のインストールは、この日付以降も実行されます。 ただし、前に示した変更のため、できるだけ早く Project Server 2010 から移行することを強く推奨します。

## <a name="what-are-my-options"></a>使用できるオプション

移行オプションは次のとおりです。

- Project Online への移行

- 新しいオンプレミス バージョンの Project Server に移行する (好ましくは Project Server 2019)

Project Server 2010 のサポート終了を回避するために使用できる 2 つのパスを次に示します。

![Project Server 2010 のアップグレード パス](../media/project-server-2010-end-of-support/project-server-2010-end-of-support-timeline.png)

|Project Server 2019 に移行する理由|Project Online に移行する理由|
|---|---|
|ビジネス ルールは、クラウドでのビジネスの運用を制限します。  <br/><br/>  環境の更新を制御する必要があります。|モバイル ユーザーまたはリモート ユーザーがいます。<br/><br/>  オンプレミス サーバーを移行するためのコストは重要な懸念事項です (ハードウェア、ソフトウェア、実装の時間と労力など)。 <br/><br/>  移行後、環境を維持するためのコストが懸念されます (自動更新、保証されたアップタイムなど)。|

> [!NOTE]
> 移行オプションの詳細については [、「2010](upgrade-from-office-2010-servers-and-products.md)サーバーとクライアントからのアップグレードに役立つリソースOfficeを参照してください。 Project Server と Project Online は同じリソース プールを共有できないので、Project Server はハイブリッド構成をサポートしません。

### <a name="what-are-my-options-for-project-client"></a>Project クライアントのオプションは何ですか?

Project Professional 2010 または Project Standard 2010 を使用している場合のオプションは次のとおりです。

- Project Professional または Project Standard の新しいバージョンに移動する
- Web 用 Project Online や Project などのオンライン ソリューションに移動する

#### <a name="move-to-a-newer-version-of-project-client"></a>Project クライアントの新しいバージョンに移動する

Project Standard 2010 から移行する場合は、新しいバージョンの Project Standard (Project Standard 2016 または Project Standard 2019) に移行できます。 最新の機能を利用するには、最新バージョンに移行することをお勧めします。 現在より少ないバージョン (Project Standard 2016) に移行すると、もう一度早く移行する必要があります。

同様に、Project Professional 2010 から移行する場合は、新しいバージョン (Project Professional 2019 または Project Professional 2016) に移行できます。 繰り返しますが、可能な場合は最新バージョンに移動します。 Project Professional を使用して Project Server に接続する場合は、使用する Project Server のバージョンに接続する Project Professional のバージョンに移行してください。

Project Professional 2010 ユーザーは、Project Online Desktop クライアント (Project Professional 2019 のサブスクリプション ベースのバージョン) に移行できます。 Project Plan 3 および Project Plan 5 サブスクリプションに含まれています。

#### <a name="move-to-an-online-solution"></a>オンライン ソリューションに移動する

Project Professional 2010 または Project Standard 2010 から Project サブスクリプション ベースのオンライン ソリューションに移行できます。 Project Plan 3 と Plan 5 の両方に、Project Online と最新のクラウド サービス [Project for the Web が含まれます](https://support.office.com/article/what-can-you-do-with-project-for-the-web-b30f5442-be5f-43d2-9072-c95bff778ea1)。 どちらも、探索する価値のある新機能と利点を提供します。

機能とライセンスの詳細については [、「Microsoft Project サービスの説明」を参照してください](/office365/servicedescriptions/project-online-service-description/project-online-service-description)。

## <a name="important-considerations-for-migrating-from-project-server-2010"></a>Project Server 2010 からの移行に関する重要な考慮事項

Project Server 2010 からの移行を計画する場合は、次の点を考慮してください。

- **Microsoft ソリューション プロバイダーからヘルプを受ける** - Project Server 2010 からのアップグレードは難しい場合があります。 多くの準備と計画が必要です。 Project Server 2010 を最初にセットアップしたユーザーでなかった場合は、特に困難な場合があります。 Microsoft ソリューション プロバイダーは、Project Server 2019 または Project Online への移行を計画している場合に役立ちます。 Microsoft ソリューション プロバイダー センターでソリューション プロバイダー [を検索します](https://go.microsoft.com/fwlink/p/?linkid=841249)。

- **カスタマイズの計画** - Project Server 2019 または Project Online に移行すると、Project Server 2010 環境のカスタマイズが機能しない場合があります。 バージョン間で Project Server アーキテクチャに大きな違いがあります。 また、バージョンで動作する必要なオペレーティング システム、データベース サーバー、および Web ブラウザーも異なります。 新しい環境でカスタマイズをテストまたは再構築する方法を計画します。 この機会に、特定のカスタマイズがまだ必要かどうかを判断してください。 詳細については、「[Create a plan for current customizations during upgrade to SharePoint 2013](/SharePoint/upgrade-and-update/create-a-plan-for-current-customizations-during-upgrade-to-sharepoint-2013)」を参照してください。

- **時間と忍耐** - 計画、実行、およびテストのアップグレードには、特に Project Server 2019 へのアップグレードにかなりの時間と労力が必要です。 Project Server 2010 から Project Server 2019 に移行する場合は、最初に Project Server 2013 に移行し、データを確認してから Project Server 2016 に移行し、次に Project Server 2019 に移行する必要があります。 Microsoft ソリューション プロバイダーに時間と見積もりコストを確認して支援する必要がある場合があります。

## <a name="migrate-to-project-online"></a>Project Online への移行

Project Server 2010 から Project Online に移行する場合は、次の手順に従ってプロジェクト 計画データを手動で移行できます。

1. Project Server 2010 から .mpp 形式にプロジェクト 計画を保存します。

2. Project Professional 2016、Project Professional 2019、または Project Online デスクトップ クライアントを使用して、各 .mpp ファイルを開き、それを Project Online に保存して発行します。

Project Online で PWA 構成を手動で作成できます (たとえば、必要なユーザー設定フィールドやエンタープライズ カレンダーを再作成します)。 Microsoft ソリューション プロバイダーは、このプロセスにも役立ちます。

主なリソース:

|関連情報|説明|
|---|---|
|[Project Online の使用を開始する](https://support.office.com/article/e3e5f64f-ada5-4f9d-a578-130b2d4e5f11)|Project Online を設定して使用する方法|
|[Project Online サービスの説明](/office365/servicedescriptions/project-online-service-description/project-online-service-description)|利用可能なさまざまな Project Online プランに関する情報|

## <a name="migrate-to-a-newer-on-premises-version-of-project-server"></a>新しいオンプレミス バージョンの Project Server に移行する

Project Online に移行することで、最高の価値とユーザー エクスペリエンスを得たと強く信じています。 ただし、一部の組織では、プロジェクト データをオンプレミスに保持する必要がある場合もあります。 プロジェクト データをオンプレミスに保持する場合は、Project Server 2010 環境を Project Server 2013、Project Server 2016、または Project Server 2019 に移行できます。

Project Online に移行できない場合は、Project Server 2019 に移行することをお勧めします。 Project Server 2019 には、以前のリリースの Project Server の主要な機能のほとんどが含まれています。 また、Project Online で使用できるエクスペリエンスと最も密接に一致しますが、一部の機能は Project Online でのみ使用できます。

各移行が完了したら、データが正常に移行されたことを確認します。

> [!NOTE]
> オンプレミス のソリューションに限定され、Project Server 2013 への移行のみを検討している場合は、このバージョンのサポート期間が数年しか残っていない点に注意してください。 Service Pack 2 2023 Project Server 2013 10 月 13 日のサポート終了日。 サポート終了日の詳細については、「Microsoft 製品ライフサイクル ポリシー [」を参照してください](/lifecycle/)。

### <a name="how-do-i-migrate-to-project-server-2019"></a>Project Server 2019 に移行する方法

Project Server 2010 と Project Server 2019 のアーキテクチャ上の違いは、直接移行パスを妨げる。 そのため、Project Server 2019 に到達するまで、Project Server 2010 データを各連続するバージョンの Project Server に移行する必要があります。 Project Server 2010 を Project Server 2019 にアップグレードする手順:

1. [移行] Project Server 2013。

2. Project Serve 2013 から Project Server 2016 に移行します。

3. Project Server 2016 から Project Server 2019 に移行します。

各移行が完了したら、データが正常に移行されたことを確認します。

### <a name="step-1-migrate-to-project-server-2013"></a>手順 1: 移行を実行Project Server 2013

Project Server 2010 からプロジェクト サーバーへのアップグレードの詳細については、「Upgrade to Project Server 2013」を参照[Project Server 2013。](/project/upgrade-to-project-server-2016)

主なリソース:

- [Project Server 2013 のアップグレード プロセスの概要](/project/upgrade-to-project-server-2016)

  Project Server 2010 からプロジェクト サーバー 2010 にアップグレードする方法の概要をProject Server 2013。
- [サーバーへのアップグレードを計画Project Server 2013](/project/plan-for-upgrade-to-project-server-2016)

  Project Server 2010 からシステム要件を含む、プロジェクト サーバー 2010 Project Server 2013計画に関する考慮事項を確認します。

- [アップグレードの新機能は、Project Server 2013の](/project/what-s-new-in-project-server-2013-upgrade) 重要な変更点を含めて説明します。

   - 一部のユーザーに対する一Project Server 2013。 データベース接続メソッドは、Project Server 2010 からプロジェクト サーバーにアップグレードする唯一のProject Server 2013。

   - アップグレード プロセスでは、Project Server 2010 データを Project Server 2013 形式に変換するだけでなく、4 つの Project Server 2010 データベースを 1 つの Project Web App データベースに統合します。

   - SharePoint Server 2013 と sharePoint Server 2013 Project Server 2013以前のバージョンからのクレーム ベース認証に変更されました。 従来の認証を使用している場合は、アップグレード時にこれを考慮する必要があります。 詳細については、「[SharePoint 2013 でクラシックモードからクレームベース認証に移行する]( https://docs.microsoft.com/sharepoint/upgrade-and-update/migrate-from-classic-mode-to-claims-based-authentication-in-sharepoint-2013)」を参照してください。

主なリソース:

- [Project Server 2013 へのアップグレード プロセスの概要](/project/overview-of-the-project-server-2016-upgrade-process)

- [データベースおよび Project Web App サイト コレクションをアップグレードする (Project Server 2013)](/project/upgrading-to-project-server-2016)

- [Microsoft Project Server のアップグレード プロセス図](https://go.microsoft.com/fwlink/p/?linkid=841270)

- [8 つの簡単な手順で大きなデータベース統合、Project Server 2010 ~ 2013 の移行](https://go.microsoft.com/fwlink/p/?linkid=841271)

### <a name="step-2-migrate-to-project-server-2016"></a>手順 2: Project Server 2016 に移行する

移行後、Project Server 2013が正常に移行されたことを確認したら、次に Project Server 2016 に移行します。

詳細については [、「Upgrade to Project Server 2016」を参照してください](/Project/upgrade-to-project-server-2016)。

主なリソース:

- [Project Server 2016 のアップグレード プロセスの概要](/Project/overview-of-the-project-server-2016-upgrade-process)

  Project Server 2016 へのアップグレードに必要Project Server 2013を理解します。

- [Project Server 2016 へのアップグレードを計画する](/Project/plan-for-upgrade-to-project-server-2016)

  プロジェクトサーバーから Project Server 2016 にアップグレードする際にProject Server 2013検討事項を確認します。

[Project Server 2016](/project/plan-for-upgrade-to-project-server-2016#thingknow) のアップグレードについて知る必要がある点は、このバージョンにアップグレードする場合の重要な変更点です。これには次のものが含まれます。

- Project Server 2016 環境を作成する場合は、Project Server 2016 インストール ファイルが SharePoint Server 2016 に含まれている点に注意してください。 詳細については [、「Deploy Project Server 2016」を参照してください](/project/deploy-project-server-2016)。

- Project Server 2016 では、リソース プランは非推奨です。 リソース Project Server 2013 Project Server 2016 および Project Online の Resource Engagements に移行されます。 詳細については [、「概要: リソースエンゲージメント](https://support.office.com/article/73eefb5a-81fe-42bf-980e-9532b1bdc870) 」を参照してください。

### <a name="step-3-migrate-to-project-server-2019"></a>手順 3: Project Server 2019 に移行する

Project Server 2016 に移行し、データが正常に移行されたことを確認したら、次に、データを Project Server 2019 に移行します。

Project Server 2016 から Project Server 2019 にアップグレードするために必要な操作については [、「Upgrade to Project Server 2019」](/Project/upgrade-to-project-server-2016)を参照してください。

主なリソース:

- [Project Server 2019 アップグレード プロセスの概要](/project/overview-of-the-project-server-2019-upgrade-process)

  プロジェクト サーバーから Project Server 2016 にアップグレードするために必要なProject Server 2013を理解します。

- [Project Server 2019 へのアップグレードを計画する](/project/plan-for-upgrade-to-project-server-2019)

  Project Server 2016 から Project Server 2019 へのアップグレードに関する計画上の考慮事項について説明します。

- [Project Server 2019 アップグレードについて知る必要がある点](/project/plan-for-upgrade-to-project-server-2016)<br/><br/>このバージョンへのアップグレードに関する重要な変更点については、以下を参照してください。

   - アップグレード プロセスでは、Project Server 2016 データベースから SharePoint Server 2019 コンテンツ データベースにデータが移行されます。  Project Server 2019 は、SharePoint Server ファームに独自の Project Server データベースを作成しなくなりました。

   - アップグレード後、アップグレードの変更点に注意Project Web App。  詳細については [、「What's new in Project Server 2019」を参照してください](/project/what-s-new-for-it-pros-in-project-server-2019#PWAChanges)。

**その他のリソース**:

- [Project Online Service の説明](/office365/servicedescriptions/project-online-service-description/project-online-service-description): Project Server 2016 および Project Online Premium に含まれるポートフォリオ管理機能を参照してください。

- [Microsoft Office Project Portfolio Server 2010 移行ガイド](https://go.microsoft.com/fwlink/p/?linkid=841279)

## <a name="summary-of-options-for-office-2010-client-and-servers-and-windows-7"></a>2010 クライアントとOffice Windows 7 のオプションの概要

Office 2010 サーバー/クライアント、および Windows 7のアップグレード、移行、およびクラウドへの移行オプションを視覚的にまとめた概要は、[サポート終了ポスター](../downloads/Office2010Windows7EndOfSupport.pdf) をご覧ください。

[![2010 年 2010 Officeサーバーと Windows 7 ポスターのサポートの終了](../media/upgrade-from-office-2010-servers-and-products/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)

このポスターは、Office 2010 クライアントおよびサーバー製品と Windows 7 のサポートが終了しないようにするために使用できるさまざまなパスを示しています。Microsoft 365 Enterprise での優先パスとオプションのサポートが強調表示されています。

また、この [ポスター](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Office2010Windows7EndOfSupport.pdf) をダウンロードして、レター、リーガル、またはタブロイド (11 x 17) 形式で印刷することもできます。

## <a name="related-topics"></a>関連項目

[SharePoint 2010 からのアップグレード](upgrade-from-sharepoint-2010.md)

[Office 2010 サーバー/クライアントからアップグレードする](upgrade-from-office-2010-servers-and-products.md)