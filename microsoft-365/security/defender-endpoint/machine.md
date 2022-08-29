---
title: マシン リソースの種類
description: Microsoft Defender for Endpointの Machine リソースの種類のメソッドとプロパティについて説明します。
keywords: apis、サポートされている API、get、machines
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
ms.custom: api
ms.openlocfilehash: d5b6c51fd6f0e581a1299e72600930d9ef4a2a3e
ms.sourcegitcommit: 217108c59be41b01963a393b4f16d137636fe6a8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/12/2022
ms.locfileid: "67327401"
---
# <a name="machine-resource-type"></a>マシン リソースの種類

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
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
|[マシンの一覧表示](get-machines.md)|[machine](machine.md) コレクション|組織内の [マシン](machine.md) エンティティのセットを一覧表示します。|
|[マシンを取得する](get-machine-by-id.md)|[マシン](machine.md)|ID で [コンピューター](machine.md) を取得します。|
|[ログオンしているユーザーを取得する](get-machine-log-on-users.md)|[user](user.md) コレクション|コンピューターにログオンした [ユーザー](user.md) のセットを取得 [します](machine.md)。|
|[関連するアラートを取得する](get-machine-related-alerts.md)|[alert](alerts.md) コレクション|コンピューターで発生した [アラート](alerts.md) エンティティのセットを取得 [します](machine.md)。|
|[インストールされたソフトウェアを取得する](get-installed-software.md)|[ソフトウェア](software.md) コレクション|特定のマシン ID に関連するインストール済みソフトウェアのコレクションを取得します。|
|[検出された脆弱性を取得する](get-discovered-vulnerabilities.md)|[脆弱性の](vulnerability.md) 収集|特定のマシン ID に関連する検出された脆弱性のコレクションを取得します。|
|[セキュリティ上の推奨事項を取得する](get-security-recommendations.md)|[レコメンデーション](recommendation.md) コレクション|特定のマシン ID に関連するセキュリティに関する推奨事項のコレクションを取得します。|
|[マシン タグの追加または削除](add-or-remove-machine-tags.md)|[マシン](machine.md)|特定のコンピューターにタグを追加または削除します。|
|[IP でマシンを検出する](find-machines-by-ip.md)|[machine](machine.md) コレクション|IP で見られるマシンを検索します。|
|[タグでマシンを検出する](find-machines-by-tag.md)|[machine](machine.md) コレクション|タグでコンピューターを検索 [します](machine-tags.md)。|
|[不足している KB を取得する](get-missing-kbs-machine.md)|KB コレクション|マシン ID に関連付けられている欠落している KB の一覧を取得する|
|[デバイス値の設定](set-device-value.md)|[machine](machine.md) コレクション|[デバイスの値を設定します](tvm-assign-device-value.md)。|
|[コンピューターの更新](update-machine-method.md)|[machine](machine.md) コレクション|コンピューターの更新状態を取得します。|
|

## <a name="properties"></a>プロパティ

<br>

****

|プロパティ|種類|説明|
|---|---|---|
|id|文字列|[マシン](machine.md) ID。|
|computerDnsName|String|[マシン](machine.md) の完全修飾名。|
|firstSeen|DateTimeOffset|[Microsoft Defender for Endpointによってマシン](machine.md)が観察された最初の日付と時刻。|
|lastSeen|DateTimeOffset|最後に受信した完全なデバイス レポートの日時。 通常、デバイスは 24 時間ごとに完全なレポートを送信します。|
|osPlatform|String|オペレーティング システム プラットフォーム。|
|onboardingstatus|文字列|マシンオンボードの状態。 指定できる値は、"オンボード済み" と "オフボード" です。|
|osProcessor|文字列|オペレーティング システム プロセッサ。 代わりに osArchitecture プロパティを使用します。|
|version|String|オペレーティング システムのバージョン。|
|osBuild|Null 許容 long|オペレーティング システムのビルド番号。|
|lastIpAddress|文字列|[コンピューター](machine.md)上のローカル NIC の最後の IP。|
|lastExternalIpAddress|文字列|[コンピューター](machine.md)がインターネットにアクセスした最後の IP。|
|healthStatus|列挙|[マシン](machine.md) の正常性状態。 指定できる値は、"Active"、"Inactive"、"ImpairedCommunication"、"NoSensorData"、"NoSensorDataImpairedCommunication"、"Unknown" です。|
|rbacGroupName|String|マシン グループ名。|
|rbacGroupId|文字列|マシン グループ ID。|
|riskScore|Null 許容列挙型|Microsoft Defender for Endpointによって評価されたリスク スコア。 指定できる値は、'None'、'Informational'、'Low'、'Medium'、'High' です。|
|aadDeviceId|Null 許容表現 Guid|AAD デバイス ID ( [マシン](machine.md) が AAD Joined の場合)。|
|machineTags|String コレクション|[マシン](machine.md) タグのセット。|
|exposureLevel|Null 許容列挙型|Microsoft Defender for Endpointによって評価される露出レベル。 指定できる値は、'None'、'Low'、'Medium'、'High' です。|
|deviceValue|Null 許容列挙型|[デバイスの値](tvm-assign-device-value.md)。 指定できる値は、"Normal"、"Low"、"High" です。|
|ipAddresses|IpAddress コレクション|***IpAddress*** オブジェクトのセット。 「 [Get machines API](get-machines.md)」を参照してください。|
|osArchitecture|文字列|オペレーティング システムアーキテクチャ。 指定できる値は、"32 ビット"、"64 ビット" です。 osProcessor の代わりにこのプロパティを使用します。|
|
