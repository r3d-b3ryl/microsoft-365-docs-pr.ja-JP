---
title: AutoPilot プロファイルの設定について
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 99bfbf81-e719-4630-9b0f-c187edfa1f8a
description: 自動操縦プロファイルは、ユーザーデバイスへの Windows のインストール方法を制御するのに役立ちます。 プロファイルには、Cortana のインストールをスキップするなどの、既定の設定とオプションの設定が含まれています。
ms.openlocfilehash: 5c2ec3f4c3e0ebc4ea545d11f819c897f414ad52
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43627416"
---
# <a name="about-autopilot-profile-settings"></a>AutoPilot プロファイルの設定について

## <a name="autopilot-profile-settings"></a>自動操縦プロファイルの設定

自動操縦プロファイルを使用して、ユーザーデバイスへの Windows のインストール方法を制御できます。 プロファイルには、次の設定が含まれています。
  
 **自動操縦既定の機能 (必須) は、自動的に設定されます。**
  
|**設定**|**説明**|
|:-----|:-----|
|Cortana、OneDrive、OEM 登録をスキップする  <br/> |Cortana や個人用 OneDrive のようなコンシューマーアプリのインストールをスキップします。 デバイスユーザーは、ユーザーがデバイスのローカル管理者である限り、これらを後でインストールすることができます。 デバイスは Microsoft 365 Business Premium で管理されるため、元の製造元の登録はスキップされます。  <br/> |
|会社のブランドが表示されたサインイン画面  <br/> |会社で[Microsoft 365 サインインページに会社のブランドを追加](https://support.office.com/article/a1229cdb-ce19-4da5-90c7-2b9b146aef0a)すると、デバイスのユーザーはサインインしたときにそのような操作を受けることができます。  <br/> |
|構成済み AAD アカウントを使用した MDM 自動登録  <br/> |ユーザー id は Azure Active Directory によって管理され、ユーザーは Microsoft 365 Business Premium 資格情報を使用して Windows と Microsoft 365 にサインインします。  <br/> |
   
 **オプションの設定:**
  
|**設定**|**説明**|
|:-----|:-----|
|プライバシーの設定のスキップ (既定ではオフ)  <br/> |このオプションが [ **オン**] に設定されている場合は、デバイス ユーザーが最初にサインインしたときに、デバイスと Windows の使用許諾契約書が表示されません。  <br/> |
|ユーザーがローカル管理者になることを許可しない  <br/> |このオプションが [ **オン**] に設定されている場合、デバイス ユーザーは Cortana などの個人用アプリをインストールできません。<br/> |
   
