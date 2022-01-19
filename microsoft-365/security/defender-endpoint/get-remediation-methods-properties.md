---
title: 修復アクティビティのメソッドとプロパティ
description: API 応答には、テナントで作成& 脆弱性の管理修復アクティビティの脅威が含まれる。 選択した修復タスクに対して、すべての修復アクティビティ、1 つの修復アクティビティ、または公開されているデバイスに関する情報を要求できます。
keywords: apis、修復、修復 API、get、修復タスク、修復方法、修復プロパティ、
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-jweston
author: jweston-1
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 124a44f6a04e4e4e77d80ac91ed4da169e2a4aae
ms.sourcegitcommit: dd6514ae173f1c821d4ec25298145df6cb232e2e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/19/2022
ms.locfileid: "62074560"
---
# <a name="remediation-activity-methods-and-properties"></a>修復アクティビティのメソッドとプロパティ

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!Include[Prerelease information](../../includes/prerelease.md)]

[!Include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!Include[Improve request performance](../../includes/improve-request-performance.md)]

API 応答には、テナント[& 脆弱性の管理](next-gen-threat-and-vuln-mgt.md)された修復アクティビティの脅威が含まれる。

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
カテゴリ|文字列|修復アクティビティのカテゴリ (ソフトウェア/セキュリティ構成)
completerEmail|文字列|修復アクティビティが手動で誰かが完了した場合、この列には自分のメールが含まれる
completerId|文字列|修復アクティビティが手動で誰かが完了した場合、この列にはオブジェクト ID が含まれる
completionMethod|文字列|修復アクティビティは、"完了済みとしてマーク" を選択したユーザーが "自動的に" (すべてのデバイスにパッチが適用されている場合) または "手動" で完了できます。
createdOn|DateTime|この修復アクティビティが作成された時刻
説明|文字列|この修復アクティビティの説明
dueOn|DateTime|この修復アクティビティの作成者セットの期限
fixedDevices||固定されているデバイスの数
ID|文字列|この修復アクティビティの ID
nameId|文字列|関連する製品名
優先度|文字列|この修復アクティビティの作成者セットの優先度 (High\Medium\Low)
productId|文字列|関連する製品 ID
productivityImpactRemediationType|文字列|ユーザーに影響を与えないデバイスに対してだけ、いくつかの構成変更を要求できます。 この値は、「すべての公開デバイス」または「ユーザーに影響を与えないデバイスのみ」の選択を示します。
rbacGroupNames|文字列|関連するデバイス グループ名
recommendedProgram|文字列|にアップグレードする推奨プログラム
recommendedVendor|文字列|アップグレードの推奨ベンダー
recommendedVersion|文字列|更新/アップグレードの推奨バージョン
relatedComponent|文字列|この修復アクティビティの関連コンポーネント (セキュリティ推奨事項の関連コンポーネントと同様)
requesterEmail|文字列|作成者の電子メール アドレス
requesterId|文字列|Creator オブジェクト ID
requesterNotes|文字列|この修復アクティビティに作成者が追加したメモ (フリー テキスト)
Scid|文字列|関連するセキュリティ推奨事項の SCID
状態|文字列|修復アクティビティの状態 (アクティブ/完了)
statusLastModifiedOn|DateTime|状態フィールドが更新された日付
targetDevices|Long|この修復が適用される公開デバイスの数
Title|String|この修復アクティビティのタイトル
型|String|修復の種類
vendorId|文字列|関連ベンダー名

## <a name="see-also"></a>関連項目

- [ID による 1 つの修復アクティビティを取得する](get-remediation-one-activity.md)

- [すべての修復作業を一覧表示する](get-remediation-all-activities.md)

- [1 つの修復アクティビティの暴露デバイスを一覧表示する](get-remediation-exposed-devices-activities.md)

- [リスクベースの脅威& 脆弱性の管理](next-gen-threat-and-vuln-mgt.md)

- [組織の脆弱性](tvm-weaknesses.md)
