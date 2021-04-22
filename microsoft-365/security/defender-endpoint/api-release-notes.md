---
title: Microsoft Defender for Endpoint API リリース ノート
description: Microsoft Defender for Endpoint セットの API に対して行われた更新プログラムのリリース ノート。
keywords: Microsoft Defender for Endpoint API リリース ノート、mde、API、Microsoft Defender for Endpoint API、更新プログラム、メモ、リリース
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
ms.technology: mde
ms.openlocfilehash: 02fd995b04c1644e88b38fd0feebc2c80a3681ac
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933627"
---
# <a name="microsoft-defender-for-endpoint-api-release-notes"></a>Microsoft Defender for Endpoint API リリース ノート

**適用対象:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

- Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

次の情報は、Microsoft Defender for Endpoint API に対して行われた更新プログラムと、その更新日を示しています。


> [!TIP]
> RSS フィード: 次の URL をコピーしてフィード リーダーに貼り付け、このページが更新された場合に通知を受け取ります。 
>```
>https://docs.microsoft.com/api/search/rss?search=%22Release+notes+for+updates+made+to+the+Microsoft+Defender+for+Endpoint+set+of+APIs%22&locale=en-us&facet=&%24filter=scopes%2Fany%28t%3A+t+eq+%27Windows+10%27%29
>```


### <a name="10022021"></a>10.02.2021
<hr>

- 新しい API が[追加されました。](batch-update-alerts.md) 

<br>

### <a name="25012021"></a>25.01.2021
<hr>

- Advanced [Hunting API](run-advanced-query-api.md) のレート制限が 1 分あたり 15 ~ 45 要求に更新されました。 

<br>

### <a name="21012021"></a>21.01.2021
<hr>

- 新しい API を追加しました: [タグでデバイスを検索します](machine-tags.md)。 
- 新しい API: インポート [インジケーターを追加しました](import-ti-indicators.md)。 

<br>

### <a name="03012021"></a>03.01.2021
<hr>

- 更新されたアラート証拠: 追加 ***detectionStatus** _, _*_parentProcessFilePath_*_ および _ *_parentProcessFileName_** プロパティ。
- 更新された [Alert エンティティ](alerts.md): ***detectorId プロパティが追加*** されました。

<br>

### <a name="15122020"></a>15.12.2020
<hr>

- 更新された [Device エンティティ](machine.md) : ***IpInterfaces リストが追加*** されました。 「リスト [デバイス」を参照してください](get-machines.md)。

<br>

### <a name="04112020"></a>04.11.2020
<hr>

- 新しい API を追加しました: [デバイスの値を設定します](set-device-value.md)。
- 更新された [Device エンティティ](machine.md) : ***deviceValue プロパティが追加*** されました。

<br>

### <a name="01092020"></a>01.09.2020
<hr>

- 関連する Evidence を使用して Alert エンティティを展開するオプションを追加しました。 「リスト [通知」を参照してください](get-alerts.md)。

<br>
<br>