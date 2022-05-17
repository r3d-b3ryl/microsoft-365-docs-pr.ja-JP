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
description: 一元化されたアドインを使用して、組織内のユーザーとグループにアドインを展開する方法について説明します。
ms.openlocfilehash: ec972cd8ce837ae21384bc3b97513bd1263a7d84
ms.sourcegitcommit: 9255a7e8b398f92d8dae09886ae95dc8577bf29a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2022
ms.locfileid: "65435437"
---
# <a name="manage-add-ins-in-the-microsoft-365-admin-center"></a>Microsoft 365 管理センターでアドインを管理する

Office アドインは、ドキュメントをカスタマイズし、Web 上の情報にアクセスする方法を合理化するのに役立ちます。 [「Office アドインの使用を開始](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)する」を参照してください。 

管理者が組織内のユーザーのアドインを展開した後、管理者はアドインをオフまたはオンにしたり、アドインへのアクセスを編集、削除、管理したりできます。

管理センターからのアドインのインストールの詳細については、「管理センター [にアドインを展開する](./manage-deployment-of-add-ins.md)」を参照してください。
  
## <a name="add-in-states"></a>アドインの状態

アドインは **、[オン] または [****オフ]** の状態にすることができます。
  
| 状態 | 状態が発生する原因 | 影響 |
|:-----|:-----|:-----|
|**アクティブ**  <br/> |管理者がアドインをアップロードし、ユーザーまたはグループに割り当てた。  <br/> |アドインを割り当てられたユーザーやグループは、関連するクライアントでアドインを表示します。  <br/> |
|**オフ**  <br/> |管理者がアドインをオフにした。  <br/> |アドインを割り当てられたユーザーやグループは、そのアドインにアクセスできません。  <br/> アドインの状態が [アクティブ] に変更されると、ユーザーやグループはもう一度アクセスできるようになります。  <br/> |
|**Deleted**  <br/> |管理者がアドインを削除した。  <br/> |アドインを割り当てられたユーザーやグループは、そのアドインにアクセスできません。  <br/> |
   
アドインを使用しなくなった場合は、アドインを削除することを検討してください。 たとえば、アドインを無効にすると、その年の特定の時間帯にのみアドインが使用される場合に意味がある場合があります。

## <a name="delete-an-add-in"></a>アドインを削除する

展開されたアドインを削除できます。

1. 管理センターで、**設定** > **Integrated アプリ** ページに移動します。

2. 展開されたアドインを選択してから、**[構成]** タブを選択します。

3. **[構成]** ウィンドウで、[**Advanced 設定** > **Add-ins**] に移動します。

4. リストからアドインを再度選択します。

5. **[アドインの削除]** を選択します。 右下隅にある [アドイン] ボタンを削除します。

6. 選択内容を確認し、**[削除]** を選択します。

## <a name="edit-add-in-access"></a>アドインのアクセスを編集する

展開後、管理者はアドインへのユーザー アクセスを管理することもできます。

1. 管理センターで、**設定** > **Integrated アプリ** ページに移動します。

2. 展開されたアドインを選択します。

3. **[アクセス権を持つユーザー]** の下の **[編集]** をクリックします。

4. 変更を保存します。

## <a name="prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook"></a>すべてのクライアントでOffice Microsoft Storeをオフにしてアドインのダウンロードを防止する (Outlookを除く)

> [!NOTE]
> アドインのインストールOutlookは、[別のプロセス](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/specify-who-can-install-and-manage-add-ins)によって管理されます。

組織として、Office Microsoft Storeからの新しいOffice アドインのダウンロードを禁止することができます。 これを一元展開と組み合わせて使用すると、組織内のユーザーに組織で承認されたアドインのみが確実に展開されます。
  
**アドインの取得を無効にするには**
  
1. 管理センターで、**[設定]** \> [[組織の設定]](https://go.microsoft.com/fwlink/p/?linkid=2053743) のページの順に移動します。

2. **[ユーザー所有のアプリとサービス]** を選びます。
    
3. ユーザーが Office ストアにアクセスできるようにするオプションをオフにします。

    これにより、すべてのユーザーがストアから次のアドインを取得できなくなります。
      
    - Word、Excel、および PowerPoint 2016 のアドイン:
        
      - Windows
      - Mac
      - 事業所
        
        
    - **AppSource** 内で開始される取得
        
    - Microsoft 365 内のアドイン
        
    ストアへのアクセスを試みるユーザーには **、Office Microsoft Store アドインの個別の取得を防ぐために、申し訳ありませんMicrosoft 365が構成されているというメッセージが表示されます。**
  
Office Microsoft Storeを無効にするためのサポートは、次のバージョンで使用できます。
  
- Windows: 16.0.9001 - 現在利用可能です。
    
- Mac: 16.10.18011401 - 現在利用可能です。
    
- iOS: 2.9.18010804 - 現在利用可能です。
    
- Web - 現在利用可能です。
    
これにより、管理者が一元展開を使用してOffice Microsoft Storeからアドインを割り当てることができなくなります。

> [!NOTE] 
> Visio データ ビジュアライザー、Bing地図、People Graphなどのアドインは、管理者がMicrosoft Storeを無効にした場合でもリボンに表示されます。 これらのリンクを削除するには、管理者は、グループ ポリシー オブジェクト (GPO) を使用してMicrosoft Storeを無効にする必要があります。
  
ユーザーが Microsoft アカウントでサインインできないようにするには、組織アカウントのみを使用するようにログオンを制限できます。 詳細については、[Office 2016 の ID、認証、および承認に関するOffice参照してください](/DeployOffice/security/identity-authentication-and-authorization-in-office)。  

> [!NOTE] 
> また、ユーザーが Office ストアにアクセスできないようにすると、[ネットワーク共有からテストするためにアドインOfficeサイドローディング](/office/dev/add-ins/testing/create-a-network-shared-folder-catalog-for-task-pane-and-content-add-ins)できなくなります。

## <a name="more-about-the-end-user-experience-with-add-ins"></a>アドインを使用したエンド ユーザー エクスペリエンスの詳細

アドインをデプロイすると、エンド ユーザーは自分のOffice アプリケーションでアドインの使用を開始できます。 アドインは、アドインがサポートするすべてのプラットフォームに表示されます。 [「Office アドインの使用を開始](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)する」を参照してください。 
  
アドインがアドイン コマンドをサポートする場合、そのコマンドは Office のリボンに表示されます。次の例では、[ **引用の検索** ] コマンドが [ **引用** ] アドインで表示されています。 

![検索引用文献を含むリボンをOfficeします。](../../media/553b0c0a-65e9-4746-b3b0-8c1b81715a86.png)
  
展開されたアドインがアドイン コマンドをサポートしていない場合、または展開されたすべてのアドインを表示する場合は、 **マイ アドイン** を使用して表示できます。 
  
### <a name="in-word-2016-excel-2016-or-powerpoint-2016"></a>Word 2016、Excel 2016、または PowerPoint 2016

1. [**アドインの挿入\>**] を選択します。 
    
2. Office アドイン ウィンドウの [ **管理による管理者** ] タブを選択します。 
    
3. 前にデプロイしたアドイン (この例では **引用文献**) をダブルクリックします。

    ![[Office アドイン] ページの [管理者管理] タブ。](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)
  
### <a name="in-outlook"></a>Outlook

1. **[ホーム**] リボンで、[**アドインの取得**] を選択します。

    ![Outlookの [Microsoft Store] ボタンをクリックします。](../../media/getaddinsicon.png)
  
2. 左側のナビゲーションで、**[管理者が管理]** を選びます。 

## <a name="related-content"></a>関連コンテンツ

[未成年者とアドインをMicrosoft Storeから取得する](./minors-and-acquiring-addins-from-the-store.md)

