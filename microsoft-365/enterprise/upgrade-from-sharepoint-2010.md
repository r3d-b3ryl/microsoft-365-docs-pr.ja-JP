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
description: 2010 年からサーバー 2010 および SharePointサーバー 2010 SharePointアップグレードする情報とリソースを検索します。 2021 年 4 月 13 日の両方のサポート。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5f0919bd80b68167ccfae38a461c79b704e2b803
ms.sourcegitcommit: a7b289b8cc3a2eb79d5e46f20f2968adc0237da1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2021
ms.locfileid: "58394518"
---
# <a name="upgrading-from-sharepoint-2010"></a>SharePoint 2010 からのアップグレード

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

Microsoft SharePoint 2010 および SharePoint Server 2010 は **、2021** 年 4 月 13 日にサポートが終了します。 この記事では、既存の SharePoint Server 2010 データを Microsoft 365 の SharePoint Online に移行したり、オンプレミスの SharePoint Server 2010 環境をアップグレードしたりするのに役立つリソースを提供します。

## <a name="what-is-end-of-support"></a>サポート終了 *とは何ですか*?

ほとんどの Microsoft 製品にはサポート ライフサイクルがあります。その間、新機能、バグ修正、セキュリティ修正などをご利用ください。 サポート終了日が終わると、製品は動作を停止しますが、Microsoft は次の機能を提供しなくなりました。

- 発生する可能性のある問題に対するテクニカル サポート。

- サーバーの安定性と使いやすさに影響を与える可能性がある問題のバグ修正。

- サーバーがセキュリティ侵害に対して脆弱になる可能性のある脆弱性に対するセキュリティ修正。

- タイム ゾーンの更新。

つまり、製品のそれ以上の更新プログラム、パッチ、または修正プログラム (セキュリティ パッチ/修正プログラムを含む) はありません。 Microsoft サポートは、サポートの取り組みを、より新しいバージョンに完全に移行します。

SharePoint Server 2010 のサポートの終了として、製品をアップグレードして重要なデータを移行する前に、不要になったデータを削除してください。

> [!NOTE]
> 通常、ソフトウェア ライフサイクルは最初のリリースから 10 年間続く。 [Microsoft ソリューション プロバイダーは、](https://go.microsoft.com/fwlink/?linkid=841249)次のバージョンのソフトウェアにアップグレードしたり、Microsoft 365移行 (または両方) に移行したりするのに役立ちます。 重要な基礎となるテクノロジのサポート終了日も、特に SharePoint で使用している Microsoft SQL Server のバージョンに関する情報を確認してください。 詳細については、「固定ライフサイクル ポリシー [」を参照してください](https://support.microsoft.com/help/14085)。

## <a name="plan-ahead"></a>計画を立て

サポートが終了する日付を製品ライフサイクル [サイトで確認します](https://support.microsoft.com/lifecycle/search?alpha=SharePoint%20Server%202010)。 これらの日付を念頭に置いてアップグレードまたは移行を計画します。 記載されている日付 *で製品の* 動作が停止しない場合があります。 ただし、インストールは、その日付以降に修正プログラムが適用されなくなるので、製品の次のバージョンへのスムーズな移行を計画する必要があります。

このマトリックスは、移行オプション間でコースをプロットするのに役立ちます。

|サポート製品の終了|中 |高|
|---|---|---|
|SharePoint Server 2010|SharePointServer 2013 (オンプレミス)|SharePoint Online|
||SharePointServer 2013 ハイブリッド と SharePoint Online|SharePointServer 2016 (オンプレミス)|
|||SharePointクラウド ハイブリッド検索|

スケールの低端 (良好) でオプションを選択した場合は、SharePoint Server 2010 からの移行後すぐに別のアップグレードの計画を開始する必要があります。

サーバー 2010 のサポート終了を回避するために使用できる 3 SharePointを示します。

![SharePointServer 2010 のアップグレード パス](../media/upgrade-from-sharepoint-2010/upgrade-from-sharepoint-2010-paths.png)

> [!NOTE]
> SharePoint Server 2010 および SharePoint Foundation 2010 のサポートの終了は、2021 年 4 月 13 日に予定されています。 ただし、製品ライフサイクル サイト [で](https://support.microsoft.com/lifecycle) 最新の日付を確認してください。

## <a name="whats-next"></a>次の手順

SharePointServer 2013 および SharePoint Foundation 2013 は、独自のサーバーにオンプレミスでインストールできます。 または、オンラインサービスSharePointオンラインサービスを使用Microsoft 365。 以下から選択できます。

- [オンライン] SharePoint移行します。

- オンプレミスSharePointサーバーまたはSharePoint Foundation をアップグレードします。

- 上記の両方を実行します。

- ハイブリッド ソリューション[SharePoint実装](/sharepoint/hybrid/hybrid)します。

カスタマイズの保守や移行、ハードウェアのアップグレードなど、サーバー ファームを維持するための隠れたコストを検討してください。 これらの要因を考慮した場合は、オンプレミスのアップグレードが容易になります。 多くのカスタマイズを行わずに従来の SharePoint サーバーでファームを実行する場合は、オンラインへの移行を計画SharePointできます。 オンプレミスのサーバー環境SharePoint、ハードウェア管理のオーバーヘッドを削減するために、SharePoint Online で一部のデータを移動することもできます。

> [!NOTE]
> SharePoint管理者は、Microsoft 365 サブスクリプションを作成し、新しい SharePoint Online サイトをセットアップし、SharePoint Server 2010 からクリーンに切り離し、重要なドキュメントのみを新しいサイトに取り込みます。 その後、残りのデータをサーバー 2010 SharePointからオンプレミスのアーカイブにドレインできます。

|SharePoint Online|オンプレミスの SharePoint Server|
|---|---|
|高コストの時間 (計画/実行/検証)|高コストの時間 (計画/実行/検証)|
|資金コストが安い (ハードウェアの購入の必要なし)|資金コストの増加 (ハードウェア購入)|
|一度の移行でのコスト|将来繰り返される一度の移行でのコスト|
|低い総所有コスト/メンテナンス|高い総所有コスト/メンテナンス|

データを整理し、クラウドに何をMicrosoft 365残すのかを決定する間に、1 回の移行でコストが高くなります。 ただし、データが移行された後は、ハードウェアとソフトウェアの更新プログラムを管理する必要がなくなったので、今後のアップグレードは自動的に行います。 ファームのアップタイムは、Microsoft サービス レベル契約 [(SLA) によってサポートされます](/office365/servicedescriptions/office-365-platform-service-description/service-level-agreement)。

### <a name="migrate-to-sharepoint-online"></a>SharePoint Online への移行

オンラインでSharePoint機能が提供されます。 「サービス[SharePoint説明」を参照してください](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-service-description)。

サーバー 2010 (または SharePoint Foundation 2010) からオンラインにSharePoint移行SharePointできません。 移行作業の多くが手動です。 ただし、この段階では、移動前に不要になったデータとサイトを削除できます。 他のデータをストレージにアーカイブできます。 

Server 2010 SharePoint Foundation 2010 および SharePoint 2010 はサポートの最後に動作を停止しません。 そのため、管理者は、顧客がデータの一部をSharePoint忘れた場合でも、ユーザーがまだ実行されている期間を持つ可能性があります。

SharePoint Server 2013 または SharePoint Server 2016 にアップグレードし、SharePoint Online にデータを入れる場合は[、SharePoint 移行 API](https://support.office.com/article/Upload-on-premises-content-to-SharePoint-Online-using-PowerShell-cmdlets-555049c6-15ef-45a6-9a1f-a1ef673b867c?ui=en-US&amp;rs=en-US&amp;ad=US)を使用して情報を OneDrive for Business に移行できます。

|SharePointオンラインの利点|SharePointオンライン上の欠点|
|---|---|
|Microsoft が SPO ハードウェアおよびすべてのハードウェアの管理を行う。|利用可能な機能は、オンプレミスのサーバー SharePoint SPO によって異なる場合があります。|
|サブスクリプションのグローバル管理者であり、SPO サイトに管理者を割り当てできます。|SharePoint Server オンプレミスのファーム管理者が使用できる一部のアクションは、Microsoft 365 の SharePoint Administrator ロールに存在しない (または必要ありません)。 ただしSharePoint管理、サイト コレクション管理、およびサイト所有権は組織に対してローカルです。|
|Microsoft は、オンラインで実行されるサーバーを含む、基になるハードウェアとSQL更新プログラム、修正プログラムSharePoint適用します。|サービス内の基になるファイル システムにアクセスしないので、カスタマイズは制限されます。|
|Microsoft はサービス [レベル契約を発行し](/office365/servicedescriptions/office-365-platform-service-description/service-level-agreement) 、迅速にサービス レベルのインシデントを解決します。|バックアップと復元、その他の回復オプションは、オンラインのサービスによってSharePointされます。 使用しない場合、バックアップは上書きされます。|
|セキュリティ テストとサーバーパフォーマンスの調整は、Microsoft によってサービス内で継続的に実行されます。|ユーザー インターフェイスとその他の SharePoint 機能の変更はサービスによってインストールされ、オン/オフの切り替えが必要な場合がある。|
|Microsoft 365多くの業界標準を満た[しています。](/compliance/regulatory/offering-home)|移行の際に [FastTrack](https://go.microsoft.com/fwlink/?linkid=518597) でできることが限られる。  <br/> アップグレードの多くが手動または SPO 移行 API を介して行う場合は、「SharePoint および OneDrive 移行コンテンツ ロードマップ」に[記載されています](/sharepointmigration/upload-on-premises-content-to-sharepoint-online-using-powershell-cmdlets)。|
|Microsoft サポート のエンジニアとデータセンターの従業員は、サブスクリプションへの無制限の管理者アクセス権を持つ必要があります。|新しいバージョンの SharePoint をサポートするためにハードウェア インフラストラクチャをアップグレードする必要がある場合や、アップグレードにセカンダリ ファームが必要な場合は、追加コストが発生する可能性があります。|
|ソリューション プロバイダーは、データをオンラインに移行する 1 回SharePointできます。|[オンライン] に対するSharePointが制御できる場合ではありません。 移行後、メニュー、ライブラリ、その他の機能の設計上の違いが一時的に使いやすさに影響を与える可能性があります。|
|オンライン製品は、サービス全体で自動的に更新されます。 機能は廃止される可能性がありますが、サポート ライフサイクルの真の終わりはありません。|SharePoint Server または SharePoint Foundation のサポートのSQLがあります。|

新しいサイトを作成し、必要Microsoft 365にデータを手動で移行する場合は、必要に応[Microsoft 365を確認してください](https://www.microsoft.com/microsoft-365/)。

### <a name="upgrade-sharepoint-server-on-premises"></a>オンプレミスの SharePoint Server のアップグレード

アップグレードはSharePoint Server 2019に行く *必要があります*。 SharePoint Server 2010 から SharePoint Server 2016 または SharePoint 2019 に直接アップグレードする方法はありません。 シリアル アップグレード パス:

- SharePointServer 2010 \> SharePoint Server 2013 SharePoint \> Server 2016

2010 年 2010 年から 2016 年のサーバー 2016 SharePointパス全体をSharePoint計画します。 アップグレードには、ハードウェアのコスト (SQLサーバーもアップグレードする必要があります)、ソフトウェア、および管理が含まれます。 また、カスタマイズのアップグレードや破棄が必要になる場合もあります。 サーバー ファームをアップグレードする前に、重要なカスタマイズをSharePointしてください。

> [!NOTE]
> サポート終了 SharePoint 2010 ファームを維持し、新しいハードウェアに SharePoint Server 2016 ファームをインストールして (別のファームを並べて実行します)、コンテンツの手動移行を計画して実行できます (コンテンツのダウンロードと再アップロードなど)。 しかし、2010 年から手動で移動するアカウントのエイリアスを持つ最新の最終変更アカウントを持つドキュメントなど、これらの手動による移動には潜在的な落とし穴があります。 また、サイト、サブサイト、アクセス許可、リスト構造の再作成など、一部の作業を前もって行う必要があります。 アップグレードする前に、必ず環境をクリーンアップしてください。 ストレージに移動できるデータや不要になったデータを検討します。 これにより、移行の影響を軽減できます。 アップグレードする前に既存のファームが機能し、使用を停止する前に (確かに) 機能する必要があります。

以下の、*サポートされるアップグレード パスとサポート外のアップグレード パス* を確認してください。

- [SharePoint Server 2010](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262747(v=office.12))

- [SharePoint Server 2013](/SharePoint/upgrade-and-update/review-supported-editions-and-products-for-upgrading-to-sharepoint-2013)

カスタマイズがある *場合は、* 移行パスの各手順を計画する必要があります。

- [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc263203(v=office.14))

- [SharePoint Server 2013](/SharePoint/upgrade-and-update/create-a-communication-plan-for-the-upgrade-to-sharepoint-2013)

|オンプレミスの利点|オンプレミスの欠点|
|---|---|
|サーバー のハードウェアから、SharePointファーム (SQL) のすべての側面を完全に制御します。|すべての休憩と修正は、会社の責任です。 ただし、製品がサポート終了を過ぎない場合は、有料の Microsoft サポートに参加できます。|
|ハイブリッドの SharePoint Online サブスクリプションにオンプレミス ファームを接続するオプションを備えた、オンプレミスの SharePoint Server のフル機能一式。|アップグレード、パッチ、セキュリティ修正、ハードウェア アップグレード、および SharePoint Server とそのファームのSQLはオンプレミスで管理されます。|
|オンライン以外のカスタマイズ オプションをフル アクセスSharePointします。|[Microsoft コンプライアンス オファリングは](/compliance/regulatory/offering-home) 、オンプレミスで手動で構成する必要があります。|
|セキュリティ テストとサーバーパフォーマンスの調整は、管理下のオンプレミスで実行されます。|Microsoft 365は、オンプレミスの SharePointサーバーと相互運用しない SharePointオンラインで使用できる機能を提供する場合があります。|
|ソリューション プロバイダーは、データを次のバージョンのサーバー (以降) SharePoint移行するのに役立ちます。|SharePoint Server サイトでは、SharePoint Online で表示される [SSL/TLS](/SharePoint/security-for-sharepoint-server/enable-tls-1-1-and-tls-1-2-support-in-sharepoint-server-2016) 証明書が自動的に使用されることはない。|
|オンプレミスのサーバーで名前付け規則とバックアップと復元、その他のSharePointを完全に制御します。|製品のライフサイクルによって、オンプレミスの SharePoint Server の機能が異なる。|

### <a name="upgrade-resources"></a>リソースのアップグレード

まず、ハードウェア要件とソフトウェア要件を比較します。 現在の環境が基本的な要件を満たしない場合は、ファームまたはサーバーのハードウェアを最初にアップグレードするSQLがあります。 

一部のサイトをオンラインの "evergreen" ハードウェアに移動SharePointがあります。 評価が完了したら、サポートされているアップグレード パスと方法に従います。

- *ハードウェア/ソフトウェアの要件:*

    [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262485(v=office.14))  | [SharePoint Server 2013](/SharePoint/install/hardware-and-software-requirements-0)  | [SharePoint Server 2016](/SharePoint/install/hardware-and-software-requirements)

- *ソフトウェアの境界と制限:*

    [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262787(v=office.14))  | [SharePoint Server 2013](/SharePoint/install/software-boundaries-and-limits)  | [SharePoint Server 2016](/SharePoint/install/software-boundaries-and-limits-0)

- *アップグレード プロセスの概要:*

    [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc303420(v=office.14))  | [SharePoint Server 2013](/SharePoint/upgrade-and-update/upgrade-to-sharepoint-server-2016)  | [SharePoint Server 2016](/SharePoint/upgrade-and-update/upgrade-to-sharepoint-server-2016)

### <a name="create-a-hybrid-solution-with-sharepoint-online-and-sharepoint-server-on-premises"></a>オンプレミスのオンラインサーバーとSharePointサーバー SharePointハイブリッド ソリューションを作成する

ハイブリッド セットアップは、一部の移行ニーズに合ったオンプレミスとオンラインの両方を提供します。 SharePoint Server 2013、2016、または 2019 ファームを SharePoint Online に接続して SharePoint ハイブリッドを作成できます。SharePoint ハイブリッド[ソリューション](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx)について説明します。

ハイブリッド サーバー ファームSharePoint移行の目標である場合は、オンラインで移動するサイトとユーザー、およびオンプレミスの状態を維持する必要があるサイトを把握します。 サーバー ファームSharePoint、企業への影響が大き、中、低とランク付けすると、この決定に役立ちます。 ログイン用のユーザー アカウントとサーバー検索インデックスをオンラインSharePoint共有するSharePointがあります。 ただし、サイトの使い方を確認するまで、この要素は明確ではない場合があります。 会社が後ですべてのコンテンツを SharePoint Online に移行する場合は、残りのすべてのアカウントとデータをオンラインに移動し、オンプレミス ファームを使用停止できます。 サーバー ファームの管理SharePoint、その時点Microsoft 365コンソールを介して行われます。

既存の種類のハイブリッドについて、およびオンプレミスの SharePoint ファームと Microsoft 365 サブスクリプションとの間の接続を構成する方法について理解してください。

|オプション|説明|
|---|---|
|[Microsoft コンプライアンスの提供](/compliance/regulatory/offering-home)。|移行の際に [FastTrack](https://www.microsoft.com/fasttrack/microsoft-365) でできることが限られる。<br/><br/> アップグレードの多くが手動または SPO 移行 API を介して行う場合は、「SharePoint および OneDrive 移行コンテンツ ロードマップ」に[記載されています](/sharepointmigration/upload-on-premises-content-to-sharepoint-online-using-powershell-cmdlets)。|
|Microsoft サポート のエンジニアとデータセンターの従業員は、サブスクリプションへの無制限の管理者アクセス権を持つ必要があります。|新しいバージョンの SharePoint をサポートするためにハードウェア インフラストラクチャをアップグレードする必要がある場合や、セカンダリ ファームが必要な場合は、追加コストが発生する場合があります。|
|パートナーが、SharePoint Online へのデータの移行を一度で行えるようにサポートできる。||
|オンライン製品は、サービス全体で自動的に更新されます。 機能は廃止される可能性がありますが、サポートの真の終わりはありません。||

新しいサイトを作成し、必要にMicrosoft 365にデータを手動で移行することを決定した場合は、必要に応じて、Microsoft 365[を確認してください](https://www.microsoft.com/microsoft-365/)。

### <a name="upgrade-sharepoint-server-on-premises"></a>オンプレミスの SharePoint Server のアップグレード

アップグレードのバージョンをスキップSharePointはありません。 つまり、アップグレードは次の手順で連続して実行されます。

- SharePoint 2007 \> SharePoint Server 2010 SharePoint \> Server 2013 SharePoint \> Server 2016

SharePoint 2007 から SharePoint Server 2016 へのパス全体を実行するには、時間の大幅な投資を意味し、ハードウェア (SQL サーバーもアップグレードする必要があります)、ソフトウェア、および管理コストが必要になります。 機能の重大性に応じて、カスタマイズをアップグレードまたは破棄する必要があります。

> [!NOTE]
> エンド オブ ライフ SharePoint 2007 ファームを維持し、SharePoint Server 2016 ファームを新しいハードウェアにインストールし (したがって、別のファームはサイド バイ サイドで実行)、コンテンツの手動移行を計画して実行できます (コンテンツのダウンロードと再アップロードなど)。 ただし、最後に変更されたアカウントを手動で移動するアカウントのエイリアスに置き換えるドキュメントの移動など、手動による移動にはいくつかの欠点があります。 また、サイト、サブサイト、アクセス許可、リスト構造の再作成など、多くの作業を前もって行う必要があります。 いずれにしても、ストレージに移動できるデータ、または移行の影響を減らす必要がなくなったデータを検討してください。

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
|セキュリティ テストとサーバーパフォーマンスの調整は、管理下のオンプレミスで実行されます。|Microsoft 365、オンプレミスのサーバーと相互運用しない SharePoint Online でSharePoint機能を使用できる場合があります。|
|パートナーは、データを次のバージョンのサーバー (以降) SharePoint移行するのに役立ちます。|SharePoint Server サイトでは、SharePoint Online で表示される [SSL/TLS](/SharePoint/security-for-sharepoint-server/enable-tls-1-1-and-tls-1-2-support-in-sharepoint-server-2016) 証明書が自動的に使用されることはない。|
|オンプレミスのサーバーで名前付け規則とバックアップと復元、その他のSharePointを完全に制御します。|製品のライフサイクルによって、オンプレミスの SharePoint Server の機能が異なる。|

### <a name="upgrade-resources"></a>リソースのアップグレード

ハードウェアとソフトウェアの要件を満たしていることを確認してから、サポートされているアップグレード方法に従って操作を行ってください。

- *ハードウェア/ソフトウェア要件*:

    [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262485(v=office.14)) | [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262485(v=office.14)) | [SharePoint Server 2013](/SharePoint/install/hardware-and-software-requirements-0) | [SharePoint Server 2016](/SharePoint/install/hardware-and-software-requirements)

- *ソフトウェアの境界と制限*:

    [SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262787(v=office.12)) | [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262787(v=office.14)) | [SharePoint Server 2013](/SharePoint/install/software-boundaries-and-limits) | [SharePoint Server 2016](/SharePoint/install/software-boundaries-and-limits-0)

- *アップグレード プロセスの概要*:

    [SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc303420(v=office.12)) | [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc303420(v=office.14)) | [SharePoint Server 2013](/SharePoint/upgrade-and-update/upgrade-to-sharepoint-server-2016) | [SharePoint Server 2016](/SharePoint/upgrade-and-update/upgrade-to-sharepoint-server-2016)

### <a name="create-a-sharepoint-hybrid-solution-between-sharepoint-online-and-on-premises"></a>SharePoint Online とオンプレミスの間で、SharePoint ハイブリッド ソリューションを作成する

移行のニーズに対する答えが、オンプレミスで提供されるコントロールと SharePoint Online によって提供される低い所有コストの間にある場合は、ハイブリッドを通じて SharePoint Server 2013 または 2016 ファームを SharePoint Online に接続できます。 [ハイブリッド ソリューションSharePoint詳細](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx)

ハイブリッド SharePoint Server ファームがビジネスに役立つと判断した場合は、既存の種類のハイブリッドについて理解し、オンプレミスの SharePoint ファームと Microsoft 365 サブスクリプション間の接続を構成する方法について理解してください。

テスト ラボ ガイドを使用してMicrosoft 365開発/テスト環境を作成[できます](m365-enterprise-test-lab-guides.md)。 試用版または購入した Microsoft 365 サブスクリプションを取得した後、SharePoint Online でサイト コレクション、Web、およびドキュメント ライブラリを作成し、データを移行できます。 移行 API を使用して手動で移行するか、またはハイブリッド ウィザードを使用してマイ サイト コンテンツを OneDrive for Businessに移行できます。

> [!NOTE]
> ハイブリッド オプションを使用するには、SharePoint Server 2010 ファームを最初にオンプレミスで SharePoint Server 2013 または 2016 にアップグレードする必要があります。 SharePointFoundation 2010 および SharePoint Foundation 2013 は、オンラインでのハイブリッド接続SharePointしません。

## <a name="summary-of-options-for-office-2010-client-and-servers-and-windows-7"></a>2010 クライアントとサーバー Office 7 のオプションWindows概要

Office 2010 サーバー/クライアント、および Windows 7のアップグレード、移行、およびクラウドへの移行オプションを視覚的にまとめた概要は、[サポート終了ポスター](../downloads/Office2010Windows7EndOfSupport.pdf) をご覧ください。

[![2010 年のクライアントOfficeサーバーと 7 ポスターのWindows終了](../media/upgrade-from-office-2010-servers-and-products/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)

このポスターは、Office 2010 クライアントおよびサーバー製品と Windows 7 のサポート終了を回避するために使用できるさまざまなパスを示し、Microsoft 365 Enterprise では優先パスとオプションのサポートが強調表示されています。

また、この [ポスター](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Office2010Windows7EndOfSupport.pdf) をダウンロードして、レター、リーガル、またはタブロイド (11 x 17) 形式で印刷することもできます。

## <a name="related-articles"></a>関連記事

[2007 または 2010 Office 2010 サーバーとクライアントからのアップグレードに役立つリソース](upgrade-from-office-2010-servers-and-products.md)

[SharePoint 2010 から SharePoint 2013 へのアップグレード プロセスの概要](/SharePoint/upgrade-and-update/overview-of-the-upgrade-process-from-sharepoint-2010-to-sharepoint-2013)

[SharePoint 2010 から SharePoint 2013 へのアップグレードのベスト プラクティス](/SharePoint/upgrade-and-update/best-practices-for-upgrading-from-sharepoint-2010-to-sharepoint-2013)

[SharePoint 2013 でのデータベース アップグレードの問題のトラブルシューティング](/SharePoint/upgrade-and-update/troubleshoot-database-upgrade-issues-in-sharepoint-2013)

[アップグレードに役立つ Microsoft ソリューション プロバイダーを検索する](https://go.microsoft.com/fwlink/?linkid=841249)

[更新された SharePoint 2013 製品サービス ポリシー](/SharePoint/product-servicing-policy/updated-product-servicing-policy-for-sharepoint-2013)

[更新された SharePoint Server 2016 製品サービス ポリシー](/SharePoint/product-servicing-policy/updated-product-servicing-policy-for-sharepoint-server-2016)