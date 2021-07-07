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
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322961"
---
# <a name="modify-a-custom-sensitive-information-type-using-powershell"></a><span data-ttu-id="94014-103">PowerShell を使用してカスタム機密情報の種類を変更する</span><span class="sxs-lookup"><span data-stu-id="94014-103">Modify a custom sensitive information type using PowerShell</span></span>

<span data-ttu-id="94014-104">コンプライアンス センターの PowerShell でカスタムの機密情報の種類を変更するには、次のようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="94014-104">In Compliance center PowerShell, modifying a custom sensitive information type requires you to:</span></span>

1. <span data-ttu-id="94014-105">カスタムの機密情報の種類が含まれている既存のルール パッケージを XML ファイル (または、ある場合は既存の XML ファイル) にエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="94014-105">Export the existing rule package that contains the custom sensitive information type to an XML file (or use the existing XML file if you have it).</span></span>

2. <span data-ttu-id="94014-106">エクスポートした XML ファイルで、カスタムの機密情報の種類を変更します。</span><span class="sxs-lookup"><span data-stu-id="94014-106">Modify the custom sensitive information type in the exported XML file.</span></span>

3. <span data-ttu-id="94014-107">更新した XML ファイルを既存のルール パッケージにインポートします。</span><span class="sxs-lookup"><span data-stu-id="94014-107">Import the updated XML file back into the existing rule package.</span></span>

<span data-ttu-id="94014-108">コンプライアンス センターの PowerShell に接続するには、「[コンプライアンス センター PowerShell に接続する](/powershell/exchange/exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="94014-108">To connect to Compliance Center PowerShell, see [Connect to Compliance Center PowerShell](/powershell/exchange/exchange-online-powershell).</span></span>

### <a name="step-1-export-the-existing-rule-package-to-an-xml-file"></a><span data-ttu-id="94014-109">手順 1: 既存のルール パッケージを XML ファイルにエクスポートします</span><span class="sxs-lookup"><span data-stu-id="94014-109">Step 1: Export the existing rule package to an XML file</span></span>

> [!NOTE]
> <span data-ttu-id="94014-110">XML ファイルのコピーがある場合 (たとえば、先ほど作成してインポートした場合)、次の手順に進んで、XML ファイルを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="94014-110">If you have a copy of the XML file (for example, you just created and imported it), you can skip to the next step to modify the XML file.</span></span>

1. <span data-ttu-id="94014-111">不明な場合には、[Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtype) コマンドレットを実行して、カスタム ルール パッケージの名前を確認します。</span><span class="sxs-lookup"><span data-stu-id="94014-111">If you don't already know it, run the [Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtype) cmdlet to find the name of the custom rule package:</span></span>

   ```powershell
   Get-DlpSensitiveInformationTypeRulePackage
   ```

   > [!NOTE]
   > <span data-ttu-id="94014-p101">組み込みの機密情報の種類が含まれる組み込みのルール パッケージは、Microsoft Rule Package と呼ばれます。コンプライアンス センターの UI で作成したカスタムの機密情報の種類が含まれるルール パッケージは Microsoft.SCCManaged.CustomRulePack と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="94014-p101">The built-in rule package that contains the built-in sensitive information types is named Microsoft Rule Package. The rule package that contains the custom sensitive information types that you created in the Compliance center UI is named Microsoft.SCCManaged.CustomRulePack.</span></span>

2. <span data-ttu-id="94014-114">[Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage) コマンドレットを使用して、カスタム ルール パッケージを変数に格納します。</span><span class="sxs-lookup"><span data-stu-id="94014-114">Use the [Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage) cmdlet to store the custom rule package to a variable:</span></span>

   ```powershell
   $rulepak = Get-DlpSensitiveInformationTypeRulePackage -Identity "RulePackageName"
   ```

   <span data-ttu-id="94014-115">たとえば、ルール パッケージの名前が "Employee ID Custom Rule Pack" (従業員 ID カスタム ルール パック) の場合、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="94014-115">For example, if the name of the rule package is "Employee ID Custom Rule Pack", run the following cmdlet:</span></span>

   ```powershell
   $rulepak = Get-DlpSensitiveInformationTypeRulePackage -Identity "Employee ID Custom Rule Pack"
   ```

3. <span data-ttu-id="94014-116">[Set-Content](/powershell/module/microsoft.powershell.management/set-content) コマンドレットを使用して、カスタム ルール パッケージを XML ファイルにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="94014-116">Use the [Set-Content](/powershell/module/microsoft.powershell.management/set-content) cmdlet to export the custom rule package to an XML file:</span></span>

   ```powershell
   Set-Content -Path "XMLFileAndPath" -Encoding Byte -Value $rulepak.SerializedClassificationRuleCollection
   ```

   <span data-ttu-id="94014-117">この例では、ルール パッケージを C:\My Documents フォルダーの ExportedRulePackage.xml という名前のファイルにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="94014-117">This example export the rule package to the file named ExportedRulePackage.xml in the C:\My Documents folder.</span></span>

   ```powershell
   Set-Content -Path "C:\My Documents\ExportedRulePackage.xml" -Encoding Byte -Value $rulepak.SerializedClassificationRuleCollection
   ```

#### <a name="step-2-modify-the-sensitive-information-type-in-the-exported-xml-file"></a><span data-ttu-id="94014-118">手順 2: エクスポートした XML ファイルでカスタムの機密情報の種類を変更します</span><span class="sxs-lookup"><span data-stu-id="94014-118">Step 2: Modify the sensitive information type in the exported XML file</span></span>

<span data-ttu-id="94014-119">XML ファイル内の機密情報の種類、およびファイル内の他の要素については、このトピックで前述されています。</span><span class="sxs-lookup"><span data-stu-id="94014-119">Sensitive information types in the XML file and other elements in the file are described earlier in this topic.</span></span>

#### <a name="step-3-import-the-updated-xml-file-back-into-the-existing-rule-package"></a><span data-ttu-id="94014-120">手順 3: 更新した XML ファイルを既存のルール パッケージにインポートします</span><span class="sxs-lookup"><span data-stu-id="94014-120">Step 3: Import the updated XML file back into the existing rule package</span></span>

<span data-ttu-id="94014-121">更新された XML を既存のルール パッケージに再びインポートするには、[Set-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/set-dlpsensitiveinformationtyperulepackage) コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="94014-121">To import the updated XML back into the existing rule package, use the [Set-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/set-dlpsensitiveinformationtyperulepackage) cmdlet:</span></span>

```powershell
Set-DlpSensitiveInformationTypeRulePackage -FileData ([Byte[]]$(Get-Content -Path "C:\My Documents\External Sensitive Info Type Rule Collection.xml" -Encoding Byte -ReadCount 0))
```

<span data-ttu-id="94014-122">構文とパラメーターの詳細情報については、[Set-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/set-dlpsensitiveinformationtyperulepackage) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="94014-122">For detailed syntax and parameter information, see [Set-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/set-dlpsensitiveinformationtyperulepackage).</span></span>


## <a name="more-information"></a><span data-ttu-id="94014-123">詳細情報</span><span class="sxs-lookup"><span data-stu-id="94014-123">More information</span></span>

- [<span data-ttu-id="94014-124">データ損失防止について</span><span class="sxs-lookup"><span data-stu-id="94014-124">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)

- [<span data-ttu-id="94014-125">機密情報の種類のエンティティ定義</span><span class="sxs-lookup"><span data-stu-id="94014-125">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)

- [<span data-ttu-id="94014-126">DLP 関数の検索対象</span><span class="sxs-lookup"><span data-stu-id="94014-126">What the DLP functions look for</span></span>](what-the-dlp-functions-look-for.md)
