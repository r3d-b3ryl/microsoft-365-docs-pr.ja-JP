---
title: Microsoft 365 Defender前提条件
description: Microsoft 365 Defenderのライセンス、ハードウェアとソフトウェアの要件、およびその他の構成設定について説明します
keywords: 要件, 前提条件, ハードウェア, ソフトウェア, ブラウザー, Microsoft 365 Defender, M365, ライセンス, E5, A5, EMS, 購入
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
ms.openlocfilehash: 5281df5fe500907af6bb54384bb44b5a29534460
ms.sourcegitcommit: d4797cfc15c732f1a7ef21e4f944e672a7170f9a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2022
ms.locfileid: "62444595"
---
# <a name="microsoft-365-defender-prerequisites"></a>Microsoft 365 Defender前提条件

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

[Microsoft 365 Defender](microsoft-365-defender.md)のプロビジョニングと使用に関するライセンスとその他の要件について説明します。

## <a name="licensing-requirements"></a>ライセンスの要件
これらのライセンスのいずれかを使用すると、追加コストなしでMicrosoft 365 Defender ポータルからMicrosoft 365 Defender機能にアクセスできます。

- Microsoft 365 E5 または A5
- Microsoft 365 E5 Security アドオンを使用したMicrosoft 365 E3
- Enterprise Mobility + Security E5 アドオンを使用したMicrosoft 365 E3
- Microsoft 365 A5 セキュリティ アドオンを使用したMicrosoft 365 A3
- Windows 10 Enterprise E5 または A5
- Windows 11 Enterprise E5 または A5
- Enterprise Mobility + Security (EMS) E5 または A5 
- Office 365 E5 または A5
- Microsoft Defender for Endpoint
- Microsoft Defender for Identity 
- Microsoft Defender for Cloud Apps
- Defender for Office 365 (プラン 2)

詳細については、[Microsoft 365 Enterpriseサービス プランを参照してください](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise)。

> まだライセンスをお持ちでない場合 [Microsoft 365 サブスクリプションを試用する/購入する](../../commerce/try-or-buy-microsoft-365.md)

### <a name="check-your-existing--licenses"></a>既存のライセンスを確認する
Microsoft 365 管理センター ([admin.microsoft.com](https://admin.microsoft.com/)) に移動して、既存のライセンスを表示します。 管理センターで、[**課金**]  >  [**ライセンス**] の順に移動します。

>[!NOTE]
> ライセンス情報を表示するには、[Azure ADで](/azure/active-directory/roles/permissions-reference)**課金管理者** ロールまたは **グローバル リーダー** ロールのいずれかを割り当てる必要があります。 アクセスの問題が発生した場合は、グローバル管理者に連絡してください。

## <a name="required-permissions"></a>必要なアクセス許可
Microsoft 365 Defenderを有効にするには、Azure Active Directoryの **グローバル管理者** または **セキュリティ管理者** である必要があります。 Microsoft 365 Defenderを使用するために必要なロールの一覧と、データへのアクセスの規制方法に関する情報については、[Microsoft 365 Defenderへのアクセスの管理](m365d-permissions.md)に関する記事を参照してください。

## <a name="browser-requirements"></a>ブラウザー要件
Microsoft Edge、Internet Explorer 11、または HTML 5 準拠の Web ブラウザーを使用して、Microsoft 365 Defender ポータルでMicrosoft 365 Defenderにアクセスします。

## <a name="availability-to-us-gcc-gcc-high-and-other-us-government-institutions"></a>米国GCC、GCC High、およびその他の米国政府機関への可用性

米国政府機関のお客様に関連する情報については、「[米国政府機関のお客様向けのMicrosoft 365 Defender」を参照してください](usgov.md)。

現時点では、統合Microsoft 365 Defender機能へのMicrosoft Defender for Office 365統合は、次のOffice 365データセンターの場所のお客様には利用できません。

- ノルウェー 
- 南アフリカ 
- アラブ首長国連邦 
- スウェーデン 
- シンガポール 


## <a name="related-topics"></a>関連項目
- [Microsoft 365 Defenderの概要](microsoft-365-defender.md)
- [Microsoft 365 Defender を有効にする](m365d-enable.md)
- [アクセスとアクセス許可を管理する](m365d-permissions.md)
