---
title: Microsoft Defender for Endpoint API リリース ノート
description: MICROSOFT DEFENDER FOR ENDPOINT API セットに対して行われた更新プログラムのリリース ノート。
keywords: Microsoft Defender for Endpoint API リリース ノート、mde、API、Microsoft Defender for Endpoint API、更新プログラム、ノート、リリース
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 3087d5cb22f7cc8ef1afedad73de027caf00771e
ms.sourcegitcommit: 414682b9bf42dc19a89c893d3c515aee9765b6e4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2022
ms.locfileid: "67280445"
---
# <a name="microsoft-defender-for-endpoint-api-release-notes"></a>Microsoft Defender for Endpoint API リリース ノート

**適用対象:** 
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)

>Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

次の情報は、Microsoft Defender for Endpoint API に対して行われた更新と、それらが行われた日付の一覧です。

> [!TIP]
> RSS フィード: ご自身のフィード リーダーに次の URL をコピーして貼り付けると、このページの更新時に通知を受け取ることができます。
>
> ```http
> /api/search/rss?search=%22Release+notes+for+updates+made+to+the+Microsoft+Defender+for+Endpoint+set+of+APIs%22&locale=en-us&facet=&%24filter=scopes%2Fany%28t%3A+t+eq+%27Windows+10%27%29
> ```

## <a name="release-notes---newest-to-oldest-ddmmyyyy"></a>リリース ノート - 最新から最も古い (dd.mm.yyyy)

### <a name="08082022"></a>08.08.2022

- 新しい Export Device Health API メソッドを追加しました - GET /api/public/avdeviceshealth [Export device health メソッドとプロパティ](device-health-api-methods-properties.md)

### <a name="06102021"></a>06.10.2021

- 新しい Export Assessment API メソッド - _Delta Export ソフトウェア脆弱性評価 (JSON 応答)_ [デバイスごとのエクスポート評価方法とプロパティを](get-assessment-methods-properties.md)追加しました。

### <a name="05252021"></a>05.25.2021

- デバイスごとの新しい API [Export 評価メソッドとプロパティを](get-assessment-methods-properties.md)追加しました。

### <a name="03052021"></a>03.05.2021

- 新しい API: [修復アクティビティのメソッドとプロパティを](get-remediation-methods-properties.md)追加しました。

### <a name="10022021"></a>10.02.2021

- 新しい API: [バッチ更新アラート](batch-update-alerts.md)を追加しました。

### <a name="25012021"></a>25.01.2021

- [Advanced Hunting API](run-advanced-query-api.md) のレート制限を 1 分あたり 15 から 45 要求に更新しました。

### <a name="21012021"></a>21.01.2021

- 新しい API を追加しました: [タグでデバイスを検索](machine-tags.md)します。
- 新しい API の [追加: インジケーターのインポート](import-ti-indicators.md)。

### <a name="03012021"></a>03.01.2021

- アラートの証拠が更新されました。***detectionStatus** _、 _*_parentProcessFilePath_*_ 、および _ *_parentProcessFileName_** プロパティが追加されました。
- [更新されたアラート エンティティ](alerts.md): ***DetectorId プロパティを*** 追加しました。

### <a name="15122020"></a>15.12.2020

- 更新された [デバイス](machine.md) エンティティ: ***IpInterfaces リストを*** 追加しました。 「 [デバイスの一覧表示](get-machines.md)」を参照してください。

### <a name="04112020"></a>04.11.2020

- 新しい API を追加しました: [デバイスの値を設定します](set-device-value.md)。
- 更新された [デバイス](machine.md) エンティティ: ***deviceValue プロパティを*** 追加しました。

### <a name="01092020"></a>01.09.2020

- 関連する証拠を使用してアラート エンティティを展開するオプションを追加しました。 [アラートの一覧表示を](get-alerts.md)参照してください。
