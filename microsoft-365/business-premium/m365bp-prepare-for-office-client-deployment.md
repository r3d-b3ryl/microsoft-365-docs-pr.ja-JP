---
title: Microsoft 365 Business Premium による Office クライアントの展開を準備する
f1.keywords:
- CSH
ms.author: efrene
author: efrene
manager: scotv
ms.date: 04/01/2022
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: high
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
description: 32 ビット Office アプリを Windows 10 コンピューターに自動的にインストールし、最新の状態に保つ方法を学びます。
ms.openlocfilehash: 1b1aa1ba5f34528ea6e27fad38964b0fb952b287
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65090623"
---
# <a name="prepare-for-office-client-deployment-by-microsoft-365-business-premium"></a>Microsoft 365 Business Premium による Office クライアントの展開を準備する

> [!NOTE]
> Microsoft Defender for Business は、2022 年 3 月 1 日以降、Microsoft 365 Business Premium のお客様に展開されます。 このオファリングでは、デバイスに追加のセキュリティ機能が提供されます。 [Defender for Business の詳細については、こちらをご覧ください](../security/defender-business/mdb-overview.md)。

## <a name="prepare-to-automatically-install-office-apps-to-client-computers"></a>Office アプリをクライアント コンピューターに自動的にインストールするための準備

 Microsoft 365 Business Premium を使用すると、32 ビット版の Office アプリを Windows 10 コンピューターに自動的にインストールして、更新プログラムで最新状態に維持することができます。
  
自動インストールは、エンドユーザーのコンピューターで Windows 10 Business が実行されていて、なおかつ次の場合に最適です。
  
- 既存の Office デスクトップ アプリ (Word、Excel、PowerPoint、Outlook、OneNote、Publisher、Access、OneDrive) がない。
    
    または
    
- Office のクイック実行の既存バージョンがインストールされている。
    
Office のクイック実行バージョンがあるかどうかを判断するには、任意の Office アプリで **[ファイル]** \> **[アカウント]** (Outlook では **[Office アカウント]**) の順に移動します。**Office の更新プログラム** が次の図のように示される場合は、クイック実行を使用してインストールされています。 
  
![Office アプリ アカウントでの Office 更新のスクリーンショット](./../media/e3439380-fa43-4ed6-ae5d-64851c297df5.png)
  
 **この機能の恩恵を受けるユーザー**
  
次の PC を持つエンドユーザー:
  
- Windows 10 Business ユーザー ライセンス、アクティブな Microsoft 365 for Business ライセンス、および Windows 10 Creators Update が **あり**、Azure Active Directory に参加している。 
    
- 64 ビット版の Office アプリが **ない** (例: Word、Excel、PowerPoint) 場合。64 ビット版の Office アプリが必要な場合、この機能は適合しません。Microsoft 365 Business 管理コンソールから Office 2016 の 64 ビット版のクイック実行バージョンのトリガーがサポートされていないからです。 
    
- 任意の 2016 Windows インストーラー (MSI) 単体アプリ (Visio や Project など) が **ない場合**。Microsoft 365 Business では Office は Office 2016 のクイック実行バージョンにアップグレードされますが、これは Office 2016 MSI 単体アプリでは動作しません。 
    
次の表では、Microsoft 365 for Business 管理コンソールから 32 ビット版クイック実行バージョンの Office を正しく展開するために、開始状態に応じて、エンドユーザー/管理者が実行する必要のあるアクションを示します。<br/>


|Office インストールの開始状態|Microsoft 365 for Business Office のインストール前に行うアクション|最終的な状態|
|:-----|:-----|:-----|
|Office スイート製品がインストールされない  |なし  |クイック実行を使用して Office 2016 の 32 ビット版をインストールする  |
|Office (2016 以前) の 32 ビット版クイック実行バージョンはあるが、単体アプリはない  |なし  |必要に応じて、最新の Office 2016 の 32 ビット版クイック実行バージョンにアップグレードする **\*** |
|Office の 32 ビット版クイック実行バージョンと、32 ビットまたは 64 ビット版クイック実行の単体 Office アプリ (Visio、Project など) がある  |なし  |単体アプリは影響を受けません。スイート製品を Office 2016 の 32 ビット版クイック実行バージョンにアップグレードする  |
|Office の 32 ビット版クイック実行バージョンと、32 ビットまたは 64 ビット版 (2016 を除く) MSI の単体 Office アプリがある  |なし  |単体アプリは影響を受けません。スイート製品を Office 2016 の 32 ビット版クイック実行バージョンにアップグレードする  |
|任意の Office の 64 ビット版クイック実行バージョンがある  |32 ビット版の Office アプリに置き換えても問題ない場合は、64 ビット版の Office アプリをアンインストールする  |64 ビット版の Office アプリを削除した場合は、32 ビット版クイック実行バージョンの Office 2016 をインストールする  |
|Office 2016 の MSI インストールがある (単体アプリの有無は関係ない)  |MSI Office 2016 をアンインストールする  |Office 2016 の 32 ビット版クイック実行バージョンをインストールする。単体アプリへの変更はなし  |
|既存の Office 2013 (以前) の MSI インストールおよび/または単体の Office アプリ  |なし  |Office 2016 の 32 ビット版クイック実行バージョンと既存の MSI Office インストール (および単体アプリ) が共存する  |
   
 **(\*) 注:** 既知の問題により、Office 2016 の 32 ビット版クイック実行バージョンにはアップグレードされません。これは修正中です。 
  