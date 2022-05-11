---
title: Microsoft 365 Business Premium ユーザーのWindows デバイスを設定する
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
description: Microsoft 365 Business Premium ユーザーに対してWindows 10 Proを実行するWindows デバイスを設定し、一元管理とセキュリティ制御を有効にします。
ms.openlocfilehash: b9c8a5eb724a74959983e86dcdcb8f2f8f96b540
ms.sourcegitcommit: 7dc7e9fd76adf848f941919f86ca25eecc704015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2022
ms.locfileid: "65318582"
---
# <a name="set-up-windows-devices-for-microsoft-365-business-premium-users"></a>Microsoft 365 Business Premium ユーザーのWindows デバイスを設定する

## <a name="before-you-begin"></a>はじめに

Microsoft 365 Business Premium ユーザー用にWindows デバイスを設定する前に、すべてのWindows デバイスがWindows 10 Proバージョン 1703 (Creators Update) またはWindows 11 Proを実行していることを確認します。 

Windows 10 Pro (またはWindows 11 Pro) は、Windows 10 Businessをデプロイするための前提条件です。これは、Windows 10 ProとWindows 11 Proを補完する一連のクラウド サービスとデバイス管理機能です。を使用して、Microsoft 365 Business Premiumの一元管理とセキュリティ制御を有効にします。

[Microsoft 365 Business Premiumの要件について詳しくは、こちらを参照してください](https://www.microsoft.com/microsoft-365/business/microsoft-365-business-premium?activetab=pivot:techspecstab)。

## <a name="windows-10-pro-and-windows-11-pro"></a>Windows 10 ProとWindows 11 Pro

以前のバージョンのWindows (Windows 7 Pro、Windows 8 Pro、Windows 8.1 Proなど) を実行しているWindowsデバイスがある場合、Microsoft 365 Business Premium サブスクリプションはユーザーに対して、次の権限を付与します。これらのデバイスをWindows 10 ProまたはWindows 11 Proにアップグレードします。
  
Windows デバイスをアップグレードする方法の詳細については、次の記事を参照してください。

- [Windows ホームをWindows Proにアップグレードする](https://support.microsoft.com/windows/upgrade-windows-home-to-windows-pro-ef34d520-e73f-3198-c525-d1a218cc2818)
- [Windows 10 Pro にアップグレードする](https://support.microsoft.com/windows/upgrade-to-windows-10-pro-71ecc746-0f81-a4c0-bd4b-0db8559e0796)
  
アップグレードが完了したら、「 [デバイスが Azure AD に接続されていることを確認する](#verify-the-device-is-connected-to-azure-ad) 」を参照して、アップグレードがあることを確認するか、アップグレードが機能していることを確認します。

## <a name="join-windows-devices-to-your-organizations-azure-ad"></a>Windowsデバイスを組織の Azure AD に参加させる

会社のすべてのWindows デバイスがWindows 10 ProまたはWindows 11 Pro実行されている場合は、これらのデバイスを組織のAzure Active Directory (Azure AD) に参加させることができます。 

1. Windows デバイスで、Windows ロゴを選択し、設定 アイコンを選択します。
  
2. **設定** で、**AccountsAccess** >  **の職場または学校** \> **のConnect** に移動します。
  
3. メール アドレスを入力し、[ **次へ**] を選択します。

4. プロンプトに従ってプロセスを完了します。

## <a name="verify-the-device-is-connected-to-azure-ad"></a>デバイスが Azure AD に接続されていることを確認する

同期の状態を確認するには、**設定** の [**職場または学校へのアクセス**] ページで [**接続済み**] _ \<organization name\> 領域を選択して、[**情報**] と **[切断**] ボタンを公開します。 [ **情報]** を選択して同期状態を取得します。 
  
[ **同期の状態** ] ページで、[ **同期** ] を選択して、PC に最新のモバイル デバイス管理ポリシーを取得します。  
  
## <a name="next-steps"></a>次の手順

モバイル デバイスを設定するには、「[Microsoft 365 Business Premium ユーザー向けのモバイル デバイスのセットアップ](set-up-mobile-devices.md)」を参照してください。 

保護を強化するには、「[ビジネス プランのMicrosoft 365をセキュリティで保護するためのベスト プラクティス」を](../security-and-compliance/secure-your-business-data.md)参照してください。
  

