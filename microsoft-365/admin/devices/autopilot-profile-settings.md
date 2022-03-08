---
title: AutoPilot プロファイルの設定について
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: conceptual
f1.keywords:
- ZTDProfileSettings
- O365E_ZTDProfileSettings
- BCS365_ZTDProfileSettings
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
- Adm_TOC
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
description: AutoPilot プロファイルは、ユーザー デバイスにインストールWindows方法を制御するのに役立ちます。 プロファイルには、インストールのスキップなど、既定の設定とオプションCortanaがあります。
ms.openlocfilehash: d0b1a15ef8279234868b94ab5c16e449a54cf62f
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63313875"
---
# <a name="about-autopilot-profile-settings"></a>AutoPilot プロファイルの設定について

## <a name="autopilot-profile-settings"></a>AutoPilot プロファイルの設定

> [!NOTE]
> Microsoft Defender for Business は、2022 年 3 月 1 日からMicrosoft 365 Business Premium顧客に展開しています。 この機能は、デバイスに追加のセキュリティ機能を提供します。 [Defender for Business の詳細については、「Defender for Business」を参照してください](../../security/defender-business/mdb-overview.md)。

AutoPilot プロファイルを使用して、ユーザー デバイスWindows方法を制御できます。 プロファイルには、次の設定が含まれています。
  
 **自動で設定される AutoPilot の既定の機能 (必須)。**
  
|**設定**|**説明**|
|:-----|:-----|
|[Cortana、OneDrive、OEM 登録をスキップする  <br/> |アプリや個人用アプリなど、コンシューマー アプリのインストールCortanaスキップOneDrive。 デバイスユーザーは、ユーザーがデバイスのローカル管理者である限り、後でこれらをインストールできます。 デバイスはユーザーによって管理されるので、元の製造元の登録はスキップMicrosoft 365 Business Premium。  <br/> |
|会社のブランドが表示されたサインイン画面  <br/> |会社に [会社の[](../setup/customize-sign-in-page.md)ブランドをサインインに追加Microsoft 365] ページがある場合、デバイス ユーザーはサインイン時にそのエクスペリエンスを取得します。  <br/> |
|構成済み AAD アカウントを使用した MDM 自動登録  <br/> |ユーザー ID は Azure Active Directory によって管理され、ユーザーは自分の資格情報を使用して Windows および Microsoft 365にMicrosoft 365 Business Premiumします。  <br/> |
   
 **オプションの設定:**
  
|**設定**|**説明**|
|:-----|:-----|
|プライバシーの設定のスキップ (既定ではオフ)  <br/> |このオプションが [ **オン**] に設定されている場合は、デバイス ユーザーが最初にサインインしたときに、デバイスと Windows の使用許諾契約書が表示されません。  <br/> |
|ユーザーがローカル管理者になることを許可しない  <br/> |このオプションが [ **オン**] に設定されている場合、デバイス ユーザーは Cortana などの個人用アプリをインストールできません。<br/> |

## <a name="see-also"></a>関連項目

[ビジネス プランのセキュリティをMicrosoft 365するトップ 10 の方法](../security-and-compliance/secure-your-business-data.md)