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
ms.openlocfilehash: 16675317136af9dc03c3bddf88fca954ff72bce1
ms.sourcegitcommit: adea59259a5900cad5de29ddf46d1ca9e9e1c82f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/04/2022
ms.locfileid: "64635373"
---
# <a name="about-autopilot-profile-settings"></a>AutoPilot プロファイルの設定について

## <a name="autopilot-profile-settings"></a>AutoPilot プロファイルの設定

> [!NOTE]
> Microsoft Defender for Business 2022 年 3 月 1 日からMicrosoft 365 Business Premium顧客に展開しています。 この機能は、デバイスに追加のセキュリティ機能を提供します。 [Defender for Business の詳細については、「Defender for Business」を参照してください](../security/defender-business/mdb-overview.md)。

AutoPilot プロファイルを使用して、ユーザー デバイスWindows方法を制御できます。 プロファイルには、次の設定が含まれています。
  
## <a name="autopilot-default-features-required-that-are-set-automatically"></a>自動設定される AutoPilot の既定の機能 (必須)
  
| 設定 | 説明 |
|:-----|:-----|
|[Cortana、OneDrive、OEM 登録をスキップする  |アプリや個人用アプリなど、コンシューマー アプリのインストールCortanaスキップOneDrive。 デバイスユーザーは、ユーザーがデバイスのローカル管理者である限り、後でこれらをインストールできます。 デバイスはユーザーによって管理されるので、元の製造元の登録はスキップMicrosoft 365 Business Premium。  |
|会社のブランドが表示されたサインイン画面  |会社に [会社の[](../admin/setup/customize-sign-in-page.md)ブランドをサインインに追加Microsoft 365] ページがある場合、デバイス ユーザーはサインイン時にそのエクスペリエンスを取得します。  |
|構成済み AAD アカウントを使用した MDM 自動登録  |ユーザー ID は Azure Active Directory によって管理され、ユーザーは自分の資格情報を使用して Windows および Microsoft 365にMicrosoft 365 Business Premiumします。  |

## <a name="optional-settings"></a>オプションの設定
  
| 設定 | 説明 |
|:-----|:-----|
|プライバシーの設定のスキップ (既定ではオフ)  |このオプションが [ **オン**] に設定されている場合は、デバイス ユーザーが最初にサインインしたときに、デバイスと Windows の使用許諾契約書が表示されません。  |
|ユーザーがローカル管理者になることを許可しない  |このオプションが [ **オン**] に設定されている場合、デバイス ユーザーは Cortana などの個人用アプリをインストールできません。|

## <a name="see-also"></a>関連項目

[ビジネス プランのセキュリティをMicrosoft 365するトップ 10 の方法](../admin/security-and-compliance/secure-your-business-data.md)