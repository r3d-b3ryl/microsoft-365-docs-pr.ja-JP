---
title: Microsoft Defender Security Center MSSP カスタマー ポータルにアクセスする
description: Microsoft Defender Security Center MSSP カスタマー ポータルにアクセスする
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
ms.openlocfilehash: 97122decede91e8b4f059b3b66999ac12b300172
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164859"
---
# <a name="access-the-microsoft-defender-security-center-mssp-customer-portal"></a>Microsoft Defender Security Center MSSP カスタマー ポータルにアクセスする

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**

- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

>Microsoft Defender for Endpoint を体験してみませんか? [無料試用版にサインアップします。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)




>[!NOTE] 
>これらの一連の手順は、MSSP に向けて指示されます。 

既定では、MSSP のお客様は、次の URL を使用して Microsoft Defender セキュリティ センター テナントにアクセスします `https://securitycenter.windows.com` 。
 

ただし、MSSP は、MSSP カスタマー ポータルにアクセスするには、テナント固有の URL を次の形式で  `https://securitycenter.windows.com?tid=customer_tenant_id` 使用する必要があります。 

一般に、MSSP は、管理する予定の MSSP 顧客の Azure ADに追加する必要があります。


次の手順を使用して、MSSP カスタマー テナント ID を取得し、その ID を使用してテナント固有の URL にアクセスします。

1. MSSP として、資格情報を使用して Azure ADにログインします。 

2. ディレクトリを MSSP 顧客のテナントに切り替えます。

3.  [Azure **Active Directory >プロパティ] を選択します**。 [ディレクトリ ID] フィールドにテナント ID があります。 

4. 次の URL の値を置き換え、MSSP カスタマー ポータル `customer_tenant_id` にアクセスします `https://securitycenter.windows.com?tid=customer_tenant_id` 。


## <a name="related-topics"></a>関連項目
- [ポータルへの MSSP アクセスを許可する](grant-mssp-access.md)
- [アラート通知の構成](configure-mssp-notifications.md)
- [顧客テナントからアラートを取得する](fetch-alerts-mssp.md)
