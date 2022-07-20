---
title: 管理されたデバイスをセットアップする
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
ms.topic: how-to
ms.service: o365-administration
ms.localizationpriority: high
ms.date: 07/19/2022
ms.collection:
- M365-Campaigns
- m365solution-smb
ms.custom:
- MiniMaven
search.appverid:
- BCS160
- MET150
description: 管理されたデバイスをセットアップする方法
ms.openlocfilehash: a4298bcdc284f1957a1afa73cbc7ae8e3f15e7d1
ms.sourcegitcommit: c1eaea74c8ffce2f9f477c9469342e88e4a70c14
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2022
ms.locfileid: "66895011"
---
# <a name="set-up-managed-devices"></a>管理されたデバイスをセットアップする

"管理された" デバイスは、組織によって制御および監視されているため、定期的に更新され、安全です。 デバイスを管理下に置くことは重要な目標です。 これらのデバイスを制御できるようにするために、Microsoft Business Premium に含まれている Intune と Azure Active Directory でデバイス マネージャーに登録します。

1. [セットアップ ウィザード](../business/set-up.md)でデバイスとデータの保護ポリシーを設定します。

2. コンピューターを Microsoft 365 のユーザー名とパスワードを使用して [Azure Active Directory](../business/set-up-windows-devices.md) に接続しました。 

## <a name="enroll-devices-in-intune"></a>Intune でデバイスを登録する

1. Microsoft エンドポイント マネージャー管理センター ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) に移動してサインインします。

2. **[デバイス]** > **[デバイスを登録]** の順に選択します。 

   :::image type="content" source="media/m365bp-endpoint-manager-enroll-devices.png" alt-text="Microsoft エンドポイント マネージャーを使用してデバイスを登録します。"::: 

3. 以下の特定のデバイス登録ガイダンスに従ってください。

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

次のガイダンスを使用して、[デバイスを Defender for Business 機能にオンボーディング](m365bp-onboard-devices-mdb.md)します。

