---
title: 完全一致スキーマと機密情報の種類ウィザードを使用する
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: ''
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 完全一致スキーマと機密情報の種類ウィザードrを使用する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2081de887e09794350222dac3527bb3ff932837a
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/16/2020
ms.locfileid: "49699160"
---
# <a name="use-the-exact-data-match-schema-and-sensitive-information-type-wizard"></a><span data-ttu-id="a3683-103">完全一致スキーマと機密情報の種類ウィザードを使用する</span><span class="sxs-lookup"><span data-stu-id="a3683-103">Use the Exact Data Match Schema and Sensitive Information Type Wizard</span></span>

<span data-ttu-id="a3683-104">[完全一致 (EDM) ベースの分類を使用してカスタムの機密情報の種類を作成するには](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)、さまざまな手順が必要です。</span><span class="sxs-lookup"><span data-stu-id="a3683-104">[Creating a custom sensitive information type with Exact Data Match (EDM) based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)  involves many steps.</span></span>  <span data-ttu-id="a3683-105">このウィザードを使用すると、スキーマと機密情報の種類パターン (ルール パッケージ) ファイルを作成して、プロセスを簡素化できます。</span><span class="sxs-lookup"><span data-stu-id="a3683-105">You can use this wizard to create your schema and sensitive information type pattern (rule package) files to help simplify the process.</span></span>

> [!NOTE]
> <span data-ttu-id="a3683-106">完全一致スキーマと機密情報の種類ウィザードは、World Wide クラウドと GCC クラウドでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="a3683-106">The Exact Data Match Schema and Sensitive Information Type Wizard is only available for the World Wide and GCC clouds only.</span></span>

<span data-ttu-id="a3683-107">このウィザードが代わりとなるのは、次のような場合です。</span><span class="sxs-lookup"><span data-stu-id="a3683-107">This wizard can be used instead of the:</span></span>

- [<span data-ttu-id="a3683-108">機密情報のデータベースのスキーマを定義する</span><span class="sxs-lookup"><span data-stu-id="a3683-108">Define the schema for your database of sensitive information</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#define-the-schema-for-your-database-of-sensitive-information)
- [<span data-ttu-id="a3683-109">パターンを設定する (ルール パッケージ)</span><span class="sxs-lookup"><span data-stu-id="a3683-109">Set up a pattern (rule package)</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#set-up-a-rule-package)

<span data-ttu-id="a3683-110">手順 [パート 1: EDM ベースの分類をセットアップする](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-1-set-up-edm-based-classification)。</span><span class="sxs-lookup"><span data-stu-id="a3683-110">steps in [Part 1: Set up EDM-based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-1-set-up-edm-based-classification).</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="a3683-111">前提条件.</span><span class="sxs-lookup"><span data-stu-id="a3683-111">Pre-requisites</span></span>

1. <span data-ttu-id="a3683-112">EDM [ワーク フローの概要](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#the-work-flow-at-a-glance)で、カスタムの機密情報の種類を作成する手順がわかります。</span><span class="sxs-lookup"><span data-stu-id="a3683-112">Familiarize yourself with the steps to create a custom sensitive information type with EDM [work flow at a glance](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#the-work-flow-at-a-glance).</span></span>

2. <span data-ttu-id="a3683-113">[機密データを .csv 形式で保存](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#save-sensitive-data-in-csv-format) セクションの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="a3683-113">Perform the steps in the [Save sensitive data in .csv format](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#save-sensitive-data-in-csv-format) section.</span></span>

## <a name="use-the-exact-data-match-schema-and-sensitive-information-type-pattern-wizard"></a><span data-ttu-id="a3683-114">完全一致スキーマと機密情報の種類パターンウィザードを使用する</span><span class="sxs-lookup"><span data-stu-id="a3683-114">Use the exact data match schema and sensitive information type pattern wizard</span></span>

1. <span data-ttu-id="a3683-115">テナントの Microsoft 365 コンプライアンス センターでは、**データの分類** > **完全一致** に移動します。 </span><span class="sxs-lookup"><span data-stu-id="a3683-115">In the Microsoft 365 Compliance center for your tenant go to **Data classification** > **Exact data matches**.</span></span>

2. <span data-ttu-id="a3683-116">**EDM スキーマを作成** を選択して、スキーマ ウィザードの構成 ポップアップを開きます。</span><span class="sxs-lookup"><span data-stu-id="a3683-116">Choose **Create EDM schema** to open the schema wizard configuration flyout.</span></span>

![EDM スキーマ作成ウィザードの設定ポップアップ](../media/edm-schema-wizard-1.png)

3. <span data-ttu-id="a3683-118">適切な **名前** と **説明** を入力します。</span><span class="sxs-lookup"><span data-stu-id="a3683-118">Fill in an appropriate **Name** and **Description**.</span></span>

4. <span data-ttu-id="a3683-119">この動作が必要な場合は、**すべてのスキーマ フィールドの区切り文字と句読点を無視する** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a3683-119">Choose **Ignore delimiters and punctuations for all schema fields** if you want that behavior.</span></span> <span data-ttu-id="a3683-120">EDM 構成方法の詳細については、「[ 完全一致 (EDM) ベースの分類をを使用してカスタムの機密情報の種類を作成する](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a3683-120">To learn more about configuring EDM to ignore case or delimitere, see [Creating a custom sensitive information type with Exact Data Match (EDM) based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span></span>

5. <span data-ttu-id="a3683-121">**スキーマ フィールド#1** 必要な値を入力し、必要に応じてフィールドを追加します。</span><span class="sxs-lookup"><span data-stu-id="a3683-121">Fill in your desired values for your **Schema field #1** and add more fields as needed.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="a3683-122">1 つ以上 5 つ以下のスキーマ フィールド を検索可能として指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3683-122">At least one, but no more than five of your schema fields must be designated as searchable.</span></span>

6. <span data-ttu-id="a3683-123">[保存] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a3683-123">Choose save.</span></span> <span data-ttu-id="a3683-124">スキーマ一覧表が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a3683-124">Your schema will now be listed.</span></span>

7. <span data-ttu-id="a3683-125">**EDM の機密情報の種類** を選択し、 **EDM の機密情報の種類を作成** して、機密情報の種類の構成ウィザードを開きます。</span><span class="sxs-lookup"><span data-stu-id="a3683-125">Choose **EDM sensitive info types** and **Create EDM sensitive info type** to open the sensitive info type configuration wizard.</span></span>

8. <span data-ttu-id="a3683-126">**既存のEDM スキーマを選択** を選択し、リストの手順2 から 6 で作成したスキーマを選択します。</span><span class="sxs-lookup"><span data-stu-id="a3683-126">Choose **Choose an existing EDM schema** and choose the schema you created in steps 2-6 from the list.</span></span>

9. <span data-ttu-id="a3683-127">**次へ** を選択し、**パターンの作成** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a3683-127">Choose **Next** and choose **Create pattern**.</span></span>

10. <span data-ttu-id="a3683-128">**信頼度** および **主要要素** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a3683-128">Choose the **Confidence level** and **Primary element**.</span></span>  <span data-ttu-id="a3683-129">パターン構成方法の詳細については、「[コンプライアンス センターでカスタムの機密情報の種類を作成](create-a-custom-sensitive-information-type.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a3683-129">To learn more about configuring a pattern, see [Create a custom sensitive information type in the Compliance Center](create-a-custom-sensitive-information-type.md)</span></span>

11.  <span data-ttu-id="a3683-130">**主要要素の機密情報の種類** を選択し、それをに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="a3683-130">Choose the **Primary element's sensitive info type** to associate it with.</span></span> <span data-ttu-id="a3683-131">利用可能な機密情報の種類の詳細については、「[機密情報の種類のエンティティ定義](sensitive-information-type-entity-definitions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a3683-131">See [Sensitive Information Type Entity Definitions](sensitive-information-type-entity-definitions.md) to learn more about the available sensitive information types.</span></span>

12. <span data-ttu-id="a3683-132">[**完了**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a3683-132">Choose **Done**.</span></span>

13. <span data-ttu-id="a3683-133">目的の **信頼度と文字の間隔** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a3683-133">Choose your desired **Confidence level and character proximity**.</span></span>  <span data-ttu-id="a3683-134">これは、EDM の機密情報の種類の既定値となります。</span><span class="sxs-lookup"><span data-stu-id="a3683-134">This will be the default value for the whole EDM sensitive info type</span></span>

13. <span data-ttu-id="a3683-135">EDM の機密情報の種類の追加のパターンを作成する場合は、 **パターンの作成** 選択します。</span><span class="sxs-lookup"><span data-stu-id="a3683-135">Choose **Create pattern** if you want to creaet additional patterns for your EDM sensitive info type.</span></span>

14. <span data-ttu-id="a3683-136">[**次へ**] を選択し、**名前** および **管理者向けの説明** を入力します。</span><span class="sxs-lookup"><span data-stu-id="a3683-136">Choose **Next** and fill in a **Name** and **Description for admins**.</span></span>

15. <span data-ttu-id="a3683-137">レビューし、[**送信**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a3683-137">Review and choose **Submit**.</span></span>

<span data-ttu-id="a3683-138">編集および削除コントロールを表示して、機密情報の種類パターンを削除または編集します。</span><span class="sxs-lookup"><span data-stu-id="a3683-138">You can delete or edit the sensitive information type pattern by selecting it which surfaces the edit and delete controls.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a3683-139">スキーマを削除し、それが既に EDM の機密情報の種類に関連付けられている場合は、まずEDM の機密情報の種類を削除し、その後、スキーマを削除できます。</span><span class="sxs-lookup"><span data-stu-id="a3683-139">If you want to remove a schema, and it is already associated with an EDM sensitive info type, you must first delete the EDM sensitive info type, then you can delete the schema.</span></span>

## <a name="post-steps"></a><span data-ttu-id="a3683-140">ステップを投稿する</span><span class="sxs-lookup"><span data-stu-id="a3683-140">Post steps</span></span>

<span data-ttu-id="a3683-141">このウィザードを使用して EDM のスキーマおよびパターン (ルール パッケージ) ファイルを作成後、EDM ユーザー機密情報の種類を使用する前に、手順 [パート 2: 機密性の高いデータをハッシュおよびアップロードする](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-2-hash-and-upload-the-sensitive-data)の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3683-141">After you have used this wizard to create your EDM schema and pattern (rule package) files, you still have to perform the steps in [Part 2: Hash and upload the sensitive data](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-2-hash-and-upload-the-sensitive-data) before you can use the EDM custom sensitive information type.</span></span>