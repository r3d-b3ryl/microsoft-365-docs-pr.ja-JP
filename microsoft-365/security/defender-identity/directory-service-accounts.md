---
title: Microsoft Defender for Identityで Directory Services アカウントを構成する
description: Microsoft 365 Defenderで Microsoft Defender for Identity Directory Services アカウントを構成する方法について説明します
ms.date: 08/15/2021
ms.topic: how-to
author: dcurwin
ms.author: dacurwin
ms.service: microsoft-defender-for-identity
ms.custom: admindeeplinkDEFENDER
manager: raynew
ms.collection: M365-security-compliance
ms.openlocfilehash: e31c226037d5d9e945350ba73e1df9abc79571e9
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64470001"
---
# <a name="microsoft-defender-for-identity-directory-services-account-in-microsoft-365-defender"></a>Microsoft 365 Defenderで Directory Services アカウントをMicrosoft Defender for Identityする

**適用対象:**

- Microsoft 365 Defender
- Defender for Identity

この記事では、[Microsoft 365 Defenderで Microsoft Defender for Identity](/defender-for-identity) Directory Services [アカウントを構成](/microsoft-365/security/defender/overview-security-center)する方法について説明します。

>[!IMPORTANT]
>Microsoft 365 Defenderとの統合の一環として、一部のオプションと詳細は Defender for Identity ポータルの場所から変更されています。 使い慣れた機能と新機能の両方を見つける場所については、以下の詳細を参照してください。

## <a name="configure-directory-services-account"></a>Directory Services アカウントを構成する

[センサー](sensor-health.md#add-a-sensor)を Active Directory ドメインに接続するには、Directory Services アカウントを構成する必要があります。

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a>で、[**設定**] に移動し、[**ID] に移動します**。

   :::image type="content" source="../../media/defender-identity/settings-identities.png" alt-text="設定 ページの [ID] オプション" lightbox="../../media/defender-identity/settings-identities.png":::


1. **[ディレクトリ サービス アカウント] を選択します**。 どのドメインに関連付けられているアカウントが表示されます。

   :::image type="content" source="../../media/defender-identity/directory-service-accounts.png" alt-text="[ディレクトリ サービス アカウント] メニュー項目" lightbox="../../media/defender-identity/directory-service-accounts.png":::

1. アカウントを選択すると、そのアカウントの設定を含むウィンドウが開きます。

   :::image type="content" source="../../media/defender-identity/account-settings.png" alt-text="[アカウント設定] ページ" lightbox="../../media/defender-identity/account-settings.png":::

1. 新しい Directory Services アカウントを追加するには、[ **新しいアカウントの作成** ] を選択し、 **アカウント名**、 **ドメイン**、 **およびパスワード** を入力します。 **グループマネージド サービス アカウント** (gMSA) か、単 **一ラベル ドメイン** に属しているかどうかを選択することもできます。

   :::image type="content" source="../../media/defender-identity/new-directory-service-account.png" alt-text="[新しいアカウントの作成] オプション" lightbox="../../media/defender-identity/new-directory-service-account.png":::

1. **[保存]** を選択します。

## <a name="see-also"></a>関連項目

- [センサーの正常性と設定をMicrosoft Defender for Identityする](sensor-health.md)
