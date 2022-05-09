---
title: Microsoft 365利用状況分析のレポートをカスタマイズする
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
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
description: ブラウザーとPower BI Desktopでレポートをカスタマイズする方法について説明します。
ms.openlocfilehash: 32cf44c8d72160a583a841e26c2ad6934bd7eef2
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60175733"
---
# <a name="customize-the-reports-in-microsoft-365-usage-analytics"></a>Microsoft 365利用状況分析のレポートをカスタマイズする

Microsoft 365利用状況分析は、ユーザーがMicrosoft 365を採用して使用する方法に関する分析情報を提供するダッシュボードをPower BIに提供します。 このダッシュボードは、利用状況データを利用するための開始点に過ぎません。 レポートをカスタマイズし、洞察機能を個人に合わせて調整できます。

また、Power BI デスクトップを使用し、レポートをさらにカスタマイズできます。レポートを他のデータ ソースに接続することで事業に関してさらに深い洞察が得られます。

## <a name="customizing-reports-in-the-browser"></a>ブラウザーでレポートをカスタマイズする

次の 2 つの例は、既存のビジュアルを変更する方法と新しいビジュアルを作成する方法を示しています。

### <a name="modify-an-existing-visual"></a>既存のビジュアルを変更する

この例では、 **ライセンス認証** レポート内の [ **アクティブ化** ] タブを変更する方法を示します。

1. **[ライセンス認証]/[ライセンス]レポートで**、[**アクティブ化**] タブを選択します。

2. Power BIの [その他のページ] ボタンから上部の **[編集]** ボタンを![選択して、編集モードに入ります。](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) ボタンをクリックします。

    ![右上のナビゲーションで [レポートの編集] をクリックします。](../../media/e2c16663-1fbd-4d7f-887c-0cbb891d3b3d.png)

3. 右上にある [ **このページを複製する**] を選択します。

    ![[このページを複製する] を選択します。](../../media/b2d18dcd-6b82-4ce7-ab79-1b24e3721309.png)

4. 右下で、Android、iOS、Mac などの OS に基づいてアクティブ化しているユーザーの数を示す横棒グラフのいずれかを選択します。

5. 右側の **[視覚化]** 領域で、ビジュアルから **Mac カウント** を削除するには、その横にある **[X** ] を選択します。

    ![Mac カウントを削除します。](../../media/ce3d8358-df57-4f64-bd25-ac5be7fc8713.png)

### <a name="create-a-new-visual"></a>新しいビジュアルを作成する

次の例は、新しい Yammer ユーザーを月単位で追跡記録する新しいビジュアルの作成方法を示しています。

1. 左側のナビゲーションを使用して **製品使用状況** レポートに移動し、**Yammer** タブを選択します。

2. Power BIで [その他のページ] ボタンを![選択して、編集モードに切り替えます。](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) と **編集** します。

3. ページの下部にある ![Power BIの [ページの追加] ボタン。](../../media/d3b8c117-17d4-4f53-b078-8fefc2155b24.png) をクリックして新しいページを作成します。

4. 右側の **[視覚化]** 領域で、 **積み上げ横棒グラフ** (最初の行は左から) を選択します。

    ![横棒グラフを選択します。](../../media/214c3fed-6eae-43e6-83fb-708a2d74406e.png)

5. その視覚化の右下を選択し、ドラッグして大きくします。

6. 右側の **[フィールド]** 領域で、[ **予定表** ] テーブルを展開します。

7. [ **MonthName**] を [フィールド] 領域までドラッグします。[ **視覚エフェクト**] 領域の [ **軸**] 見出しのすぐ下にあります。

    ![月の名前をドラッグします。](../../media/bff99987-8c4b-4618-89fd-47df557b0ed7.png)

8. 右にある [ **フィールド**] 領域の [ **TenantProductUsage**] テーブルを展開します。

9. [ **FirstTimeUsers**] を [フィールド] 領域までドラッグします。[ **値**] 見出しのすぐ下にあります。

10. [ **Product**] を [ **フィールド**] 領域までドラッグします。[ **ビジュアル レベル フィルター**] 見出しのすぐ下にあります。

11. [ **フィルターの種類**] 領域が表示されたら、[ **Yammer**] チェック ボックスを選択します。

    ![[Yammer] チェック ボックスをオンにします。](../../media/82e99730-0de9-42da-928a-76aab0c3e609.png)

12. 視覚化の一覧のすぐ下にある [視覚化] の [**書式**] アイコンPower BI [書式] アイコン![を](../../media/ee0602f3-3df5-4930-b862-db1d90ae4ae2.png)選択します。

13. [タイトル] を展開し、[ **タイトル テキスト**] 値を [ **月別の新規 Yammer ユーザー**] に変更します。

14. [ **テキストのサイズ**] 値を [ **12**] に変更します。

15. 右下のページの名前を編集して、新しいページのタイトルを変更します。

16. 上部の **閲覧ビュー** をクリックしてレポートを保存し、 **保存します**。

## <a name="customizing-the-reports-in-power-bi-desktop"></a>Power BI Desktop のレポートをカスタマイズする

ほとんどのお客様にとっては、Power BI Web のレポートとグラフ ビジュアルを変更すれば十分です。ただし、場合によっては、自社の事業という文脈において深い洞察を得るには、このデータを他のデータ ソースと接続する必要があります。その場合、Power BI デスクトップを利用して追加のレポートをカスタマイズしたり、ビルドしたりできます。[Power BI デスクトップ](https://go.microsoft.com/fwlink/p/?linkid=849797)は無料でダウンロードできます。

### <a name="use-the-reporting-apis"></a>レポート API を使用する

まず、これらのレポートを有効にするMicrosoft 365から ODATA レポート API に直接接続します。

1. Go to **get data** \> **Other** \> **ODATA Feed** \> **Connect**.

2. URL ウィンドウに「https://<i></i> reports.office.com/pbi/v1.0/\<tenantid\>」と入力します。

    **メモ：** レポート API はプレビュー段階にあり、運用環境に移行するまで変更される可能性があります。

    ![デスクトップの OData フィード URL Power BI。](../../media/c0ef967e-a454-4eba-bc8e-61e113170053.png)

3. Microsoft 365 (組織または学校) 管理者の資格情報を入力して、プロンプトが表示されたらMicrosoft 365に対して認証します。

    Microsoft 365導入テンプレート アプリ レポートへのアクセスが許可されているユーザーの詳細については、[FAQ](usage-analytics.md#faq) を参照してください。

4. 接続が承認されると、[ナビゲーター] ウィンドウが表示されます。このウィンドウに、接続先として利用できるデータセットが表示されます。

    すべて選択し、[ **読み込み**] を選択します。

    これで Power BI デスクトップにデータがダウンロードされます。このファイルを保存すれば、必要なレポートの作成を開始できます。

    ![レポート API で使用できる ODATA 値。](../../media/545b4d17-dbbd-4cfc-b75a-a8b27283d438.png)

### <a name="use-the-microsoft-365-usage-analytics-template"></a>Microsoft 365利用状況分析テンプレートを使用する

また、Microsoft 365使用状況分析レポートに対応するPower BI テンプレート ファイルを開始点として使用して、データに接続することもできます。 pbit ファイルを利用することの長所は、接続文字列が既に確立されていることです。 基本スキーマが返すデータに加え、作成されたあらゆるカスタム メジャーを活用し、基本スキーマの上にさらに構築することもできます。

Power BI テンプレート ファイルは[、Microsoft ダウンロード センターからダウンロード](https://download.microsoft.com/download/7/8/2/782ba8a7-8d89-4958-a315-dab04c3b620c/Microsoft%20365%20Usage%20Analytics.pbit)できます。 Power BI テンプレート ファイルをダウンロードしたら、次の手順に従って作業を開始します。

1. pbit ファイルを開きます。

2. ダイアログにテナント ID 値を入力します。

    ![テナント ID を入力して pbit ファイルを開きます。](../../media/071ed0bf-8b9d-49c6-81fc-fd4c6cc85bd3.png)

3. プロンプトが表示されたら、Microsoft 365に対して認証する管理者資格情報を入力します。

     Microsoft 365使用状況分析レポートへのアクセスを許可されているユーザーの詳細については、以下をご覧ください。

    承認された後に、Power BI ファイルのデータが更新されます。

    データの読み込みには時間がかかることがあります。完了後、ファイルを .pbix ファイルとして保存し、レポートのカスタマイズを続けたり、このレポートにデータ ソースを追加したりできます。

4. レポートを作成する方法、Power BI サービスにレポートを公開する方法、組織と共有する方法を理解するには、「[Getting started with Power BI](/power-bi/fundamentals/desktop-getting-started)」 (Power BI を始める) ドキュメントをご覧ください。この方法でカスタマイズと共有を行う場合、追加の Power BI ライセンスが必要になることがあります。詳細については、Power BI の[ライセンスに関するページ](https://go.microsoft.com/fwlink/p/?linkid=849803)を参照してください。
