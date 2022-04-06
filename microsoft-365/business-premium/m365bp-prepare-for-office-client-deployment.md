---
title: クライアントによるクライアントOffice展開の準備をMicrosoft 365 Business Premium
f1.keywords:
- CSH
ms.author: efrene
author: efrene
manager: scotv
ms.date: 04/01/2022
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
ms.openlocfilehash: 2ed85916914e4f3ecfa9c7c5aeccb08eade1c006
ms.sourcegitcommit: adea59259a5900cad5de29ddf46d1ca9e9e1c82f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/04/2022
ms.locfileid: "64635308"
---
# <a name="prepare-for-office-client-deployment-by-microsoft-365-business-premium"></a>クライアントによるクライアントOffice展開の準備をMicrosoft 365 Business Premium

> [!NOTE]
> Microsoft Defender for Business 2022 年 3 月 1 日からMicrosoft 365 Business Premium顧客に展開しています。 この機能は、デバイスに追加のセキュリティ機能を提供します。 [Defender for Business の詳細については、「Defender for Business」を参照してください](../security/defender-business/mdb-overview.md)。

## <a name="prepare-to-automatically-install-office-apps-to-client-computers"></a>Office アプリをクライアント コンピューターに自動的にインストールするための準備

32 ビット Microsoft 365 Business Premium を使用して、32 ビット OfficeアプリをWindows 10更新プログラムで最新の状態に保つ。
  
自動インストールは、エンド ユーザーのコンピューターが次の場合に最適Windows 10 Business。
  
- 既存の Office デスクトップ アプリ (Word、Excel、PowerPoint、Outlook、OneNote、Publisher、Access、OneDrive) がない。
    
    または
    
- Office のクイック実行の既存バージョンがインストールされている。
    
To determine if you have the Click-to-Run version of Office, in any Office app go to **File** \> **Account** ( **Office Account** in Outlook). 次の図に **Office更新** プログラムが表示されている場合は、インストールは次の手順で行クイック実行。 
  
![アカウントのOffice更新プログラムOffice アプリスクリーンショット。](./../media/e3439380-fa43-4ed6-ae5d-64851c297df5.png)
  
 **Who機能の利点**
  
次の PC を持つエンドユーザー:
  
- **ユーザー** ライセンスWindows 10 Business、ビジネス ライセンスMicrosoft 365アクティブなライセンス、Windows 10 Creators Updateを持ち、Azure Active Directory。 
    
-  64 ビット アプリ (Word、Office、Excel など) をPowerPoint。 64 ビット Office アプリが必要な場合、ビジネス管理コンソール用の Microsoft 365 から 64 ビット 2016 クイック実行 バージョンの Office をトリガーするサポートがないので、この機能は適しています。 
    
- 任意の 2016 Windows インストーラー (MSI) 単体アプリ (Visio や Project など) が **ない** 。 Microsoft 365 2016 Office クイック実行 バージョンへのOffice アップグレードの場合、Office MSI スタンドアロン アプリでは動作しません。 
    
次の表に、Microsoft 365 for business 管理コンソールから 32 ビット クイック実行 バージョンの Office 展開を成功するために、エンド ユーザー/管理者が実行する必要があるアクションを示します。<br/>


|Office インストールの開始状態|ビジネス ユーザーがインストールするMicrosoft 365前に実行Officeアクション|最終的な状態|
|:-----|:-----|:-----|
|Office スイート製品がインストールされない  |なし  |Officeを使用して 2016 32 ビットがインストールクイック実行  |
|Office (2016 以前) の 32 ビット版クイック実行バージョンはあるが、単体アプリはない  |なし  |必要に応じて、最新の Office 2016 の 32 ビット版クイック実行バージョンにアップグレードする **\*** |
|既存クイック実行 32 ビット バージョンの Office および クイック実行 32 ビットまたは 64 ビットスタンドアロン Office アプリ (Visio、Project など)  |None  |スタンドアロン アプリは影響を受け取らない。 スイート製品を Office 2016 の 32 ビット版クイック実行バージョンにアップグレードする  |
|Office の 32 ビット版クイック実行バージョンと、32 ビットまたは 64 ビット版 (2016 を除く) MSI の単体 Office アプリがある  |なし  |スタンドアロン アプリは影響を受け取らない。 スイート製品を Office 2016 の 32 ビット版クイック実行バージョンにアップグレードする  |
|任意の Office の 64 ビット版クイック実行バージョンがある  |64 ビット アプリOfficeアンインストールする (32 ビット アプリに置き換Officeする  |64 ビット版の Office アプリを削除した場合は、32 ビット版クイック実行バージョンの Office 2016 をインストールする  |
|Office 2016 の MSI インストールがある (単体アプリの有無は関係ない)  |MSI Office 2016 をアンインストールする  |Office 2016 の 32 ビット版クイック実行バージョンをインストールする。単体アプリへの変更はなし  |
|既存の Office 2013 (以前) の MSI インストールおよび/または単体の Office アプリ  |なし  |Office 2016 の 32 ビット版クイック実行バージョンと既存の MSI Office インストール (および単体アプリ) が共存する  |
   
 **(\*) 注:** 既知の問題により、Office 2016 の 32 ビット版クイック実行バージョンにはアップグレードされません。 修正が進行中です。 
  