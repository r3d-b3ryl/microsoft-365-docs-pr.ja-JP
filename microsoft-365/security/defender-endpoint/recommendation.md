---
title: 推奨メソッドとプロパティ
description: 最近使用した上位のアラートを取得します。
keywords: apis, graph api, supported apis, get, alerts, recent
search.product: eADQiWindows 10XVcnh
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
ms.openlocfilehash: 5e1364b19ac29f7d753c6d5b479303b8c0ef355b
ms.sourcegitcommit: 07405a81513d1c63071a128b9d5070d3a3bfe1cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/19/2021
ms.locfileid: "61122455"
---
# <a name="recommendation-resource-type"></a>おすすめリソースの種類

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a>メソッド

<br>

****

|メソッド|戻り値の型|説明|
|---|---|---|
|[すべての推奨事項を一覧表示する](get-all-recommendations.md)|おすすめコレクション|組織に影響を与えるすべてのセキュリティ推奨事項の一覧を取得します。|
|[ID による推奨事項の取得](get-recommendation-by-id.md)|推奨事項|セキュリティの推奨事項を ID で取得します。|
|[おすすめソフトウェアを取得する](list-recommendation-software.md)|[ソフトウェア](software.md)|特定のソフトウェアに関連するセキュリティ推奨事項を取得します。|
|[おすすめデバイスを取得する](get-recommendation-machines.md)|MachineRef コレクション|セキュリティ推奨事項に関連付けられているデバイスの一覧を取得します。|
|[推奨事項の脆弱性を取得する](get-recommendation-vulnerabilities.md)|[脆弱性の](vulnerability.md) コレクション|セキュリティ推奨事項に関連付けられている脆弱性の一覧を取得します。|
|

## <a name="properties"></a>プロパティ

<br>

****

|プロパティ|種類|説明|
|---|---|---|
|id|文字列|推奨事項 ID|
|productName|文字列型 (String)|関連するソフトウェア名|
|recommendationName|文字列|おすすめ名|
|弱点|Long|検出された脆弱性の数|
|ベンダー|文字列|関連ベンダー名|
|recommendedVersion|文字列|推奨バージョン|
|recommendedProgram|文字列|推奨プログラム|
|recommendedVendor|文字列|推奨ベンダー|
|recommendationCategory|文字列|おすすめカテゴリ。 使用できる値は、"Accounts"、"Application"、"Network"、"OS"、"SecurityControls" です。|
|subCategory|文字列|おすすめサブカテゴリ|
|severityScore|倍精度浮動小数点数|組織の Microsoft Secure Score for Devices に対する構成の潜在的な影響 (1-10)|
|publicExploit|ブール値|パブリックエクスプロイトが利用可能|
|activeAlert|ブール値|アクティブなアラートは、この推奨事項に関連付けられている|
|associatedThreats|String collection|脅威分析レポートは、この推奨事項に関連付けられている|
|remediationType|文字列|修復の種類。 指定できる値は、"ConfigurationChange"、"Update"、"Upgrade"、"Uninstall" です。|
|状態|列挙|推奨事項の例外の状態。 指定できる値は、"Active" と "Exception" です。|
|configScoreImpact|倍精度浮動小数点数|デバイスの Microsoft Secure Score の影響|
|exposureImpact|倍精度浮動小数点数|露出スコアの影響|
|totalMachineCount|Long|インストールされているデバイスの数|
|exposedMachinesCount|Long|脆弱性にさらされるインストール済みデバイスの数|
|nonProductivityImpactedAssets|Long|影響を受けないデバイスの数|
|relatedComponent|文字列|関連するソフトウェア コンポーネント|
|
