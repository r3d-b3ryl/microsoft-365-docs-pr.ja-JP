---
title: Microsoft 365 Officeによるクライアント展開の準備
f1.keywords:
- CSH
ms.author: efrene
author: efrene
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
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: ed34fff3-2881-4ed4-9906-1ba6bb8dd804
description: Windows 10 コンピューターに 32 ビット Officeアプリを自動的にインストールし、更新を維持する方法について学習します。
ms.openlocfilehash: 868d06fadfef0f55b41131b7fdfbb368b9128405
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580056"
---
# <a name="prepare-for-office-client-deployment-by-microsoft-365-for-business"></a>Microsoft 365 Officeによるクライアント展開の準備

この記事は、Microsoft 365 Business Premium に適用されます。

## <a name="prepare-to-automatically-install-office-apps-to-client-computers"></a>Office アプリをクライアント コンピューターに自動的にインストールするための準備

Microsoft 365 Business Premium を使用すると、Windows 10 コンピューターに 32 ビット Office アプリを自動的にインストールし、更新プログラムを最新の状態に保つ必要があります。
  
自動インストールは、エンド ユーザーのコンピューターが Windows 10 Business 上に次の場合に最適です。
  
- 既存の Office デスクトップ アプリ (Word、Excel、PowerPoint、Outlook、OneNote、Publisher、Access、OneDrive) がない。
    
    または
    
- Office のクイック実行の既存バージョンがインストールされている。
    
To determine if you have the Click-to-Run version of Office, in any Office app go to **File** \> **Account** ( **Office Account** in Outlook). 次の図に **Office更新** プログラムが表示された場合は、インストールは次の手順で行クイック実行。 
  
![Screenshot of Office updates in Office app Account](../media/e3439380-fa43-4ed6-ae5d-64851c297df5.png)
  
 **この機能を利用してメリットを得るユーザー**
  
次の PC を持つエンドユーザー:
  
-  Windows 10 Business ユーザー ライセンス、アクティブな Microsoft 365 for Business ライセンス、Windows 10 Creators Update を持ち、Azure Active Directory に参加しています。 
    
- **64 ビット** アプリ (word、Excel、PowerPoint など) Office 64 ビット アプリを持つ必要があります。 64 ビット Office アプリが必要な場合は、Microsoft 365 for business 管理コンソールから 64 ビット 2016 クイック実行 バージョンの Office をトリガーするサポートが存在しないので、この機能は適しています。 
    
- 任意の 2016 Windows インストーラー (MSI) 単体アプリ (Visio や Project など) が **ない** 。 Microsoft 365 for business upgrades Office クイック実行 バージョンの Office 2016 にアップグレードすると、Office 2016 MSI スタンドアロン アプリでは動作しません。 
    
次の表に、Microsoft 365 for business 管理コンソールから 32 ビット クイック実行 バージョンの Office 展開を成功するために、エンド ユーザー/管理者が実行する必要があるアクションを示します。
  
|**Office インストールの開始状態**|**Microsoft 365 for business Office実行するアクション**|**終了状態**|
|:-----|:-----|:-----|
|Office スイート製品がインストールされない  <br/> |なし  <br/> |Officeを使用して 2016 32 ビットがインストールクイック実行  <br/> |
|Office (2016 以前) の 32 ビット版クイック実行バージョンはあるが、単体アプリはない  <br/> |なし  <br/> |必要に応じて、最新の Office 2016 の 32 ビット版クイック実行バージョンにアップグレードする **\*** <br/> |
|既存クイック実行 32 ビット バージョンの Office および クイック実行 32 ビットまたは 64 ビットスタンドアロン Office アプリ (Visio、Project など)  <br/> |なし  <br/> |スタンドアロン アプリは影響を受け取らない。 スイート製品を Office 2016 の 32 ビット版クイック実行バージョンにアップグレードする  <br/> |
|Office の 32 ビット版クイック実行バージョンと、32 ビットまたは 64 ビット版 (2016 を除く) MSI の単体 Office アプリがある  <br/> |なし  <br/> |スタンドアロン アプリは影響を受け取らない。 スイート製品を Office 2016 の 32 ビット版クイック実行バージョンにアップグレードする  <br/> ||||
|任意の Office の 64 ビット版クイック実行バージョンがある  <br/> |64 ビット アプリOfficeアンインストールする (32 ビット アプリに置き換Office場合)  <br/> |64 ビット版の Office アプリを削除した場合は、32 ビット版クイック実行バージョンの Office 2016 をインストールする  <br/> |
|Office 2016 の MSI インストールがある (単体アプリの有無は関係ない)  <br/> |MSI Office 2016 をアンインストールする  <br/> |Office 2016 の 32 ビット版クイック実行バージョンをインストールする。単体アプリへの変更はなし  <br/> |
|既存の Office 2013 (以前) の MSI インストールおよび/または単体の Office アプリ  <br/> |なし  <br/> |Office 2016 の 32 ビット版クイック実行バージョンと既存の MSI Office インストール (および単体アプリ) が共存する  <br/> |
||||
   
 **(\*) 注:** 既知の問題により、Office 2016 の 32 ビット版クイック実行バージョンにはアップグレードされません。 修正が進行中です。 
  
