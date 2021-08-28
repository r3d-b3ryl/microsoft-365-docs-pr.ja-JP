---
title: SharePoint Online のパフォーマンスの問題の診断
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 7/9/2019
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- SPO160
- MET150
ms.assetid: 3c364f9e-b9f6-4da4-a792-c8e8c8cd2e86
description: この記事では、開発者ツールを使用してオンライン サイトで一般的なSharePointを診断Internet Explorer示します。
ms.openlocfilehash: 44e60a2144b1a9a8ecc9ef5572e5cfd988c4b8af
ms.sourcegitcommit: c2d752718aedf958db6b403cc12b972ed1215c00
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58561100"
---
# <a name="diagnosing-performance-issues-with-sharepoint-online"></a>SharePoint Online のパフォーマンスの問題の診断

この記事では、開発者ツールを使用してオンライン サイトで一般的なSharePointを診断Internet Explorer示します。
  
オンライン サイト上のページにカスタマイズのパフォーマンス上SharePoint、3 つの異なる方法があります。
  
- F12 ツール バー ネットワーク モニター

- カスタマイズされていないベースラインとの比較

- SharePointオンライン応答ヘッダーのメトリック

このトピックでは、これらの各メソッドを使用してパフォーマンスの問題を診断する方法について説明します。 問題の原因を把握したら、見つけ出すパフォーマンスの向上に関する記事をSharePointソリューションに取り組む必要があります https://aka.ms/tune 。
  
## <a name="using-the-f12-tool-bar-to-diagnose-performance-in-sharepoint-online"></a>F12 ツール バーを使用してオンラインでのパフォーマンスをSharePointする
<a name="F12ToolInfo"> </a>

この記事では、11 Internet Explorer使用します。 他のブラウザーの F12 開発者ツールのバージョンは、若干異なって見える場合があります。同様の機能があります。 F12 開発者ツールの詳細については、以下を参照してください。
  
- [F12 ツールの新機能](/previous-versions/windows/internet-explorer/ie-developer/dev-guides/bg182632(v=vs.85))

- [F12 開発者ツールの使用](/previous-versions/windows/internet-explorer/ie-developer/samples/bg182326(v=vs.85))

開発者ツールを表示するには **、F12** キーを押し、次のアイコンWi-Fiクリックします。
  
![F12 開発者ツールの Wifi アイコンのスクリーンショット。](../media/27acacbb-5688-459a-aa2f-5c8c5f17b76e.png)
  
[ネットワーク **] タブ** で、緑色の再生ボタンを押してページを読み込む。 このツールは、要求したページを取得するためにブラウザーが要求するファイルをすべて返します。 次のスクリーン ショットは、そのようなリストを 1 つ示しています。
  
![ページ要求で返されるファイル リストのスクリーンショット。](../media/247a9422-76da-4b0c-bed3-ce77b05e4560.png)
  
また、このスクリーン ショットに示すように、右側にファイルのダウンロード時間を確認することもできます。
  
![要求されたページを読み込むのに要する時間を示すSharePoint。](../media/d71ad1fa-9018-4fae-82eb-c1838e7db0ff.png)
  
これにより、ファイルの読み込み時間が視覚的に表示されます。 緑の線は、ページをブラウザーでレンダリングする準備が整った状態を表します。 これにより、サイトのページ読み込み速度が遅くなる可能性があるさまざまなファイルを簡単に確認できます。
  
## <a name="setting-up-a-non-customized-baseline-for-sharepoint-online"></a>オンライン用にカスタマイズされていないベースラインをSharePointする
<a name="F12ToolInfo"> </a>

サイトのパフォーマンスの弱点を特定する最善の方法は、オンラインで完全に使い切れたサイト コレクションをSharePointすることです。 この方法では、サイトのさまざまな側面と、ページ上のカスタマイズを行う必要がないものとを比較できます。 ホーム OneDrive for Businessは、カスタマイズを行う可能性が低い別のサイト コレクションの良い例です。
  
## <a name="viewing-sharepoint-response-header-information"></a>応答SharePoint情報の表示
<a name="F12ToolInfo"> </a>

[SharePointオンライン] では、各ファイルの応答ヘッダーでブラウザーに返される情報にアクセスできます。 パフォーマンスの問題を診断する最も有用な値は **SPRequestDuration** です。これは、要求が処理されるサーバーにかかった時間を表示します。 これは、要求が非常に重く、リソースが多いかどうかを判断するのに役立ちます。 これは、サーバーがページにサービスを提供するために実行している作業の量に関する最良の洞察です。

### <a name="to-view-sharepoint-response-header-information"></a>応答ヘッダー SharePointを表示するには
  
1. F12 ツールがインストールされていることを確認します。 これらのツールのダウンロードとインストールの詳細については [、「F12 ツールの新機能」を参照してください](/previous-versions/windows/internet-explorer/ie-developer/dev-guides/bg182632(v=vs.85))。

2. F12 ツールの [ネットワーク] **タブで、** 緑色の再生ボタンを押してページを読み込む。

3. ツールによって返される .aspx ファイルのいずれかをクリックし、[詳細] を **クリックします**。

    ![応答ヘッダーの詳細を表示します。](../media/1f8a044a-caf8-4613-be2b-7e064141ac8a.png)
  
4. [**応答ヘッダー**] をクリックします。

    ![応答ヘッダーの URL を示す図。](../media/efc7076e-447e-447e-882a-ae3aa721e2c3.png)
  
## <a name="whats-causing-performance-issues-in-sharepoint-online"></a>オンラインでのパフォーマンスの問題の原因SharePoint?
<a name="F12ToolInfo"> </a>

SharePoint [Online](navigation-options-for-sharepoint-online.md)のナビゲーション オプションの記事では、SPRequestDuration 値を使用して、複雑な構造ナビゲーションが原因でページがサーバー上で処理に長い時間がかかると判断する例を示します。 ベースライン サイトの値を取得することで (カスタマイズなし)、特定のファイルの読み込みに時間がかかっているかどうかを判断できます。 オンラインのナビゲーション オプションで[使用SharePointは](navigation-options-for-sharepoint-online.md)、メインの .aspx ファイルです。 このファイルには、ページの読み込み ASP.NET 実行されるコードのほとんどが含まれている。 使用するサイト テンプレートに応じて、ホーム ページをカスタマイズする場合は、start.aspx、home.aspx、default.aspx、または別の名前を使用できます。 この数がベースライン サイトよりかなり高い場合は、パフォーマンスの問題を引き起こしている複雑な問題がページに発生しているという良い兆候です。
  
サイト固有の問題を特定したら、パフォーマンスの低下の原因を把握するために推奨される方法は、ページのカスタマイズなど、考えられるすべての原因を排除し、それらをサイトに 1 つ 1 つ追加し戻すことです。 ページがうまく機能する十分なカスタマイズを削除したら、特定のカスタマイズを 1 つ 1 つ追加できます。
  
たとえば、非常に複雑なナビゲーションを使用している場合は、ナビゲーションを変更してサブサイトを表示しない場合は、開発者ツールをチェックして、これが違いを生み出すのか確認してください。 または、コンテンツのロールアップが大量にある場合は、ページから削除して、問題が改善されるのか確認してください。 考えられるすべての原因を排除し、一度に 1 つで追加し戻す場合、最大の問題である機能を簡単に特定し、ソリューションに向けて作業できます。