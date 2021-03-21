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
description: SharePoint 2010 および Sharepoint Server 2010 からアップグレードする情報とリソースを検索します。 2021 年 4 月 13 日の両方のサポート。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4fa82fb0e382a244cdc126609ac62d17280b9702
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925334"
---
# <a name="upgrading-from-sharepoint-2010"></a>SharePoint 2010 からのアップグレード

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

Microsoft SharePoint 2010 と SharePoint Server 2010 は **、2021** 年 4 月 13 日にサポートの終了に達します。 この記事では、既存の SharePoint Server 2010 データを Microsoft 365 の SharePoint Online に移行したり、オンプレミスの SharePoint Server 2010 環境をアップグレードしたりするのに役立つリソースを提供します。

## <a name="what-is-end-of-support"></a>サポート終了 *とは何ですか*?

ほとんどの Microsoft 製品にはサポート ライフサイクルがあります。その間、新機能、バグ修正、セキュリティ修正などをご利用ください。 サポート終了日が終わると、製品は動作を停止しますが、Microsoft は次の機能を提供しなくなりました。

- 発生する可能性のある問題に対するテクニカル サポート。

- サーバーの安定性と使いやすさに影響を与える可能性がある問題のバグ修正。

- サーバーがセキュリティ侵害に対して脆弱になる可能性のある脆弱性に対するセキュリティ修正。

- タイム ゾーンの更新。

つまり、製品のそれ以上の更新プログラム、パッチ、または修正プログラム (セキュリティ パッチ/修正プログラムを含む) はありません。 Microsoft サポートは、サポートの取り組みを、より新しいバージョンに完全に移行します。

SharePoint Server 2010 のサポートが終了するにつれて、製品をアップグレードして重要なデータを移行する前に、不要になったデータを削除してください。

> [!NOTE]
> 通常、ソフトウェア ライフサイクルは最初のリリースから 10 年間続く。 [Microsoft ソリューション プロバイダーは、](https://go.microsoft.com/fwlink/?linkid=841249) 次のバージョンのソフトウェアにアップグレードしたり、Microsoft 365 移行 (または両方) に移行したりするのに役立ちます。 重要な基になるテクノロジのサポート終了日も、特に SharePoint で使用している Microsoft SQL Serverのバージョンに関する情報を確認してください。 詳細については、「固定ライフサイクル ポリシー [」を参照してください](https://support.microsoft.com/help/14085)。

## <a name="plan-ahead"></a>計画を立て

サポートが終了する日付を製品ライフサイクル [サイトで確認します](https://support.microsoft.com/lifecycle/search?alpha=SharePoint%20Server%202010)。 これらの日付を念頭に置いてアップグレードまたは移行を計画します。 記載されている日付 *で製品の* 動作が停止しない場合があります。 ただし、インストールは、その日付以降に修正プログラムが適用されなくなるので、製品の次のバージョンへのスムーズな移行を計画する必要があります。

このマトリックスは、移行オプション間でコースをプロットするのに役立ちます。

|サポート製品の終了|中 |高|
|---|---|---|
|SharePoint Server 2010|SharePoint Server 2013 (オンプレミス)|SharePoint Online|
||SharePoint Server 2013 ハイブリッドと SharePoint Online|SharePoint Server 2016 (オンプレミス)|
|||SharePoint クラウド ハイブリッド検索|

スケールの低端 (良好) でオプションを選択した場合は、SharePoint Server 2010 からの移行後すぐに別のアップグレードの計画を開始する必要があります。

SharePoint Server 2010 のサポートが終了しないようにするために使用できる 3 つのパスを次に示します。

![SharePoint Server 2010 のアップグレード パス](../media/upgrade-from-sharepoint-2010/upgrade-from-sharepoint-2010-paths.png)

> [!NOTE]
> SharePoint Server 2010 および SharePoint Foundation 2010 のサポートの終了は、現在 2021 年 4 月 13 日に予定されています。 ただし、製品ライフサイクル サイト [で](https://support.microsoft.com/lifecycle) 最新の日付を確認してください。

## <a name="whats-next"></a>次の手順

SharePoint Server 2013 および SharePoint Foundation 2013 は、独自のサーバーにオンプレミスでインストールできます。 または、Microsoft 365 の一部であるオンライン サービスである SharePoint Online を使用できます。 次のオプションを選択できます。

- SharePoint Online に移行します。

- SharePoint Server または SharePoint Foundation をオンプレミスでアップグレードします。

- 上記の両方を実行します。

- [SharePoint ハイブリッド ソリューションを実装](/sharepoint/hybrid/hybrid)します。

カスタマイズの保守や移行、ハードウェアのアップグレードなど、サーバー ファームを維持するための隠れたコストを検討してください。 これらの要因を考慮した場合は、オンプレミスのアップグレードが容易になります。 多くのカスタマイズを行わずに従来の SharePoint サーバーでファームを実行する場合は、SharePoint Online への計画的な移行のメリットを得る可能性があります。 オンプレミスの SharePoint Server 環境では、SharePoint Online で一部のデータを移動して、ハードウェア管理のオーバーヘッドを削減することもできます。

> [!NOTE]
> SharePoint 管理者は、Microsoft 365 サブスクリプションを作成し、新しい SharePoint Online サイトをセットアップし、SharePoint Server 2010 からクリーンに切り離し、重要なドキュメントのみを新しいサイトに取り込みます。 その後、残りのデータを SharePoint Server 2010 サイトからオンプレミスのアーカイブにドレインできます。

|SharePoint Online|オンプレミスの SharePoint Server|
|---|---|
|高コストの時間 (計画/実行/検証)|高コストの時間 (計画/実行/検証)|
|資金コストが安い (ハードウェアの購入の必要なし)|資金コストの増加 (ハードウェア購入)|
|一度の移行でのコスト|将来繰り返される一度の移行でのコスト|
|低い総所有コスト/メンテナンス|高い総所有コスト/メンテナンス|

Microsoft 365 への 1 回の移行では、データを整理し、クラウドに何を取り込むか、何を残すのかを決定する間、コストが高くなります。 ただし、データが移行された後は、ハードウェアとソフトウェアの更新プログラムを管理する必要がなくなったので、今後のアップグレードは自動的に行います。 ファームのアップタイムは、Microsoft サービス レベル契約 [(SLA) によってサポートされます](/office365/servicedescriptions/office-365-platform-service-description/service-level-agreement)。

### <a name="migrate-to-sharepoint-online"></a>SharePoint Online への移行

SharePoint Online が必要なすべての機能を提供します。 [「SharePoint サービスの説明」を参照してください](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-service-description)。

SharePoint Server 2010 (または SharePoint Foundation 2010) から SharePoint Online に直接移行することはできません。 移行作業の多くが手動です。 ただし、この段階では、移動前に不要になったデータとサイトを削除できます。 他のデータをストレージにアーカイブできます。 

SharePoint Server 2010 と SharePoint Foundation 2010 はサポートの最後に動作を停止しません。 そのため、ユーザーがデータの一部を移動することを忘れた場合、管理者は SharePoint がまだ実行されている期間を持つ可能性があります。

SharePoint Server 2013 または SharePoint Server 2016 にアップグレードし、データを SharePoint Online に挿入する場合は [、SharePoint](https://support.office.com/article/Upload-on-premises-content-to-SharePoint-Online-using-PowerShell-cmdlets-555049c6-15ef-45a6-9a1f-a1ef673b867c?ui=en-US&amp;rs=en-US&amp;ad=US) 移行 API を使用して情報を OneDrive for Business に移行できます。

|SharePoint Online の利点|SharePoint Online の欠点|
|---|---|
|Microsoft が SPO ハードウェアおよびすべてのハードウェアの管理を行う。|利用可能な機能は、SharePoint Server オンプレミスと SPO の間で異なる場合があります。|
|サブスクリプションのグローバル管理者であり、SPO サイトに管理者を割り当てできます。|SharePoint Server オンプレミスのファーム管理者が使用できる一部のアクションは、Microsoft 365 の SharePoint Administrator ロールに存在しない (または必要ありません)。 ただし、SharePoint 管理、サイト コレクション管理、およびサイト所有権は組織に対してローカルです。|
|Microsoft は、SharePoint Online が実行されるサーバーを含む、基になるハードウェアとソフトウェアにパッチ、修正SQL更新プログラムを適用します。|サービス内の基になるファイル システムにアクセスしないので、カスタマイズは制限されます。|
|Microsoft はサービス [レベル契約を発行し](/office365/servicedescriptions/office-365-platform-service-description/service-level-agreement) 、迅速にサービス レベルのインシデントを解決します。|バックアップと復元、その他の回復オプションは、SharePoint Online のサービスによって自動化されます。 使用しない場合、バックアップは上書きされます。|
|セキュリティ テストとサーバーパフォーマンスの調整は、Microsoft によってサービス内で継続的に実行されます。|ユーザー インターフェイスとその他の SharePoint 機能の変更はサービスによってインストールされ、オン/オフの切り替えが必要な場合がある。|
|Microsoft 365 は、多くの業界標準である [Microsoft コンプライアンス製品を満たしています](/compliance/regulatory/offering-home)。|移行の際に [FastTrack](https://go.microsoft.com/fwlink/?linkid=518597) でできることが限られる。  <br/> アップグレードの多くが手動または SharePoint Online および OneDrive 移行コンテンツ ロードマップで説明されている SPO 移行 API [を介して行います](/sharepointmigration/upload-on-premises-content-to-sharepoint-online-using-powershell-cmdlets)。|
|Microsoft サポート のエンジニアとデータセンターの従業員は、サブスクリプションへの無制限の管理者アクセス権を持つ必要があります。|新しいバージョンの SharePoint をサポートするためにハードウェア インフラストラクチャをアップグレードする必要がある場合や、アップグレードにセカンダリ ファームが必要な場合は、追加コストが発生する可能性があります。|
|ソリューション プロバイダーは、データを SharePoint Online に移行する 1 回のジョブに役立ちます。|SharePoint Online に対するすべての変更がコントロール内にあるという場合は、この操作を行う必要があります。 移行後、メニュー、ライブラリ、その他の機能の設計上の違いが一時的に使いやすさに影響を与える可能性があります。|
|オンライン製品は、サービス全体で自動的に更新されます。 機能は廃止される可能性がありますが、サポート ライフサイクルの真の終わりはありません。|SharePoint Server または SharePoint Foundation のサポートの終了ライフサイクルと、基になるサーバー SQLがあります。|

新しい Microsoft 365 サイトを作成し、必要に応じて手動でデータを移行する場合は [、Microsoft 365](https://www.microsoft.com/microsoft-365/)のオプションを確認してください。

### <a name="upgrade-sharepoint-server-on-premises"></a>オンプレミスの SharePoint Server のアップグレード

SharePoint Server 2019 では、アップグレードはシリアルに  *実行する必要があります*。 SharePoint Server 2010 から SharePoint Server 2016 または SharePoint 2019 に直接アップグレードする方法はありません。 シリアル アップグレード パス:

- SharePoint Server 2010 \> SharePoint Server 2013 \> SharePoint Server 2016

SharePoint 2010 から SharePoint Server 2016 へのパス全体に従うには時間と計画が必要です。 アップグレードには、ハードウェアのコスト (SQLサーバーもアップグレードする必要があります)、ソフトウェア、および管理が含まれます。 また、カスタマイズのアップグレードや破棄が必要になる場合もあります。 SharePoint Server ファームをアップグレードする前に、重要なカスタマイズを文書化してください。

> [!NOTE]
> サポート終了の SharePoint 2010 ファームを維持し、SharePoint Server 2016 ファームを新しいハードウェアにインストールして (別のファームを並べて実行します)、コンテンツの手動移行を計画して実行できます (たとえば、コンテンツをダウンロードして再アップロードする場合など)。 しかし、2010 年から手動で移動するアカウントのエイリアスを持つ最新の最終変更アカウントを持つドキュメントなど、これらの手動による移動には潜在的な落とし穴があります。 また、サイト、サブサイト、アクセス許可、リスト構造の再作成など、一部の作業を前もって行う必要があります。 アップグレードする前に、必ず環境をクリーンアップしてください。 ストレージに移動できるデータや不要になったデータを検討します。 これにより、移行の影響を軽減できます。 アップグレードする前に既存のファームが機能し、使用を停止する前に (確かに) 機能する必要があります。

以下の、*サポートされるアップグレード パスとサポート外のアップグレード パス* を確認してください。

- [SharePoint Server 2010](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262747(v=office.12))

- [SharePoint Server 2013](/SharePoint/upgrade-and-update/review-supported-editions-and-products-for-upgrading-to-sharepoint-2013)

カスタマイズがある *場合は、* 移行パスの各手順を計画する必要があります。

- [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc263203(v=office.14))

- [SharePoint Server 2013](/SharePoint/upgrade-and-update/create-a-communication-plan-for-the-upgrade-to-sharepoint-2013)

|オンプレミスの利点|オンプレミスの欠点|
|---|---|
|サーバー ハードウェアから SharePoint ファームのすべての側面 (および SharePoint ファームのSQLを完全に制御します。|すべての休憩と修正は、会社の責任です。 ただし、製品がサポート終了を過ぎない場合は、有料の Microsoft サポートに参加できます。|
|ハイブリッドの SharePoint Online サブスクリプションにオンプレミス ファームを接続するオプションを備えた、オンプレミスの SharePoint Server のフル機能一式。|SharePoint Server とそのファームのアップグレード、パッチ、セキュリティ修正、ハードウェア アップグレード、およびすべてのメンテナンスSQLオンプレミスで管理されます。|
|SharePoint Online よりもカスタマイズオプションを大きくするためのフル アクセス。|[Microsoft コンプライアンス オファリングは](/compliance/regulatory/offering-home) 、オンプレミスで手動で構成する必要があります。|
|セキュリティ テストとサーバーパフォーマンスの調整は、管理下のオンプレミスで実行されます。|Microsoft 365 は、SharePoint Server とオンプレミスで相互運用しない SharePoint Online の機能を利用できる場合があります。|
|ソリューション プロバイダーは、データを次のバージョンの SharePoint Server (以降) に移行するのに役立ちます。|SharePoint Server サイトでは、SharePoint Online で表示される [SSL/TLS](/SharePoint/security-for-sharepoint-server/enable-tls-1-1-and-tls-1-2-support-in-sharepoint-server-2016) 証明書が自動的に使用されることはない。|
|SharePoint Server オンプレミスの名前付け規則とバックアップと復元、その他の回復オプションを完全に制御できます。|製品のライフサイクルによって、オンプレミスの SharePoint Server の機能が異なる。|

### <a name="upgrade-resources"></a>リソースのアップグレード

まず、ハードウェア要件とソフトウェア要件を比較します。 現在の環境が基本的な要件を満たしない場合は、ファームまたはサーバーのハードウェアを最初にアップグレードするSQLがあります。 

一部のサイトを SharePoint Online の "evergreen" ハードウェアに移動する場合があります。 評価が完了したら、サポートされているアップグレード パスと方法に従います。

- *ハードウェア/ソフトウェアの要件:*

    [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262485(v=office.14))  | [SharePoint Server 2013](/SharePoint/install/hardware-and-software-requirements-0)  | [SharePoint Server 2016](/SharePoint/install/hardware-and-software-requirements)

- *ソフトウェアの境界と制限:*

    [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262787(v=office.14))  | [SharePoint Server 2013](/SharePoint/install/software-boundaries-and-limits)  | [SharePoint Server 2016](/SharePoint/install/software-boundaries-and-limits-0)

- *アップグレード プロセスの概要:*

    [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc303420(v=office.14))  | [SharePoint Server 2013](/SharePoint/upgrade-and-update/upgrade-to-sharepoint-server-2016)  | [SharePoint Server 2016](/SharePoint/upgrade-and-update/upgrade-to-sharepoint-server-2016)

### <a name="create-a-hybrid-solution-with-sharepoint-online-and-sharepoint-server-on-premises"></a>SharePoint Online と SharePoint Server オンプレミスでハイブリッド ソリューションを作成する

ハイブリッド セットアップは、一部の移行ニーズに合ったオンプレミスとオンラインの両方を提供します。 SharePoint Server 2013、2016、または 2019 ファームを SharePoint Online に接続して SharePoint ハイブリッドを作成できます [。SharePoint](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx)ハイブリッド ソリューションについて説明します。

ハイブリッド SharePoint Server ファームが移行の目標である場合は、オンラインで移動するサイトとユーザー、およびオンプレミスに残る必要があるサイトを把握します。 SharePoint Server ファーム のコンテンツを、企業への影響が高く、中程度、または低い値としてランク付けすると、この決定に役立ちます。 ログイン用のユーザー アカウントと SharePoint Server 検索インデックスのみを SharePoint Online と共有する必要があります。 ただし、サイトの使い方を確認するまで、この要素は明確ではない場合があります。 会社が後ですべてのコンテンツを SharePoint Online に移行する場合は、残りのすべてのアカウントとデータをオンラインに移動し、オンプレミス ファームを使用停止できます。 SharePoint ファームの管理/管理は、その時点から Microsoft 365 コンソールを介して行われます。

既存の種類のハイブリッドと、オンプレミスの SharePoint ファームと Microsoft 365 サブスクリプションとの間の接続を構成する方法について理解してください。

|オプション|説明|
|---|---|
|[Microsoft コンプライアンスの提供](/compliance/regulatory/offering-home)。|移行の際に [FastTrack](https://www.microsoft.com/fasttrack/microsoft-365) でできることが限られる。<br/><br/> アップグレードの多くが手動または SharePoint Online および OneDrive 移行コンテンツ ロードマップで説明されている SPO 移行 API [を介して行います](/sharepointmigration/upload-on-premises-content-to-sharepoint-online-using-powershell-cmdlets)。|
|Microsoft サポート のエンジニアとデータセンターの従業員は、サブスクリプションへの無制限の管理者アクセス権を持つ必要があります。|新しいバージョンの SharePoint をサポートするためにハードウェア インフラストラクチャをアップグレードする必要がある場合や、セカンダリ ファームが必要な場合は、追加コストが発生する可能性があります。|
|パートナーが、SharePoint Online へのデータの移行を一度で行えるようにサポートできる。||
|オンライン製品は、サービス全体で自動的に更新されます。 機能は廃止される可能性がありますが、サポートの真の終わりはありません。||

新しい Microsoft 365 サイトを作成し、必要に応じて手動でデータを移行する場合は [、Microsoft 365](https://www.microsoft.com/microsoft-365/)オプションを確認してください。

### <a name="upgrade-sharepoint-server-on-premises"></a>オンプレミスの SharePoint Server のアップグレード

SharePoint Upgrades でバージョンをスキップする方法はありません。 つまり、アップグレードは次の手順で連続して実行されます。

- SharePoint 2007 \> SharePoint Server 2010 \> SharePoint Server 2013 \> SharePoint Server 2016

SharePoint 2007 から SharePoint Server 2016 へのパス全体を実行するには、時間の大幅な投資を意味し、ハードウェア (SQL サーバーもアップグレードする必要があります)、ソフトウェア、および管理コストが含まれます。 機能の重大性に応じて、カスタマイズをアップグレードまたは破棄する必要があります。

> [!NOTE]
> エンド オブライフ SharePoint 2007 ファームを維持し、SharePoint Server 2016 ファームを新しいハードウェアにインストールして (したがって、別のファームがサイド バイ サイドで実行される)、コンテンツの手動移行を計画して実行できます (コンテンツのダウンロードと再アップロードなど)。 ただし、最後に変更されたアカウントを手動で移動するアカウントのエイリアスに置き換えるドキュメントの移動など、手動による移動にはいくつかの欠点があります。 また、サイト、サブサイト、アクセス許可、リスト構造の再作成など、多くの作業を前もって行う必要があります。 いずれにしても、ストレージに移動できるデータ、または移行の影響を減らす必要がなくなったデータを検討してください。

アップグレードする前に、必ず環境をクリーンアップしてください。 アップグレードする前に既存のファームが機能し、使用を停止する前に確実に機能する必要があります。

以下の、*サポートされるアップグレード パスとサポート外のアップグレード パス* を確認してください。

- [SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262747(v=office.12))

- [SharePoint Server 2010](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262747(v=office.12))

- [SharePoint Server 2013](/SharePoint/upgrade-and-update/review-supported-editions-and-products-for-upgrading-to-sharepoint-2013)

カスタマイズがある *場合は、* 移行パスの各手順でアップグレードを計画する必要があります。

- [SharePoint 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc263203(v=office.12))

- [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc263203(v=office.14))

- [SharePoint Server 2013](/SharePoint/upgrade-and-update/create-a-communication-plan-for-the-upgrade-to-sharepoint-2013)

|オンプレミスの pro|オンプレミスの con|
|---|---|
|サーバー ハードウェアからの、SharePoint ファームの機能すべての完全なコントロール。|すべての休憩と修正は、会社の責任です。 (ただし、製品がサポート終了を過ぎない場合は、有料の Microsoft サポートに参加できます)。|
|ハイブリッドの SharePoint Online サブスクリプションにオンプレミス ファームを接続するオプションを備えた、オンプレミスの SharePoint Server のフル機能一式。|オンプレミスに管理される SharePoint Server のアップグレード、パッチ、セキュリティ修正プログラム、およびすべての保守。|
|高度なカスタマイズのためのフル アクセス許可。|[Microsoft コンプライアンス オファリングは](/compliance/regulatory/offering-home) 、オンプレミスで手動で構成する必要があります。|
|セキュリティ テストとサーバーパフォーマンスの調整は、管理下のオンプレミスで実行されます。|Microsoft 365 では、SharePoint Server オンプレミスと相互運用しない SharePoint Online の機能を利用できる場合があります。|
|パートナーは、データを次のバージョンの SharePoint Server (以降) に移行するのに役立ちます。|SharePoint Server サイトでは、SharePoint Online で表示される [SSL/TLS](/SharePoint/security-for-sharepoint-server/enable-tls-1-1-and-tls-1-2-support-in-sharepoint-server-2016) 証明書が自動的に使用されることはない。|
|SharePoint Server オンプレミスの名前付け規則とバックアップと復元、その他の回復オプションを完全に制御できます。|製品のライフサイクルによって、オンプレミスの SharePoint Server の機能が異なる。|

### <a name="upgrade-resources"></a>リソースのアップグレード

ハードウェアとソフトウェアの要件を満たしていることを確認してから、サポートされているアップグレード方法に従って操作を行ってください。

- *ハードウェア/ソフトウェア要件*:

    [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262485(v=office.14)) | [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262485(v=office.14)) | [SharePoint Server 2013](/SharePoint/install/hardware-and-software-requirements-0) | [SharePoint Server 2016](/SharePoint/install/hardware-and-software-requirements)

- *ソフトウェアの境界と制限*:

    [SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262787(v=office.12)) | [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262787(v=office.14)) | [SharePoint Server 2013](/SharePoint/install/software-boundaries-and-limits) | [SharePoint Server 2016](/SharePoint/install/software-boundaries-and-limits-0)

- *アップグレード プロセスの概要*:

    [SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc303420(v=office.12)) | [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc303420(v=office.14)) | [SharePoint Server 2013](/SharePoint/upgrade-and-update/upgrade-to-sharepoint-server-2016) | [SharePoint Server 2016](/SharePoint/upgrade-and-update/upgrade-to-sharepoint-server-2016)

### <a name="create-a-sharepoint-hybrid-solution-between-sharepoint-online-and-on-premises"></a>SharePoint Online とオンプレミスの間で、SharePoint ハイブリッド ソリューションを作成する

移行のニーズに対する答えが、オンプレミスで提供されるコントロールと SharePoint Online によって提供される低い所有コストの間にある場合は、ハイブリッドを介して SharePoint Server 2013 または 2016 ファームを SharePoint Online に接続できます。 [SharePoint ハイブリッド ソリューションの詳細](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx)

ハイブリッド SharePoint Server ファームがビジネスに役立つと判断した場合は、既存の種類のハイブリッドについて理解し、オンプレミスの SharePoint ファームと Microsoft 365 サブスクリプション間の接続を構成する方法について理解してください。

テスト ラボ ガイドを使用してセットアップできる Microsoft 365 開発/テスト環境 [を作成](m365-enterprise-test-lab-guides.md)できます。 試用版を取得するか、Microsoft 365 サブスクリプションを購入した後、データを移行できるサイト コレクション、Web、およびドキュメント ライブラリを SharePoint Online に作成できます。 移行 API を使用して手動で移行するか、またはハイブリッド ウィザードを使用して、My Site コンテンツを OneDrive for Business に移行する場合は、手動で移行できます。

> [!NOTE]
> ハイブリッド オプションを使用するには、まず SharePoint Server 2010 ファームをオンプレミスで SharePoint Server 2013 または 2016 にアップグレードする必要があります。 SharePoint Foundation 2010 と SharePoint Foundation 2013 は、SharePoint Online とのハイブリッド接続をサポートしません。

## <a name="summary-of-options-for-office-2010-client-and-servers-and-windows-7"></a>2010 クライアントとOffice Windows 7 のオプションの概要

Office 2010 サーバー/クライアント、および Windows 7のアップグレード、移行、およびクラウドへの移行オプションを視覚的にまとめた概要は、[サポート終了ポスター](../downloads/Office2010Windows7EndOfSupport.pdf) をご覧ください。

[![2010 年 2010 Officeサーバーと Windows 7 ポスターのサポートの終了](../media/upgrade-from-office-2010-servers-and-products/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)

このポスターは、Office 2010 クライアントおよびサーバー製品と Windows 7 のサポート終了を回避するために使用できるさまざまなパスを示し、Microsoft 365 Enterprise での優先パスとオプションのサポートが強調表示されています。

また、この [ポスター](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Office2010Windows7EndOfSupport.pdf) をダウンロードして、レター、リーガル、またはタブロイド (11 x 17) 形式で印刷することもできます。

## <a name="related-articles"></a>関連記事

[2007 または 2010 Office 2010 サーバーとクライアントからのアップグレードに役立つリソース](upgrade-from-office-2010-servers-and-products.md)

[Overview of the upgrade process from SharePoint 2010 to SharePoint 2013](/SharePoint/upgrade-and-update/overview-of-the-upgrade-process-from-sharepoint-2010-to-sharepoint-2013)

[SharePoint 2010 から SharePoint 2013 へのアップグレードのベスト プラクティス](/SharePoint/upgrade-and-update/best-practices-for-upgrading-from-sharepoint-2010-to-sharepoint-2013)

[SharePoint 2013 でのデータベース アップグレードの問題のトラブルシューティング](/SharePoint/upgrade-and-update/troubleshoot-database-upgrade-issues-in-sharepoint-2013)

[アップグレードに役立つ Microsoft ソリューション プロバイダーを検索する](https://go.microsoft.com/fwlink/?linkid=841249)

[更新された SharePoint 2013 製品サービス ポリシー](/SharePoint/product-servicing-policy/updated-product-servicing-policy-for-sharepoint-2013)

[更新された SharePoint Server 2016 製品サービス ポリシー](/SharePoint/product-servicing-policy/updated-product-servicing-policy-for-sharepoint-server-2016)