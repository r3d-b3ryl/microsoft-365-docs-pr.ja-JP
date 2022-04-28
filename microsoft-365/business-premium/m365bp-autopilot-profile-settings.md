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
ms.localizationpriority: high
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
description: AutoPilot プロファイルは、Windows をユーザー デバイスにインストールする方法を制御するのに役立ちます。 プロファイルには、Cortana のインストールをスキップするなどの既定の設定とオプションの設定が含まれています。
ms.openlocfilehash: 9cfacb4ca69f8a674a50cfd5946e6a095433aed9
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65090647"
---
# <a name="about-autopilot-profile-settings"></a>AutoPilot プロファイルの設定について

## <a name="autopilot-profile-settings"></a>AutoPilot プロファイルの設定について

> [!NOTE]
> Microsoft Defender for Business は、2022 年 3 月 1 日以降、Microsoft 365 Business Premium のお客様に展開されます。 このオファリングでは、デバイスに追加のセキュリティ機能が提供されます。 [Defender for Business の詳細については、こちらをご覧ください](../security/defender-business/mdb-overview.md)。

AutoPilot プロファイルを使用して、ユーザー デバイスに Windows をインストールする方法を制御することができます。プロファイルには、次の設定が含まれています。
  
## <a name="autopilot-default-features-required-that-are-set-automatically"></a>自動的に設定される AutoPilot の既定の機能 (必須)
  
| Setting | 説明 |
|:-----|:-----|
|Cortana、OneDrive、OEM の登録のスキップ  |Cortana や個人用 OneDrive のようなコンシューマー アプリのインストールがスキップされます。デバイス ユーザーがデバイスのローカル管理者である場合は、後でインストールできます。デバイスは Microsoft 365 Business Premium によって管理されるため、元の製造元の登録はスキップされます。  |
|会社のブランドが表示されたサインイン画面  |会社に、[[会社のブランドを Microsoft 365 サインインに追加する] ページ](../admin/setup/customize-sign-in-page.md)がある場合、サインインしたデバイス ユーザーにはそのページが表示されます。  |
|構成済み AAD アカウントを使用した MDM 自動登録  |ユーザー ID は Azure Active Directory によって管理され、ユーザーは Microsoft 365 Business Premium 資格情報を使って Windows と Microsoft 365 にサインインします。  |

## <a name="optional-settings"></a>オプションの設定
  
| Setting | 説明 |
|:-----|:-----|
|プライバシーの設定のスキップ (既定ではオフ)  |このオプションが [ **オン**] に設定されている場合は、デバイス ユーザーが最初にサインインしたときに、デバイスと Windows の使用許諾契約書が表示されません。  |
|ユーザーがローカル管理者になることを許可しない  |このオプションが [ **オン**] に設定されている場合、デバイス ユーザーは Cortana などの個人用アプリをインストールできません。|

## <a name="see-also"></a>関連項目

[ビジネス プラン用に Microsoft 365 をセキュリティで保護する上位 10 の方法](../admin/security-and-compliance/secure-your-business-data.md)