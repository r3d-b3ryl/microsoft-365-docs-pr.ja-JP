---
title: Microsoft 365 Defender の前提条件
description: Microsoft 365 Defender のライセンス、ハードウェアとソフトウェアの要件、その他の構成設定について説明します。
keywords: 要件, 前提条件, ハードウェア, ソフトウェア, ブラウザー, MTP, M365, ライセンス, E5, A5, EMS, 購入
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: ee1777debdb91a6ac73737db2db48e434ed3e2e2
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930092"
---
# <a name="microsoft-365-defender-prerequisites"></a>Microsoft 365 Defender の前提条件

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

[ライセンスと、Microsoft 365 Defender](microsoft-threat-protection.md)のプロビジョニングと使用に関するその他の要件について説明します。

## <a name="licensing-requirements"></a>ライセンスの要件
これらのライセンスは、追加コストなしで Microsoft 365 セキュリティ センターの Microsoft 365 Defender 機能にアクセスできます。

- Microsoft 365 E5 または A5
- Microsoft 365 E5 セキュリティまたは A5 セキュリティ
- Windows 10 Enterprise E5 または A5
- Enterprise Mobility + Security (EMS) E5 または A5 
- Office 365 E5 または A5
- Microsoft Defender for Endpoint
- Microsoft Defender for Identity 
- Microsoft Cloud App Security
- Defender for Office 365 (プラン 2)

> [!NOTE]
> 現在、Office 365 の試用版ライセンスは、Microsoft 365 Defender へのアクセスを提供しません。

詳細については [、Microsoft 365 Enterprise サービス プランを参照してください](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise)。

> まだライセンスを持っていない場合 [Microsoft 365 サブスクリプションを試用する/購入する](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide)

### <a name="check-your-existing--licenses"></a>既存のライセンスを確認する
既存のライセンスを表示するには、Microsoft 365 管理センター[(admin.microsoft.com](https://admin.microsoft.com/)) に移動します。 管理センターで、[**課金**]  >  [**ライセンス**] の順に移動します。

>[!NOTE]
> ライセンス情報を表示するには[、Azure](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) ADの課金管理者またはグローバル 閲覧者ロールが割り当てられている必要があります。  アクセスの問題が発生した場合は、グローバル管理者に連絡してください。

## <a name="required-permissions"></a>必要なアクセス許可
Microsoft 365 Defenderを **有効** にする場合は、Azure Active Directory のグローバル管理者またはセキュリティ管理者である必要があります。 Microsoft 365 Defender の使用に必要な役割の一覧と、データへのアクセスが規制される方法に関する情報については [、Microsoft 365 Defender](mtp-permissions.md)へのアクセスの管理に関するページをご覧ください。

## <a name="browser-requirements"></a>ブラウザー要件
Microsoft Edge、Internet Explorer 11、または HTML 5 準拠の Web ブラウザーを使用して、Microsoft 365 セキュリティ センターで Microsoft 365 Defender にアクセスします。

## <a name="availability-to-us-gcc-gcc-high-and-other-us-government-institutions"></a>米国の GCC、GCC High、その他の米国政府機関の利用可能性
現在、Microsoft 365 Defender は *次の機能を* 利用できません。
- 米国政府機関コミュニティ クラウド (GCC)
- US Government Community Cloud High (GCC High)
- 米国国防総省
- 商用ライセンスを持つすべての米国政府機関

## <a name="related-topics"></a>関連項目
- [Microsoft 365 Defender の概要](microsoft-threat-protection.md)
- [Microsoft 365 Defender を有効にする](mtp-enable.md)
- [アクセスとアクセス許可を管理する](mtp-permissions.md)
