---
title: コンプライアンス センターでカスタムの機密情報の種類を管理する
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.date: ''
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: コンプライアンス センターでカスタムの機密情報の種類を変更および削除する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0efbb93096fc3c0b61a57319aa2d23a079f684d1
ms.sourcegitcommit: bb493f12701f6d6ee7d5e64b541adb87470bc7bc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2022
ms.locfileid: "62902626"
---
# <a name="manage-custom-sensitive-information-types-in-the-compliance-center"></a>コンプライアンス センターでカスタムの機密情報の種類を管理する

この記事では、コンプライアンス センターで既存のカスタム機密情報の種類を変更および削除する手順について説明します。

## <a name="modify-custom-sensitive-information-types-in-the-compliance-center"></a>コンプライアンス センターでカスタムの機密情報の種類を変更する

1. コンプライアンス センターで、**[データの分類]** \> **[機密情報の種類]** の順に移動し、変更する機密情報の種類をリストから選択して **[編集]** を選択します。

2. 固有の重要要素およびサポート要素、信頼度レベル、文字の近接度、[**追加チェック**](sit-regex-validators-additional-checks.md#sensitive-information-type-additional-checks)で、その他のパターンを追加、もしくは既存のパターンの編集と削除を行うことができます。

## <a name="remove-custom-sensitive-information-types-in-the-compliance-center"></a>コンプライアンス センターでカスタムの機密情報の種類を削除する 

> [!NOTE]
> カスタムの機密情報の種類のみを削除できます。組み込みの機密情報の種類は削除できません。

> [!IMPORTANT]
> カスタムの機密情報の種類を削除する前に、その機密情報の種類を参照している DLP ポリシーまたは Exchange メール フロー ルール (別名: トランスポート ルール) がないことを確認してください。

1. コンプライアンス センターで、**[データの分類]** \> **[機密情報の種類]** の順に移動し、削除したいリストから機密情報の種類を選択します。

2. 開くフライアウトで、**[削除]** を選択します。
