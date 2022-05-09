---
title: Microsoft 365 Defender MSSP カスタマー ポータルにアクセスする
description: Microsoft 365 Defender MSSP カスタマー ポータルにアクセスする
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
# <a name="access-the-microsoft-365-defender-mssp-customer-portal"></a>Microsoft 365 Defender MSSP カスタマー ポータルにアクセスする

**適用対象:**
- [Microsoft Defender for Endpoint プラン 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint プラン 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-mssp-support-abovefoldlink)

> [!NOTE]
> これらの一連の手順は、MSSP に向けられます。

既定では、MSSP のお客様は、次の URL を使用してMicrosoft 365 Defenderテナントにアクセスします`https://security.microsoft.com/`。

ただし、MSSP カスタマー ポータルにアクセスするには、テナント固有の URL を次の形式  `https://security.microsoft.com?tid=customer_tenant_id` で使用する必要があります。

一般に、MSSP は、管理する MSSP 顧客の各Azure ADに追加する必要があります。

MSSP カスタマー テナント ID を取得し、その ID を使用してテナント固有の URL にアクセスするには、次の手順に従います。

1. MSSP として、資格情報を使用してAzure ADにログインします。

2. ディレクトリを MSSP 顧客のテナントに切り替えます。

3. **Azure Active Directory >プロパティ** を選択します。 テナント ID は、[ディレクトリ ID] フィールドに表示されます。

4. 次の URL の値を `customer_tenant_id` 置き換えて MSSP カスタマー ポータルにアクセスします `https://security.microsoft.com/?tid=customer_tenant_id`。

## <a name="related-topics"></a>関連項目

- [ポータルへの MSSP アクセスを許可する](grant-mssp-access.md)
- [アラート通知を構成する](configure-mssp-notifications.md)
- [顧客テナントからアラートを取得する](fetch-alerts-mssp.md)
