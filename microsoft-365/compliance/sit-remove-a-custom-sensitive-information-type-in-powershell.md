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
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: PowerShell を使用してカスタム機密情報の種類を削除する方法について説明します。
ms.openlocfilehash: 9365eeff6100b16c94b9fa09b06dc51b272b60a6
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322952"
---
# <a name="remove-a-custom-sensitive-information-type-using-powershell"></a><span data-ttu-id="377b6-103">PowerShell を使用してカスタム機密情報の種類を削除する</span><span class="sxs-lookup"><span data-stu-id="377b6-103">Remove a custom sensitive information type using PowerShell</span></span>



<span data-ttu-id="377b6-104">コンプライアンス センターの PowerShell では、カスタムの機密情報の種類を削除する 2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="377b6-104">In Compliance center PowerShell, there are two methods to remove custom sensitive information types:</span></span>

- <span data-ttu-id="377b6-105">**個々のカスタム機密情報の種類を削除** する: [「PowerShell](sit-modify-a-custom-sensitive-information-type-in-powershell.md#modify-a-custom-sensitive-information-type-using-powershell)を使用してカスタム機密情報の種類を変更する」に記載されているメソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="377b6-105">**Remove individual custom sensitive information types**: Use the method documented in [Modify a custom sensitive information type using PowerShell](sit-modify-a-custom-sensitive-information-type-in-powershell.md#modify-a-custom-sensitive-information-type-using-powershell).</span></span> <span data-ttu-id="377b6-106">カスタム機密情報の種類を含むカスタム ルール パッケージをエクスポートし、機密情報の種類を XML ファイルから削除し、更新された XML ファイルを既存のカスタム ルール パッケージにインポートし戻します。</span><span class="sxs-lookup"><span data-stu-id="377b6-106">You export the custom rule package that contains the custom sensitive information type, remove the sensitive information type from the XML file, and import the updated XML file back into the existing custom rule package.</span></span>

- <span data-ttu-id="377b6-107">**カスタム ルール パッケージとそれに含まれるすべてのカスタムの機密情報の種類を削除する**: この方法は、このセクションに記載されています。</span><span class="sxs-lookup"><span data-stu-id="377b6-107">**Remove a custom rule package and all custom sensitive information types that it contains**: This method is documented in this section.</span></span>

> [!NOTE]
> <span data-ttu-id="377b6-108">カスタムの機密情報の種類を削除する前に、その機密情報の種類を参照している DLP ポリシーまたは Exchange メール フロー ルール (別名: トランスポート ルール) がないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="377b6-108">Before your remove a custom sensitive information type, verify that no DLP policies or Exchange mail flow rules (also known as transport rules) still reference the sensitive information type.</span></span>

1. [<span data-ttu-id="377b6-109">コンプライアンス センター PowerShell に接続する</span><span class="sxs-lookup"><span data-stu-id="377b6-109">Connect to Compliance center PowerShell</span></span>](/powershell/exchange/exchange-online-powershell)

2. <span data-ttu-id="377b6-110">カスタム ルール パッケージを削除する場合、[Remove-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/remove-dlpsensitiveinformationtyperulepackage) コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="377b6-110">To remove a custom rule package, use the [Remove-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/remove-dlpsensitiveinformationtyperulepackage) cmdlet:</span></span>

   ```powershell
   Remove-DlpSensitiveInformationTypeRulePackage -Identity "RulePackageIdentity"
   ```

   <span data-ttu-id="377b6-111">Name 値 (任意の言語) または `RulePack id` (GUID) 値を使用して、ルール パッケージを識別します。</span><span class="sxs-lookup"><span data-stu-id="377b6-111">You can use the Name value (for any language) or the `RulePack id` (GUID) value to identify the rule package.</span></span>

   <span data-ttu-id="377b6-112">この例では、"Employee ID Custom Rule Pack" (従業員 ID カスタム ルール パック) という名前のルール パッケージを削除します。</span><span class="sxs-lookup"><span data-stu-id="377b6-112">This example removes the rule package named "Employee ID Custom Rule Pack".</span></span>

   ```powershell
   Remove-DlpSensitiveInformationTypeRulePackage -Identity "Employee ID Custom Rule Pack"
   ```

   <span data-ttu-id="377b6-113">構文とパラメーターの詳細情報については、[Remove-dlpsensitiveinformationtyperulepackage](/powershell/module/exchange/remove-dlpsensitiveinformationtyperulepackage) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="377b6-113">For detailed syntax and parameter information, see [Remove-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/remove-dlpsensitiveinformationtyperulepackage).</span></span>

3. <span data-ttu-id="377b6-114">カスタムの機密情報の種類が正常に削除されたことを確認するには、次に示す手順のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="377b6-114">To verify that you've successfully removed a custom sensitive information type, do any of the following steps:</span></span>

   - <span data-ttu-id="377b6-115">[Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage) コマンドレットを実行して、ルール パッケージが一覧表示されないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="377b6-115">Run the [Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage) cmdlet and verify the rule package is no longer listed:</span></span>

     ```powershell
     Get-DlpSensitiveInformationTypeRulePackage
     ```

   - <span data-ttu-id="377b6-116">[Get-DlpSensitiveInformationType](/powershell/module/exchange/get-dlpsensitiveinformationtype) コマンドレットを実行し、削除されたルール パッケージで機密情報の種類が一覧表示されなくなったことを確認します。</span><span class="sxs-lookup"><span data-stu-id="377b6-116">Run the [Get-DlpSensitiveInformationType](/powershell/module/exchange/get-dlpsensitiveinformationtype) cmdlet to verify the sensitive information types in the removed rule package are no longer listed:</span></span>

     ```powershell
     Get-DlpSensitiveInformationType
     ```

     <span data-ttu-id="377b6-117">カスタムの機密情報の種類の場合、Publisher プロパティ値を Microsoft Corporation 以外に設定します。</span><span class="sxs-lookup"><span data-stu-id="377b6-117">For custom sensitive information types, the Publisher property value will be something other than Microsoft Corporation.</span></span>

   - <span data-ttu-id="377b6-118">\<Name\>Name を機密情報の種類の名前値 (たとえば、従業員 ID) に置き換えて、[Get-DlpSensitiveInformationType](/powershell/module/exchange/get-dlpsensitiveinformationtype)コマンドレットを実行し、機密情報の種類が一覧表示されなくなったことを確認します。</span><span class="sxs-lookup"><span data-stu-id="377b6-118">Replace \<Name\> with the Name value of the sensitive information type (for example, Employee ID) and run the [Get-DlpSensitiveInformationType](/powershell/module/exchange/get-dlpsensitiveinformationtype) cmdlet to verify the sensitive information type is no longer listed:</span></span>

     ```powershell
     Get-DlpSensitiveInformationType -Identity "<Name>"
     ```

## <a name="more-information"></a><span data-ttu-id="377b6-119">詳細情報</span><span class="sxs-lookup"><span data-stu-id="377b6-119">More information</span></span>

- [<span data-ttu-id="377b6-120">データ損失防止について</span><span class="sxs-lookup"><span data-stu-id="377b6-120">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)

- [<span data-ttu-id="377b6-121">機密情報の種類のエンティティ定義</span><span class="sxs-lookup"><span data-stu-id="377b6-121">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)

- [<span data-ttu-id="377b6-122">DLP 関数の検索対象</span><span class="sxs-lookup"><span data-stu-id="377b6-122">What the DLP functions look for</span></span>](what-the-dlp-functions-look-for.md)
