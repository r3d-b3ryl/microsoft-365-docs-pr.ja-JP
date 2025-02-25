---
title: レビュー セット用の電子情報開示 (Premium) ダッシュボード
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
ms.date: 04/05/2022
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: レビュー セットにはMicrosoft Purview eDiscovery (Premium) ダッシュボードを使用してコーパスをすばやく分析し、レビュー戦略の策定に役立つ傾向や主要な統計を特定します。
ms.openlocfilehash: 225cc0d732023322b87e0e04c2cca1455fb0ff87
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2022
ms.locfileid: "66629059"
---
# <a name="ediscovery-premium-dashboard-for-review-sets"></a>レビュー セット用の電子情報開示 (Premium) ダッシュボード

Microsoft Purview eDiscovery (Premium) の場合、大量のドキュメントと電子メール メッセージを確認する必要がある場合があります。 レビュー プロセスを開始する前に、コーパスをすばやく分析して、レビュー戦略の策定に役立つ傾向や主要な統計情報を特定することができます。 これを行うには、電子情報開示 (Premium) ダッシュボードを使用してレビュー セットを作成し、コーパスをすばやく分析できます。

## <a name="step-1-create-a-widget-on-the-review-set-dashboard"></a>手順 1: レビュー セット ダッシュボードにウィジェットを作成する

1. Microsoft Purview コンプライアンス ポータルで、**電子情報開示>電子情報開示 (Premium)** に移動して、組織内のケースの一覧を表示します。
  
2. 既存のケースを選択します。
  
3. [ **レビュー セット** ] タブをクリックし、レビュー セットを選択します。
  
4. **[個々の結果]** ドロップダウン リストで、**[検索プロファイルの表示]** をクリックします。 

   ![DashboardPivot。](../media/dashboardpivot.png)

   **[検索プロファイル ビュー]** ページが表示されます。このページを初めて表示するときに、3 つの既定のウィジェットが表示されます。

   ![ダッシュ ボード。](../media/dashboardonly.png)
  
5. **[新規] ウィジェット** をクリックし、次のいずれかの項目を選択します。

   ![新しいウィジェットドロップダウン リスト。](../media/NewWidgetDropdownBox.png)

   - **ライブラリから選択します。** ウィジェットの既定のライブラリを表示します。 ウィジェットをクリックし、[ **追加** ] をクリックして、[ **検索プロファイル] ビュー** ページのウィジェットに追加します。
  
   - **カスタム ウィジェットを作成する:** カスタム ウィジェットの設定に使用できるポップアップ ページを表示します。 

6. カスタム ウィジェットを作成するには、[ウィジェットの **追加** ] ポップアップ ページで次の操作を行います。

   ![ウィジェットを作成します。](../media/addwidget.png)

    a. ウィジェットの名前を入力します。ウィジェットのタイトル バーに表示されます。 ウィジェットに名前を付ける必要がありますが、ウィジェット データを識別すると便利です。

    b. ウィジェット データに使用される [ **ピボットの選択** ] ドロップダウン リストでプロパティを選択します。 この一覧のアイテムは、レビュー セット内のアイテムの検索可能なプロパティです。 これらのプロパティの説明については、 [電子情報開示 (Premium) のドキュメント メタデータ フィールドに](document-metadata-fields-in-Advanced-eDiscovery.md)関するページを参照してください。 ウィジェットのピボット オプションは、このトピックの **[検索可能なフィールド名** ] 列に一覧表示されます。

    c. 選択したピボット プロパティのデータを表示するグラフの種類を選択します。

  6. [ **追加]** をクリックしてカスタム ウィジェットを作成し、[ **検索プロファイル] ビュー** ページに表示します。

## <a name="step-2-create-a-review-set-search-query"></a>手順 2: レビュー セット検索クエリを作成する

1. ウィジェットのタイトル バーで **[...** ] をクリックし、[ **条件の適用**] をクリックします。

   ![ダッシュボードホーム。](../media/searchprofilehome.png)

2. ポップアップ ページで、ウィジェット キーまたはウィジェット グラフの要素をクリックしてフィルターを作成します。

   ![CreateFilter。](../media/applyconditionfilter.png)

3. 他のウィジェットの複数のウィジェットに対して手順 1 ~ 2 を繰り返します。 

4. 完了したら、[ **クエリとして保存]** をクリックして、レビュー セットの新しい検索クエリとして条件を保存します。

   ![クエリ。](../media/savequery.png)

5. **検索プロファイル ビュー** を閉じて、検索結果ビューに戻ります。

   ビジュアル フィルターを作成した場合、結果のクエリが表示される検索結果に適用され、手順 4. で保存した検索クエリが **[保存済みクエリ]** に表示されます。 レビュー セットのクエリの詳細については、「レビュー セット [内のデータのクエリ](review-set-search.md)」を参照してください。
