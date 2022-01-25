---
title: イベントに対Power Automateコネクタを使用してFlowする方法
ms.reviewer: ''
description: Microsoft Defender for Endpoint Flow コネクタを使用して、テナントで新しいイベントが発生するといつでもトリガーされるフローを作成します。
keywords: flow, サポートされている api, api, Microsoft flow, query, automation, power automation
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
ms.topic: how-to
MS.technology: mde
ms.custom: api
ms.openlocfilehash: fdb3876de6f74c95858dee01aba9615198282b16
ms.sourcegitcommit: bcea69bacd1b48827bd60af2880909593a1609a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/25/2022
ms.locfileid: "62202199"
---
# <a name="how-to-use-power-automate-connector-to-set-up-a-flow-for-events"></a>イベントに対Power Automateコネクタを使用してFlowする方法

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)


セキュリティ手順の自動化は、すべての最新のセキュリティ 運用センター (SOC) の標準的な要件です。 SOC チームが最も効率的な方法で運用するには、自動化が必要です。 Microsoft Power Automateを使用して、自動化されたワークフローを作成し、数分以内にエンドツーエンドのプロシージャオートメーションを構築できます。 Microsoft Power Automateは、このために正確に構築されたさまざまなコネクタをサポートしています。  

この記事では、テナントに新しいアラートが作成された場合など、イベントによってトリガーされるオートメーションの作成について説明します。 Microsoft Defender API には、多くの機能Power Automate公式のコネクタがあります。 



:::image type="content" alt-text="編集資格情報 1 のイメージ。" source="images/api-flow-0.png":::

> [!NOTE]
> プレミアム コネクタライセンスの前提条件の詳細については、「Premium [Connectors のライセンス」を参照してください](/power-automate/triggers-introduction#licensing-for-premium-connectors)。


## <a name="usage-example"></a>使用例

次の例では、テナントで新Flowアラートが発生する場合にトリガーされる新しいアラートを作成する方法を示します。 フローを開始するイベントと、そのトリガーが発生した場合に実行される次のアクションを定義する方法について説明します。  

1. Microsoft Power Automate[にログインします](https://flow.microsoft.com)。

2. [マイ フロー **] [** \> **新しい** \> **自動入力から] 空白に移動します**。

    :::image type="content" alt-text="編集資格情報 2 のイメージ。" source="images/api-flow-1.png":::

3. ユーザーの名前を選択しFlow"Microsoft Defender ATP Triggers" をトリガーとして検索し、新しいアラート トリガーを選択します。

    :::image type="content" alt-text="編集資格情報 3 のイメージ。" source="images/api-flow-2.png":::

これで、新Flow発生するごとにトリガーされるメッセージが表示されます。

:::image type="content" alt-text="編集資格情報 4 のイメージ。" source="images/api-flow-3.png":::

ここで行う必要があるのは、次の手順を選択する必要があります。
たとえば、アラートの重大度が高い場合にデバイスを分離し、そのデバイスに関する電子メールを送信できます。
アラート トリガーは、アラート ID とコンピューター ID のみを提供します。 コネクタを使用して、これらのエンティティを展開できます。

### <a name="get-the-alert-entity-using-the-connector"></a>コネクタを使用して Alert エンティティを取得する

1. 新しい **手順で [Microsoft Defender ATP]** を選択します。

2. [アラート **] - [単一のアラート API を取得する] を選択します**。

3. 最後の **手順の [アラート ID]** を [入力] に **設定します**。

    :::image type="content" alt-text="資格情報の編集のイメージ 5." source="images/api-flow-4.png" lightbox="images/api-flow-4.png":::

### <a name="isolate-the-device-if-the-alerts-severity-is-high"></a>アラートの重大度が [高] の場合はデバイスを分離する

1. 新 **しい手順として** 条件を追加します。

2. アラートの重大度が High に **等しいか確認** します。

   [はい] の場合は **、[コンピューター ID]** とコメントを含む Microsoft Defender ATP - [コンピューターの分離] アクションを追加します。

    :::image type="content" alt-text="編集資格情報 6 のイメージ。" source="images/api-flow-5.png" lightbox="images/api-flow-5.png":::

3. アラートと分離に関する電子メールを送信する新しい手順を追加します。 メール コネクタや Gmail など、非常に使いやすいOutlookがあります。

4. フローを保存します。

また、高度な検索 **クエリを** 実行するスケジュールされたフローを作成できます。

## <a name="related-topic"></a>関連トピック
- [エンドポイント API 用 Microsoft Defender](apis-intro.md)
