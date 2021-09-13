---
title: PowerShell を使用してカスタム機密情報の種類を変更する
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: PowerShell を使用してカスタム機密情報を変更する方法について説明します。
ms.openlocfilehash: 9f8a9ef119e632c695113320ab86a3bdfef8a197
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59218853"
---
# <a name="modify-a-custom-sensitive-information-type-using-powershell"></a>PowerShell を使用してカスタム機密情報の種類を変更する

コンプライアンス センターの PowerShell でカスタムの機密情報の種類を変更するには、次のようにする必要があります。

1. カスタムの機密情報の種類が含まれている既存のルール パッケージを XML ファイル (または、ある場合は既存の XML ファイル) にエクスポートします。

2. エクスポートした XML ファイルで、カスタムの機密情報の種類を変更します。

3. 更新した XML ファイルを既存のルール パッケージにインポートします。

コンプライアンス センターの PowerShell に接続するには、「[コンプライアンス センター PowerShell に接続する](/powershell/exchange/exchange-online-powershell)」を参照してください。

### <a name="step-1-export-the-existing-rule-package-to-an-xml-file"></a>手順 1: 既存のルール パッケージを XML ファイルにエクスポートします

> [!NOTE]
> XML ファイルのコピーがある場合 (たとえば、先ほど作成してインポートした場合)、次の手順に進んで、XML ファイルを変更することができます。

1. 不明な場合には、[Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtype) コマンドレットを実行して、カスタム ルール パッケージの名前を確認します。

   ```powershell
   Get-DlpSensitiveInformationTypeRulePackage
   ```

   > [!NOTE]
   > 組み込みの機密情報の種類が含まれる組み込みのルール パッケージは、Microsoft Rule Package と呼ばれます。コンプライアンス センターの UI で作成したカスタムの機密情報の種類が含まれるルール パッケージは Microsoft.SCCManaged.CustomRulePack と呼ばれます。

2. [Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage) コマンドレットを使用して、カスタム ルール パッケージを変数に格納します。

   ```powershell
   $rulepak = Get-DlpSensitiveInformationTypeRulePackage -Identity "RulePackageName"
   ```

   たとえば、ルール パッケージの名前が "Employee ID Custom Rule Pack" (従業員 ID カスタム ルール パック) の場合、次のコマンドレットを実行します。

   ```powershell
   $rulepak = Get-DlpSensitiveInformationTypeRulePackage -Identity "Employee ID Custom Rule Pack"
   ```

3. [Set-Content](/powershell/module/microsoft.powershell.management/set-content) コマンドレットを使用して、カスタム ルール パッケージを XML ファイルにエクスポートします。

   ```powershell
   Set-Content -Path "XMLFileAndPath" -Encoding Byte -Value $rulepak.SerializedClassificationRuleCollection
   ```

   この例では、ルール パッケージを C:\My Documents フォルダーの ExportedRulePackage.xml という名前のファイルにエクスポートします。

   ```powershell
   Set-Content -Path "C:\My Documents\ExportedRulePackage.xml" -Encoding Byte -Value $rulepak.SerializedClassificationRuleCollection
   ```

#### <a name="step-2-modify-the-sensitive-information-type-in-the-exported-xml-file"></a>手順 2: エクスポートした XML ファイルでカスタムの機密情報の種類を変更します

XML ファイル内の機密情報の種類、およびファイル内の他の要素については、このトピックで前述されています。

#### <a name="step-3-import-the-updated-xml-file-back-into-the-existing-rule-package"></a>手順 3: 更新した XML ファイルを既存のルール パッケージにインポートします

更新された XML を既存のルール パッケージに再びインポートするには、[Set-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/set-dlpsensitiveinformationtyperulepackage) コマンドレットを使用します。

```powershell
Set-DlpSensitiveInformationTypeRulePackage -FileData ([Byte[]]$(Get-Content -Path "C:\My Documents\External Sensitive Info Type Rule Collection.xml" -Encoding Byte -ReadCount 0))
```

構文とパラメーターの詳細情報については、[Set-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/set-dlpsensitiveinformationtyperulepackage) をご覧ください。


## <a name="more-information"></a>詳細情報

- [データ損失防止について](dlp-learn-about-dlp.md)

- [機密情報の種類のエンティティ定義](sensitive-information-type-entity-definitions.md)

- [DLP 関数の検索対象](what-the-dlp-functions-look-for.md)
