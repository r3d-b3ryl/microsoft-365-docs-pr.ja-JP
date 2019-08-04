---
title: Microsoft 365 Business による Office クライアントの展開を準備する
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.date: 10/31/2017
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: M365-subscription-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: ed34fff3-2881-4ed4-9906-1ba6bb8dd804
description: 32ビット版の Office アプリを Windows 10 コンピューターに自動的にインストールして、更新したままにする方法について説明します。
ms.openlocfilehash: 20269c493b0e3b5a7deb56a24a5e1a9583ef9d0a
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "34074652"
---
# <a name="prepare-for-office-client-deployment-by-microsoft-365-business"></a>Microsoft 365 Business による Office クライアントの展開を準備する

## <a name="prepare-to-automatically-install-office-apps-to-client-computers"></a>Office アプリをクライアント コンピューターに自動的にインストールするための準備

Microsoft 365 Business を使用すると、32 ビット版の Office アプリを Windows 10 コンピューターに自動的にインストールして、更新プログラムで最新状態に維持することができます。
  
これは、エンドユーザーのコンピューターで Windows 10 Business が実行されていて、なおかつ次の場合に最適です。
  
- 既存の Office デスクトップ アプリ (Word、Excel、PowerPoint、Outlook、OneNote、Publisher、Access、OneDrive) がない。
    
    または
    
- Office のクイック実行の既存バージョンがインストールされている。
    
To determine if you have the Click-to-Run version of Office, in any Office app go to **File** \> **Account** ( **Office Account** in Outlook). If you see Office Updates as shown in the following figure, then the installation was done by using Click-to-Run. 
  
![Screenshot of Office updates in Office app Account](media/e3439380-fa43-4ed6-ae5d-64851c297df5.png)
  
 **この機能の恩恵を受けるユーザー**
  
次の PC を持つエンドユーザー:
  
- Windows 10 Business ユーザー ライセンス、アクティブな Microsoft 365 Business ライセンス、および Windows 10 Creators Update が **あり** 、Azure Active Directory に参加している。 
    
- 64 ビット版の Office アプリが **ない** (例:Word、Excel、PowerPoint)。64 ビット版の Office アプリが必要な場合、この機能は適合しません。Microsoft 365 Business 管理コンソールから Office 2016 の 64 ビット版のクイック実行バージョンのトリガーがサポートされていないからです。 
    
- 任意の 2016 Windows インストーラー (MSI) 単体アプリ (Visio や Project など) が **ない** 。Microsoft 365 Business では Office は Office 2016 のクイック実行バージョンにアップグレードされますが、これは Office 2016 MSI 単体アプリでは動作しません。 
    
次の表では、Microsoft 365 Business管理コンソールから 32 ビット版クイック実行バージョンの Office を正しく展開するために、開始状態に応じて、エンドユーザー/管理者が実行する必要のあるアクションを示します。
  
|**Office インストールの開始状態**|**Microsoft 365 Business Office のインストール前に行うアクション**|**終了状態**|
|:-----|:-----|:-----|
|Office スイート製品がインストールされない  <br/> |None  <br/> |クイック実行を使用して Office 2016 の 32 ビット版をインストールする  <br/> |
|Office (2016 以前) の 32 ビット版クイック実行バージョンはあるが、単体アプリはない  <br/> |None  <br/> |必要に応じて、最新の Office 2016 の 32 ビット版クイック実行バージョンにアップグレードする **\*** <br/> |
|Office の 32 ビット版クイック実行バージョンと、32 ビットまたは 64 ビット版クイック実行の単体 Office アプリ (Visio、Project など) がある  <br/> |None  <br/> |単体アプリは影響を受けない。スイート製品を Office 2016 の 32 ビット版クイック実行バージョンにアップグレードする  <br/> |
|Office の 32 ビット版クイック実行バージョンと、32 ビットまたは 64 ビット版 (2016 を除く) MSI の単体 Office アプリがある  <br/> |None  <br/> |単体アプリは影響を受けない。スイート製品を Office 2016 の 32 ビット版クイック実行バージョンにアップグレードする  <br/> ||||
|任意の Office の 64 ビット版クイック実行バージョンがある  <br/> |32 ビット版の Office アプリに置き換えても問題ない場合は、64 ビット版の Office アプリをアンインストールする  <br/> |64 ビット版の Office アプリを削除した場合は、32 ビット版クイック実行バージョンの Office 2016 をインストールする  <br/> |
|Office 2016 の MSI インストールがある (単体アプリの有無は関係ない)  <br/> |MSI Office 2016 をアンインストールする  <br/> |Office 2016 の 32 ビット版クイック実行バージョンをインストールする。単体アプリへの変更はなし  <br/> |
|既存の Office 2013 (以前) の MSI インストールおよび/または単体の Office アプリ  <br/> |なし  <br/> |Office 2016 の 32 ビット版クイック実行バージョンと既存の MSI Office インストール (および単体アプリ) が共存する  <br/> |
||||
   
 **(\*) 注:** 既知の問題により、Office 2016 の 32 ビット版クイック実行バージョンにはアップグレードされません。修正中です。 
  


