---
title: 考慮すべき 2007 の移行オプションをSharePointする
ms.author: tracyp
author: MSFTTracyP
manager: scotv
ms.date: 1/31/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-solutions
ms.localizationpriority: medium
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
description: この記事には、SharePoint Server 2007 を使用してアップグレードの計画に役立つユーザー向けの情報が含まれています。
ms.openlocfilehash: 044bfce8ea64233950fa291c72896f36531d206e
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65090753"
---
# <a name="sharepoint-2007-migration-options-to-consider"></a>考慮すべき 2007 の移行オプションをSharePointする

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

Microsoft SharePoint 2007 および SharePoint Server 2007 はサポート終了に達しました。 アップグレードの時間です。 この記事では、移行オプションに関する情報を提供します。
  
## <a name="common-upgrade-strategies-for-sharepoint"></a>SharePointの一般的なアップグレード戦略

SharePoint サーバー環境をアップグレードするには、複数の方法があります。 Microsoft Office SharePoint Server 2007 ファームがある場合は、アップグレード方法の例をいくつか次に示します。
  
- データベース接続
    
- 並べてアップグレードする
    
- 一括アップグレード
    
- ハイブリッド アップグレード (分離されたデータベースを使用したインプレース/個別のデータベース接続)
    
- SharePoint ハイブリッド (オンラインでオンプレミス SharePointに接続)
    
- サイト コレクションまたはライブラリ間でデータを手動で移動する
    
- FastTrack ウィザードを Microsoft 365 にアップグレードする ([SharePoint Online 展開アドバイザー](https://aka.ms/spoguidance))
    
- Microsoft 365の SharePoint Online (SPO) への移行 API
    
最適な機能は何ですか?
  
ファームの機能と使用に関する知識は、アップグレードに関する戦術的な強みです。 ユーザーがSharePoint ファームを使用する方法は、オプションから選択するのに役立ちます。
  
> [!TIP]
> Microsoft Office SharePoint Server 2007 には、ここでは説明していない段階的なアップグレードもあります。 ステップ固有のアップグレードに関する記事の一覧については、[SharePoint Server 2007 のサポート終了ロードマップを](sharepoint-2007-end-of-support.md)参照してください。 
  
アップグレードするSharePointのバージョンについては、[必ず製品](https://support.microsoft.com/lifecycle/search)ライフサイクルとシステム要件を確認してください。 これは、次のアップグレードが必要になるタイミングを認識するためです (たとえば、SharePoint Server 2010 などのレガシ製品で一時停止してアップグレードを計画する場合は、サポート終了日がわかっていることを確認してください)、プランをサポートするハードウェアがあることを確認してください。 
  
SharePoint サイトの一部または全部をクラウドのMicrosoft 365に移行する予定がある場合は、Microsoft 365へのリンクをブックマーク[し、サービスの説明をOffice 365](/office365/servicedescriptions/office-365-service-descriptions-technet-library)します。 サービスの説明は、SharePoint Online 機能とオンプレミスのSharePoint サーバーとの違いについて説明する必要があります。 サーバー 2007 ファームMicrosoft Office SharePoint機能をアップグレードします。 インストールに破損しているサイトがある場合は、アップグレードする前に修正してください。
  
## <a name="a-note-about-managing-risk"></a>リスクの管理に関するメモ

"side-by-side" のようなメソッドは、アップグレード ロジックのスキームで重要です。 並べてアップグレードするときは、Microsoft Office SharePoint Server 2007 ファームを維持しますが、新しいハードウェア上にファームから次のバージョン (SharePoint Server 2010) を構築します。 これは、次の 3 つの方法で役立ちます。
  
1. データベースアタッチを使用して、Microsoft Office SharePoint Server 2007 データベースのバックアップを個別にアップグレードする場所があります。
    
2. Microsoft Office SharePoint Server 2007 ファームで使用されている重要なドキュメント ライブラリとその他の情報がごくわずかである場合は、Microsoft Office SharePoint Server 2007 から SharePointにデータを手動で移動することを選択できます。 Server 2010 を使用するか、特定のサイトと Web のみを次のバージョンに移行します (これにより、ジョブが簡単になります)。
    
3. Microsoft Office SharePoint Server 2007 サーバー ファームに対して行う操作が少ないほど、アップグレード時にファームに含まれるデータが直接安全になります。
    
In-Placeアップグレードなどの方法は、Microsoft Office SharePoint Server 2007 ファームで直接動作するため、パスを破棄して元の環境からやり直す簡単なオプションが少なくなります。 可能な限り、いくつかの安全策 (元の環境のバックアップの作成とテストなど) を構築します。 たとえば、Microsoft Office SharePoint Server 2007 ファームが仮想であり、バックアップと復元の目的で複製されている場合は、アップグレードのためにサービスウィンドウの前に最新のデータベースをバックアップして復元します。 データベースバックアップを復元するオプションがあることを知っておくと、フェールセーフになるだけでなく、安心できます。
  
> [!TIP]
> [Microsoft Office SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc261992(v=office.12))、[SharePoint Server 2010、SharePoint Server 2013](/previous-versions/office/sharepoint-server-2010/cc261992(v=office.14))、SharePoint [Server 2016](/SharePoint/upgrade-and-update/best-practices-for-upgrade) の[](/SharePoint/upgrade-and-update/best-practices-for-upgrading-from-sharepoint-2010-to-sharepoint-2013)アップグレードに関するベスト プラクティスドキュメントが存在します。 アップグレードまたはMicrosoft 365移行の経験がある [Microsoft パートナー](https://partnercenter.microsoft.com/pcv/search)を検索することもできます。 
  
## <a name="make-your-plan"></a>計画を立てる

アップグレードする必要がある場合は、プランが必要であり、1 つのサイズがこれらのケースにすべて適合するわけではありません。 プランは、"SharePoint Online を使用してMicrosoft 365 サブスクリプションを作成し、ドメインを登録し、そこにファイルを保存するようにユーザーをリダイレクトする" という簡単な場合があります。 また、そうでない場合もあります。 その決定は自分の判断であり、自分とユーザーが本当に必要としているものにかかっています。
  
> [!NOTE]
> ライフサイクルが終了したソフトウェアで実行するのは危険です。 サポート対象外の製品は、問題が見つかったときに修正プログラムが適用されなくなりました。 また、これは、新しいセキュリティの脅威が発生した場合、ライフサイクルの終了製品がサポートされなくなったため、セキュリティパッチや修正プログラムがないことを意味します。 この状況は避けてください。 
  
### <a name="first-know-your-farm"></a>まず、ファームを把握する

アップグレードする場合、意思決定は、組織のファームが行う内容に基づく必要があります。 どのようなニーズが満たされますか? その役割は何ですか? 会社の各ファームには、異なるロールが含まれる場合があります。 SharePoint ファームの中には *重要な* 場合もあれば、ファイル アーカイブである場合もあります。安全に保管できます。 または、ファームが一度に多数のロールを満たす場合は、サイト コレクション、Web、またはドキュメント ライブラリが行う機能、カスタマイズ、およびそれらの重要性を把握することが必要になる場合があります。 このレベルでのデータの分析は、多くの作業に見えますが、アップグレードまたは移行する前にドメインをマスターする時間と労力を節約できます。 すべての移動部分と最も重要なビットがわかったら、成長し、後に残すことができるものもわかります。 その知識は、今後のメリットに過ぎません。 
  
では、SharePoint サーバー ファームについて、ユーザーが最も重要と言っていることは何ですか?
  
- 組み込みのSharePoint機能
    
- 大きなデータ コーパス (ファイルのアーカイブなど)
    
- 可用性
    
- ファーム内の重要なアプリ、Web パーツ、またはドキュメント (ミッション クリティカル ファーム)
    
- コンプライアンス基準が満たされている
    
- カスタマイズ
    
SharePoint ファームからビジネスに不可欠なものを実行する場合は、クライアント サービス要件に関する重要なデータの大規模なカタログのように動作するとします。"Critical apps" の横に目盛りを付けるだけでなく、"可用性" も設定できます。つまり、しばらくの間SharePointを使用できなかった場合、ビジネスは影響を受けます。 同様に、ファームが提供する重要なサービスはカスタム コード、サイト定義、または連携する多くのカスタマイズに基づいているため、"カスタマイズ" をチェックすることもできます。
  
ソフトウェアに組み込まれているものを使用せずにこれらのニーズを満たSharePoint、一般的にソフトウェアを更新して通常の管理とメンテナンスを行う場合は、"組み込みのSharePoint" を選択している可能性があります。これは、古いバージョンのSharePointに座る理由でもあります。 つまり、必要な処理は既に行われ、Microsoft Office SharePoint Server 2007 のサポート終了時に、今までアップグレードする必要はありません。
  
これらの項目を箇条書きにすると、アップグレードの条件が作成されます。 つまり、アップグレードを検討するには、このバーを満たす必要があります。 これにより、現在のニーズに合わないメソッドを除外する方法が提供されます。
  
### <a name="a-simple-sample-plan"></a>単純なサンプル プラン

SharePointアップグレードのパスについては、リーダーシップやその他の管理者との間で、より広範な合意が必要になる場合があります。 SharePoint サーバー管理者は、多くの場合、Microsoft SQL Server管理者と協力し、ネットワークチームやセキュリティ チームと連携します。 多くの利害関係者がいる場合は、アップグレードと移行計画の契約を作成するか、調整する必要がある場合があります。 たとえば、会社の一部がMicrosoft 365で SharePoint Online を使用するようにデータを移行する場合、ネットワーク内でパフォーマンスチューニングまたはテストが必要になる可能性があります。 影響を受けるチームには事前に通知する必要があります。
  
簡単なサンプルでは、SharePoint管理者の提案を示し、すべての利害関係者が合意した計画を一覧表示します。 明確にするために、契約と決定事項を文書化します。
  
この計画は、ファームの詳細な分析の後に開始され、ファームの役割、問題点、およびその他の重要な情報の特定を試み、アップグレード オプションの絞り込みにつながりそうです。 その後、アップグレードの提案はSharePoint管理者によって行われ、関係者はアクション プランに同意します。
  
"最も重要な" 箇条書き:
  
- 可用性、SharePointに組み込まれている機能、コンプライアンス標準。
    
- ほとんどのデータは 3 つのサイト コレクション上にあり、1 つの会議ワークスペースが開発チームによって重要で、世界中の複数のタイム ゾーンで頻繁に使用されています。
    
- 広く使用されているサイトは他に 17 個あります。
    
- 2 つのドキュメント ライブラリ (ルート サイト コレクション上の会議ワークスペースとドキュメント) が最も大きい (それぞれ 8,000 を超えるドキュメント)。 スプレッドシートの添付ファイルを含む多数のアーカイブされたドキュメントとリストがあります。
    
- 機密データを持つライブラリのリストは 14 個あり、コンプライアンスを維持する必要があります。
    
- どこに行っても、保留と電子検出を行う能力が必要です。
    
- InfoSec 規則により、このデータの一部はオンプレミスに留まる必要があります。
    
 **アップグレードと移行の選択肢:**
  
| はい | いいえ |
|:-----|:-----|
|データベースアタッチを使用してデータベースをアップグレードする  <br/> |一括アップグレード  <br/> |
|ファームを並べてアップグレードする  <br/> |ハイブリッド アップグレード  <br/> |
|Microsoft 365の SPO への移行 API (個人用サイト データの場合)  <br/> |SharePoint ハイブリッド (まだ必要ありません)  <br/> |
|重要なデータに対してオンラインSharePointに手動で移行する場合  <br/> |FastTrack ウィザードをMicrosoft 365にアップグレードする  <br/> |
   
 **提案されたプラン:**
  
データベースを最初にアップグレードできるように、一部の仮想化されたオンプレミスのバージョンのSharePointサイド バイ サイドでアップグレードします。 2007 SharePointから 2010 SharePointに移動します。 管理者と開発者は、結果として得られるファームをテストします。 ユーザーは、結果として得られるファームをテストします。 この間に発生するショー停止の問題を修正します。 繰り返しになりますが、2010 データベースSharePoint 2013 SharePointにアップグレードします。 テストします。 ユーザー テスト/パイロット。 この間に発生するショー停止の問題を修正します。
  
- SPO を使用した検索フェデレーション ハイブリッドがニーズを満たしているかどうかを検討してください。
    
- ここから [SharePoint](https://fasttrack.microsoft.com) Online にアップグレードする場合は、FastTrackサポートを検討してください。 
    
- サイト コレクションを Microsoft 365 サブスクリプションにオフロードできるかどうかを決定します。 (Microsoft 365は、多くの[コンプライアンス基準を](/compliance/regulatory/offering-home)満たしています。 Microsoft 365電子[情報開示](https://support.office.com/article/edea80d6-20a7-40fb-b8c4-5e8c8395f6da)があり、コンプライアンス センターを通じて[保留](https://support.office.com/article/A18F8975-AA7F-43B4-A7D6-001D14744D8E)を行うことができます)。 
    
それ以外の場合は、SharePoint Server 2016 へのサイド バイ サイド アップグレードを続行します。
  
> [!NOTE]
> アップグレードを計画している管理者によって行われた推奨事項と実際のプロセスの間には、アップグレードが依存している他の利害関係者との会話があります。 たとえば、経済が管理者に計画の変更を強制する場合があります。 最終的な決定が何であれ、今後合意された計画が何であるかを文書化する必要があります。 次のようになります。 
  
 **自分のアクション プラン:**
  
オンプレミスでは、仮想環境を使用して、既定の SharePoint Server 2010 および 2013 をビルドします。 SharePoint Server 2016 は、2016 のシステム要件を満たす新しいハードウェア上に構築されます。 2007 年 SharePoint からサーバー 2016 までの間のすべてのバージョンにデータベースをアップグレードするために、データベースアタッチ SharePointを行います。 ネイティブ機能がまだニーズを満たしていない場合は、現在、SharePoint Server 2016 環境でコアカスタマイズが再作成され、テストされています。 成功した場合は、アップグレードされたデータベースを含む新しいハードウェア上にオンプレミス ファームがあり、カスタマイズが少なくなります。 アップグレードされたコンテンツ データベースを SharePoint Server 2013 の新しいサイト コレクションにアタッチし、テスト、ユーザー テスト/パイロットを行い、ライブ使用のために新しいSharePoint Server 2016 環境に DNS カットオーバーを行います。
  
- 現時点では、SharePoint Server 2016 と SharePoint Online 間のフェデレーション ハイブリッドは検討しません。
    
- サイトの推定 35% が、バニティ ドメインを持つ新しい SPO サイトに変わるか、最終的にはOneDrive for Businessストレージになります。 サイトを変換したり、新しいサイトを SPO にルーティングしたりする他の機会を探しています。
    
- 移行のこの部分の一部は手動で、ドラッグ アンド ドロップで個人用サイトをOneDrive for Businessし、一部は移行 API によって行われます。
    
詳細な手順、または特定のアップグレードの指示へのリンクの数は、プランに従う必要があります。 MOSS 2007 コンピューターは使用停止にすべきではなく、比較のために仮想環境を維持する必要があります。ただし、ユーザーが SharePoint Server 2016 にリダイレクトされると、アップグレードは完了します。
  
多くの場合、方法を選択する際の主な要因は、アップグレードの合計コストと時間のコストです (詳細については、SharePoint移行ロードマップの記事を参照してください)。 ただし、今後の計画は、期待を設定し、賢明に選択し、成功がどのようになるかをフレーミングすることで大いに役立ちます。
  
## <a name="related-links"></a>関連リンク

[Office 2007 のサーバーとクライアントからのアップグレードに役立つリソース](upgrade-from-office-2007-servers-and-products.md)
  
[Microsoft ライフサイクル ポリシーとライフサイクル検索](https://support.microsoft.com/lifecycle)
  
[アップグレードまたは移行に役立つ Microsoft パートナーを検索する](https://partnercenter.microsoft.com/pcv/search)
