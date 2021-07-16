---
title: Microsoft 365 の検索でのテナントの分離
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: この記事では、テナントの分離がテナント データを分離する方法について説明します。Microsoft 365します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3416afdeceaa7000b516ec89b4a2a1e59d8708d0
ms.sourcegitcommit: 27addd4dac07926528b788215d2dcd0e46301eb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/16/2021
ms.locfileid: "53464086"
---
# <a name="tenant-isolation-in-microsoft-365-search"></a><span data-ttu-id="79589-103">Microsoft 365 の検索でのテナントの分離</span><span class="sxs-lookup"><span data-stu-id="79589-103">Tenant Isolation in Microsoft 365 Search</span></span>

<span data-ttu-id="79589-104">SharePointオンライン検索では、共有データ構造の効率とテナント間の情報漏洩に対する保護のバランスを取るテナント分離モデルを使用します。</span><span class="sxs-lookup"><span data-stu-id="79589-104">SharePoint Online search uses a tenant separation model that balances the efficiency of shared data structures with protection against information leaking between tenants.</span></span> <span data-ttu-id="79589-105">このモデルでは、検索機能が次の機能から回避されます。</span><span class="sxs-lookup"><span data-stu-id="79589-105">With this model, we prevent the Search features from:</span></span>

- <span data-ttu-id="79589-106">他のテナントのドキュメントを含むクエリ結果を返す</span><span class="sxs-lookup"><span data-stu-id="79589-106">Returning query results that contain documents from other tenants</span></span>
- <span data-ttu-id="79589-107">熟練したユーザーが他のテナントに関する情報を受け取る可能性があるクエリ結果に十分な情報を公開する</span><span class="sxs-lookup"><span data-stu-id="79589-107">Exposing sufficient information in query results that a skilled user could infer information about other tenants</span></span>
- <span data-ttu-id="79589-108">別のテナントからのスキーマまたは設定の表示</span><span class="sxs-lookup"><span data-stu-id="79589-108">Showing schema or settings from another tenant</span></span>
- <span data-ttu-id="79589-109">テナント間での分析処理情報の混在や、テナント間のストアの結果の間違い</span><span class="sxs-lookup"><span data-stu-id="79589-109">Mixing analytics processing information between tenants or store results in the wrong tenant</span></span>
- <span data-ttu-id="79589-110">別のテナントからの辞書エントリの使用</span><span class="sxs-lookup"><span data-stu-id="79589-110">Using dictionary entries from another tenant</span></span>

<span data-ttu-id="79589-111">テナント データの種類ごとに、コード内で 1 つ以上の保護層を使用して、情報の偶発的な漏洩を防止します。</span><span class="sxs-lookup"><span data-stu-id="79589-111">For each type of tenant data, we use one or more layers of protection in the code to prevent accidental leaking of information.</span></span> <span data-ttu-id="79589-112">最も重要なデータは、単一の欠陥が実際の情報漏洩や知覚情報漏洩を生じさせるのを防ぐ保護の層が最も多い。</span><span class="sxs-lookup"><span data-stu-id="79589-112">The most critical data has the most layers of protection to make sure that a single defect doesn't result in actual or perceived information leakage.</span></span>

## <a name="tenant-separation-for-the-search-index"></a><span data-ttu-id="79589-113">検索インデックスのテナントの分離</span><span class="sxs-lookup"><span data-stu-id="79589-113">Tenant Separation for the Search Index</span></span>

<span data-ttu-id="79589-114">検索インデックスは、インデックス コンポーネントをホストするサーバーのディスクに格納され、テナントはインデックス ファイルを共有します。</span><span class="sxs-lookup"><span data-stu-id="79589-114">The search index is stored on disk in the servers hosting the index components and the tenants share the index files.</span></span> <span data-ttu-id="79589-115">テナントのインデックス付きドキュメントは、そのテナントのクエリにのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="79589-115">A tenant's indexed documents are visible only for queries for that tenant.</span></span> <span data-ttu-id="79589-116">3 つの独立したメカニズムが情報漏洩を防止します。</span><span class="sxs-lookup"><span data-stu-id="79589-116">Three independent mechanisms prevent information leakage:</span></span>

- <span data-ttu-id="79589-117">テナント ID のフィルター処理</span><span class="sxs-lookup"><span data-stu-id="79589-117">Tenant ID filtering</span></span>
- <span data-ttu-id="79589-118">テナント ID 用語のプレフィックス</span><span class="sxs-lookup"><span data-stu-id="79589-118">Tenant ID term prefixing</span></span>
- <span data-ttu-id="79589-119">ACL チェック</span><span class="sxs-lookup"><span data-stu-id="79589-119">ACL checks</span></span>

<span data-ttu-id="79589-120">3 つのメカニズムはすべて、Search が間違ったテナントにドキュメントを返すのに失敗する必要があります。</span><span class="sxs-lookup"><span data-stu-id="79589-120">All three mechanisms would have to fail for Search to return documents to the wrong tenant.</span></span>

## <a name="tenant-id-filtering-and-tenant-id-term-prefixing"></a><span data-ttu-id="79589-121">テナント ID フィルターとテナント ID 用語プレフィックス</span><span class="sxs-lookup"><span data-stu-id="79589-121">Tenant ID Filtering and Tenant ID Term Prefixing</span></span>

<span data-ttu-id="79589-122">検索では、フルテキスト インデックスにインデックスが付くすべての用語にテナント ID が付くプレフィックスが付けされます。</span><span class="sxs-lookup"><span data-stu-id="79589-122">Search prefixes every term that is indexed in the full-text index with the tenant ID.</span></span> <span data-ttu-id="79589-123">たとえば *、"foo"* という用語が *"123"* の ID を持つテナントに対してインデックスが作成されている場合、フルテキスト インデックスのエントリは *"123foo" になります*。</span><span class="sxs-lookup"><span data-stu-id="79589-123">For example, when the term "*foo*" is indexed for a tenant with an ID of "*123*", the entry in the full-text index is "*123foo.*"</span></span>

<span data-ttu-id="79589-124">すべてのクエリは、テナント ID フィルターと呼ばれるプロセスを使用してテナント ID を含めるに変換されます。</span><span class="sxs-lookup"><span data-stu-id="79589-124">Every query is converted to include the tenant ID using a process called tenant ID filtering.</span></span> <span data-ttu-id="79589-125">たとえば、クエリ *"foo"* は "<*guid*>。*foo* AND *tenantID*:<*guid*>"。ここで、<*guid*>クエリを実行するテナントを表します。</span><span class="sxs-lookup"><span data-stu-id="79589-125">For example, the query "*foo*" is converted to "<*guid*>.*foo* AND *tenantID*:<*guid*>", where <*guid*> represents the tenant performing the query.</span></span> <span data-ttu-id="79589-126">このクエリ変換は各インデックス ノード内で行われますが、クエリもコンテンツ処理も影響しません。</span><span class="sxs-lookup"><span data-stu-id="79589-126">This query conversion occurs within each index node and neither query nor content processing can influence it.</span></span> <span data-ttu-id="79589-127">テナント ID がすべてのクエリに追加されるので、他のテナントの用語の頻度は、1 つのテナントで最適な一致ランクを見て推測することはできません。</span><span class="sxs-lookup"><span data-stu-id="79589-127">Because the tenant ID is added to every query, the frequency of a term in other tenants can't be inferred by looking at best match ranking in one tenant.</span></span>

<span data-ttu-id="79589-128">テナント ID の用語プレフィックスは、フルテキスト インデックスでのみ発生します。</span><span class="sxs-lookup"><span data-stu-id="79589-128">Tenant ID term prefixing occurs only in the full-text index.</span></span> <span data-ttu-id="79589-129">フィールド検索 *("title:foo"* など) は、用語の先頭にテナント ID が付かない合成検索インデックスに移動します。</span><span class="sxs-lookup"><span data-stu-id="79589-129">Fielded searches, such as "*title:foo*", go to a synthetic search index where terms aren't prefixed by tenant ID.</span></span> <span data-ttu-id="79589-130">代わりに、フィールド検索の先頭にフィールド名が付きます。</span><span class="sxs-lookup"><span data-stu-id="79589-130">Instead, fielded searches are prefixed with the field name.</span></span> <span data-ttu-id="79589-131">たとえば、クエリ "*title:foo*" は "*fields.title:foo AND fields.tenantID*:<*guid*>" に変換されます。</span><span class="sxs-lookup"><span data-stu-id="79589-131">For example, the query "*title:foo*" is converted to "*fields.title:foo AND fields.tenantID*:<*guid*>."</span></span> <span data-ttu-id="79589-132">用語の頻度は合成検索インデックスのヒット数のランク付けには影響しないので、用語のプレフィックスによってテナントを分離する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="79589-132">Because the frequency of a term doesn't influence ranking of hits in the synthetic search index, there's no need for tenant separation by term prefixing.</span></span> <span data-ttu-id="79589-133">*"title:foo"* のようなフィールド検索の場合、テナントコンテンツの分離は、クエリ変換によるテナント ID フィルタリングによって異なります。</span><span class="sxs-lookup"><span data-stu-id="79589-133">For a fielded search like "*title:foo*", tenant content separation depends on tenant ID filtering by query conversion.</span></span>

## <a name="document-access-control-list-checks"></a><span data-ttu-id="79589-134">ドキュメント アクセス制御リストのチェック</span><span class="sxs-lookup"><span data-stu-id="79589-134">Document Access Control List Checks</span></span>

<span data-ttu-id="79589-135">検索は、検索インデックスに保存される ACL を介してドキュメントへのアクセスを制御します。</span><span class="sxs-lookup"><span data-stu-id="79589-135">Search controls access to documents through ACLs that are saved in the search index.</span></span> <span data-ttu-id="79589-136">すべてのアイテムは、特別な ACL フィールド内の用語のセットでインデックスが作成されます。</span><span class="sxs-lookup"><span data-stu-id="79589-136">Every item is indexed with a set of terms in a special ACL field.</span></span> <span data-ttu-id="79589-137">ACL フィールドには、ドキュメントを表示できるグループまたはユーザーごとに 1 つの用語が含まれる。</span><span class="sxs-lookup"><span data-stu-id="79589-137">The ACL field contains one term per group or user that can view the document.</span></span> <span data-ttu-id="79589-138">すべてのクエリは、認証されたユーザーが属するグループごとに 1 つのアクセス制御エントリ (ACE) 用語の一覧で拡張されます。</span><span class="sxs-lookup"><span data-stu-id="79589-138">Every query is augmented with a list of access control entry (ACE) terms, one for each group to which the authenticated user belongs.</span></span>

<span data-ttu-id="79589-139">たとえば、"<*guid"*>。*foo AND tenantID*:<*guid*>" は次<*guid*>。*foo AND tenantID*:<*guid* >  *AND* (*docACL:* < *ace1* >  *OR docACL*:<*ace2* >  *OR docACL*:<*ace3* >  *..*)"</span><span class="sxs-lookup"><span data-stu-id="79589-139">For example, a query like "<*guid*>.*foo AND tenantID*:<*guid*>" becomes: "<*guid*>.*foo AND tenantID*:<*guid*> *AND* (*docACL:*<*ace1*> *OR docACL*:<*ace2*> *OR docACL*:<*ace3*> *...*)"</span></span>

<span data-ttu-id="79589-140">ユーザーとグループの識別子とそれ以降の ACL は一意であるため、一部のユーザーにのみ表示されるドキュメントのテナント間のセキュリティレベルが強化されます。</span><span class="sxs-lookup"><span data-stu-id="79589-140">Because user and group identifiers and hence ACEs are unique, this provides an extra level of security between tenants for documents that are only visible to some users.</span></span> <span data-ttu-id="79589-141">テナント内の通常のユーザーにアクセスを許可する特別な "外部ユーザーを除くすべてのユーザー" ACE も同様です。</span><span class="sxs-lookup"><span data-stu-id="79589-141">The same is the case for the special "Everyone except external users" ACE that grants access to regular users in the tenant.</span></span> <span data-ttu-id="79589-142">ただし、"Everyone" の ACEs は、すべてのテナントで同じので、パブリック ドキュメントのテナント分離はテナント ID フィルターによって異なります。</span><span class="sxs-lookup"><span data-stu-id="79589-142">But since ACEs for "Everyone" are the same for all tenants, tenant separation for public documents depends on tenant ID filtering.</span></span> <span data-ttu-id="79589-143">拒否の ACL もサポートされています。</span><span class="sxs-lookup"><span data-stu-id="79589-143">Deny ACEs are also supported.</span></span> <span data-ttu-id="79589-144">クエリ拡張では、拒否 ACE との一致がある場合に結果からドキュメントを削除する句を追加します。</span><span class="sxs-lookup"><span data-stu-id="79589-144">The query augmentation adds a clause that removes a document from the result when there is a match with a deny ACE.</span></span>

<span data-ttu-id="79589-145">検索Exchange Online、インデックスは、オンラインの場合と同様に、テナント ID (サブスクリプション ID) ではなく、個々のユーザーのメールボックスのメールボックス ID にSharePointされます。</span><span class="sxs-lookup"><span data-stu-id="79589-145">In Exchange Online search, the index is partitioned on mailbox ID for individual user's mailboxes instead of tenant ID (subscription ID) as in SharePoint Online.</span></span> <span data-ttu-id="79589-146">パーティショニングメカニズムは、SharePointと同じですが、ACL フィルターはありません。</span><span class="sxs-lookup"><span data-stu-id="79589-146">The partitioning mechanism is the same as SharePoint Online, but there is no ACL filtering.</span></span>
