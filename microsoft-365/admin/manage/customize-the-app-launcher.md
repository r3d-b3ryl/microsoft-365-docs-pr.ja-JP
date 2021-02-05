---
title: カスタム タイルをアプリ起動ツールに追加する
f1.keywords:
- CSH
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
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 1136115a-75af-4497-b693-640c4ce70bc6
description: 'カスタム タイルをアプリ起動ツールに追加して、電子メール、ドキュメント、アプリ、SharePoint サイト、外部サイト、その他のリソースへのクイック リンクを作成します。 '
ms.openlocfilehash: 96d059b252b63e48e20edb29861cf8233e220e34
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114191"
---
# <a name="add-custom-tiles-to-the-app-launcher"></a>カスタム タイルをアプリ起動ツールに追加する

::: moniker range="o365-21vianet"

> [!NOTE]
> 管理センターは変更中です。 エクスペリエンスがここで説明されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true)」を参照してください。

::: moniker-end

Microsoft 365 では、アプリ起動ツールを使ってメール、予定表、ドキュメント、アプリにすばやく簡単にアクセスできます ([詳細をご覧ください](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a))。 これらは、Microsoft 365 で取得するアプリと[、SharePoint ストア](https://support.microsoft.com/office/dd98e50e-d3db-4ecb-9bb7-82b189822d43)または Azure アプリから追加するカスタム アプリ[AD。](https://msdn.microsoft.com/office/office365/howto/connect-your-app-to-o365-app-launcher)
  
SharePoint サイト、外部サイト、レガシー アプリなどをポイントするカスタム タイルをアプリ起動ツールに追加できます。カスタム タイルは、アプリ起動ツールの [ **すべて**] のアプリの下に表示されますが、[ **ホーム**] アプリにピン留めしたり、同じ操作を行うようにユーザーに指示したりできます。この操作により、関連サイト、アプリ、仕事に必要なリソースへのアクセスが容易になります。以下の例では、"Contoso Portal" と呼ばれるカスタム タイルを使って、組織の SharePoint イントラネット サイトにアクセスします。 
  
![アプリ起動ツール](../../media/7acc06cc-ac7a-4c6e-8ea7-81570a5bdbab.png)
  
## <a name="add-a-custom-tile-to-the-app-launcher"></a>カスタム タイルをアプリ起動ツールに追加する

1. グローバル管理者として管理センターにサインインし、[**設定** 組織の設定] に移動して、[組織プロファイル]  >  **タブを選択** します。
    
2. [組織プロファイル **] タブで** 、カスタム アプリ起動 **ツールのタイルを選択します**。
  
3. [カスタム **タイルの追加] を選択します**。 
  
4. 新しいタイルの **タイル名** を入力します。 名前がタイルに表示されます。 
    
5. タイルの **Web サイトの URL** を入力します。 これは、ユーザーがアプリ起動ツールでタイルを選択するときに移動する場所です。 URL で HTTPS を使用します。<br/>ヒント: SharePoint サイトのタイルを作成する場合は、そのサイトに移動し、URL をコピーして、ここに貼り付けます。 既定のチーム サイトの URL は次のように表示されます。 `https://<company_name>.sharepoint.com` 
  
6. タイルの **画像の URL** を入力します。 この画像は [個人用アプリ] ページとアプリ起動ツールに表示されます。<br/>ヒント: 画像は 60x60 ピクセルで、認証を必要とせずに組織内のすべてのユーザーが利用できる必要があります。

7. タイルの **説明** を入力します。 You see this when you select the tile on the My apps page and select **App details**. 
  
8. [変更 **の保存] を** 選択して、カスタム タイルを作成します。 
    
これでカスタム タイルは、管理者とユーザー用にアプリ起動ツールの [ **すべて**] のタブに表示されるようになります。 
  
## <a name="promote-the-tile-to-app-launcher"></a>タイルをアプリ アプリに昇格起動ツール

1. アプリ起動ツールアイコンを選択し、[すべてのアプリ] **を選択します**。 
    
2. アプリの新しいタイルを見つけ、省略記号を選択して、[ランチャーにピン留 **めする] を選択します**。
  
    > [!NOTE]
    > 前の手順で作成したカスタム タイルが表示されない場合は、Exchange Online メールボックスが自分に割り当てられていること、およびメールボックスに最低一度はサインインしていることを確認します。 これらの手順は、Microsoft 365 のカスタム タイルに必要です。 
  
> [!IMPORTANT]
> 自身とユーザーの両方がこれらの手順に従って、[個人用アプリ] ページからアプリ起動ツールへとタイルを昇格する必要があります。 
  
## <a name="edit-or-delete-a-custom-tile"></a>Edit or delete a custom tile

1. 管理センターで、[Settings Org   >  **Settings Organization**  >  **profile] タブに移動** </a> します。
    
2. [組織プロファイル **] ページで** 、[組織のカスタム タイルの追加] の横にある   **[編集**] を **選択します**。

3. カスタム タイルの **タイル名**、 **URL**、 **説明**、 **画像 URL** を更新します。( [カスタム タイルをアプリ起動ツールに追加する](#add-a-custom-tile-to-the-app-launcher)参照)。
    
4. [更新 **閉じる]** \> **を選択します**。 
    
カスタム タイルを削除するには、カスタム タイル ウィンドウ **から** タイルを選択し、[削除] タイル **を選択**  >  **します**。 
  
## <a name="whats-next"></a>次の手順

アプリ起動ツールにタイルを追加する以外に、アプリ起動ツールのタイルをナビゲーション バーに追加できます (詳しくは[、以下を参照してください](https://support.microsoft.com/office/eb34a21b-52fa-4fbf-a8d5-146132242985))。 組織のブランドに合わせて Microsoft 365 の外観をカスタマイズするには [、「Microsoft 365](../setup/customize-your-organization-theme.md)テーマをカスタマイズする」を参照してください。
  
