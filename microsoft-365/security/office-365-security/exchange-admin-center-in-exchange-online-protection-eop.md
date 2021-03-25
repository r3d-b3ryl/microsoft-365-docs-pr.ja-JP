---
title: スタンドアロン EOP の Exchange 管理者センター
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 97921f0e-832f-40c7-b56d-414faede5191
ms.collection:
- M365-security-compliance
description: スタンドアロンの Exchange Online Protection (EOP) の Web 管理インターフェイスについて説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ab834d14673370a39e148aefa568591ff4c50b8f
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206785"
---
# <a name="exchange-admin-center-in-standalone-eop"></a>スタンドアロン EOP の Exchange 管理者センター

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
-  [Exchange Online Protection スタンドアロン](exchange-online-protection-overview.md)

Exchange 管理センター (EAC) は、スタンドアロンの Exchange Online Protection (EOP) 用の Web ベースの管理コンソールです。

このトピックの Exchange Online バージョンについては、 「[Exchange Online の Exchange 管理センター](/exchange/exchange-admin-center)」を参照してください。

## <a name="open-the-eac-in-eop"></a>EOP で EAC を開く

スタンドアロン EOP のお客様は、次の方法を使用して EAC にアクセスできます。

- **Microsoft 365 管理センターから**:

  1. [すべて表示 <https://admin.microsoft.com> ] に移動し **、[すべて表示] をクリックします**。

     ![Microsoft 365 管理センターで [すべて表示] をクリックします。](../../media/m365-center-show-all.png)

  2. 表示される **[管理センター]** セクションで、[すべての管理 **センター] をクリックします**。

     ![[Microsoft 365 管理センターのすべての管理センター] をクリックします。](../../media/m365-center-select-all-admin-centers.png)

  3. 表示される **[すべての管理センター] ページ** で **、[Exchange Online Protection] をクリックします**。

- に直接移動します `https://admin.protection.outlook.com/ecp/` 。

## <a name="common-user-interface-elements-in-the-eac-in-eop"></a>EOP の EAC の一般的なユーザー インターフェイス要素

ここでは、EAC のユーザー インターフェイス要素について説明します。

![Exchange Online Protection の Exchange 管理センター](../../media/EOP-AdminCenter.png)

### <a name="feature-pane"></a>機能ウィンドウ

EAC で実行する多くのタスクで、これがナビゲーションの第 1 階層になります。[機能] ウィンドウは、機能領域ごとに整理されています。

- **受信者**: グループと外部連絡先を表示する場所です。

- **アクセス許可**: 管理者の役割を管理する場所です。

- **コンプライアンス管理**: 管理者役割グループ レポートと管理者監査ログ レポートが表示されます。

- **保護**: マルウェア対策ポリシー、既定の接続フィルター ポリシー、および DKIM を管理できる場所です。

  > [!NOTE]
  > マルウェア対策ポリシーと既定の接続フィルター ポリシーは、セキュリティ コンプライアンス センターで&する必要があります。 詳細については [、「EOP でマルウェア対策ポリシーを構成する」および「EOP](configure-anti-malware-policies.md) で接続フィルターを構成する」 [を参照してください](configure-the-connection-filter-policy.md)。

- **メール フロー**: ここでは、メール フロー ルール (トランスポート ルールとも呼ばれる)、受け入れドメイン、コネクタを管理し、メッセージ 追跡を実行できる場所を管理します。

- **ハイブリッド**: ハイブリッド構成ウィザードを実行 [](/Exchange/hybrid-configuration-wizard)できる場所と [、Exchange Online PowerShell](/powershell/exchange/mfa-connect-to-exchange-online-powershell)モジュールをインストールできる場所です。

### <a name="tabs"></a>タブ

タブは、ナビゲーションの第 2 階層になります。各機能領域にはさまざまなタブがあり、それぞれのタブは各機能を表しています。

### <a name="toolbar"></a>ツール バー

ほとんどのタブは、クリックするとツールバーが表示されます。ツールバーには、特定のアクションを実行する複数のアイコンがあります。次の表は、各アイコンとそのアクションを示しています。

****

|Icon|Name|アクション|
|---|---|---|
|![[追加] アイコン](../../media/ITPro-EAC-AddIcon.gif)|追加、新規|このアイコンを使用して、新しいオブジェクトを作成します。これらの一部のアイコンには下方向キーが関連付けられており、これをクリックして、作成可能な追加のオブジェクトを表示できます。|
|![編集アイコン](../../media/ITPro-EAC-EditIcon.gif)|編集|このアイコンを使用してオブジェクトを編集します。|
|![[削除] アイコン](../../media/ITPro-EAC-DeleteIcon.gif)|削除|このアイコンを使用してオブジェクトを削除します。一部の削除アイコンには下方向キーがあり、これをクリックして追加オプションを表示できます。|
|![[検索] アイコン](../../media/ITPro-EAC-.gif)|検索|このアイコンを使用して、検索するオブジェクトの検索文字列を入力できる検索ボックスを開きます。|
|![[最新の情報に更新] アイコン](../../media/ITPro-EAC-RefreshIcon.gif)|最新の情報に更新|このアイコンを使用してリスト ビューを更新します。|
|![[その他のオプション] アイコン](../../media/ITPro-EAC-MoreOptionsIcon.gif)|その他のオプション|このアイコンを使用して、そのタブのオブジェクトに対して実行できる他のアクションを表示します。たとえば、 **受信者 \> ユーザー** のアイコンをクリックすると、 **詳細検索** のオプションが表示されます。  |
|![上矢印アイコン](../../media/ITPro-EAC-UpArrowIcon.gif)![下矢印アイコン](../../media/ITPro-EAC-DownArrowIcon.gif)|上方向キーと下方向キー|これらのアイコンを使用して、オブジェクトの優先度を上下に移動します。|
|![[削除] アイコン](../../media/ITPro-EAC-RemoveIcon.gif)|削除|このアイコンを使用して、一覧からオブジェクトを削除します。|
|

### <a name="list-view"></a>リスト ビュー

タブを選択すると、通常、リスト ビューが表示されます。EAC リスト ビューの表示可能限度は、ほぼ 10,000 オブジェクトです。さらに、ページングが含まれているため、結果をページングできます。

### <a name="details-pane"></a>詳細ウィンドウ

リスト ビューからオブジェクトを選択すると、そのオブジェクトに関する情報が詳細ウィンドウに表示されます。場合によっては、[詳細] ウィンドウに管理タスクが含まれていることがあります。

### <a name="me-tile-and-help"></a>[自分] タイルとヘルプ

**[自分]** タイルでは、EAC からのサインアウトおよび他のユーザーとしてサインインが行えます。 [ヘルプ **アイコン]** ![ ドロップダウン ](../../media/ITPro-EAC-HelpIcon.gif) メニューから、次の操作を実行できます。

- **ヘルプ**: ![ヘルプ アイコン](../../media/ITPro-EAC-HelpIcon.gif)をクリックして、オンライン ヘルプ コンテンツを表示します。
- **フィードバック**: フィードバックを残します。
- **コミュニティ**: コミュニティ フォーラムで回答を検索する質問を投稿します。
- **ヘルプ バブルを無効にする**: ヘルプ バブルは、オブジェクトを作成または編集する際に、フィールドのコンテキスト ヘルプを表示します。 ヘルプ バブルをオフにしたり、無効になっている場合はオンにすることができます。
- **コマンド ログの表示**: EAC で構成した結果に基づいて、同等の PowerShell コマンドを表示する新しいウィンドウが開きます。

## <a name="supported-browsers"></a>サポートされているブラウザー

EAC を最大限に活用できるように、常に最新のブラウザー、Office クライアント、アプリを使用することをお勧めします。 また、ソフトウェア更新プログラムも、利用可能になり次第インストールすることをお勧めします。 サービスでサポートされているブラウザーとシステム要件の詳細については、「サービスのシステム要件」 [を参照](https://products.office.com/office-system-requirements)Office。

## <a name="supported-languages"></a>サポートされている言語

次の言語がサポートされ、スタンドアロン EOP の EAC で使用できます。

- アムハラ語
- アラビア語
- バスク語 (バスク)
- バングラ語 (インド)
- ブルガリア語
- カタルニア語
- 簡体字中国語
- 繁体字中国語
- クロアチア語
- チェコ語
- デンマーク語
- オランダ語
- 英語
- エストニア語
- フィリピン語 (フィリピン)
- フィンランド語
- フランス語
- ガリシア語
- ドイツ語
- ギリシャ語
- グジャラート語
- ヘブライ語
- ヒンディー語
- ハンガリー語
- アイスランド語
- インドネシア語
- イタリア語
- 日本語
- カンナダ語
- カザフ語
- スワヒリ語
- 韓国語
- ラトビア語
- リトアニア語
- マレー語 (ブルネイ・ダルサラーム国)
- マレー語 (マレーシア)
- マラヤーラム語
- マラーティー語
- ノルウェー語 (ブークモール)
- ノルウェー語 (ニーノシュク)
- オリヤー語
- ペルシャ語
- ポーランド語
- ポルトガル語 (ブラジル)
- ポルトガル語 (ポルトガル)
- ルーマニア語
- ロシア語
- セルビア語 (キリル、セルビア)
- セルビア語 (ラテン)
- スロバキア語
- スロベニア語
- スペイン語
- スウェーデン語
- タミール語
- テルグ語
- タイ語
- トルコ語
- ウクライナ語
- ウルドゥ語
- ベトナム語
- ウェールズ語