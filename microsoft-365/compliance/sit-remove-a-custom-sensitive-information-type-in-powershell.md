---
title: PowerShell を使用してカスタム機密情報の種類を削除する
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
description: PowerShell を使用してカスタム機密情報の種類を削除する方法について説明します。
ms.openlocfilehash: bb3bf67a1493ec232a66b2bdc0c784ea52de32f5
ms.sourcegitcommit: 8410a49995a084e4cc9b3f7286c8d506b7a85d79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/11/2021
ms.locfileid: "60914406"
---
# <a name="remove-a-custom-sensitive-information-type-using-powershell"></a>PowerShell を使用してカスタム機密情報の種類を削除する

コンプライアンス センターの PowerShell では、カスタムの機密情報の種類を削除する 2 つの方法があります。

- **個々のカスタム機密情報の種類を削除** する: [「PowerShell](sit-modify-a-custom-sensitive-information-type-in-powershell.md#modify-a-custom-sensitive-information-type-using-powershell)を使用してカスタム機密情報の種類を変更する」に記載されているメソッドを使用します。 カスタム機密情報の種類を含むカスタム ルール パッケージをエクスポートし、機密情報の種類を XML ファイルから削除し、更新された XML ファイルを既存のカスタム ルール パッケージにインポートし戻します。

- **カスタム ルール パッケージとそれに含まれるすべてのカスタムの機密情報の種類を削除する**: この方法は、このセクションに記載されています。

> [!NOTE]
> カスタムの機密情報の種類を削除する前に、その機密情報の種類を参照している DLP ポリシーまたは Exchange メール フロー ルール (別名: トランスポート ルール) がないことを確認してください。

1. [コンプライアンス センター PowerShell に接続する](/powershell/exchange/exchange-online-powershell)

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

- [データ損失防止について](dlp-learn-about-dlp.md)

- [機密情報の種類のエンティティ定義](sensitive-information-type-entity-definitions.md)

- [DLP 関数の検索対象](what-the-dlp-functions-look-for.md)
