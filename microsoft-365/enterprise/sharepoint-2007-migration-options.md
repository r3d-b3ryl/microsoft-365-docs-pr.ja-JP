---
title: SharePoint 2007 の移行オプションを検討する
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 1/31/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
search.appverid:
- MET150
- SPS150
- OSU140
- SPO160
- SPB160
- OSI150
- OSI160
- BSA160
- OSU160
ms.assetid: 66325a43-5816-4f8e-81ba-c11b71345b7c
f1.keywords:
- NOCSH
ms.custom:
- seo-marvel-apr2020
description: この記事では、アップグレードの計画に役立SharePointサーバー 2007 を使用しているユーザー向け情報を示します。
ms.openlocfilehash: 38c4713b7dfb705c99d970c5f68a37b031c951a5
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59210543"
---
# <a name="sharepoint-2007-migration-options-to-consider"></a>SharePoint 2007 の移行オプションを検討する

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

Microsoft SharePoint 2007 および SharePoint Server 2007 はサポートの終了に達しました。 アップグレードの時期です! この記事では、移行オプションに関する情報を提供します。
  
## <a name="common-upgrade-strategies-for-sharepoint"></a>アップグレードに関する一般的なSharePoint

サーバー環境をアップグレードするには、複数SharePointがあります。 サーバー 2007 ファームMicrosoft Office SharePointアップグレード方法の例を次に示します。
  
- データベース接続
    
- サイド バイ サイド アップグレード
    
- 一括アップグレード
    
- ハイブリッド アップグレード (デタッチされたデータベースを含むインプレイス/個別のデータベース接続)
    
- SharePointハイブリッド (オンプレミス のサーバーにオンラインで接続SharePoint)
    
- サイト コレクションまたはライブラリ間でデータを手動で移動する
    
- FastTrackウィザードを Microsoft 365 ( SharePoint 展開アドバイザー )[にアップグレードする](https://aka.ms/spoguidance)
    
- 移行 API から SharePoint Online (SPO) への移行Microsoft 365
    
最適な機能は何ですか?
  
ファームの動作と使用に関する知識は、アップグレードに関する戦術的な強みです。 ユーザーがファームファームをSharePoint方法は、オプションから選ぶのに役立ちます。
  
> [!TIP]
> Microsoft Office SharePoint Server 2007 には、ここでは段階的なアップグレードも含まれています。 手順固有のアップグレード記事の一覧については、「SharePoint [Server 2007](sharepoint-2007-end-of-support.md)のサポート ロードマップ」を参照してください。 
  
アップグレードする製品のバージョン[については](https://support.microsoft.com/lifecycle/search)、製品ライフサイクルとシステム要件SharePoint確認してください。 そのため、次のアップグレードが必要になる時期を認識できます (たとえば、SharePoint Server 2010 などの従来の製品でアップグレードを計画する場合は、そのサポート終了日を確認してください)、計画をサポートするハードウェアが確実に用意されている必要があります。 
  
SharePoint サイトの一部またはすべてをクラウドの Microsoft 365 に移行する予定の場合は、Microsoft 365 および Office 365 サービスの説明へのリンクをブックマーク[する必要](/office365/servicedescriptions/office-365-service-descriptions-technet-library)があります。 オンライン機能の詳細と、SharePointサーバーとの違いについて説明するには、サービスのSharePointがあります。 サーバー 2007 Microsoft Office SharePoint機能をアップグレードします。 インストールに壊れたサイトがある場合は、アップグレード前に修正してください。
  
## <a name="a-note-about-managing-risk"></a>リスクの管理に関するメモ

アップグレード ロジックのスキームでは、"サイド バイ サイド" のようなメソッドが重要です。 サイド バイ サイドでアップグレードする場合は、Microsoft Office SharePoint Server 2007 ファームを維持しますが、新しいハードウェアでファームから次のバージョン (SharePoint Server 2010) を構築します。 これは、次の 3 つの方法で役立ちます。
  
1. データベース接続を使用して、サーバー 2007 データベースMicrosoft Office SharePointバックアップを取って個別にアップグレードする場所があります。
    
2. Microsoft Office SharePoint Server 2007 ファームで使用されている重要なドキュメント ライブラリや他の情報の数が少ない場合は、Microsoft Office SharePoint Server 2007 から SharePoint Server 2010 に手動でデータを移動するか、特定のサイトと Web のみを次のバージョンに移動するか (作業を容易にすることができます)。
    
3. サーバー 2007 サーバー Microsoft Office SharePointに対して行う操作が少なMicrosoft Office SharePoint、アップグレード時にファームに含まれるデータが安全になります。
    
In-Place アップグレードのような方法は、Microsoft Office SharePoint Server 2007 ファームで直接機能し、パスを放棄して元の環境から再び開始する簡単なオプションを少なくできます。 可能な限り、いくつかの安全対策 (元の環境のバックアップの取得とテストなど) を組み込む必要があります。 たとえば、Microsoft Office SharePoint Server 2007 ファームが仮想であり、バックアップと復元の目的で複製されている場合は、アップグレードのサービス ウィンドウの前に最新のデータベースをバックアップして復元します。 データベース バックアップを復元するオプションがある場合は、フェールセーフを与えるだけでなく、安心できます。
  
> [!TIP]
> アップグレードのベスト プラクティス ドキュメントは[、Microsoft Office SharePoint Server 2007、SharePoint](/previous-versions/office/sharepoint-2007-products-and-technologies/cc261992(v=office.12)) [Server 2010、SharePoint](/previous-versions/office/sharepoint-server-2010/cc261992(v=office.14)) [Server 2013、](/SharePoint/upgrade-and-update/best-practices-for-upgrading-from-sharepoint-2010-to-sharepoint-2013)および SharePoint Server [2016](/SharePoint/upgrade-and-update/best-practices-for-upgrade)に存在します。 アップグレードや移行の経験[がある Microsoft パートナー](https://partnercenter.microsoft.com/pcv/search) Microsoft 365できます。 
  
## <a name="make-your-plan"></a>計画を立て

アップグレードする必要がある場合は、プランが必要であり、1 つのサイズがこのような場合にすべて収まらない場合があります。 プランは、「SharePoint Microsoft 365 Online で Microsoft 365 サブスクリプションを作成し、ドメインを登録し、そこにファイルを保存するユーザーをリダイレクトする」という単純な方法です。 そうではない場合があります。 この決定はユーザーの判断であり、ユーザーが本当に必要としているものに影響します。
  
> [!NOTE]
> ライフサイクルが終了したソフトウェアで実行することは危険です。 サポートが終了している製品は、問題が見つかったときに修正プログラムが適用されなくなりました。 また、新しいセキュリティ上の脅威が発生した場合、ライフサイクルの終了製品がサポートされなくなったため、セキュリティパッチや修正プログラムが存在しなくなるという意味です。 その状況は避けて下さい! 
  
### <a name="first-know-your-farm"></a>まず、ファームを知る

アップグレード時の意思決定は、ファームが組織に対して何をしているかに基づいて行う必要があります。 どのようなニーズを満たす必要がありますか? その役割は何ですか? 会社の各ファームの役割は異なる場合があります。 一部のSharePointファームは重要な場合があります。ファイル アーカイブである場合があります。安全に管理できます。 または、ファームが一度に多くの役割を満たしている場合は、サイト コレクション、Web、またはドキュメント ライブラリの機能、カスタマイズ、および重要な役割を知る必要があります。 このレベルでデータを分析すると、多くの作業に見えるかもしれませんが、アップグレードまたは移行する前にドメインをマスターするための時間と労力を節約できます。 すべての移動部分と最も重要なビットを知った後は、自分が何を生き残り、取り残すのかを知る必要があります。 この知識は、今後のメリットにしかならな 
  
では、ユーザーがサーバー ファームについて最も重要SharePointは何ですか?
  
- 組み込みのSharePoint機能
    
- 大きなデータコーパス (ファイルのアーカイブなど)
    
- 可用性
    
- ファーム内の重要なアプリ、Web パーツ、またはドキュメント (ミッション クリティカル ファーム)
    
- コンプライアンス基準が満たされている
    
- カスタマイズ
    
SharePoint ファームからビジネスに不可欠な何かを実行する場合は、クライアント サービス要件に関する重要なデータの大規模なカタログのように動作すると、"重要なアプリ" の横にチェックを入れるだけでなく、"可用性" を設定することもできます。つまり、しばらくの間 SharePoint を使用できなかった場合、ビジネスは影響を受け取る可能性があります。 同様に、ファームが提供する重要なサービスは、カスタム コード、サイト定義、または一緒に動作する多数のカスタマイズに基づくため、「カスタマイズ」をチェックできます。
  
SharePointがソフトウェアに組み込まれる機能を使用する以外に何もせずにこれらのニーズを満たした場合、通常は更新して通常の管理とメンテナンスを実行している場合は、'組み込み SharePoint' を選択している可能性があります。これは、以前のバージョンの SharePoint に座る理由にもなっている可能性があります。 つまり、既に必要な機能を実行し、Microsoft Office SharePoint Server 2007 のサポート終了時点でアップグレードする必要がなかったのです。
  
これらの項目の箇条書きを行う場合は、アップグレードの条件を作成します。 つまり、アップグレードを行う場合は、このバーを満たす必要があります。 これにより、現在ニーズに合わないメソッドを排除できます。
  
### <a name="a-simple-sample-plan"></a>簡単なサンプル プラン

アップグレードのパスに関して、リーダーシップや他の管理者とのSharePoint必要があります。 SharePointサーバー管理者は、多くの場合、Microsoft SQL Server、ネットワークチームやセキュリティ チームなどと協力します。 関係者が多い場合は、アップグレードと移行計画に関する契約を作成するか、調整する必要があります。 たとえば、Microsoft 365 で会社の一部が SharePoint Online を使用するデータを移行する場合、ネットワーク内でパフォーマンス調整やテストが必要になる可能性があります。 影響を受けるチームには事前に通知する必要があります。
  
簡単なサンプルでは、管理者SharePoint提案を表示し、すべての関係者が合意した計画を一覧表示します。 明確にするために、契約と決定を文書化します。
  
この計画は、ファームの詳細な分析の後に開始され、一部のアップグレード オプションの絞り込みにつながるファーム、痛みポイント、その他の重要な情報の役割を特定します。 その後、アップグレード提案は管理者SharePoint行い、関係者はアクション プランに同意します。
  
"最も重要な" 箇条書きリスト:
  
- 可用性、ユーザーに組み込SharePoint、コンプライアンス標準。
    
- ほとんどのデータは 3 つのサイト コレクションに含まれており、開発チームが使用する会議ワークスペースは 1 つであり、世界中の複数のタイム ゾーンで特に重要で多用されています。
    
- 他にも広く使用されているサイトは 17 件です。
    
- 2 つのドキュメント ライブラリ (ルート サイト コレクションの会議ワークスペースとドキュメント) が最大 (それぞれ 8000 ドキュメントを超える) です。 スプレッドシートの添付ファイルを含む多数のアーカイブ済みドキュメントとリストがあります。
    
- コンプライアンスにとどまる必要がある機密データを持つライブラリのリストは 14 個です。
    
- どこに行っても保留と電子発見を行う能力が必要です。
    
- このデータの一部は、InfoSec ルールのためにオンプレミスに残る必要があります。
    
 **アップグレードと移行の選択肢:**
  
| はい | いいえ |
|:-----|:-----|
|データベース接続を使用してデータベースをアップグレードする  <br/> |一括アップグレード  <br/> |
|ファームを並べてアップグレードする  <br/> |ハイブリッド アップグレード  <br/> |
|サイト内の SPO へのMicrosoft 365 API (個人用サイト データの場合)  <br/> |SharePointハイブリッド (まだ必要ありません)  <br/> |
|重要なデータに対するSharePointオンラインへの手動データの移行  <br/> |FastTrackウィザードのアップグレードを実行Microsoft 365  <br/> |
   
 **私の提案された計画:**
  
最初にデータベースをアップグレードSharePoint、一部の仮想化されたバージョンのオンプレミスをアップグレードします。 2007 SharePointから 2010 SharePointに移動します。 管理者と開発者は、結果のファームをテストします。 ユーザーは、結果のファームをテストします。 この期間中に、表示停止の問題を修正します。 繰り返しますが、2010 データベースSharePoint 2013 にSharePointします。 テストします。 ユーザー のテスト/パイロット。 この期間中に、表示停止の問題を修正します。
  
- SPO を含む検索フェデレーション ハイブリッドがニーズを満たした場合を検討します。
    
- ここから[FastTrackオンライン](https://fasttrack.microsoft.com)にアップグレードする場合は、SharePointを検討してください。 
    
- 任意のサイト コレクションをサブスクリプションにオフロードMicrosoft 365します。 (Microsoft 365多くのコンプライアンス基準[を満たしています](/compliance/regulatory/offering-home)。 Microsoft 365持[ち、](https://support.office.com/article/edea80d6-20a7-40fb-b8c4-5e8c8395f6da)コンプライアンス センターを[通](https://support.office.com/article/A18F8975-AA7F-43B4-A7D6-001D14744D8E)じて保留を実行できます)。 
    
それ以外の場合は、サーバー 2016 へのサイド バイ サイド アップグレードSharePoint続行します。
  
> [!NOTE]
> アップグレードを計画している管理者が行った推奨事項と実際のプロセスの間で、アップグレードが依存している他の関係者との会話が行います。 たとえば、経済的に管理者に計画の変更を強制する場合があります。 最終的な決定が何であれ、今後、合意された計画が何かを文書化する必要があります。 次のような場合があります。 
  
 **自分のアクション プラン:**
  
オンプレミスでは、仮想環境を使用して、サーバー 2010 および 2013 SharePoint既定の環境を構築します。 SharePointサーバー 2016 は、2016 のシステム要件を満たす新しいハードウェア上に構築されます。 データベース接続は、2007 年から 2016 年SharePointサーバー 2016 との間のすべてのバージョンSharePointします。 この時点で、SharePoint Server 2016 環境では、ネイティブ機能がニーズを満たしていない場合に、コアカスタマイズが再作成され、テストされています。 成功した場合は、アップグレードされたデータベースを含む新しいハードウェア上にオンプレミス ファームを作成し、カスタマイズを少なくします。 アップグレードされたコンテンツ データベースを SharePoint Server 2013 の新しいサイト コレクションに接続し、テスト、ユーザーテスト/パイロットを行い、ライブで使用するために新しい SharePoint Server 2016 環境に DNS カットオーバーを実行します。
  
- 現在、サーバー 2016 と SharePointオンライン間のフェデレーション ハイブリッドSharePoint検討しません。
    
- サイトの推定 35% が、バニティ ドメインを持つ新しい SPO サイトに変わったり、最終的にはストレージOneDrive for Businessすることができます。 サイトを変換したり、新しいサイトを SPO にルーティングする他の機会を探しています。
    
- 移行のこの部分の一部は手動で、個人用サイトにドラッグ アンド OneDrive for Business、一部は移行 API によって行います。
    
詳細な手順、または特定のアップグレード方法へのリンクの数は、計画に従う必要があります。 MOSS 2007 コンピューターを使用停止にし、比較のために仮想環境を維持する必要があります。ただし、アップグレードは、ユーザーがサーバー 2016 にリダイレクトSharePoint完了します。
  
多くの場合、方法を選択する際の主な要因は、アップグレードの総コストと時間のコストです (詳細については、「SharePoint 移行ロードマップ」の記事を参照してください)。 ただし、先に計画を立てていると、期待を設定し、賢明に選択し、成功の見た目をフレーミングする際に大きなメリットがあります。
  
## <a name="related-links"></a>関連リンク

[Office 2007 のサーバーとクライアントからのアップグレードに役立つリソース](upgrade-from-office-2007-servers-and-products.md)
  
[Microsoft ライフサイクル ポリシーとライフサイクル検索](https://support.microsoft.com/lifecycle)
  
[アップグレードまたは移行に役立つ Microsoft パートナーを検索する](https://partnercenter.microsoft.com/pcv/search)
