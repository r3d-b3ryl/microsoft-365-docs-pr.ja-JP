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
ms.openlocfilehash: c8024cf08be2259ffa8b6747bebf4943e11e4d60
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695264"
---
# <a name="declare-records-by-using-retention-labels"></a><span data-ttu-id="e1ab6-103">保持ラベルを使用してレコードを宣言する</span><span class="sxs-lookup"><span data-stu-id="e1ab6-103">Declare records by using retention labels</span></span>

><span data-ttu-id="e1ab6-104">*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="e1ab6-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="e1ab6-105">[保持ラベル](retention.md#retention-labels)を使用して、コンテンツをレコードとしてマークします。</span><span class="sxs-lookup"><span data-stu-id="e1ab6-105">You use [retention labels](retention.md#retention-labels) to mark content as a record.</span></span> <span data-ttu-id="e1ab6-106">それらの保持ラベルを発行してユーザーや管理者が手動でコンテンツに適用できるようにするか、レコードとしてマークするコンテンツにそれらのラベルを自動的に適用することができます。</span><span class="sxs-lookup"><span data-stu-id="e1ab6-106">You can either publish those labels so that users and administrators can manually apply them to content, or auto-apply those labels to content that you want to mark as a record.</span></span>

## <a name="configuring-retention-labels-to-declare-records"></a><span data-ttu-id="e1ab6-107">保持ラベルを構成してレコードを宣言する</span><span class="sxs-lookup"><span data-stu-id="e1ab6-107">Configuring retention labels to declare records</span></span>

<span data-ttu-id="e1ab6-108">[保持ラベル](retention.md#retention-labels)を作成するときに、そのコンテンツをレコードとしてマークするオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="e1ab6-108">When you create a [retention label](retention.md#retention-labels), select the option to mark the content as a record.</span></span>

>[!NOTE] 
> <span data-ttu-id="e1ab6-109">Microsoft 365 コンプライアンスセンターで **情報 ガバナンス**から保持ラベルを作成または構成する場合、コンテンツをレコードとしてマークするオプションは利用できません。</span><span class="sxs-lookup"><span data-stu-id="e1ab6-109">The option to mark the content as a record is not available when you create or configure retention labels from **Information Governance** in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="e1ab6-110">代わりに **レコード管理**を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e1ab6-110">Instead, you must use **Records Management**.</span></span>

1. <span data-ttu-id="e1ab6-111">[Microsoft 365 コンプライアンス センター](https://compliance.microsoft.com)で、**レコードの管理** \> **ファイル プラン**に移動します。</span><span class="sxs-lookup"><span data-stu-id="e1ab6-111">In the [Microsoft 365 compliance center](https://compliance.microsoft.com), go to **Records Management** \> **File Plan**.</span></span> <span data-ttu-id="e1ab6-112">[**ファイルプラン**] ページで、[**ラベルの作成**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="e1ab6-112">On the **File plan** page, select **Create a label**.</span></span>

2. <span data-ttu-id="e1ab6-113">ウィザードの [**ラベルの設定**] ページで、コンテンツをレコードとして分類するオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="e1ab6-113">On the **Label settings** page in the wizard, choose the option to classify content as a record.</span></span>
    
   ![[このラベルを使用して、コンテンツをレコードに分類する] チェックボックスをクリックします](../media/recordversioning6.png)

3. <span data-ttu-id="e1ab6-115">必要に応じて、SharePoint や OneDrive のドキュメントと Exchange メールに保持ラベルを適用します。</span><span class="sxs-lookup"><span data-stu-id="e1ab6-115">Apply the retention label to SharePoint or OneDrive documents and Exchange emails, as needed.</span></span> <span data-ttu-id="e1ab6-116">手順については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e1ab6-116">For instructions:</span></span>
    
    - [<span data-ttu-id="e1ab6-117">アイテム保持ラベルを作成してアプリに適用する</span><span class="sxs-lookup"><span data-stu-id="e1ab6-117">Create retention labels and apply them in apps</span></span>](create-apply-retention-labels.md)
    
    - [<span data-ttu-id="e1ab6-118">保持ラベルをコンテンツに自動的に適用する</span><span class="sxs-lookup"><span data-stu-id="e1ab6-118">Apply a retention label to content automatically</span></span>](apply-retention-labels-automatically.md)

## <a name="applying-the-configured-retention-label-to-content"></a><span data-ttu-id="e1ab6-119">コンテンツに構成した保持ラベルを適用する</span><span class="sxs-lookup"><span data-stu-id="e1ab6-119">Applying the configured retention label to content</span></span>

<span data-ttu-id="e1ab6-120">保持ラベルは、コンテンツをレコードとしてマークする場合、ユーザーが以下のようにアプリ内でそれを適用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="e1ab6-120">When retention labels that mark content as a record are made available for users to apply them in apps:</span></span>

- <span data-ttu-id="e1ab6-121">Exchange の場合、メールボックスへの書き込みアクセス権を持つすべてのユーザーは、これらのラベルを適用できます。</span><span class="sxs-lookup"><span data-stu-id="e1ab6-121">For Exchange, any user with write-access to the mailbox can apply these labels.</span></span> 
- <span data-ttu-id="e1ab6-122">SharePoint および OneDrive の場合、既定のメンバー グループ (投稿アクセス許可レベル) のすべてのユーザーがこれらのラベルを適用できます。</span><span class="sxs-lookup"><span data-stu-id="e1ab6-122">For SharePoint and OneDrive, any user in the default Members group (the Contribute permission level) can apply these labels.</span></span>

<span data-ttu-id="e1ab6-123">保持ラベルを使用してレコードとしてマークされたドキュメントの例は、以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e1ab6-123">Example of a document marked as record by using a retention label:</span></span>

![レコードとしてタグ付けされたドキュメントの詳細ウィンドウ](../media/recordversioning7.png)

## <a name="next-steps"></a><span data-ttu-id="e1ab6-125">次の手順</span><span class="sxs-lookup"><span data-stu-id="e1ab6-125">Next steps</span></span>

<span data-ttu-id="e1ab6-126">レコードであるドキュメントを更新する必要がある場合は、「[レコードのバージョン管理を使用して SharePoint または OneDriveに保存されているレコードを更新する](record-versioning.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e1ab6-126">If you need to update documents that are records, see [Use record versioning to update records stored in SharePoint or OneDrive](record-versioning.md).</span></span>

<span data-ttu-id="e1ab6-127">レコードの廃棄の詳細については、「[コンテンツの廃棄](disposition.md)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e1ab6-127">To learn about the disposition of records, see [Disposing of content](disposition.md).</span></span>
