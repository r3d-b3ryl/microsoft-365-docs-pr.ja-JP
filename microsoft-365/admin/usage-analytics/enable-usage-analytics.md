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
description: Power BI の Microsoft 365 Usage Analytics テンプレートアプリを使用して、テナントのデータの収集を開始する方法について説明します。
ms.openlocfilehash: b5cb8df7fbe8ce1844d2af3ecaf62c7903d4e98b
ms.sourcegitcommit: 6501e01a9ab131205a3eef910e6cea7f65b3f010
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2020
ms.locfileid: "46527381"
---
# <a name="enable-microsoft-365-usage-analytics"></a>Microsoft 365 利用状況分析を有効にする

::: moniker range="o365-21vianet"

> [!NOTE]
> 管理センターは変更されました。 エクスペリエンスがここで説明されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)」を参照してください。

::: moniker-end

Microsoft 365 usage analytics は、Microsoft 365 US Government Community ではまだ利用できません。
  
## <a name="steps-to-enable-microsoft-365-usage-analytics"></a>Microsoft 365 usage analytics を有効にする手順

Microsoft 365 usage analytics の使用を開始するには、まず、Microsoft 365 管理センターでデータを利用できるようにし、次に Power BI でテンプレートアプリを開始する必要があります。
  
### <a name="get-power-bi"></a>Power BI を取得する

Power BI をまだ持っていない場合は、 [POWER Bi Pro にサインアップ](https://go.microsoft.com/fwlink/p/?linkid=845347)できます。 [**無料**] を選択して試用版にサインアップするか、**今すぐ購入**して power BI Pro を入手します。
  
  
[ **製品**] を展開して Power BI のバージョンを購入することもできます。 

> [!NOTE]
> テンプレートアプリをインストール、カスタマイズ、および配布するには、Power BI Pro ライセンスが必要です。 詳細については、「[前提条件](https://docs.microsoft.com/power-bi/service-template-apps-install-distribute?source=docs#prerequisites)」を参照してください。

コンテンツを共有するには、Power BI Pro ライセンスが必要です。また、共有しているユーザーも、コンテンツを[プレミアム容量](https://docs.microsoft.com/power-bi/service-premium-what-is)のワークスペースに配置する必要があります。 
  
### <a name="enable-the-template-app"></a>テンプレートアプリを有効にする

テンプレートアプリを有効にするには、**全体管理者**、**レポート閲覧**者、 **Exchange 管理者**、 **Skype For business 管理**者、または**SharePoint 管理者**である必要があります。 
  
詳細については、「[管理者ロールについ](../add-users/about-admin-roles.md)て」を参照してください。 
  
1. 管理センターで、[**レポート**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用状況</a>] ページの順に移動します。 
    
2. [**使用法**] ページで、 **Microsoft 365 Usage analytics**カードを見つけて、[**開始**] を選択します。
    
3. 表示された [レポート] パネルで、Power BI to Save **On** the **Microsoft 365 usage analytics が [データを利用できるようにする**] を設定し \> **Save**ます。 
  
これにより、データ収集プロセスが開始され、テナントのサイズに応じて 2 ~ 48 時間で完了します。 データ収集が完了すると、 **[POWER BI に移動**] ボタンが有効になります (灰色ではなくなります)。 
    
### <a name="initiate-the-template-app"></a>テンプレートアプリを開始する

テンプレートアプリを開始するには、**全体管理者**、**レポート閲覧**者、 **Exchange 管理者**、 **Skype For business 管理**者、または**SharePoint 管理者**のいずれかである必要があります。 
  
1. テナント Id をコピーして、[ **POWER BI に移動] を**選択します。
    
2.  When you get to Power BI, sign in. ナビゲーションメニューから [アプリの >取得] を選択します。    
  
3. [**アプリ**] タブで、[検索] ボックスに「microsoft 365」と入力し、[ **microsoft 365 usage analytics** \> **Get now**] を選択します。

    [![[今すぐ取得] を選択する](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)
    
4.  アプリがインストールされると、 タイルをクリックして開きます。

5.  [**アプリの検索**] をクリックして、サンプルデータを含むアプリを表示します。 [**接続**] をクリックして、アプリを組織のデータに接続します。

6.  [**接続**] をクリックした後、[ **Microsoft 365 Usage analytics に接続**します] 画面で、手順 (1) でコピーしたテナント Id (ダッシュなし) を入力し、[**次へ**] を選択します。
    
7. 次の画面で、**認証方法**として [ **Microsoft アカウント**] を選択し \> **Sign in**ます。 他の認証方法を選択した場合は、テンプレートアプリへの接続が失敗します。
    
    ![認証方法として Microsoft アカウントを選択する](../../media/ab6f0463-c3f7-4088-a605-67c699fa86ad.png)
  
8. テンプレートアプリがインスタンス化されると、Microsoft 365 usage analytics ダッシュボードが web 上の Power BI で利用できるようになります。 ダッシュボードの最初の読み込みには、2 ~ 30 分かかります。
  
テナントレベル集計は、すべてのレポートで使用可能になります。 **ユーザーレベルの詳細は、カレンダー月の最初または15日以降にのみ使用可能に**なります。 これにより、ユーザーアクティビティの下にあるすべてのレポートが影響を受ける可能性があります (「 [Microsoft 365 usage analytics のレポート](navigate-and-utilize-reports.md)を表示および使用する方法に関するヒント」を参照してください)。
    
## <a name="make-the-collected-data-anonymous"></a>収集されたデータを匿名にする

すべてのレポート用に収集されるデータを匿名にするためには、グローバル管理者になる必要があります。 これにより、レポートおよびテンプレートアプリ内のユーザー、グループ、サイト名など、識別可能な情報が非表示になります。
  
1. 管理センターで、[設定] [ **Settings** \> **組織設定**] に移動し、[**サービス**] タブの [**レポート**] を選択します。
    
2. [**レポート**] を選択し、**匿名識別子を表示**するように選択します。 この設定は、利用状況レポートだけでなく、テンプレートアプリにも適用されます。
  
3. [**変更の保存**] を選択します。
