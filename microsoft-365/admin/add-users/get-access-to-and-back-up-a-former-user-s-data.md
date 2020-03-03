---
title: 元ユーザーのデータにアクセスしてバックアップを作成する
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- SPO_Content
ms.custom:
- MSStore_Link
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: a6f7f9ad-e3f5-43de-ade5-e5a0d7531604
description: ユーザーが組織を離れたときに、従業員のファイルと電子メールを保存する方法について説明します。
ms.openlocfilehash: 3c7a63852ad20fc005f7a0f4e3f909474bda2a3c
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/02/2020
ms.locfileid: "42353198"
---
# <a name="get-access-to-and-back-up-a-former-users-data"></a>元ユーザーのデータにアクセスしてバックアップを作成する


従業員が組織を離れる場合は、データ (ドキュメントと電子メール) にアクセスして、それを確認し、バックアップするか、新しい従業員に提供することをお勧めします。
  
    
## <a name="access-a-former-users-onedrive-documents"></a>以前のユーザーの OneDrive ドキュメントにアクセスする

ユーザーのライセンスを削除してもアカウントを削除しない場合は、ユーザーの OneDrive のコンテンツにアクセスできるようにすることができます。 ユーザーのアカウントを削除した場合、既定では30日間で、以前のユーザーの OneDrive データにアクセスできます。 [削除されたユーザーの OneDrive の保持を設定する方法について説明](/onedrive/set-retention)します。 この時間内に[ユーザーアカウントを復元](/office365/admin/add-users/restore-user)しない場合は、その OneDrive コンテンツが削除されます。 

以前のユーザーの OneDrive ファイルを保持するには、まず自分の OneDrive にアクセスして、保存するファイルを移動します。 

::: moniker range="o365-worldwide"

> [!NOTE]
> 新しい Microsoft 365 管理センターを利用していない場合、[ホーム] ページの上部にある [**新しい管理センターをお試しください**] の切り替えを選択して有効にすることができます。

1. 管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">アクティブなユーザー</a>] の順に選択します。  
    
2. ユーザーを選択します。

3. 右側のウィンドウで、[ **OneDrive**] を選択します。 [**ファイルへのアクセスを取得**] で、[**ファイルへのリンクの作成**] を選択します。

4. リンクを選択して、ファイルの場所を開きます。 ファイルをコンピューターにダウンロードするか、[**移動**] または [**コピー** ] を選択して、自分の OneDrive または共有ライブラリにファイルを移動またはコピーします。 

> [!NOTE]
> 一度に 500 MB のファイルとフォルダーを移動またはコピーすることができます。<br/>
> バージョン履歴があるドキュメントを移動またはコピーすると、最新バージョンのみが移動されます。  

::: moniker-end

::: moniker range="o365-germany"

1. 管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">[アクティブなユーザー]</a> ページの順に移動します。  

2. ユーザーを選択します。

3. 右側のウィンドウで、[ **OneDrive の設定**] を展開し、[**アクセス**] の横にある [ **access ファイル**] を選択します。

4. リンクを選択して、ファイルの場所を開きます。 ファイルをコンピューターにダウンロードするか、[**移動**] または [**コピー** ] を選択して、自分の OneDrive または共有ライブラリにファイルを移動またはコピーします。 

> [!NOTE]
> 一度に 500 MB のファイルとフォルダーを移動またはコピーすることができます。<br/>
> バージョン履歴があるドキュメントを移動またはコピーすると、最新バージョンのみが移動されます。  

::: moniker-end

::: moniker range="o365-21vianet"

1. 管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">[アクティブなユーザー]</a> ページの順に移動します。 

2. ユーザーを選択します。

3. 右側のウィンドウで、[ **OneDrive の設定**] を展開し、[**アクセス**] の横にある [ **access ファイル**] を選択します。

4. リンクを選択して、ファイルの場所を開きます。 ファイルをコンピューターにダウンロードするか、[**移動**] または [**コピー** ] を選択して、自分の OneDrive または共有ライブラリにファイルを移動またはコピーします。  

> [!NOTE]
> 一度に 500 MB のファイルとフォルダーを移動またはコピーすることができます。<br/>
> バージョン履歴があるドキュメントを移動またはコピーすると、最新バージョンのみが移動されます。  

::: moniker-end
    


## <a name="revoke-admin-access-to-a-users-onedrive"></a>ユーザーの OneDrive への管理者アクセスを無効にする

グローバル管理者は、ユーザーの OneDrive のコンテンツにアクセスできるようにすることができますが、不要になった場合はアクセスを削除することをお勧めします。 

::: moniker range="o365-worldwide"

1. グローバル管理者または SharePoint 管理者として、<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">管理センター</a>にサインインします。 

::: moniker-end

::: moniker range="o365-germany"

1. グローバル管理者または SharePoint 管理者として、<a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">管理センター</a>にサインインします。

::: moniker-end

::: moniker range="o365-21vianet"

1. グローバル管理者または SharePoint 管理者として、<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">管理センター</a>にサインインします。

::: moniker-end

   管理センターにアクセスするためのアクセス許可がないことを示すメッセージが表示された場合は、組織の管理者のアクセス許可がありません。

2. 左側のウィンドウで、[**管理センター**] \> [**SharePoint**] の順に選択します。 (場合によっては、管理センターのリストを表示するために **[すべて表示]** を選択する必要があります。)

3. 従来の SharePoint 管理センターが表示された場合は、ページ上部の [**今すぐ起動する**] を選択します。これにより、新しい SharePoint 管理センターが開きます。

4. 左側のウィンドウで、[**その他の機能**] を選択します。

5. [**ユーザープロファイル**] で、[**開く**] を選択します。

6. [**人**] で、[**ユーザープロファイルの管理**] を選択します。

7. ユーザーの名前を入力し、[**検索**] を選択します。

8. ユーザーを右クリックし、[**サイトコレクションの所有者の管理**] を選択します。

9. ユーザーのデータへのアクセスが不要になったユーザーを削除し、[ **OK]** を選択します。

    
## <a name="access-the-outlook-data-of-a-former-user"></a>以前のユーザーの Outlook データにアクセスする

元従業員のメール メッセージ、予定表、タスク、連絡先を保存するには、情報を Outlook データ ファイル (.pst) にエクスポートします。
  
1. Outlook に [元従業員のメールを追加](https://support.office.com/article/6e27792a-9267-4aa4-8bb6-c84ef146101b.aspx)します ([ユーザーのパスワードの再設定](reset-passwords.md)を行えば、自分しか知らないパスワードに設定し直すことができます)。
    
2. Outlook で、[**ファイル**] を選択します。
    
    ![Outlook 2016 のリボンの外観。](../../media/d7f66ed3-9861-4521-b410-e86a58ab15a7.png)
  
3. [**エクスポート&amp; ** \> **インポート/エクスポート**を開く] を選択します。
    
    ![Backstage ビューの [インポート/エクスポート]](../../media/6013919e-d8ce-4902-b7b4-78ff4260a2f8.jpg)
  
4. [**ファイルへエクスポート**] を選択し、[**次へ**] を選択します。
    
    ![インポート/エクスポート ウィンドウの [ファイルへエクスポート] オプション](../../media/458466a0-366b-4fbf-a2db-1919412c6527.jpg)
  
5. [ **Outlook データファイル (.pst)**] を選択し、[**次へ**] を選択します。
    
6. [メールボックス-Ayano Weiler] や [anne@contoso.com] などの名前または電子メールアドレスを選択して、エクスポートするアカウントを選択します。 アカウントのすべての内容 (メール、予定表、連絡先、タスク、メモなど) をエクスポートする場合、[ **サブフォルダーを含む**] チェック ボックスがオンになっていることを確認します。 
    
    > [!NOTE]
    > 一度にエクスポートできるアカウントは 1 つだけです。複数のアカウントをエクスポートする場合は、アカウントがエクスポートされるたびに、上の手順を繰り返します。 
  
    ![一番上のフォルダーが選択され、[サブフォルダーを含む] がオンになった [Outlook データ ファイルのエクスポート] ダイアログ ボックス](../../media/ce36616f-d76d-4ce2-b517-8ac4874e0971.jpg)
  
7. [**次へ**] を選択します。
    
8. [**参照**] を選択して、Outlook データファイル (.pst) の保存場所を選択します。 *ファイル名*を入力し、[ **OK** ] を選択して続行します。 
    
    > [!NOTE]
    > If you've used export before, the previous folder location and file name appear. 別の*ファイル名*を入力してから、 **[OK]** を選択します。 
  
9. 既存の Outlook データ ファイル (.pst) にエクスポートする場合は、[ **オプション**] で、ファイルに既に存在しているアイテムをエクスポートするときの処理を指定します。
    
10. **[完了]** を選択します。
    
Outlook により、エクスポートがすぐに開始されます。ただし、新しい Outlook データ ファイル (.pst) を作成するか、パスワードで保護されたファイルを使う場合を除きます。
  
   - If you're creating an Outlook Data File (.pst), an optional password can help protect the file. [ **Outlook データファイルの作成**] ダイアログボックスが表示されたら、 **[パスワード] ボックスと [** パスワードの**確認**] ボックスに*パスワード*を入力し、[ **OK]** を選択します。 [ **Outlook データファイルのパスワード**] ダイアログボックスで、*パスワード*を入力し、[ **OK**] を選択します。
    
  - パスワードで保護された既存の Outlook データファイル (.pst) にエクスポートする場合は、[ **Outlook データファイルのパスワード**] ダイアログボックスで、*パスワード*を入力し、[ **OK]** を選択します。
    
Outlook 2010 で、[電子メール、連絡先、予定表を outlook の .pst ファイルにエクスポートまたはバックアップ](https://support.office.com/article/14252b52-3075-4e9b-be4e-ff9ef1068f91.aspx)する方法を参照してください。 
  
## <a name="give-another-user-access-to-a-former-users-email"></a>元のユーザーの電子メールに別のユーザーがアクセスできるようにする 

元従業員の電子メールメッセージ、予定表、タスク、および連絡先に別の従業員へのアクセス権を付与するには、別の従業員の Outlook 受信トレイに情報をインポートします。

> [!NOTE]
> また[、以前のユーザーのメールボックスを共有メールボックスに変換](https://docs.microsoft.com/office365/admin/email/convert-user-mailbox-to-shared-mailbox)したり、元[従業員の電子メールを別の従業員に転送](https://docs.microsoft.com/office365/admin/add-users/remove-former-employee#forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox)したりすることもできます。

  
1. Outlook で、[**ファイル** \> ] [エクスポート\>の**インポート/エクスポート**] を**開き&amp; **ます。
    
    これにより、インポート/エクスポート ウィザードが開始されます。
    
2. [**別のプログラムまたはファイルからのインポート**] を選択し、[**次へ**] を選択します。
    
    ![インポート/エクスポート ウィザード](../../media/15cdd674-cd7b-492c-8e93-992cfa890f26.jpg)
  
3. [ **Outlook データファイル (.pst)**] を選択し、[**次へ**] を選択します。
    
4. インポートする .pst ファイルを探して選びます。
    
5. [ **オプション**] で、重複するアイテムの処理方法を選びます。
    
6. [**次へ**] を選択します。
    
7. Outlook データファイル (.pst) にパスワードが割り当てられている場合は、パスワードを入力し、[ **OK]** を選択します。
    
8. アイテムのインポートに関するオプションを設定します。 通常、既定の設定を変更する必要はありません。
    
9. **[完了]** を選択します。
    
> [!TIP]
> Outlook データファイル (.pst) から少数のアイテムのみをインポートまたは復元する場合は、Outlook データファイルを開くことができます。 次に、ナビゲーションウィンドウで、Outlook データファイルフォルダーから既存の Outlook フォルダーにアイテムをドラッグします。 
  
  
## <a name="related-articles"></a>関連記事
[Office 365 から元従業員を削除する](remove-former-employee.md)

[OneDrive アカウントの管理者を追加および削除する](/sharepoint/manage-user-profiles#add-and-remove-admins-for-a-users-onedrive)

[削除された OneDrive を復元する](/onedrive/restore-deleted-onedrive)
  
[OneDrive の保持と削除](/onedrive/retention-and-deletion)
  

