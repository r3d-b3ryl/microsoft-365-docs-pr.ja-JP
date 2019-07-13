---
title: Azure Active Directory テナントの詳細
description: このトピックでは、Microsoft マネージドデスクトップに登録するときに AAD アカウントに加えられた変更について説明します。
keywords: Microsoft マネージドデスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.openlocfilehash: 6b2b30d8dedba1086bfa9268fb0fdbce20367c20
ms.sourcegitcommit: dd426c686b52cf79325f11022b2d99bc45285577
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2019
ms.locfileid: "35643948"
---
# <a name="azure-active-directory-tenant-details"></a>Azure Active Directory テナントの詳細
{gory (アカウント、API 呼び出し、アクセス許可など) についての詳細。


## <a name="data-transmitted-to-and-from-your-aad-account"></a>AAD アカウントとの間で転送されるデータ


Microsoft からアカウントに送信されるデータは次のとおりです。

- グループ名
- セキュリティポリシーの構成
- デバイスの注文
- ユーザーアカウント (msadmin、mstest、mwaas_soc_ro、mwaas_wdgsoc)
- ユーザーアカウントへの E5 ライセンスの割り当て
- 更新リングの Windows update ポリシー

お客様のアカウントから Microsoft に送信されるデータは次のとおりです。

- デバイスの更新、使用状況、および信頼性のデータ
- アプリの展開と信頼性のデータ
- 更新およびセキュリティポリシーの展開データ
- デバイスに割り当てられているユーザー  

アカウントから送信されるデータは、米国でホストされている Microsoft テナントの Azure SQL データベースに格納されます。 データは、「Microsoft Azure セキュリティ}」に記載されているポリシーに従って保存および処理されます。 

## <a name="api-permissions-and-calls"></a>API のアクセス許可と呼び出し

**登録中:**

API のアクセス許可:
- DeviceManagementServiceConfig.ReadWrite.All
- Directory.AccessAsUser.All
- User.ReadWrite.All
- DeviceManagementConfiguration.ReadWrite.All
- DeviceManagementManagedDevices.ReadWrite.All
- Group.ReadWrite.All

API 呼び出し:
- POST/organization/{organizationId}/setMobileDeviceManagementAuthority
- メンバーの取得/投稿/ディレクトリの取得/{2}
- GET/POST/users
- 取得/投稿/グループ
- PATCH/グループ/{* id}
- 取得/ポスト/Devicemanagement/deviceconfigurた。
- /DeviceManagement/detectedApps を取得する

**登録後、通常の管理では、次のようになります。**

API のアクセス許可:
- DeviceManagementManagedDevices.ReadWrite.All
- DeviceManagementApps.ReadWrite.All
- DeviceManagementConfiguration.ReadWrite.All
- Reports.Read.All
- User.ReadWrite.All
- Group.ReadWrite.All
- Directory.AccessAsUser.All

API 呼び出し:
- メンバーの取得/投稿/ディレクトリの取得/{2}
- GET/PATCH/POST/users
- 取得/投稿/グループ
- PATCH/グループ/{* id}
- 取得/ポスト/Devicemanagement/deviceconfigurた。
- GET/POST/deviceAppManagement/mobileApps
- /DeviceManagement/detectedApps を取得する
- /Devices を取得する
- 投稿/ユーザー/{id | userPrincipalName}/割り当てライセンス
- /SubscribedSkus を取得する

## <a name="accounts-used-by-microsoft-managed-desktop"></a>Microsoft マネージドデスクトップで使用されるアカウント





| アカウント | 説明  | 条件付きアクセス  | 多要素認証  | これが OK な理由 |
|---------|---------|---------|---------|--------------|
| msadmin @ * onmmicrosoft .com | 管理者特権を持つ制限付きサービスアカウント。 Microsoft Intune およびユーザー管理者として使用されます。 {これは何ですか?} Microsoft モダンデスクトップデバイスのテナントを定義して構成するにはには、対話的なログイン権限がありません。サービスを使用してのみ操作を実行します。  | ネットワークで発生しないため、除外されます。        | 対話型ログオンがないため、除外されます。        | Azure Key Vault に格納されたパスワード |
| mstest @ * onmmicrosoft .com     |         |         |         |
| mssupport @ * onmmicrosoft .com     |         |         |         |
| msadminint @ * onmmicrosoft .com     |         |         |         |
