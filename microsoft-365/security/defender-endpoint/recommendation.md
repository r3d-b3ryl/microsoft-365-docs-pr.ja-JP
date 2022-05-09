---
title: 推奨メソッドとプロパティ
description: 最近使用した上位のアラートを取得します。
keywords: apis, graph api, サポートされている API, get, alerts, recent
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: f6e8295d83d5ab6fb86726903800d2779f394836
ms.sourcegitcommit: 348f3998a029a876a9dcc031f808e9e350804f22
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/03/2021
ms.locfileid: "61301488"
---
# <a name="recommendation-resource-type"></a>推奨事項リソースの種類

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a>メソッド

<br>

****

|メソッド|戻り値の型|説明|
|---|---|---|
|[すべての推奨事項を一覧表示する](get-all-recommendations.md)|レコメンデーション コレクション|組織に影響を与えるすべてのセキュリティ推奨事項の一覧を取得します|
|[ID による推奨事項の取得](get-recommendation-by-id.md)|推奨事項|ID でセキュリティに関する推奨事項を取得します|
|[レコメンデーション ソフトウェアを入手する](list-recommendation-software.md)|[ソフトウェア](software.md)|特定のソフトウェアに関連するセキュリティに関する推奨事項を取得します|
|[レコメンデーション デバイスを取得する](get-recommendation-machines.md)|MachineRef コレクション|セキュリティの推奨事項に関連付けられているデバイスの一覧を取得します。|
|[推奨事項の脆弱性を取得する](get-recommendation-vulnerabilities.md)|[脆弱性の](vulnerability.md) 収集|セキュリティの推奨事項に関連付けられている脆弱性の一覧を取得します。|
|

## <a name="properties"></a>プロパティ

<br>

****

|プロパティ|種類|説明|
|---|---|---|
|id|String|推奨事項 ID|
|productName|文字列型 (String)|関連するソフトウェア名|
|recommendationName|String|推奨事項の名前|
|弱点|Long|検出された脆弱性の数|
|ベンダー|String|関連するベンダー名|
|recommendedVersion|String|推奨されるバージョン|
|recommendedProgram|String|推奨されるプログラム|
|recommendedVendor|String|推奨ベンダー|
|recommendationCategory|String|推奨事項のカテゴリ。 指定できる値は、"Accounts"、"Application"、"Network"、"OS"、"SecurityControls" です。|
|サブカテゴリ|String|推奨事項サブカテゴリ|
|severityScore|倍精度浮動小数点数|組織のデバイスの Microsoft Secure Score (1- 10) に対する構成の潜在的な影響|
|publicExploit|ブール値|パブリック エクスプロイトを利用できます|
|activeAlert|ブール値|アクティブなアラートがこの推奨事項に関連付けられている|
|associatedThreats|String collection|脅威分析レポートは、この推奨事項に関連付けられている|
|remediationType|String|修復の種類。 指定できる値は、"ConfigurationChange"、"Update"、"Upgrade"、"Uninstall" です。|
|状態|列挙|推奨事項の例外の状態。 指定できる値は、"Active" と "Exception" です。|
|configScoreImpact|倍精度浮動小数点数|デバイスに対する Microsoft Secure Score の影響|
|exposureImpact|倍精度浮動小数点数|露出スコアの影響|
|totalMachineCount|Long|インストールされているデバイスの数|
|exposedMachinesCount|Long|脆弱性にさらされているインストール済みデバイスの数|
|nonProductivityImpactedAssets|Long|影響を受けないデバイスの数|
|relatedComponent|String|関連するソフトウェア コンポーネント|
|
