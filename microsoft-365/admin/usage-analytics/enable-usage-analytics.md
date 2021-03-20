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
description: Power BI で Microsoft 365 Usage Analytics テンプレート アプリを使用してテナントのデータ収集を開始する方法について説明します。
ms.openlocfilehash: 1ef50380041650763961ffbe6e01c63b26800ee3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50913876"
---
# <a name="enable-microsoft-365-usage-analytics"></a>Microsoft 365 利用状況分析を有効にする

::: moniker range="o365-21vianet"

> [!NOTE]
> 管理センターは変更中です。 エクスペリエンスがここで説明されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet)」を参照してください。

::: moniker-end

Microsoft 365 使用状況分析は、Microsoft 365 US Government Community ではまだ利用できません。
  
## <a name="steps-to-enable-microsoft-365-usage-analytics"></a>Microsoft 365 利用状況分析を有効にする手順

Microsoft 365 利用状況分析を開始するには、まず Microsoft 365 管理センターでデータを利用し、次に Power BI でテンプレート アプリを開始する必要があります。
  
### <a name="get-power-bi"></a>Power BI を取得する

Power BI をまだ持ってない場合は [、Power BI Pro にサインアップできます](https://go.microsoft.com/fwlink/p/?linkid=845347)。 [**無料で試** 用] を選択して試用版にサインアップするか、[今すぐ購入] を選択して Power BI Pro を取得します。
  
  
[ **製品**] を展開して Power BI のバージョンを購入することもできます。 

> [!NOTE]
> テンプレート アプリをインストール、カスタマイズ、配布するには、Power BI Pro ライセンスが必要です。 詳細については、「前提条件」を [参照してください](/power-bi/service-template-apps-install-distribute?source=docs#prerequisites)。

データを共有するには、ユーザーとデータを共有するユーザー、Power BI Pro ライセンスが必要、またはコンテンツが Power BI プレミアム サービスのワークスペースにある [必要があります](/power-bi/service-premium-what-is)。 
  
### <a name="enable-the-template-app"></a>テンプレート アプリを有効にする

テンプレート アプリを有効にするには、グローバル管理者である **必要があります**。
  
詳細 [については、「管理者の役割」](../add-users/about-admin-roles.md) を参照してください。 
  
1. 管理センターで、[**レポート**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用状況</a>] ページの順に移動します。 
    
2. [使用状況 **] ページで****、Microsoft 365** 利用状況分析カードを見つけて、[開始]**を選択します**。
    
3. 開く [レポート] パネルで、[Power BI の **Microsoft 365** 利用状況分析でデータを使用できる] を [保存時] **に設定** \> **します**。 
  
データ収集プロセスは、テナントのサイズに応じて 2 ~ 48 時間で完了します。 データ **収集が完了すると、[Power BI** に移動] ボタンが有効になります (灰色ではなくなりました)。 
    
### <a name="start-the-template-app"></a>テンプレート アプリを起動する

テンプレート アプリを起動するには、グローバル管理者、レポートリーダー **、Exchange 管理者、Skype** **for Business** 管理者、**または SharePoint 管理者である必要があります**。  
  
1. テナント ID をコピーし **、[Power BI に移動] を選択します**。
    
2.  When you get to Power BI, sign in. 次に **、[アプリ]** -> **ナビゲーション メニューから**[アプリを取得する] を選択します。    
  
3. [アプリ **] タブで** 、検索ボックスに「Microsoft 365」と入力し **、[Microsoft 365 利用状況** 分析] を選択します。今すぐ \> **取得します**。

    [![[今すぐ取得] を選択します。](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)
    
4.  アプリがインストールされた後。 タイルを選択して開きます。

5.  [アプリ **の探索] を** 選択して、サンプル データを使用してアプリを表示します。 [ **接続] を** 選択して、アプリを組織のデータに接続します。

6.  [ **接続]** を選択し **、[Microsoft 365** 利用状況分析に接続する] 画面で、手順 (1) でコピーしたテナント ID (ダッシュなし) を入力し、[次へ] を選択 **します**。
    
7. 次の画面で、[認証]**メソッドとして [OAuth2]** **を選択します** \> 。 他の認証方法を選択すると、テンプレート アプリへの接続が失敗します。
    
    ![認証方法として Microsoft アカウントを選択する](../../media/ab6f0463-c3f7-4088-a605-67c699fa86adnew.png)
  
8. テンプレート アプリのインスタンス化後、Microsoft 365 利用状況分析ダッシュボードは、Web 上の Power BI で使用できます。 ダッシュボードの初期読み込みには 2 ~ 30 分かかります。
  
テナント レベルの集計は、オプトイン後にすべてのレポートで使用できます。 **ユーザー レベルの詳細は、オプトイン後の次の暦月の 5 日の周りにのみ利用できます**。 これは、[ユーザー アクティビティ] の下のすべてのレポートに影響します (これらのレポートを表示および使用する方法のヒントについては [、「Microsoft 365](navigate-and-utilize-reports.md) 利用状況分析のレポートを移動して利用する」を参照してください)。
    
## <a name="make-the-collected-data-anonymous"></a>収集されたデータを匿名にする

すべてのレポート用に収集されるデータを匿名にするためには、グローバル管理者になる必要があります。 これにより、レポートやテンプレート アプリのユーザー名、グループ名、サイト名などの識別可能な情報が非表示になります。
  
1. 管理センターで、[組織の設定] の **[設定**] に移動し、[サービス] タブの [レポート] \> を **選択します**。 
    
2. [ **レポート] を** 選択し、[匿名識別子の **表示] を選択します**。 この設定は、使用状況レポートとテンプレート アプリの両方に適用されます。
  
3. [**変更の保存**] を選択します。