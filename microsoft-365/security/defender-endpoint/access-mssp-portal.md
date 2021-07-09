---
title: MSSP カスタマー Microsoft 365 Defenderにアクセスする
description: MSSP カスタマー Microsoft 365 Defenderにアクセスする
keywords: マネージド セキュリティ サービス プロバイダー、mssp、構成、統合
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
ms.openlocfilehash: 8583b28adecd892ec6875faa934fd7ab08e5db11
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339588"
---
# <a name="access-the-microsoft-365-defender-mssp-customer-portal"></a>MSSP カスタマー Microsoft 365 Defenderにアクセスする

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**

- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

>Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)




>[!NOTE] 
>これらの一連の手順は、MSSP に向けて指示されます。 

既定では、MSSP のお客様は次の URL Microsoft Defender セキュリティ センターテナントにアクセスします `https://securitycenter.windows.com` 。
 

ただし、MSSP は、MSSP カスタマー ポータルにアクセスするには、テナント固有の URL を次の形式で  `https://securitycenter.windows.com?tid=customer_tenant_id` 使用する必要があります。 

一般に、MSSP は、管理する予定の MSSP 顧客の Azure ADに追加する必要があります。


次の手順を使用して、MSSP カスタマー テナント ID を取得し、その ID を使用してテナント固有の URL にアクセスします。

1. MSSP として、資格情報を使用して Azure ADにログインします。 

2. ディレクトリを MSSP 顧客のテナントに切り替えます。

3.  [プロパティ **Azure Active Directory >] を選択します**。 [ディレクトリ ID] フィールドにテナント ID があります。 

4. 次の URL の値を置き換え、MSSP カスタマー ポータル `customer_tenant_id` にアクセスします `https://securitycenter.windows.com?tid=customer_tenant_id` 。


## <a name="related-topics"></a>関連項目
- [ポータルへの MSSP アクセスを許可する](grant-mssp-access.md)
- [アラート通知を構成する](configure-mssp-notifications.md)
- [顧客テナントからアラートを取得する](fetch-alerts-mssp.md)
