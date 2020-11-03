---
title: Microsoft 365 Defender の前提条件
description: Microsoft 365 Defender のライセンス、ハードウェアおよびソフトウェアの要件、およびその他の構成設定について説明します。
keywords: 要件、前提条件、ハードウェア、ソフトウェア、ブラウザー、MTP、M365、license、E5、A5、EMS、購入
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 415cdb79a6aa9371ee2f07de579cfb2f873f1acb
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844778"
---
# <a name="microsoft-365-defender-prerequisites"></a>Microsoft 365 Defender の前提条件

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

[Microsoft 365 Defender](microsoft-threat-protection.md)をプロビジョニングおよび使用するためのライセンスおよびその他の要件について説明します。

## <a name="licensing-requirements"></a>ライセンスの要件
これらのライセンスのいずれかを使用すると、追加のコストを必要とせずに microsoft 365 セキュリティセンターの Microsoft 365 Defender の機能にアクセスできます。

- Microsoft 365 E5 または A5
- Microsoft 365 E5 セキュリティまたは A5 セキュリティ
- Windows 10 Enterprise E5 または A5
- Enterprise Mobility + Security (EMS) E5 または A5 
- Office 365 E5 または A5
- Microsoft Defender for Endpoint
- Id の Microsoft Defender 
- Microsoft Cloud App Security
- Office 365 の Defender (プラン 2)

> [!NOTE]
> Office 365 の試用版ライセンスは現在、Microsoft 365 Defender へのアクセスを提供していません。

詳細については、 [Microsoft 365 Enterprise service プランを参照して](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise)ください。

> まだライセンスを持っていませんか? [Microsoft 365 サブスクリプションを試用する/購入する](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide)

### <a name="check-your-existing--licenses"></a>既存のライセンスを確認する
Microsoft 365 管理センター ([admin.microsoft.com](https://admin.microsoft.com/)) に移動して、既存のライセンスを表示します。 管理センターで、[ **課金** ]  >  [ **ライセンス** ] の順に移動します。

>[!NOTE]
> ライセンス情報を表示するには、 [AZURE AD の](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles)**課金管理者** または **グローバル閲覧** 者の役割のいずれかが割り当てられている必要があります。 アクセスの問題が発生した場合は、グローバル管理者に連絡してください。

## <a name="required-permissions"></a>必要なアクセス許可
Microsoft 365 Defender を有効にするには、Azure Active Directory の **グローバル管理者** または **セキュリティ管理者** である必要があります。 Microsoft 365 Defender を使用するために必要な役割の一覧と、データへのアクセスを規制する方法については、「 [microsoft 365 Defender へのアクセスの管理](mtp-permissions.md)について」を参照してください。

## <a name="browser-requirements"></a>ブラウザー要件
Microsoft Edge、Internet Explorer 11、または任意の HTML 5 準拠の web ブラウザーを使用して、microsoft 365 セキュリティセンターの Microsoft 365 Defender にアクセスします。

## <a name="availability-to-us-gcc-gcc-high-and-other-us-government-institutions"></a>米国 GCC、GCC 高、その他の米国政府機関向けの可用性
現時点では、Microsoft 365 Defender を使用することはでき *ません* 。
- 米国政府機関向けコミュニティクラウド (GCC)
- 米国政府機関向けコミュニティクラウド高 (GCC 高)
- 米国国防総省
- 市販のライセンスを持つ米国の全行政機関

## <a name="related-topics"></a>関連項目
- [Microsoft 365 Defender の概要](microsoft-threat-protection.md)
- [Microsoft 365 Defender をオンにする](mtp-enable.md)
- [アクセスとアクセス許可を管理する](mtp-permissions.md)
