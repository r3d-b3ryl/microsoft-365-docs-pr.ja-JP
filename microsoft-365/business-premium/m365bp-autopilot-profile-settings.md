---
title: Autopilot プロファイルの設定について
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
ms.topic: conceptual
f1.keywords:
- ZTDProfileSettings
- O365E_ZTDProfileSettings
- BCS365_ZTDProfileSettings
ms.service: o365-administration
ms.localizationpriority: high
ms.date: 07/19/2022
ms.collection: ''
ms.custom:
- MiniMaven
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
- MOE150
description: Autopilot プロファイルは、Windows をユーザー デバイスにインストールする方法を制御するのに役立ちます。 プロファイルには、Cortana のインストールをスキップするなどの既定の設定とオプションの設定が含まれています。
ms.openlocfilehash: 9fcec0d34a23a56943a1a17d7e7f74435910055e
ms.sourcegitcommit: c1eaea74c8ffce2f9f477c9469342e88e4a70c14
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2022
ms.locfileid: "66894725"
---
# <a name="about-autopilot-profile-settings"></a>Autopilot プロファイルの設定について

## <a name="autopilot-profile-settings"></a>AutoPilot プロファイルの設定について

Autopilot プロファイルを使用して、ユーザー デバイスへの Windows のインストール方法を制御できます。 プロファイルには、次の設定が含まれています。
  
## <a name="autopilot-default-features-required-that-are-set-automatically"></a>自動的に設定される Autopilot の既定の機能 (必須)
  
| 設定 | 説明 |
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

[ビジネス プランの Microsoft 365 をセキュリティで保護するためのベスト プラクティス](../admin/security-and-compliance/secure-your-business-data.md)