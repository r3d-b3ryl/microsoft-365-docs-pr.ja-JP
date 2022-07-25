---
title: すべての医療条件エンティティ定義
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
search.appverid: MET150
ms.topic: reference
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContainsSensitiveInformation
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
hideEdit: true
feedback_system: None
recommendations: false
description: すべての医療条件の機密情報の種類エンティティ定義。
ms.openlocfilehash: 85d4f7fc5159d486aff23318df1d4dca5da0856e
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66997032"
---
# <a name="all-medical-terms-and-conditions"></a>すべての医療条項

すべての医療契約条件は、医療条件と医療条件を検出するバンドルされた名前付きエンティティです。 英語の用語のみを検出します。 この SIT を使用して、医療の使用条件と考えられるすべての一致を検出します。

## <a name="format"></a>フォーマット

Dictionary

## <a name="pattern"></a>パターン

Dictionary

## <a name="checksum"></a>チェックサム

不要

## <a name="description"></a>説明

このバンドルされた名前付きエンティティは、キュレーションされた辞書に存在する医療条件に言及するテキストと一致します。 サポートされている言語ごとに 1 つのキュレーションされた辞書があります。 辞書は、多くの国際医療リソースから提供されています。 辞書には、多数の誤検知を危険にさらさずに、できるだけ多くの病状が含まれています。 各エントリには、次のように、カバレッジを確保するために 1 つの条件が一般的に記述されるさまざまなフォームが含まれています。

- *TB*
- *結核*
- *phthisis pulmonalis*

## <a name="contains"></a>Contains

このバンドルされた名前付きエンティティ SIT には、これらの個々の SIT が含まれています。

- 血液検査の用語
- 薬品の種類
- 病気
- ジェネリック医薬品名
- 社会保障に関する米国の障穣評価に記載されている障穣
- 臨床検査の用語
- 病状に関連するライフスタイル
- 医療の専門分野
- 外科的処置
- ブランド医薬品名

