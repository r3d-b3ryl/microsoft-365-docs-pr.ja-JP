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
description: 管理センターで一元展開を使用して、組織内のユーザーとグループにアドインを展開する方法について説明します。
ms.openlocfilehash: caaea8404c099f56704d21684323a4b20e61f52d
ms.sourcegitcommit: 222fc3f8841de82b1b558f47db8a79aa5054d0ed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/11/2020
ms.locfileid: "45103101"
---
# <a name="manage-add-ins-in-the-admin-center"></a>管理センターでアドインを管理する

::: moniker range="o365-21vianet"

> [!NOTE]
> 管理センターは変更されました。 エクスペリエンスがここで説明されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)」を参照してください。

::: moniker-end

Office アドインは、ドキュメントをカスタマイズしたり、web 上の情報にアクセスする方法を合理化したりするのに役立ちます (「 [office アドインの使用を開始](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)する」を参照してください)。 

管理者が組織内のユーザーに対してアドインを展開した後、管理者はアドインのオン/オフ、編集、削除、およびアドインへのアクセスの管理を行うことができます。

管理センターからのアドインのインストールの詳細については、「[管理センターで](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)のアドインの展開」を参照してください。
  
## <a name="add-in-states"></a>アドインの状態

アドインは、 **[オン**] または [**オフ**] のどちらかの状態にすることができます。
  
|**状態**|**状態が発生する原因**|**影響**|
|:-----|:-----|:-----|
|**Active**  <br/> |管理者がアドインをアップロードし、ユーザーまたはグループに割り当てました。  <br/> |アドインを割り当てられたユーザーやグループは、関連するクライアントでアドインを表示します。  <br/> |
|**オフ**  <br/> |管理者がアドインをオフにした。  <br/> |アドインを割り当てられたユーザーやグループは、そのアドインにアクセスできません。  <br/> アドインの状態が [アクティブ] に変更されると、ユーザーやグループはもう一度アクセスできるようになります。  <br/> |
|**Deleted**  <br/> |管理者がアドインを削除した。  <br/> |アドインを割り当てられたユーザーやグループは、そのアドインにアクセスできません。  <br/> |
   
アドインを使用していない場合は、削除することを検討してください。 たとえば、特定の時間帯にのみアドインが使用されている場合、アドインをオフにしても意味があります。

## <a name="delete-an-add-in"></a>アドインを削除する

展開されたアドインを削除することもできます。

1. 管理センターで、[**設定**  >  **サービス & アドイン**] ページに移動します。

2. 展開されたアドインを選択します。

3. [**アドインの削除**] をクリックします。 右下隅にある [アドイン] ボタンを削除します。

4. 選択内容を確認し、[**アドインの削除]** を選びます。

## <a name="edit-add-in-access"></a>アドインのアクセスを編集する

展開後、管理者はアドインへのユーザーアクセスを管理することもできます。

1. 管理センターで、[**設定**  >  **サービス & アドイン**] ページに移動します。

2. 展開されたアドインを選択します。

3. [**アクセスできるユーザー**] の [**編集**] をクリックします。

4. 変更を保存します。

## <a name="prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook"></a>すべてのクライアント (Outlook を除く) で Office ストアをオフにして、アドインのダウンロードを禁止する

> [!NOTE]
> Outlook アドインのインストールは、[別のプロセス](https://technet.microsoft.com/library/jj943754%28v=exchg.150%29.aspx)で管理されます。

組織の場合は、Office ストアから新しい Office アドインをダウンロードできないようにする必要があります。 これを一元展開と組み合わせて使用することにより、組織内のユーザーが組織内の承認済みアドインのみを展開するようにすることができます。
  
**アドインの取得を無効にするには**
  
1. 管理センターで、 [**設定**] \> [[サービス&amp;アドイン](https://go.microsoft.com/fwlink/p/?linkid=2053743)] ページの順に移動します。
    
3. **[ユーザー所有のアプリとサービス]** を選びます。
    
4. ユーザーが Office ストアにアクセスできるようにするオプションをオフにします。

これにより、すべてのユーザーがストアから次のアドインを取得するのを防ぐことができます。
  
- Word、Excel、PowerPoint 2016 用のアドインは次のとおりです。
    
  - Windows
    
  - Mac
    
  - Office
    
    
- **Appsource**内からの取得
    
- Microsoft 365 内のアドイン
    
ストアにアクセスしようとするユーザーには、次のメッセージが表示されます。**申し訳ございません。 Microsoft 365 は、Office ストアアドインの個別の取得を防止するように構成されています。**
  
Office ストアの無効化のサポートは、次のバージョンで利用できます。
  
- Windows: 16.0.9001-現在使用可能です。
    
- Mac: 16.10.18011401-現在利用可能です。
    
- iOS: 2.9.18010804-現在使用可能です。
    
- Web は現在利用できます。
    
これにより、管理者は一元展開を使用して Office ストアからアドインを割り当てることができます。
  
ユーザーが Microsoft アカウントでサインインできないようにするには、組織のアカウントのみを使用するようにログオンを制限することができます。 詳細については、「 [Office 2016 の id、認証、および承認](https://technet.microsoft.com/library/jj683102%28v=office.16%29.aspx)」を参照してください。  

## <a name="more-about-the-end-user-experience-with-add-ins"></a>アドインを使用したエンドユーザーの作業の詳細

アドインを展開すると、エンドユーザーは Office アプリケーションでアドインを使い始めることができます (「 [Office アドインの使用を開始](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)する」を参照してください)。 アドインは、アドインがサポートするすべてのプラットフォームに表示されます。
  
アドインがアドイン コマンドをサポートする場合、そのコマンドは Office のリボンに表示されます。次の例では、[ **引用の検索** ] コマンドが [ **引用** ] アドインで表示されています。 

![検索引用を含む Office リボン](../../media/553b0c0a-65e9-4746-b3b0-8c1b81715a86.png)
  
展開されたアドインがアドインコマンドをサポートしていない場合や、展開されたすべてのアドインを表示する場合は、 **[マイ**アドイン] で表示できます。 
  
### <a name="in-word-2016-excel-2016-or-powerpoint-2016"></a>Word 2016、Excel 2016、または PowerPoint 2016

1. [ ** \> マイアドインの挿入**] を選択します。 
    
2. Office アドイン ウィンドウの [ **管理による管理者** ] タブを選択します。 
    
3. 前に展開したアドインをダブルクリックします (この例では [ **引用文献** ])。 <br/>![[Office アドイン] ページの [管理者による管理] タブ](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)
  
### <a name="in-outlook"></a>Outlook

1. [**ホーム**] リボンで、[アドインの**取得**] を選択します。<br/>![Outlook の [格納] ボタン](../../media/getaddinsicon.png)
  
2. 左側のナビゲーションで、**[管理者が管理]** を選びます。 

## <a name="learn-more"></a>詳細情報

[管理センターでアドインを展開する](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)

[Office アドイン](https://go.microsoft.com/fwlink/p/?linkid=846362)の作成と構築の詳細情報を表示します。
  
[一元展開 PowerShell コマンドレットを使用してアドインを管理](https://docs.microsoft.com/office365/enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins)します。
  
[トラブルシューティング: ユーザーがアドインを表示していない](https://docs.microsoft.com/office365/troubleshoot/access-management/user-not-seeing-add-ins)

[未成年者と Microsoft ストアからのアドインの取得](https://docs.microsoft.com/microsoft-365/admin/manage/minors-and-acquiring-addins-from-the-store)