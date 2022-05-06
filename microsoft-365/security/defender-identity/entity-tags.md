---
title: Microsoft 365 Defenderでエンティティ タグをMicrosoft Defender for Identityする
description: Microsoft 365 Defenderでエンティティ タグMicrosoft Defender for Identity適用する方法について説明します
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
# <a name="defender-for-identity-entity-tags-in-microsoft-365-defender"></a>Microsoft 365 Defenderの Defender for Identity エンティティ タグ

**適用対象:**

- Microsoft 365 Defender
- Defender for Identity

この記事では、[Microsoft 365 Defenderでエンティティ タグMicrosoft Defender for Identity](/defender-for-identity)適用する方法について説明[します](/microsoft-365/security/defender/overview-security-center)。

>[!IMPORTANT]
>Microsoft 365 Defenderとの統合の一環として、一部のオプションと詳細は Defender for Identity ポータルの場所から変更されています。 使い慣れた機能と新機能の両方を見つける場所については、以下の詳細を参照してください。

## <a name="entity-tags"></a>エンティティ タグ

Microsoft 365 Defenderでは、3 種類の Defender for Identity エンティティ タグ (**機密タグ**、**Honeytoken タグ**、**Exchange サーバー タグ**) を設定できます。

これらのタグを設定するには、<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a>で **[設定**] に移動し、[**ID] に移動します**。

:::image type="content" source="../../media/defender-identity/settings-identities.png" alt-text="[設定] ページの [名前] 列の [ID] オプション" lightbox="../../media/defender-identity/settings-identities.png":::

[ **エンティティ** タグ] の下にタグ設定が表示されます。

:::image type="content" source="../../media/defender-identity/tag-settings.png" alt-text="[エンティティ タグ] ウィンドウ" lightbox="../../media/defender-identity/tag-settings.png":::

タグの種類を設定するには、次の手順に従います。

## <a name="sensitive--tags"></a>機密タグ

**機密タグ** は、価値の高い資産を識別するために使用されます。 横移動パスは、エンティティの秘密度の状態にも依存します。 一部のエンティティは、Defender for Identity によって自動的に機密と見なされます。 これらの資産の一覧については、「 [機密エンティティ](/defender-for-identity/manage-sensitive-honeytoken-accounts#sensitive-entities)」を参照してください。

ユーザー、デバイス、またはグループに機密として手動でタグ付けすることもできます。

1. [ **機密]** を選択します。 その後、既存の機密 **ユーザー**、 **デバイス**、 **およびグループ** が表示されます。

   :::image type="content" source="../../media/defender-identity/sensitive-entities.png" alt-text="[機密エンティティ] メニュー項目の [デバイス] タブ" lightbox="../../media/defender-identity/sensitive-entities.png":::

1. 各カテゴリの下にある **[Tag....** ] を選択して、その種類のエンティティにタグを付けます。 たとえば、[ **グループ**] で [タグ グループ] を選択 **します。** タグ付けするために選択できるグループを含むウィンドウが開きます。 グループを検索するには、検索ボックスにその名前を入力します。

   :::image type="content" source="../../media/defender-identity/add-groups.png" alt-text="グループを追加するオプション" lightbox="../../media/defender-identity/add-groups.png":::

1. グループを選択し、[**選択の追加]** をクリックします。

   :::image type="content" source="../../media/defender-identity/add-selection.png" alt-text="[選択の追加] オプション" lightbox="../../media/defender-identity/add-selection.png":::

## <a name="honeytoken-tags"></a>Honeytoken タグ

Honeytoken エンティティは、悪意のあるアクターのトラップとして使用されます。 これらの honeytoken エンティティに関連付けられているすべての認証は、アラートをトリガーします。

機密性の高いアカウントにタグを付けるのと同じ方法で、 **Honeytoken** タグを使用してユーザーまたはデバイスにタグを付けることができます。

1. **[Honeytoken**] を選択します。 その後、既存の honeytoken **ユーザー** とデバイスが表示 **されます**。

    ![Honeytoken エンティティ。](../../media/defender-identity/honeytoken-entities.png)

1. 各カテゴリの下にある **[Tag....** ] を選択して、その種類のエンティティにタグを付けます。 たとえば、[**ユーザー**] で [**ユーザーのタグ付け**] を選択します。 タグ付けするために選択できるグループを含むウィンドウが開きます。 グループを検索するには、検索ボックスにその名前を入力します。

   :::image type="content" source="../../media/defender-identity/add-users.png" alt-text="ユーザーを追加するオプション" lightbox="../../media/defender-identity/add-users.png":::

1. ユーザーを選択し、[**選択の追加]** をクリックします。

   :::image type="content" source="../../media/defender-identity/add-selected-user.png" alt-text="選択したユーザーを追加するオプション" lightbox="../../media/defender-identity/add-selected-user.png":::

## <a name="exchange-server-tags"></a>Exchange サーバー タグ

Defender for Identity は、Exchange サーバーを価値の高い資産と見なし、自動的に機密としてタグ付 **けします**。 デバイスにExchange サーバーとして手動でタグを付けることもできます。

1. **サーバー Exchange選択します**。 次に、Exchange **サーバー** タグでラベル付けされた既存のデバイスが表示されます。

   :::image type="content" source="../../media/defender-identity/exchange-servers.png" alt-text="[Exchange サーバー] メニュー項目" lightbox="../../media/defender-identity/exchange-servers.png":::

1. デバイスをExchange サーバーとしてタグ付けするには、[デバイスの **タグ付け**] を選択します。  タグ付けするために選択できるデバイスを含むウィンドウが開きます。 デバイスを検索するには、検索ボックスにその名前を入力します。

   :::image type="content" source="../../media/defender-identity/add-devices.png" alt-text="デバイスを追加するオプション" lightbox="../../media/defender-identity/add-devices.png":::

1. デバイスを選択し、[**選択の追加]** をクリックします。

   :::image type="content" source="../../media/defender-identity/select-device.png" alt-text="デバイスの選択" lightbox="../../media/defender-identity/select-device.png":::

## <a name="see-also"></a>関連項目

- [Defender for Identity セキュリティ アラートを管理する](manage-security-alerts.md)
