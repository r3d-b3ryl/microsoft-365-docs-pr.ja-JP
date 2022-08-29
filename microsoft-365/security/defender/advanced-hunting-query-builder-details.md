---
title: Microsoft 365 Defenderでハンティングするためにガイドモードでサポートされているデータ型とフィルター
description: Microsoft 365 Defenderの高度なハンティングのさまざまなガイド付きモード機能を使用して、クエリを絞り込みます。
keywords: ガイドモード, 高度な捜索, 脅威の捜索, サイバー脅威の捜索, Microsoft 365 Defender, microsoft 365, m365, 検索, クエリ, テレメトリ, カスタム検出, スキーマ, kusto
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 37b5509429d34439d8615dfa18ab29150da94dc7
ms.sourcegitcommit: 7374c7b013890744d74e5214f7f8d69ca7874466
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/23/2022
ms.locfileid: "67406781"
---
# <a name="refine-your-query-in-guided-mode"></a>ガイド モードでクエリを絞り込む 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

> [!IMPORTANT]
> 一部の情報は、市販される前に大幅に変更される可能性があるプレリリース製品に関するものです。 Microsoft は、ここに記載された情報に関して、明示または黙示を問わず、いかなる保証も行いません。
## <a name="use-different-data-types"></a>さまざまなデータ型を使用する

ガイド モードでの高度なハンティングでは、クエリを微調整するために使用できるいくつかのデータ型がサポートされています。

- 数値<br>
![3 番目の条件としての数値のスクリーンショット](../../media/guided-hunting/data-numbers.png)

- 文字列<br>
![3 番目の条件としての文字列のスクリーンショット](../../media/guided-hunting/data-strings.png)

   フリー テキスト ボックスに値を入力し、 **Enter** キーを押して追加します。 値間の区切り記号は **Enter** であることに注意してください。<br>

   ![使用できるさまざまな条件を示すスクリーンショット](../../media/guided-hunting/data-strings-2.png)

- ブール型<br>
![3 番目の条件としてのブール値のスクリーンショット](../../media/guided-hunting/boolean.png)


- Datetime<br>
![3 番目の条件としての datetime 値のスクリーンショット](../../media/guided-hunting/data-datetime.png)


- クローズド リスト - 探している正確な値を覚える必要はありません。 複数選択をサポートする推奨されるクローズド リストから簡単に選択できます。<br>
![3 番目の条件として使用されるクローズド リストのスクリーンショット](../../media/guided-hunting/data-closed.png)


## <a name="use-subgroups"></a>サブグループを使用する
[ **サブグループの追加]** をクリックすると、条件のグループを作成できます。

![スクリーンショットの強調表示 サブグループの追加ボタン](../../media/guided-hunting/subgroup-1.png)

![サブグループの使用を示すスクリーンショット](../../media/guided-hunting/subgroup-2.png)

## <a name="use-smart-auto-complete-for-search"></a>検索にスマートオートコンプリートを使用する
デバイスとユーザー アカウントを検索するためのスマートオートコンプリートがサポートされています。 デバイス ID、完全なデバイス名、またはユーザー アカウント名を覚えておく必要はありません。 探しているデバイスまたはユーザーの最初の数文字の入力を開始すると、必要なものを選択できる推奨リストが表示されます。

![スマートオートコンプリートのサポートを示すスクリーンショット](../../media/guided-hunting/smart-auto.png)

## <a name="use-eventtype"></a>`EventType` を使う
該当するセクションで **EventType** フィルターを使用して、ログオンに失敗したすべてのイベント、ファイル変更イベント、成功したネットワーク接続などの特定のイベントの種類を探すことさえできます。

たとえば、レジストリ値の削除を検索する条件を追加する場合は、[ **レジストリ イベント** ] セクションに移動して **[EventType**] を選択できます。

![さまざまな EventType のスクリーンショット](../../media/guided-hunting/hunt-specific-events-1.png)

[レジストリ イベント] で EventType を選択すると、探しているレジストリ イベント ( **RegistryValueDeleted**) など、さまざまなレジストリ イベントから選択できます。

![EventType RegistryValueDeleted のスクリーンショット](../../media/guided-hunting/hunt-specific-events-2.png)

>[!NOTE] 
>`EventType` は、高度なモードの `ActionType` ユーザーの方が使い慣れている可能性があるデータ スキーマと同等です。

## <a name="test-your-query-with-a-smaller-sample-size"></a>サンプル サイズを小さくしてクエリをテストする
引き続きクエリに取り組んでおり、そのパフォーマンスとサンプル結果をすばやく確認したい場合は、[ **サンプル サイズ** ] ドロップダウン メニューから小さいセットを選択して、返されるレコードの数を調整します。 
 
![サンプル サイズドロップダウン メニューのスクリーンショット](../../media/guided-hunting/smaller-sample.png)

既定では、サンプル サイズは 10,000 の結果に設定されます。 これは、ハンティングで返すことができるレコードの最大数です。 ただし、サンプル サイズを 10 または 100 に下げて、クエリの改善に取り組んでいる間にリソースが少なくなるので、クエリをすばやくテストすることを非常に推奨します。

次に、クエリを完了し、それを使用してハンティング アクティビティに関連するすべての結果を取得する準備ができたら、サンプル サイズが最大 10k に設定されていることを確認します。

## <a name="switch-to-advanced-mode-after-building-a-query"></a>クエリを作成した後、詳細モードに切り替える
**[編集]** をクリックすると、選択した条件によって生成された KQL クエリを表示できます。 KQL で編集すると、対応する KQL クエリを使用して、高度なモードで新しいタブが開きます。

![[KQL で編集] ボタンを強調表示するスクリーンショット](../../media/guided-hunting/switch-to-advanced.png)

![ガイド付きクエリから詳細クエリまで、同じクエリを示すスクリーンショット](../../media/guided-hunting/switch-to-advanced-2.png)

上の例では、選択したビューが [すべて] であるため、KQL クエリは、名前と SHA256 のファイル プロパティを持つすべてのテーブルと、これらのプロパティをカバーするすべての関連列を検索することがわかります。 

ビューを **[Emails & コラボレーション**] に変更すると、クエリは次のように絞り込まれます。

![ガイド付きクエリから高度なクエリまで、ドメインが制限されている同じクエリを示すスクリーンショット](../../media/guided-hunting/switch-to-advanced-3.png)

## <a name="see-also"></a>関連項目
 - [高度なハンティング クォータと使用パラメーター](advanced-hunting-limits.md)
 - [適切な設定で高度なハンティング カバレッジを拡張する](advanced-hunting-extend-data.md)