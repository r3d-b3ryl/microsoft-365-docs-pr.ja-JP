---
title: Microsoft 365 Defenderで検出除外をMicrosoft Defender for Identityする
description: Microsoft 365 DefenderでMicrosoft Defender for Identity検出除外を構成する方法について説明します。
ms.date: 11/02/2021
ms.topic: how-to
author: dcurwin
ms.author: dacurwin
ms.service: microsoft-defender-for-identity
manager: raynew
ms.collection: M365-security-compliance
ms.openlocfilehash: e2df92e44b323bd0555407d72ebd48a7e050c9a5
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64473917"
---
# <a name="configure-defender-for-identity-detection-exclusions-in-microsoft-365-defender"></a>Microsoft 365 Defenderで Defender for Identity 検出の除外を構成する

**適用対象:**

- Microsoft 365 Defender
- Defender for Identity

この記事では、[Microsoft 365 DefenderでMicrosoft Defender for Identity](/defender-for-identity)検出除外を構成する方法について[](/microsoft-365/security/defender/overview-security-center)説明します。

> [!IMPORTANT]
> Microsoft 365 Defenderとの統合の一環として、一部のオプションと詳細は Defender for Identity ポータルの場所から変更されています。 使い慣れた機能と新機能の両方を見つける場所については、以下の詳細を参照してください。

[!INCLUDE [Product long](includes/product-long.md)] は、特定の IP アドレス、コンピューター、ドメイン、またはユーザーを多数の検出から除外できるようにします。

たとえば、 **DNS 偵察** アラートは、スキャン メカニズムとして DNS を使用するセキュリティ スキャナーによってトリガーされる可能性があります。 除外を作成すると、Defender for Identity はこのようなスキャナーを無視し、誤検知を減らすことができます。

>[!NOTE]
>DNS アラートを [介して疑わしい通信](/defender-for-identity/exfiltration-alerts#suspicious-communication-over-dns-external-id-2031) が開かれた最も一般的なドメインのうち、顧客がアラートから最も除外したドメインを観察しました。 これらのドメインは既定で除外リストに追加されますが、簡単に削除できます。

## <a name="how-to-add-detection-exclusions"></a>検出除外を追加する方法

1. [Microsoft 365 Defender](https://security.microsoft.com/)で、[**設定**] に移動し、[**ID] に移動します**。

   :::image type="content" source="../../media/defender-identity/settings-identities.png" alt-text="[名前] 列の [ID] オプション" lightbox="../../media/defender-identity/settings-identities.png":::

1. 左側のメニューに **[除外されたエンティティ** ] が表示されます。

   :::image type="content" source="../../media/defender-identity/excluded-entities.png" alt-text="[除外されたエンティティ] ウィンドウ" lightbox="../../media/defender-identity/excluded-entities.png":::

その後、 **検出ルールによる** 除外とグローバル除外エンティティの 2 つの方法で **除外** を設定できます。

## <a name="exclusions-by-detection-rule"></a>検出規則による除外

1. 左側のメニューで、[ **検出規則による除外]** を選択します。 検出ルールの一覧が表示されます。

   :::image type="content" source="../../media/defender-identity/exclusions-by-detection-rule.png" alt-text="左側のウィンドウの [除外されたエンティティ] 項目の [検出規則による除外] オプション" lightbox="../../media/defender-identity/exclusions-by-detection-rule.png":::

1. 構成する検出ごとに、次の手順を実行します。

    1. ルールを選択します。 検索バーを使用して検出を検索できます。 選択すると、検出ルールの詳細を含むウィンドウが開きます。

       :::image type="content" source="../../media/defender-identity/detection-rule-details.png" alt-text="検出ルールの詳細" lightbox="../../media/defender-identity/detection-rule-details.png":::

    1. 除外を追加するには、[ **除外されたエンティティ** ] ボタンを選択し、除外の種類を選択します。 除外されたエンティティは、ルールごとに異なります。 これには、ユーザー、デバイス、ドメイン、IP アドレスが含まれます。 この例では、[ **デバイスの除外]** と [ **IP アドレスの除外]** の順に選択します。

       :::image type="content" source="../../media/defender-identity/exclude-devices-or-ip-addresses.png" alt-text="デバイスまたは IP アドレスを除外するオプション" lightbox="../../media/defender-identity/exclude-devices-or-ip-addresses.png":::

    1. 除外の種類を選択したら、除外を追加できます。 開いたウィンドウで、除外を **+** 追加するボタンを選択します。

       :::image type="content" source="../../media/defender-identity/add-exclusion.png" alt-text="除外を追加するオプション" lightbox="../../media/defender-identity/add-exclusion.png":::

    1. 次に、除外するエンティティを追加します。 **[+ 追加]** を選択して、エンティティを一覧に追加します。

       :::image type="content" source="../../media/defender-identity/add-excluded-entity.png" alt-text="除外するエンティティを追加するオプション" lightbox="../../media/defender-identity/add-excluded-entity.png":::

    1. 次に、(この例では) **[IP アドレスの除外** ] を選択して除外を完了します。

       :::image type="content" source="../../media/defender-identity/exclude-ip-addresses.png" alt-text="IP アドレスを除外するオプション" lightbox="../../media/defender-identity/exclude-ip-addresses.png":::

    1. 除外を追加したら、[除外 **されたエンティティ** ] ボタンに戻って、一覧をエクスポートしたり、除外を削除したりできます。 この例では、[ **デバイスの除外]** に戻っています。 リストをエクスポートするには、下矢印ボタンを選択します。

       :::image type="content" source="../../media/defender-identity/return-to-exclude-devices.png" alt-text="[デバイスを除外する] オプション" lightbox="../../media/defender-identity/return-to-exclude-devices.png":::

    1. 除外を削除するには、除外を選択し、ごみ箱アイコンを選択します。

       :::image type="content" source="../../media/defender-identity/delete-exclusion.png" alt-text="[除外の削除] オプション" lightbox="../../media/defender-identity/delete-exclusion.png":::

## <a name="global-excluded-entities"></a>グローバルに除外されたエンティティ

**グローバル除外エンティティ** によって除外を構成することもできます。 グローバル除外を使用すると、Defender for Identity が持つすべての検出で除外される特定のエンティティ (IP アドレス、サブネット、デバイス、またはドメイン) を定義できます。 たとえば、デバイスを除外した場合、検出の一部としてデバイス ID を持つ検出にのみ適用されます。

1. 左側のメニューで、[ **グローバル除外エンティティ**] を選択します。 除外できるエンティティのカテゴリが表示されます。

   :::image type="content" source="../../media/defender-identity/global-excluded-entities.png" alt-text="グローバルに除外されたエンティティサブメニュー項目" lightbox="../../media/defender-identity/global-excluded-entities.png":::

1. 除外の種類を選択します。 この例では、[ **ドメインの除外]** を選択しました。

   :::image type="content" source="../../media/defender-identity/exclude-domains.png" alt-text="[ドメイン] タブ" lightbox="../../media/defender-identity/exclude-domains.png":::

1. 除外するドメインを追加できるウィンドウが開きます。 除外するドメインを追加します。

   :::image type="content" source="../../media/defender-identity/add-excluded-domain.png" alt-text="除外するドメインを追加するオプション" lightbox="../../media/defender-identity/add-excluded-domain.png":::

1. ドメインが一覧に追加されます。 [ **除外ドメイン]** を選択して除外を完了します。

   :::image type="content" source="../../media/defender-identity/select-exclude-domains.png" alt-text="除外するドメインを選択するオプション" lightbox="../../media/defender-identity/select-exclude-domains.png":::

1. その後、すべての検出ルールから除外するエンティティの一覧にドメインが表示されます。 リストをエクスポートしたり、エンティティを削除したりするには、それらを選択して **[削除** ] ボタンをクリックします。

   :::image type="content" source="../../media/defender-identity/global-excluded-entries-list.png" alt-text="グローバルに除外されたエントリの一覧" lightbox="../../media/defender-identity/global-excluded-entries-list.png":::

## <a name="see-also"></a>関連項目

- [Defender for Identity セキュリティ アラートを管理する](manage-security-alerts.md)
