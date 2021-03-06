---
title: 管理センターでアドインを管理する
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
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: 集中型アドインを使用して組織内のユーザーとグループにアドインを展開する方法について学習します。
ms.openlocfilehash: b888c0f329e3f1f36f5aa566df7efbab07cd1f5f
ms.sourcegitcommit: a6b998fef5bdb35ec6726c743a24fea721535fcd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2021
ms.locfileid: "50509136"
---
# <a name="manage-add-ins-in-the-admin-center"></a>管理センターでアドインを管理する

::: moniker range="o365-21vianet"

> [!NOTE]
> 管理センターは変更中です。 エクスペリエンスがここで説明されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true)」を参照してください。

::: moniker-end

Officeアドインを使用すると、ドキュメントをカスタマイズし、Web 上の情報にアクセスする方法を合理化できます (「Office アドインの使用を開始する」を [参照してください](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862))。 

管理者が組織内のユーザーにアドインを展開した後、管理者はアドインをオフまたはオン、編集、削除、およびアドインへのアクセスを管理できます。

管理センターからのアドインのインストールの詳細については、「管理センターでアドインを展開する」 [を参照してください](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)。
  
## <a name="add-in-states"></a>アドインの状態

アドインは[オン]または **[オフ]** のいずれかの状態 **にできます** 。
  
|**状態**|**状態が発生する原因**|**影響**|
|:-----|:-----|:-----|
|**Active**  <br/> |管理者はアドインをアップロードし、ユーザーまたはグループに割り当てしました。  <br/> |アドインを割り当てられたユーザーやグループは、関連するクライアントでアドインを表示します。  <br/> |
|**オフ**  <br/> |管理者がアドインをオフにした。  <br/> |アドインを割り当てられたユーザーやグループは、そのアドインにアクセスできません。  <br/> アドインの状態が [アクティブ] に変更されると、ユーザーやグループはもう一度アクセスできるようになります。  <br/> |
|**Deleted**  <br/> |管理者がアドインを削除した。  <br/> |アドインを割り当てられたユーザーやグループは、そのアドインにアクセスできません。  <br/> |
   
アドインを使用しているユーザーがいない場合は、削除を検討してください。 たとえば、一年の特定の期間中にのみアドインを使用する場合は、アドインをオフにしてください。

## <a name="delete-an-add-in"></a>アドインを削除する

展開されたアドインを削除できます。

1. 管理センターで、[アドイン **の設定**  >  **サービス] &に移動** します。

     > [!NOTE]
    > 管理センターは、統合アプリを使用した展開エクスペリエンスに更新されています。 上記の手順が表示されない場合は、[設定] 統合アプリに移動して、[集中展開]  >  **セクションに移動します**。 [統合アプリ] ページ **の上部** で、[アドイン] **を選択します**。

2. 展開されたアドインを選択します。

3. [アドインの **削除] をクリックします**。 右下隅にある [アドイン] ボタンを削除します。

4. 選択内容を確認し、[**アドインの削除]** を選びます。

## <a name="edit-add-in-access"></a>アドインのアクセスを編集する

展開後、管理者はアドインへのユーザー アクセスを管理できます。

1. 管理センターで、[アドイン **の設定**  >  **サービス] &に移動** します。

     > [!NOTE]
    > 管理センターは、統合アプリを使用した展開エクスペリエンスに更新されています。 上記の手順が表示されない場合は、[設定] 統合アプリに移動して、[集中展開]  >  **セクションに移動します**。 [統合アプリ] ページ **の上部** で、[アドイン] **を選択します**。

2. 展開されたアドインを選択します。

3. [アクセス権を **持つユーザー]** **の下の [編集] をクリックします**。

4. 変更を保存します。

## <a name="prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook"></a>すべてのクライアントでアドイン ストアをオフにしてアドインOfficeを防止する (Outlook を除く)

> [!NOTE]
> Outlook アドインのインストールは、別のプロセスによって [管理されます](https://technet.microsoft.com/library/jj943754%28v=exchg.150%29.aspx)。

組織として、新しいアドインを OfficeストアからダウンロードOfficeがあります。 これを集中展開と組み合わせて使用して、組織で承認されたアドインのみを組織内のユーザーに展開できます。
  
**アドインの取得をオフにする**
  
1. 管理センターで、 [**設定**] \> [[サービス&amp;アドイン](https://go.microsoft.com/fwlink/p/?linkid=2053743)] ページの順に移動します。

     > [!NOTE]
    > 管理センターは、統合アプリを使用した展開エクスペリエンスに更新されています。 上記の手順が表示されない場合は、[設定] 統合アプリに移動して、[集中展開]  >  **セクションに移動します**。 [統合アプリ] ページ **の上部** で、[アドイン] **を選択します**。
    
3. **[ユーザー所有のアプリとサービス]** を選びます。
    
4. ユーザーが Office ストアにアクセスできるようにするオプションをオフにします。

これにより、すべてのユーザーがストアから次のアドインを取得できます。
  
- Word、Excel、および PowerPoint 2016 のアドインは、次の場所から使用できます。
    
  - Windows
    
  - Mac
    
  - Office
    
    
- AppSource 内から **始まる取得**
    
- Microsoft 365 内のアドイン
    
ストアにアクセスしようとすると、次のメッセージが表示されます。申し訳ありませんが **、Microsoft 365** は、Office ストア アドインの個別の取得を防止するように構成されています。
  
ストアをオフにOfficeサポートは、次のバージョンで使用できます。
  
- Windows: 16.0.9001 - 現在利用可能です。
    
- Mac: 16.10.18011401 - 現在利用可能です。
    
- iOS: 2.9.18010804 - 現在利用可能です。
    
- Web - 現在利用可能です。
    
これにより、管理者が一元展開を使用してアドインを管理ストアから割り当Officeされません。
  
ユーザーが Microsoft アカウントでサインインを防止するには、組織アカウントのみを使用するログオンを制限できます。 詳細については [、2016 年の ID、](https://technet.microsoft.com/library/jj683102%28v=office.16%29.aspx)認証、および認証Office参照してください。  

> [!NOTE]
> ユーザーが Office ストアにアクセスしなかOfficeアドインをサイドローディング [してテストを行うのも妨げる可能性があります](https://docs.microsoft.com/office/dev/add-ins/testing/create-a-network-shared-folder-catalog-for-task-pane-and-content-add-ins)。

## <a name="more-about-the-end-user-experience-with-add-ins"></a>アドインを使用したエンド ユーザー エクスペリエンスの詳細

アドインを展開すると、エンド ユーザーはアドインを Office アプリケーションで使用できます (「アドインの使用を開始する [Office」を参照してください](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862))。 アドインは、アドインがサポートしているすべてのプラットフォームに表示されます。
  
アドインがアドイン コマンドをサポートする場合、そのコマンドは Office のリボンに表示されます。次の例では、[ **引用の検索** ] コマンドが [ **引用** ] アドインで表示されています。 

![Office付きリボン](../../media/553b0c0a-65e9-4746-b3b0-8c1b81715a86.png)
  
展開されたアドインがアドイン コマンドをサポートしない場合、またはすべての展開されたアドインを表示する場合は、[マイ アドイン] を使用して表示 **できます**。 
  
### <a name="in-word-2016-excel-2016-or-powerpoint-2016"></a>Word 2016、Excel 2016、または PowerPoint 2016

1. [ **アドイン \> の挿入] を選択します**。 
    
2. Office アドイン ウィンドウの [ **管理による管理者** ] タブを選択します。 
    
3. 前に展開したアドインをダブルクリックします (この例では [ **引用文献** ])。 <br/>![[アドイン] ページの [Office管理] タブ](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)
  
### <a name="in-outlook"></a>Outlook

1. [ホーム **] リボンで** 、[ **アドインの取得] を選択します**。<br/>![Outlook の [格納] ボタン](../../media/getaddinsicon.png)
  
2. 左側のナビゲーションで、**[管理者が管理]** を選びます。 

## <a name="learn-more"></a>詳細情報

[管理センターでアドインを展開する](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)

[Office アドイン](https://docs.microsoft.com/office/dev/add-ins/overview/office-add-ins)の作成と構築の詳細情報を表示します。
  
[アドインを管理するには、集中展開 PowerShell コマンドレットを使用します](https://docs.microsoft.com/microsoft-365/enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins)。
  
[トラブルシューティング: アドインが表示されないユーザー](https://docs.microsoft.com/office365/troubleshoot/access-management/user-not-seeing-add-ins)

[未成年者と Microsoft Store からアドインを取得する](https://docs.microsoft.com/microsoft-365/admin/manage/minors-and-acquiring-addins-from-the-store)
