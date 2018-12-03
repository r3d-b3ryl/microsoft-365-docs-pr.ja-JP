---
title: 手順 2 - ディレクトリとネットワークの準備
ms.author: jogruszc
author: JGruszczyk
manager: jemed
ms.date: 09/14/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 環境内のディレクトリとネットワークの準備状況を評価する方法について説明します。
ms.openlocfilehash: e690e99110e647ffc06c9ff7d40b789d8670e571
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869018"
---
# <a name="step-2-directory-and-network-readiness"></a>手順 2: ディレクトリとネットワークの準備

ディレクトリとネットワークが構成され、Windows 10 と Office 365 ProPlus への移行をサポートする準備ができていることを確認します。そのためには、ユーザーが Azure Active Directory サービスを利用できるようにする必要があります。また、ネットワークには通常のトラフィックに加え、PC のアップグレード時やユーザーのファイル、設定、アプリケーションの復元時に発生する可能性のある大量のデータ移動を処理できる容量が必要です。

![](media/step-2-directory-and-network-readiness-media/step-2-directory-and-network-readiness-media-1.png)

<table>
<thead>
<td><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-5.png" alt="Step 2" height="144" width="144" /></td>
<td><p><strong>手順 2: ディレクトリとネットワークの準備</strong></p>
<p>Office 365 ProPlus のクラウド接続サービスと Windows Autopilot などの新しい展開オプションには、Azure Active Directory が必要です。ネットワークと接続性も、Windows の画像、アプリ、ドライバー、関連ファイルを PC に移動する場合に、計画すべき重要な分野です。新しいツールと展開オプションによって、ネットワーク トラフィックを削減および合理化する方法について説明します。</p></td>
<td><a href="https://aka.ms/ddev2" target="_blank"><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-15.png" alt="Step 2" height="130" width="231" /></a></td>
</thead>
</table>

>[!NOTE]
>ディレクトリとネットワークの準備は、推奨される展開プロセスの輪における 2 番目の手順であり、Azure Active Directory に焦点を当て、ネットワークを最適化します。完全なデスクトップ展開プロセスを確認するには、「[モダン デスクトップ展開センター](https://aka.ms/HowToShift)」を参照してください。
>

ディレクトリとネットワークの準備は、スムーズな OS とデスクトップの展開を実現するために不可欠です。自動化された展開と同様、ファイル共有にアクセスできるようにする必要があります。また、お使いのネットワークで非常に大きなファイルの転送を (おそらく一度に数百または数千台の PC に対して) サポートできるようにする必要があります。

Windows 10 および Office 365 ProPlus への移行に伴い、クラウドベースの ID が Azure Active Directory で設定されていることを確認する必要も生じます。これにより、Office 365 ProPlus のライセンス認証を行うだけでなく、Windows Autopilot のような最新のプロビジョニング ソリューションも利用できるようになります。

この記事では、Windows 10 および Office 365 ProPlus への展開に向けて、ディレクトリ サービスや、ユーザーとデバイスのアクセス許可を準備するためのツールとオプションについて説明します。

## <a name="adding-azure-active-directory"></a>Azure Active Directory の追加

組織で既に Office 365、Exchange Online、Microsoft Intune、その他の Microsoft Online サービスを使用している場合の利点は、既に Azure Active Directory が使用されていることです。その場合は、デスクトップ展開の対象ユーザーが Azure Active Directory に含まれており、ライセンスが割り当てられていることを確認するだけで済みます。

現在、Azure Active Directory を使用していない場合、それをセットアップするのに役立つ[多くのリソース](https://docs.microsoft.com/ja-JP/azure/active-directory/)があります。お持ちの Office 365 ライセンスの一部として、Microsoft FastTrack 経由でカスタマイズされた支援を受けることができます。Microsoft FastTrack の詳細については、[こちら](https://fasttrack.microsoft.com)をご確認ください。

Azure Active Directory を配置したら、対象ユーザーは Office 365 ProPlus アプリにサインインしてライセンス認証を行うことができます。また、Microsoft Intune や Windows AutoPilot Deployment を使用して、アプリとポリシーを自動展開できます。

## <a name="network-readiness"></a>ネットワークの準備

展開を計画するときは、帯域幅の要件を考慮する必要があります。展開には、ネットワークに影響を与える 3 つの主要コンポーネント – PC のイメージング、ソフトウェアの更新、ユーザーの個人用設定 – があります。これらのコンポーネント用に、最初の移行で PC ごとに 20 GB 以上、最新の状態を保つため PC ごとに毎月 1 GB 以上が必要になる場合も少なくありません。

まず、これら 3 つの主要コンポーネントの要件を確認することから始めましょう。

### <a name="pc-imaging"></a>PC のイメージング

下の図は、イメージのサイズに基づいて計画するうえで役立ちます。カスタマイズされていない Windows イメージの場合は、通常、PC ごとに 3 GB を計画する必要がありますが、アプリでカスタマイズしたイメージの場合は、6 GB 以上を見込む必要があります。ドライバー パッケージを検討する必要もあります。これは、PC ごとに数百 MB、時には最大 1 GB になることがあります。

### <a name="software-updates"></a>ソフトウェアの更新

ソフトウェアの更新用のネットワーク帯域幅を計画する必要があります。Windows 10 と Office 365 ProPlus では、毎月および半年ごとに更新プログラムを提供する新しいサービス モデルを使用します。このモデルを初めて利用する場合は、どのように機能するかについての詳細を、[こちら](https://docs.microsoft.com/ja-JP/windows/deployment/update/waas-overview)で確認してください。

新しいサービス モデルには、年 2 回の Windows 機能更新プログラム、Office の半期ごとのチャネル更新プログラム、毎月の品質更新プログラムが含まれています。機能更新プログラムのサイズは通常 2 - 4 GB で、Office の半期ごとのチャネル更新プログラムは更新ごとに 300 - 400 MB です。さらに、毎月の品質更新プログラムがあります。これらは数百 MB から 1 GB 以上になることがあります。毎月の更新は累積的で、Windows 10 の各バージョンのサービス有効期間にわたってサイズが増えていくためです。そうは言っても、更新を実装するためにネットワークを通過するデータ量を減らすのに役立つツールがあります。これについては、以下で詳しく説明します。

### <a name="user-personalization"></a>ユーザーの個人用設定

考慮すべき 3 番目のコンポーネントは、ユーザーの個人用設定です。ここでは、PC のリフレッシュまたは交換プロセスの一部として、ユーザーのファイル、設定、アプリケーションの復元に対応するために、ネットワーク帯域幅を計画する必要があります。これらのアイテムは合計で PC ごとに 20 GB を超えることがよくあります。ユーザーによっては、100 GB を超える場合もあります。

## <a name="limiting-bandwidth"></a>**帯域幅の制限**

ネットワーク上の展開に関連するトラフィックの影響を制限する 1 つの方法は、クライアント上の BITS (バックグラウンド インテリジェント転送サービス) 設定を使用して調整することです。BITS は、アダプティブ ビット レート (ABR) を使用して、展開のために使用可能な帯域幅を調整します。これは、グループ ポリシーを使用してクライアント上で構成できます。

[BITS について](https://docs.microsoft.com/ja-JP/windows/desktop/bits/about-bits)

System Center Configuration Manager を使用している場合は、BITS 対応の配布ポイントを構成することも、WDS でマルチキャストを有効にすることもできます。

特定のトラフィックを調整すると、通常のネットワーク トラフィックは、更新プログラムやアプリケーションをダウンロードしている PC の影響を受けにくくなります。しかし、これらのタスクのために帯域幅の特定の割合を切り分けると、生産性は Windows または Office の展開による影響を受けず、プロセスが必要に応じて実行を続けるようになります。そのため、展開に関連するダウンタイムが悪化し、展開が実行される間、ユーザーが PC からロックアウトされる可能性があります。

幸い、大規模なデスクトップ展開のネットワークへの影響を簡単に管理できる新しいツールが用意されています。これには、利用可能な帯域幅の使用を最適化する LEDBAT、展開トラフィックをネットワークの中心から離して境界に移動させるピアツーピア (P2P) オプションが含まれます。

![](media/step-2-directory-and-network-readiness-media/step-2-directory-and-network-readiness-media-3.png)

## <a name="scavenging-bandwidth"></a>**帯域幅の清掃**

Windows Server 2019 および System Center Configuration Manager バージョン 1806 でサポートされている低遅延バックグラウンド トランスポート (LEDBAT) は、Windows クライアントへのネットワーク トラフィックを最適化するよう設計されています。

[Windows Server 2019 のネットワーク機能のトップ テン: \#9 LEDBAT – 遅延に最適化されたバックグラウンド トランスポート](https://blogs.technet.microsoft.com/networking/2018/07/25/ledbat/)

従来の調整とは異なり、LEDBAT はバックグラウンド タスクとして利用可能なすべてのネットワーク帯域幅を使用でき、他のトラフィックから要求された場合は即座に帯域幅を明け渡します。BITS とは異なり、遅延はありません。すべて自動化されているため、手動でのチューニングやスケジューリングは必要なく、サーバー側ですべてがセットアップされます。これにより、大幅なパフォーマンスの向上を実現します。

![](media/step-2-directory-and-network-readiness-media/step-2-directory-and-network-readiness-media-4.png)

## <a name="peer-to-peer-options"></a>**ピアツーピア オプション**

Windows 10 の移行では、PC イメージング、ソフトウェアの更新、ユーザーの個人用設定のために、ピアツーピア オプションがますます使用されるようになっています。それは、Windows 10 の初期展開後にビルド間のアップグレードを容易にするうえでも役に立ちます。ここでは、Windows 10 および Office 関連のトラフィックをネットワークの中心から離すためのいくつかの例を取り上げます。従来の調整方法の必要性を低減し、配布ポイントまたはインターネットからダウンロードするのではなく、ローカル ネットワークのピア上で必要な更新ファイルを PC から検索できるようにします。

**BranchCache** を使用すると、ネットワークを飽和させることなく、分散環境でコンテンツをダウンロードできます。これには次の 2 つのオプションがあります。コンテンツをキャッシュするためにローカル サーバーを使用できるホスト型キャッシュ モードと、クライアントが既にダウンロードしたコンテンツを互いに共有できる分散キャッシュ モード (System Center Configuration Manager でサポートされているモード) です。

System Center Configure でサポートされている**ピア キャッシュ** クライアントでは、ピア キャッシュを使用することもできます。これにより、ネットワーク上で確実に利用可能な PC でコンテンツ配信のソースをホストできるようになります。すべての PC でこれを有効にする必要はなく、ホストとして信頼性の高いネットワーク接続を持つ PC (デスクトップ、ミニタワー、タワー PC など) のみを対象にします。ピア キャッシュは、セットアップ中に Windows PE フェーズで実行される展開タスクにも使用できます。

注: BranchCache とピア キャッシュは補完的であり、同じ環境で一緒に作業できます。

[BranchCache 対ピア キャッシュ](https://blogs.technet.microsoft.com/swisspfe/2018/01/25/branch-cache-vs-peer-cache/)

**配信の最適化**: 別のピアツーピア キャッシュ テクノロジである配信の最適化は、Windows 展開用のネットワーク ベースのコントロールを提供します。Windows 10 の配信の最適化により、組み込みの UWP アプリを更新したり、Microsoft Store からアプリケーションをインストールしたり、簡易更新プログラムを使用してソフトウェアを更新したりできます。この機能は、Windows 10 の初期のバージョンから利用可能でしたが、System Center Configuration Manager と統合されたのはごく最近のことです。Windows 10 バージョン 1803 以降の新しい構成オプションでは、バックグラウンド更新やフォアグラウンド ジョブ (Store からのアプリのインストールなど) の帯域幅制限を個別に設定できるようになりました。

![](media/step-2-directory-and-network-readiness-media/step-2-directory-and-network-readiness-media-5.png)

**Office 365 ProPlus のその他の考慮事項**

ここでは、Office 365 ProPlus の展開によるネットワーク負荷を軽減する 3 つの項目を示します。

**バイナリ デルタ圧縮**: Office 365 ProPlus では、バイナリ デルタ圧縮を使用して、Office 365 ProPlus の最新リリースから次のリリースに更新するときにソフトウェアの更新によって消費される帯域幅を削減します。前のリリースからのバイナリ レベルの変更のみを引き出すことで、累積的な更新プログラムによる毎月のサイズ膨張の影響を最小限に抑えることができます。これにより、PC ごとに、毎月数百 MB のデータを節減できる可能性があります。ただし、この機能を使用する場合、リリースをスキップすることはできません。スキップしたい場合は、完全な累積的更新プログラムをダウンロードする必要があります。

[Office 365 ProPlus の更新プログラムをダウンロードする](https://docs.microsoft.com/ja-JP/deployoffice/overview-of-the-update-process-for-office-365-proplus#download-the-updates-for-office-365-proplus)

**Outlook データ ファイル**: 多くの場合、Outlook はユーザーのメール ボックス全体をローカルにキャッシュし、オフラインで使用するように構成されています。インプレース アップグレード以外の Windows 展開では、アップグレード後にユーザーの Outlook データ ファイルを再構築する必要があります。これは自動化されたプロセスですが、Outlook メールボックスの制限値を通常どおり最大 100 GB に設定した場合、すべてのユーザーのローカルのメールボックス全体を再キャッシュすると大量のデータ転送が発生します。ネットワーク負荷を軽減するには、グループ ポリシーを使用して “Mail to keep offline” の設定値を小さくすることを検討してください。Office 365 ProPlus または Outlook 2016 の Outlook では、既定値は 12 か月に設定されています。オフライン キャッシュを直近 1 - 6 か月の間に設定することを検討してください。この設定を変更してもオンライン メールボックスのサイズには影響しませんし、オンラインの時に Outlook 経由でメールボックス全体を検索することもできます。

![](media/step-2-directory-and-network-readiness-media/step-2-directory-and-network-readiness-media-6.png)

**OneDrive ファイル オンデマンドおよび既知のフォルダー移動**: OneDrive は、PC やクラウド内の他のデバイスからユーザー ファイルを同期および保護するための優れた手段です。既知のフォルダー移動を使用すれば、ユーザーのデスクトップ、ドキュメントや画像のフォルダーから OneDrive にファイルの同期を実行し、新しいデバイスや再イメージ化された PC にサインインしたときに、それらのファイルを使用することができます。ただし、デスクトップ、ドキュメントや画像の保存先に格納されるファイルのサイズと数が膨大になるため、PC で OneDrive を有効にして適用するポリシーのロールアウトを計画的に行う必要があります。1 つのオプションは、グループ ポリシー ネットワーク コントロールを使用して、OneDrive 同期サービスで使用される帯域幅を調整することです。

![](media/step-2-directory-and-network-readiness-media/step-2-directory-and-network-readiness-media-7.png)

[既知のフォルダー移動のセットアップ](https://techcommunity.microsoft.com/t5/Microsoft-OneDrive-Blog/Migrate-Your-Files-to-OneDrive-Easily-with-Known-Folder-Move/ba-p/207076)

[OneDrive ファイル オンデマンド](https://www.microsoft.com/ja-JP/microsoft-365/blog/2017/05/11/introducing-onedrive-files-on-demand-and-additional-features-making-it-easier-to-access-and-share-files/)

OneDrive をまだロールアウトしていない場合は、Windows 7 から Windows 10 への移行時が OneDrive を有効にする絶好の機会であり、そうすることにより Office 365 ProPlus をシームレスに統合できます。アプリとデバイスの準備作業中に、このロールアウトを開始することを検討してください。これにより、Windows イメージを移動し、ネットワーク経由でアプリを展開する前に、ファイルの同期が開始されます。

## <a name="next-step"></a>次の手順 

## <a name="step-3-office-and-lob-app-deliveryhttpsakamsmdd3"></a>[手順 3: Office と LOB アプリの配信](https://aka.ms/mdd3)

## <a name="previous-step"></a>前の手順

## <a name="step-1-device-and-app-readinesshttpsakamsmdd1"></a>[手順 1: デバイスとアプリの準備](https://aka.ms/mdd1)

## <a name="feedback"></a>フィードバック

お客様のご意見をお寄せください。お寄せいただく内容の種類を選択:

製品に関するフィードバック: サインインしてドキュメントに関するフィードバックを送る

この新しいフィードバック システムは、GitHub Issues を利用して構築されています。この変更については、こちらのブログ記事をご覧ください。
