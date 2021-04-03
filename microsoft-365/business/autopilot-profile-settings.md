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
description: AutoPilot プロファイルは、Windows がユーザー デバイスにインストールされる方法を制御するのに役立ちます。 プロファイルには、Cortana のインストールをスキップするなど、既定とオプションの設定が含まれる。
ms.openlocfilehash: 86f8718131f0a0b93e18e65e39e02e7d65aded1a
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578509"
---
# <a name="about-autopilot-profile-settings"></a>AutoPilot プロファイルの設定について

## <a name="autopilot-profile-settings"></a>AutoPilot プロファイルの設定

AutoPilot プロファイルを使用して、ユーザー デバイスへの Windows のインストール方法を制御できます。 プロファイルには、次の設定が含まれています。
  
 **自動で設定される AutoPilot の既定の機能 (必須)。**
  
|**設定**|**説明**|
|:-----|:-----|
|Cortana、OneDrive、OEM 登録をスキップする  <br/> |Cortana や個人用 OneDrive のようなコンシューマー アプリのインストールをスキップします。 デバイスユーザーは、ユーザーがデバイスのローカル管理者である限り、後でこれらをインストールできます。 デバイスは Microsoft 365 Business Premium によって管理されるので、元の製造元の登録はスキップされます。  <br/> |
|会社のブランドが表示されたサインイン画面  <br/> |会社に [会社のブランドを [Microsoft 365](../admin/setup/customize-sign-in-page.md)サインインに追加する] ページがある場合、デバイス ユーザーはサインイン時にそのエクスペリエンスを取得します。  <br/> |
|構成済み AAD アカウントを使用した MDM 自動登録  <br/> |ユーザー ID は Azure Active Directory によって管理され、ユーザーは Microsoft 365 Business Premium 資格情報を使用して Windows と Microsoft 365 にサインインします。  <br/> |
   
 **オプションの設定:**
  
|**設定**|**説明**|
|:-----|:-----|
|プライバシーの設定のスキップ (既定ではオフ)  <br/> |このオプションが [ **オン**] に設定されている場合は、デバイス ユーザーが最初にサインインしたときに、デバイスと Windows の使用許諾契約書が表示されません。  <br/> |
|ユーザーがローカル管理者になることを許可しない  <br/> |このオプションが [ **オン**] に設定されている場合、デバイス ユーザーは Cortana などの個人用アプリをインストールできません。<br/> |
