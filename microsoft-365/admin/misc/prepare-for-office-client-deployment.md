---
title: ビジネス向けOfficeクライアントの展開Microsoft 365準備する
f1.keywords:
- CSH
ms.author: efrene
author: efrene
manager: scotv
ms.date: 10/31/2017
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection: M365-subscription-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ROBOTS: NO INDEX, NO FOLLOW
ms.assetid: ed34fff3-2881-4ed4-9906-1ba6bb8dd804
description: 32 ビット アプリをコンピューターに自動的Officeし、Windows 10する方法について学習します。
ms.openlocfilehash: f57f9538f859136179491620f1ce11ca17981068
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60174053"
---
# <a name="prepare-for-office-client-deployment-by-microsoft-365-for-business"></a>ビジネス向けOfficeクライアントの展開Microsoft 365準備する

この記事は、このMicrosoft 365 Business Premium。

## <a name="prepare-to-automatically-install-office-apps-to-client-computers"></a>Office アプリをクライアント コンピューターに自動的にインストールするための準備

32 ビット Microsoft 365 Business Premiumを使用して、32 ビット Office アプリをWindows 10更新プログラムで最新の状態に保つ。
  
自動インストールは、エンド ユーザーのコンピューターが次の手順で実行されている場合Windows 10 Business最適です。
  
- 既存の Office デスクトップ アプリ (Word、Excel、PowerPoint、Outlook、OneNote、Publisher、Access、OneDrive) がない。
    
    または
    
- Office のクイック実行の既存バージョンがインストールされている。
    
To determine if you have the Click-to-Run version of Office, in any Office app go to **File** \> **Account** ( **Office Account** in Outlook). 次の図に **Office更新** プログラムが表示される場合は、インストールは次の手順で実行クイック実行。 
  
![アカウントのOffice更新プログラムOffice アプリスクリーンショット。](../../media/e3439380-fa43-4ed6-ae5d-64851c297df5.png)
  
 **Who機能を持つことの利点**
  
次の PC を持つエンドユーザー:
  
- **ユーザー** ライセンスWindows 10 Business、ビジネス ライセンスMicrosoft 365アクティブなWindows 10 Creators Update持ち、Azure Active Directory。 
    
- **64** ビット アプリ (Word、Office、Excel など) をPowerPoint。 64 ビット Office アプリが必要な場合、ビジネス管理コンソール用の Microsoft 365 から 64 ビット 2016 クイック実行 バージョンの Office をトリガーするサポートが存在しないので、この機能は適しています。 
    
- 任意の 2016 Windows インストーラー (MSI) 単体アプリ (Visio や Project など) が **ない** 。 Microsoft 365 Office クイック実行 バージョン Office 2016 にアップグレードする場合、Office MSI スタンドアロン アプリでは動作しません。 
    
次の表に、エンド ユーザー/管理者が、ビジネス管理コンソール用の Microsoft 365 から 32 ビット クイック実行 バージョンの Office 展開を成功するために必要なアクションを示します。<br/>


|Office インストールの開始状態|ビジネス アプリケーションのインストールMicrosoft 365前に実行Officeアクション|最終的な状態|
|:-----|:-----|:-----|
|Office スイート製品がインストールされない  <br/> |なし  <br/> |Officeを使用して 2016 32 ビットがインストールクイック実行  <br/> |
|Office (2016 以前) の 32 ビット版クイック実行バージョンはあるが、単体アプリはない  <br/> |なし  <br/> |必要に応じて、最新の Office 2016 の 32 ビット版クイック実行バージョンにアップグレードする **\*** <br/> |
|既存クイック実行 32 ビット バージョンの Office および クイック実行 32 ビットまたは 64 ビットスタンドアロン Office アプリ (Visio、Project など)  <br/> |None  <br/> |スタンドアロン アプリは影響を受け取らない。 スイート製品を Office 2016 の 32 ビット版クイック実行バージョンにアップグレードする  <br/> |
|Office の 32 ビット版クイック実行バージョンと、32 ビットまたは 64 ビット版 (2016 を除く) MSI の単体 Office アプリがある  <br/> |なし  <br/> |スタンドアロン アプリは影響を受け取らない。 スイート製品を Office 2016 の 32 ビット版クイック実行バージョンにアップグレードする  <br/> |
|任意の Office の 64 ビット版クイック実行バージョンがある  <br/> |64 ビット アプリをアンインストールOffice 32 ビット アプリに置き換Officeします。  <br/> |64 ビット版の Office アプリを削除した場合は、32 ビット版クイック実行バージョンの Office 2016 をインストールする  <br/> |
|Office 2016 の MSI インストールがある (単体アプリの有無は関係ない)  <br/> |MSI Office 2016 をアンインストールする  <br/> |Office 2016 の 32 ビット版クイック実行バージョンをインストールする。単体アプリへの変更はなし  <br/> |
|既存の Office 2013 (以前) の MSI インストールおよび/または単体の Office アプリ  <br/> |なし  <br/> |Office 2016 の 32 ビット版クイック実行バージョンと既存の MSI Office インストール (および単体アプリ) が共存する  <br/> |
||||
   
 **(\*) 注:** 既知の問題により、Office 2016 の 32 ビット版クイック実行バージョンにはアップグレードされません。 修正が進行中です。 
  
