---
title: 電子情報開示での復号化
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Microsoft 365 eDiscovery ツールが電子メールメッセージに添付された暗号化ドキュメントを処理する方法について説明します。
ms.openlocfilehash: 91d5689bfb64d272c896c0e92422ce1f45fd5f72
ms.sourcegitcommit: 89f56c3e0b619a4700a75a21927d9ffc90658632
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/10/2020
ms.locfileid: "48984901"
---
# <a name="decryption-in-microsoft-365-ediscovery-tools"></a><span data-ttu-id="09d3a-103">Microsoft 365 電子情報開示ツールの復号化</span><span class="sxs-lookup"><span data-stu-id="09d3a-103">Decryption in Microsoft 365 eDiscovery tools</span></span>

<span data-ttu-id="09d3a-104">暗号化は、ファイル保護と情報保護戦略の重要な部分です。</span><span class="sxs-lookup"><span data-stu-id="09d3a-104">Encryption is an important part of your file protection and information protection strategy.</span></span> <span data-ttu-id="09d3a-105">すべての種類の組織は暗号化テクノロジを使用して、組織内の機密コンテンツを保護し、適切な人物だけがそのコンテンツにアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="09d3a-105">Organizations of all types use encryption technology to protect sensitive content within their organization and ensure that only the right people have access to that content.</span></span>

<span data-ttu-id="09d3a-106">暗号化されたコンテンツに対して一般的な電子情報開示タスクを実行するには、コンテンツ検索、コア電子情報開示ケース、および高度な電子情報開示ケースからエクスポートされたときに電子メールメッセージのコンテンツを解読するために電子情報開示マネージャーが必要でした。</span><span class="sxs-lookup"><span data-stu-id="09d3a-106">To execute common eDiscovery tasks on encrypted content, eDiscovery managers were required to decrypt email message content as it was exported from content searches, Core eDiscovery cases, and Advanced eDiscovery cases.</span></span> <span data-ttu-id="09d3a-107">Microsoft 暗号化テクノロジを使用して暗号化されたコンテンツは、エクスポートされるまで確認できませんでした。</span><span class="sxs-lookup"><span data-stu-id="09d3a-107">Content encrypted with Microsoft encryption technologies was not available for review until after it was exported.</span></span>

<span data-ttu-id="09d3a-108">電子情報開示ワークフローで暗号化されたコンテンツを管理しやすくするために、Microsoft 365 の電子情報開示ツールでは、電子メールメッセージに添付され、Exchange Online で送信される暗号化ファイルの復号化が組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="09d3a-108">To make it easier to manage encrypted content in the eDiscovery workflow, Microsoft 365 eDiscovery tools now incorporate decryption of encrypted files that are attached to email messages and sent in Exchange Online.</span></span> <span data-ttu-id="09d3a-109">この新しい機能の前に、rights management (および添付ファイルではない) で保護された電子メールメッセージのコンテンツのみが復号化されました。</span><span class="sxs-lookup"><span data-stu-id="09d3a-109">Prior to this new capability, only the content of an email message protected by rights management (and not attached files) were decrypted.</span></span> <span data-ttu-id="09d3a-110">これで、Microsoft 暗号化テクノロジを使用して暗号化されたファイルが検索条件に一致する電子メールメッセージに添付されている場合、その暗号化ファイルは、検索結果が確認のために準備されるときに復号化されます。</span><span class="sxs-lookup"><span data-stu-id="09d3a-110">Now, if a file that's encrypted with a Microsoft encryption technology is attached to an email message that matches the search criteria, the encrypted file will be decrypted when the search results are prepared for review.</span></span> <span data-ttu-id="09d3a-111">これにより、電子情報開示マネージャーは、検索結果をプレビューするときに暗号化された電子メール添付ファイルの内容を表示し、それらの添付ファイルを詳細な電子情報開示のレビューセットに追加した後に確認できます。</span><span class="sxs-lookup"><span data-stu-id="09d3a-111">This allows eDiscovery managers to view the content of encrypted email attachments when previewing search results, and review them once they have been added to a review set in Advanced eDiscovery.</span></span>

> [!NOTE]
> <span data-ttu-id="09d3a-112">近日中に Microsoft 365 電子情報開示ツールは、SharePoint Online と OneDrive for Business に保存されている暗号化されたドキュメントをサポートします。</span><span class="sxs-lookup"><span data-stu-id="09d3a-112">Starting soon, Microsoft 365 eDiscovery tools will support encrypted documents stored in SharePoint Online and OneDrive for Business.</span></span> <span data-ttu-id="09d3a-113">これには、適用される機密ラベルの結果として暗号化されたドキュメントが含まれます。</span><span class="sxs-lookup"><span data-stu-id="09d3a-113">This will include documents that are encrypted as a result of sensitivity labels applied to them.</span></span>

## <a name="supported-encryption-technologies"></a><span data-ttu-id="09d3a-114">サポートされる暗号化テクノロジ</span><span class="sxs-lookup"><span data-stu-id="09d3a-114">Supported encryption technologies</span></span>

<span data-ttu-id="09d3a-115">Microsoft の電子情報開示ツールは、Microsoft 暗号化テクノロジで暗号化されたアイテムをサポートします。</span><span class="sxs-lookup"><span data-stu-id="09d3a-115">Microsoft eDiscovery tools support items encrypted with Microsoft encryption technologies.</span></span> <span data-ttu-id="09d3a-116">これらのテクノロジには、Office メッセージの暗号化と Azure Rights Management があります。</span><span class="sxs-lookup"><span data-stu-id="09d3a-116">These technologies include Office Message Encryption and Azure Rights Management.</span></span> <span data-ttu-id="09d3a-117">Microsoft 暗号化テクノロジの詳細については、「 [暗号化](encryption.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="09d3a-117">For more information about Microsoft encryption technologies, see [Encryption](encryption.md).</span></span> <span data-ttu-id="09d3a-118">サードパーティの暗号化テクノロジによって暗号化されたコンテンツはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="09d3a-118">Content encrypted by third-party encryption technologies isn't supported.</span></span> <span data-ttu-id="09d3a-119">これには、Microsoft 以外のテクノロジで暗号化されたコンテンツをプレビューまたはエクスポートするときのサポートはありません。</span><span class="sxs-lookup"><span data-stu-id="09d3a-119">This includes no support when previewing or exporting content encrypted with non-Microsoft technologies.</span></span>

## <a name="ediscovery-activities-that-support-encrypted-items"></a><span data-ttu-id="09d3a-120">暗号化されたアイテムをサポートする電子情報開示アクティビティ</span><span class="sxs-lookup"><span data-stu-id="09d3a-120">eDiscovery activities that support encrypted items</span></span>

<span data-ttu-id="09d3a-121">次の表は、電子メール massages に添付された暗号化ファイルの暗号化をサポートする、Microsoft 365 電子情報開示ツールで実行されるタスクを示しています。</span><span class="sxs-lookup"><span data-stu-id="09d3a-121">The following table identifies the tasks performed in Microsoft 365 eDiscovery tools that support decryption of encrypted files attached to email massages.</span></span> <span data-ttu-id="09d3a-122">サポートタスクは、検索条件に一致する電子メールメッセージに添付された暗号化ファイルに対して実行できます。</span><span class="sxs-lookup"><span data-stu-id="09d3a-122">The support tasks can be performed on an encrypted file that's attached to an email message that matches the criteria of a search.</span></span> <span data-ttu-id="09d3a-123">値 "N/A" は、対応する電子情報開示ツールでは機能が使用できないことを示します。</span><span class="sxs-lookup"><span data-stu-id="09d3a-123">A value of "N/A" indicates that the function isn't available in the corresponding eDiscovery tool.</span></span>

|<span data-ttu-id="09d3a-124">電子情報開示タスク</span><span class="sxs-lookup"><span data-stu-id="09d3a-124">eDiscovery task</span></span>  |<span data-ttu-id="09d3a-125">コンテンツ検索</span><span class="sxs-lookup"><span data-stu-id="09d3a-125">Content search</span></span>  |<span data-ttu-id="09d3a-126">コア電子情報開示</span><span class="sxs-lookup"><span data-stu-id="09d3a-126">Core eDiscovery</span></span>  |<span data-ttu-id="09d3a-127">Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="09d3a-127">Advanced eDiscovery</span></span>  |
|:---------|:---------|:---------|:---------|
|<span data-ttu-id="09d3a-128">暗号化されたファイル内のコンテンツを検索する</span><span class="sxs-lookup"><span data-stu-id="09d3a-128">Search for content in encrypted files</span></span>     |<span data-ttu-id="09d3a-129">必要</span><span class="sxs-lookup"><span data-stu-id="09d3a-129">Yes</span></span>      |<span data-ttu-id="09d3a-130">必要</span><span class="sxs-lookup"><span data-stu-id="09d3a-130">Yes</span></span>      |<span data-ttu-id="09d3a-131">必要</span><span class="sxs-lookup"><span data-stu-id="09d3a-131">Yes</span></span>      |
|<span data-ttu-id="09d3a-132">暗号化されたファイルのプレビュー</span><span class="sxs-lookup"><span data-stu-id="09d3a-132">Preview encrypted files</span></span>     |<span data-ttu-id="09d3a-133">必要</span><span class="sxs-lookup"><span data-stu-id="09d3a-133">Yes</span></span>      |<span data-ttu-id="09d3a-134">必要</span><span class="sxs-lookup"><span data-stu-id="09d3a-134">Yes</span></span>     |<span data-ttu-id="09d3a-135">必要</span><span class="sxs-lookup"><span data-stu-id="09d3a-135">Yes</span></span>       |
|<span data-ttu-id="09d3a-136">検証セット内の暗号化ファイルを確認する</span><span class="sxs-lookup"><span data-stu-id="09d3a-136">Review encrypted files in a review set</span></span>    |<span data-ttu-id="09d3a-137">N/A</span><span class="sxs-lookup"><span data-stu-id="09d3a-137">N/A</span></span>      |<span data-ttu-id="09d3a-138">N/A</span><span class="sxs-lookup"><span data-stu-id="09d3a-138">N/A</span></span>        | <span data-ttu-id="09d3a-139">はい</span><span class="sxs-lookup"><span data-stu-id="09d3a-139">Yes</span></span>        |
|<span data-ttu-id="09d3a-140">暗号化されたファイルをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="09d3a-140">Export encrypted files</span></span>    |<span data-ttu-id="09d3a-141">必要</span><span class="sxs-lookup"><span data-stu-id="09d3a-141">Yes</span></span>       |<span data-ttu-id="09d3a-142">必要</span><span class="sxs-lookup"><span data-stu-id="09d3a-142">Yes</span></span>  |<span data-ttu-id="09d3a-143">必要</span><span class="sxs-lookup"><span data-stu-id="09d3a-143">Yes</span></span>    |

## <a name="requirements-for-decryption-in-ediscovery"></a><span data-ttu-id="09d3a-144">電子情報開示での復号化の要件</span><span class="sxs-lookup"><span data-stu-id="09d3a-144">Requirements for decryption in eDiscovery</span></span>

<span data-ttu-id="09d3a-145">Microsoft 暗号化テクノロジで暗号化された添付ファイルをプレビュー、確認、エクスポートするには、RMS の暗号化解除の役割を割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="09d3a-145">You have to be assigned the RMS Decrypt role to preview, review, and export attached files encrypted with Microsoft encryption technologies.</span></span> <span data-ttu-id="09d3a-146">また、Advanced 電子情報開示のレビューセットに追加された暗号化電子メール添付ファイルを確認してクエリを実行するには、この役割を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="09d3a-146">You also have to be assigned this role to review and query encrypted email attachments that are added to a review set in Advanced eDiscovery.</span></span>

<span data-ttu-id="09d3a-147">この役割は、既定では、Office 365 セキュリティ & コンプライアンスセンターの電子情報開示マネージャーの役割グループに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="09d3a-147">This role is assigned by default to the eDiscovery Manager role group in the Office 365 Security & Compliance Center.</span></span> <span data-ttu-id="09d3a-148">RMS の暗号化解除の役割の詳細については、「 [電子情報開示のアクセス許可を割り当てる](assign-ediscovery-permissions.md#rms-decrypt)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="09d3a-148">For more information about the RMS Decrypt role, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md#rms-decrypt).</span></span>
