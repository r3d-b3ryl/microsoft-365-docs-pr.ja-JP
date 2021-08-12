---
title: 低速のネットワークでOffice 365のベスト プラクティス
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/29/2016
audience: End User
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
search.appverid:
- MET150
- MET150
- MOP150
- MEW150
- BCS160
ms.assetid: fd16c8d2-4799-4c39-8fd7-045f06640166
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
description: この記事では、低速のネットワークで使用する場合に採用できるベスト プラクティスOffice 365ガイドします。
ms.openlocfilehash: b09fe2a38cd98a09e7d6375abccb0486b59c34c092f60c78144ebc695453f7c6
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53819600"
---
# <a name="best-practices-for-using-office-365-on-a-slow-network"></a>低速のネットワークでOffice 365のベスト プラクティス

インターネット接続が常に高速でダウンしない場合は、いいと思いますか? おそらくその日が来るだろう。 しかし、その間に、バルキー ネットワークを回避し、毎日の作業を完了するために、実用的な操作が可能です。 クラウド Office 365サービスですが、コンテンツをオフラインで操作し、変更をスムーズに同期する方法も多数用意されています。 また、アプリケーションの実行速度が速く、ユーザー インターフェイスの応答性が高いからといって、オフラインでコンテンツを操作する方が効率的な場合があります。 ポイントはこれです:Office 365両方の世界のベストを提供します。 それを利用する方法を次に示します。

> [!TIP]
> ネットワーク接続の速度がどれくらい遅いか (または高速) を確認する必要がありますか? [OOKLA 速度テストまたはネットワーク](https://www.speedtest.net/)速度[テスト アプリを試してみてください](https://www.windowsphone.com/store/app/network-speed-test/9b9ae06b-2961-41ef-987d-b09567cffe70)。

## <a name="why-is-my-network-so-slow"></a>ネットワークの速度が遅い理由

ネットワーク パフォーマンス自体を制御する必要はありませんが、何が起こっているのかを理解するのに役立ちます。 インターネットは非常に複雑ですが、状況をよりよく理解するのに役立ついくつかの概念があります。 この記事のベスト プラクティスに従って、パフォーマンスの問題を回避し、不満を軽減できます。

### <a name="major-factors-that-affect-network-performance"></a>ネットワークパフォーマンスに影響を与える主な要因

![ネットワークパフォーマンスの要因](../media/62a94322-3f1a-4d2d-bbdc-2aa0722d2d96.png)

 **帯域幅と待機時間**: ネットワークパフォーマンスの最も重要な 2 つの手段は、帯域幅と待機時間です。

- 帯域幅は、ビット/秒で測定されるスループットの速度です。 大きい方が良いです。 帯域幅は水道管に似たものになります。 パイプが大きいほど、より多くの水を"通過"できます。

- 待機時間は、コンテンツがサーバーまたはサービスからデバイスに取得するのにかかる時間であり、ミリ秒単位で測定されます。 より速い方が良いです。 遅延は、低帯域幅、疎接続、伝送時間など、さまざまな要因によって発生する可能性があります。

 **一般的な問題**: 帯域幅と待機時間に加えて、他の問題はネットワークパフォーマンスに影響を与え、しばしば予測不可能です。 ネットワークのパフォーマンスは、時刻または物理的な場所に基づいて変動する可能性があります。 自然災害や大規模なパブリック イベントなど、インターネットの使用が急増する特定のイベントが発生すると、ネットワークが詰まってしまう可能性があります。 読み込まれるページのサイズと複雑さ、および転送されるファイルの数とサイズは、パフォーマンスに直接影響します。 WiFi 接続は一時的に低下する可能性があります。たとえば、すべてのユーザーに同時にツイートを要求することで、数千の大規模な会議会議をポーリングします。

 **衛星ネットワークに関** する考慮事項: 衛星ネットワークは、陸上ネットワークが実現不可能な場合 (バックカントリー、クルーズ船、リモート科学領域など) に役立ちます。 これらのネットワークは、赤道から 22,000 マイル上の地理同期軌道に配置された衛星に依存しています。 ただし、伝送は実際には約 90,000 マイルを移動します。そのため、衛星ネットワークの待機時間は、地上ネットワーク (20 ~ 50 ミリ秒) よりも遅くなります (500 ミリ秒以上)。 最適な条件下では、この待機時間に気付かない場合がありますが、大きなファイルのダウンロード、ビデオのストリーミング、ゲームのプレイでは、おそらくそうなるはずです。 もう 1 つの問題は、雷雨や吹雪などの激しい天候が一時的に衛星伝送を中断する可能性がある「雨のフェード」です。

## <a name="are-you-sure-its-the-network"></a>ネットワークだと確信していますか?

パフォーマンスの問題が発生するたびに、まずデバイスが問題の根本原因ではないか確認してください。 大きな改善を行うには、次の 2 つの操作を実行できます。

- デバイスがうまく動作し、コンピューターにマルウェアがインストールされていないことを確認します。

- 可能であれば、メモリを購入します。 メモリの追加は、デバイスのパフォーマンスを向上させる最も簡単で最も効果的な方法です。 大きなファイルやビデオを操作する場合は特に便利です。

詳細については、「パフォーマンスとメンテナンス[Windows」](https://windows.microsoft.com/windows/performance-maintenance-help#performance-maintenance-help)を参照ヒント[PC](https://support.microsoft.com/help/4002019/windows-10-improve-pc-performance)のパフォーマンスを向上Windows 10。

## <a name="best-practices-for-using-your-browser"></a>ブラウザーを使用するためのベスト プラクティス

ブラウザーは Office 365 へのゲートウェイなので、特にページの読み込みにかかる時間と、Office 365 サービスへのラウンド トリップの頻度によって、パフォーマンスに影響を与える可能性があります。

### <a name="browsers-in-general"></a>ブラウザー全般

ブラウザー全般に関する提案を次に示します。

- パフォーマンスに影響を与える可能性がある、または実際に必要ないブラウザー アドオンを無効にします。

- 一時インターネット ファイルのキャッシュ サイズを大きくします。

- 仕事または学校のアカウントにサインインしたら、ブラウザー ウィンドウを終日開いた状態にしてください。 もう一度サインインせずに、他のタブとウィンドウを開く方法があります。 別のアカウントにサインインする必要がある場合は、プライベート ブラウズを使用します。

- 各ページをダウンロードして開いた後は、タブを使用して開いた状態にしてください。 タブ間を移動し、その日の後半にページを使用するのは簡単です。 ページを更新できるのは、そのページに最新のデータが必要な場合のみです。

- ページを開くのに時間がかかっている場合は、ページのダウンロードを停止し (ESC キーを押します)、ページを更新します (F5 キーを押します)。

- 可能な場合は、ラウンド トリップを小Office 365。 たとえば、リストやライブラリをページングするのではなく、検索を使用して大きなライブラリ内のファイルを検索し、リスト内でフィルター処理して、目的の結果に直接アクセスします。 または、ページの読み込み時間を最小限に抑えるビューを作成します。 詳細については、「大規模なリストとライブラリを管理[する」を参照Office 365。](https://support.office.com/article/b4038448-ec0e-49b7-b853-679d3d8fb784#BKMK_PAGES)

- ビデオのパフォーマンスが低い場合は、ビデオをダウンロードしてデバイスで視聴できる場合があります。 ダウンロード リンクを使用できる場合や、ビデオ リンクを右クリックして [ターゲットを名前を付けて保存] **を選択できる場合があります**。

### <a name="browser-specific"></a>ブラウザー固有

特定のブラウザーに関する提案を次に示します。

- **Internet Explorer:** 以前のバージョンInternet Explorer大幅なパフォーマンス向上のために、バージョン 11 以降にアップグレードします。 詳細については、「トラブルシューティング ガイド [for Internet Explorer」 を参照してください](https://support.microsoft.com/help/2437121/troubleshooting-guide-for-internet-explorer-when-you-access-office-365)。
- **FireFox**: 詳細については、「Firefox の動作が遅 [い、または動作を停止する」を参照してください](https://support.mozilla.org/products/firefox/fix-problems/slowness-or-hanging)。
- **Safari**: 詳細については [、「Apple - Safari」を参照してください](https://www.apple.com/safari/)。
- **Chrome**: 詳細については [、「Chrome ヘルプ」を参照してください](https://support.google.com/chrome/?hl=en)。

## <a name="best-practices-for-using-outlook-and-outlook-web-app"></a>ユーザーとユーザーを使用Outlookベスト プラクティスOutlook Web App

電子メールの読み取り、書き込み、整理は、全員の日の大きな部分です。 OWA Outlookと Outlook Web App (OWA) の両方がオフライン サポートを提供します。 スマートフォンで電子メール アプリを使用する方法も便利です。 ニーズに最適な次のオプションを使用します。

- 以前のバージョンより大幅にパフォーマンスを向上Outlook最新バージョンのバージョンにアップグレードします。

- Outlook Web App OWA が次にユーザーに接続できるときにアップロードされるオフライン メッセージ、連絡先、予定表イベントをOffice 365。 オフライン モードでの OWA の設定と使用の詳細については、「オフラインでの OWA の[使用Outlook Web App参照してください](https://support.office.com/article/3214839c-0604-4162-8a97-6856b4c27b36)。

- Outlookキャッシュ モードで作業し、可能な限り自動的に接続できます。 メールボックス全体Outlook、またはメールボックスの一部をダウンロードできます。 詳細については、「キャッシュモードを[有効にする」および「Exchangeで](https://support.office.com/article/7885af08-9a60-4ec3-850a-e221c1ed0c1c)オフラインで作業する」[を参照Outlook。](https://support.office.com/article/f3a1251c-6dd5-4208-aef9-7c8c9522d633)

- Outlookオフライン モードも提供しています。 これを使用するには、まずキャッシュ モードを設定して、アカウントの情報をコンピューターにコピーする必要があります。 オフライン モードでは、Outlook送受信設定を使用するか、手動でオンラインで動作する設定を使用して接続を試みます。 詳細については、「データ接続[](https://support.office.com/article/827fe51f-5609-4062-82b4-3578057f9282)料金を回避するためにオフラインで作業する」、オフラインで作業するときに送受信設定を変更する、オフラインからオンラインに切り替える」[を参照してください](https://support.office.com/article/2460e4a8-16c7-47fc-b204-b1549275aac9)。 [](https://support.office.com/article/f681ec10-cb14-40cb-8709-1909a13c304a)

- スマートフォンをお持ちの場合は、携帯電話会社のネットワークを使用してメールとカレンダーをトリアージできます。

> [!NOTE]
> 次に、OWA または OWA を使用するOutlookを示します。 デバイスでディスク領域が問題ではない場合は、Outlook機能の完全なセットを使用して、最適な機能を使用できます。 デバイスでディスク領域が問題である場合は、機能のサブセットを持ち、オンライン環境でも最適に動作する OWA の使用を検討してください。 もちろん、どちらを使うのも、一緒にうまく機能するからです。

## <a name="best-practices-for-using-onedrive-for-business"></a>アプリを使用するためのベスト プラクティスOneDrive for Business

OneDrive for Businessは、オンラインとオフラインでファイルを操作するように、一から設計されています。 一度設定すると、変更を行う場所や場所を問いなく、変更の同期が自動的に確実に行われます。 ネットワークの速度が遅い場合は、オフライン バージョンのファイルを操作できます。

同期OneDrive for Businessには、SharePoint および Office 365 ビジネス サブスクリプションが付属するか、OneDrive for Business同期アプリを無料でダウンロードできます[](https://support.microsoft.com/kb/2903984)。 また、このアプリはエクスプローラーで開 **くコマンドや** コマンドを使用するよりも **アップロード** です。 詳細については、「コンピューターを[セットアップしてファイルを同期OneDrive for Business」をOffice 365。](https://support.office.com/article/23e1f12b-d896-4cb1-a238-f91d19827a16)

同期アプリの使用に関する追加OneDrive for Business示します。

- 大規模なライブラリを初めて同期する場合は、オフ時間 (夜間など) に同期を開始します。
- [ライブラリとアプリ[の同期を](https://support.office.com/article/a7e41f1f-3a98-4ca7-9443-f10250688330)停止する] 機能を使用OneDrive for Business、更新プログラムの一時的な同期を停止できます。 ただし、この機能は、一度に数時間など、短い期間に使用して、多数の更新プログラムをキューに入れ、複数のユーザーが同じドキュメントで作業する場合のマージ競合のリスクを最小限に抑えるために使用します。

## <a name="best-practices-for-using-onenote"></a>アプリを使用するためのベスト プラクティスOneNote

すべてのSharePointチーム サイトには、ノートブックOneNote組み込みであり、独自のノートブックを簡単に作成できます。 OneNoteは、タスクを完了するために毎日必要な情報を収集する最適な方法です。 たとえば、多くのチームOneNote会議、プロジェクト メモ、アイデア、計画、および状態レポートのコレクション ポイントとして使用します。 ページ、セクション、タブを使用して、この不一部の情報を整理できます。

デスクトップ、OneNoteタブレット、スマートフォンなど、事実上すべてのデバイスからコンテンツにアクセスできるのが、この機能の美しさです。 また、保存や同期について心配する必要はありません。これは、OneNote実行する必要があります。

詳細については、「Microsoft OneNote」[を参照してください](https://office.microsoft.com/onenote)。

## <a name="best-practices-for-using-skype-for-business-and-lync-online"></a>Lync Online と Skype for Businessを使用するためのベスト プラクティス

ネットワークの速度が遅い場合Skype for Business Lync Online を使用する場合の一般的なガイドラインを次に示します。

- 低速のネットワークで正常に動作する場合は、いつでもインスタント メッセージングを使用します。

- 仮想プライベート ネットワーク (VPN) またはリモート アクセス サービス (RAS) 接続を使用して電話をかけることを避ける。

- オーディオ デバイスが承認済みである必要があります。 詳細については [、「Phones and Devices qualified for Microsoft Lync」を参照してください](/skypeforbusiness/lync-cert/ip-phones)。

- オンライン プレゼンテーションPowerPoint使用する場合は、スライドのサイズと複雑さを小さくします。 詳細については、「プレゼンテーションの[パフォーマンスヒントを向上させる」を参照してください](https://support.office.com/article/34c82835-5f23-4bf0-98cc-72235bbd2949)。

- ビデオのパフォーマンスは、ネットワークのパフォーマンスに非常に依存します。 ネットワークの速度が遅い場合は、ビデオを使用しないようにします。

詳細については、「Lync Online でのオーディオ品質またはビデオ品質の低下」、または[「Lync Online](https://support.microsoft.com/kb/2386655)での接続の問題のトラブルシューティング方法」[を参照](https://support.office.com/article/troubleshoot-connection-issues-in-skype-for-business-ca302828-783f-425c-bbe2-356348583771)Skype for Business。

## <a name="best-practices-for-using-sharepoint-lists"></a>リストの使用に関するSharePoint方法

リスト データをオフラインで操作して、データをスクラブ、分析、またはレポートする方法は、低速ネットワークの影響を最小限に抑える最適な方法です。 ほとんどのリストは、Microsoft Access 2019 と Microsoft Access 2016リンクを使用して読み取りおよび書き込みできます。 リストをテーブルテーブルにエクスポートExcel、テーブルとリストの間に一Excelデータ接続を作成します。 リストにリンク[されているテーブルをオフラインで操作するSharePointします](https://support.office.com/article/work-offline-with-tables-that-are-linked-to-sharepoint-lists-5d66594a-6176-4a25-a198-320f13ccf41e)。

詳細については、「大規模なリストとライブラリを管理する」の「大規模なリストの管理の[詳細」を参照](https://support.office.com/article/b4038448-ec0e-49b7-b853-679d3d8fb784)Office 365。

## <a name="best-practices-for-customizing-web-pages"></a>Web ページをカスタマイズするためのベスト プラクティス

Web ページをカスタマイズすると、誤ってページのパフォーマンスが低下する可能性があります。 ページの複雑さ、サイズ、追加される Web パーツの数、最初に表示されるリストアイテムまたはライブラリ アイテムの数、ページのコード化方法など、多くの要因が影響を及ぼす可能性があります。

詳細については、「Tune [SharePoint オンライン パフォーマンス」を参照してください](tune-sharepoint-online-performance.md)。

## <a name="best-practices-for-using-project-online"></a>アプリを使用するためのベスト プラクティスProject Online

次のガイドラインは、ネットワークパフォーマンスの向上に役立ちます。

- Project OnlineオンラインSharePoint同期が必要です。時間がかかる場合があります。 プロジェクト チームの回転率が低い場合は、サイト同期Project無効にして、詳細ページの公開とProjectのパフォーマンスProject向上させます。 Active Directory の同期を、実際にシステムを使用する必要があるリソースのグループに制限し、大規模なグループの同期後に潜在的なアクセス許可の問題を監視します。

- 組織でプロジェクト サイトを使用する場合は、自動的ではなくオンデマンドで作成します。 これにより、最初の発行エクスペリエンスが高速化され、不要なサイトやコンテンツの作成が回避されます。

- Project詳細ページ (PDP) は、プロジェクト全体の再計算をトリガーし、ワークフロー アクションを開始できます。どちらもパフォーマンスが高い操作になります。 同じ PDP で 2 つの更新プロセスを同時にトリガーしないようにするには、予定表フィールド (開始日、終了日、状態の日付、および現在の日付) とスケジュールされていないフィールド (プロジェクト名、説明、所有者) を更新しないようにします。

- 各 PDP に表示Web パーツユーザー設定フィールドの数を減らします。 読み込みと時間の節約を向上させるために更新が必要なフィールドのみを含む専用の PDP を作成します。

- レポートに OData を使用する場合は、サーバー側フィルターを使用して実行時にクエリを実行するデータの量を制限します。

詳細については、「パフォーマンスの調整[」をProject Onlineしてください](https://support.office.com/article/12ba0ebd-c616-42e5-b9b6-cad570e8409c)。

## <a name="whats-the-best-way-to-report-problems"></a>問題を報告する最善の方法は何ですか?

Microsoft は、ネットワークの監視、帯域幅と待機時間の測定、ページ読み込み時間の短縮、ディスク I/O の削減、最小限のダウンロード戦略を使用するページの再設計、データ センターへのハードウェアの追加、データ センターの追加など、Office 365 の全体的なパフォーマンスを継続的に向上させます。 現在の状態とレポートの問題の確認の詳細については、「サービスの正常性を確認するOffice 365[を参照してください](view-service-health.md)。

## <a name="see-also"></a>関連項目

[Office 365 のネットワーク計画とパフォーマンス チューニング](network-planning-and-performance.md)

[Office 365 ネットワーク接続の原則](microsoft-365-network-connectivity-principles.md)

[Office 365 エンドポイントの管理](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)

[Office 365 エンドポイントの FAQ](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d)
