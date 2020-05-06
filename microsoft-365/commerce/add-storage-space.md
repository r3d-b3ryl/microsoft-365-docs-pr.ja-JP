---
title: サブスクリプションのストレージ領域を追加する
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- commerce
- Adm_TOC
- SPO_Content
ms.custom:
- MAX_CampaignID
- okr_SMB
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEU150
- GEA150
- GSP150
ms.assetid: 96ea3533-de64-4b01-839a-c560875a662c
description: Microsoft 365 サブスクリプションでファイルストレージを追加および削減する方法について説明します。 追加のファイルストレージを使用すると、SharePoint Online および OneDrive により多くのコンテンツを格納できます。
ms.openlocfilehash: a944c272f456fd6f284e1df28c52420e4deb40d4
ms.sourcegitcommit: eb3c7f473e8fe62624f52c9bb38dcd6a96fa58a3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "44045942"
---
# <a name="add-storage-space-for-your-subscription"></a>サブスクリプションのストレージ領域を追加する

SharePoint Online サイト コレクションの容量が不足し始めた場合、ご使用のプランが対象に含まれている場合は、サブスクリプションに容量を追加できます。 使用可能なアドオンの一覧に**Office 365 の追加ファイルストレージ**が表示されない場合は、プランが対象外であることを意味します。 詳細については、「[プランの対象の有無](#is-my-plan-eligible-for-office-365-extra-file-storage)」を参照してください。

## <a name="view-available-storage"></a>利用可能な記憶域を表示する

::: moniker range="o365-worldwide"

1. [新しい SharePoint 管理センターの [アクティブなサイト] ページ](https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true)に移動し、組織の[管理者権限](https://docs.microsoft.com/sharepoint/sharepoint-admin-role)が付与されているアカウントでサインインします。

2. ページの右上に、すべてのサイトで使用されている記憶域の容量とサブスクリプションの記憶域の合計が表示されます。 (組織の Office 365 で Multi-Geo が構成されている場合、バーにはすべての地理的な場所で使用されている記憶域の容量も表示されます。) 

::: moniker-end

::: moniker range="o365-germany"

1. グローバルまたはhttps://portal.office.de SharePoint 管理者としてにサインインし、[管理者] タイルを選択して、管理センターを開きます。 (ページへのアクセス許可がないことを示すメッセージが表示される場合、組織で Microsoft 365 管理者のアクセス許可を持っていません)。

2. 左側のウィンドウの [**管理センター**] で、[ **SharePoint**] を選択します。 従来の SharePoint 管理センターが表示された場合は、ページ上部の [**今すぐ起動する**] を選択します。これにより、新しい SharePoint 管理センターが開きます。

3. 新しい SharePoint 管理センターの左側のウィンドウで、**[アクティブなサイト]** を選択します。

4. ページの右上に、すべてのサイトで使用されている記憶域の容量とサブスクリプションの記憶域の合計が表示されます。

::: moniker-end

::: moniker range="o365-21vianet"

1. グローバルまたはhttps://login.partner.microsoftonline.cn/ SharePoint 管理者としてにサインインし、[管理者] タイルを選択して、管理センターを開きます。 (ページへのアクセス許可がないことを示すメッセージが表示される場合、組織で Microsoft 365 管理者のアクセス許可を持っていません)。

2. 左側のウィンドウの [**管理センター**] で、[ **SharePoint**] を選択します。 従来の SharePoint 管理センターが表示された場合は、ページ上部の [**今すぐ起動する**] を選択します。これにより、新しい SharePoint 管理センターが開きます。

3. 新しい SharePoint 管理センターの左側のウィンドウで、**[アクティブなサイト]** を選択します。

4. ページの右上に、すべてのサイトで使用されている記憶域の容量とサブスクリプションの記憶域の合計が表示されます。  

::: moniker-end

![[アクティブなサイト] ページの記憶域バー](https://docs.microsoft.com/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

> [!NOTE]
> 記憶域の使用量には、過去 24 から 48 時間以内に行われた変更は含まれません。

使用している記憶域の容量を決定したら、サブスクリプションの記憶域を追加または削除できます。 記憶域を追加するためにどのくらいのコストがかかるかを確認するには、この記事の手順に従って、購入する前に価格情報を確認してください。
  
サイトコレクションの記憶域の制限を設定する方法については、「[サイトコレクションの記憶域の制限を管理](https://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits)する」を参照してください。
  
## <a name="add-storage-to-your-subscription"></a>サブスクリプションにストレージを追加する

サブスクリプションのために特別なストレージをまだ購入していない場合は、これを行うことができます。

::: moniker range="o365-worldwide"

1. 管理センターで、[**課金**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">サービスを購入する</a>] ページに移動します。

2. [**サービスを購入**する] ページの下部で、 **[アドオン] を選択し**ます。

3. [ **Office 365 その他のファイル記憶域**] を選択します。

4. [ **Office 365 追加ファイル記憶域**] ページで、[基本サブスクリプション] を選択し、追加する記憶域の gb 数を入力します。

5. [**今すぐチェックアウト**] を選択します。

6. [**どのように表示しますか?** ] ページで、選択した記憶域の gb 数を確認し、価格情報を確認して、[**次へ**] を選択します。

7. [**注文の完了**] ページで、合計値を確認します。 変更を加える必要がある場合は、[**順序の編集**] を選択します。 注文で貸方の確認が必要な場合は、チェックボックスをオンにします。 完了したら、[**注文** \> ] [**管理者のホーム] に移動**します。

::: moniker-end

::: moniker range="o365-germany"

1. 管理センターで、[**課金** \><a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">サブスクリプション</a>] ページに移動します。  

2. [**サブスクリプション**] ページで、ストレージスペースを追加するサブスクリプションを選択し、[アドオン]**を選択します。**

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > **アドオン**が表示されない場合、パートナーを通じてサブスクリプションを購入した場合は、[ **Volume Licensing SERVICE Center (VLSC)**] を選択します。
  
3. [アドオンの**購入**] を選択します。

    ![管理センターの [サブスクリプション] ページで、[アドオンの購入] リンクをオンにします。](../media/f5cbc3fa-90f7-4299-976d-2482f2c69755.png)
  
4. [**購入サービス**] ページで、[ **Office 365 追加のファイルストレージ**] をマウス上またはタップし、[**今すぐ購入**] を選択します。
  
5. 必要なユーザーライセンス数を入力し、表示された場合は、基本サブスクリプションを選択します。 [**今すぐチェックアウト**] を選択します。
  
6. [**どのように表示しますか?** ] ページで、選択した記憶域の gb 数を確認し、価格情報を確認して、[**次へ**] を選択します。

7. [**注文の完了**] ページで、[**注文**] を選択します。

::: moniker-end

::: moniker range="o365-21vianet"

1. 管理センターで、[**課金情報**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">サブスクリプション</a>] ページに移動します。

2. [**サブスクリプション**] ページで、ストレージスペースを追加するサブスクリプションを選択し、[アドオン]**を選択します。**

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > **アドオン**が表示されない場合、パートナーを通じてサブスクリプションを購入した場合は、[ **Volume Licensing SERVICE Center (VLSC)**] を選択します。
  
3. [アドオンの**購入**] を選択します。

    ![管理センターの [サブスクリプション] ページで、[アドオンの購入] リンクをオンにします。](../media/f5cbc3fa-90f7-4299-976d-2482f2c69755.png)
  
4. [**購入サービス**] ページで、[ **Office 365 追加のファイルストレージ**] をマウス上またはタップし、[**今すぐ購入**] を選択します。
  
5. 必要なユーザーライセンス数を入力し、表示された場合は、基本サブスクリプションを選択します。 [**今すぐチェックアウト**] を選択します。
  
6. [**どのように表示しますか?** ] ページで、選択した記憶域の gb 数を確認し、価格情報を確認して、[**次へ**] を選択します。

7. [**注文の完了**] ページで、[**注文**] を選択します。

::: moniker-end

## <a name="increase-or-decrease-storage"></a>容量を増やす、または減らす

**Office 365 追加ファイル記憶域**アドオンを使用して、追加のファイル記憶域を既に購入している場合は、以下の手順を使用してサブスクリプションの追加の記憶域を増加または減少させることができます。 記憶域を1ギガバイトまで減らすことができます。 その他の記憶領域をすべて削除するには、[サポートに連絡](../admin/contact-support-for-business-products.md)する必要があります。

::: moniker range="o365-worldwide"

1. 管理センターで、[<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">製品</a>の**請求** \> ] ページに移動します。

2. **Office 365 追加ファイル記憶域**アドオンを含むサブスクリプションを選択します。

3. [**アドオン] を選択し、[****数量の変更**] を選択します。

4. [**ギガバイトの追加/削除**] ウィンドウで、サブスクリプションに使用する合計ギガバイト数を入力し、[**変更の送信**] を選択します。

::: moniker-end

::: moniker range="o365-germany"

1. 管理センターで、[**課金情報**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">サブスクリプション</a>] ページに移動します。

2. [**サブスクリプション**] ページで、 **[アドオン] を選択し**ます。

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > **アドオン**が表示されない場合、パートナーを通じてサブスクリプションを購入した場合は、[ **Volume Licensing SERVICE Center (VLSC)**] を選択します。
  
3. [ **Office 365 その他のファイル記憶域**] で、[**数量の変更**] を選択します。

    ![[数量の変更] リンク。](../media/96473f2b-6ff6-45ec-b1a3-d7b204ac1f6e.png)
  
4. 右側のウィンドウで、必要な合計ギガバイト数を入力し、[**送信**] を選択します。

    たとえば、現時点での追加のファイル記憶域は 200 ギガバイトであるが、必要なのは 100 ギガバイトのみである場合、ボックスに「 **100**」と入力します。

5. **[閉じる]** を選択します。

::: moniker-end

::: moniker range="o365-21vianet"

1. 管理センターで、[**課金情報**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">サブスクリプション</a>] ページに移動します。

2. [**サブスクリプション**] ページで、 **[アドオン] を選択し**ます。

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > **アドオン**が表示されない場合、パートナーを通じてサブスクリプションを購入した場合は、[ **Volume Licensing SERVICE Center (VLSC)**] を選択します。
  
3. [ **Office 365 その他のファイル記憶域**] で、[**数量の変更**] を選択します。

    ![[数量の変更] リンク。](../media/96473f2b-6ff6-45ec-b1a3-d7b204ac1f6e.png)
  
4. 右側のウィンドウで、必要な合計ギガバイト数を入力し、[**送信**] を選択します。

    たとえば、現時点での追加のファイル記憶域は 200 ギガバイトであるが、必要なのは 100 ギガバイトのみである場合、ボックスに「 **100**」と入力します。

5. **[閉じる]** を選択します。

::: moniker-end

## <a name="is-my-plan-eligible-for-office-365-extra-file-storage"></a>私のプランは Office 365 Extra File Storage の対象ですか。

Office 365 Extra File Storage は、次のサブスクリプションでご利用いただけます。
  
- Office 365 Enterprise E1

- Office 365 Enterprise E2

- Office 365 Enterprise E3

- Office 365 Enterprise E4

- Office 365 Enterprise E5

- SharePoint プラン1を使用した web 用 Office

- SharePoint プラン2を使用した web 用 Office

- SharePoint Online プラン 1

- SharePoint Online プラン 2

- Microsoft 365 Business Basic

- Microsoft 365 Business Standard

- Microsoft 365 Business Premium

- Microsoft 365 E3

- Microsoft 365 E5

- Microsoft 365 F1

> [!NOTE]
> Office 365 の特別なファイル記憶域は、GCC、GCC High、および DOD プランでも使用できます。
