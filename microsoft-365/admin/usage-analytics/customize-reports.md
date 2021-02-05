---
title: Microsoft 365 利用状況分析のレポートをカスタマイズする
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9b76065f-29b9-4b89-8059-c5f9db9ddbf6
description: ブラウザーと Power BI Desktop でレポートをカスタマイズする方法について学習します。
ms.openlocfilehash: 0375b61b6922c99acf927a4283571451deabaf14
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114299"
---
# <a name="customize-the-reports-in-microsoft-365-usage-analytics"></a>Microsoft 365 利用状況分析のレポートをカスタマイズする

::: moniker range="o365-21vianet"

> [!NOTE]
> 管理センターは変更中です。 エクスペリエンスがここで説明されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true)」を参照してください。

::: moniker-end

Microsoft 365 利用状況分析は、ユーザーが Microsoft 365 を導入して使用する方法に関する洞察を提供する Power BI のダッシュボードを提供します。 このダッシュボードは、利用状況データを利用するための開始点に過ぎません。 レポートをカスタマイズし、洞察機能を個人に合わせて調整できます。
  
また、Power BI デスクトップを使用し、レポートをさらにカスタマイズできます。レポートを他のデータ ソースに接続することで事業に関してさらに深い洞察が得られます。
  
## <a name="customizing-reports-in-the-browser"></a>ブラウザーでレポートをカスタマイズする

次の 2 つの例は、既存のビジュアルを変更する方法と新しいビジュアルを作成する方法を示しています。
  
### <a name="modify-an-existing-visual"></a>既存のビジュアルを変更する

この例では、ライセンス認証/ライセンス レポート **内** の [ライセンス認証] **タブを変更する方法を示** します。 
  
1. [ライセンス **認証/ライセンス] レポートで** 、[ライセンス認証] タブ **を選択** します。
    
2. Power BI ボタンの [その他のページ] ボタンで上部の [編集] ボタンを選択して、編集 ![ モードに入 ](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) ります。 
    
    ![Click Edit report on the top right navigation](../../media/e2c16663-1fbd-4d7f-887c-0cbb891d3b3d.png)
  
3. On the top right, choose **Duplicate this page**.
    
    ![Choose Duplicate this page](../../media/b2d18dcd-6b82-4ce7-ab79-1b24e3721309.png)
  
4. 右下で、Android、iOS、Mac などの OS に基づいて、アクティブ化するユーザーの数を示す任意の棒グラフを選択します。
    
5. 右側の **[視覚エフェクト** ] 領域で、ビジュアルから **Mac Count** を削除するには、その横にある **[X] を** 選択します。

    ![Mac Count の削除](../../media/ce3d8358-df57-4f64-bd25-ac5be7fc8713.png)    
    
### <a name="create-a-new-visual"></a>新しいビジュアルを作成する

次の例は、新しい Yammer ユーザーを月単位で追跡記録する新しいビジュアルの作成方法を示しています。
  
1. 左側のナビゲーション **を使って製品** の使用状況レポートに移動し、次の **Yammerします。**
    
2. Power BI の [その他のページ] ボタンを選択して ![ 編集モードに切り ](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) 替 **え、編集モードに切り替えます**。 
    
3. ページの下部にある ![Power BI の [ページの追加] ボタン](../../media/d3b8c117-17d4-4f53-b078-8fefc2155b24.png) をクリックして新しいページを作成します。
  
4. 右側の **[視覚エフェクト]** 領域で、[積み上げ棒グラフ] **(左上** の行) を選択します。

    ![棒グラフの選択](../../media/214c3fed-6eae-43e6-83fb-708a2d74406e.png)
    
5. その視覚エフェクトの右下を選択し、ドラッグして大きくします。

6. 右側の **[フィールド]** 領域で、[カレンダー] テーブル **を展開** します。

7. [ **MonthName**] を [フィールド] 領域までドラッグします。[ **視覚エフェクト**] 領域の [ **軸**] 見出しのすぐ下にあります。
 
    ![月名をドラッグする](../../media/bff99987-8c4b-4618-89fd-47df557b0ed7.png)
    
8. 右にある [ **フィールド**] 領域の [ **TenantProductUsage**] テーブルを展開します。

9. [ **FirstTimeUsers**] を [フィールド] 領域までドラッグします。[ **値**] 見出しのすぐ下にあります。

10. [ **Product**] を [ **フィールド**] 領域までドラッグします。[ **ビジュアル レベル フィルター**] 見出しのすぐ下にあります。

11. [ **フィルターの種類**] 領域が表示されたら、[ **Yammer**] チェック ボックスを選択します。

    ![Select Yammer checkbox](../../media/82e99730-0de9-42da-928a-76aab0c3e609.png)
  
12. 視覚エフェクトの一覧の下で、Power  BI Visualizaions の [書式] アイコン ![ の [書式] アイコンを選択します ](../../media/ee0602f3-3df5-4930-b862-db1d90ae4ae2.png) 。

13. [タイトル] を展開し、[ **タイトル テキスト**] 値を [ **月別の新規 Yammer ユーザー**] に変更します。
    
14. [ **テキストのサイズ**] 値を [ **12**] に変更します。
    
15. 右下のページの名前を編集して、新しいページのタイトルを変更します。

16.  上の読み取りビューを **クリックしてレポート** を保存し、[保存] を **クリックします**。
    
## <a name="customizing-the-reports-in-power-bi-desktop"></a>Power BI Desktop のレポートをカスタマイズする

ほとんどのお客様にとっては、Power BI Web のレポートとグラフ ビジュアルを変更すれば十分です。ただし、場合によっては、自社の事業という文脈において深い洞察を得るには、このデータを他のデータ ソースと接続する必要があります。その場合、Power BI デスクトップを利用して追加のレポートをカスタマイズしたり、ビルドしたりできます。[Power BI デスクトップ](https://go.microsoft.com/fwlink/p/?linkid=849797)は無料でダウンロードできます。 
  
### <a name="use-the-reporting-apis"></a>レポート API を使用する

まず、これらのレポートを提供する Microsoft 365 の ODATA レポート API に直接接続します。
  
1. Go to **get data** \> **Other** \> **ODATA Feed** \> **Connect**.
    
2. URL ウィンドウに「https:// <i></i> \<tenantid\> reports.office.com/pbi/v1.0/」と入力します。
    
    **注:** レポート API はプレビュー中であり、実稼働に入るまで変更される可能性があります。 
  
    ![OData feed URL for Power BI desktop](../../media/c0ef967e-a454-4eba-bc8e-61e113170053.png)
  
3. メッセージが表示されたら、Microsoft 365 (組織または学校) 管理者の資格情報を入力して、Microsoft 365 に対して認証を行います。
    
    Microsoft 365 [導入テンプレート](usage-analytics.md#faq) アプリ レポートにアクセスできるユーザーの詳細については、FAQ を参照してください。 
    
4. 接続が承認されると、[ナビゲーター] ウィンドウが表示されます。このウィンドウに、接続先として利用できるデータセットが表示されます。
    
    すべて選択し、[読み込み] **を選択します**。
    
    これで Power BI デスクトップにデータがダウンロードされます。 このファイルを保存すれば、必要なレポートの作成を開始できます。
    
    ![レポート API で使用可能な ODATA 値](../../media/545b4d17-dbbd-4cfc-b75a-a8b27283d438.png)
  
### <a name="use-the-microsoft-365-usage-analytics-template"></a>Microsoft 365 利用状況分析テンプレートを使用する

データに接続するための開始点として、Microsoft 365 利用状況分析レポートに対応する Power BI テンプレート ファイルを使用することもできます。 pbit ファイルを利用することの長所は、接続文字列が既に確立されていることです。 基本スキーマが返すデータに加え、作成されたあらゆるカスタム メジャーを活用し、基本スキーマの上にさらに構築することもできます。
  
Power BI テンプレート ファイルは、ダウンロード センターから Microsoft ダウンロード センターから [ダウンロードできます](https://download.microsoft.com/download/7/8/2/782ba8a7-8d89-4958-a315-dab04c3b620c/Microsoft%20365%20Usage%20Analytics.pbit)。 Power BI テンプレート ファイルをダウンロードしたら、次の手順から開始します。
  
1. pbit ファイルを開きます。
    
2. ダイアログにテナント ID 値を入力します。
    
    ![Enter your tenant ID to open the pbit file](../../media/071ed0bf-8b9d-49c6-81fc-fd4c6cc85bd3.png)
  
3. メッセージが表示されたら、管理者の資格情報を入力して Microsoft 365 への認証を行います。
    
     Microsoft 365 利用状況分析レポートへのアクセスが許可されているユーザーに関する詳細については、以下を参照してください。 
    
    承認された後に、Power BI ファイルのデータが更新されます。
    
    データの読み込みには時間がかかることがあります。完了後、ファイルを .pbix ファイルとして保存し、レポートのカスタマイズを続けたり、このレポートにデータ ソースを追加したりできます。
    
4. レポートを作成する方法、Power BI サービスにレポートを公開する方法、組織と共有する方法を理解するには、「[Getting started with Power BI](https://go.microsoft.com/fwlink/?linkid=849802)」 (Power BI を始める) ドキュメントをご覧ください。この方法でカスタマイズと共有を行う場合、追加の Power BI ライセンスが必要になることがあります。詳細については、Power BI の[ライセンスに関するページ](https://go.microsoft.com/fwlink/p/?linkid=849803)を参照してください。 
    

