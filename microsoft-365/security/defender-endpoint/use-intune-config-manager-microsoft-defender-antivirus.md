---
title: サーバーをMicrosoft Defender ウイルス対策構成Microsoft エンドポイント マネージャー
description: Microsoft Defender AV Microsoft エンドポイント マネージャー Microsoft Intuneを構成するには、Microsoft Defender AV と Microsoft Defender AV を構成するEndpoint Protection
keywords: scep、intune、エンドポイント保護、構成
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/24/2021
ms.reviewer: phuijbr, oogunrinde
manager: dansimp
ms.technology: mde
audience: ITPro
ms.topic: how-to
ms.openlocfilehash: d2380053ffcb81a939494b487e17d065bd9d67c72664145e0232d9e1fd89608c
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53839185"
---
# <a name="use-microsoft-endpoint-manager-to-configure-and-manage-microsoft-defender-antivirus"></a>[Microsoft エンドポイント マネージャーを使用して、構成および管理Microsoft Defender ウイルス対策

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

このオプションを使用[Microsoft エンドポイント マネージャー](/mem/endpoint-manager-overview)スキャンをMicrosoft Defender ウイルス対策できます。 [Microsoft Intune](/mem/intune/fundamentals/what-is-intune)[構成マネージャーは](/mem/configmgr/core/understand/introduction)、このページの一部エンドポイント マネージャー。  

## <a name="configure-microsoft-defender-antivirus-scans-in-endpoint-manager"></a>コンピューター Microsoft Defender ウイルス対策スキャンを構成エンドポイント マネージャー

1. 管理センター ( ) Microsoft エンドポイント マネージャーに [https://endpoint.microsoft.com](https://endpoint.microsoft.com) 移動し、サインインします。

2. [エンドポイント セキュリティ **] に移動します**。

3. [管理 **] で**、[ウイルス対策] **を選択します**。

4. ポリシーをMicrosoft Defender ウイルス対策します。 

5. [**管理**] で [**プロパティ**] を選択します。

6. **[構成の設定]** の横にある **[編集]** を選択します。

7. [スキャン] **セクションを** 展開し、スキャン設定を確認または編集します。

8. [レビュー **] + [保存] の選択**


> [!TIP]
> サポートが必要な場合 「Manage [endpoint security in Microsoft Intune」 を参照してください](/mem/intune/protect/endpoint-security)。


## <a name="related-articles"></a>関連記事

- [管理および構成ツールの参照記事](configuration-management-reference-microsoft-defender-antivirus.md)
- [Microsoft Defender ウイルス対策 (Windows 10)](microsoft-defender-antivirus-in-windows-10.md)