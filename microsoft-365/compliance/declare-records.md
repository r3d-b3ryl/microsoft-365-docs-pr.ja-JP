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
ms.openlocfilehash: 490f81ba9c1d2d291539107650ec3c3f5938eba8
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "48198926"
---
# <a name="declare-records-by-using-retention-labels"></a><span data-ttu-id="f1816-103">保持ラベルを使用してレコードを宣言する</span><span class="sxs-lookup"><span data-stu-id="f1816-103">Declare records by using retention labels</span></span>

><span data-ttu-id="f1816-104">*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="f1816-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="f1816-105">ドキュメントとメールを[レコード](records-management.md#records)として宣言するには、コンテンツを**レコード**または**規制レコード**としてマークする[保持ラベル](retention.md#retention-labels)を使用します。</span><span class="sxs-lookup"><span data-stu-id="f1816-105">To declare documents and emails as [records](records-management.md#records), you use [retention labels](retention.md#retention-labels) that mark the content as a **record** or a **regulatory record**.</span></span>

> [!NOTE]
> <span data-ttu-id="f1816-106">規制レコードは、現在プレビュー中です。</span><span class="sxs-lookup"><span data-stu-id="f1816-106">Regulatory records are currently in preview.</span></span>

<span data-ttu-id="f1816-107">レコードと規制レコードのどちらを使用すればよいかわからない場合は、「[許可またはブロックされているアクションの制限を比較する](records-management.md#compare-restrictions-for-what-actions-are-allowed-or-blocked)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f1816-107">If you're not sure whether to use a record or a regulatory record, see [Compare restrictions for what actions are allowed or blocked](records-management.md#compare-restrictions-for-what-actions-are-allowed-or-blocked).</span></span> <span data-ttu-id="f1816-108">規制レコードを使用する必要がある場合は、次のセクションで説明するように、まず PowerShell コマンドを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f1816-108">If you need to use regulatory records, you must first run a PowerShell command, as described in the next section.</span></span>

<span data-ttu-id="f1816-109">その後、ユーザーや管理者がラベルをコンテンツに適用できるように保持ラベル ポリシーでラベルを公開するか、アイテムをレコード (規制レコードではない) としてマークするラベルの場合は、レコードとして宣言するコンテンツにラベルを自動適用することができます。</span><span class="sxs-lookup"><span data-stu-id="f1816-109">You can then either publish those labels in a retention label policy so that users and administrators can apply them to content, or for labels that mark items as records (but not regulatory records), auto-apply those labels to content that you want to declare a record.</span></span>

## <a name="how-to-display-the-option-to-mark-content-as-a-regulatory-record"></a><span data-ttu-id="f1816-110">規制レコードとしてコンテンツをマークするオプションを表示する方法</span><span class="sxs-lookup"><span data-stu-id="f1816-110">How to display the option to mark content as a regulatory record</span></span>

>[!NOTE] 
> <span data-ttu-id="f1816-111">次の手順は、監査ログの [[アイテム保持ポリシーと保持ラベルのアクティビティ](search-the-audit-log-in-security-and-compliance.md#retention-policy-and-retention-label-activities)] セクションの [**保持ラベルの規制レコード オプションを有効にする**] をログに記録する監査可能なアクションです。</span><span class="sxs-lookup"><span data-stu-id="f1816-111">The following procedure is an auditable action, logging **Enabled regulatory record option for retention labels** in the [Retention policy and retention label activities](search-the-audit-log-in-security-and-compliance.md#retention-policy-and-retention-label-activities) section of the audit log.</span></span>

<span data-ttu-id="f1816-112">既定では、コンテンツを規制レコードとしてマークするための保持ラベル オプションは、保持ラベル ウィザードには表示されません。</span><span class="sxs-lookup"><span data-stu-id="f1816-112">By default, the retention label option to mark content as a regulatory record isn't displayed in the retention label wizard.</span></span> <span data-ttu-id="f1816-113">このオプションを表示するには、まず PowerShell コマンドを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f1816-113">To display this option, you must first run a PowerShell command:</span></span>

1. <span data-ttu-id="f1816-114">[Office 365 セキュリティ センターとコンプライアンス センターの PowerShell への接続](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="f1816-114">[Connect to the Office 365 Security & Compliance Center Powershell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="f1816-115">次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="f1816-115">Run the following cmdlet:</span></span>
    
    ```powershell
    Set-RegulatoryComplianceUI -Enabled $true
    ````
    <span data-ttu-id="f1816-116">確認のためのメッセージが表示されることはなく、設定はすぐに有効になります。</span><span class="sxs-lookup"><span data-stu-id="f1816-116">There is no prompt to confirm and the setting takes effect immediately.</span></span>

<span data-ttu-id="f1816-117">保持ラベル ウィザードでのこのオプションの表示に関して気が変わった場合には、同じコマンドレットを **False** 値で実行することで、このオプションを再び非表示にすることができます: `Set-RegulatoryComplianceUI -Enabled $false` </span><span class="sxs-lookup"><span data-stu-id="f1816-117">If you change your mind about seeing this option in the retention label wizard, you can hide it again by running the same cmdlet with the **false** value: `Set-RegulatoryComplianceUI -Enabled $false`</span></span> 

## <a name="configuring-retention-labels-to-declare-records"></a><span data-ttu-id="f1816-118">保持ラベルを構成してレコードを宣言する</span><span class="sxs-lookup"><span data-stu-id="f1816-118">Configuring retention labels to declare records</span></span>

<span data-ttu-id="f1816-119">Microsoft 365 コンプライアンス センターの**レコード管理**ソリューションから保持ラベルを作成または編集する場合、アイテムをレコードとしてマークするオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="f1816-119">When you create or edit a retention label from the **Records Management** solution in the Microsoft 365 compliance center, you have the option to mark items as a record.</span></span> <span data-ttu-id="f1816-120">前のセクションで実行した PowerShell コマンドを実行した場合、代わりに規制レコードとしてアイテムをマークすることができます。</span><span class="sxs-lookup"><span data-stu-id="f1816-120">If you ran the PowerShell command from the previous section, you can alternatively mark items as a regulatory record.</span></span>

<span data-ttu-id="f1816-121">例:</span><span class="sxs-lookup"><span data-stu-id="f1816-121">For example:</span></span>

![保持ラベルを構成して、コンテンツをレコードまたは規制レコードとしてマークする](../media/recordversioning6.png)

<span data-ttu-id="f1816-123">この保持ラベルを使用することで、ラベルを必要に応じて SharePoint や OneDrive のドキュメントまたは Exchange のメールに適用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="f1816-123">Using this retention label, you can now apply it to SharePoint or OneDrive documents and Exchange emails, as needed.</span></span> 

<span data-ttu-id="f1816-124">詳細な手順については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f1816-124">For full instructions:</span></span>

- [<span data-ttu-id="f1816-125">アイテム保持ラベルを作成してアプリに適用する</span><span class="sxs-lookup"><span data-stu-id="f1816-125">Create retention labels and apply them in apps</span></span>](create-apply-retention-labels.md)

- <span data-ttu-id="f1816-126">[保持ラベルをコンテンツに自動的に適用する](apply-retention-labels-automatically.md) (規制レコードはサポート対象外です)</span><span class="sxs-lookup"><span data-stu-id="f1816-126">[Apply a retention label to content automatically](apply-retention-labels-automatically.md) (not supported for regulatory records)</span></span>


## <a name="applying-the-configured-retention-label-to-content"></a><span data-ttu-id="f1816-127">コンテンツに構成した保持ラベルを適用する</span><span class="sxs-lookup"><span data-stu-id="f1816-127">Applying the configured retention label to content</span></span>

<span data-ttu-id="f1816-128">アイテムをレコードや規制レコードとしてマークする保持ラベルをユーザーがアプリ内で適用できるようにする場合:</span><span class="sxs-lookup"><span data-stu-id="f1816-128">When retention labels that mark items as a record or regulatory record are made available for users to apply them in apps:</span></span>

- <span data-ttu-id="f1816-129">Exchange の場合、メールボックスへの書き込みアクセス権を持つすべてのユーザーは、これらのラベルを適用できます。</span><span class="sxs-lookup"><span data-stu-id="f1816-129">For Exchange, any user with write-access to the mailbox can apply these labels.</span></span> 
- <span data-ttu-id="f1816-130">SharePoint および OneDrive の場合、既定のメンバー グループ (投稿アクセス許可レベル) のすべてのユーザーがこれらのラベルを適用できます。</span><span class="sxs-lookup"><span data-stu-id="f1816-130">For SharePoint and OneDrive, any user in the default Members group (the Contribute permission level) can apply these labels.</span></span>

<span data-ttu-id="f1816-131">保持ラベルを使用してレコードとしてマークされたドキュメントの例は、以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f1816-131">Example of a document marked as record by using a retention label:</span></span>

![レコードとしてタグ付けされたドキュメントの詳細ウィンドウ](../media/recordversioning7.png)

## <a name="next-steps"></a><span data-ttu-id="f1816-133">次の手順</span><span class="sxs-lookup"><span data-stu-id="f1816-133">Next steps</span></span>

<span data-ttu-id="f1816-134">レコード管理でサポートされているシナリオの一覧については、「[レコード管理の一般的なシナリオ](get-started-with-records-management.md#common-scenarios-for-records-management)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f1816-134">For a list of scenarios supported by records management, see [Common scenarios for records management](get-started-with-records-management.md#common-scenarios-for-records-management).</span></span>
