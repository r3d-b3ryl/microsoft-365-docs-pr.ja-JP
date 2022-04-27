---
title: デバイスのアプリケーション保護設定を編集またはWindows 10する
ms.author: deniseb
author: denisebmsft
manager: scotv
audience: Admin
ms.topic: article
f1.keywords:
- Win10AppPolicy
- O365E_Win10AppPolicy
- BCS365_Win10AppPolicy
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- M365-identity-device-management
- Adm_TOC
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
description: アプリ管理ポリシーを作成または編集し、ユーザーの個人用デバイスで作業ファイルを保護するWindows 10します。
ms.openlocfilehash: 4c8393954d7f1cc1a8083221021cdc21b9921432
ms.sourcegitcommit: adea59259a5900cad5de29ddf46d1ca9e9e1c82f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/04/2022
ms.locfileid: "64635365"
---
# <a name="set-or-edit-application-protection-settings-for-windows-10-devices"></a>デバイスのアプリケーション保護設定を設定またはWindows 10する

この記事は、ユーザーにMicrosoft 365 Business Premium。

> [!NOTE]
> Microsoft Defender for Business 2022 年 3 月 1 日からMicrosoft 365 Business Premium顧客に展開しています。 この機能は、デバイスに追加のセキュリティ機能を提供します。 [Defender for Business の詳細については、「Defender for Business」を参照してください](../security/defender-business/mdb-overview.md)。

## <a name="edit-an-app-management-policy-for-windows-10"></a>アプリの管理ポリシーを編集Windows 10

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> の管理センターにアクセスします。     

2. 左側のナビゲーションで、[デバイス ポリシー **] を** \> **選択します** 。

3. 既存のアプリ ポリシーをWindowsし、[編集] を **クリックします**。

4. 変更 **する設定** の横にある [編集] を選択し、[保存] を **選択します**。

## <a name="create-an-app-management-policy-for-windows-10"></a>Windows 10 用のアプリの管理ポリシーを作成する

ユーザーが作業タスクを実行する個人の Windows 10 デバイスを持っている場合、それらのデバイスでもデータを保護することができます。
  
1. <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> から管理センターにアクセスします。 

2. 左側のナビゲーションで、[デバイス ポリシー **の追加]** \> **を選択** \> **します**。

3. [ **ポリシーの追加**] ウィンドウで、このポリシーの一意の名前を入力します。 

4. [ **ポリシーの種類**] で、[ **Windows 10 のアプリケーション管理**] を選びます。

5. [**デバイスの種類] で**、[個人] **または [会社****所有] を選択します**。

6. [ **作業ファイルを暗号化する**] が自動的にオンになります。 

7. 作業ファイルをユーザーの PC に保存させたくない場合は、[ **ユーザーが会社のデータを個人用のファイルにコピーすることを防止し、作業ファイルを OneDrive for Business に保存するようユーザーに強制します**] を **オン** に設定します。 

8. [デバイス **上のデータの回復Windows展開します**。 オンにすることをお勧 **めします**。
    データ回復エージェント証明書を先に作成してから、その場所を参照します。 手順については、「 [Create and verify an Encrypting File System (EFS) Data Recovery Agent (DRA) 証明書」を参照してください](/windows/security/information-protection/windows-information-protection/create-and-verify-an-efs-dra-certificate)。
    
    既定では、デバイスに保存されていてユーザーのプロファイルに関連付けられている秘密キーを使用して、作業ファイルの暗号化が行われます。 該当するユーザーのみがファイル開き、暗号化を解除することができます。 ただし、デバイスが失われたり、ユーザーが削除されたりした場合、ファイルを暗号化された状態に留めておくことができます。 管理者は、データ復旧エージェント (DRA) 証明書を使用してファイルを復号化できます。
    
    ![Browse to Data Recovery Agent certificate.](./../media/7d7d664f-b72f-4293-a3e7-d0fa7371366c.png)
  
9. [**追加のドメインまたは** SharePoint Online の場所を追加する場合は、[追加のネットワークとクラウドの場所を保護する] を展開して、一覧表示されているアプリのファイルが確実に保護されます。 いずれかのフィールドに複数の項目を入力する必要がある場合は、項目間にセミコロン (;) を使用します。
    
    ![Expand Protect additional network and cloud locations, and enter domains or SharePoint Online sites you own.](./../media/7afaa0c7-ba53-456d-8c61-312c45e09625.png)
  
11. Next decide **Who will get these settings?** If you don't want to use the default **All Users** security group, choose **Change**, choose the security groups who will get these settings \> **Select**.
12. 最後に、[ **追加**] を選択してポリシーを保存し、それをデバイスに割り当てます。

## <a name="see-also"></a>関連項目

[ビジネス プランのセキュリティをMicrosoft 365するトップ 10 の方法](../admin/security-and-compliance/secure-your-business-data.md)