---
title: Microsoft Defender for Identity entity tags in Microsoft 365 Defender
description: Microsoft Defender for Identity エンティティ タグをアプリケーションに適用する方法についてMicrosoft 365 Defender
ms.date: 06/08/2021
ms.topic: how-to
author: dcurwin
ms.author: dacurwin
ms.service: microsoft-defender-for-identity
ms.custom: admindeeplinkDEFENDER
manager: raynew
ms.collection: M365-security-compliance
ms.openlocfilehash: c960f0cc1726155e733a0e88386fa7788cfc35e0
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64468063"
---
# <a name="defender-for-identity-entity-tags-in-microsoft-365-defender"></a>Defender for Identity entity tags in Microsoft 365 Defender

**適用対象:**

- Microsoft 365 Defender
- Defender for Identity

この記事では、Microsoft [Defender for Identity エンティティ](/defender-for-identity) タグをアプリケーションで適用[するMicrosoft 365 Defender。](/microsoft-365/security/defender/overview-security-center)

>[!IMPORTANT]
>Id ポータルの Defender Microsoft 365 Defenderの場所から、一部のオプションと詳細が変更されました。 使い慣れた機能と新機能の両方を見つける場所については、以下の詳細をお読みください。

## <a name="entity-tags"></a>エンティティ タグ

このMicrosoft 365 Defender、3 種類の Defender for Identity エンティティ タグ (機密タグ、**Honeytoken** タグ、およびサーバー **Exchange) を設定できます**。 

これらのタグを設定 <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">するには、Microsoft 365 Defender</a>に移動し、[**設定 ID****] に移動します**。

:::image type="content" source="../../media/defender-identity/settings-identities.png" alt-text="[Id] オプションは、[名前] ページの [名前] 列設定します。" lightbox="../../media/defender-identity/settings-identities.png":::

タグの設定は、[エンティティ タグ] の **下に表示されます**。

:::image type="content" source="../../media/defender-identity/tag-settings.png" alt-text="[エンティティ タグ] ウィンドウ" lightbox="../../media/defender-identity/tag-settings.png":::

タグの各種類を設定するには、以下の手順に従います。

## <a name="sensitive--tags"></a>機密タグ

機密 **タグは、** 価値の高い資産を識別するために使用されます。 横方向の移動パスは、エンティティの感度の状態にも依存します。 一部のエンティティは、Defender for Identity によって自動的に機密性が高いと見なされます。 これらのアセットの一覧については、「機密性の高い [エンティティ」を参照してください](/defender-for-identity/manage-sensitive-honeytoken-accounts#sensitive-entities)。

ユーザー、デバイス、またはグループに機密として手動でタグを付けすることもできます。

1. [機密] **を選択します**。 その後、既存の機密性の高い **ユーザー、デバイス**、 **およびグループ** が表示 **されます**。

   :::image type="content" source="../../media/defender-identity/sensitive-entities.png" alt-text="[機密エンティティ] メニュー項目の [デバイス] タブ" lightbox="../../media/defender-identity/sensitive-entities.png":::

1. 各カテゴリで、[ **Tag...] を選択して** 、その種類のエンティティにタグを付けします。 たとえば、[グループ] で **[タグ** グループ] **を選択します。** 選択してタグ付けできるグループを含むウィンドウが開きます。 グループを検索するには、検索ボックスにグループ名を入力します。

   :::image type="content" source="../../media/defender-identity/add-groups.png" alt-text="グループを追加するオプション" lightbox="../../media/defender-identity/add-groups.png":::

1. グループを選択し、[選択の追加 **] をクリックします。**

   :::image type="content" source="../../media/defender-identity/add-selection.png" alt-text="[選択の追加] オプション" lightbox="../../media/defender-identity/add-selection.png":::

## <a name="honeytoken-tags"></a>Honeytoken のタグ

Honeytoken エンティティは、悪意のあるアクターのトラップとして使用されます。 これらの honeytoken エンティティに関連付けられた認証は、アラートをトリガーします。

ユーザーまたはデバイスに **Honeytoken** タグを付け、機密性の高いアカウントにタグ付けするのと同じ方法でタグ付けできます。

1. [ **Honeytoken] を選択します**。 次に、既存の honeytoken ユーザーと **デバイスが** 表示 **されます**。

    ![Honeytoken エンティティ。](../../media/defender-identity/honeytoken-entities.png)

1. 各カテゴリで、[ **Tag...] を選択して** 、その種類のエンティティにタグを付けします。 たとえば、[ユーザー] で **[ユーザーの** タグ付 **け] を選択します。** 選択してタグ付けできるグループを含むウィンドウが開きます。 グループを検索するには、検索ボックスにグループ名を入力します。

   :::image type="content" source="../../media/defender-identity/add-users.png" alt-text="ユーザーを追加するオプション" lightbox="../../media/defender-identity/add-users.png":::

1. ユーザーを選択し、[選択の追加 **] をクリックします。**

   :::image type="content" source="../../media/defender-identity/add-selected-user.png" alt-text="選択したユーザーを追加するオプション" lightbox="../../media/defender-identity/add-selected-user.png":::

## <a name="exchange-server-tags"></a>Exchangeサーバー タグ

Defender for Identity は、Exchangeを高価値アセットと見なし、自動的に機密としてタグ付 **けします**。 デバイスに手動でタグを付け、Exchangeすることもできます。

1. [サーバー **Exchange選択します**。 次に、既存のデバイスにサーバー タグのラベルが付Exchange **表示** されます。

   :::image type="content" source="../../media/defender-identity/exchange-servers.png" alt-text="[サーバー Exchange] メニュー項目" lightbox="../../media/defender-identity/exchange-servers.png":::

1. デバイスをサーバーとしてタグ付けするにはExchangeを **選択します**。  タグ付けするデバイスを選択すると、ウィンドウが開きます。 デバイスを検索するには、検索ボックスにデバイスの名前を入力します。

   :::image type="content" source="../../media/defender-identity/add-devices.png" alt-text="デバイスを追加するオプション" lightbox="../../media/defender-identity/add-devices.png":::

1. デバイスを選択し、[選択の追加 **] をクリックします。**

   :::image type="content" source="../../media/defender-identity/select-device.png" alt-text="デバイスの選択" lightbox="../../media/defender-identity/select-device.png":::

## <a name="see-also"></a>関連項目

- [Defender for Identity セキュリティアラートの管理](manage-security-alerts.md)
