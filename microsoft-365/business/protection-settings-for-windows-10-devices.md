---
title: Windows 10 デバイスのアプリケーション保護設定を設定する
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
f1_keywords:
- Win10AppPolicy
- O365E_Win10AppPolicy
- BCS365_Win10AppPolicy
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 02e74022-44af-414b-9d74-0ebf5c2197f0
description: アプリの管理ポリシーを作成し、ユーザーの個人用 Windows 10 デバイス上の作業ファイルを保護する方法について説明します。
ms.openlocfilehash: c3e003205da30fa79069946960ef00e4195f0cbc
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "44386539"
---
# <a name="set-application-protection-settings-for-windows-10-devices"></a>Windows 10 デバイスのアプリケーション保護設定を設定する

## <a name="create-an-app-management-policy-for-windows-10"></a>Windows 10 用のアプリの管理ポリシーを作成する

ユーザーが作業タスクを実行する個人の Windows 10 デバイスを持っている場合、それらのデバイスでもデータを保護することができます。
  
1. <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> で管理センターにアクセスします。 
    
2. 左側のナビゲーションで、[**デバイス**ポリシーの追加] を選択し \> **Policies** \> **Add**ます。

3. [ **ポリシーの追加**] ウィンドウで、このポリシーの一意の名前を入力します。 
    
4. [ **ポリシーの種類**] で、[ **Windows 10 のアプリケーション管理**] を選びます。
    
5. [**デバイスの種類**] で、[**個人**] または [**会社所有**] のどちらかを選択します。
    
6. [ **作業ファイルを暗号化する**] が自動的にオンになります。 
    
7. 作業ファイルをユーザーの PC に保存させたくない場合は、[ **ユーザーが会社のデータを個人用のファイルにコピーすることを防止し、作業ファイルを OneDrive for Business に保存するようユーザーに強制します**] を **オン**に設定します。 
    
9. **[Windows デバイス上のデータの回復] を**展開します。 これをオンにすることをお勧め**します。**
    
    データ回復エージェント証明書を先に作成してから、その場所を参照します。 手順については、「[暗号化ファイルシステム (EFS) データ回復エージェント (DRA) 証明書を作成および検証する](https://go.microsoft.com/fwlink/p/?linkid=853700)」を参照してください。
    
    既定では、デバイスに保存されていてユーザーのプロファイルに関連付けられている秘密キーを使用して、作業ファイルの暗号化が行われます。 該当するユーザーのみがファイル開き、暗号化を解除することができます。 ただし、デバイスが失われたり、ユーザーが削除されたりした場合、ファイルを暗号化された状態に留めておくことができます。 管理者は、データ回復エージェント (DRA) 証明書を使用して、ファイルの暗号化を解除できます。
    
    ![Browse to Data Recovery Agent certificate.](../media/7d7d664f-b72f-4293-a3e7-d0fa7371366c.png)
  
10. 追加のドメインまたは SharePoint Online の場所を追加して、一覧表示されているすべてのアプリのファイルが保護されるようにする場合は、 **[追加のネットワークとクラウドの場所を保護**する] を展開します。 いずれかのフィールドに複数の項目を入力する必要がある場合は、項目間にセミコロン (;) を使用します。
    
    ![Expand Protect additional network and cloud locations, and enter domains or SharePoint Online sites you own.](../media/7afaa0c7-ba53-456d-8c61-312c45e09625.png)
  
11. Next decide **Who will get these settings?** If you don't want to use the default **All Users** security group, choose **Change**, choose the security groups who will get these settings \> **Select**.
    
12. 最後に、[ **追加**] を選択してポリシーを保存し、それをデバイスに割り当てます。 
