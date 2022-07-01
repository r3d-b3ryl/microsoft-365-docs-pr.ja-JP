---
title: 管理されたデバイスをセットアップする
f1.keywords:
- NOCSH
ms.author: v-kcirillo
author: cirilk
manager: dansimp
audience: Admin
ms.topic: how-to
ms.service: o365-administration
ms.localizationpriority: high
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-Campaigns
- m365solution-smb
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
description: 管理されたデバイスをセットアップする方法
ms.openlocfilehash: cd65c70f9ed9c2ec43196d792c81fa3e82f4e05d
ms.sourcegitcommit: 85799f0efc06037c1ff309fe8e609bbd491f9b68
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2022
ms.locfileid: "66573987"
---
# <a name="set-up-managed-devices"></a>管理されたデバイスをセットアップする

"管理された" デバイスは、組織によって制御および監視されているため、定期的に更新され、安全です。 デバイスを管理下に置くことは重要な目標です。 これらのデバイスを制御できるようにするために、Microsoft Business Premium に含まれている Intune と Azure Active Directory Premium を使用してデバイス マネージャーに登録されます。 

ユーザーが次の 2 つの手順を完了すると、Windows 10 または 11 PC は管理対象と見なされます。

1. [セットアップ ウィザード](../business/set-up.md)でデバイスとデータの保護ポリシーを設定します。

2. コンピューターを Microsoft 365 のユーザー名とパスワードを使用して [Azure Active Directory](../business/set-up-windows-devices.md) に接続しました。 

## <a name="enroll-devices-in-microsoft-endpoint-manager"></a>Microsoft エンドポイント マネージャーにデバイスを登録する

これで、エンドポイント マネージャーにデバイスを登録できます。 https://endpoint.microsoft.com に移動し、**[デバイス]** > **[デバイスの登録]** を選択します。 

:::image type="content" source="media/m365bp-endpoint-manager-enroll-devices.png" alt-text="Microsoft エンドポイント マネージャーを使用してデバイスを登録します。"::: 

以下の特定のデバイス登録ガイダンスに従ってください。

### <a name="for-windows-enrollment"></a>Windows 登録の場合:

1. **[Windows]** > **[Windows 登録]** の順に選択します。 

2. リストされている登録方法から、**[自動登録]** を選択します。

### <a name="for-ios-enrollment"></a>iOS 登録の場合:

1. **[iOS]** > **[iOS 登録]** の順に選択します。

2. ポリシーのリストからポリシーを選択して、その詳細を確認します。

3. **[プロパティ]** を選択して、ポリシーを管理します。

4. **[設定]** > **[システム セキュリティ]** の順に選択し、Intune でセキュリティの詳細を構成します。

5. 構成プロファイルを確認します。 

6. プロファイルを作成し、必要に応じて組織内のデバイスにプッシュします。

### <a name="for-android-enrollment"></a>Android 登録の場合:

1. **[Android]** > **[Android 登録]** の順に選択します。

2. **[管理対象 Google Play]** を選択し、Microsoft に対し、情報を Google に送信するアクセス許可を付与します。

## <a name="next-objective"></a>次の目標

次のガイダンスを使用して、[デバイスをオンボードします](m365bp-onboard-devices-mdb.md)。

