---
title: ユーザー用WindowsデバイスをMicrosoft 365 Business Premiumする
f1.keywords:
- CSH
ms.author: deniseb
author: denisebmsft
manager: scotv
audience: Admin
ms.topic: article
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
- TRN_M365B
- OKR_SMB_Videos
- seo-marvel-mar
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
- adminvideo
search.appverid:
- BCS160
- MET150
ms.assetid: 2d7ff45e-0da0-4caa-89a9-48cabf41f193
description: ユーザーにWindowsデバイスWindows 10 ProをMicrosoft 365 Business Premium、一元的な管理とセキュリティ制御を有効にします。
ms.openlocfilehash: f64114ac6a117ac3eacc9b6aa9de31366e847f33
ms.sourcegitcommit: 601ab9ad2b624e3b5e04eed927a08884c885c72a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2022
ms.locfileid: "64403591"
---
# <a name="set-up-windows-devices-for-microsoft-365-business-premium-users"></a>ユーザー用WindowsデバイスをMicrosoft 365 Business Premiumする

## <a name="before-you-begin"></a>はじめに

Microsoft 365 Business Premium ユーザー用に Windows デバイスをセットアップする前に、すべての Windows デバイスが Windows 10 Pro バージョン 1703 (Creators Update) または Windows 11 Pro を実行Pro。 

Windows 10 Pro (または Windows 11 Pro) は、Windows 10 Business を展開する前提条件であり、Windows 10 Pro と Windows 11 を補完する一連のクラウド サービスとデバイス管理機能Proをクリックし、サーバーの一元管理とセキュリティ制御をMicrosoft 365 Business Premium。

[詳細については、Microsoft 365 Business Premium](https://www.microsoft.com/microsoft-365/business/microsoft-365-business-premium?activetab=pivot:techspecstab)。

## <a name="windows-10-pro-and-windows-11-pro"></a>Windows 10 Proおよび Windows 11 Pro

Windows 7 Pro、Windows 8 Pro、Windows 8.1 Pro など、Windows の以前のバージョンを実行している Microsoft 365 Business Premium デバイスがある場合は、Microsoft 365 Business Premium サブスクリプションにアクセスする権限があります。 Windowsこれらのデバイスを 11 Windows 10 Proまたは 11 WindowsにアップグレードPro。
  
デバイスをアップグレードする方法の詳細についてはWindows記事を参照してください。

- [ホームを WindowsにアップグレードWindows Pro](https://support.microsoft.com/windows/upgrade-windows-home-to-windows-pro-ef34d520-e73f-3198-c525-d1a218cc2818)
- [Windows 10 Pro にアップグレードする](https://support.microsoft.com/windows/upgrade-to-windows-10-pro-71ecc746-0f81-a4c0-bd4b-0db8559e0796)
  
アップグレードが完了した後は、「デバイスが Azure ADに接続されていることを確認する」を[参照](#verify-the-device-is-connected-to-azure-ad)して、アップグレードを確認するか、アップグレードが正常に動作したのを確認してください。

## <a name="join-windows-devices-to-your-organizations-azure-ad"></a>組織Windowsデバイスに参加Azure AD

すべての会社の Windows デバイスが Windows 10 Pro または Windows 11 Pro を実行している場合は、これらのデバイスを組織の Azure Active Directory (Azure AD) に参加できます。 

1. デバイスでWindowsロゴを選択Windowsし、次に [設定] アイコンをクリックします。
  
2. [**設定** アカウント アクセスの作業 **または** > **学校の管理] に移動Connect**\>。
  
3. メール アドレスを入力し、[次へ] を **選択します**。

4. プロンプトに従ってプロセスを完了します。

## <a name="verify-the-device-is-connected-to-azure-ad"></a>デバイスが Azure AD に接続されていることを確認する

同期の状態を確認するには、設定  の [仕事または学校にアクセスする] ページで **、[** 接続済み **] _** \<organization name\> 領域を選択して、[**情報**] と [切断] ボタンを表示 **します**。 [ **情報] を** 選択して同期の状態を取得します。 
  
[同期の **状態] ページで** 、[ **同期] を** 選択して、最新のモバイル デバイス管理ポリシーを PC に取得します。  
  
## <a name="next-steps"></a>次の手順

モバイル デバイスを設定するには、「モバイル デバイスをユーザーに設定する[Microsoft 365 Business Premiumを参照してください](set-up-mobile-devices.md)。 

保護を強化するには、「ビジネス プランのセキュリティ保護方法の上位 [10 Microsoft 365」を参照してください](../security-and-compliance/secure-your-business-data.md)。
  
