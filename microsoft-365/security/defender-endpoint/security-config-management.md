---
title: Microsoft エンドポイント マネージャーを使用してデバイス上の Microsoft Defender for Endpoint の構成設定を管理する
description: Microsoft Defender for Endpoint を使用して、Microsoft エンドポイント マネージャーのセキュリティ設定を有効にする方法について説明します。
keywords: デバイス管理、エンドポイント デバイス用 Microsoft Defender の構成、Microsoft エンドポイント マネージャー
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: e21346b48f65016465e669369aa14b3f4c85c23b
ms.sourcegitcommit: 3fb76db6b34e24569417f4c8a41b99f46a780389
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2022
ms.locfileid: "63527100"
---
# <a name="manage-microsoft-defender-for-endpoint-configuration-settings-on-devices-with-microsoft-endpoint-manager"></a>Microsoft エンドポイント マネージャーを使用してデバイス上の Microsoft Defender for Endpoint の構成設定を管理する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft Defender for Endpoint on devices on devices with Microsoft エンドポイント マネージャー](/mem/intune/protect/mde-security-integration)
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)



[!include[Prerelease information](../../includes/prerelease.md)]


> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-configureendpointsscript-abovefoldlink)


Microsoft Defender for Endpoint のセキュリティ管理は、Microsoft エンドポイント マネージャー (Microsoft Intune または Microsoft Endpoint Configuration Manager) によって管理されていないデバイスが Microsoft Defender のセキュリティ構成を受け取る機能です。から直接エンドポイント マネージャー。


前提条件、サポートされているプラットフォームなど、セキュリティ構成管理の詳細については、「Manage [Microsoft Defender for Endpoint on devices with devices with](/mem/intune/protect/mde-security-integration) Microsoft エンドポイント マネージャー」 を参照してください。



[!INCLUDE [Prerequisites](../../includes/security-config-mgt-prerequisites.md)]

>[!NOTE]
>この機能は徐々に展開されています。 

セキュリティ構成管理の詳細については、「Manage [Microsoft Defender for Endpoint on devices on devices with](/mem/intune/protect/mde-security-integration) Microsoft エンドポイント マネージャー。

登録の問題が発生した場合は、「セキュリティ構成管理のオンボーディングの問題の [トラブルシューティング」を参照してください](troubleshoot-security-config-mgt.md)。

> [!NOTE]
> この機能は、Intune または Configuration Manager に既に登録されているMicrosoft エンドポイント マネージャーには適用されません。 Intune に登録されたデバイスは、確立された管理チャネルを通じてポリシーを引き続き受け取る。

## <a name="identify-onboarded-devices"></a>オンボード デバイスの識別

次の手順を使用して、エンドポイントが Microsoft Defender for Endpoint オンボーディング プロセスのセキュリティ管理を正常に完了したと検証します。

1.  デバイスが [デバイス インベントリ] セクションに表示[Microsoft 365 Defender。](https://security.microsoft.com/)

2.  このポータル[Azure Active Directory](https://aad.portal.azure.com/#blade/Microsoft_AAD_Devices/DevicesMenuBlade/Devices/menuId/)、デバイスが正常に登録されたことを確認します。

3.  [管理 [センター Microsoft エンドポイント マネージャーで](https://endpoint.microsoft.com/#blade/Microsoft_Intune_DeviceSettings/DevicesMenu/mDMDevicesPreview)、[デバイス] セクションでデバイスが正常に登録されたことを確認>**確認** します。


## <a name="offboard-devices"></a>オフボード デバイス
Microsoft Defender for Endpoint のセキュリティ管理を介してオンボードされたオフボード デバイスについては、「 [Microsoft Defender for Endpoint Service のオフボード デバイス」を参照してください](offboard-machines.md)。

>[!NOTE]
>オフボードを有効にすると [、タンパープロテクション](prevent-changes-to-security-settings-with-tamper-protection.md#manage-tamper-protection-for-your-organization-using-the-microsoft-365-defender-portal) が無効になります。

## <a name="troubleshooting-security-management"></a>セキュリティ管理のトラブルシューティング 
Microsoft Defender for Endpoint 登録の問題のセキュリティ管理のトラブルシューティングについては、「 [Microsoft Defender for Endpoint](troubleshoot-security-config-mgt.md) のセキュリティ管理に関連するオンボーディングの問題のトラブルシューティング」を参照してください。

## <a name="related-topic"></a>関連トピック
- [Microsoft Defender for Endpoint のセキュリティ管理に関連するオンボーディングの問題のトラブルシューティング](troubleshoot-security-config-mgt.md)
- [Microsoft Defender for Endpoint on devices on devices with Microsoft エンドポイント マネージャー](/mem/intune/protect/mde-security-integration#configure-your-tenant-to-support-mde-security-configuration-management)
