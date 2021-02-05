---
title: サブスクリプションの記憶領域を追加する
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
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
- AdminSurgePortfolio
search.appverid:
- MET150
description: Microsoft 365 サブスクリプションでファイル ストレージを追加および削減する方法について説明します。 追加のファイル ストレージを使用すると、SharePoint Online と OneDrive にさらに多くのコンテンツを格納できます。
ms.date: ''
ms.openlocfilehash: fd59de31a27a1dd29800ae1d081e1f509f399124
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114909"
---
# <a name="add-storage-space-for-your-subscription"></a>サブスクリプションの記憶領域を追加する

::: moniker range="o365-21vianet"

> [!NOTE]
> 管理センターは変更中です。 エクスペリエンスがここで説明されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true)」を参照してください。

::: moniker-end

SharePoint Online サイト コレクションの容量が不足し始めた場合、ご使用のプランが対象に含まれている場合は、サブスクリプションに容量を追加できます。 利用可能なアドオンの一覧に **Office 365 Extra File Storage** が表示されない場合は、プランが対象とされていないことを意味します。 詳細については、「プランが対象 [ですか?」を参照してください。](#is-my-plan-eligible-for-office-365-extra-file-storage)

> [!NOTE]
> ボリューム ライセンスまたは CSP を通じてサブスクリプションを購入した場合、組織の Office **365 Extra File Storage** を Microsoft から直接購入することはできません。 サポートについては、担当の担当者またはパートナーにお問い合わせください。

## <a name="before-you-begin"></a>開始する前に

この記事のタスクを実行するには、グローバル管理者または SharePoint 管理者である必要があります。 詳細については、[「管理者の役割について」](../admin/add-users/about-admin-roles.md) を参照してください。

## <a name="view-available-storage"></a>利用可能な記憶域の表示

::: moniker range="o365-worldwide"

1. SharePoint 管理センターで、[アクティブなサイト<a href="https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true" target="_blank"></a>] ページに移動し、組織の管理者権限を持つ[アカウントでサインイン](https://docs.microsoft.com/sharepoint/sharepoint-admin-role)します。

2. ページの右上に、すべてのサイトで使用されている記憶域の容量とサブスクリプションの記憶域の合計が表示されます。 組織が Office 365 で複数地域を構成している場合は、すべての地域の場所で使用される記憶域の量もバーに表示されます。

   ![[アクティブなサイト] ページの記憶域バー](https://docs.microsoft.com/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

   > [!NOTE]
   > 記憶域の使用量には、過去 24 から 48 時間以内に行われた変更は含まれません。

::: moniker-end

::: moniker range="o365-germany"

1. グローバル管理者または SharePoint 管理者としてサインインし、[管理] タイルを選択して管理 https://portal.office.de センターを開きます。 ページにアクセスするアクセス許可を持たなかったというメッセージが表示された場合は、組織に Microsoft 365 管理者のアクセス許可が付与されていないことを意味します。

2. 左側のウィンドウの [**管理センター**] で、[**SharePoint**]を選択します。 従来の SharePoint 管理センターが表示された場合は、ページ上部の [**今すぐ起動する**] を選択します。これにより、新しい SharePoint 管理センターが開きます。

3. 新しい SharePoint 管理センターの左側のウィンドウで、**[アクティブなサイト]** を選択します。

4. ページの右上に、すべてのサイトで使用されている記憶域の容量とサブスクリプションの記憶域の合計が表示されます。

   ![[アクティブなサイト] ページの記憶域バー](https://docs.microsoft.com/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

   > [!NOTE]
   > 記憶域の使用量には、過去 24 から 48 時間以内に行われた変更は含まれません。

::: moniker-end

::: moniker range="o365-21vianet"

1. グローバル管理者または SharePoint 管理者としてサインインし、[管理] タイルを選択して管理 https://login.partner.microsoftonline.cn/ センターを開きます。 (ページにアクセスするアクセス許可が付与されていないというメッセージが表示される場合は、組織に Microsoft 365 管理者のアクセス許可が付与されていないことを意味します。

2. 左側のウィンドウの [**管理センター**] で、[**SharePoint**]を選択します。 従来の SharePoint 管理センターが表示された場合は、ページ上部の [**今すぐ起動する**] を選択します。これにより、新しい SharePoint 管理センターが開きます。

3. 新しい SharePoint 管理センターの左側のウィンドウで、**[アクティブなサイト]** を選択します。

4. ページの右上に、すべてのサイトで使用されている記憶域の容量とサブスクリプションの記憶域の合計が表示されます。  

   ![[アクティブなサイト] ページの記憶域バー](https://docs.microsoft.com/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

   > [!NOTE]
   > 記憶域の使用量には、過去 24 から 48 時間以内に行われた変更は含まれません。

::: moniker-end

使用している記憶域の容量を決定した後、サブスクリプションの記憶域を追加または削除できます。 記憶域を追加するために必要なコストを確認するには、この記事の手順に従い、購入する前に価格情報を確認します。
  
サイト コレクションの記憶域制限の設定については、「サイト コレクションの記憶域の制限を [管理する」を参照してください](https://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits)。
  
## <a name="add-storage-to-your-subscription"></a>サブスクリプションにストレージを追加する

サブスクリプションの追加ストレージをまだ購入していない場合は、購入できます。

::: moniker range="o365-worldwide"

1. 管理センターで、[**課金**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">サービスを購入する</a>] ページに移動します。
2. [サービスの購入] ページの下部 **で** 、[アドオン] **を選択します**。
3. Select **Office 365 Extra File Storage**.
4. [Office **365 Extra File Storage]** ページで、基本サブスクリプションを選択し、追加するストレージのギガバイト数を入力します。
5. [今 **すぐチェックアウト] を選択します**。
6. On the **How does this look?** page, verify the number of gbs of storage you selected, review the pricing information, and then select **Next**.
7. [注文 **の完了] ページ** で、合計を確認します。 変更が必要な場合は、[順序の編集] **を選択します**。 注文に与信チェックが必要な場合は、チェック ボックスをオンにします。 完了したら、[注文を管理ホームに移動 \> **] を選択します**。

::: moniker-end

::: moniker range="o365-germany"

1. 管理センターで、[課金サブスクリプション] \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">ページに移動</a>します。  

2. [ **サブスクリプション] ページ** で、記憶域を追加するサブスクリプションを選択し、[アドオン] **を選択します**。

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > アドオンが表示されていない場合に、サブスクリプションがパートナー経由で購入された場合は、ボリューム ライセンス サービス センター **(VLSC) を選択します**。
  
3. [ **アドオンの購入] を選択します**。

    ![管理センターの [サブスクリプション] ページにある [アドオン] リンクを購入します。](../media/f5cbc3fa-90f7-4299-976d-2482f2c69755.png)
  
4. [サービス **の購入]** ページで **、365** Extra File Storage をOfficeまたはタップし、[今すぐ購入] を選択 **します**。
  
5. 必要なユーザー ライセンスの数を入力し、表示されている場合は基本サブスクリプションを選択します。 [今 **すぐチェックアウト] を選択します**。
  
6. On the **How does this look?** page, verify the number of gbs of storage you selected, review the pricing information, and then select **Next**.

7. [注文 **の完了] ページで** 、[注文] **を選択します**。

::: moniker-end

::: moniker range="o365-21vianet"

1. 管理センターの **[課金]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">[サブスクリプション]</a> ページに移動します。

2. [ **サブスクリプション] ページ** で、記憶域を追加するサブスクリプションを選択し、[アドオン] **を選択します**。

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > アドオンが表示されていない場合に、サブスクリプションがパートナー経由で購入された場合は、ボリューム ライセンス サービス センター **(VLSC) を選択します**。
  
3. [ **アドオンの購入] を選択します**。

    ![管理センターの [サブスクリプション] ページにある [アドオン] リンクを購入します。](../media/f5cbc3fa-90f7-4299-976d-2482f2c69755.png)
  
4. [サービス **の購入]** ページで **、[365** Extra File Storage] をOfficeまたはタップし、[今すぐ購入] を選択 **します**。
  
5. 必要なユーザー ライセンスの数を入力し、表示されている場合は基本サブスクリプションを選択します。 [今 **すぐチェックアウト] を選択します**。
  
6. On the **How does this look?** page, verify the number of gbs of storage you selected, review the pricing information, and then select **Next**.

7. [注文 **の完了] ページで** 、[注文] **を選択します**。

::: moniker-end

## <a name="increase-or-decrease-storage"></a>容量を増やす、または減らす

**Office 365** Extra File Storage アドオンを介して追加のファイル ストレージを既に購入している場合は、次の手順を使用して、サブスクリプションの追加の記憶域を増減できます。 記憶域を 1 GB まで減らします。 追加の記憶領域を削除するには、サポートにお [問い合わせください](../admin/contact-support-for-business-products.md)。

::: moniker range="o365-worldwide"

1. 管理センターで、**[課金]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">[お使いの製品]</a> ページの順に移動します。
2. [製品 **] タブ** で、新しい Office **365 Extra File Storage** アドオンを含むサブスクリプションを選択します。
3. 製品の詳細ページの [アドオン] セクションで、[アドオンの管理]**を選択します**。
4. [アドオン **の管理]** ウィンドウの [アドオン] ボックスの一覧で **、[365 extra File Storage] Officeを選択します**。
5. [ **数量]** テキスト ボックスに、サブスクリプションに使用する記憶域の GB 数を入力します。
6. **[保存]** を選択します。

::: moniker-end

::: moniker range="o365-germany"

1. 管理センターの **[課金]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">[サブスクリプション]</a> ページに移動します。

2. [サブスクリプション **] ページで** 、[アドオン **] を選択します**。

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > アドオンが表示されていない場合に、サブスクリプションがパートナー経由で購入された場合は、ボリューム ライセンス サービス センター **(VLSC) を選択します**。
  
3. [Office **365 Extra File Storage]** で、[数量の変更 **] を選択します**。

    ![[数量の変更] リンク。](../media/96473f2b-6ff6-45ec-b1a3-d7b204ac1f6e.png)
  
4. 右側のウィンドウで、必要なギガバイトの総数を入力し、[送信] を選択 **します**。

    たとえば、現時点での追加のファイル記憶域は 200 ギガバイトであるが、必要なのは 100 ギガバイトのみである場合、ボックスに「 **100**」と入力します。

5. **[閉じる]** を選択します。

::: moniker-end

::: moniker range="o365-21vianet"

1. 管理センターの **[課金]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">[サブスクリプション]</a> ページに移動します。

2. [サブスクリプション **] ページで** 、[アドオン **] を選択します**。

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > アドオンが表示されていない場合に、サブスクリプションがパートナー経由で購入された場合は、ボリューム ライセンス サービス センター **(VLSC) を選択します**。
  
3. [Office **365 Extra File Storage]** で、[数量の変更 **] を選択します**。

    ![[数量の変更] リンク。](../media/96473f2b-6ff6-45ec-b1a3-d7b204ac1f6e.png)
  
4. 右側のウィンドウで、必要なギガバイトの総数を入力し、[送信] を選択 **します**。

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

- Office SharePoint プラン 1 を使用する Web の場合

- Office SharePoint プラン 2 を使用する Web の場合

- SharePoint Online プラン 1

- SharePoint Online プラン 2

- Microsoft 365 Business Basic

- Microsoft 365 Business Standard

- Microsoft 365 Business Premium

- Microsoft 365 E3

- Microsoft 365 E5

- Microsoft 365 F1

> [!NOTE]
> Office 365 Extra File Storage は、GCC、GCC High、DOD プランでも利用できます。

## <a name="related-content"></a>関連コンテンツ

[サイトの記憶域の制限を管理](ttps://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits) する (記事)\
[OneDrive ユーザーの既定の記憶領域を設定する](https://docs.microsoft.com/onedrive/set-default-storage-space)(記事)
