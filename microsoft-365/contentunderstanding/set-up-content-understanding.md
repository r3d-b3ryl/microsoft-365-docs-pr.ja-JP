---
title: SharePoint Syntex の設定
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection: enabler-strategic
search.appverid: MET150
localization_priority: Priority
description: Project Cortex のコンテンツ理解をセットアップする
ms.openlocfilehash: dfbcc8e41a28e3107b58ac6b8d471e3a2a08d036
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087573"
---
# <a name="set-up-sharepoint-syntex"></a>SharePoint Syntex の設定

管理者は、Microsoft 365 管理センターを使用して、[Microsoft SharePoint Syntex](index.md)をセットアップできます。 

事前に、次のことを考慮します。

- Which SharePoint sites will you enable form processing? All of them, some, or select sites?
- 既定のコンテンツセンターの名前を何にしますか?

Microsoft 365管理センターでの最初のセットアップの後でも設定を変更できます。

Prior to setup, make sure to plan for the best way to set up and configure content understanding in your environment. For example, you need to make considerations about the following names of:

- フォームの処理を有効にする SharePoint サイト (すべてのサイト、一部、または選択したサイト)
- コンテンツセンターと、プライマリサイト管理者の名前

## <a name="requirements"></a>要件 

> [!NOTE]
> Microsoft 365 管理センターにアクセスし、コンテンツ認識できるようにするには、グローバル管理者または SharePoint 管理者のアクセス許可が必要です。

管理者は、セットアップ後に選択した設定を変更することができます。また、コンテンツ認識管理設定全体において、Microsoft 365 管理センターの管理設定を理解している必要があります。

## <a name="to-set-up-sharepoint-syntex"></a>SharePoint Syntex の設定

1. Microsoft 365 管理センターで、**[設定]** を選択し、**[ファイルとコンテンツ]** セクションを表示します。

2. **[ファイルとコンテンツ]** セクションで、**[コンテンツを自動的に理解する]** を選択します。<br/>

3. [ **自動化コンテンツ理解世帯** ]の ページで、[ **使用を開始する**] をクリックして、セットアッププロセスを確認します。<br/>

    > [!div class="mx-imgBorder"]
    > ![セットアップを開始する](../media/content-understanding/admin-content-understanding-get-started.png)</br>

4. On the **Configure Form Processing** page, you can choose if you want to let users be able to create form processing models in specific SharePoint document libraries. A menu option will be available in the document library ribbon to **Create a form processing model** in SharePoint document libraries in which it is enabled.
 
     **どの SharePoint ライブラリがフォーム処理モデルを作成するためのオプションを表示するようにするか** については、次を選択できます。</br>
      - **すべての SharePoint ライブラリ** は、組織内のすべての SharePoint ライブラリで使用できるようにします。</br>
      - **[選択したサイトのライブラリのみ]**、使用可能にするサイトを選択するか、最大50サイトのリストをアップロードします。</br>
      - **SharePointライブラリはなし** どのサイトも使用できるようにしたくない場合(セットアップ後に変更できます)。

   > [!div class="mx-imgBorder"]
   > ![フォームの処理を構成する](../media/content-understanding/admin-configforms.png)

   > [!Note]
   > 含まれているサイトを削除しても、そのサイトのライブラリに適用されている既存のモデルには影響しません。また、ドキュメント理解モデルをライブラリに適用する機能もありません。 
    
5. **コンテンツセンターの作成** ページで、ユーザーがドキュメント理解モデルを作成して管理することができるように、SharePoint コンテンツセンターサイトを作成できます。

    1. [**サイト名**] に、コンテンツ センター サイトの名前を入力します。
    
    1. The **Site address** will show the URL for your site, based on what you selected for the site name. If you want to change it, click **Edit**.

       > [!div class="mx-imgBorder"]
       > ![コンテンツ センターを作成する](../media/content-understanding/admin-cu-create-cc.png)</br>

       [**次へ**] を選択します。

6. On the **Review and finish** page, you can look at your selected setting and choose to make changes. If you are satisfied with your selections, select **Activate**.

7. [確認]ページで、 **[完了]** をクリックします。

8. You'll be returned to your **Automate content understanding** page. From this page, you can select **Manage** to make any changes to your configuration settings. 

## <a name="assign-licenses"></a>ライセンスを割り当てる

SharePoint Syntex を構成したら、SharePoint Syntex機能を使用するユーザーにライセンスを割り当てる必要があります。

ライセンスを割り当てる

1. Microsoft 365 管理センターで、**[ユーザー** ]、[**アクティブなユーザー**]の順にクリックします。

2. ライセンスを付与するユーザーを選択し、[ **製品ライセンスの管理**] をクリックします。

3. **[さらに割り当てる]** を選択します。

4. Select **SharePoint Syntex**. Under **Apps**, make sure **Common Data Service for SharePoint Syntex**, **SharePoint Syntex**, and **SharePoint Syntex - SPO type** are all selected.

    > [!div class="mx-imgBorder"]
    > ![Microsoft 365 管理センターの SharePoint Syntex ライセンス](../media/content-understanding/sharepoint-syntex-licenses.png)

5. **[変更の保存]** をクリックします。

## <a name="ai-builder-credits"></a>AI ビルダークレジット

If you have 300 or more SharePoint Syntex licenses for SharePoint Syntex in your organization, you will be allocated one million AI Builder credits. If you have fewer than 300 licenses, you must purchase AI Builder credits in order to use forms processing.

Ai builder の容量は、[ [AI ビルダー電卓](https://powerapps.microsoft.com/ai-builder-calculator)を使用して見積もることができます。

[Power Platform 管理センター](https://admin.powerplatform.microsoft.com/resources/capacity) に移動して、クレジットと使用状況を確認します。

## <a name="see-also"></a>関連項目

[フォーム処理モデルの概要](https://docs.microsoft.com/ai-builder/form-processing-model-overview)

[ステップバイステップ: ドキュメント理解モデルを作成する方法について理解する (ビデオ)](https://www.youtube.com/watch?v=DymSHObD-bg)

