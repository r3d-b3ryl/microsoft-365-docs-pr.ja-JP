---
title: タイム ゾーンの設定をMicrosoft 365 Defenderする
description: ここに含まれる情報を使用して、Microsoft 365 Defenderタイム ゾーンの設定を構成し、ライセンス情報を表示します。
keywords: 設定, Microsoft Defender, サイバーセキュリティ脅威インテリジェンス, Microsoft Defender for Endpoint, タイム ゾーン, utc, ローカル時刻, ライセンス
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
ms.openlocfilehash: adf693bded45dcb44abd8d1e7892e5edc7b65585
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64467161"
---
# <a name="microsoft-365-defender-time-zone-settings"></a>タイム ゾーンの設定をMicrosoft 365 Defenderする

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)


> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-settings-abovefoldlink)

**タイム ゾーン** メニューを使用してタイム ゾーンを構成し、ライセンス情報を表示します。
:::image type="content" source="images/atp-time-zone.png" alt-text="タイム ゾーンの設定-1" lightbox="images/atp-time-zone.png":::

## <a name="time-zone-settings"></a>タイム ゾーンの設定

時間の側面は、認識されたサイバー攻撃と実際のサイバー攻撃の評価と分析において重要です。

Cyberforensic の調査では、多くの場合、タイムスタンプを使用して一連のイベントをまとめられます。 システムに正しいタイム ゾーン設定が反映されていることが重要です。

Microsoft Defender for Endpoint世界協定時刻 (UTC) またはローカル時刻を表示できます。

現在のタイム ゾーン設定がMicrosoft Defender for Endpoint メニューに表示されます。 表示されるタイム ゾーンは、[ **タイム ゾーン** ] メニューで変更できます。

:::image type="content" source="images/atp-time-zone-menu.png" alt-text="タイム ゾーンの設定-2" lightbox="images/atp-time-zone-menu.png":::

### <a name="utc-time-zone"></a>UTC タイム ゾーン

Microsoft Defender for Endpointでは、既定で UTC 時刻が使用されます。

Microsoft Defender for Endpointタイム ゾーンを UTC に設定すると、すべてのユーザーのすべてのシステム タイムスタンプ (アラート、イベントなど) が UTC で表示されます。 これは、世界中のさまざまな場所で作業しているセキュリティ アナリストが、イベントの調査中に同じタイムスタンプを使用するのに役立ちます。

### <a name="local-time-zone"></a>ローカル タイム ゾーン

ローカル タイム ゾーン設定を使用Microsoft Defender for Endpoint選択できます。 すべてのアラートとイベントは、ローカル タイム ゾーンを使用して表示されます。

ローカル タイム ゾーンは、デバイスの地域設定から取得されます。 地域設定を変更すると、Microsoft Defender for Endpointタイム ゾーンも変更されます。 この設定を選択すると、Microsoft Defender for Endpointに表示されるタイムスタンプが、すべてのMicrosoft Defender for Endpoint ユーザーのローカル時刻に揃えられます。 異なるグローバルな場所にあるアナリストには、地域の設定に従ってMicrosoft Defender for Endpointアラートが表示されるようになりました。

アナリストが 1 つの場所に配置されている場合は、ローカル時刻の使用を選択すると便利です。 この場合、ローカル ユーザーが疑わしいメール リンクをクリックした場合など、イベントをローカル時刻に関連付ける方が簡単な場合があります。

### <a name="set-the-time-zone"></a>タイム ゾーンを設定する

Microsoft Defender for Endpointタイム ゾーンは、既定で UTC に設定されます。 タイム ゾーンを設定すると、すべてのMicrosoft Defender for Endpoint ビューの時刻も変更されます。

タイム ゾーンを設定するには:

1. [ **タイム ゾーン** ] メニューをクリックします。
   :::image type="content" source="images/atp-time-zone.png" alt-text="タイム ゾーンの設定-3" lightbox="images/atp-time-zone.png":::
1. **タイム ゾーン UTC** インジケーターを選択します。
1. **タイムゾーン UTC** またはローカル タイム ゾーン (-7:00 など) を選択します。

### <a name="regional-settings"></a>地域の設定

Microsoft Defender for Endpointに異なる日付形式を適用するには、Internet Explorer (IE) と Microsoft Edge (Edge) の地域設定を使用します。 Google Chrome などの別のブラウザーを使用している場合は、必要な手順に従って、そのブラウザーの時刻と日付の設定を変更します。 

#### <a name="internet-explorer-ie-and-microsoft-edge"></a>Internet Explorer (IE) とMicrosoft Edge

IE とMicrosoft Edge、コントロール **パネルの** **[クロック、言語、リージョン]** オプションで構成されたリージョン設定を使用します。 

#### <a name="known-issues-with-regional-formats"></a>地域形式に関する既知の問題

##### <a name="date-and-time-formats"></a>日付と時刻の形式

時刻と日付の形式には既知の問題がいくつかあります。 サポートされている形式以外に地域設定を構成すると、ポータルで設定が正しく反映されない場合があります。

次の日付と時刻の形式がサポートされています。

- 日付形式 MM/dd/yyyy
- 日付形式 dd/MM/yyyy
- 時間形式 hh:mm:ss (12 時間形式)

現在、次の日付と時刻の形式はサポートされていません。

- 日付形式 yyyy-MM-dd
- 日付形式 dd-MMM-yy
- 日付形式 dd/MM/yy
- 日付形式 MM/dd/yy
- yy の日付形式。 yyyy のみが表示されます。
- 時間形式 HH:mm:ss (24 時間形式)

##### <a name="decimal-symbol-used-in-numbers"></a>数値で使用される小数点記号

**[地域]** 設定の [**数値**] 書式設定でコンマが選択されている場合でも、使用される小数点記号は常にドットです。 たとえば、15,5K は 15.5K と表示されます。
