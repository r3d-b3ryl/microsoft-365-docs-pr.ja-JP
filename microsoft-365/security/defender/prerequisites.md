---
title: Microsoft 365Defender の前提条件
description: Defender のライセンス、ハードウェアとソフトウェアの要件、その他の構成設定Microsoft 365する
keywords: 要件、前提条件、ハードウェア、ソフトウェア、ブラウザー、Microsoft 365 Defender、M365、ライセンス、E5、A5、EMS、購入
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: f3fd597181d73c1768057ea7740ab111e5af2068
ms.sourcegitcommit: 82a4d74020cd93ba444006317cfecc178c6d41dc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2021
ms.locfileid: "52689159"
---
# <a name="microsoft-365-defender-prerequisites"></a>Microsoft 365Defender の前提条件

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

Defender のプロビジョニングと使用に関するライセンスその他の[要件Microsoft 365します](microsoft-365-defender.md)。

## <a name="licensing-requirements"></a>ライセンスの要件
これらのライセンスを使用すると、セキュリティ センター Microsoft 365 Defender 機能Microsoft 365追加コストなしでアクセスできます。

- Microsoft 365 E5 または A5
- Microsoft 365 E3アドオンMicrosoft 365 E5 Securityを使用する
- Microsoft 365A5 セキュリティ アドオンMicrosoft 365 A3
- Windows 10 Enterprise E5 または A5
- Enterprise Mobility + Security (EMS) E5 または A5 
- Office 365 E5 または A5
- Microsoft Defender for Endpoint
- Microsoft Defender for Identity 
- Microsoft Cloud App Security
- Defender for Office 365 (プラン 2)

詳細については、サービス[プランのMicrosoft 365 Enterpriseしてください](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise)。

> まだライセンスがありませんか? [Microsoft 365 サブスクリプションを試用する/購入する](../../commerce/try-or-buy-microsoft-365.md)

### <a name="check-your-existing--licenses"></a>既存のライセンスを確認する
既存のMicrosoft 365を表示するには、admin.microsoft.com[管理センター](https://admin.microsoft.com/)( admin.microsoft.com ) に移動します。 管理センターで、[**課金**]  >  [**ライセンス**] の順に移動します。

>[!NOTE]
> ライセンス情報を表示するには[、Azure](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles)サーバーで課金管理者またはグローバル リーダー AD割り当てる必要があります。  アクセスの問題が発生した場合は、グローバル管理者に連絡してください。

## <a name="required-permissions"></a>必要なアクセス許可
Defender を有効に **するには、** グローバル管理者またはセキュリティAzure Active Directory管理者Microsoft 365があります。 Microsoft 365 Defender を使用するために必要な役割の一覧と、データへのアクセスが規制される方法に関する情報については、「Defender へのアクセスの管理」[をMicrosoft 365してください](m365d-permissions.md)。

## <a name="browser-requirements"></a>ブラウザー要件
Microsoft 365、Microsoft 365 11、または HTML 5 準拠の web ブラウザーを使用Microsoft Edgeセキュリティ センター Internet Explorer Defender にアクセスします。

## <a name="availability-to-us-gcc-gcc-high-and-other-us-government-institutions"></a>米国の政府機関GCC、GCC、その他の米国政府機関への可用性
現時点では、Microsoft 365 Defender *を使用* できません。
- US Government Community Cloud (GCC)
- 米国 Government Community Cloud高 (GCC高)
- 米国国防総省
- 商用ライセンスを持つすべての米国政府機関


現時点では、Microsoft Defender for Office 365統合された Defender 機能Microsoft 365統合は、データセンターの次の場所Office 365使用できません。

- ブラジル 
- ドイツ 
- ノルウェー 
- シンガポール 
- 南アフリカ
- スイス 
- アラブ首長国連邦 


## <a name="related-topics"></a>関連項目
- [Microsoft 365Defender の概要](microsoft-365-defender.md)
- [Microsoft 365 Defender を有効にする](m365d-enable.md)
- [アクセスとアクセス許可の管理](m365d-permissions.md)
