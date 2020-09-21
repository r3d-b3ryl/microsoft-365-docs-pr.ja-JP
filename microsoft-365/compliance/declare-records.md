---
title: 保持ラベルを使用してレコードを宣言する
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 保持ラベルを使用してレコードを宣言する。
ms.openlocfilehash: 841c5197addff704016e344ba7ae44355c872f72
ms.sourcegitcommit: 9f5b136b96b3af4db4cc6f5b1f35130ae60d6b12
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "47817110"
---
# <a name="declare-records-by-using-retention-labels"></a><span data-ttu-id="d5b39-103">保持ラベルを使用してレコードを宣言する</span><span class="sxs-lookup"><span data-stu-id="d5b39-103">Declare records by using retention labels</span></span>

><span data-ttu-id="d5b39-104">*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="d5b39-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="d5b39-105">ドキュメントとメールをレコードとして宣言するには、アイテムをレコードとしてマークする[保持ラベル](retention.md#retention-labels)を使用します。</span><span class="sxs-lookup"><span data-stu-id="d5b39-105">To declare documents and emails as a record, you use [retention labels](retention.md#retention-labels) that mark items as a record.</span></span> <span data-ttu-id="d5b39-106">それらの保持ラベルを発行してユーザーや管理者が手動でコンテンツに適用できるようにするか、レコードとしてマークするコンテンツにそれらのラベルを自動的に適用することができます。</span><span class="sxs-lookup"><span data-stu-id="d5b39-106">You can either publish those labels so that users and administrators can manually apply them to content, or auto-apply those labels to content that you want to mark as a record.</span></span>

## <a name="configuring-retention-labels-to-declare-records"></a><span data-ttu-id="d5b39-107">保持ラベルを構成してレコードを宣言する</span><span class="sxs-lookup"><span data-stu-id="d5b39-107">Configuring retention labels to declare records</span></span>

<span data-ttu-id="d5b39-108">保持ラベルを作成または構成するときに、そのアイテムをレコードとしてマークするオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="d5b39-108">When you create or configure a retention label, select the option to mark items as a record.</span></span>

>[!NOTE] 
> <span data-ttu-id="d5b39-109">Microsoft 365 コンプライアンスセンターで **情報 ガバナンス**から保持ラベルを作成または構成する場合、コンテンツをレコードとしてマークするオプションは利用できません。</span><span class="sxs-lookup"><span data-stu-id="d5b39-109">The option to mark the content as a record is not available when you create or configure retention labels from **Information Governance** in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="d5b39-110">代わりに **レコード管理**を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5b39-110">Instead, you must use **Records Management**.</span></span>

<span data-ttu-id="d5b39-111">コンテンツをレコードとしてマークする新しい保持ラベルを作成するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="d5b39-111">To create a new retention label that marks the content as a record:</span></span>

1. <span data-ttu-id="d5b39-112">[Microsoft 365 コンプライアンス センター](https://compliance.microsoft.com)で、**レコードの管理** \> **ファイル プラン**に移動します。</span><span class="sxs-lookup"><span data-stu-id="d5b39-112">In the [Microsoft 365 compliance center](https://compliance.microsoft.com), go to **Records Management** \> **File Plan**.</span></span> <span data-ttu-id="d5b39-113">[**ファイルプラン**] ページで、[**ラベルの作成**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="d5b39-113">On the **File plan** page, select **Create a label**.</span></span>

2. <span data-ttu-id="d5b39-114">ウィザードの [**保持設定の定義**] ページで、アイテムをレコードとしてマークするオプションを選択します:</span><span class="sxs-lookup"><span data-stu-id="d5b39-114">On the **Define retention settings** page in the wizard, choose the option to mark items as records:</span></span>
    
   ![アイテムをレコードとしてマークする保持設定を選択する](../media/recordversioning6.png)

3. <span data-ttu-id="d5b39-116">必要に応じて、SharePoint や OneDrive のドキュメントと Exchange メールに保持ラベルを適用します。</span><span class="sxs-lookup"><span data-stu-id="d5b39-116">Apply the retention label to SharePoint or OneDrive documents and Exchange emails, as needed.</span></span> <span data-ttu-id="d5b39-117">手順については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d5b39-117">For instructions:</span></span>
    
    - [<span data-ttu-id="d5b39-118">アイテム保持ラベルを作成してアプリに適用する</span><span class="sxs-lookup"><span data-stu-id="d5b39-118">Create retention labels and apply them in apps</span></span>](create-apply-retention-labels.md)
    
    - [<span data-ttu-id="d5b39-119">保持ラベルをコンテンツに自動的に適用する</span><span class="sxs-lookup"><span data-stu-id="d5b39-119">Apply a retention label to content automatically</span></span>](apply-retention-labels-automatically.md)

## <a name="applying-the-configured-retention-label-to-content"></a><span data-ttu-id="d5b39-120">コンテンツに構成した保持ラベルを適用する</span><span class="sxs-lookup"><span data-stu-id="d5b39-120">Applying the configured retention label to content</span></span>

<span data-ttu-id="d5b39-121">保持ラベルは、コンテンツをレコードとしてマークする場合、ユーザーが以下のようにアプリ内でそれを適用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="d5b39-121">When retention labels that mark content as a record are made available for users to apply them in apps:</span></span>

- <span data-ttu-id="d5b39-122">Exchange の場合、メールボックスへの書き込みアクセス権を持つすべてのユーザーは、これらのラベルを適用できます。</span><span class="sxs-lookup"><span data-stu-id="d5b39-122">For Exchange, any user with write-access to the mailbox can apply these labels.</span></span> 
- <span data-ttu-id="d5b39-123">SharePoint および OneDrive の場合、既定のメンバー グループ (投稿アクセス許可レベル) のすべてのユーザーがこれらのラベルを適用できます。</span><span class="sxs-lookup"><span data-stu-id="d5b39-123">For SharePoint and OneDrive, any user in the default Members group (the Contribute permission level) can apply these labels.</span></span>

<span data-ttu-id="d5b39-124">保持ラベルを使用してレコードとしてマークされたドキュメントの例は、以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d5b39-124">Example of a document marked as record by using a retention label:</span></span>

![レコードとしてタグ付けされたドキュメントの詳細ウィンドウ](../media/recordversioning7.png)

## <a name="next-steps"></a><span data-ttu-id="d5b39-126">次の手順</span><span class="sxs-lookup"><span data-stu-id="d5b39-126">Next steps</span></span>

<span data-ttu-id="d5b39-127">レコード管理でサポートされているシナリオの一覧については、「[レコード管理の一般的なシナリオ](get-started-with-records-management.md#common-scenarios-for-records-management)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d5b39-127">For a list of scenarios supported by records management, see [Common scenarios for records management](get-started-with-records-management.md#common-scenarios-for-records-management).</span></span>
