---
title: AutoPilot プロファイルの設定について
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: conceptual
f1_keywords:
- ZTDProfileSettings
- O365E_ZTDProfileSettings
- BCS365_ZTDProfileSettings
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 99bfbf81-e719-4630-9b0f-c187edfa1f8a
description: AutoPilot プロファイルは、ユーザー デバイスにインストールWindows方法を制御するのに役立ちます。 プロファイルには、インストールのスキップなど、既定の設定とオプションCortana含まれる。
ms.openlocfilehash: 9d425e73a5cedf51ce8267afa9505cbde8b97038
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59176719"
---
# <a name="about-autopilot-profile-settings"></a>AutoPilot プロファイルの設定について

## <a name="autopilot-profile-settings"></a>AutoPilot プロファイルの設定

AutoPilot プロファイルを使用して、ユーザー デバイスWindows方法を制御できます。 プロファイルには、次の設定が含まれています。
  
 **自動で設定される AutoPilot の既定の機能 (必須)。**
  
|**設定**|**説明**|
|:-----|:-----|
|[Cortana、OneDrive OEM 登録をスキップする  <br/> |アプリや個人用アプリなど、コンシューマー アプリのインストールCortanaスキップOneDrive。 デバイスユーザーは、ユーザーがデバイスのローカル管理者である限り、後でこれらをインストールできます。 デバイスはユーザーによって管理されるので、元の製造元の登録はスキップMicrosoft 365 Business Premium。  <br/> |
|会社のブランドが表示されたサインイン画面  <br/> |会社に [会社[](../setup/customize-sign-in-page.md)のブランドをサインインに追加Microsoft 365] ページがある場合、デバイス ユーザーはサインイン時にそのエクスペリエンスを取得します。  <br/> |
|構成済み AAD アカウントを使用した MDM 自動登録  <br/> |ユーザー ID は Azure Active Directory によって管理され、ユーザーは自分の資格情報を使用して WindowsおよびMicrosoft 365にサインインMicrosoft 365 Business Premiumされます。  <br/> |
   
 **オプションの設定:**
  
|**設定**|**説明**|
|:-----|:-----|
|プライバシーの設定のスキップ (既定ではオフ)  <br/> |このオプションが [ **オン**] に設定されている場合は、デバイス ユーザーが最初にサインインしたときに、デバイスと Windows の使用許諾契約書が表示されません。  <br/> |
|ユーザーがローカル管理者になることを許可しない  <br/> |このオプションが [ **オン**] に設定されている場合、デバイス ユーザーは Cortana などの個人用アプリをインストールできません。<br/> |
