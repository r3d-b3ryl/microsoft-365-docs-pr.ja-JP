---
title: サブスクリプションの記憶域を追加する
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
- Adm_TOC
- SPO_Content
ms.custom:
- MAX_CampaignID
- okr_SMB
- AdminSurgePortfolio
- commerce
search.appverid:
- MET150
description: Microsoft 365 サブスクリプションのファイル ストレージを追加および削減する方法について説明します。 追加のファイル ストレージを使用すると、SharePoint Online と OneDrive にさらに多くのコンテンツを格納できます。
ms.date: ''
ms.openlocfilehash: 626cc81faea43ebdcf618a4f26c33069bae6a206
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/03/2021
ms.locfileid: "50405890"
---
# <a name="add-storage-space-for-your-subscription"></a>サブスクリプションの記憶域を追加する

::: moniker range="o365-21vianet"

> [!NOTE]
> 管理センターは変更中です。 エクスペリエンスがここで説明されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true)」を参照してください。

::: moniker-end

SharePoint Online サイト コレクションの容量が不足し始めた場合、ご使用のプランが対象に含まれている場合は、サブスクリプションに容量を追加できます。 使用可能なアドオンの一覧に Office **365 Extra File Storage** が表示されない場合は、プランが対象外となります。 詳細については、「自分のプラン [が適格か」を参照してください。](#is-my-plan-eligible-for-office-365-extra-file-storage)

> [!NOTE]
> ボリューム ライセンスまたは CSP を使用してサブスクリプションを購入した場合、Microsoft から直接組織Office **365 Extra File Storage** を購入することはできません。 サポートについては、担当者またはパートナーにお問い合わせください。

## <a name="before-you-begin"></a>はじめに

この記事のタスクを実行するには、グローバル管理者または SharePoint 管理者である必要があります。 詳細については、「[管理者の役割について](../admin/add-users/about-admin-roles.md)」を参照してください。

## <a name="view-available-storage"></a>使用可能なストレージの表示

1. SharePoint 管理センターで、[アクティブ な<a href="https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true" target="_blank"></a>サイト] ページに移動し、組織の管理者権限を持つ[アカウントでサインイン](https://docs.microsoft.com/sharepoint/sharepoint-admin-role)します。

2. ページの右上に、すべてのサイトで使用されている記憶域の容量とサブスクリプションの記憶域の合計が表示されます。 組織が 365 で複数地域を構成しているOfficeバーには、すべての地域の場所で使用される記憶域の量も表示されます。

   ![[アクティブなサイト] ページの記憶域バー](https://docs.microsoft.com/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

   > [!NOTE]
   > 記憶域の使用量には、過去 24 から 48 時間以内に行われた変更は含まれません。

使用している記憶域の量を決定した後、サブスクリプションの記憶域を追加または削除できます。 記憶域の追加に必要なコストを確認するには、この記事の手順に従い、購入前に価格情報を確認してください。
  
サイト コレクションの記憶域制限の設定の詳細については [、「Manage site collection storage limits」を参照してください](https://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits)。
  
## <a name="add-storage-to-your-subscription"></a>サブスクリプションにストレージを追加する

サブスクリプション用の追加ストレージをまだ購入していない場合は、そのストレージを使用できます。

1. 管理センターで、[**課金**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">サービスを購入する</a>] ページに移動します。
2. [サービスの購入]ページの下部にある[アドオン] セクションで **、[365** Officeストレージ] を見つけて、[詳細] を選択 **します**。
3. [製品の詳細] ページで、[次へ] を **選択します**。
4. 必要に応じて、基本サブスクリプションを選択し、追加するストレージのギガバイト数を入力します。
5. [今 **すぐチェックアウト] を選択します**。
6. [この **外観の確認方法]** ページで、選択したストレージのギガバイト数を確認し、価格情報を確認し、[次へ] を選択 **します**。
7. [注文 **の完了] ページ** で、合計を確認します。 変更が必要な場合は、[順序の編集] **を選択します**。 注文で与信チェックが必要な場合は、チェック ボックスをオンにします。 完了したら、[管理ホームに移動する] を \> **選択します**。

## <a name="increase-or-decrease-storage"></a>容量を増やす、または減らす

**Office 365** Extra File Storage アドオンを使用して追加のファイル ストレージを既に購入している場合は、次の手順を使用して、サブスクリプションの余分な記憶域領域を増やしたり減らしたりできます。 ストレージを 1 ギガバイトまで減らします。 余分な記憶域を削除するには、サポート [にお問い合わせください](../admin/contact-support-for-business-products.md)。

1. 管理センターで、**[課金]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">[お使いの製品]</a> ページの順に移動します。
2. [製品 **] タブ** で、365 Extra File **Storage Officeを含むサブスクリプションを** 選択します。
3. [製品の詳細] ページの [アドオン] セクション **で、[** アドオンの管理 **] を選択します**。
4. [アドオン **の管理] ウィンドウの**[アドオン] リストから **、[365 Officeストレージ] を選択します**。
5. [数量 **]** テキスト ボックスに、サブスクリプションに必要な記憶域の GB の数を入力します。
6. **[保存]** を選択します。

## <a name="is-my-plan-eligible-for-office-365-extra-file-storage"></a>私のプランは Office 365 Extra File Storage の対象ですか。

Office 365 Extra File Storage は、次のサブスクリプションでご利用いただけます。
  
- Office 365 Enterprise E1
- Office 365 Enterprise E2
- Office 365 Enterprise E3
- Office 365 Enterprise E4
- Office 365 Enterprise E5
- Office SharePoint プラン 1 を使用した Web の詳細
- Office SharePoint プラン 2 を使用した Web の詳細
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

[サイトストレージの制限を管理](ttps://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits) する (記事)\
[OneDrive ユーザーの既定の記憶域を設定する](https://docs.microsoft.com/onedrive/set-default-storage-space)(記事)