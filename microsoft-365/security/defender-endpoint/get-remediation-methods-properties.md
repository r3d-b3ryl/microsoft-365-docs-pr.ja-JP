---
title: 修復アクティビティのメソッドとプロパティ
description: API 応答には、テナントで作成& 脆弱性の管理修復アクティビティの脅威が含まれる。 選択した修復タスクに対して、すべての修復アクティビティ、1 つの修復アクティビティ、または公開されているデバイスに関する情報を要求できます。
keywords: apis、修復、修復 API、get、修復タスク、修復方法、修復プロパティ、
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-jweston
author: jweston-1
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 0ca1bc84d5e8cf5498ed3dc19cba3928823796ff
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59190981"
---
# <a name="remediation-activity-methods-and-properties"></a>修復アクティビティのメソッドとプロパティ

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

API 応答には、テナント [& 脆弱性の管理](next-gen-threat-and-vuln-mgt.md)   された脅威と修復アクティビティが含まれる。

## <a name="methods"></a>メソッド

メソッド|データ型|説明
:---|:---|:---
[すべての修復作業を一覧表示する](get-remediation-all-activities.md)|調査コレクション|すべての修復アクティビティに関する情報を返します。
[1 つの修復アクティビティの暴露デバイスを一覧表示する](get-remediation-exposed-devices-activities.md)|調査エンティティ|指定した修復アクティビティの公開デバイスに関する情報を返します。
[ID による 1 つの修復アクティビティを取得する](get-remediation-one-activity.md)|調査エンティティ|指定した修復アクティビティの情報を返します。

修復アクティビティの [詳細については、次の情報を参照してください](tvm-remediation.md)。

## <a name="properties"></a>プロパティ

プロパティ ID|データ型|説明
:---|:---|:---
category|String|修復アクティビティのカテゴリ (ソフトウェア/セキュリティ構成)
completerEmail|String|修復アクティビティが手動で誰かが完了した場合、この列には自分のメールが含まれる
completerId|String|修復アクティビティが手動で誰かが完了した場合、この列にはオブジェクト ID が含まれる
completionMethod|String|修復アクティビティは、"完了済みとしてマーク" を選択したユーザーが "自動的に" (すべてのデバイスにパッチが適用されている場合) または "手動" で完了できます。
createdOn|DateTime|この修復アクティビティが作成された時刻
説明|String|この修復アクティビティの説明
dueOn|DateTime|この修復アクティビティの作成者セットの期限
fixedDevices||固定されているデバイスの数
id|String|この修復アクティビティの ID
nameId|String|関連する製品名
priority|String|この修復アクティビティの作成者セットの優先度 (High\Medium\Low)
productId|String|関連する製品 ID
productivityImpactRemediationType|String|いくつかの構成変更は、ユーザーに影響がないデバイスに対してだけ要求できます。 この値は、「すべての公開デバイス」または「ユーザーに影響を与えないデバイスのみ」の選択を示します。
rbacGroupNames|String|関連するデバイス グループ名
recommendedProgram|String|にアップグレードする推奨プログラム
recommendedVendor|String|アップグレードの推奨ベンダー
recommendedVersion|String|更新/アップグレードの推奨バージョン
relatedComponent|String|この修復アクティビティの関連コンポーネント (セキュリティ推奨事項の関連コンポーネントと同様)
requesterEmail|String|作成者の電子メール アドレス
requesterId|String|Creator オブジェクト ID
requesterNotes|String|この修復アクティビティに作成者が追加したメモ (フリー テキスト)
scid|String|関連するセキュリティ推奨事項の SCID
status|String|修復アクティビティの状態 (アクティブ/完了)
statusLastModifiedOn|DateTime|状態フィールドが更新された日付
targetDevices|Long|この修復が適用される公開デバイスの数
title|String|この修復アクティビティのタイトル
type|String|修復の種類
vendorId|String|関連ベンダー名

## <a name="see-also"></a>関連項目

- [ID による 1 つの修復アクティビティを取得する](get-remediation-one-activity.md)

- [すべての修復作業を一覧表示する](get-remediation-all-activities.md)

- [1 つの修復アクティビティの暴露デバイスを一覧表示する](get-remediation-exposed-devices-activities.md)

- [リスクベースの脅威& 脆弱性の管理](next-gen-threat-and-vuln-mgt.md)

- [組織の脆弱性](tvm-weaknesses.md)
