---
title: 機密情報の種類の制限
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: ''
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: インスタンス数とその他の機密情報の種類の制限について説明します
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5cb574ac9aa0d20818379d7f11ace0a40b68905f
ms.sourcegitcommit: 60c6ce8cbdf539f8b6ff1c6029eb16f81461a3ad
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2022
ms.locfileid: "67434551"
---
# <a name="sensitive-information-type-limits"></a>機密情報の種類の制限

これらの制限は、厳密なデータ一致の機密情報の種類を除くすべての機密情報の種類 (SIT) に適用されます。

これらの制限は、SIT を使用するすべての Microsoft Purview ポリシーに適用されます。

高いパフォーマンスと待機時間を確保するために、カスタム SIT 構成には制限があります。

|極限|値|
|---|---|
|コンプライアンス センターを通じて作成されたカスタム SIT の最大数| 500 |
|正規表現の最大長| 1024 文字|
|キーワード リスト内の特定の用語の最大長| 50 文字|
|キーワード リスト内の用語の最大数| 2048|
|機密情報の種類ごとの個別の正規表現の最大数| 20|
|キーワード ディクショナリの最大サイズ (圧縮後)| 1 MB (~1,000,000 文字)|
|テナント内のキーワード ディクショナリ ベースの SID の最大数|50 |

> [!NOTE]
> ビジネスで 500 を超えるカスタム SIT を作成する必要がある場合は、サポート チケットを発行してください。

### <a name="instance-count-supported-values-for-sit"></a>SIT でサポートされているインスタンス数の値

SIT インスタンス数の制限は、次のソリューションで SIT が使用されている場合に適用されます。

- Microsoft Purview データ損失防止ポリシー
- Microsoft Purview 情報保護 ポリシー
- Microsoft Purview データ ライフサイクル管理
- 通信コンプライアンス
- Microsoft Purview レコード管理
- Microsoft Defender for Cloud Apps
- Microsoft Priva

スキャンされたアイテムがルールの条件を満たすには、1 つのアイテム内の SIT の一意のインスタンスの数が最小値と最大値の間に収める必要があります。 これは **インスタンス数** と呼ばれます。

- **最小** フィールド: 一致をトリガーするためにアイテム内に存在する必要がある SIT の一意のインスタンスの下限 (最小数)。 min フィールドでは、次の値がサポートされます。
  - 1 ~ 500
- **最大** フィールド: アイテム内に存在し、引き続き一致をトリガーできる SIT の一意のインスタンスの数の上限。 max フィールドでは、次の値がサポートされます。
  - 1 ~ 500 - アイテム内の SIT のインスタンス数に対して 500 以下の特定の上限を設定する場合に使用します。
  - Any - スキャンされた項目に SIT の一意のインスタンスの未定義数が見つかり、その一意のインスタンスの数が一意のインスタンスの最小数の値を満たすか超えた場合に、一意のインスタンス数の条件を満たす場合に使用 `Any` します。 つまり、最小値が満たされていれば、一意のインスタンス数の条件が満たされます。

たとえば、1 つのアイテムに少なくとも 500 個の SIT の一意のインスタンスが見つかったときにルールで一致をトリガーする場合は、**最小値** を [最大値]  に`Any``500`設定します。

> [!NOTE]
> 最大 100 個の完全データ一致 (EDM) 評価がサポートされます。 EDM SIT を使用するポリシーは、 **最小** または **最大** インスタンス数の値が 100 を超えて書き込まれるべきではありません。

