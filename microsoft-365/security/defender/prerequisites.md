---
title: Microsoft 365 Defender前提条件
description: ライセンス、ハードウェアとソフトウェアの要件、その他の構成設定についてMicrosoft 365 Defender
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
ms.openlocfilehash: 4bc846927524bd80adf512107e1d072c7969d58f
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59211833"
---
# <a name="microsoft-365-defender-prerequisites"></a>Microsoft 365 Defender前提条件

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

ライセンスと、ライセンスのプロビジョニングと使用に関するその他の要件について[Microsoft 365 Defender。](microsoft-365-defender.md)

## <a name="licensing-requirements"></a>ライセンスの要件
これらのライセンスは、追加コストなしで、Microsoft 365 DefenderポータルMicrosoft 365 Defender機能にアクセスできます。

- Microsoft 365 E5 または A5
- Microsoft 365 E3アドオンMicrosoft 365 E5 Securityを使用する
- Microsoft 365 A3セキュリティ Microsoft 365 A5を使用する
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
[ライセンス] Microsoft 365 管理センター[(](https://admin.microsoft.com/)admin.microsoft.com ) に移動して、既存のライセンスを表示します。 管理センターで、[**課金**]  >  [**ライセンス**] の順に移動します。

>[!NOTE]
> ライセンス情報を表示するには[、Azure](/azure/active-directory/roles/permissions-reference)サーバーで課金管理者またはグローバル リーダー AD割り当てる必要があります。  アクセスの問題が発生した場合は、グローバル管理者に連絡してください。

## <a name="required-permissions"></a>必要なアクセス許可
サーバーを有効に **するには、** グローバル管理者またはセキュリティ管理者Azure Active Directory必要Microsoft 365 Defender。 データへのアクセスを規制する方法Microsoft 365 Defender使用するために必要な役割の一覧については、「データへのアクセスの管理」を[参照](m365d-permissions.md)Microsoft 365 Defender。

## <a name="browser-requirements"></a>ブラウザー要件
11 Microsoft 365 Defender HTML 5 準拠の web ブラウザー Microsoft 365 Defender、Microsoft Edge 11 Internet Explorerを使用して、Microsoft 365 Defender ポータルでアクセスします。

## <a name="availability-to-us-gcc-gcc-high-and-other-us-government-institutions"></a>米国の政府機関GCC、GCC、その他の米国政府機関への可用性
現在、Microsoft 365 Defender *を使用* できません。
- US Government Community Cloud (GCC)
- 米国 Government Community Cloud高 (GCC高)
- 米国国防総省
- 商用ライセンスを持つすべての米国政府機関


現在、Microsoft Defender for Office 365統合Microsoft 365 Defenderは、次のデータセンターの場所Office 365使用できません。

- ブラジル 
- ドイツ 
- ノルウェー 
- シンガポール 
- 南アフリカ
- スイス 
- アラブ首長国連邦 


## <a name="related-topics"></a>関連項目
- [Microsoft 365 Defender概要](microsoft-365-defender.md)
- [Microsoft 365 Defender を有効にする](m365d-enable.md)
- [アクセスとアクセス許可の管理](m365d-permissions.md)
