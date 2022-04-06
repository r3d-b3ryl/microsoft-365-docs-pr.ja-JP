---
title: Microsoft Defender for Identity でディレクトリ サービス アカウントを構成する
description: Microsoft Defender for Identity Directory Services アカウントを構成する方法については、「Microsoft Defender for Identity Directory Services」Microsoft 365 Defender
ms.date: 08/15/2021
ms.topic: how-to
author: dcurwin
ms.author: dacurwin
ms.service: microsoft-defender-for-identity
ms.custom: admindeeplinkDEFENDER
manager: raynew
ms.collection: M365-security-compliance
ms.openlocfilehash: 0b7e9045ecc479c2da382979211caaa46e8a01d1
ms.sourcegitcommit: b3530441288b2bc44342e00e9025a49721796903
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/20/2022
ms.locfileid: "63683299"
---
# <a name="microsoft-defender-for-identity-directory-services-account-in-microsoft-365-defender"></a>Microsoft Defender for Identity Directory Services アカウント (Microsoft 365 Defender

**適用対象:**

- Microsoft 365 Defender
- Defender for Identity

この記事では、Microsoft [Defender for Identity](/defender-for-identity) Directory Services アカウントを構成する方法について説明[します。Microsoft 365 Defender](/microsoft-365/security/defender/overview-security-center)。

>[!IMPORTANT]
>Id ポータルの Defender Microsoft 365 Defenderの場所から、一部のオプションと詳細が変更されました。 使い慣れた機能と新機能の両方を見つける場所については、以下の詳細をお読みください。

## <a name="configure-directory-services-account"></a>ディレクトリ サービス アカウントの構成

センサーを Active [Directory ドメインに](sensor-health.md#add-a-sensor) 接続するには、Directory Services アカウントを構成する必要があります。

1. [<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a>] で、[id **] 設定** に **移動します**。

    ![[ID] 設定に移動します。](../../media/defender-identity/settings-identities.png)

1. [ **ディレクトリ サービス アカウント] を選択します**。 どのドメインに関連付けられているアカウントが表示されます。

    ![ディレクトリ サービス アカウント。](../../media/defender-identity/directory-service-accounts.png)

1. アカウントを選択すると、そのアカウントの設定でウィンドウが開きます。

    ![アカウント設定。](../../media/defender-identity/account-settings.png)

1. 新しい Directory Services アカウントを追加するには、[新しいアカウントの作成] **を選択し**、[アカウント名]、[ドメイン]、および [**パスワード] を** 入力 **します**。 グループ管理サービス **アカウント (** gMSA) の場合と、それが単一ラベル ドメインに属している場合も **選択できます**。

    ![新しいディレクトリ サービス アカウント。](../../media/defender-identity/new-directory-service-account.png)

1. **[保存]** を選択します。

## <a name="see-also"></a>関連項目

- [Microsoft Defender for Identity センサーの正常性と設定](sensor-health.md)
