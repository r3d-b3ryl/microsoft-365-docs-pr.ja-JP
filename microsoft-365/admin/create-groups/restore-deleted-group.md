---
title: 削除済みの Office 365 グループを復元する
ms.reviewer: arvaradh
f1.keywords:
- CSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b7c66b59-657a-4e1a-8aa0-8163b1f4eb54
description: 'Exchange 管理センターを使用して、削除された Office 365 グループを復元する方法について説明します。 '
ms.openlocfilehash: c88f10df27e5f3a0af79c93c7d0e347c5646abc9
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/02/2020
ms.locfileid: "42352438"
---
# <a name="restore-a-deleted-office-365-group"></a>削除済みの Office 365 グループを復元する

Office 365 グループの所有者である場合は、次の手順に従って自分でグループを復元できます。

1. [[削除さ](https://outlook.office.com/people/group/deleted)れたグループ] ページで、[**グループ**] ノードの下の [**グループの管理**] オプションを選択し、[**削除済み**] を選択します。
2. 復元するグループの横にある [**復元**] タブをクリックします。

削除されたグループがここに表示されない場合は、管理者に問い合わせてください。
  
Office 365 グループの復元を希望するユーザーの場合は、管理者に依頼してこれらの手順を実行するか、ヘルプデスクにお問い合わせください。  
   
グループを削除した場合、既定では30日間保持されます。 この30日の期間は、引き続きグループを復元できるため、"ソフト削除" と見なされます。 30日後、グループとそれに関連するコンテンツは完全に削除され、復元することはできません。
  
"削除" という期間の間、ユーザーがサイトにアクセスしようとすると、404の_禁止_メッセージが表示されます。 この期間が過ぎると、ユーザーがサイトにアクセスしようとすると、404_見つかりません_メッセージが表示されます。
  
グループを復元すると、次のコンテンツが復元されます。
  
- Azure Active Directory (AD) Office 365 のグループオブジェクト、プロパティ、およびメンバー。
    
- グループの電子メールアドレス。
    
- Exchange Online の共有の受信トレイと予定表。
    
- SharePoint Online チームサイトとファイル。
    
- OneNote ノートブック
    
- Planner
    
- Teams

- Yammer グループおよびグループコンテンツ (Yammer から Office 365 グループが作成されている場合)
    
コンテンツの保持期限の 30 日間が経過してから完全に削除されるまで待てない場合、[Office 365 グループを完全に削除する](#permanently-delete-an-office-365-group)こともできます。 

> [!NOTE]
> 削除された Office 365 グループの所有者は、グループを復元することもできます。 管理者権限のない所有者アクセス許可を使用して office 365 グループを復元するには、「 [PowerShell を使用して office 365 グループを復元](#restore-an-office-365-group-using-powershell)する」を参照してください。

## <a name="restore-an-office-365-group-using-the-exchange-admin-center"></a>Exchange 管理センターを使用して Office 365 グループを復元する

Office 365 グローバル管理者のアクセス許可を持っている必要があります。

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 管理センター</a>に移動します。
    
2. Exchange 管理センターで、[ **受信者**]、[ **グループ**] の順に選びます。 グループがアクティブであるか、または削除されているかを表示できます。 グループが完全に削除された場合、グループはまったく表示されません。
  
3. グループがソフト削除された正確な時間を表示するには、グループを選択して、右側のウィンドウに情報を表示します。
      
4. 復元するグループを選択し、[復元] アイコンを選択します。
    
    ![復元するグループを選択し、[復元] アイコンを選択します。](../../media/restore-group.png)
  
5. [更新] を選択します。 ![[更新] アイコン](../../media/6464df90-2a91-4c1f-92a6-9a38c7696ac3.gif) を選んで、ページの情報を更新します。 使用しているグループは、"アクティブ" として表示されます。 グループに関連付けられているフォームおよびフォームデータも復元されます。
    
## <a name="restore-an-office-365-group-using-powershell"></a>PowerShell を使用して Office 365 グループを復元する

Office 365 グローバル管理者のアクセス許可を持っているか、または削除された Office 365 グループの以前の所有者である必要があります。

> [!IMPORTANT]
> PowerShell で MsolGroup を使用してグループを削除した場合、グループは完全に削除されます。 PowerShell を使用してグループを削除する場合は、 **Remove-AzureADMSGroup** を使用して Office 365 グループを論理的に削除することをお勧めします。 そうすれば、必要に応じて、復元することができます。 
  
### <a name="install-the-preview-version-of-the-azure-active-directory-powershell-for-graph"></a>Graph 用 Azure Active Directory PowerShell のプレビュー バージョンをインストールする

> [!IMPORTANT]
> 同じコンピューターにプレビュー バージョンと GA バージョンの両方を同時にインストールすることはできません。
  
ベストプラクティスとして、*常に*最新の状態を維持することをお勧めします。つまり、old AzureADPreview または old AzureAD version をアンインストールし、最新のバージョンを取得することをお勧めします。 
  
 
1. 検索バーに「Windows PowerShell」と入力します。
    
2. **[Windows PowerShell]** を右クリックし、**[管理者として実行]** を選択します。
  
2. インストールされているモジュールを確認します。
    
  ```
  Get-InstalledModule -Name "AzureAD*"
  ```

3. AzureADPreview または AzureAD の以前のバージョンをアンインストールするには、次のコマンドを実行します。
  
```
   Uninstall-Module AzureADPreview
```

または
  
```
   Uninstall-Module AzureAD
```

4. AzureADPreview の最新のバージョンをインストールするには、次のコマンドを実行します。
  
```
   Install-Module AzureADPreview
```



信頼されていないリポジトリに関するメッセージに対して「**Y**」と入力します。新しいモジュールのインストールには 1 分ほどかかります。
  
### <a name="restore-the-deleted-group"></a>削除したグループを復元する
  
1. Previoius セクション「Windows PowerShell 用 Azure Active Directory モジュールのプレビューバージョンをインストールする」に記載されているように、 **AzureADPreview**モジュールをインストールしましたか?  Not having the most current **preview** version is the #1 reason these steps don't work for people. 
    
2. まだ開いていない場合は、コンピューターで Windows PowerShell ウィンドウを開きます (標準の Windows PowerShell ウィンドウか、[ **管理者として実行**] を選択して開いたウィンドウかは関係ありません)。
    
3. 各コマンドの後に**enter**キーを押して、次のコマンドを実行します。 
    
  ```
  Import-Module AzureADPreview
  ```

  ```
  Connect-AzureAD
  ```



  開いている [**アカウントにサインインする**] 画面に、Azure AD サービスに接続するための管理者アカウントのユーザー名とパスワードを入力し、[**サインイン**] を選択します。
  
4. 次のコマンドを実行して、組織内の回復可能な削除によって削除されたすべての Office 365 グループを、まだ30日の回復可能な削除期間内に表示します。
    
  ```
  Get-AzureADMSDeletedGroup
  ```

5. 復元する 1 つまたは複数のグループのオブジェクト ID をメモします。 このリストに含まれているグループが表示されていない場合は、既に完全に削除されている可能性があります。
    
    > [!CAUTION]
    > 削除したグループと同じエイリアスまたは SMTP アドレスを持つ新しいグループが作成されている場合、削除したグループを復元するには、その新しいグループを事前に削除しておく必要があります。 
  
6. そのグループを復元するには、次のコマンドを実行します。
    
  ```
  Restore-AzureADMSDeletedDirectoryObject -Id <objectId>
  ```

7. 通常、この処理には数分しかかかりませんが、ほとんどの場合、完全に復元するまでに24時間かかることがあります。 グループが正常に復元されたことを確認するには、PowerShell で次のコマンドを実行します。
    
  ```
  Get-AzureADGroup -ObjectId <objectId>
  ```

復元が正常に完了すると、Outlook および Outlook on the web のナビゲーション ウィンドウにグループが再び表示されます。SharePoint や Planner などの復元されたすべてのコンテンツをグループ メンバーが再び利用できるようになります。
  
## <a name="permanently-delete-an-office-365-group"></a>Office 365 グループを完全に削除する

場合によっては、30日間のソフト削除期間が経過するのを待たずに、グループを完全に削除する必要があります。 それを行うには、PowerShell を起動し、次のコマンドを実行して、グループのオブジェクト ID を取得します。
  
```
Get-AzureADMSDeletedGroup
```

完全に削除するグループまたはグループのオブジェクト ID を書き留めておきます。
  
> [!CAUTION]
> グループを削除すると、グループとそのデータが永久に削除されます。 
  
グループを削除するには、PowerShell で次のコマンドを実行します。
  
```
Remove-AzureADMSDeletedDirectoryObject -Id <objectId>
```

グループが正常に削除されたことを確認するには、 *Get AzureADMSDeletedGroup*  コマンドレットをもう一度実行して、グループが論理的に削除されたグループの一覧に表示されなくなったことを確認します。グループとそのすべてのデータが完全に削除されるまで 24 時間ほどかかる場合があります。 
  
## <a name="got-questions-about-office-365-groups"></a>Office 365 についてご質問がある場合

[Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups)を参照して、Office 365 グループに関する質問を投稿し、会話に参加してください。 
  
## <a name="related-articles"></a>関連記事

[PowerShell で Office 365 グループを管理する](https://support.office.com/article/aeb669aa-1770-4537-9de2-a82ac11b0540)
  
[Remove-UnifiedGroup コマンドレットを使用してグループを削除する](https://technet.microsoft.com/library/mt238270%28v=exchg.160%29.aspx)
  
[グループに接続されたチーム サイトの設定を管理する](https://support.office.com/article/8376034d-d0c7-446e-9178-6ab51c58df42.aspx)
  
[Outlook でグループを削除する](https://support.office.com/article/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f.aspx)
