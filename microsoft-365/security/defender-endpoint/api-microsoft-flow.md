---
title: Power Automate コネクタを使用してイベントのFlow設定する方法
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
ms.openlocfilehash: 63626978311b679d0f8b520e4b041d92942bd1fd
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64467997"
---
# <a name="how-to-use-power-automate-connector-to-set-up-a-flow-for-events"></a>Power Automate コネクタを使用してイベントのFlow設定する方法

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

セキュリティ手順の自動化は、すべての最新のセキュリティ 運用センター (SOC) の標準的な要件です。 SOC チームが最も効率的な方法で運用するには、自動化が必要です。 Microsoft Power Automateを使用して、自動化されたワークフローを作成し、数分以内にエンドツーエンドのプロシージャオートメーションを構築できます。 Microsoft Power Automateは、このために正確に構築されたさまざまなコネクタをサポートしています。  

この記事では、テナントに新しいアラートが作成された場合など、イベントによってトリガーされるオートメーションの作成について説明します。 Microsoft Defender API には、多くの機能Power Automate公式のコネクタがあります。 

:::image type="content" source="images/api-flow-0.png" alt-text="Microsoft Defender 365 ポータルの [アクション] ページ" lightbox="images/api-flow-0.png" :::

> [!NOTE]
> プレミアム コネクタのライセンスの前提条件の詳細については、「 [Premium コネクタのライセンス」を参照してください](/power-automate/triggers-introduction#licensing-for-premium-connectors)。

## <a name="usage-example"></a>使用例

次の例では、テナントで新Flowアラートが発生する場合にトリガーされるイベントを作成する方法を示します。 フローを開始するイベントと、そのトリガーが発生した場合に実行される次のアクションを定義する方法について説明します。  

1. [Microsoft Power Automate にログインします](https://flow.microsoft.com)。

2. [自分の **フロー] [** \> **新しい自動** \> **から] 空白に移動します**。

    :::image type="content" source="images/api-flow-1.png" alt-text="Microsoft Defender 365 ポータルの [マイ フロー] メニュー項目の [新しいフロー] ウィンドウ" lightbox="images/api-flow-1.png":::

3. ユーザーの名前を選択しFlow"Microsoft Defender ATP Triggers" をトリガーとして検索し、新しいアラート トリガーを選択します。

    :::image type="content" source="images/api-flow-2.png" alt-text=" Microsoft Defender 365 ポータルの [フローのトリガーの選択] セクション" lightbox="images/api-flow-2.png" :::

これで、新Flow発生するごとにトリガーされるメッセージが表示されます。

:::image type="content" source="images/api-flow-3.png" alt-text="トリガーの説明" lightbox="images/api-flow-3.png":::

ここで行う必要があるのは、次の手順を選択する必要があります。
たとえば、アラートの重大度が高い場合にデバイスを分離し、そのデバイスに関する電子メールを送信できます。
アラート トリガーは、アラート ID とコンピューター ID のみを提供します。 コネクタを使用して、これらのエンティティを展開できます。

### <a name="get-the-alert-entity-using-the-connector"></a>コネクタを使用して Alert エンティティを取得する

1. 新しい **手順で [Microsoft Defender ATP** ] を選択します。

2. [アラート **] - [単一のアラート API を取得する] を選択します**。

3. 最後の **手順の [アラート ID** ] を [入力] に **設定します**。

    :::image type="content" source="images/api-flow-4.png" alt-text="[アラート] ウィンドウ"  lightbox="images/api-flow-4.png":::

### <a name="isolate-the-device-if-the-alerts-severity-is-high"></a>アラートの重大度が [高] の場合はデバイスを分離する

1. 新 **しい手順として** 条件を追加します。

2. アラートの重大度が High に **等しいか確認** します。

   [はい] の場合は、[コンピューター ID] とコメントを含む Microsoft **Defender ATP -** [コンピューターの分離] アクションを追加します。

    :::image type="content" source="images/api-flow-5.png" alt-text="[操作] ウィンドウ"  lightbox="images/api-flow-5.png":::

3. アラートと分離に関する電子メールを送信する新しい手順を追加します。 メール コネクタや Gmail など、非常に使いやすいOutlookがあります。

4. フローを保存します。

また、高度な検索 **クエリを** 実行するスケジュールされたフローを作成できます。

## <a name="related-topic"></a>関連トピック
- [エンドポイント API 用 Microsoft Defender](apis-intro.md)
