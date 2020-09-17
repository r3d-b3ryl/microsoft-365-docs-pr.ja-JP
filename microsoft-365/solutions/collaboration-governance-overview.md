---
title: Microsoft 365 のコラボレーションガバナンスの概要
ms.reviewer: mmclean
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: Microsoft 365 グループ、Teams、SharePoint、Yammer の関連する機能を管理する方法について説明します。
ms.openlocfilehash: b217dc089eb150d01eed9cd720b2caa290d54bf1
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950714"
---
# <a name="overview-of-collaboration-governance-in-microsoft-365"></a>Microsoft 365 のコラボレーションガバナンスの概要

Microsoft 365 には、組織で必要となる可能性があるすべてのガバナンス機能を実装するための豊富なツールセットがあります。 この記事では、IT プロフェッショナルが適切な質問をして、ガバナンスの要件を確認する方法と、組織のプロファイルに基づいてそれらを満たす方法について説明します。

## <a name="what-are-microsoft-365-groups"></a>Microsoft 365 グループとは

今日、組織は多様なツールセットを使用していることがわかっています。 開発者は、チームチャット、メールを送信する役員、およびエンタープライズソーシャルを介して接続する組織全体を使用しています。 グループはそれぞれ一意であり、独自の機能上のニーズと作業スタイルがあるため、複数のコラボレーションツールが使用されています。 一部のユーザーはメールのみを使用し、他のユーザーは主にチャットに住んでいます。 

ユーザーは、IT が提供するツールがニーズに合わないと思った場合、自分のシナリオに対応するお気に入りのコンシューマー アプリをダウンロードすることになるでしょう。 このプロセスにより、ユーザーはすぐに使い始めることができますが、複数のログイン、共有の困難さ、コンテンツの閲覧場所の不足など、組織全体でユーザー エクスペリエンスが低下します。 この概念は「シャドウ IT」と呼ばれ、組織に重大なリスクをもたらします。 これにより、ユーザー アクセスを均一に管理し、セキュリティとサービス コンプライアンスのニーズを保証できる機能が減ります。

Microsoft 365 グループ、Teams、Yammer などのサービスは、ユーザーを強化し、共同作業に必要なツールを提供することで IT のシャドウを軽減します。 Microsoft 365 グループでは、共同作業を希望するユーザーのセットを選択し、それらのユーザーが共有するリソースのコレクションを簡単にセットアップすることができます。 グループにメンバーを追加すると、グループによって提供されるすべての資産に対して必要なアクセス許可が自動的に付与されます。 Teams と Yammer は、両方とも Microsoft 365 グループを使用してメンバーシップを管理します。

![Microsoft 365 グループと関連サービスを示す図](../media/microsoft-365-groups-hub-spoke.png)

Microsoft 365 グループには、組織内のグループの管理に役立つ、有効期限ポリシー、命名規則、ブロックされた単語ポリシーなど、さまざまなガバナンスコントロールが含まれています。 詳細については、「 [microsoft 365 グループおよび Microsoft Teams の組織とライフサイクルのガバナンスを計画](plan-organization-lifecycle-governance.md) する」を参照してください。

## <a name="technical-architecture"></a>技術アーキテクチャ

Microsoft 365 では、次の3つの主要な通信方法がサポートされています。

- Outlook: グループの受信トレイと予定表が共有される電子メールを通じた共同作業
- Microsoft Teams: 特定のサブグループによって開催される、さまざまなトピックに関する非公式でリアルタイム会話を可能にする常設チャットベースのワークスペース。
- Yammer: 共同作業のためのエンタープライズ ソーシャル エクスペリエンス

> [!NOTE]
> 他のチームワークアプリケーションを使用して新しいグループを作成します。たとえば、SharePoint、Planner、Stream などのグループは、Outlook の受信トレイと、Teams に接続する機能を備えています。

グループの作成場所に応じて、次のような特定のリソースが自動的にプロビジョニングされます。
- [受信トレイ](https://support.office.com/article/have-a-group-conversation-in-outlook-a0482e24-a769-4e39-a5ba-a7c56e828b22) -グループメンバー間の電子メールスレッドの場合。 この受信トレイにはメールアドレスが設定されており、従来の配布リストのように、グループ外のユーザーや組織外からのメッセージを受け付けるように設定できます。
 - [予定表](https://support.office.com/article/schedule-a-meeting-on-a-group-calendar-in-outlook-0cf1ad68-1034-4306-b367-d75e9818376a): グループに関連したスケジュール済みイベント用
- [SharePoint チームサイト](https://support.office.com/article/what-is-a-sharepoint-team-site-75545757-36c3-46a7-beed-0aaa74f0401e) –グループに関連する情報、リンク、およびコンテンツの中央リポジトリ
- [OneNote ノートブック](https://support.office.com/article/get-started-with-onenote-e768fafa-8f9b-4eac-8600-65aa10b2fe97) –アイデア、研究、情報を収集するためのものです。
- [Planner](https://support.office.com/article/microsoft-planner-help-4a9a13c6-3adf-4a60-a6fc-15c0b15e16fc): グループのメンバーへのプロジェクト タスクの割り当ておよび管理用
- [Yammer グループ](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2) –会話を行い、情報を共有するための共通の場所
- Teams – Microsoft 365 のチャットベースのワークスペース
- Stream-ビデオストリーミングサービス

> [!NOTE]
> Yammer または Teams によって作成された新しい Office 365 グループは、そのグループのユーザー間の主なコミュニケーションが各自の個別のクライアントで行われるため、Outlook やアドレス帳には表示されません。 Yammer グループを Teams に接続することはできません。

## <a name="collaboration-options"></a>グループ作業のオプション

複数の場所で共同作業を行ったり、Microsoft 365 内で会話したりすることができます。 会話を開始する場所を理解すると、コミュニケーションの戦略を定義するのに役立ちます。

![Teams、Yammer、Outlook をいつ使用するかを示す図](../media/inner-loop-outer-loop.png)

- Teams: チャット ベースのワークスペース (高速なコミュケーション) – 内部ループ
  - 日常的に作業するメンバーとの共同作業のために作成されています
  - 単一のエクスペリエンスでユーザーが簡単に情報を得られるようにします
  - タブ、コネクタおよびボットを追加します
  - Live chat、音声ビデオ会議、レコーディングされた会議

- Yammer: 組織全体をつなぐ (エンタープライズ ソーシャル) – 外部ループ
  - 共通の利息や専門知識を共有しているが、必ずしも日常的に共同作業するわけではないユーザーの、社内で働くグループのコミュニティ。
  - リーダーのつながり、学習コミュニティ、役割ベースのコミュニティ

- メールボックスと予定表 (電子メールベースのコラボレーション)
  - ユーザーグループとの対象指定された通信に使用する
  - 他のグループメンバーとの会議の共有予定表
 
すべてのグループは、ユーザーがコンテンツを共有し、カスタマイズされたページと作成者のニュースを作成できる、接続された SharePoint チームサイトを取得します。 [既存の SharePoint チームサイトを新しい Microsoft 365 グループに接続](https://docs.microsoft.com/sharepoint/dev/features/groupify/groupify-overview)することもできます。

## <a name="illustrations"></a>示さ

### <a name="microsoft-teams-and-related-productivity-services-in-microsoft-365-for-it-architects"></a>IT アーキテクト向け Microsoft 365 の Microsoft Teams と関連生産性サービス
Microsoft Teamsをリードする Microsoft 365 での生産性サービスの論理的なアーキテクチャ。

|**アイテム**|**説明**|
|:-----|:-----|
|[![Teams の論理的なアーキテクチャ ポスターのサムネイル](../downloads/msft-teams-logical-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-teams-logical-architecture.pdf) <br/> [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-teams-logical-architecture.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-teams-logical-architecture.vsdx)  <br>更新日: 2019 年 4 月   |マイクロソフトは、連携してデータ ガバナンス、セキュリティ、およびコンプライアンス機能を備えたコラボレーション エクスペリエンスを提供する、一連の生産性サービスを提供しています。 <br/> <br/>この一連の図は、Microsoft Teams をはじめとする、エンタープライ ズアーキテクト向けの生産性サービスの論理アーキテクチャを概説したものです。|


### <a name="groups-in-microsoft-365-for-it-architects"></a>IT アーキテクト向け Microsoft 365 のグループ
IT アーキテクトが Microsoft 365 のグループについて知っておくべきこと

|**アイテム**|**説明**|
|:-----|:-----|
|[![グループ インフォグラフィックのサムネイル](../downloads/msft-m365-groups-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) <br/> [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-groups.vsdx) <br> 更新日: 2019 年 6 月|これらの図は、さまざまな種類のグループがどのように作成および管理されているか、そしていくつかのガバナンスの推奨事項を詳述しています。|

## <a name="conference-sessions"></a>会議セッション

Microsoft 365 グループと Teams のガバナンスの詳細については、これらの電話会議セッションをご覧ください。

**事柄**

スケールでの管理とガバナンス、使用方法と導入のためのベストプラクティス、セルフサービスなど、Microsoft 365 グループの基本技術および新技術技術について説明します。

- [Microsoft 365 グループを採用する](https://www.youtube.com/watch?v=dAamBF1gb7M)

**ガバナンス**

グループの有効期限のライフサイクル、命名ポリシー、分類ラベル、外部ゲストとのコラボレーション、グループ作成のアクセス許可の管理方法について説明します。

- [コラボレーションを変革し、Office 365 グループとの統合を促進する](https://www.youtube.com/watch?v=Bhf_bKx3lAg)

**お客様の例**

グローバルなコラボレーションプラットフォームを提供するために、Microsoft 365 グループ、SharePoint、Teams、Yammer がどのように連携するかについて、舞台裏の例を参照してください。

- [Office 365 グループ、SharePoint、Teams、Yammer を使用してコラボレーションを検索する](https://www.youtube.com/watch?v=Rx9eVwqXeQk)
