---
title: Advanced eDiscoveryのダッシュボード
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: レビュー セットAdvanced eDiscoveryダッシュボードを使用して、コーパスをすばやく分析し、レビュー戦略の策定に役立つ傾向や主要な統計を特定します。
ms.openlocfilehash: b7bc487e95c2dbae1a65aaad94face6bee19d39b
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60175481"
---
# <a name="advanced-ediscovery-dashboard-for-review-sets"></a>Advanced eDiscoveryのダッシュボード

一部のケースAdvanced eDiscovery、大量のドキュメントと電子メール メッセージを確認する必要がある場合があります。 レビュー プロセスを開始する前に、コーパスをすばやく分析して、レビュー戦略の策定に役立つ傾向や主要な統計を特定できます。 これを行うには、レビュー セットAdvanced eDiscoveryダッシュボードを使用して、コーパスをすばやく分析できます。

## <a name="step-1-create-a-widget-on-the-review-set-dashboard"></a>手順 1: レビュー セット ダッシュボードにウィジェットを作成する

1. [電子情報開示Microsoft 365 コンプライアンス センター] に移動> Advanced eDiscovery **組織の** ケースの一覧を表示します。
  
2. 既存のケースを選択します。
  
3. [レビュー セット **] タブを** クリックし、レビュー セットを選択します。
  
4. **[個々の結果]** ドロップダウン リストで、**[検索プロファイルの表示]** をクリックします。 

   ![DashbordPivot。](../media/dashboardpivot.png)

   [ **プロファイル ビューの検索]** ページが表示されます。このページを初めて表示すると、3 つの既定のウィジェットが表示されます。

   ![ダッシュボード。](../media/dashboardonly.png)
  
5. [新しい **ウィジェット] を** クリックし、次のいずれかの項目を選択します。

   ![新しいウィジェットのドロップダウン リスト。](../media/NewWidgetDropdownBox.png)

   - **ライブラリから選択します。** ウィジェットの既定のライブラリを表示します。 ウィジェットをクリックし、[追加] **をクリック** して、[検索プロファイル ビュー] ページのウィジェット **にウィジェットを追加** します。
  
   - **カスタム ウィジェットの作成:** カスタム ウィジェットのセットアップに使用できるフライアウト ページを表示します。 

6. カスタム ウィジェットを作成するには、[ウィジェットの追加] フライアウト ページ **で次の操作** を行います。

   ![ウィジェットの作成。](../media/addwidget.png)

    a. ウィジェットのタイトル バーに表示されるウィジェットの名前を入力します。 ウィジェットに名前を付ける必要がありますが、ウィジェット データを識別すると便利です。

    b. ウィジェット データに使用する **[ピボットの** 選択] ドロップダウン リストでプロパティを選択します。 このリストのアイテムは、レビュー セット内のアイテムの検索可能なプロパティです。 これらのプロパティの詳細については、「ドキュメント のメタデータ フィールド」[を参照Advanced eDiscovery。](document-metadata-fields-in-Advanced-eDiscovery.md) ウィジェットのピボット オプションは、このトピックの **[検索可能なフィールド名** ] 列に一覧表示されます。

    c. 選択したピボット プロパティのデータを表示するグラフの種類を選択します。

  6. [追加 **]** をクリックしてカスタム ウィジェットを作成し、[検索] プロファイル **ビュー ページに表示** します。

## <a name="step-2-create-a-review-set-search-query"></a>手順 2: レビュー セット検索クエリを作成する

1. ウィジェット **のタイトル バーで [...]** をクリックし、[条件の適用] **をクリックします**。

   ![ダッシュボード。](../media/searchprofilehome.png)

2. [フライアウト] ページで、ウィジェット キーまたはウィジェット グラフの要素をクリックして、フィルターを作成します。

   ![CreateFilter。](../media/applyconditionfilter.png)

3. 他のウィジェットの複数のウィジェットに対して手順 1 ~ 2 を繰り返します。 

4. 完了したら、[クエリとして保存]をクリックして、条件をレビュー セットの新しい検索クエリとして保存します。

   ![クエリ。](../media/savequery.png)

5. [検索] **プロファイル ビューを閉** じて、検索結果ビューに戻します。

   ビジュアル フィルターを作成した場合、表示される検索結果に結果のクエリが適用され、手順 4 で保存した検索クエリが [保存済みクエリ] の下に **表示されます**。 レビュー セット クエリの詳細については、「レビュー セットの [データをクエリする」を参照してください](review-set-search.md)。
