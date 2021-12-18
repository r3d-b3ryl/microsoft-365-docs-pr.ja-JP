---
title: サーバーをMicrosoft Defender ウイルス対策構成Microsoft エンドポイント マネージャー
description: '[Microsoft エンドポイント マネージャーとMicrosoft Intuneを使用して、Microsoft Defender ウイルス対策とEndpoint Protection'
keywords: scep、intune、エンドポイント保護、構成
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 12/16/2021
ms.reviewer: phuijbr, oogunrinde
manager: dansimp
ms.technology: mde
audience: ITPro
ms.topic: how-to
ms.collection: m365-security-compliance
ms.openlocfilehash: 1eb126481cc9872c42906e0311d1c771da44c693
ms.sourcegitcommit: 282f3a58b8e11615b3e53328e6b89a6ac52008e9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2021
ms.locfileid: "61560210"
---
# <a name="use-microsoft-endpoint-manager-to-configure-and-manage-microsoft-defender-antivirus"></a>[Microsoft エンドポイント マネージャーを使用して、構成および管理Microsoft Defender ウイルス対策

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**

- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)

このオプションを使用[Microsoft エンドポイント マネージャー](/mem/endpoint-manager-overview)スキャンをMicrosoft Defender ウイルス対策できます。 [Microsoft Intune](/mem/intune/fundamentals/what-is-intune)[構成マネージャーは](/mem/configmgr/core/understand/introduction)、このページの一部エンドポイント マネージャー。

## <a name="configure-microsoft-defender-antivirus-scans-in-endpoint-manager"></a>コンピューター Microsoft Defender ウイルス対策スキャンを構成エンドポイント マネージャー

1. 管理センター ( ) Microsoft エンドポイント マネージャーに [https://endpoint.microsoft.com](https://endpoint.microsoft.com) 移動し、サインインします。

2. [エンドポイント セキュリティ **] に移動します**。

3. [管理 **] で**、[ウイルス対策] **を選択します**。

4. ポリシーをMicrosoft Defender ウイルス対策します。

5. [**管理**] で [**プロパティ**] を選択します。

6. **[構成の設定]** の横にある **[編集]** を選択します。

   > [!IMPORTANT]
   > AllowOnAccessProtection および AllowIntrusionPreventionSystem ウイルス対策設定は正式に廃止され、構成できません。 

7. [スキャン] **セクションを** 展開し、スキャン設定を確認または編集します。

8. [確認 **] + [保存] を選択します**。

> [!TIP]
> サポートが必要な場合 「Manage [endpoint security in Microsoft Intune」 を参照してください](/mem/intune/protect/endpoint-security)。

## <a name="related-articles"></a>関連記事

- [管理および構成ツールの参照記事](configuration-management-reference-microsoft-defender-antivirus.md)
- [Microsoft Defender ウイルス対策 (Windows 10)](microsoft-defender-antivirus-in-windows-10.md)
