---
title: 使用状況分析でレポートMicrosoft 365カスタマイズする
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
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
description: ブラウザーとブラウザーでレポートをカスタマイズする方法についてPower BI Desktop。
ms.openlocfilehash: 5dcdee05fbb413c7f1925f5e81c7e6596da111e5
ms.sourcegitcommit: c2d752718aedf958db6b403cc12b972ed1215c00
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58556494"
---
# <a name="customize-the-reports-in-microsoft-365-usage-analytics"></a>使用状況分析でレポートMicrosoft 365カスタマイズする

Microsoft 365利用状況分析は、ユーザーがデータをPower BIして使用する方法に関する分析情報を提供するダッシュボードを提供Microsoft 365。 このダッシュボードは、利用状況データを利用するための開始点に過ぎません。 レポートをカスタマイズし、洞察機能を個人に合わせて調整できます。

また、Power BI デスクトップを使用し、レポートをさらにカスタマイズできます。レポートを他のデータ ソースに接続することで事業に関してさらに深い洞察が得られます。

## <a name="customizing-reports-in-the-browser"></a>ブラウザーでレポートをカスタマイズする

次の 2 つの例は、既存のビジュアルを変更する方法と新しいビジュアルを作成する方法を示しています。

### <a name="modify-an-existing-visual"></a>既存のビジュアルを変更する

次の使用例は、ライセンス認証レポート **内** の [ライセンス認証] **タブを変更する方法を示** しています。

1. [ライセンス認証 **/ライセンス] レポートで** 、[ライセンス認証] タブ **を選択** します。

2. 上部の [編集] ボタンをクリックして、編集モードを入力します。[ページの詳細] ボタンを ![ Power BI。](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) ボタンをクリックします。

    ![上部のナビゲーションで [レポートの編集] をクリックします。](../../media/e2c16663-1fbd-4d7f-887c-0cbb891d3b3d.png)

3. 上部の [このページの複製] **を選択します**。

    ![[このページの複製] を選択します。](../../media/b2d18dcd-6b82-4ce7-ab79-1b24e3721309.png)

4. 右下で、Android、iOS、Mac などの OS に基づいてアクティブ化するユーザーの数を示す棒グラフを選択します。

5. 右側の **[視覚化]** 領域で、ビジュアルから **Mac Count** を削除するには、その横にある **[X]** を選択します。

    ![Mac Count を削除します。](../../media/ce3d8358-df57-4f64-bd25-ac5be7fc8713.png)

### <a name="create-a-new-visual"></a>新しいビジュアルを作成する

次の例は、新しい Yammer ユーザーを月単位で追跡記録する新しいビジュアルの作成方法を示しています。

1. 左側のナビゲーションを **使用して [** 製品の使用状況] レポートに移動し、[製品の使用状況]**タブYammer** します。

2. [その他のページ] ボタンを選択して編集モード ![ に切りPower BI。](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) および **編集 .**

3. ページの下部で、 ![[ページの追加] ボタンをクリックPower BI。](../../media/d3b8c117-17d4-4f53-b078-8fefc2155b24.png) をクリックして、新しいページを作成します。

4. 右側の **[視覚化]** 領域で、[積 **み上** げ棒グラフ] (左上から最初の行) を選択します。

    ![[棒グラフ] を選択します。](../../media/214c3fed-6eae-43e6-83fb-708a2d74406e.png)

5. その視覚エフェクトの右下を選択し、ドラッグして大きくします。

6. 右側の **[フィールド** ] 領域で、[予定表] テーブル **を展開** します。

7. [ **MonthName**] を [フィールド] 領域までドラッグします。[ **視覚エフェクト**] 領域の [ **軸**] 見出しのすぐ下にあります。

    ![[月名] をドラッグします。](../../media/bff99987-8c4b-4618-89fd-47df557b0ed7.png)

8. 右にある [ **フィールド**] 領域の [ **TenantProductUsage**] テーブルを展開します。

9. [ **FirstTimeUsers**] を [フィールド] 領域までドラッグします。[ **値**] 見出しのすぐ下にあります。

10. [ **Product**] を [ **フィールド**] 領域までドラッグします。[ **ビジュアル レベル フィルター**] 見出しのすぐ下にあります。

11. [ **フィルターの種類**] 領域が表示されたら、[ **Yammer**] チェック ボックスを選択します。

    ![[選択Yammer] チェック ボックスをオンにします。](../../media/82e99730-0de9-42da-928a-76aab0c3e609.png)

12. 視覚化の一覧の下で、[Visualizaions] の [書式] アイコンPower BI ![ 選択します ](../../media/ee0602f3-3df5-4930-b862-db1d90ae4ae2.png) 。

13. [タイトル] を展開し、[ **タイトル テキスト**] 値を [ **月別の新規 Yammer ユーザー**] に変更します。

14. [ **テキストのサイズ**] 値を [ **12**] に変更します。

15. 右下のページの名前を編集して、新しいページのタイトルを変更します。

16. 上部の [閲覧ビュー] を **クリックし、[** 保存] をクリックしてレポートを **保存します**。

## <a name="customizing-the-reports-in-power-bi-desktop"></a>Power BI Desktop のレポートをカスタマイズする

ほとんどのお客様にとっては、Power BI Web のレポートとグラフ ビジュアルを変更すれば十分です。ただし、場合によっては、自社の事業という文脈において深い洞察を得るには、このデータを他のデータ ソースと接続する必要があります。その場合、Power BI デスクトップを利用して追加のレポートをカスタマイズしたり、ビルドしたりできます。[Power BI デスクトップ](https://go.microsoft.com/fwlink/p/?linkid=849797)は無料でダウンロードできます。

### <a name="use-the-reporting-apis"></a>レポート API を使用する

まず、これらのレポートに電力を供給する ODATA レポート API に直接接続Microsoft 365から開始できます。

1. Go to **get data** \> **Other** \> **ODATA Feed** \> **Connect**.

2. URL ウィンドウに「https:// reports.office.com/pbi/v1.0/」 <i></i> と入力 \<tenantid\> します。

    **注:** レポート API はプレビュー中で、本番環境に入るまで変更される可能性があります。

    ![デスクトップの OData フィード URL Power BIします。](../../media/c0ef967e-a454-4eba-bc8e-61e113170053.png)

3. プロンプトが表示Microsoft 365に認証する管理者資格情報 (組織または学校) Microsoft 365入力します。

    導入テンプレート[アプリ レポート](usage-analytics.md#faq)にアクセスできるユーザーの詳細については、「FAQ Microsoft 365参照してください。

4. 接続が承認されると、[ナビゲーター] ウィンドウが表示されます。このウィンドウに、接続先として利用できるデータセットが表示されます。

    すべて選択し、[読み込み] **を選択します**。

    これで Power BI デスクトップにデータがダウンロードされます。このファイルを保存すれば、必要なレポートの作成を開始できます。

    ![レポート API で使用できる ODATA 値。](../../media/545b4d17-dbbd-4cfc-b75a-a8b27283d438.png)

### <a name="use-the-microsoft-365-usage-analytics-template"></a>使用状況分析テンプレートMicrosoft 365使用する

また、Power BI利用状況分析レポートに対応する Microsoft 365 テンプレート ファイルをデータに接続する開始点として使用することもできます。 pbit ファイルを利用することの長所は、接続文字列が既に確立されていることです。 基本スキーマが返すデータに加え、作成されたあらゆるカスタム メジャーを活用し、基本スキーマの上にさらに構築することもできます。

Microsoft ダウンロード センターからPower BIテンプレート ファイル[をダウンロードできます](https://download.microsoft.com/download/7/8/2/782ba8a7-8d89-4958-a315-dab04c3b620c/Microsoft%20365%20Usage%20Analytics.pbit)。 テンプレート ファイルをダウンロードしたPower BI、次の手順に従って開始します。

1. pbit ファイルを開きます。

2. ダイアログにテナント ID 値を入力します。

    ![テナント ID を入力して pbit ファイルを開きます。](../../media/071ed0bf-8b9d-49c6-81fc-fd4c6cc85bd3.png)

3. プロンプトが表示されたら、管理者資格情報を入力してMicrosoft 365認証します。

     利用状況分析レポートにアクセスできるユーザーのMicrosoft 365詳細については、次の情報を参照してください。

    承認された後に、Power BI ファイルのデータが更新されます。

    データの読み込みには時間がかかることがあります。完了後、ファイルを .pbix ファイルとして保存し、レポートのカスタマイズを続けたり、このレポートにデータ ソースを追加したりできます。

4. レポートを作成する方法、Power BI サービスにレポートを公開する方法、組織と共有する方法を理解するには、「[Getting started with Power BI](/power-bi/fundamentals/desktop-getting-started)」 (Power BI を始める) ドキュメントをご覧ください。この方法でカスタマイズと共有を行う場合、追加の Power BI ライセンスが必要になることがあります。詳細については、Power BI の[ライセンスに関するページ](https://go.microsoft.com/fwlink/p/?linkid=849803)を参照してください。
