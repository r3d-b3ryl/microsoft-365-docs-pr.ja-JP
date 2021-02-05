---
title: SharePoint Syntex の設定
ms.author: mikeplum
author: MikePlumleyMSFT
ms.reviewer: ssquires
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- enabler-strategic
- m365initiative-syntex
search.appverid: MET150
localization_priority: Priority
description: Project Cortex のコンテンツ理解をセットアップする
ms.openlocfilehash: 0e5b48bab343f887a1438386bfa4f7915126ccd7
ms.sourcegitcommit: c0cfb9b354db56fdd329aec2a89a9b2cf160c4b0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2021
ms.locfileid: "50094711"
---
# <a name="set-up-sharepoint-syntex"></a>SharePoint Syntex の設定

管理者は、Microsoft 365 管理センターを使用して、[Microsoft SharePoint Syntex](index.md)をセットアップできます。 

事前に、次のことを考慮します。

- どの SharePoint サイトでフォームの処理を有効にできますか? これらのすべて、それともサイトのいくつかを選択しますか?
- 既定のコンテンツ センターの名前を何にしますか?

Microsoft 365管理センターでの最初のセットアップの後でも設定を変更できます。

設定する前に、使用している環境のコンテンツ解釈をセットアップして構成する最適な方法を計画してください。 たとえば、以下について決定を行う必要があります。

- フォームの処理を有効にする SharePoint サイト (すべてのサイト、一部、または選択したサイト)
- コンテンツ センターの名前と管理者

## <a name="requirements"></a>要件 

> [!NOTE]
> Microsoft 365 管理センターにアクセスし、SharePoint Syntex をセットアップするには、グローバル管理者または SharePoint 管理者のアクセス許可が必要です。

管理者は、セットアップ後に選択した設定を変更することができます。また、コンテンツ認識管理設定全体において、Microsoft 365 管理センターの管理設定を理解している必要があります。

## <a name="to-set-up-sharepoint-syntex"></a>SharePoint Syntex の設定

1. Microsoft 365 管理センターで、**[設定]** を選択し、**[ファイルとコンテンツ]** セクションを表示します。

2. **[ファイルとコンテンツ]** セクションで、**[コンテンツを自動的に理解する]** を選択します。<br/>

3. [ **自動化コンテンツ理解世帯** ]の ページで、[ **使用を開始する**] をクリックして、セットアッププロセスを確認します。<br/>

    > [!div class="mx-imgBorder"]
    > ![セットアップを開始する](../media/content-understanding/admin-content-understanding-get-started.png)</br>

4. [ **フォーム処理の構成**] ページで、特定の SharePoint ドキュメントライブラリにユーザーがフォーム処理モデルを作成できるようにするかどうかを選択できます。 ドキュメントライブラリのリボンには、メニューオプションが用意されています。これを有効にしている SharePoint ドキュメントライブラリで  **フォーム処理モデルを作成** します。
 
     **どの SharePoint ライブラリがフォーム処理モデルを作成するためのオプションを表示するようにするか** については、次を選択できます。</br>
      - **すべての SharePoint サイトのライブラリ** は、組織内のすべての SharePoint ライブラリで使用できるようにします。</br>
      - **選択した SharePoint サイトのライブラリ** は、使用可能にするサイトを選択するか、最大 50 件のサイトのリストをアップロードします。</br>
      - **SharePointライブラリはなし** どのサイトも使用できるようにしたくない場合(セットアップ後に変更できます)。

   > [!div class="mx-imgBorder"]
   > ![フォームの処理を構成する](../media/content-understanding/admin-configforms.png)

   > [!Note]
   > 含まれているサイトを削除しても、そのサイトのライブラリに適用されている既存のモデルには影響しません。また、ドキュメント理解モデルをライブラリに適用する機能もありません。 
    
5. **コンテンツセンターの作成** ページで、ユーザーがドキュメント理解モデルを作成して管理することができるように、SharePoint コンテンツセンターサイトを作成できます。

    1. [**サイト名**] に、コンテンツ センター サイトの名前を入力します。
    
    1. [ **サイトアドレス** には、サイト名に選択した内容に基づいて、サイトの URL が表示されます。 変更する場合は、[ **編集**] をクリックします。

       > [!div class="mx-imgBorder"]
       > ![コンテンツ センターを作成する](../media/content-understanding/admin-cu-create-cc.png)</br>

       [**次へ**] を選択します。

6. [ **確認と完了**] ページで、選択した設定を確認して、変更を行うことができます。 選択内容に問題がない場合は、[**ライセンス認証**]を行います。

7. [確認]ページで、 **[完了]** をクリックします。

8. **コンテンツ理解の自動作成** ページに戻ります。 このページでは、[ **管理** ] を選択して、構成設定に変更を加えることができます。 

## <a name="assign-licenses"></a>ライセンスを割り当てる

SharePoint Syntex を構成したら、SharePoint Syntex機能を使用するユーザーにライセンスを割り当てる必要があります。

ライセンスを割り当てる

1. Microsoft 365 管理センターで、**[ユーザー** ]、[**アクティブなユーザー**]の順にクリックします。

2. ライセンスを付与するユーザーを選択し、[ **製品ライセンスの管理**] をクリックします。

3. [**もっと割り当てる**] を選択します。

4. **[SharePoint Syntex]** を選択します。 **[アプリ]** で、**Common Data Service for SharePoint Syntex**、**SharePoint Syntex**、**SharePoint Syntex - SPO type** がすべて選択されていることを確認します。

    > [!div class="mx-imgBorder"]
    > ![Microsoft 365 管理センターの SharePoint Syntex ライセンス](../media/content-understanding/sharepoint-syntex-licenses.png)

5. **[変更の保存]** をクリックします。

## <a name="ai-builder-credits"></a>AI ビルダークレジット

組織に300以上のSharePoint Syntex用 SharePoint Syntexライセンスがある場合は、100万のAI Builder クレジットが割り当てられます。 ライセンス数が300未満の場合、フォーム処理を使用するには、AI ビルダークレジットを購入する必要があります。

Ai builder の容量は、[ [AI ビルダー電卓](https://powerapps.microsoft.com/ai-builder-calculator)を使用して見積もることができます。

[Power Platform 管理センター](https://admin.powerplatform.microsoft.com/resources/capacity) に移動して、クレジットと使用状況を確認します。

## <a name="see-also"></a>関連項目

[フォーム処理モデルの概要](https://docs.microsoft.com/ai-builder/form-processing-model-overview)

[ステップバイステップ: ドキュメント理解モデルを作成する方法について理解する (ビデオ)](https://www.youtube.com/watch?v=DymSHObD-bg)
