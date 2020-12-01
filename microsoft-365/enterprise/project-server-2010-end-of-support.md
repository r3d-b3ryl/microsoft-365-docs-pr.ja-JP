---
title: Project Server 2010 サポート終了のロードマップ
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
description: Project Server 2010 のサポートは、2021年4月13日に終了します。 この記事は、Project Online またはオンプレミスの Project Server の新しいバージョンにアップグレードするためのガイドとして使用してください。
ms.openlocfilehash: 239b3d93cfa6a1184ea21225fa97732712b8eb14
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519704"
---
# <a name="project-server-2010-end-of-support-roadmap"></a>Project Server 2010 のサポート終了のロードマップ

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

Project Server 2010 は **、2021年4月 13** 日のサポート終了に到達します。 この日付は、2020年10月13日の以前のサポート終了日から延長されました。 現在 Project Server 2010 を使用している場合は、これらの関連製品に次のサポート終了日があることに注意してください。

|製品 |サポート終了日|
|---|---|
|Project 2010 Standard|2020 年 10 月 13 日|
|Project 2010 Professional|2020 年 10 月 13 日|

サポート終了の詳細については、「 [Office 2010 サーバーおよびクライアント製品からのアップグレード](plan-upgrade-previous-versions-office.md)」を参照してください。

## <a name="what-does-end-of-support-mean"></a>*サポート終了の* 意味

ほぼすべての Microsoft 製品には、新機能、バグ修正、セキュリティ更新プログラムを入手するためのサポートライフサイクルがあります。 このライフサイクルは通常、製品の最初のリリースから10年間続きます。 このライフサイクルの終了は、製品のサポート終了と呼ばれます。 Project Server 2010 が2021年4月13日のサポート終了時点に達すると、Microsoft は提供しなくなります。

- 発生する可能性のある問題のテクニカルサポート。

- 検出された問題についてバグ修正を行い、サーバーの安定性と有用性に影響を与える可能性があります。

- 検出された脆弱性に対するセキュリティ修正プログラムによって、サーバーがセキュリティ侵害に対して脆弱になる可能性がある。

- タイム ゾーンの更新。

Project Server 2010 のインストールは、この日付以降も引き続き実行されます。 しかし、前述の変更のため、できるだけ早く Project Server 2010 から移行することを強くお勧めします。

## <a name="what-are-my-options"></a>使用できるオプション

移行オプションは次のとおりです。

- Project Online への移行

- 新しいオンプレミスバージョンの Project Server に移行する (Project Server 2019 を推奨)

Project Server 2010 のサポート終了を回避するために取ることができる2つのパスを次に示します。

![Project Server 2010 のアップグレードパス](../media/project-server-2010-end-of-support/project-server-2010-end-of-support-timeline.png)

|Project Server 2019 への移行を希望するのはなぜですか?|Project Online への移行を希望するのはなぜですか?|
|---|---|
|ビジネスルールは、クラウドでのビジネスの運営から制限されています。  <br/><br/>  環境に対して更新プログラムを制御する必要がある。|モバイルまたはリモートのユーザーがいます。<br/><br/>  オンプレミスサーバーを移行するためのコストは重大な問題です (ハードウェア、ソフトウェア、実装する時間と労力など)。 <br/><br/>  移行後は、環境を維持するためのコストが問題となります (たとえば、自動更新、稼働状態の保証など)。|

> [!NOTE]
> 移行オプションの詳細については、「 [Office 2010 サーバーおよびクライアントからのアップグレードに役立つリソース](upgrade-from-office-2010-servers-and-products.md)」を参照してください。 Project server と Project Online は同じリソース共有元を共有できないため、Project Server はハイブリッド構成をサポートしていないことに注意してください。

### <a name="what-are-my-options-for-project-client"></a>Project クライアントのオプションとは

Project Professional 2010 または Project Standard 2010 を使用している場合、オプションは次のとおりです。

- Project Professional または Project Standard の新しいバージョンに移行する
- Project Online や Project などのオンラインソリューションへの移動

#### <a name="move-to-a-newer-version-of-project-client"></a>新しいバージョンの Project クライアントに移動する

Project Standard 2010 から移行している場合は、project standard の新しいバージョン (Project Standard 2016 または Project Standard 2019) に移行できます。 最新の機能を利用するには、最新のバージョンに移行することをお勧めします。 現在のバージョンよりも低いバージョンに移行する (Project Standard 2016) ということは、すぐに移行する必要があることを意味します。

同様に、Project Professional 2010 から移行している場合は、新しいバージョンに移行できます (Project Professional 2019 または Project Professional 2016)。 可能であれば、最新バージョンに移動します。 Project Professional を使用して Project Server に接続する場合は、使用している Project Server のバージョンに接続しているバージョンの project Professional に移行する必要があります。

Project Professional 2010 ユーザーは、project Professional 2019 のサブスクリプションベースのバージョンである Project Online デスクトップクライアントに移行することもできます。 これは、プロジェクト計画3およびプロジェクト計画5のサブスクリプションに含まれています。

#### <a name="move-to-an-online-solution"></a>オンラインソリューションへの移動

Project Professional 2010 または Project Standard 2010 から Project サブスクリプションベースのオンラインソリューションに移行することもできます。 プロジェクトプラン3とプラン5の両方に、Project Online と、 [web 用の](https://support.office.com/article/what-can-you-do-with-project-for-the-web-b30f5442-be5f-43d2-9072-c95bff778ea1)最新のクラウドサービスが含まれています。 どちらも、探索価値のある新機能とメリットを提供します。

機能とライセンスの詳細については、「 [Microsoft Project サービスの説明](https://docs.microsoft.com/office365/servicedescriptions/project-online-service-description/project-online-service-description)」を参照してください。

## <a name="important-considerations-for-migrating-from-project-server-2010"></a>Project Server 2010 から移行する場合の重要な考慮事項

Project Server 2010 からの移行を計画する場合は、次の点を考慮してください。

- **Microsoft solution provider からヘルプを取得** する-Project Server 2010 からのアップグレードは、課題になることがあります。 これには、多くの準備と計画が必要です。 最初に Project Server 2010 をセットアップしたユーザーがいない場合は、特に難しいことがあります。 Microsoft ソリューションプロバイダーは、Project Server 2019 への移行または Project Online への移行を計画している場合に役立つことがあります。 [Microsoft ソリューションプロバイダセンター](https://go.microsoft.com/fwlink/p/?linkid=841249)でソリューションプロバイダーを検索します。

- **カスタマイズを計画** する-project server 2019 または project Online に移行するときに、project server 2010 環境でのカスタマイズを行うことができない場合があります。 バージョン間の Project Server アーキテクチャには大きな違いがあります。 また、バージョンと共に動作する必要のあるオペレーティングシステム、データベースサーバー、および web ブラウザーが異なります。 新しい環境でカスタマイズをテストまたは再構築する方法を計画します。 この機会を利用して、特定のカスタマイズが依然として必要かどうかを判断します。 詳細については、「[Create a plan for current customizations during upgrade to SharePoint 2013](https://docs.microsoft.com/SharePoint/upgrade-and-update/create-a-plan-for-current-customizations-during-upgrade-to-sharepoint-2013)」を参照してください。

- **時間および** アップグレードの計画、実行、およびテストは、特に Project Server 2019 へのアップグレードのために、時間と労力を必要とします。 Project Server 2010 から Project Server 2019 に移行している場合は、まず Project Server 2013 に移行し、データを確認してから、Project Server の2016に移行してから、Project Server の2019に移行する必要があります。 Microsoft ソリューションプロバイダーを使用して、時間枠と見積もりコストを確認することもできます。

## <a name="migrate-to-project-online"></a>Project Online への移行

Project Server 2010 から Project Online に移行することを選択した場合は、次の手順に従って、プロジェクト計画のデータを手動で移行できます。

1. プロジェクト計画を Project Server 2010 から .mpp 形式で保存します。

2. Project Professional 2016、Project Professional 2019、または Project Online デスクトップクライアントを使用して、各 .mpp ファイルを開き、Project Online に保存して発行します。

Project Online で手動で PWA 構成を作成できます (たとえば、必要なユーザー設定フィールドやエンタープライズカレンダーを再作成します)。 このプロセスでは、Microsoft ソリューションプロバイダーを支援することもできます。

主なリソース:

|関連情報|説明|
|---|---|
|[Project Online の使用を開始する](https://support.office.com/article/e3e5f64f-ada5-4f9d-a578-130b2d4e5f11)|Project Online をセットアップして使用する方法|
|[Project Online サービスの説明](https://go.microsoft.com/fwlink/p/?linkid=829088)|利用可能なさまざまな Project Online プランに関する情報|

## <a name="migrate-to-a-newer-on-premises-version-of-project-server"></a>新しいオンプレミスバージョンの Project Server に移行する

Project Online に移行することによって、最高の価値とユーザーの利便性を得られるというのは強く信じられません。 また、project データをオンプレミスで保持する必要がある組織も理解しています。 プロジェクトデータをオンプレミスで保持することを選択した場合は、project server 2010 環境を Project server 2013、Project Server 2016、または Project Server 2019 に移行できます。

Project Online に移行できない場合は、Project Server 2019 に移行することをお勧めします。 Project Server 2019 には、以前のリリースの Project Server の主要な機能の大部分が含まれています。 また、project online で利用できる機能とほぼ同じですが、一部の機能は Project online でのみ利用可能です。

各移行を完了したら、データが正常に移行されたことを確認します。

> [!NOTE]
> オンプレミスのソリューションに制限されていて、Project Server 2013 への移行のみを検討している場合は、このバージョンのサポートがさらに数年以上残っていることに注意してください。 Project Server 2013 Service Pack 2 (2023 年10月13日) のサポート終了日。 サポート終了日の詳細については、「 [Microsoft 製品ライフサイクルポリシー](https://go.microsoft.com/fwlink/p/?linkid=842066)」を参照してください。

### <a name="how-do-i-migrate-to-project-server-2019"></a>Project Server 2019 に移行する方法

Project Server 2010 と Project Server 2019 のアーキテクチャ上の違いにより、直接移行パスは回避されます。 そのため、project server 2019 に移動するまで、project server 2010 のデータを各バージョンの project Server に移行する必要があります。 Project Server 2010 を Project Server 2019 にアップグレードする手順:

1. Project Server 2013 に移行します。

2. プロジェクトサービス2013から Project Server 2016 に移行します。

3. Project Server 2016 から Project Server 2019 に移行します。

各移行を完了したら、データが正常に移行されたことを確認します。

### <a name="step-1-migrate-to-project-server-2013"></a>手順 1: Project Server 2013 に移行する

Project Server 2010 から Project Server 2013 へのアップグレードに関する総合的な情報については、「 [Upgrade To Project server 2013](https://go.microsoft.com/fwlink/p/?linkid=841822)」を参照してください。

主なリソース:

- [Project Server 2013 のアップグレード プロセスの概要](https://go.microsoft.com/fwlink/p/?linkid=841822)

  Project Server 2010 から Project Server 2013 にアップグレードする方法の概要について説明します。
- [Project Server 2013 へのアップグレードを計画する](https://go.microsoft.com/fwlink/p/?linkid=841823)

  システム要件を含め、Project Server 2010 から Project Server 2013 にアップグレードするときの計画に関する考慮事項について説明します。

- [Project Server 2013 アップグレードの新機能](https://go.microsoft.com/fwlink/p/?linkid=841824) このバージョンの重要な変更点については、以下を含みます。

   - Project Server 2013 への一括アップグレードはありません。 Project Server 2010 から Project Server 2013 にアップグレードするためにサポートされている唯一の方法は、データベース接続方式です。

   - アップグレードプロセスでは、Project Server 2010 のデータを Project server 2013 形式に変換するだけでなく、4つの Project Server 2010 データベースを1つの Project Web App データベースに統合することもできます。

   - SharePoint Server 2013 と Project Server 2013 の両方が、以前のバージョンからクレームベース認証に変更されました。 従来の認証を使用している場合は、アップグレード時にこれを考慮する必要があります。 詳細については、「[SharePoint 2013 でクラシックモードからクレームベース認証に移行する]( https://docs.microsoft.com/sharepoint/upgrade-and-update/migrate-from-classic-mode-to-claims-based-authentication-in-sharepoint-2013)」を参照してください。

主なリソース:

- [Project Server 2013 へのアップグレード プロセスの概要](https://go.microsoft.com/fwlink/p/?linkid=841274)

- [データベースおよび Project Web App サイト コレクションをアップグレードする (Project Server 2013)](https://go.microsoft.com/fwlink/p/?linkid=841272)

- [Microsoft Project Server のアップグレードプロセスの図](https://go.microsoft.com/fwlink/p/?linkid=841270)

- [高度なデータベース統合、Project Server 2010 から2013への移行は、簡単な手順で8つ](https://go.microsoft.com/fwlink/p/?linkid=841271)

### <a name="step-2-migrate-to-project-server-2016"></a>手順 2: Project Server 2016 に移行する

Project Server 2013 に移動し、データが正常に移行されたことを確認した後、次の手順では、Project Server 2016 に移行します。

詳細については、「 [Upgrade To Project Server 2016](https://docs.microsoft.com/Project/upgrade-to-project-server-2016)」を参照してください。

主なリソース:

- [Project Server 2016 のアップグレード プロセスの概要](https://docs.microsoft.com/Project/overview-of-the-project-server-2016-upgrade-process)

  Project Server 2013 から Project Server 2016 にアップグレードするために必要な作業について説明します。

- [Project Server 2016 へのアップグレードを計画する](https://docs.microsoft.com/Project/plan-for-upgrade-to-project-server-2016)

  「Project Server 2013 から Project Server 2016 にアップグレードするときの計画に関する考慮事項」を参照してください。

[Project Server 2016 アップグレードに関して知って](https://docs.microsoft.com/project/plan-for-upgrade-to-project-server-2016#thingknow) おくべきことは、このバージョンへのアップグレードに関する次の重要な変更点について説明します。

- Project Server 2016 環境を作成するときは、Project Server 2016 のインストールファイルが SharePoint Server 2016 に含まれていることに注意してください。 詳細については、「 [Deploy Project Server 2016](https://go.microsoft.com/fwlink/p/?linkid=841829)」を参照してください。

- Project Server 2016 では、リソース計画は廃止されました。 Project Server 2013 のリソース計画は、project Server 2016 および Project Online のリソース予約に移行されます。 詳細については、「 [概要: リソース予約](https://support.office.com/article/73eefb5a-81fe-42bf-980e-9532b1bdc870) 」を参照してください。

### <a name="step-3-migrate-to-project-server-2019"></a>手順 3: Project Server 2019 に移行する

Project Server 2016 に移行し、データが正常に移行されたことを確認した後、次の手順として、データを Project Server 2019 に移行します。

Project Server 2016 から Project Server 2019 にアップグレードするために必要な作業については、「 [upgrade To Project server 2019](https://docs.microsoft.com/Project/upgrade-to-project-server-2016)」を参照してください。

主なリソース:

- [Project Server 2019 のアップグレードプロセスの概要](https://docs.microsoft.com/project/overview-of-the-project-server-2019-upgrade-process)

  Project Server 2013 から Project Server 2016 にアップグレードするために必要な作業についての高度な理解を得ることができます。

- [Project Server 2019 へのアップグレードを計画する](https://docs.microsoft.com/project/plan-for-upgrade-to-project-server-2019)

  Project Server 2016 から Project Server 2019 にアップグレードする場合の計画に関する考慮事項を確認します。

- [Project Server 2019 のアップグレードに関して知っておくべき事柄](https://go.microsoft.com/fwlink/p/?linkid=841827)<br/><br/>このバージョンへのアップグレードの重要な変更点について説明します。これには次のものが含まれます。

   - アップグレードプロセスによって、Project Server 2016 データベースから SharePoint Server 2019 コンテンツデータベースにデータが移行されます。  Project Server 2019 は、SharePoint Server ファームに独自の Project Server データベースを作成しなくなります。

   - アップグレード後に、Project Web App にいくつかの変更が加えられていることに注意してください。  詳細については、「 [Project Server 2019 の新機能](https://docs.microsoft.com/project/what-s-new-for-it-pros-in-project-server-2019#PWAChanges)」を参照してください。

**その他の技術情報**:

- [Project Online サービスの説明](https://go.microsoft.com/fwlink/p/?linkid=841280): project Server 2016 および Project Online Premium に含まれているポートフォリオ管理機能を参照してください。

- [Microsoft Office Project ポートフォリオサーバー2010移行ガイド](https://go.microsoft.com/fwlink/p/?linkid=841279)

## <a name="summary-of-options-for-office-2010-client-and-servers-and-windows-7"></a>Office 2010 のクライアントおよびサーバーおよび Windows 7 のオプションの概要

Office 2010 サーバー/クライアント、および Windows 7のアップグレード、移行、およびクラウドへの移行オプションを視覚的にまとめた概要は、[サポート終了ポスター](../downloads/Office2010Windows7EndOfSupport.pdf) をご覧ください。

[![Office 2010 のクライアントおよびサーバーおよび Windows 7 ポスターのサポート終了](../media/upgrade-from-office-2010-servers-and-products/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)

このポスターは、Office 2010 のクライアントおよびサーバー製品と Windows 7 のサポート終了を回避するために実行できるさまざまなパスを示しています。これには、Microsoft 365 Enterprise で推奨されるパスとオプションのサポートが強調表示されています。

このポスターを [ダウンロード](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Office2010Windows7EndOfSupport.pdf) して、レター、リーガル、またはタブロイド (11 x 17) 形式で印刷することもできます。

## <a name="related-topics"></a>関連トピック

[SharePoint 2010 からのアップグレード](upgrade-from-sharepoint-2010.md)

[Office 2010 サーバー/クライアントからアップグレードする](upgrade-from-office-2010-servers-and-products.md)
