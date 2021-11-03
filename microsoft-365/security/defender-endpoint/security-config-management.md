---
title: デバイスの Microsoft Defender for Endpoint 構成設定を管理する (Microsoft エンドポイント マネージャー
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 08fae46ce14a74dacefd76fbc8e77511c40609e6
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/02/2021
ms.locfileid: "60677064"
---
# <a name="manage-microsoft-defender-for-endpoint-configuration-settings-on-devices-with-microsoft-endpoint-manager"></a>デバイスの Microsoft Defender for Endpoint 構成設定を管理する (Microsoft エンドポイント マネージャー

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft Defender for Endpoint on devices on devices with Microsoft エンドポイント マネージャー](/mem/intune/protect/mde-security-integration)
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-configureendpointsscript-abovefoldlink)


Microsoft Defender for Endpoint のセキュリティ管理は、Microsoft エンドポイント マネージャー (Microsoft Intune または Microsoft Endpoint Configuration Manager) によって管理されていないデバイスが Microsoft Defender のセキュリティ構成を直接受信する機能です。からエンドポイント マネージャー。


前提条件、サポートされているプラットフォームなど、セキュリティ構成管理の詳細については、「Manage Microsoft Defender for Endpoint on devices with devices with Microsoft エンドポイント マネージャー」 を[参照してください](/mem/intune/protect/mde-security-integration)。



[!INCLUDE [Prerequisites](../../includes/security-config-mgt-prerequisites.md)]


セキュリティ構成管理の詳細については、「Microsoft [Defender for Endpoint on devices on devices with Microsoft エンドポイント マネージャー」 を参照してください](/mem/intune/protect/mde-security-integration)。

登録に関する問題が発生した場合は、「セキュリティ構成管理のオンボーディングの問題の [トラブルシューティング」を参照してください](troubleshoot-security-config-mgt.md)。

> [!NOTE]
> この機能は、Intune または Configuration Manager に既に登録Microsoft エンドポイント マネージャーには適用されません。 Intune に登録されたデバイスは、確立された管理チャネルを通じてポリシーを引き続き受け取る。

## <a name="identify-onboarded-devices"></a>オンボード デバイスの識別

次の手順を使用して、エンドポイントが Microsoft Defender for Endpoint オンボーディング プロセスのセキュリティ管理を正常に完了したと検証します。

1.  デバイスが [デバイス インベントリ] セクションに表示[Microsoft 365 Defender。](https://security.microsoft.com/)

2.  このポータル[Azure Active Directory、](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/UsersManagementMenuBlade/MsGraphUsers)デバイスが正常に登録されたことを確認します。

3.  [管理 [Microsoft エンドポイント マネージャー]](https://endpoint.microsoft.com/#blade/Microsoft_Intune_DeviceSettings/DevicesMenu/mDMDevicesPreview)で、[デバイス] セクションでデバイスが正常に登録されたことを確認>**確認** します。


## <a name="offboard-devices"></a>オフボード デバイス
Microsoft Defender for Endpoint のセキュリティ管理を介してオンボードされたオフボード デバイスについては [、「Microsoft Defender for Endpoint](offboard-machines.md)Service からのオフボード デバイス」を参照してください。

>[!NOTE]
>オフボードを有効にすると [、タンパープロテクション](prevent-changes-to-security-settings-with-tamper-protection.md#manage-tamper-protection-for-your-organization-using-the-microsoft-365-defender-portal) が無効になります。

## <a name="troubleshooting-security-management"></a>セキュリティ管理のトラブルシューティング 
Microsoft Defender for Endpoint 登録の問題に関するセキュリティ管理のトラブルシューティングについては [、「Security Management for Microsoft Defender for Endpoint」](troubleshoot-security-config-mgt.md)に関連するオンボーディングの問題のトラブルシューティングを参照してください。

## <a name="related-topic"></a>関連トピック
- [Microsoft Defender for Endpoint のセキュリティ管理に関連するオンボーディングの問題のトラブルシューティング](troubleshoot-security-config-mgt.md)
- [Microsoft Defender for Endpoint on devices on devices with Microsoft エンドポイント マネージャー](/mem/intune/protect/mde-security-integration#configure-your-tenant-to-support-mde-security-configuration-management)
