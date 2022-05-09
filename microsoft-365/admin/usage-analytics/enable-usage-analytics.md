---
title: Microsoft 365 利用状況分析を有効にする
f1.keywords:
- CSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
- admindeeplinkMAC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9db96e9f-a622-4d5d-b134-09dcace55b6a
description: Power BIで Microsoft 365 Usage Analytics テンプレート アプリを使用して、テナントのデータの収集を開始する方法について説明します。
ms.openlocfilehash: cc2b74696dbdab416493be1909f1781b31f201a6
ms.sourcegitcommit: 52eea2b65c0598ba4a1b930c58b42dbe62cdaadc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2022
ms.locfileid: "64946948"
---
# <a name="enable-microsoft-365-usage-analytics"></a>Microsoft 365 利用状況分析を有効にする

Microsoft 365米国Government Community Cloud (GCC) テナントでMicrosoft 365利用状況分析を有効にするには、「[Microsoft 365へのConnect」を参照してください。Usage Analytics を使用してデータをGovernment Community Cloud (GCC) します](connect-to-gcc-data-with-usage-analytics.md)。

## <a name="before-you-begin"></a>開始する前に

Microsoft 365使用状況分析を開始するには、まずMicrosoft 365 管理センターでデータを使用できるようにしてから、<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Power BI</a>でテンプレート アプリを開始する必要があります。

## <a name="get-power-bi"></a>Power BI を取得する

まだPower BIがない場合は、[Power BI Proにサインアップ](https://go.microsoft.com/fwlink/p/?linkid=845347)できます。 [**無料で試す**] を選択して試用版にサインアップするか、[**今すぐ購入]** を選択してPower BI Pro。


[ **製品**] を展開して Power BI のバージョンを購入することもできます。

> [!NOTE]
> テンプレート アプリをインストール、カスタマイズ、配布するには、Power BI Pro ライセンスが必要です。 詳細については、「前提条件」を参照 [してください](/power-bi/service-template-apps-install-distribute?source=docs#prerequisites)。

データを共有するには、データを共有するユーザー、Power BI Pro ライセンスが必要なユーザー、またはコンテンツが[Power BI Premium サービス](/power-bi/service-premium-what-is)のワークスペース内にある必要があります。

## <a name="enable-the-template-app"></a>テンプレート アプリを有効にする

テンプレート アプリを有効にするには、**グローバル管理者** である必要があります。

詳細については、 [管理者ロールに関](../add-users/about-admin-roles.md) するページを参照してください。

1. 管理センターで、[**設定** \> **組織の設定** \> **サービス**] タブに移動します。

2. [ **サービス** ] タブで、[  **レポート**] を選択します。

3. 開いた [レポート] パネルで、[**Power BIの利用状況分析Microsoft 365レポート データを使用できるようにする**] を **[保存時]** \> に設定 **します**。

データ収集プロセスは、テナントのサイズに応じて 2 ~ 48 時間で完了します。 データ収集が完了すると **、[Power BIに移動**] ボタンが有効になります (灰色は表示されなくなります)。 完了すると、アプリは組織レベルで使用履歴データを提供します。 

> [!NOTE]
> **[ユーザー アクティビティ]** タブのデータは、現在の月の 15 日目と翌月の最初の日の後にのみ更新されるため、最初の更新が完了するまで最初は空のままになります。

## <a name="start-the-template-app"></a>テンプレート アプリを起動する

テンプレート アプリを起動するには、**グローバル管理者**、**レポート リーダー**、**Exchange管理者、Skype for Business管理者**、または **SharePoint管理者** である必要があります。

1. テナント ID をコピーし、[**Power BIに移動**] を選択します。

2. When you get to Power BI, sign in. 次に、ナビゲーション メニューから **AppsGet**-> **アプリ** を選択します。

3. [**アプリ**] タブで、検索ボックスに「Microsoft 365」と入力し、**使用状況分析** \> Microsoft 365選択 **します**。

    [![[今すぐ取得] を選択します。](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)

4. アプリがインストールされたら。 タイルを選択して開きます。

5. [ **アプリの探索** ] を選択して、サンプル データを含むアプリを表示します。 **Connect** を選択して、アプリを組織のデータに接続します。

6. **Connect** を選択し、**Connectで使用状況分析画面をMicrosoft 365** し、手順 (1) でコピーしたテナント ID (ダッシュなし) を入力し、[**次へ**] を選択します。

7. 次の画面で、[**認証方法**\>] **サインイン** として **[OAuth2**] を選択します。 他の認証方法を選択した場合、テンプレート アプリへの接続は失敗します。

    ![認証方法として Microsoft アカウントを選択します。](../../media/ab6f0463-c3f7-4088-a605-67c699fa86adnew.png)

8. テンプレート アプリがインスタンス化されると、Microsoft 365利用状況分析ダッシュボードが web 上のPower BIで利用できるようになります。 ダッシュボードの初回読み込みには、2 ~ 30 分かかります。

テナント レベルの集計は、オプトインした後、すべてのレポートで使用できます。 **ユーザー レベルの詳細は、オプトインした後、翌暦月の 5 日頃にのみ利用できるようになります**。 これにより、ユーザー アクティビティのすべてのレポートに影響します (これらのレポートを表示および使用する方法に関するヒントについては、[Microsoft 365利用状況分析のレポートの移動と利用](navigate-and-utilize-reports.md)に関するページを参照してください)。

## <a name="make-the-collected-data-anonymous"></a>収集されたデータを匿名にする

レポートで組織の使用状況データに関する情報を入力します。 既定では、レポートにユーザー、グループ、およびサイトの識別可能な名前を持つ情報が表示されます。 2021 年 9 月 1 日より、企業が地域のプライバシー法をサポートするのに役立つ継続的な取り組みの一環として、既定ですべてのレポートのユーザー情報を非表示にしています。
  
グローバル管理者は、組織のプライバシー方針で許可されている場合は、テナント用のこの変更を元に戻し、特定可能なユーザー情報を表示することができます。 これは、Microsoft 365 管理センターで以下の手順に従うことで設定できます。
  
1. 管理センターで、**[設定]** \> **[組織の設定]** \> **[サービス]** のページの順に移動します。

2. [**レポート**] を選択します。 
  
3. ステートメントのチェックを外します **すべてのレポートで、ユーザー、グループ、およびサイトの識別されていない名前を表示し**、変更を保存します。  
  
これらの変更が有効になるまで数分かかります。 特定可能なユーザー情報の表示は、Microsoft Purview コンプライアンス ポータル監査ログに記録されるイベントです。   

## <a name="related-content"></a>関連コンテンツ

[利用状況分析について](usage-analytics.md) (記事)\
[利用状況分析の最新バージョンを取得](get-the-latest-version-of-usage-analytics.md) する (記事)\
[Microsoft 365利用状況分析のレポートを移動して利用](navigate-and-utilize-reports.md)する (記事)
