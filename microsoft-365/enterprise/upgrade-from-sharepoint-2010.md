---
title: SharePoint 2010 からのアップグレード
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 04/13/2020
audience: ITPro
ms.topic: conceptual
ms.prod: office-online-server
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
search.appverid:
- MET150
- WSU140
- OSU140
ms.assetid: 985a357f-6db7-401f-bf7a-1bafdf1f312c
f1.keywords:
- NOCSH
description: SharePoint 2010 および Sharepoint Server 2010 からアップグレードするための情報とリソースを検索します。 2021年4月13日の両方のサポートをサポートします。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fba095a15164f8a09ce1e0a1cbd5ee9cd298aa74
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519765"
---
# <a name="upgrading-from-sharepoint-2010"></a>SharePoint 2010 からのアップグレード

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

Microsoft SharePoint 2010 と SharePoint Server 2010 は **、2021年4月 13** 日にサポート終了になります。 この記事では、既存の SharePoint Server 2010 データを Microsoft 365 の SharePoint Online に移行したり、オンプレミスの SharePoint Server 2010 環境をアップグレードしたりするのに役立つリソースを提供します。

## <a name="what-is-end-of-support"></a>*サポート終了* とは

ほとんどの Microsoft 製品には、新機能、バグ修正、セキュリティ修正プログラムなどを利用できるように、サポートライフサイクルが用意されています。 サポート終了日以降、製品は機能しなくなりますが、Microsoft は提供しなくなります。

- 発生する可能性のある問題のテクニカルサポート。

- サーバーの安定性と有用性に影響を与える可能性がある問題について、バグ修正が行われます。

- セキュリティ侵害に対してサーバーが脆弱になる可能性がある脆弱性に対するセキュリティ修正。

- タイム ゾーンの更新。

そのため、これ以上の更新プログラム、修正プログラム、または製品に対する修正プログラム (セキュリティパッチや修正プログラムを含む) はありません。 Microsoft サポートは、そのサポートの作業をより新しいバージョンに完全に移行しています。

SharePoint Server 2010 のサポート終了の方法では、製品をアップグレードして重要なデータを移行する前に、不要になったデータを削除します。

> [!NOTE]
> 通常、ソフトウェアライフサイクルは初回リリースから10年間持続します。 [Microsoft ソリューションプロバイダー](https://go.microsoft.com/fwlink/?linkid=841249) は、次のバージョンのソフトウェアへのアップグレード、または microsoft 365 移行 (またはその両方) への移行に役立てることができます。 特に、SharePoint で使用している Microsoft SQL Server のバージョンに関する、重要な基礎テクノロジのサポート終了日について十分に理解しておいてください。 詳細については、「 [固定ライフサイクルポリシー](https://support.microsoft.com/help/14085)」を参照してください。

## <a name="plan-ahead"></a>事前に計画する

[製品ライフサイクルサイト](https://support.microsoft.com/lifecycle/search?alpha=SharePoint%20Server%202010)で、が終了する日付を確認します。 これらの日付を考慮して、アップグレードまたは移行を計画します。 ご使用の製品は、表示されている日付になっても機能しなく *なり* ます。 しかし、インストールにはその日の後にパッチが適用されなくなるため、製品の次のバージョンへのスムーズな移行を計画する必要があります。

この行列は、移行オプション間でのコースのプロットに役に立ちます。

|サポート終了製品|中 |高|
|---|---|---|
|SharePoint Server 2010|SharePoint Server 2013 (社内)|SharePoint Online|
||Sharepoint Server 2013 と SharePoint Online のハイブリッド|SharePoint Server 2016 (社内)|
|||SharePoint クラウドハイブリッド検索|

スケールの下限 (良好) でオプションを選択する場合は、SharePoint Server 2010 から移行した後に、別のアップグレードの計画を開始する必要があります。

SharePoint Server 2010 のサポート終了を回避するために実行できる3つのパスを次に示します。

![SharePoint Server 2010 のアップグレードパス](../media/upgrade-from-sharepoint-2010/upgrade-from-sharepoint-2010-paths.png)

> [!NOTE]
> 現時点では、SharePoint Server 2010 および SharePoint Foundation 2010 のサポート終了は、2021年4月13日に予定されています。 ただし、最新の日付については [製品ライフサイクルサイト](https://support.microsoft.com/lifecycle) を必ず確認してください。

## <a name="whats-next"></a>次の手順

SharePoint Server 2013 と SharePoint Foundation 2013 は、オンプレミスのサーバーにインストールすることができます。 または、Microsoft 365 の一部であるオンラインサービスである SharePoint Online を使用することもできます。 次のいずれかを選択できます。

- SharePoint Online に移行します。

- オンプレミスの SharePoint Server または SharePoint Foundation をアップグレードします。

- 上記の両方を実行します。

- [SharePoint ハイブリッド](https://docs.microsoft.com/sharepoint/hybrid/hybrid)ソリューションを実装します。

カスタマイズの管理や移行、ハードウェアのアップグレードなど、サーバーファームを維持するための非表示のコストを考慮します。 これらの要因を考慮した場合、オンプレミスでのアップグレードが容易になります。 カスタマイズしていない従来の SharePoint サーバー上でファームを実行すると、SharePoint Online への計画された移行の恩恵を受けることができます。 オンプレミスの SharePoint Server 環境では、SharePoint Online でデータを移動して、ハードウェア管理のオーバーヘッドを軽減することもできます。

> [!NOTE]
> SharePoint 管理者は、Microsoft 365 サブスクリプションを作成し、新しい SharePoint Online サイトをセットアップした後、SharePoint Server 2010 をクリーンな状態にした後、重要なドキュメントのみを新しいサイトに持ち込むことができます。 その後、残りのデータを SharePoint Server 2010 サイトからオンプレミスのアーカイブにドレインできます。

|SharePoint Online|オンプレミスの SharePoint Server|
|---|---|
|時間のかかる (計画/実行/検証)|時間のかかる (計画/実行/検証)|
|資金コストが安い (ハードウェアの購入の必要なし)|ファンドのコストが高くなる (ハードウェアの購入)|
|一度の移行でのコスト|将来繰り返される一度の移行でのコスト|
|所有権/保守費用の低い総コスト|所有権/保守のコストの高い総コスト|

Microsoft 365 への1回の移行では、データを整理し、クラウドへの対応を決定する際に、より多くのコストが発生します。 しかし、データを移行した後は、ハードウェアおよびソフトウェアの更新プログラムを管理する必要がなくなるので、今後のアップグレードは自動的に実行されます。 また、ファームの稼働時間は、 [Microsoft サービスレベル契約 (SLA)](https://go.microsoft.com/fwlink/?linkid=843153)によって支えられます。

### <a name="migrate-to-sharepoint-online"></a>SharePoint Online への移行

SharePoint Online が必要なすべての機能を提供していることを確認します。 「 [SharePoint サービスの説明](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-service-description)」を参照してください。

Sharepoint Server 2010 (または SharePoint Foundation 2010) から SharePoint Online に直接移行することはできません。 移行作業の多くは手動で行います。 しかし、この段階では、移行前に不要になったデータとサイトを排除する機会が提供されます。 他のデータをストレージにアーカイブすることができます。 

SharePoint Server 2010 と SharePoint Foundation 2010 は、サポート終了時に機能しなくなりますことに注意してください。 そのため、ユーザーがデータの移動を忘れることがないように、管理者は SharePoint を実行している期間を持つことができます。

Sharepoint Server 2013 または SharePoint Server 2016 にアップグレードし、データを SharePoint Online に格納する場合は、 [Sharepoint 移行 API](https://support.office.com/article/Upload-on-premises-content-to-SharePoint-Online-using-PowerShell-cmdlets-555049c6-15ef-45a6-9a1f-a1ef673b867c?ui=en-US&amp;rs=en-US&amp;ad=US) を使用して情報を OneDrive for business に移行することができます。

|SharePoint Online の利点|SharePoint Online の短所|
|---|---|
|Microsoft が SPO ハードウェアおよびすべてのハードウェアの管理を行う。|利用可能な機能は、オンプレミスの SharePoint Server と SPO で異なる場合があります。|
|サブスクリプションの全体管理者であり、管理者を SPO サイトに割り当てることができます。|SharePoint Server オンプレミスのファーム管理者が使用できる一部のアクションは、Microsoft 365 の SharePoint 管理者の役割に存在しないか、または必要ありません。 ただし、SharePoint 管理、サイトコレクションの管理、およびサイトの所有権は、組織にとってローカルなものです。|
|Microsoft は、SharePoint Online が実行されている SQL サーバーを含む、基礎となるハードウェアおよびソフトウェアにパッチ、修正、および更新プログラムを適用します。|サービスの基礎となるファイルシステムへのアクセス権がないため、カスタマイズは制限されています。|
|Microsoft は [サービスレベル契約](https://go.microsoft.com/fwlink/?linkid=843153) を公開し、サービスレベルのインシデントを解決するために迅速に移行します。|バックアップと復元、その他の回復オプションは、SharePoint Online のサービスによって自動化されます。 使用されていない場合、バックアップは上書きされます。|
|セキュリティテストとサーバーのパフォーマンスチューニングは、Microsoft によって継続的にサービスで実行されます。|ユーザー インターフェイスとその他の SharePoint 機能の変更はサービスによってインストールされ、オン/オフの切り替えが必要な場合がある。|
|Microsoft 365 は、さまざまな業界標準を満たしています。 [microsoft コンプライアンスサービス](https://go.microsoft.com/fwlink/?linkid=843165)。|移行の際に [FastTrack](https://go.microsoft.com/fwlink/?linkid=518597) でできることが限られる。  <br/> アップグレードの多くは手動で行うか、 [SharePoint Online および OneDrive 移行コンテンツロードマップ](https://go.microsoft.com/fwlink/?linkid=843184)に記載されている SPO migration API を使用して行います。|
|Microsoft サポートエンジニアおよびデータセンターの従業員は、サブスクリプションに対する無制限の管理者アクセス権を持ちません。|新しいバージョンの SharePoint をサポートするようにハードウェアインフラストラクチャをアップグレードする必要がある場合や、アップグレードにセカンダリファームが必要な場合は、追加のコストがかかることがあります。|
|ソリューションプロバイダーは、データを SharePoint Online に移行するワンタイムジョブに役立ちます。|SharePoint Online のすべての変更がコントロール内にあるわけではありません。 移行後、メニュー、ライブラリ、およびその他の機能の設計の違いが、一時的に利便性に影響する場合があります。|
|オンライン製品は、サービスを通じて自動的に更新されます。 機能は廃止されることがありますが、サポートの終了のサイクルが実際にはありません。|SharePoint Server または SharePoint Foundation および基盤となる SQL server には、サポート終了のライフサイクルが用意されています。|

新しい Microsoft 365 サイトを作成し、必要に応じてそのサイトに手動でデータを移行する場合は、 [microsoft 365 のオプション](https://www.microsoft.com/microsoft-365/)を確認してください。

### <a name="upgrade-sharepoint-server-on-premises"></a>オンプレミスの SharePoint Server のアップグレード

SharePoint Server 2019 の場合、アップグレードは  *シリアル* に移動する必要があります。 SharePoint Server 2010 から SharePoint Server 2016 または SharePoint 2019 に直接アップグレードする方法はありません。 シリアルアップグレードのパス:

- Sharepoint server 2010 sharepoint server \> 2013 \> sharepoint server 2016

SharePoint 2010 から SharePoint Server 2016 へのパス全体を追跡するための時間と計画が必要になります。 アップグレードには、ハードウェアのコスト (SQL サーバーもアップグレードする必要があります)、ソフトウェア、および管理が含まれます。 また、カスタマイズをアップグレードしたり、破棄したりする必要がある場合もあります。 SharePoint Server ファームをアップグレードする前に、必ず重要なカスタマイズをドキュメント化してください。

> [!NOTE]
> サポート終了時の SharePoint 2010 ファームを維持し、新しいハードウェアに SharePoint Server 2016 ファームをインストールする (個別のファームを並行して実行する) ことができます。その後、コンテンツをダウンロードして再アップロードするために、コンテンツの手動の移行を計画して実行することができます (例:)。 しかし、2010からのドキュメントなど、手動による移動を実行するアカウントのエイリアスを使用して、現在の最終変更のアカウントを持っているなど、手動による移動には、次のような落とし穴が発生する可能性があります。 また、サイト、サブサイト、アクセス許可、リスト構造の再作成など、いくつかの作業を事前に行う必要があります。 アップグレードの前に、必ず環境をクリーンにしてください。 ストレージに移動できるデータや不要なデータを検討します。 これにより、移行の影響が軽減されます。 アップグレード前に既存のファームが機能していること、および使用を停止する前に (確かに) あることを確認してください。

以下の、*サポートされるアップグレード パスとサポート外のアップグレード パス* を確認してください。

- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843156)

- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843157)

*カスタマイズ* を行っている場合は、移行パスの各手順を計画することが重要です。

- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843160)

- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843162)

|オンプレミスの利点|オンプレミスの欠点|
|---|---|
|サーバーハードウェア上の SharePoint ファーム (およびその SQL) のすべての側面を完全に制御します。|すべてのブレークと修正は会社の責任です。 ただし、製品のサポートが終了していない場合は、有料の Microsoft サポートに連絡することができます。|
|ハイブリッドの SharePoint Online サブスクリプションにオンプレミス ファームを接続するオプションを備えた、オンプレミスの SharePoint Server のフル機能一式。|アップグレード、パッチ、セキュリティ修正、ハードウェアのアップグレード、および SharePoint Server とその SQL ファームのすべてのメンテナンスは、オンプレミスで管理されます。|
|SharePoint Online よりも詳細なカスタマイズオプションへのフルアクセス。|[Microsoft コンプライアンスサービス](https://go.microsoft.com/fwlink/?linkid=843165) は、オンプレミスで手動で構成する必要があります。|
|セキュリティテストとサーバーのパフォーマンスチューニングは、お客様の管理下にあります。|Microsoft 365 では、オンプレミスの SharePoint Server と相互運用できない SharePoint Online の機能を使用することができます。|
|ソリューションプロバイダーは、SharePoint Server の次のバージョン (および以降) にデータを移行するのに役立ちます。|SharePoint Server サイトでは、SharePoint Online で表示される [SSL/TLS](https://go.microsoft.com/fwlink/?linkid=843167) 証明書が自動的に使用されることはない。|
|オンプレミスの SharePoint Server での名前付け規則、バックアップと復元、その他の回復オプションを完全に制御します。|製品のライフサイクルによって、オンプレミスの SharePoint Server の機能が異なる。|

### <a name="upgrade-resources"></a>リソースをアップグレードする

最初に、ハードウェア要件とソフトウェア要件を比較します。 現在の環境が基本要件を満たしていない場合は、まずファームまたは SQL サーバーのハードウェアをアップグレードする必要があります。 

一部のサイトを SharePoint Online の "永続" ハードウェアに移動することを決定する場合があります。 評価が済んだら、サポートされているアップグレードパスと方法に従います。

- *ハードウェア/ソフトウェア要件:*

    [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843204)  | [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843206)  | [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843207)

- *ソフトウェアの境界と制限:*

    [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843247)  | [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843248)  | [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843249)

- *アップグレードプロセスの概要は次のとおりです。*

    [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843251)  | [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843252)  | [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843359)

### <a name="create-a-hybrid-solution-with-sharepoint-online-and-sharepoint-server-on-premises"></a>SharePoint Online とオンプレミスの SharePoint Server を使用してハイブリッドソリューションを作成する

ハイブリッドセットアップは、一部の移行ニーズに対して、オンプレミスとオンラインの両方の最良の機能を提供します。 Sharepoint Server 2013、2016、または2019ファームを SharePoint Online に接続して、sharepoint ハイブリッドを作成することができます。詳細については、「 [sharepoint ハイブリッドソリューションについて](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx)」を参照してください。

ハイブリッド SharePoint Server ファームが移行目標の場合は、オンラインで移行するサイトとユーザー、およびオンプレミスを維持する必要があるサイトとユーザーを図に示します。 SharePoint Server ファームのコンテンツを、会社への高、中、または低レベルの影響としてランク付けすることで、この決定に役立てることができます。 SharePoint Online では、ログインのユーザーアカウントと SharePoint Server 検索インデックスのみを共有する必要があります。 ただし、サイトの使用方法を確認するまで、この要素は明確ではありません。 後で会社がすべてのコンテンツを SharePoint Online に移行することを決定した場合は、残りのすべてのアカウントとデータをオンラインにして、オンプレミスのファームを使用停止にすることができます。 SharePoint ファームの管理/管理は、その時点から Microsoft 365 コンソールを通じて行われます。

ハイブリッドの既存の種類と、オンプレミスの SharePoint ファームと Microsoft 365 サブスクリプションとの間の接続を構成する方法について理解しておいてください。

|オプション|説明|
|---|---|
|[Microsoft コンプライアンスサービス](https://go.microsoft.com/fwlink/?linkid=843165)。|移行の際に [FastTrack](https://www.microsoft.com/fasttrack/microsoft-365) でできることが限られる。<br/><br/> アップグレードの多くは手動で行うか、 [SharePoint Online および OneDrive 移行コンテンツロードマップ](https://go.microsoft.com/fwlink/?linkid=843184)に記載されている SPO migration API を使用して行います。|
|Microsoft サポートエンジニアおよびデータセンターの従業員は、サブスクリプションに対する無制限の管理者アクセス権を持ちません。|新しいバージョンの SharePoint をサポートするためにハードウェアインフラストラクチャをアップグレードする必要がある場合や、セカンダリファームが必要な場合は、追加のコストがかかることがあります。|
|パートナーが、SharePoint Online へのデータの移行を一度で行えるようにサポートできる。||
|オンライン製品は、サービスを通じて自動的に更新されます。 機能は廃止されることがありますが、サポートの終了が実際にはありません。||

新しい Microsoft 365 サイトを作成し、必要に応じてデータを手動で移行する場合は、 [microsoft 365 のオプション](https://www.microsoft.com/microsoft-365/)を確認してください。

### <a name="upgrade-sharepoint-server-on-premises"></a>オンプレミスの SharePoint Server のアップグレード

SharePoint のアップグレードでバージョンをスキップする方法はありません。 これは、アップグレードが直列に進むことを意味します。

- Sharepoint 2007 \> sharepoint server 2010 \> sharepoint server 2013 \> sharepoint server 2016

SharePoint 2007 から SharePoint Server 2016 へのパス全体を取得するために、時間の大幅な投資が行われ、ハードウェア (SQL server をアップグレードする必要があります)、ソフトウェア、および管理コストが関係することを意味します。 機能の重要度に応じて、カスタマイズをアップグレードまたは破棄する必要があります。

> [!NOTE]
> ライフサイクル終了時の SharePoint 2007 ファームを維持し、新しいハードウェアに SharePoint Server 2016 ファームをインストールする (個別のファームを並行して実行する) ことができます。その後、コンテンツをダウンロードして再アップロードするために、コンテンツの手動の移行を計画して実行することができます (例:)。 しかし、このような手動移動にはいくつかの欠点があります。これは、最後に変更されたアカウントを、手動移動を行うアカウントのエイリアスで置換したドキュメントの移動などです。 また、サイト、サブサイト、アクセス許可、リスト構造の再作成など、多くの作業を事前に行う必要があります。 いずれの場合も、ストレージに移動できるデータや、移行の影響を軽減する必要がなくなったデータについて検討します。

アップグレードの前に環境をクリーンな状態にしておきます。 アップグレード前に既存のファームが機能していること、および使用を停止する前に必ず確認してください。

以下の、*サポートされるアップグレード パスとサポート外のアップグレード パス* を確認してください。

- [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843156)

- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843156)

- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843157)

*カスタマイズ* を行っている場合は、移行パスの手順ごとにアップグレードを計画することが重要です。

- [SharePoint 2007](https://go.microsoft.com/fwlink/?linkid=843158)

- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843160)

- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843162)

|オンプレミスの pro|オンプレミスの con|
|---|---|
|サーバー ハードウェアからの、SharePoint ファームの機能すべての完全なコントロール。|すべてのブレークと修正は会社の責任です。 (ただし、製品のサポートが終了していない場合は、有料の Microsoft サポートを受けてください)。|
|ハイブリッドの SharePoint Online サブスクリプションにオンプレミス ファームを接続するオプションを備えた、オンプレミスの SharePoint Server のフル機能一式。|オンプレミスに管理される SharePoint Server のアップグレード、パッチ、セキュリティ修正プログラム、およびすべての保守。|
|高度なカスタマイズのためのフル アクセス許可。|[Microsoft コンプライアンスサービス](https://go.microsoft.com/fwlink/?linkid=843165) は、オンプレミスで手動で構成する必要があります。|
|セキュリティテストとサーバーのパフォーマンスチューニングは、お客様の管理下にあります。|Microsoft 365 は、オンプレミスの SharePoint Server と相互運用できない SharePoint Online の機能を提供する場合があります。|
|パートナーは、SharePoint Server の次のバージョン (および以降) にデータを移行するのに役立ちます。|SharePoint Server サイトでは、SharePoint Online で表示される [SSL/TLS](https://go.microsoft.com/fwlink/?linkid=843167) 証明書が自動的に使用されることはない。|
|オンプレミスの SharePoint Server での名前付け規則、バックアップと復元、その他の回復オプションを完全に制御します。|製品のライフサイクルによって、オンプレミスの SharePoint Server の機能が異なる。|

### <a name="upgrade-resources"></a>リソースをアップグレードする

ハードウェアとソフトウェアの要件を満たしていることを確認してから、サポートされているアップグレード方法に従って操作を行ってください。

- *ハードウェア/ソフトウェア要件*:

    [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843204) | [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843204) | [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843206) | [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843207)

- *ソフトウェアの境界と制限*:

    [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843245) | [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843247) | [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843248) | [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843249)

- *アップグレード プロセスの概要*:

    [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843250) | [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843251) | [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843252) | [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843359)

### <a name="create-a-sharepoint-hybrid-solution-between-sharepoint-online-and-on-premises"></a>SharePoint Online とオンプレミスの間で、SharePoint ハイブリッド ソリューションを作成する

移行のニーズに対する回答が、SharePoint Online によって提供されるコントロールと SharePoint Online が提供する所有権の低コストの間にある場合は、SharePoint Server 2013 または2016ファームをハイブリッドを介して SharePoint Online に接続できます。 [SharePoint ハイブリッドソリューションについて](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx)

ハイブリッド SharePoint Server ファームにメリットがあると判断した場合は、ハイブリッドの既存の種類と、オンプレミスの SharePoint ファームと Microsoft 365 サブスクリプションとの間の接続を構成する方法について理解しておく必要があります。

[テストラボガイド](m365-enterprise-test-lab-guides.md)を使用してセットアップできる、Microsoft 365 開発/テスト環境を作成することもできます。 試用版または購入済みの Microsoft 365 サブスクリプションを取得した後、SharePoint Online にサイトコレクション、web、およびドキュメントライブラリを作成して、そこにデータを移行することができます。 移行 API を使用するか、またはハイブリッドウィザードを使用して、個人用サイトのコンテンツを OneDrive for Business に移行する場合は、手動で移行することができます。

> [!NOTE]
> ハイブリッドオプションを使用するには、SharePoint Server 2010 ファームを、オンプレミスから SharePoint Server 2013 または2016にアップグレードする必要があります。 Sharepoint Foundation 2010 および SharePoint Foundation 2013 は、SharePoint Online とのハイブリッド接続をサポートしていません。

## <a name="summary-of-options-for-office-2010-client-and-servers-and-windows-7"></a>Office 2010 のクライアントおよびサーバーおよび Windows 7 のオプションの概要

Office 2010 サーバー/クライアント、および Windows 7のアップグレード、移行、およびクラウドへの移行オプションを視覚的にまとめた概要は、[サポート終了ポスター](../downloads/Office2010Windows7EndOfSupport.pdf) をご覧ください。

[![Office 2010 のクライアントおよびサーバーおよび Windows 7 ポスターのサポート終了](../media/upgrade-from-office-2010-servers-and-products/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)

このポスターは、Microsoft 365 Enterprise で推奨パスとオプションが強調表示されている場合に、Office 2010 のクライアントおよびサーバー製品と Windows 7 のサポート終了を回避するために取ることができるさまざまなパスを示しています。

このポスターを [ダウンロード](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Office2010Windows7EndOfSupport.pdf) して、レター、リーガル、またはタブロイド (11 x 17) 形式で印刷することもできます。

## <a name="related-articles"></a>関連記事

[Office 2007 または2010サーバーおよびクライアントからのアップグレードに役立つリソース](upgrade-from-office-2010-servers-and-products.md)

[Overview of the upgrade process from SharePoint 2010 to SharePoint 2013](https://technet.microsoft.com/library/mt493301%28v=office.16%29.aspx)

[SharePoint 2010 から SharePoint 2013 へのアップグレードのベスト プラクティス](https://technet.microsoft.com/library/mt493305%28v=office.16%29.aspx)

[SharePoint 2013 でのデータベース アップグレードの問題のトラブルシューティング](https://go.microsoft.com/fwlink/?linkid=843195)

[Microsoft ソリューションプロバイダーを検索してアップグレードに役立てる](https://go.microsoft.com/fwlink/?linkid=841249)

[更新された SharePoint 2013 製品サービス ポリシー](https://technet.microsoft.com/library/mt493253%28v=office.16%29.aspx)

[更新された SharePoint Server 2016 製品サービス ポリシー](https://technet.microsoft.com/library/mt782882%28v=office.16%29.aspx)
