---
title: SharePoint 2010 からのアップグレード
ms.author: tracyp
author: MSFTTracyP
manager: scotv
ms.date: 04/13/2020
audience: ITPro
ms.topic: conceptual
ms.prod: office-online-server
ms.localizationpriority: medium
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
description: SharePoint 2010 および SharePoint Server 2010 からアップグレードする情報とリソースを確認します。 2021 年 4 月 13 日の両方のサポート。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: be25dd1260c378146d292e6487329065a3020ac8
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65077402"
---
# <a name="upgrading-from-sharepoint-2010"></a>SharePoint 2010 からのアップグレード

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

Microsoft SharePoint 2010 および SharePoint Server 2010 は **、2021 年 4 月 13** 日にサポートを終了します。 この記事では、既存のSharePoint Server 2010 データをMicrosoft 365で SharePoint Online に移行したり、オンプレミスの SharePoint Server 2010 環境をアップグレードしたりするのに役立つリソースを提供します。

## <a name="what-is-end-of-support"></a>*サポートの終了* とは何ですか?

ほとんどの Microsoft 製品にはサポート ライフサイクルがあり、その間に新機能、バグ修正、セキュリティ修正などが行われます。 サポート終了日を経過しても、製品の動作は停止しませんが、Microsoft では次のものが提供されなくなります。

- 発生する可能性がある問題のテクニカル サポート。

- サーバーの安定性と使いやすさに影響を与える可能性がある問題に関するバグ修正。

- サーバーがセキュリティ違反に対して脆弱になる可能性がある脆弱性に対するセキュリティ修正。

- タイム ゾーンの更新。

つまり、製品の更新プログラム、パッチ、修正プログラム (セキュリティ パッチや修正プログラムを含む) は今後ありません。 Microsoft サポートは、サポート作業をより新しいバージョンに完全に移行する予定です。

SharePoint Server 2010 アプローチのサポートが終了したら、製品をアップグレードして重要なデータを移行する前に不要になったデータを削除します。

> [!NOTE]
> ソフトウェア ライフサイクルは通常、最初のリリースから 10 年間続きます。 [Microsoft ソリューション プロバイダーは、ソフトウェアの](https://go.microsoft.com/fwlink/?linkid=841249)次のバージョンにアップグレードしたり、Microsoft 365移行 (またはその両方) に移行したりするのに役立ちます。 特にSharePointで使用しているMicrosoft SQL Serverのバージョンについては、重要な基盤となるテクノロジのサポート終了日を確認してください。 詳細については、「 [固定ライフサイクル ポリシー」を](https://support.microsoft.com/help/14085)参照してください。

## <a name="plan-ahead"></a>事前に計画する

[製品ライフサイクル サイト](https://support.microsoft.com/lifecycle/search?alpha=SharePoint%20Server%202010)でサポートが終了する日付を確認します。 これらの日付を念頭に置いて、アップグレードまたは移行を計画します。 製品が一覧に表示された日付に *動作を停止することはないことを忘れないでください* 。 ただし、インストールはその日以降修正プログラムが適用されなくなるので、次のバージョンの製品へのスムーズな移行を計画する必要があります。

このマトリックスは、移行オプション間でコースをプロットするのに役立ちます。

|サポート製品の終了|中 |高|
|---|---|---|
|SharePoint Server 2010|SharePoint Server 2013 (オンプレミス)|SharePoint Online|
||SharePoint Online を使用したSharePoint Server 2013 ハイブリッド|SharePoint Server 2016 (オンプレミス)|
|||クラウド ハイブリッド検索のSharePoint|

スケールの下限 (良好) でオプションを選択した場合は、SharePoint Server 2010 からの移行後すぐに別のアップグレードの計画を開始する必要があります。

SharePoint Server 2010 のサポートが終了しないようにするために使用できる 3 つのパスを次に示します。

![SharePoint Server 2010 アップグレード パス。](../media/upgrade-from-sharepoint-2010/upgrade-from-sharepoint-2010-paths.png)

> [!NOTE]
> SharePoint Server 2010 および SharePoint Foundation 2010 のサポートは、現在 2021 年 4 月 13 日に予定されています。 ただし、 [製品ライフサイクル サイト](https://support.microsoft.com/lifecycle) で最新の日付を確認してください。

## <a name="whats-next"></a>次の手順

SharePoint Server 2013 および SharePoint Foundation 2013 は、オンプレミスのサーバーにインストールできます。 または、Microsoft 365の一部であるオンライン サービスであるSharePoint Online を使用することもできます。 以下から選択できます。

- SharePoint Online に移行します。

- オンプレミスSharePointサーバーまたはSharePoint Foundation をアップグレードします。

- 上記の両方を実行します。

- [SharePointハイブリッド](/sharepoint/hybrid/hybrid) ソリューションを実装します。

カスタマイズの保守や移行、ハードウェアのアップグレードなど、サーバー ファームを維持する際の隠れたコストを考慮してください。 これらの要因を考慮した場合は、オンプレミスのアップグレードが簡単になります。 大規模なカスタマイズなしでレガシ SharePoint サーバーでファームを実行する場合は、SharePoint Online への計画的な移行の恩恵を受けることができます。 オンプレミスのSharePoint サーバー環境の場合は、ハードウェア管理のオーバーヘッドを減らすために、SharePoint Online で一部のデータを移動することを検討することもできます。

> [!NOTE]
> SharePoint管理者は、Microsoft 365 サブスクリプションを作成し、新しいSharePoint Online サイトを設定し、SharePoint Server 2010 からクリーンに切り離して、重要なドキュメントのみを新しいサイトに取り込むことができます。 その後、残りのデータは、SharePoint Server 2010 サイトからオンプレミス アーカイブにドレインできます。

|SharePoint Online|オンプレミスの SharePoint Server|
|---|---|
|高コストの時間 (プラン/実行/検証)|高コストの時間 (プラン/実行/検証)|
|資金コストが安い (ハードウェアの購入の必要なし)|より高いコスト (ハードウェア購入)|
|一度の移行でのコスト|将来繰り返される一度の移行でのコスト|
|所有権/メンテナンスの合計コストが低い|高い総保有コスト/メンテナンスコスト|

Microsoft 365への 1 回限りの移行では、データを整理し、クラウドに何を取り、何を残すのかを決定するときに、コストが高くなります。 ただし、データが移行された後は、ハードウェアとソフトウェアの更新プログラムを管理する必要がなくなったので、今後のアップグレードは自動的に行われます。 また、ファームの稼働時間は [、Microsoft サービス レベル アグリーメント (SLA)](/office365/servicedescriptions/office-365-platform-service-description/service-level-agreement) によってサポートされます。

### <a name="migrate-to-sharepoint-online"></a>SharePoint Online への移行

オンラインSharePoint必要なすべての機能が提供されていることを確認します。 [サービスの説明SharePoint](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-service-description)参照してください。

SharePoint Server 2010 (または SharePoint Foundation 2010) から SharePoint Online に直接移行することはできません。 移行作業の多くは手動です。 ただし、このステージでは、移動前に不要になったデータとサイトを排除する機会を提供します。 他のデータをストレージにアーカイブできます。 

SharePoint Server 2010 および SharePoint Foundation 2010 では、サポートが終了しても作業が停止されないことに注意してください。 そのため、管理者は、顧客がデータの一部を移動し忘れた場合に、SharePointがまだ実行されている期間を設定できます。

SharePoint Server 2013 または SharePoint Server 2016 にアップグレードし、SharePoint Online にデータを配置する場合は、[SharePoint移行 API を](https://support.office.com/article/Upload-on-premises-content-to-SharePoint-Online-using-PowerShell-cmdlets-555049c6-15ef-45a6-9a1f-a1ef673b867c?ui=en-US&amp;rs=en-US&amp;ad=US)使用して情報をOneDrive for Businessに移行できます。

|SharePoint Online の利点|SharePoint Online の欠点|
|---|---|
|Microsoft が SPO ハードウェアおよびすべてのハードウェアの管理を行う。|使用可能な機能は、SharePoint Server オンプレミスと SPO で異なる場合があります。|
|サブスクリプションの Sharepoint 管理者またはグローバル管理者であり、SPO サイトに管理者を割り当てることができます。|SharePoint Server オンプレミスのファーム管理者が使用できる一部のアクションは、Microsoft 365のSharePoint管理者ロールに存在しない (または必要ありません)。 ただし、SharePoint管理、サイト コレクション管理、サイト所有権は組織に対してローカルです。|
|Microsoft は、SharePoint Online が実行されているSQL サーバーを含む、基になるハードウェアとソフトウェアにパッチ、修正プログラム、更新プログラムを適用します。|サービス内の基になるファイル システムにアクセスできないため、カスタマイズは制限されます。|
|Microsoft は [サービス レベル アグリーメント](/office365/servicedescriptions/office-365-platform-service-description/service-level-agreement) を発行し、サービス レベルのインシデントを迅速に解決します。|バックアップと復元などの復旧オプションは、SharePoint Online のサービスによって自動化されます。 バックアップは、使用しない場合は上書きされます。|
|セキュリティ テストとサーバー パフォーマンスチューニングは、Microsoft によってサービス内で継続的に実行されます。|ユーザー インターフェイスとその他の SharePoint 機能の変更はサービスによってインストールされ、オン/オフの切り替えが必要な場合がある。|
|Microsoft 365は、[Microsoft コンプライアンス オファリング](/compliance/regulatory/offering-home)という多くの業界標準を満たしています。|移行の際に [FastTrack](https://go.microsoft.com/fwlink/?linkid=518597) でできることが限られる。  <br/> アップグレードの多くは、手動で行うか、SharePoint [Online および OneDrive 移行コンテンツ ロードマップ](/sharepointmigration/upload-on-premises-content-to-sharepoint-online-using-powershell-cmdlets)で説明されている SPO 移行 API を使用します。|
|Microsoft サポート エンジニアとデータセンターの従業員は、サブスクリプションへの無制限の管理者アクセス権を持っていません。|新しいバージョンのSharePointをサポートするためにハードウェア インフラストラクチャをアップグレードする必要がある場合や、アップグレードにセカンダリ ファームが必要な場合は、追加のコストが発生する可能性があります。|
|ソリューション プロバイダーは、データを SharePoint Online に移行する 1 回限りのジョブに役立ちます。|SharePoint Online に対するすべての変更がコントロール内にあるわけではありません。 移行後、メニュー、ライブラリ、およびその他の機能の設計の違いが一時的に使いやすさに影響を与える可能性があります。|
|オンライン製品は、サービス全体で自動的に更新されます。 機能は非推奨になる可能性がありますが、サポート ライフサイクルの真の終わりはありません。|SharePoint Server または SharePoint Foundation および基になるSQL サーバーには、サポート終了ライフサイクルがあります。|

新しいMicrosoft 365 サイトを作成することに決め、必要に応じてデータを手動で移行する場合は、[Microsoft 365 オプション](https://www.microsoft.com/microsoft-365/)を確認します。

### <a name="upgrade-sharepoint-server-on-premises"></a>オンプレミスの SharePoint Server のアップグレード

SharePoint Server 2019の時点で、アップグレードは *連続して* 行う必要があります。 SharePoint Server 2010 から SharePoint Server 2016 にアップグレードしたり、2019 を直接SharePointしたりすることはできません。 シリアル アップグレード パス:

- SharePoint Server 2010 \> SharePoint Server 2013 \> SharePoint Server 2016

SharePoint 2010 から SharePoint Server 2016 までのパス全体に従う予定です。 アップグレードには、ハードウェア (SQL サーバーもアップグレードする必要があります)、ソフトウェア、および管理のコストが伴います。 また、カスタマイズをアップグレードするか、破棄する必要がある場合もあります。 SharePoint Server ファームをアップグレードする前に、重要なカスタマイズを文書化してください。

> [!NOTE]
> サポート終了SharePoint 2010 ファームを維持し、新しいハードウェアに SharePoint Server 2016 ファームをインストールし (別のファームが並んで実行されるように)、コンテンツの手動移行を計画して実行できます (コンテンツのダウンロードや再アップロードなど)。 ただし、手動移動を行うアカウントのエイリアスを持つ現在の最終変更アカウントを持つ 2010 年からのドキュメントなど、これらの手動移動には潜在的な落とし穴があります。 また、サイト、サブサイト、アクセス許可、リスト構造の再作成など、事前に作業を行う必要があります。 アップグレードする前に、必ず環境をクリーンアップしてください。 ストレージに移動できるデータや不要になったデータを検討してください。 これにより、移行の影響を軽減できます。 アップグレードする前に既存のファームが機能していることを確認し、使用停止にする前に (確かに) 機能していることを確認してください。

以下の、*サポートされるアップグレード パスとサポート外のアップグレード パス* を確認してください。

- [SharePoint Server 2010](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262747(v=office.12))

- [SharePoint Server 2013](/SharePoint/upgrade-and-update/review-supported-editions-and-products-for-upgrading-to-sharepoint-2013)

*カスタマイズ* がある場合は、移行パスの各手順を計画することが重要です。

- [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc263203(v=office.14))

- [SharePoint Server 2013](/SharePoint/upgrade-and-update/create-a-communication-plan-for-the-upgrade-to-sharepoint-2013)

|オンプレミスの利点|オンプレミスの欠点|
|---|---|
|サーバー ハードウェアから、SharePoint ファーム (およびそのSQL) のすべての側面を完全に制御します。|すべての中断と修正は、会社の責任です。 ただし、製品がサポート終了を過ぎていない場合は、有料Microsoft サポートを利用できます。|
|ハイブリッドの SharePoint Online サブスクリプションにオンプレミス ファームを接続するオプションを備えた、オンプレミスの SharePoint Server のフル機能一式。|アップグレード、パッチ、セキュリティ修正プログラム、ハードウェア アップグレード、およびSharePoint Server とそのSQL ファームのすべてのメンテナンスは、オンプレミスで管理されます。|
|SharePoint Online よりも高いカスタマイズ オプションを実現するフル アクセス。|[Microsoft コンプライアンス オファリングは](/compliance/regulatory/offering-home) 、オンプレミスで手動で構成する必要があります。|
|セキュリティ テストとサーバー パフォーマンスのチューニングは、お客様の制御下でオンプレミスで実行されます。|Microsoft 365では、オンプレミスのSharePoint サーバーと相互運用できない機能をSharePoint Online で使用できる場合があります。|
|ソリューション プロバイダーは、データを次のバージョンの SharePoint Server (以降) に移行するのに役立ちます。|SharePoint Server サイトでは、SharePoint Online で表示される [SSL/TLS](/SharePoint/security-for-sharepoint-server/enable-tls-1-1-and-tls-1-2-support-in-sharepoint-server-2016) 証明書が自動的に使用されることはない。|
|SharePoint Server オンプレミスの名前付け規則、バックアップと復元、その他の復旧オプションを完全に制御します。|製品のライフサイクルによって、オンプレミスの SharePoint Server の機能が異なる。|

### <a name="upgrade-resources"></a>リソースをアップグレードする

まず、ハードウェアとソフトウェアの要件を比較します。 現在の環境が基本的な要件を満たしていない場合は、最初にファームまたはSQL サーバーのハードウェアをアップグレードする必要があります。 

サイトの一部を、SharePoint Online の "エバーグリーン" ハードウェアに移動することもできます。 評価を行ったら、サポートされているアップグレード パスと方法に従います。

- *ハードウェア/ソフトウェアの要件:*

    [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262485(v=office.14)) |  [SharePoint Server 2013](/SharePoint/install/hardware-and-software-requirements-0) |  [SharePoint Server 2016](/SharePoint/install/hardware-and-software-requirements)

- *ソフトウェアの境界と制限:*

    [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262787(v=office.14)) |  [SharePoint Server 2013](/SharePoint/install/software-boundaries-and-limits) |  [SharePoint Server 2016](/SharePoint/install/software-boundaries-and-limits-0)

- *次のアップグレード プロセスの概要:*

    [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc303420(v=office.14)) |  [SharePoint Server 2013](/SharePoint/upgrade-and-update/upgrade-to-sharepoint-server-2016) |  [SharePoint Server 2016](/SharePoint/upgrade-and-update/upgrade-to-sharepoint-server-2016)

### <a name="create-a-hybrid-solution-with-sharepoint-online-and-sharepoint-server-on-premises"></a>SharePoint Online と SharePoint Server をオンプレミスで使用してハイブリッド ソリューションを作成する

ハイブリッドセットアップは、一部の移行ニーズに最適なオンプレミスとオンラインの両方を提供します。 SharePoint Server 2013、2016、または 2019 ファームを SharePoint Online に接続して、SharePoint ハイブリッドソリューションを作成できます。[ハイブリッド ソリューションのSharePointについて説明](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx)します。

ハイブリッド SharePoint サーバー ファームが移行の目標である場合は、オンラインに移行するサイトとユーザー、およびオンプレミスのままにする必要があるサイトとユーザーを把握します。 SharePoint サーバー ファーム のコンテンツを会社への影響が高い、中、または低いとしてランク付けすると、この決定に役立ちます。 ログイン用のユーザー アカウントとSharePoint サーバー検索インデックスを SharePoint Online と共有するだけで済む場合があります。 ただし、サイトの使用方法を確認するまで、この要因は明確でない場合があります。 会社が後ですべてのコンテンツを SharePoint Online に移行することを決定した場合は、残りのすべてのアカウントとデータをオンラインに移動し、オンプレミス ファームを使用停止することができます。 SharePoint ファームの管理/管理は、その時点からMicrosoft 365コンソールを使用して行われます。

既存の種類のハイブリッドと、オンプレミスのSharePoint ファームとMicrosoft 365 サブスクリプションの間の接続を構成する方法について理解してください。

|オプション|説明|
|---|---|
|[Microsoft コンプライアンス オファリング](/compliance/regulatory/offering-home)。|移行の際に [FastTrack](https://www.microsoft.com/fasttrack/microsoft-365) でできることが限られる。<br/><br/> アップグレードの多くは、手動で行うか、SharePoint [Online および OneDrive 移行コンテンツ ロードマップ](/sharepointmigration/upload-on-premises-content-to-sharepoint-online-using-powershell-cmdlets)で説明されている SPO 移行 API を使用します。|
|Microsoft サポート エンジニアとデータセンターの従業員は、サブスクリプションへの無制限の管理者アクセス権を持っていません。|新しいバージョンのSharePointをサポートするためにハードウェア インフラストラクチャをアップグレードする必要がある場合や、セカンダリ ファームが必要な場合は、追加のコストが発生する可能性があります。|
|パートナーが、SharePoint Online へのデータの移行を一度で行えるようにサポートできる。||
|オンライン製品は、サービス全体で自動的に更新されます。 機能は非推奨になる可能性がありますが、サポートの真の終わりはありません。||

新しいMicrosoft 365 サイトを作成し、必要に応じて手動でデータを移行することに決めた場合は、[Microsoft 365 オプション](https://www.microsoft.com/microsoft-365/)を確認します。

### <a name="upgrade-sharepoint-server-on-premises"></a>オンプレミスの SharePoint Server のアップグレード

SharePointアップグレードではバージョンをスキップする方法はありません。 つまり、アップグレードは連続して行われます。

- SharePoint 2007 \> SharePoint Server 2010 \> SharePoint Server 2013 \> SharePoint Server 2016

SharePoint 2007 から SharePoint Server 2016 へのパス全体を実行するには、時間の大幅な投資を意味し、ハードウェア (SQL サーバーもアップグレードする必要があります)、ソフトウェア、および管理コストが伴います。 カスタマイズは、機能の重要度に応じてアップグレードまたは破棄する必要があります。

> [!NOTE]
> 2007 ファームSharePointエンド オブ ライフを維持し、新しいハードウェアに SharePoint Server 2016 ファームをインストールし (別のファームが並んで実行されるように)、コンテンツの手動移行を計画して実行できます (コンテンツのダウンロードや再アップロードなど)。 ただし、最後に変更されたアカウントを手動で移動するアカウントのエイリアスに置き換えるドキュメントの移動など、これらの手動移動にはいくつかの欠点があります。 また、サイト、サブサイト、アクセス許可、リスト構造の再作成など、多くの作業を事前に行う必要があります。 いずれの場合も、ストレージに移動できるデータや、移行の影響を減らす必要がなくなったデータを検討してください。

アップグレードする前に、必ず環境をクリーンアップしてください。 アップグレードする前、および使用停止する前に、既存のファームが機能していることを確認してください。

以下の、*サポートされるアップグレード パスとサポート外のアップグレード パス* を確認してください。

- [SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262747(v=office.12))

- [SharePoint Server 2010](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262747(v=office.12))

- [SharePoint Server 2013](/SharePoint/upgrade-and-update/review-supported-editions-and-products-for-upgrading-to-sharepoint-2013)

*カスタマイズ* がある場合は、移行パスの各手順に対してアップグレードを計画することが重要です。

- [SharePoint 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc263203(v=office.12))

- [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc263203(v=office.14))

- [SharePoint Server 2013](/SharePoint/upgrade-and-update/create-a-communication-plan-for-the-upgrade-to-sharepoint-2013)

|オンプレミスのプロ|オンプレミスの con|
|---|---|
|サーバー ハードウェアからの、SharePoint ファームの機能すべての完全なコントロール。|すべての中断と修正は、会社の責任です。 (ただし、製品がサポート終了を過ぎていない場合は、有料Microsoft サポートに参加できます)。|
|ハイブリッドの SharePoint Online サブスクリプションにオンプレミス ファームを接続するオプションを備えた、オンプレミスの SharePoint Server のフル機能一式。|オンプレミスに管理される SharePoint Server のアップグレード、パッチ、セキュリティ修正プログラム、およびすべての保守。|
|高度なカスタマイズのためのフル アクセス許可。|[Microsoft コンプライアンス オファリングは](/compliance/regulatory/offering-home) 、オンプレミスで手動で構成する必要があります。|
|セキュリティ テストとサーバー パフォーマンスのチューニングは、お客様の制御下でオンプレミスで実行されます。|Microsoft 365では、オンプレミスの SharePoint Server と相互運用しない機能をSharePoint Online で使用できる場合があります。|
|パートナーは、データを次のバージョンの SharePoint Server (以降) に移行するのに役立ちます。|SharePoint Server サイトでは、SharePoint Online で表示される [SSL/TLS](/SharePoint/security-for-sharepoint-server/enable-tls-1-1-and-tls-1-2-support-in-sharepoint-server-2016) 証明書が自動的に使用されることはない。|
|SharePoint Server オンプレミスの名前付け規則、バックアップと復元、その他の復旧オプションを完全に制御します。|製品のライフサイクルによって、オンプレミスの SharePoint Server の機能が異なる。|

### <a name="upgrade-resources"></a>リソースをアップグレードする

ハードウェアとソフトウェアの要件を満たしていることを確認してから、サポートされているアップグレード方法に従って操作を行ってください。

- *ハードウェア/ソフトウェア要件*:

    [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262485(v=office.14)) | [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262485(v=office.14)) | [SharePoint Server 2013](/SharePoint/install/hardware-and-software-requirements-0) | [SharePoint Server 2016](/SharePoint/install/hardware-and-software-requirements)

- *ソフトウェアの境界と制限*:

    [SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262787(v=office.12)) | [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262787(v=office.14)) | [SharePoint Server 2013](/SharePoint/install/software-boundaries-and-limits) | [SharePoint Server 2016](/SharePoint/install/software-boundaries-and-limits-0)

- *アップグレード プロセスの概要*:

    [SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc303420(v=office.12)) | [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc303420(v=office.14)) | [SharePoint Server 2013](/SharePoint/upgrade-and-update/upgrade-to-sharepoint-server-2016) | [SharePoint Server 2016](/SharePoint/upgrade-and-update/upgrade-to-sharepoint-server-2016)

### <a name="create-a-sharepoint-hybrid-solution-between-sharepoint-online-and-on-premises"></a>SharePoint Online とオンプレミスの間で、SharePoint ハイブリッド ソリューションを作成する

移行のニーズに対する答えが、オンプレミスによって提供されるコントロールと、SharePoint Online によって提供される所有権の低いコストとの間にある場合は、SharePoint Server 2013 または 2016 ファームをハイブリッド経由で SharePoint Online に接続できます。 [ハイブリッド ソリューションSharePointについて説明します](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx)

ハイブリッド SharePoint サーバー ファームがビジネスに役立つ場合は、既存の種類のハイブリッドについて理解し、オンプレミスのSharePoint ファームとMicrosoft 365 サブスクリプションの間の接続を構成する方法について理解します。

Microsoft 365開発/テスト環境を作成できます。これは、[テスト ラボ ガイド](m365-enterprise-test-lab-guides.md)を使用して設定できます。 試用版を取得した後、またはサブスクリプションMicrosoft 365購入した後、データを移行できるサイト コレクション、Web、およびドキュメント ライブラリを SharePoint Online で作成できます。 移行 API を使用して手動で移行するか、ハイブリッド ウィザードを使用して個人用サイト のコンテンツをOneDrive for Businessに移行する場合は、移行できます。

> [!NOTE]
> ハイブリッド オプションを使用するには、SharePoint Server 2010 ファームを最初にオンプレミスから SharePoint Server 2013 または 2016 にアップグレードする必要があります。 SharePoint Foundation 2010 および SharePoint Foundation 2013 では、SharePoint Online とのハイブリッド接続はサポートされていません。

## <a name="summary-of-options-for-office-2010-client-and-servers-and-windows-7"></a>Office 2010 クライアントとサーバー、Windows 7 のオプションの概要

Office 2010 サーバー/クライアント、および Windows 7のアップグレード、移行、およびクラウドへの移行オプションを視覚的にまとめた概要は、[サポート終了ポスター](../downloads/Office2010Windows7EndOfSupport.pdf) をご覧ください。

[![Office 2010 クライアントとサーバー、Windows 7 ポスターのサポート終了。](../media/upgrade-from-office-2010-servers-and-products/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)

このポスターでは、Office 2010 クライアントとサーバー製品、Windows 7 のサポート終了を回避するために実行できるさまざまなパスを示します。Microsoft 365 Enterpriseで優先パスとオプションのサポートが強調表示されています。

また、このポスターを [ダウンロード](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Office2010Windows7EndOfSupport.pdf) し、レター、リーガル、または Tabloid (11 x 17) 形式で印刷することもできます。

## <a name="related-articles"></a>関連記事

[Office 2007 または 2010 サーバーとクライアントからのアップグレードに役立つリソース](upgrade-from-office-2010-servers-and-products.md)

[SharePoint 2010 から SharePoint 2013 へのアップグレード プロセスの概要](/SharePoint/upgrade-and-update/overview-of-the-upgrade-process-from-sharepoint-2010-to-sharepoint-2013)

[SharePoint 2010 から SharePoint 2013 へのアップグレードのベスト プラクティス](/SharePoint/upgrade-and-update/best-practices-for-upgrading-from-sharepoint-2010-to-sharepoint-2013)

[SharePoint 2013 でのデータベース アップグレードの問題のトラブルシューティング](/SharePoint/upgrade-and-update/troubleshoot-database-upgrade-issues-in-sharepoint-2013)

[アップグレードに役立つ Microsoft ソリューション プロバイダーを検索する](https://go.microsoft.com/fwlink/?linkid=841249)

[更新された SharePoint 2013 製品サービス ポリシー](/SharePoint/product-servicing-policy/updated-product-servicing-policy-for-sharepoint-2013)

[更新された SharePoint Server 2016 製品サービス ポリシー](/SharePoint/product-servicing-policy/updated-product-servicing-policy-for-sharepoint-server-2016)
