---
title: EOP の機能アクセス許可
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 1/30/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 34674847-a6b7-4a7e-9eaa-b64f22bc150d
description: Microsoft Exchange Online Protection (EOP) を管理するタスクを実行するために必要なアクセス許可は、管理している機能に応じて異なります。
ms.openlocfilehash: dcf56a5295f7964b2271331deb2e7f8c1ba1635e
ms.sourcegitcommit: 2468bcb01625f97a322459814d81b9faad717859
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "39871853"
---
# <a name="feature-permissions-in-eop"></a><span data-ttu-id="068c4-103">EOP の機能アクセス許可</span><span class="sxs-lookup"><span data-stu-id="068c4-103">Feature permissions in EOP</span></span>

<span data-ttu-id="068c4-104">Exchange Online Protection (EOP) を管理するタスクを実行するために必要なアクセス許可は、管理している機能によって異なります。</span><span class="sxs-lookup"><span data-stu-id="068c4-104">The permissions required to perform tasks to manage Exchange Online Protection (EOP) vary depending on the feature you are managing.</span></span>

<span data-ttu-id="068c4-105">EOP をセットアップするには、Office 365 グローバル管理者、または Exchange 社内管理者 (Organization Management 役割グループ) であることが必要です。</span><span class="sxs-lookup"><span data-stu-id="068c4-105">To set up EOP, you must be an Office 365 Global Admin, or an Exchange Company Administrator (the Organization Management role group).</span></span>

## <a name="exchange-online-protection-permissions"></a><span data-ttu-id="068c4-106">Exchange Online Protection アクセス許可</span><span class="sxs-lookup"><span data-stu-id="068c4-106">Exchange Online Protection permissions</span></span>

<span data-ttu-id="068c4-p101">EOP 機能を管理するために必要なアクセス許可は、次の表で確認してください。機能が複数の役割グループを示している場合、その機能を使用する役割グループを 1 つだけが割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="068c4-p101">To find out what permissions you need to manage EOP features, see the following table. If a feature lists more than one role group, you only need to be assigned one of the role groups to use the feature.</span></span>

|<span data-ttu-id="068c4-109">**機能**</span><span class="sxs-lookup"><span data-stu-id="068c4-109">**Feature**</span></span>|<span data-ttu-id="068c4-110">**必要なアクセス許可**</span><span class="sxs-lookup"><span data-stu-id="068c4-110">**Permissions required**</span></span>|
|:-----|:-----|
|<span data-ttu-id="068c4-111">マルウェア対策</span><span class="sxs-lookup"><span data-stu-id="068c4-111">Anti-malware</span></span>|<span data-ttu-id="068c4-112">組織の管理</span><span class="sxs-lookup"><span data-stu-id="068c4-112">Organization Management</span></span> <br/><br/> <span data-ttu-id="068c4-113">検疫管理</span><span class="sxs-lookup"><span data-stu-id="068c4-113">Hygiene Management</span></span>|
|<span data-ttu-id="068c4-114">スパム対策</span><span class="sxs-lookup"><span data-stu-id="068c4-114">Anti-spam</span></span>|<span data-ttu-id="068c4-115">組織の管理</span><span class="sxs-lookup"><span data-stu-id="068c4-115">Organization Management</span></span> <br/><br/> <span data-ttu-id="068c4-116">検疫管理</span><span class="sxs-lookup"><span data-stu-id="068c4-116">Hygiene Management</span></span>|
|<span data-ttu-id="068c4-117">メール フロー ルール</span><span class="sxs-lookup"><span data-stu-id="068c4-117">Mail flow rules</span></span>|<span data-ttu-id="068c4-118">組織の管理</span><span class="sxs-lookup"><span data-stu-id="068c4-118">Organization Management</span></span> <br/><br/> <span data-ttu-id="068c4-119">レコード管理</span><span class="sxs-lookup"><span data-stu-id="068c4-119">Records Management</span></span>|
|<span data-ttu-id="068c4-120">ドメイン</span><span class="sxs-lookup"><span data-stu-id="068c4-120">Domains</span></span>|<span data-ttu-id="068c4-121">組織の管理</span><span class="sxs-lookup"><span data-stu-id="068c4-121">Organization Management</span></span> <br/><br/> <span data-ttu-id="068c4-122">表示専用組織の管理</span><span class="sxs-lookup"><span data-stu-id="068c4-122">View-Only Organization Management</span></span>|
|<span data-ttu-id="068c4-123">Advanced Threat Protection (ATP)</span><span class="sxs-lookup"><span data-stu-id="068c4-123">Advanced Threat Protection (ATP)</span></span>|<span data-ttu-id="068c4-124">組織の管理</span><span class="sxs-lookup"><span data-stu-id="068c4-124">Organization Management</span></span> <br/><br/> <span data-ttu-id="068c4-125">検疫管理</span><span class="sxs-lookup"><span data-stu-id="068c4-125">Hygiene Management</span></span>|
|<span data-ttu-id="068c4-126">Office 365 コネクタ</span><span class="sxs-lookup"><span data-stu-id="068c4-126">Office 365 connectors</span></span>|<span data-ttu-id="068c4-127">組織の管理</span><span class="sxs-lookup"><span data-stu-id="068c4-127">Organization Management</span></span>|
|<span data-ttu-id="068c4-128">メッセージ追跡</span><span class="sxs-lookup"><span data-stu-id="068c4-128">Message trace</span></span>|<span data-ttu-id="068c4-129">組織の管理</span><span class="sxs-lookup"><span data-stu-id="068c4-129">Organization Management</span></span> <br/><br/> <span data-ttu-id="068c4-130">表示専用組織の管理</span><span class="sxs-lookup"><span data-stu-id="068c4-130">View-Only Organization Management</span></span>|
|<span data-ttu-id="068c4-131">組織の構成</span><span class="sxs-lookup"><span data-stu-id="068c4-131">Organization configuration</span></span>|<span data-ttu-id="068c4-132">組織の管理</span><span class="sxs-lookup"><span data-stu-id="068c4-132">Organization Management</span></span>|
|<span data-ttu-id="068c4-133">Quarantine</span><span class="sxs-lookup"><span data-stu-id="068c4-133">Quarantine</span></span>|<span data-ttu-id="068c4-134">組織の管理</span><span class="sxs-lookup"><span data-stu-id="068c4-134">Organization Management</span></span> <br/><br/> <span data-ttu-id="068c4-135">表示専用組織の管理</span><span class="sxs-lookup"><span data-stu-id="068c4-135">View-Only Organization Management</span></span> <br/><br/> <span data-ttu-id="068c4-136">検疫管理</span><span class="sxs-lookup"><span data-stu-id="068c4-136">Hygiene Management</span></span>|
|<span data-ttu-id="068c4-137">ユーザー、連絡先、および役割グループ</span><span class="sxs-lookup"><span data-stu-id="068c4-137">Users, Contacts, and Role Groups</span></span>|<span data-ttu-id="068c4-138">組織の管理</span><span class="sxs-lookup"><span data-stu-id="068c4-138">Organization Management</span></span> <br/><br/> <span data-ttu-id="068c4-139">表示専用組織の管理</span><span class="sxs-lookup"><span data-stu-id="068c4-139">View-Only Organization Management</span></span> <br/><br/> <span data-ttu-id="068c4-140">検疫管理</span><span class="sxs-lookup"><span data-stu-id="068c4-140">Hygiene Management</span></span>|
|<span data-ttu-id="068c4-141">配布グループとセキュリティ グループ</span><span class="sxs-lookup"><span data-stu-id="068c4-141">Distribution Groups and Security Groups</span></span>|<span data-ttu-id="068c4-142">組織の管理</span><span class="sxs-lookup"><span data-stu-id="068c4-142">Organization Management</span></span> <br/><br/> <span data-ttu-id="068c4-143">表示専用組織の管理</span><span class="sxs-lookup"><span data-stu-id="068c4-143">View-Only Organization Management</span></span> <br/><br/> <span data-ttu-id="068c4-144">検疫管理</span><span class="sxs-lookup"><span data-stu-id="068c4-144">Hygiene Management</span></span>|
|<span data-ttu-id="068c4-145">レポートの表示</span><span class="sxs-lookup"><span data-stu-id="068c4-145">View reports</span></span>|<span data-ttu-id="068c4-146">組織の管理: メール保護レポートへのアクセス。</span><span class="sxs-lookup"><span data-stu-id="068c4-146">Organization Management: Access to mail protection reports.</span></span> <br/><br/> <span data-ttu-id="068c4-147">表示専用受信者: メール保護レポートへのアクセス。</span><span class="sxs-lookup"><span data-stu-id="068c4-147">View-Only Recipients: Access to mail protection reports.</span></span>  <br/><br/> <span data-ttu-id="068c4-148">コンプライアンス管理: メール保護レポートおよびデータ損失防止 (DLP) レポートへのアクセス (サブスクリプションに DLP 機能が含まれている場合)。</span><span class="sxs-lookup"><span data-stu-id="068c4-148">Compliance Management: Access to mail protection reports and Data Loss Prevention (DLP) reports (if your subscription has DLP capabilities).</span></span>|
