---
title: 管理センターでアドインを管理する
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: 集中型アドインを使用して組織内のユーザーとグループにアドインを展開する方法について学習します。
ms.openlocfilehash: d2d1c4d36bf37ad82ac5c720931146c0dfb2220d
ms.sourcegitcommit: c6a97f2a5b7a41b74ec84f2f62fabfd65d8fd92a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2022
ms.locfileid: "61935839"
---
# <a name="manage-add-ins-in-the-admin-center"></a>管理センターでアドインを管理する

Officeアドインは、ドキュメントをカスタマイズし、Web 上の情報にアクセスする方法を合理化するのに役立ちます。 「[アドインの使用をOfficeする」を参照してください](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)。 

管理者が組織内のユーザーにアドインを展開した後、管理者はアドインをオフまたはオン、編集、削除、およびアドインへのアクセスを管理できます。

管理センターからのアドインのインストールの詳細については、「管理センターでアドインを展開する」 [を参照してください](./manage-deployment-of-add-ins.md)。
  
## <a name="add-in-states"></a>アドインの状態

アドインは[オン]または **[オフ]** のいずれかの状態 **にできます** 。
  
| 状態 | 状態が発生する原因 | 影響 |
|:-----|:-----|:-----|
|**アクティブ**  <br/> |管理者はアドインをアップロードし、ユーザーまたはグループに割り当てしました。  <br/> |アドインを割り当てられたユーザーやグループは、関連するクライアントでアドインを表示します。  <br/> |
|**オフ**  <br/> |管理者がアドインをオフにした。  <br/> |アドインを割り当てられたユーザーやグループは、そのアドインにアクセスできません。  <br/> アドインの状態が [アクティブ] に変更されると、ユーザーやグループはもう一度アクセスできるようになります。  <br/> |
|**Deleted**  <br/> |管理者がアドインを削除した。  <br/> |アドインを割り当てられたユーザーやグループは、そのアドインにアクセスできません。  <br/> |
   
アドインを使用しているユーザーがいない場合は、削除を検討してください。 たとえば、一年の特定の期間中にのみアドインを使用する場合は、アドインをオフにしてください。

## <a name="delete-an-add-in"></a>アドインを削除する

展開されたアドインを削除できます。

1. 管理センターで、[統合アプリ] ページ **設定**  >  **移動** します。

2. 展開されたアドインを選択してから、**[構成]** タブを選択します。

3. [構成 **] ウィンドウ** で、[詳細設定]**設定**  >  **に移動します**。

4. リストからアドインを再度選択します。

5. **[アドインの削除]** を選択します。 右下隅にある [アドイン] ボタンを削除します。

6. 選択内容を確認し、**[削除]** を選択します。

## <a name="edit-add-in-access"></a>アドインのアクセスを編集する

展開後、管理者はアドインへのユーザー アクセスを管理することもできます。

1. 管理センターで、[統合アプリ] ページ **設定**  >  **移動** します。

2. 展開されたアドインを選択します。

3. **[アクセス権を持つユーザー]** の下の **[編集]** をクリックします。

4. 変更を保存します。

## <a name="prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook"></a>すべてのクライアントで Office ストアをオフにしてアドインのダウンロードを防止する (Outlook を除く)

> [!NOTE]
> Outlookアドインのインストールは、別のプロセスによって[管理されます](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/specify-who-can-install-and-manage-add-ins)。

組織として、新しいアドインを OfficeストアからダウンロードOfficeがあります。 これを集中展開と組み合わせて使用して、組織で承認されたアドインのみを組織内のユーザーに展開できます。
  
**アドインの取得をオフにする**
  
1. 管理センターで、**[設定]** \> [[組織の設定]](https://go.microsoft.com/fwlink/p/?linkid=2053743) のページの順に移動します。

2. **[ユーザー所有のアプリとサービス]** を選びます。
    
3. ユーザーが Office ストアにアクセスできるようにするオプションをオフにします。

    これにより、すべてのユーザーがストアから次のアドインを取得できなくなります。
      
    - Word、Excel、および PowerPoint 2016 のアドイン:
        
      - Windows
      - Mac
      - 事業所
        
        
    - AppSource 内から **始まる取得**
        
    - Microsoft 365 内のアドイン
        
    ストアにアクセスしようとすると、次のメッセージが表示されます。申し訳ありませんが、Microsoft 365 は、Office ストア アドインの個別の取得を防止するように **構成されています。**
  
ストアをオフにOfficeサポートは、次のバージョンで使用できます。
  
- Windows: 16.0.9001 - 現在利用可能です。
    
- Mac: 16.10.18011401 - 現在利用可能です。
    
- iOS: 2.9.18010804 - 現在利用可能です。
    
- Web - 現在利用可能です。
    
これにより、管理者が一元展開を使用してアドインを管理ストアから割り当Officeされません。

> [!NOTE] 
> Visio Data Visualizer、Bing地図、People Graph などのアドインは、管理者がストアを無効にした場合でも、リボンに表示されます。 これらのリンクを削除するには、管理者がグループ ポリシー オブジェクト (GPO) を使用してストアを無効にする必要があります。
  
ユーザーが Microsoft アカウントでサインインを防止するには、組織アカウントのみを使用するログオンを制限できます。 詳細については[、「Id、authentication、および authorization in Office 2016」を参照](/DeployOffice/security/identity-authentication-and-authorization-in-office)してください。  

> [!NOTE] 
> ユーザーが Office ストアにアクセスしなかOffice、ネットワーク共有からテストするためにアドインをサイドローディング[する機能も妨げる可能性があります](/office/dev/add-ins/testing/create-a-network-shared-folder-catalog-for-task-pane-and-content-add-ins)。

## <a name="more-about-the-end-user-experience-with-add-ins"></a>アドインを使用したエンド ユーザー エクスペリエンスの詳細

アドインを展開した後、エンド ユーザーは自分のアプリケーションでアドインをOfficeできます。 アドインは、アドインがサポートしているすべてのプラットフォームに表示されます。 「[アドインの使用をOfficeする」を参照してください](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)。 
  
アドインがアドイン コマンドをサポートする場合、そのコマンドは Office のリボンに表示されます。次の例では、[ **引用の検索** ] コマンドが [ **引用** ] アドインで表示されています。 

![Office付きリボンを開きます。](../../media/553b0c0a-65e9-4746-b3b0-8c1b81715a86.png)
  
展開されたアドインがアドイン コマンドをサポートしない場合、またはすべての展開されたアドインを表示する場合は、[マイ アドイン] を使用して表示 **できます**。 
  
### <a name="in-word-2016-excel-2016-or-powerpoint-2016"></a>Word 2016、Excel 2016、または PowerPoint 2016

1. [ **アドイン \> の挿入] を選択します**。 
    
2. Office アドイン ウィンドウの [ **管理による管理者** ] タブを選択します。 
    
3. 前に展開したアドイン (この例では引用) **をダブルクリックします**。

    ![[アドイン] ページの [Office管理] タブ。](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)
  
### <a name="in-outlook"></a>Outlook

1. [ホーム **] リボンで** 、[ **アドインの取得] を選択します**。

    ![[ストア] ボタンをOutlook。](../../media/getaddinsicon.png)
  
2. 左側のナビゲーションで、**[管理者が管理]** を選びます。 

## <a name="related-content"></a>関連コンテンツ

[未成年者とアドインをユーザーから取得Microsoft Store](./minors-and-acquiring-addins-from-the-store.md)

