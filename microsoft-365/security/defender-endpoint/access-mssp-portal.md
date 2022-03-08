---
title: MSSP カスタマー Microsoft 365 Defenderにアクセスする
description: MSSP カスタマー Microsoft 365 Defenderにアクセスする
keywords: マネージド セキュリティ サービス プロバイダー、mssp、構成、統合
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
ms.openlocfilehash: b1c133048e6600d553f0530e135ebfc2c441dd84
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63323669"
---
# <a name="access-the-microsoft-365-defender-mssp-customer-portal"></a>MSSP カスタマー Microsoft 365 Defenderにアクセスする

**適用対象:**
- [ Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [ Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-mssp-support-abovefoldlink)

> [!NOTE]
> これらの一連の手順は、MSSP に向けて指示されます。

既定では、MSSP のお客様は次の URL Microsoft 365 Defenderテナントにアクセスします。 `https://security.microsoft.com/`

ただし、MSSP は、MSSP カスタマー ポータルにアクセスするには、テナント固有の URL  `https://security.microsoft.com?tid=customer_tenant_id` を次の形式で使用する必要があります。

一般に、MSSP は、管理する予定の MSSP Azure ADに追加する必要があります。

次の手順を使用して、MSSP カスタマー テナント ID を取得し、その ID を使用してテナント固有の URL にアクセスします。

1. MSSP として、資格情報を使用Azure ADにログインします。

2. ディレクトリを MSSP 顧客のテナントに切り替えます。

3. [プロパティ **Azure Active Directory >選択します**。 [ディレクトリ ID] フィールドにテナント ID があります。

4. 次の URL の値を置 `customer_tenant_id` き換え、MSSP カスタマー ポータルにアクセスします `https://security.microsoft.com/?tid=customer_tenant_id`。

## <a name="related-topics"></a>関連項目

- [ポータルへの MSSP アクセスを許可する](grant-mssp-access.md)
- [アラート通知を構成する](configure-mssp-notifications.md)
- [顧客テナントからアラートを取得する](fetch-alerts-mssp.md)
