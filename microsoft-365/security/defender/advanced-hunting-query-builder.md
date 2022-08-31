---
title: 高度なハンティングでガイドモードを使用してクエリMicrosoft 365 Defender構築する
description: さまざまな使用可能なフィルターと条件を組み合わせて、ガイド付きモードでクエリを構築する方法について説明します。
keywords: ガイドモード, 高度な捜索, 脅威の捜索, サイバー脅威の捜索, Microsoft 365 Defender, microsoft 365, m365, 検索, クエリ, テレメトリ, カスタム検出, スキーマ, kusto
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.openlocfilehash: 1ec67ba3dd912851425a06066dac0648418bf58e
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67475366"
---
# <a name="build-hunting-queries-using-guided-mode-in-microsoft-365-defender"></a>Microsoft 365 Defenderでガイド モードを使用してハンティング クエリを構築する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

> [!IMPORTANT]
> 一部の情報は、市販される前に大幅に変更される可能性があるプレリリース製品に関するものです。 Microsoft は、ここに記載された情報に関して、明示または黙示を問わず、いかなる保証も行いません。

ガイド付きモードのクエリ ビルダーを使用すると、アナリストは *、Kusto 照会言語 (KQL) やデータ スキーマを知らなくても*、意味のある検索クエリを作成できます。 あらゆる経験レベルのアナリストは、クエリ ビルダーを使用して、過去 30 日間のデータをフィルター処理して脅威を検索したり、インシデント調査を拡大したり、脅威データのデータ分析を実行したり、特定の脅威領域に焦点を当てたりすることができます。

アナリストは、どのデータ セットを見て、どのフィルターと条件を使用して必要なデータに絞り込むかを選択できます。 


## <a name="open-query-in-builder"></a>ビルダーでクエリを開く
**[高度な検索**] ページで、[**新規作成**] を選択して新しいクエリ タブを開き、[**ビルダーでクエリ**] を選択します。 

![ガイド 付きモードのクエリ ビルダーのスクリーンショット](../../media/guided-hunting/query-in-builder-page.png)

これによりガイド モードが表示され、ドロップダウン メニューを使用してさまざまなコンポーネントを選択してクエリを作成できます。

## <a name="specify-the-data-domain-to-hunt-in"></a>ハントするデータ ドメインを指定する
クエリで対象となるドメインを選択することで、ハントの範囲を制御できます。

![ガイド 付きモードのクエリ ビルダー ドメインドロップダウンのスクリーンショット](../../media/guided-hunting/query-builder-view-in.png)


**[すべて]** を選択すると、現在アクセス権を持っているすべてのドメインのデータが含まれます。 特定のドメインに絞り込んだ場合、そのドメインのみに関連するフィルターが許可されます。 

次の項目から選択できます。
- すべてのドメイン - クエリで使用可能なすべてのデータを確認する
- エンドポイント - Microsoft Defender for Endpointによって提供されるエンドポイント データを調べて
- アプリと ID - Microsoft Defender for Cloud AppsとMicrosoft Defender for Identityによって提供されるアプリケーションと ID データを調べるには、[アクティビティ ログ](/defender-cloud-apps/activity-filters)に精通しているユーザーがここで同じデータを見つけることができます。
- Emailとコラボレーション - SharePoint、OneDrive などのメール やコラボレーション アプリのデータを調べるには、[脅威エクスプローラー](/office-365-security/threat-explorer)に精通しているユーザーが同じデータをここで見つけることができます。

## <a name="use-basic-filters"></a>基本フィルターを使用する

既定では、ガイド付きハンティングには、高速な作業を開始するための基本的なフィルターがいくつか含まれています。 

![ガイド 付きモードのクエリ ビルダーの基本フィルター セットのスクリーンショット](../../media/guided-hunting/query-builder-basic-filters.png)



1 つのデータ ソース ( **エンドポイント** など) を選択すると、クエリ ビルダーには該当するフィルター グループのみが表示されます。 その後、そのフィルター グループ ( **EventType** など) を選択し、選択したフィルターを選択することで、絞り込み対象のフィルターを選択できます。

![ガイド 付きモードのクエリ ビルダー エンドポイントの基本フィルター セットのスクリーンショット](../../media/guided-hunting/query-builder-query-basic-filter.png)



クエリの準備ができたら、青い **[クエリの実行** ] ボタンを選択します。 ボタンが淡色表示されている場合は、クエリをさらに入力または編集する必要があることを意味します。 

>[!NOTE]
> 基本的なフィルター ビューでは **AND** 演算子のみが使用されます。つまり、クエリを実行すると、すべてのセット フィルターが true である結果が生成されます。 


## <a name="load-sample-queries"></a>サンプル クエリを読み込む

ガイド付きハンティングに慣れるもう 1 つの簡単な方法は、[サンプル クエリの読み込み] ドロップダウン メニューを使用して **サンプル クエリを読み込む** 方法です。 
![ガイド 付きモードのクエリ ビルダーの読み込みサンプル クエリの一覧のスクリーンショット](../../media/guided-hunting/load-sample-queries.png)

>[!NOTE] 
> サンプル クエリを選択すると、既存のクエリがオーバーライドされます。 

サンプル クエリが読み込まれたら、[ **クエリの実行**] を選択します。

![ガイド 付きモードのクエリ ビルダーに読み込まれたクエリのスクリーンショット](../../media/guided-hunting/load-sample-queries-1.png)

ドメインを既に選択した場合は、それに応じて使用可能なサンプル クエリの一覧が変更されます。

![ガイド 付きモードのクエリ ビルダーの制限付きリストのスクリーンショット](../../media/guided-hunting/load-sample-queries-2.png)

サンプル クエリの完全な一覧を復元するには、 **すべてのドメイン** を選択し、 **サンプル クエリの読み込みを** 再度開きます。

読み込まれたサンプル クエリで、基本フィルター セットの外部でフィルターが使用されている場合、トグル ボタンは淡色表示されます。基本フィルター セットに戻るには、[ **すべてクリア** ] を選択し、[ **すべてのフィルター**] を切り替えます。 


## <a name="use-more-filters"></a>その他のフィルターを使用する

その他のフィルター グループと条件を表示するには、[ **切り替え] を選択して、その他のフィルターと条件を表示します**。

![ガイド モードのクエリ ビルダーのその他のフィルターの切り替えのスクリーンショット](../../media/guided-hunting/query-builder-view-in-endpoints.png)

**[すべてのフィルター**] トグルがアクティブな場合、ガイド モードでフィルターと条件の全範囲を使用できるようになりました。

![ガイド 付きモードのクエリ ビルダーのすべてのフィルターがアクティブなスクリーンショット](../../media/guided-hunting/query-builder-all-filters.png)




### <a name="create-conditions"></a>条件を作成する

クエリで使用するデータのセットを指定するには、[ **フィルターの選択] を選択します**。 さまざまなフィルター セクションを調べて、使用可能なものを見つけます。
 
![使用できるさまざまなフィルターを示すスクリーンショット](../../media/guided-hunting/query-builder-filters.png)

フィルターを検索するには、一覧の上部にある検索ボックスにセクションのタイトルを入力します。 *情報* で終わるセクションには、見ることができるさまざまなコンポーネントに関する情報を提供するフィルターと、エンティティの状態をフィルター処理するフィルターが含まれています。 *イベント* で終わるセクションには、エンティティで監視されているイベントを検索できるフィルターが含まれています。 たとえば、特定のデバイスに関連するアクティビティを探すには、[ **デバイス イベント** ] セクションのフィルターを使用できます。

>[!NOTE]
> 基本フィルターの一覧にないフィルターを選択すると、トグルが非アクティブになるか灰色表示され、基本フィルター ビューに戻ります。 クエリをリセットするか、現在のクエリ内の既存のフィルターを削除するには、[ **すべてクリア**] を選択します。 これにより、基本的なフィルターの一覧も再アクティブ化されます。


次に、2 番目のドロップダウン メニューからデータを選択し、必要に応じて 3 番目のドロップダウン メニューにエントリを指定して、データをさらにフィルター処理するための適切な条件を設定します。

![使用できるさまざまな条件を示すスクリーンショット](../../media/guided-hunting/query-builder-operators-equals.png)

**AND** 条件と **OR** 条件を使用して、クエリにさらに条件を追加できます。 AND はクエリ内のすべての条件を満たす結果を返し、OR はクエリ内の任意の条件を満たす結果を返します。  

![AND OR 演算子を示すスクリーンショット](../../media/guided-hunting/query-builder-operators.png)

クエリを絞り込むと、膨大なレコードを自動的に切り分けて、特定の脅威ハンティングのニーズに対して既にターゲットになっている結果の一覧を生成できます。

クエリの微調整に役立つ、サポートされているデータ型とその他のガイド付きモード機能を理解するには、 [ガイドモードでクエリを絞り込む方法に関する記事を参照してください](advanced-hunting-query-builder-details.md)。

## <a name="try-sample-query-walk-throughs"></a>サンプル クエリのウォークスルーを試す

ガイド付きハンティングに慣れるもう 1 つの方法は、ガイド付きモードで事前に作成されたサンプル クエリを読み込む方法です。 

ハンティング ページの [ **作業の開始** ] セクションには、読み込み可能な 3 つのガイド付きクエリ例が用意されています。 クエリの例には、通常、ハンティングに必要な最も一般的なフィルターと入力の一部が含まれています。 3 つのサンプル クエリのいずれかを読み込むと、ガイドモードを使用してエントリを構築する方法のガイド付きツアーが開きます。

![ガイド 付きモードのクエリ ビルダーによるクエリチュートリアルの開始のスクリーンショット](../../media/guided-hunting/load-examples.png)

青いティーチング バブルの指示に従って、クエリを作成します。 **[クエリの実行]** を選択します。

## <a name="try-some-queries"></a>いくつかのクエリを試す

### <a name="hunt-for-successful-connections-to-specific-ip"></a>特定の IP への接続が成功した場合にハントする
特定の IP アドレスへの正常なネットワーク通信を探すには、「ip」と入力して、推奨されるフィルターを取得します。

![特定の IP ファースト フィルターへの接続が成功した場合のガイド モード クエリ ビルダーのハントのスクリーンショット](../../media/guided-hunting/query-builder-hunt-ip.png)

IP が通信の宛先である特定の IP アドレスに関連するイベントを探すには、[IP アドレス イベント] セクションで選択 `DestinationIPAddress` します。 次に **、equals 演算子を** 選択します。 3 番目のドロップダウン メニューに IP を入力し、 **Enter** キーを押します。

![特定の IP への接続が成功した場合のガイド モード クエリ ビルダーのハントのスクリーンショット](../../media/guided-hunting/query-builder-hunt-ip-2.png)

次に、成功したネットワーク通信イベントを検索する 2 番目の条件を追加するには、特定のイベントの種類のフィルターを検索します。

![特定の IP、2 番目の条件への接続に成功するためのガイド 付きモードクエリ ビルダーのハントのスクリーンショット](../../media/guided-hunting/query-builder-hunt-ip-3.png)

**EventType** フィルターは、ログに記録されたさまざまなイベントの種類を検索します。 高度な捜索のほとんどのテーブルに存在する **ActionType** 列と同じです。 これを選択して、フィルター処理する 1 つ以上のイベントの種類を選択します。 成功したネットワーク通信イベントを探すには、 **DeviceNetworkEvents** セクションを展開し、次を選択 `ConnectionSuccess`します。

![特定の IP 3 番目の条件への接続が成功した場合のガイド モード クエリ ビルダーのハントのスクリーンショット](../../media/guided-hunting/query-builder-hunt-ip-4.png)

最後に、[ **クエリの実行** ] を選択して、成功したすべてのネットワーク通信を 52.168.117.170 IP アドレスに対して検出します。

![特定の IP 結果ビューへの接続が成功した場合のガイド モード クエリ ビルダーのハントのスクリーンショット](../../media/guided-hunting/query-builder-hunt-ip-5.png)

### <a name="hunt-for-high-confidence-phish-or-spam-emails-delivered-to-inbox"></a>受信トレイに配信された信頼性の高いフィッシングメールまたはスパムメールを探す 

配信時に受信トレイ フォルダーに配信されたすべての信頼度の高いフィッシングメールとスパム メールを検索するには、最初に [Email イベント] で **[ConfidenceLevel**] を選択し、複数選択をサポートする推奨される閉じたリストの [**フィッシング**] と [**スパム]** の両方で **[****高]** を選択します。

![ガイド付きモードのクエリ ビルダーが、受信トレイに配信された高信頼のフィッシングメールまたはスパム メールを検索する最初の条件のスクリーンショット](../../media/guided-hunting/hunt-phishing-1.png)

次に、フォルダーまたは **DeliveryLocation、受信トレイ/フォルダー** を指定する別の条件を追加します。 

![ガイド 付きモードのクエリ ビルダーが、受信トレイに配信された高信頼のフィッシングメールまたはスパム メールを検索する 2 番目の条件のスクリーンショット](../../media/guided-hunting/hunt-phishing-2.png)




## <a name="see-also"></a>関連項目

- [ガイド モードでクエリを絞り込む](advanced-hunting-query-builder-details.md)
- [ガイド モードでクエリ結果を操作する](advanced-hunting-query-builder-results.md)
 - [スキーマを理解する](advanced-hunting-schema-tables.md)
