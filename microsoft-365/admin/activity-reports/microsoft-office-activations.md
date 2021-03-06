---
title: 管理センターの Microsoft 365 レポート - Microsoft Officeアクティブ化
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: overview
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
- GEA150
ms.assetid: 87c24ae2-82e0-4d1e-be01-c3bcc3f18c60
description: ライセンス認証レポートを取得して、Office サブスクリプションをアクティブ化したユーザーを知り、追加のOffice必要なユーザーを特定する方法について学習します。
ms.openlocfilehash: e82c67560be7ccaa3780547e6c95a2823e7f0adf
ms.sourcegitcommit: babbba2b5bf69fd3facde2905ec024b753dcd1b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "50514994"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-office-activations"></a>管理センターの Microsoft 365 レポート - Microsoft Officeアクティブ化

Microsoft 365 **レポート ダッシュボードには** 、組織内の製品全体のアクティビティの概要が表示されます。 これにより、個別の製品レベルのレポートを詳細に確認して、各製品内のアクティビティについてより詳しく知ることができます。 [レポートの概要に関するトピック](activity-reports.md)を参照してください。
  
[Office ライセンス認証] レポートでは、Office サブスクリプションのライセンス認証を行ったユーザーを少なくとも 1 台のデバイスで確認できます。 Office 365 サブスクリプションライセンス認証用の Microsoft 365 Apps for enterprise、Project、Visio Pro の内訳と、デスクトップとデバイス間でのライセンス認証の内訳を提供します。 このレポートは、Office サブスクリプションのライセンス認証について、追加のヘルプやサポートが必要なユーザーを特定するときにも役立ちます。
  
> [!NOTE]
> レポートを表示するには、Microsoft 365 のグローバル管理者、グローバル リーダー、またはレポート リーダーである必要があります。または Exchange、SharePoint、Teams Service、Teams Communications、Skype for Business の管理者である必要があります。  
  
## <a name="how-to-get-to-the-office-activations-report"></a>Office ライセンス認証レポートにアクセスする方法

1. 管理センターで、[**レポート**] \> [<a href="https://admin.microsoft.com/Adminportal/Home?source=applauncher#/reportsUsage" target="_blank">使用状況</a>] ページの順に移動します。

    
2. [レポート **の選択] ドロップダウン** から、[365 **ライセンス認証Office選択** \> **します**。 
  
## <a name="interpret-the-office-activations-report"></a>Office ライセンス認証レポートを解釈する

組織の Office のライセンス認証状況を確認するには、[ **ライセンス認証**] と [ **ユーザー**] に注目します。 
  
![ライセンス認証Office数](../../media/8c0ae08d-2d71-4437-9147-12c345bb5e9d.png)
  
|アイテム|説明|
|:-----|:-----|
|1  <br/> |Office のライセンス認証状況のレポートには、Office ライセンス認証データの現在の状態が表示されます [グラフ右上に表示されたレポートの日付以降]。  <br/> |
|2  <br/> |各レポートのデータは、通常、過去 24 - 48 時間まで表示されます。  <br/> |
|3  <br/> |[ **ライセンス認証**] グラフには、デスクトップとデバイスの Office ライセンスの認証数が表示されます。  <br/> |
|4   <br/> |[ **ユーザー**] グラフには、有効なユーザー数と、デスクトップまたはデバイスで Office サブスクリプションのライセンス認証を行ったユーザー数が表示されます。  <br/> |
|5   <br/> | [ **ライセンス認証**] グラフの Y 軸は、Office ライセンス認証数です。  <br/>  [ **ユーザー**] グラフの Y 軸は、ユーザーが Office のライセンス認証を行った操作です。  <br/>  どちらのグラフも、X 軸はこの特定のレポートで選択した日付範囲です。  <br/> |
|6   <br/> |凡例でアイテムを選択すると、表示されるグラフをフィルター処理できます。 たとえば、[ライセンス認証] グラフ **で****、[Windows OS]** **、[Mac OS]** **、[Windows 10 mobile]** **、[iOS]** または **[Android]** を選択して、それぞれに関連する情報のみを表示します。 この選択を変更しても、グリッド テーブルの情報は変更されません。 <br/> ![デバイスのライセンス認証データ](../../media/59d3ec6e-2a6e-4b21-8aac-c73038c47b9f.png)  <br/> |
|7   <br/> | 表には、ユーザー レベルの Office ライセンス認証の内訳が表示されます。これは、Office 製品が割り当てられたすべてのユーザーの一覧です。表には列を追加することができます。  <br/> ![Officeアクティブ化の使用可能な列](../../media/410a4baa-cef8-4676-bf7c-02a907a3a575.png)<br/> [ **ユーザー名**] はユーザーのメール アドレスです。  <br/> [ **表示名**] はユーザーの氏名です。  <br/> **製品ライセンス** は、このユーザーに割り当てられている製品です。  <br/> [ **最終ライセンス認証日**] は、ユーザーがデスクトップまたはデバイスで Office のライセンス認証を行った日付です。  <br/> **使用される共有コンピューターのライセンス** 認証は、ユーザーが共有コンピューターのライセンス認証をOffice場合は true です。 <br/> **Windows** は、ユーザーがアクティブ化した Windows デスクトップの数Officeします。  <br/> **Mac** は、ユーザーがアクティブ化した Mac デスクトップの数をOfficeします。  <br/> **Windows 10 mobile は** 、ユーザーがアクティブ化した Windows 10 モバイル デバイスの数Officeします。  <br/> **iOS** は、ユーザーがアクティブ化した iOS デバイスの数をOfficeします。  <br/> **Android** は、ユーザーがアクティブ化した Android デバイスの数Officeします。  <br/>  組織のポリシーにより、ユーザー情報を特定できるレポートを表示できない場合は、これらすべてのレポートのプライバシー設定を変更できます。 [Microsoft 365](activity-reports.md)管理 **センター** の [アクティビティ レポート] の [レポートでユーザーの詳細を非表示にする] セクションを参照してください。  <br/> |
|||
   

