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
ms.technology: mde
ms.openlocfilehash: f96cfd56cb8d61bc62c34e2b1ee08d6313c6a8ad
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186643"
---
# <a name="machine-resource-type"></a>コンピューター リソースの種類

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender for Endpoint を体験してみませんか? [無料試用版にサインアップします。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a>メソッド

メソッド|戻り値の型 |説明
:---|:---|:---
[リスト コンピューター](get-machines.md) | [machine](machine.md) コレクション | 組織のコンピューター [エンティティ](machine.md) のセットを一覧表示します。
[コンピューターの取得](get-machine-by-id.md) | [コンピューター](machine.md) | コンピューターの [ID を](machine.md) 使用してコンピューターを取得します。
[ログオンしているユーザーを取得する](get-machine-log-on-users.md) | [user](user.md) コレクション | コンピューターにログオン [したユーザー](user.md) のセットを取得 [します](machine.md)。
[関連するアラートを取得する](get-machine-related-alerts.md) | [alert](alerts.md) コレクション | コンピューターで発生 [した](alerts.md) アラート エンティティのセットを取得 [します](machine.md)。
[インストールされているソフトウェアを取得する](get-installed-software.md) | [ソフトウェア](software.md) コレクション | 特定のコンピューター ID に関連するインストール済みソフトウェアのコレクションを取得します。
[検出された脆弱性を取得する](get-discovered-vulnerabilities.md) | [脆弱性の](vulnerability.md) コレクション | 特定のコンピューター ID に関連する検出された脆弱性のコレクションを取得します。
[セキュリティに関する推奨事項を取得する](get-security-recommendations.md) | [おすすめ](recommendation.md) コレクション | 特定のコンピューター ID に関連するセキュリティ推奨事項のコレクションを取得します。
[コンピューター タグを追加または削除する](add-or-remove-machine-tags.md) | [コンピューター](machine.md) | 特定のコンピューターにタグを追加または削除します。
[IP でコンピューターを検索する](find-machines-by-ip.md) | [machine](machine.md) コレクション | IP で見られるコンピューターを検索します。
[タグでコンピューターを検索する](find-machines-by-tag.md) | [machine](machine.md) コレクション | タグでコンピューターを [検索します](machine-tags.md)。
[不足している KB を取得する](get-missing-kbs-machine.md) | KB コレクション | コンピューター ID に関連付けられている不足している KB の一覧を取得する
[デバイスの値を設定する](set-device-value.md)| [machine](machine.md) コレクション | デバイスの [値を設定します](tvm-assign-device-value.md)。

## <a name="properties"></a>プロパティ

プロパティ |   種類   |   説明
:---|:---|:---
id | 文字列 | [マシン](machine.md) ID。
computerDnsName | 文字列 | [コンピューター](machine.md) の完全修飾名。
firstSeen | DateTimeOffset | Microsoft Defender for [](machine.md) Endpoint によってコンピューターが観測された最初の日付と時刻。
lastSeen | DateTimeOffset |最後に受信した完全なデバイス レポートの時刻と日付。 通常、デバイスは 24 時間ごとに完全なレポートを送信します。
osPlatform | 文字列 | オペレーティング システム プラットフォーム。
osProcessor | 文字列 | オペレーティング システム プロセッサ。
version | String | オペレーティング システムのバージョン。
osBuild | Null 許容長 | オペレーティング システムのビルド番号。
lastIpAddress | 文字列 | コンピューター上のローカル NIC の最後の[IP。](machine.md)
lastExternalIpAddress | 文字列 | コンピューターがインターネットに [アクセスした](machine.md) 最後の IP。
healthStatus | 列挙 | [マシンの](machine.md) 正常性状態。 指定できる値は、"Active"、"Inactive"、"ImpairedCommunication"、"NoSensorData"、"NoSensorDataImpairedCommunication"、"Unknown" です。 
rbacGroupName | 文字列 | コンピューター グループ名。
riskScore | Null 許容列挙 | Microsoft Defender for Endpoint によって評価されるリスク スコア。 指定できる値は、'None'、'Informational'、'Low'、'Medium'、および 'High' です。
exposureScore | Null 許容列挙 | [Microsoft](tvm-exposure-score.md) Defender for Endpoint によって評価される露出スコア。 指定できる値は、'None'、'Low'、'Medium'、および 'High' です。
aadDeviceId | Null 許容表現 Guid | AAD デバイス ID ( [コンピューターが](machine.md) AAD 参加している場合)。
machineTags | String collection | コンピューター タグ [の](machine.md) セット。
exposureLevel | Null 許容列挙 | Microsoft Defender for Endpoint によって評価される露出レベル。 指定できる値は、'None'、'Low'、'Medium'、および 'High' です。
deviceValue | Null 許容列挙 | デバイス [の値](tvm-assign-device-value.md)です。 指定できる値は、'Normal'、'Low'、および 'High' です。
ipAddresses | IpAddress コレクション | ***IpAddress オブジェクトの*** セット。 「Get [machines API」を参照してください](get-machines.md)。


