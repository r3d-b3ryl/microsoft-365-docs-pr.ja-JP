---
title: DLP 用のカスタムの機密情報の種類
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: 04/23/2019
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 主なパターン、英数字、信頼度など、データ損失防止 (DLP) のカスタム機密情報の種類の概要について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6934edba6eef03bc9d4bfc5c1c69f127a7d3a0e5
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817966"
---
# <a name="custom-sensitive-information-types"></a>カスタムの機密情報の種類

Microsoft 365 には機密情報の種類が多数組み込まれており、[データ損失防止](data-loss-prevention-policies.md) (DLP)、あるいは [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security) 用に組織内で使用することができます。 組み込まれている機密情報の種類は、クレジットカード番号、銀行口座番号、パスポート番号などを特定して保護するのに役立ちます。これらの情報の特定と保護は、正規表現 (regex) または関数によって定義されたパターンに基づいて行われます。 詳細については、「[機密情報の種類で検索される情報](what-the-sensitive-information-types-look-for.md)」を参照してください。

ただし、組織固有の形式で、異なる機密情報の種類 (従業員 ID やプロジェクト番号など) を特定して保護する必要がある場合は、 カスタムの機密情報の種類を作成することができます。

カスタムの機密情報の種類の基本的な部分は次のとおりです。

- **プライマリ パターン**: 従業員 ID 番号、プロジェクト番号など。これは通常、正規表現 (RegEx) によって識別されますが、キーワード リストにもできます。

- **Additional evidence**: Suppose you're looking for a nine-digit employee ID number. Not all nine-digit numbers are employee ID numbers, so you can look for additional text: keywords like "employee", "badge", "ID", or other text patterns based on additional regular expressions. This supporting evidence (also known as _supporting_ or _corroborative_ evidence) increases the likelihood that nine-digit number found in content is really an employee ID number.

- **Character proximity**: It makes sense that the closer the primary pattern and the supporting evidence are to each other, the more likely the detected content is going to be what you're looking for. You can specify the character distance between the primary pattern and the supporting evidence (also known as the _proximity window_) as shown in the following diagram:

    ![補強証拠と近接ウィンドウの図](../media/dc68e38e-dfa1-45b8-b204-89c8ba121f96.png)

- **Confidence level**: The more supporting evidence you have, the higher the likelihood that a match contains the sensitive information you're looking for. You can assign higher levels of confidence for matches that are detected by using more evidence.

  When satisfied, a pattern returns a count and confidence level, which you can use in the conditions in your DLP policies. When you add a condition for detecting a sensitive information type to a DLP policy, you can edit the count and confidence level as shown in the following diagram:

    ![インスタンス数と一致精度オプション](../media/11d0b51e-7c3f-4cc6-96d8-b29bcdae1aeb.png)

## <a name="creating-custom-sensitive-information-types"></a>カスタムの機密情報の種類を作成する

次のオプションを使用して、セキュリティ/コンプライアンス センターでカスタムの機密情報の種類を作成できます。

- **EDM を使用する** (新規) データ一致 (EDM) に基づく分類によって、カスタム機密情報の種類を設定します。 この方法では、定期的に更新できる安全なデータベースを使用して、動的な機密情報の種類を作成することができます。 詳細については、「[Exact Data Match に基づく分類で、カスタムの機密情報の種類を作成する](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)」を参照してください。

- **PowerShell を使用する** PowerShell を使用して、カスタムの機密情報の種類を設定します。 この方法は、UI を使用する場合よりも複雑ですが、より多くの構成オプションがあります。 詳細については、「[セキュリティ/コンプライアンス センターの PowerShell でカスタムの機密情報の種類を作成する](create-a-custom-sensitive-information-type-in-scc-powershell.md)」を参照してください。

- **UI を使用する** セキュリティ/コンプライアンス センターの UI を使用して、カスタムの機密情報の種類を設定します。 この方法では、正規表現、キーワード、キーワード辞書を使用することができます。 詳細については、「[カスタムの機密情報の種類を作成する](create-a-custom-sensitive-information-type.md)」を参照してください。



