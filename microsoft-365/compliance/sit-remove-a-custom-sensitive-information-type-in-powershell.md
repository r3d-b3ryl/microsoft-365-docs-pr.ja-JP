---
title: PowerShell を使用してカスタムの機密情報の種類を削除する
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: PowerShell を使用してカスタムの機密情報の種類を削除する方法について説明します
ms.openlocfilehash: e935c9340c353561e71e25fdadfec5509da041e5
ms.sourcegitcommit: 133bf9097785309da45df6f374a712a48b33f8e9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2022
ms.locfileid: "66014742"
---
# <a name="remove-a-custom-sensitive-information-type-using-powershell"></a>PowerShell を使用してカスタムの機密情報の種類を削除する

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

Security & Compliance PowerShell では、カスタムの機密情報の種類を削除するには、次の 2 つの方法があります。

- **個々のカスタム機密情報の種類を削除する**: PowerShell を使用して [カスタムの機密情報の種類を変更する](sit-modify-a-custom-sensitive-information-type-in-powershell.md#modify-a-custom-sensitive-information-type-using-powershell)に関するページに記載されているメソッドを使用します。 カスタムの機密情報の種類を含むカスタム規則パッケージをエクスポートし、XML ファイルから機密情報の種類を削除し、更新された XML ファイルを既存のカスタム ルール パッケージにインポートします。

- **カスタム ルール パッケージとそれに含まれるすべてのカスタムの機密情報の種類を削除する**: この方法は、このセクションに記載されています。

> [!NOTE]
> カスタムの機密情報の種類を削除する前に、その機密情報の種類を参照している DLP ポリシーまたは Exchange メール フロー ルール (別名: トランスポート ルール) がないことを確認してください。

1. [セキュリティ & コンプライアンス PowerShell](/powershell/exchange/exchange-online-powershell)

2. カスタム ルール パッケージを削除する場合、[Remove-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/remove-dlpsensitiveinformationtyperulepackage) コマンドレットを使用します。

   ```powershell
   Remove-DlpSensitiveInformationTypeRulePackage -Identity "RulePackageIdentity"
   ```

   Name 値 (任意の言語) または `RulePack id` (GUID) 値を使用して、ルール パッケージを識別します。

   この例では、"Employee ID Custom Rule Pack" (従業員 ID カスタム ルール パック) という名前のルール パッケージを削除します。

   ```powershell
   Remove-DlpSensitiveInformationTypeRulePackage -Identity "Employee ID Custom Rule Pack"
   ```

   構文とパラメーターの詳細情報については、[Remove-dlpsensitiveinformationtyperulepackage](/powershell/module/exchange/remove-dlpsensitiveinformationtyperulepackage) をご覧ください。

3. カスタムの機密情報の種類が正常に削除されたことを確認するには、次に示す手順のいずれかを実行します。

   - [Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage) コマンドレットを実行して、ルール パッケージが一覧表示されないことを確認します。

     ```powershell
     Get-DlpSensitiveInformationTypeRulePackage
     ```

   - [Get-DlpSensitiveInformationType](/powershell/module/exchange/get-dlpsensitiveinformationtype) コマンドレットを実行し、削除されたルール パッケージで機密情報の種類が一覧表示されなくなったことを確認します。

     ```powershell
     Get-DlpSensitiveInformationType
     ```

     カスタムの機密情報の種類の場合、Publisher プロパティ値を Microsoft Corporation 以外に設定します。

   - \<Name\>Name を機密情報の種類の名前値 (たとえば、従業員 ID) に置き換えて、[Get-DlpSensitiveInformationType](/powershell/module/exchange/get-dlpsensitiveinformationtype)コマンドレットを実行し、機密情報の種類が一覧表示されなくなったことを確認します。

     ```powershell
     Get-DlpSensitiveInformationType -Identity "<Name>"
     ```

## <a name="more-information"></a>詳細情報

- [Microsoft Purview データ損失防止についての説明](dlp-learn-about-dlp.md)

- [機密情報の種類のエンティティ定義](sensitive-information-type-entity-definitions.md)

- [機密情報の種類の機能](sit-functions.md)
