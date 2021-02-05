---
title: Microsoft 365 利用状況分析を有効にする
f1.keywords:
- CSH
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
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9db96e9f-a622-4d5d-b134-09dcace55b6a
description: Power BI で Microsoft 365 利用状況分析テンプレート アプリを使用して、テナントのデータ収集を開始する方法について説明します。
ms.openlocfilehash: 98ae107b6777ac97d0be3b37847117c6e20be63d
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114239"
---
# <a name="enable-microsoft-365-usage-analytics"></a>Microsoft 365 利用状況分析を有効にする

::: moniker range="o365-21vianet"

> [!NOTE]
> 管理センターは変更中です。 エクスペリエンスがここで説明されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true)」を参照してください。

::: moniker-end

Microsoft 365 US Government Community では、Microsoft 365 利用状況分析はまだ利用できません。
  
## <a name="steps-to-enable-microsoft-365-usage-analytics"></a>Microsoft 365 利用状況分析を有効にする手順

Microsoft 365 利用状況分析を開始するには、まず Microsoft 365 管理センターでデータを利用し、次に Power BI でテンプレート アプリを開始する必要があります。
  
### <a name="get-power-bi"></a>Power BI を取得する

Power BI をまだお持ちでない場合は [、Power BI Pro にサインアップできます](https://go.microsoft.com/fwlink/p/?linkid=845347)。 試用版 **に無料で** サインアップするか、[今すぐ購入]を選択して Power BI Pro を取得します。
  
  
[ **製品**] を展開して Power BI のバージョンを購入することもできます。 

> [!NOTE]
> テンプレート アプリをインストール、カスタマイズ、配布するには、Power BI Pro ライセンスが必要です。 詳細については、「前提条件」を [参照してください](https://docs.microsoft.com/power-bi/service-template-apps-install-distribute?source=docs#prerequisites)。

データを共有するには、自分とデータを共有するユーザー、Power BI Pro ライセンスが必要なユーザー、 [またはコンテンツ](https://docs.microsoft.com/power-bi/service-premium-what-is)が Power BI Premium サービスのワークスペースにある必要があります。 
  
### <a name="enable-the-template-app"></a>テンプレート アプリを有効にする

テンプレート アプリを有効にするには、グローバル管理者である **必要があります**。
  
詳細 [については、管理者ロールに](../add-users/about-admin-roles.md) 関するページを参照してください。 
  
1. 管理センターで、[**レポート**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用状況</a>] ページの順に移動します。 
    
2. [使用状況 **] ページで****、Microsoft 365 利用状況** 分析カードを見つけ、[開始]**を選択します**。
    
3. 表示された [レポート] パネルで、[Power BI の **Microsoft 365** 利用状況分析でデータを利用できる] を [保存時] **に設定** \> **します**。 
  
データ収集プロセスは、テナントのサイズに応じて 2 ~ 48 時間で完了します。 データ **収集が完了すると、[Power BI** に移動] ボタンが有効になります (灰色ではなくなりました)。 
    
### <a name="start-the-template-app"></a>テンプレート アプリを起動する

テンプレート アプリを起動するには、グローバル管理者、レポート閲覧者 **、Exchange 管理者****、Skype for Business** 管理者、または SharePoint 管理者である **必要があります**。 
  
1. テナント ID をコピーし **、[Power BI に移動] を選択します**。
    
2.  When you get to Power BI, sign in. 次 **に、ナビゲーション** -> **メニューから [アプリを取得** する] を選択します。    
  
3. [アプリ **] タブで** 、検索ボックスに「Microsoft 365」と入力し **、[Microsoft 365** 利用状況分析を今すぐ取得] を \> **選択します**。

    [![[今すぐ取得] を選択する](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)
    
4.  アプリがインストールされた後。 タイルを選択して開きます。

5.  [ **アプリの探索] を** 選択して、サンプル データを含むアプリを表示します。 [ **接続]** を選択して、アプリを組織のデータに接続します。

6.  Choose **Connect**, on the **Connect to Microsoft 365 usage analytics** screen, then type in the tenant ID (without dashes) you copied in step (1), and select **Next**.
    
7. 次の画面で、 **認証方法として [OAuth2]** **を** \> **選択** します。 他の認証方法を選択すると、テンプレート アプリへの接続は失敗します。
    
    ![認証方法として Microsoft アカウントを選択する](../../media/ab6f0463-c3f7-4088-a605-67c699fa86adnew.png)
  
8. テンプレート アプリがインスタンス化されると、Microsoft 365 利用状況分析ダッシュボードが Power BI on the web で利用できます。 ダッシュボードの初期読み込みには 2 ~ 30 分かかります。
  
テナント レベルの集計は、オプトイン後のすべてのレポートで利用できます。 ユーザー レベルの詳細は、オプトイン後、次のカレンダー月の **5 日の周りにのみ利用できます**。 これは、ユーザー アクティビティのすべてのレポートに影響します (これらのレポートを表示および使用する方法のヒントについては [、「Microsoft 365](navigate-and-utilize-reports.md) 利用状況分析のレポートを移動して利用する」を参照してください)。
    
## <a name="make-the-collected-data-anonymous"></a>収集されたデータを匿名にする

すべてのレポート用に収集されるデータを匿名にするためには、グローバル管理者になる必要があります。 これにより、レポートやテンプレート アプリ内のユーザー、グループ、サイト名などの特定可能な情報が非表示になります。
  
1. In the admin center, go to the **Settings** \> **Org Settings,** and under **Services** tab, choose **Reports**.
    
2. [ **レポート] を** 選択し、[匿名識別子を **表示する] を選択します**。 この設定は、利用状況レポートとテンプレート アプリの両方に適用されます。
  
3. [**変更の保存**] を選択します。
