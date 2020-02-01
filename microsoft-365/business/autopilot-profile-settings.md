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
ms.openlocfilehash: 1cc8a3171bbc4a1e5cb531b9364c7791586fc339
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "41593335"
---
# <a name="about-autopilot-profile-settings"></a>AutoPilot プロファイルの設定について

## <a name="autopilot-profile-settings"></a>自動操縦プロファイルの設定

自動操縦プロファイルを使用して、ユーザーデバイスへの Windows のインストール方法を制御できます。 プロファイルには、次の設定が含まれています。
  
 **自動操縦既定の機能 (必須) は、自動的に設定されます。**
  
|**設定**|**説明**|
|:-----|:-----|
|Cortana、OneDrive、OEM 登録をスキップする  <br/> |Cortana や個人用 OneDrive のようなコンシューマーアプリのインストールをスキップします。 デバイスユーザーは、ユーザーがデバイスのローカル管理者である限り、これらを後でインストールすることができます。 デバイスは Microsoft 365 Business によって管理されるため、元の製造元の登録はスキップされます。  <br/> |
|会社のブランドが表示されたサインイン画面  <br/> |会社に[Office 365 のサインインページに会社のブランドを追加](https://support.office.com/article/a1229cdb-ce19-4da5-90c7-2b9b146aef0a)することがある場合、デバイスユーザーはサインインしたときにそのような操作を取得します。  <br/> |
|構成済み AAD アカウントを使用した MDM 自動登録  <br/> |ユーザー id は Azure Active Directory によって管理され、ユーザーは Microsoft 365 Business 資格情報を使用して Windows および Office 365 にサインインします。  <br/> |
   
 **オプションの設定:**
  
|**設定**|**説明**|
|:-----|:-----|
|プライバシーの設定のスキップ (既定ではオフ)  <br/> |このオプションが [ **オン**] に設定されている場合は、デバイス ユーザーが最初にサインインしたときに、デバイスと Windows の使用許諾契約書が表示されません。  <br/> |
|ユーザーがローカル管理者になることを許可しない  <br/> |このオプションが [ **オン**] に設定されている場合、デバイス ユーザーは Cortana などの個人用アプリをインストールできません。<br/> |
   
