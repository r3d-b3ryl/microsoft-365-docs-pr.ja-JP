---
title: Microsoft エンドポイント マネージャーを使用してデバイス上の Microsoft Defender for Endpoint の構成設定を管理する
description: Microsoft Defender for Endpointを使用してMicrosoft エンドポイント マネージャーでセキュリティ設定を有効にする方法について説明します。
keywords: デバイス管理、Microsoft Defender for Endpoint デバイスの構成、Microsoft エンドポイント マネージャー
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
ms.openlocfilehash: 7e9e074e4aeaadf041a70baed1d741ea95a9f792
ms.sourcegitcommit: 349f0f54b0397cdd7d8fbb9ef07f1b6654a32d6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2022
ms.locfileid: "65622621"
---
# <a name="manage-microsoft-defender-for-endpoint-configuration-settings-on-devices-with-microsoft-endpoint-manager"></a>Microsoft エンドポイント マネージャーを使用してデバイス上の Microsoft Defender for Endpoint の構成設定を管理する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft エンドポイント マネージャーを使用してデバイスのMicrosoft Defender for Endpointを管理する](/mem/intune/protect/mde-security-integration)
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)



> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-configureendpointsscript-abovefoldlink)


Microsoft Defender for Endpoint用のセキュリティ管理は、Microsoft エンドポイント マネージャーによって管理されていないデバイスの機能であり、Microsoft IntuneまたはMicrosoft Endpoint Configuration Manager、Microsoft Defender のセキュリティ構成をエンドポイント マネージャーから直接受信します。


前提条件、サポートされているプラットフォームなど、セキュリティ構成管理の詳細については、「[Microsoft エンドポイント マネージャーを使用したデバイスでのMicrosoft Defender for Endpointの管理](/mem/intune/protect/mde-security-integration)」を参照してください。

このビデオでは、Microsoft エンドポイント マネージャーを使用してMicrosoft Defender for Endpointのセキュリティ構成を管理する方法について説明します。
> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4qLVq]

[!INCLUDE [Prerequisites](../../includes/security-config-mgt-prerequisites.md)]

>[!NOTE]
>この機能は段階的にロールアウトされています。 

セキュリティ構成管理の詳細については、「Microsoft エンドポイント マネージャーを[使用したデバイスでのMicrosoft Defender for Endpointの管理](/mem/intune/protect/mde-security-integration)」を参照してください。

登録の問題が発生した場合は、「 [セキュリティ構成管理のオンボードに関する問題のトラブルシューティング」を](troubleshoot-security-config-mgt.md)参照してください。

> [!NOTE]
> この機能は、Microsoft エンドポイント マネージャーに既に登録されているデバイス (IntuneまたはConfiguration Manager) には適用されません。 Intuneに登録されたデバイスは、確立された管理チャネルを通じて引き続きポリシーを受け取ります。

## <a name="identify-onboarded-devices"></a>オンボードされたデバイスを識別する

次の手順を使用して、エンドポイントがMicrosoft Defender for Endpointオンボード プロセスの Security Management を正常に完了したことを検証します。

1.  デバイスがMicrosoft 365 Defenderの [デバイス インベントリ] [セクションに表示](https://security.microsoft.com/)されることを確認します。

2.  [Azure Active Directory ポータル](https://aad.portal.azure.com/#blade/Microsoft_AAD_Devices/DevicesMenuBlade/Devices/menuId/)で、デバイスが正常に登録されたことを確認します。

3.  [Microsoft エンドポイント マネージャー管理センター](https://endpoint.microsoft.com/#blade/Microsoft_Intune_DeviceSettings/DevicesMenu/mDMDevicesPreview)で、[**デバイス>すべての** デバイス] セクションでデバイスが正常に登録されたことを確認します。


## <a name="offboard-devices"></a>オフボード デバイス
Security Management for Microsoft Defender for Endpointを介してオンボードされたオフ[ボード デバイスについては、「Microsoft Defender for Endpoint サービスのオフボード デバイス」を](offboard-machines.md)参照してください。

>[!NOTE]
>オフボードを有効にすると [、改ざん防止が無効](prevent-changes-to-security-settings-with-tamper-protection.md#manage-tamper-protection-for-your-organization-using-the-microsoft-365-defender-portal) になります。

## <a name="troubleshooting-security-management"></a>セキュリティ管理のトラブルシューティング 
Microsoft Defender for Endpoint登録の問題に対する Security Management のトラブルシューティングについては、「[Microsoft Defender for Endpointの Security Management に関連するオンボードの問題のトラブルシューティング」を](troubleshoot-security-config-mgt.md)参照してください。

## <a name="related-topic"></a>関連トピック
- [Microsoft Defender for Endpointの Security Management に関連するオンボードの問題のトラブルシューティング](troubleshoot-security-config-mgt.md)
- [Microsoft エンドポイント マネージャーを使用してデバイスのMicrosoft Defender for Endpointを管理する](/mem/intune/protect/mde-security-integration#configure-your-tenant-to-support-mde-security-configuration-management)
