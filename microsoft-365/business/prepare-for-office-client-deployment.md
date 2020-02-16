---
title: Microsoft 365 Business による Office クライアントの展開を準備する
f1.keywords:
- CSH
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
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: ed34fff3-2881-4ed4-9906-1ba6bb8dd804
description: 32ビット版の Office アプリを Windows 10 コンピューターに自動的にインストールして、更新したままにする方法について説明します。
ms.openlocfilehash: 0f8cd7df49ad627b190fad6737ec95a6d64d99d0
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42065110"
---
# <a name="prepare-for-office-client-deployment-by-microsoft-365-business"></a>Microsoft 365 Business による Office クライアントの展開を準備する

## <a name="prepare-to-automatically-install-office-apps-to-client-computers"></a>Office アプリをクライアント コンピューターに自動的にインストールするための準備

Microsoft 365 Business を使用して、Windows 10 コンピューターに32ビットの Office アプリを自動的にインストールし、更新プログラムを最新の状態に保つことができます。
  
自動インストールは、エンドユーザーのコンピューターが Windows 10 Business 上にあり、次の場合に最適に機能します。
  
- 既存の Office デスクトップ アプリ (Word、Excel、PowerPoint、Outlook、OneNote、Publisher、Access、OneDrive) がない。
    
    または
    
- Office のクイック実行の既存バージョンがインストールされている。
    
To determine if you have the Click-to-Run version of Office, in any Office app go to **File** \> **Account** ( **Office Account** in Outlook). 次の図に示すように**Office の更新プログラム**が表示された場合は、クイック実行を使用してインストールを実行しています。 
  
![Screenshot of Office updates in Office app Account](../media/e3439380-fa43-4ed6-ae5d-64851c297df5.png)
  
 **この機能を利用するメリット**
  
次の PC を持つエンドユーザー:
  
- Windows 10 Business ユーザー ライセンス、アクティブな Microsoft 365 Business ライセンス、および Windows 10 Creators Update が **あり** 、Azure Active Directory に参加している。 
    
- 64ビットの Office アプリ (例: Word、Excel、PowerPoint)**はありません**。 64ビットの Office アプリが必要な場合、この機能は、Microsoft の 365 Business 管理コンソールからの、64 2016 ビットのクイック実行バージョンの Office の起動をサポートしていないため、この機能は適していません。 
    
- 任意の 2016 Windows インストーラー (MSI) 単体アプリ (Visio や Project など) が **ない** 。 Microsoft 365 Business は office をクイック実行バージョンの Office 2016 にアップグレードします。これは Office 2016 MSI スタンドアロンアプリでは動作しません。 
    
次の表に、エンドユーザーまたは管理者が、その開始状態に応じて、Microsoft 365 Business 管理コンソールから Office 展開の32ビットクイック実行バージョンを正常にインストールするために必要となる可能性のあるアクションを示します。
  
|**Office インストールの開始状態**|**Microsoft 365 Business Office のインストール前に行うアクション**|**終了状態**|
|:-----|:-----|:-----|
|Office スイート製品がインストールされない  <br/> |なし  <br/> |クイック実行を使用して Office 2016 32 ビットがインストールされている  <br/> |
|Office (2016 以前) の 32 ビット版クイック実行バージョンはあるが、単体アプリはない  <br/> |なし  <br/> |必要に応じて、最新の Office 2016 の 32 ビット版クイック実行バージョンにアップグレードする **\*** <br/> |
|既存のクイック実行32ビットバージョンの Office とクイック実行の32ビットバージョンまたは64ビットバージョンの Office アプリ (たとえば、Visio、Project)  <br/> |なし  <br/> |スタンドアロンアプリは影響を受けません。 スイート製品を Office 2016 の 32 ビット版クイック実行バージョンにアップグレードする  <br/> |
|Office の 32 ビット版クイック実行バージョンと、32 ビットまたは 64 ビット版 (2016 を除く) MSI の単体 Office アプリがある  <br/> |なし  <br/> |スタンドアロンアプリは影響を受けません。 スイート製品を Office 2016 の 32 ビット版クイック実行バージョンにアップグレードする  <br/> ||||
|任意の Office の 64 ビット版クイック実行バージョンがある  <br/> |64ビット版の Office アプリをアンインストールしても、32ビットの Office アプリに置き換えられる場合は、アンインストールします。  <br/> |64 ビット版の Office アプリを削除した場合は、32 ビット版クイック実行バージョンの Office 2016 をインストールする  <br/> |
|Office 2016 の MSI インストールがある (単体アプリの有無は関係ない)  <br/> |MSI Office 2016 をアンインストールする  <br/> |Office 2016 の 32 ビット版クイック実行バージョンをインストールする。単体アプリへの変更はなし  <br/> |
|既存の Office 2013 (以前) の MSI インストールおよび/または単体の Office アプリ  <br/> |なし  <br/> |Office 2016 の 32 ビット版クイック実行バージョンと既存の MSI Office インストール (および単体アプリ) が共存する  <br/> |
||||
   
 **(\*) 注:** 既知の問題により、Office 2016 の 32 ビット版クイック実行バージョンにはアップグレードされません。 修正が進行中です。 
  
