---
title: コンピューター リソースの種類
description: Microsoft Defender for Endpoint の Machine リソースタイプのメソッドとプロパティについて説明します。
keywords: apis、サポートされている api、get、コンピューター
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
ms.openlocfilehash: 91ee0c6ec2e4c11b714dee586613b16fd22df278
ms.sourcegitcommit: 4740e69326eb7f8302eec7bab5bd516d498e4492
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/16/2021
ms.locfileid: "59401928"
---
# <a name="machine-resource-type"></a>コンピューター リソースの種類

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a>メソッド

<br>

****

|メソッド|戻り値の型|説明|
|---|---|---|
|[マシンの一覧表示](get-machines.md)|[machine](machine.md) コレクション|組織のコンピューター [エンティティ](machine.md) のセットを一覧表示します。|
|[コンピューターの取得](get-machine-by-id.md)|[コンピューター](machine.md)|コンピューターの [ID を](machine.md) 使用してコンピューターを取得します。|
|[ログオンしているユーザーを取得する](get-machine-log-on-users.md)|[user](user.md) コレクション|コンピューターにログオン [したユーザー](user.md) のセットを取得 [します](machine.md)。|
|[関連するアラートを取得する](get-machine-related-alerts.md)|[alert](alerts.md) コレクション|コンピューターで発生 [した](alerts.md) アラート エンティティのセットを取得 [します](machine.md)。|
|[インストールされたソフトウェアを取得する](get-installed-software.md)|[ソフトウェア](software.md) コレクション|特定のコンピューター ID に関連するインストール済みソフトウェアのコレクションを取得します。|
|[検出された脆弱性を取得する](get-discovered-vulnerabilities.md)|[脆弱性の](vulnerability.md) コレクション|特定のコンピューター ID に関連する検出された脆弱性のコレクションを取得します。|
|[セキュリティ上の推奨事項を取得する](get-security-recommendations.md)|[おすすめ](recommendation.md) コレクション|特定のコンピューター ID に関連するセキュリティ推奨事項のコレクションを取得します。|
|[マシン タグの追加または削除](add-or-remove-machine-tags.md)|[コンピューター](machine.md)|特定のコンピューターにタグを追加または削除します。|
|[IP でマシンを検出する](find-machines-by-ip.md)|[machine](machine.md) コレクション|IP で見られるコンピューターを検索します。|
|[タグでマシンを検出する](find-machines-by-tag.md)|[machine](machine.md) コレクション|タグでコンピューターを [検索します](machine-tags.md)。|
|[不足している KB を取得する](get-missing-kbs-machine.md)|KB コレクション|コンピューター ID に関連付けられている不足している KB の一覧を取得する|
|[デバイス値の設定](set-device-value.md)|[machine](machine.md) コレクション|デバイスの [値を設定します](tvm-assign-device-value.md)。|
|[コンピューターの更新](update-machine-method.md)|[machine](machine.md) コレクション|コンピューターの更新状態を取得します。|
|

## <a name="properties"></a>プロパティ

<br>

****

|プロパティ|種類|説明|
|---|---|---|
|id|文字列|[マシン](machine.md) ID。|
|computerDnsName|文字列|[コンピューター](machine.md) の完全修飾名。|
|firstSeen|DateTimeOffset|Microsoft Defender for [](machine.md) Endpoint によってコンピューターが観測された最初の日付と時刻。|
|lastSeen|DateTimeOffset|最後に受信した完全なデバイス レポートの時刻と日付。 通常、デバイスは 24 時間ごとに完全なレポートを送信します。|
|osPlatform|文字列|オペレーティング システム プラットフォーム。|
|onboardingstatus|文字列|コンピューターのオンボーディングの状態。 可能な値は、「オンボード」と「オフボード」です。|
|osProcessor|String|オペレーティング システム プロセッサ。 代わりに osArchitecture プロパティを使用します。|
|version|String|オペレーティング システムのバージョン。|
|osBuild|Null 許容長|オペレーティング システムのビルド番号。|
|lastIpAddress|文字列|コンピューター上のローカル NIC の最後の[IP。](machine.md)|
|lastExternalIpAddress|文字列|コンピューターがインターネットに [アクセスした](machine.md) 最後の IP。|
|healthStatus|列挙|[マシンの](machine.md) 正常性状態。 指定できる値は、"Active"、"Inactive"、"ImpairedCommunication"、"NoSensorData"、"NoSensorDataImpairedCommunication"、"Unknown" です。|
|rbacGroupName|文字列|コンピューター グループ名。|
|rbacGroupId|String|コンピューター グループ ID。|
|riskScore|Null 許容列挙|Microsoft Defender for Endpoint によって評価されるリスク スコア。 指定できる値は、'None'、'Informational'、'Low'、'Medium'、および 'High' です。|
|aadDeviceId|Null 許容表現 Guid|AAD デバイス ID ( [コンピューターが](machine.md) AAD 参加している場合)。|
|machineTags|String コレクション|コンピューター タグ [の](machine.md) セット。|
|exposureLevel|Null 許容列挙|Microsoft Defender for Endpoint によって評価される露出レベル。 指定できる値は、'None'、'Low'、'Medium'、および 'High' です。|
|deviceValue|Null 許容列挙|デバイス [の値](tvm-assign-device-value.md)です。 指定できる値は、'Normal'、'Low'、および 'High' です。|
|ipAddresses|IpAddress コレクション|***IpAddress オブジェクトの*** セット。 「Get [machines API」を参照してください](get-machines.md)。|
|osArchitecture|文字列|オペレーティング システムのアーキテクチャ。 指定できる値は、"32 ビット"、"64 ビット" です。 osProcessor の代わりにこのプロパティを使用します。|
|
