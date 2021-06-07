---
title: Microsoft Defender for Endpoint Flow コネクタ
ms.reviewer: ''
description: Microsoft Defender for Endpoint Flow コネクタを使用して、セキュリティを自動化し、テナントで新しいアラートが発生するといつでもトリガーされるフローを作成します。
keywords: flow, サポートされている api, api, Microsoft flow, query, automation
search.product: eADQiWindows 10XVcnh
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: dd0cc3c2da134750f905b1f80746d6ec65cc70b2
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769707"
---
# <a name="microsoft-power-automate-formerly-microsoft-flow-and-azure-functions"></a>Microsoft Power Automate (以前はMicrosoft Flow)、Azure Functions

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


- Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

セキュリティ手順の自動化は、最新のセキュリティ 運用センターの標準要件です。 専門的なサイバー防御者がいないので、SOC は最も効率的な方法で作業し、自動化が必要です。 Microsoft Power Automateは、このために正確に構築されたさまざまなコネクタをサポートしています。 数分以内にエンドツーエンドのプロシージャオートメーションを構築できます。

Microsoft Defender API には、多くの機能Flow公式のコネクタがあります。

![編集資格情報のイメージ1](images/api-flow-0.png)

> [!NOTE]
> プレミアム コネクタライセンスの前提条件の詳細については、「Premium [Connectors のライセンス」を参照してください](https://docs.microsoft.com/power-automate/triggers-introduction#licensing-for-premium-connectors)。


## <a name="usage-example"></a>使用例

次の例では、テナントで新Flowアラートが発生する場合にトリガーされる新しいアラートを作成する方法を示します。

1. Microsoft Power Automate[にログインします](https://flow.microsoft.com)。

2. [マイ フロー **] [**  >  **新しい**  >  **自動入力から] 空白に移動します**。

    ![編集資格情報のイメージ2](images/api-flow-1.png)

3. ユーザーの名前を選択Flowトリガーとして "Microsoft Defender ATPトリガー" を検索し、新しいアラート トリガーを選択します。

    ![編集資格情報のイメージ3](images/api-flow-2.png)

これで、新Flow発生するごとにトリガーされるメッセージが表示されます。

![編集資格情報のイメージ4](images/api-flow-3.png)

ここで行う必要があるのは、次の手順を選択する必要があります。
たとえば、アラートの重大度が高い場合にデバイスを分離し、そのデバイスに関する電子メールを送信できます。
アラート トリガーは、アラート ID とコンピューター ID のみを提供します。 コネクタを使用して、これらのエンティティを展開できます。

### <a name="get-the-alert-entity-using-the-connector"></a>コネクタを使用して Alert エンティティを取得する

1. 新 **しいMicrosoft Defender ATP** を選択します。

2. [アラート **] - [単一のアラート API を取得する] を選択します**。

3. 最後の **手順の [アラート ID]** を [入力] に **設定します**。

    ![編集資格情報のイメージ5](images/api-flow-4.png)

### <a name="isolate-the-device-if-the-alerts-severity-is-high"></a>アラートの重大度が [高] の場合はデバイスを分離する

1. 新 **しい手順として** 条件を追加します。

2. アラートの重大度が High に **等しいか確認** します。

   [はい] の場合Microsoft Defender ATP **コンピューター** の操作を [コンピューター ID とコメントで分離する] を追加します。

    ![資格情報の編集のイメージ6](images/api-flow-5.png)

3. アラートと分離に関する電子メールを送信する新しい手順を追加します。 メール コネクタや Gmail など、非常に使いやすいOutlookがあります。

4. フローを保存します。

また、高度な検索 **クエリを** 実行するスケジュールされたフローを作成できます。

## <a name="related-topic"></a>関連トピック
- [エンドポイント API 用 Microsoft Defender](apis-intro.md)
