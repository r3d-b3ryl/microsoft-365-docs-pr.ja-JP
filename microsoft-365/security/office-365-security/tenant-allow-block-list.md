---
title: テナント許可/ブロック一覧で許可される URL とブロックされる URL を管理する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 管理者は、セキュリティ コンプライアンス センターのテナントの許可/ブロック リストの URL エントリを構成する方法&できます。
ms.openlocfilehash: 888a96f23daf2cf47847466ad4080f310be7f9b4
ms.sourcegitcommit: 260bbb93bbda62db9e88c021ccccfa75ac39a32e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2020
ms.locfileid: "46845944"
---
# <a name="manage-urls-in-the-tenant-allowblock-list"></a><span data-ttu-id="67604-103">テナントの許可/禁止リストの URL を管理する</span><span class="sxs-lookup"><span data-stu-id="67604-103">Manage URLs in the Tenant Allow/Block List</span></span>

> [!NOTE]
> <span data-ttu-id="67604-104">このトピックで説明する機能はプレビュー段階であり、変更される可能性があります。すべての組織で利用できるものもあります。</span><span class="sxs-lookup"><span data-stu-id="67604-104">The features described in this topic are in Preview, are subject to change, and are not available in all organizations.</span></span>

<span data-ttu-id="67604-105">Exchange Online にメールボックスがある Microsoft 365 組織や、Exchange Online メールボックスを使用しないスタンドアロン Exchange Online Protection (EOP) 組織では、EOP フィルター処理について同意する場合があります。</span><span class="sxs-lookup"><span data-stu-id="67604-105">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="67604-106">たとえば、優れたメッセージが悪か (誤検知) としてマークされている、または無効なメッセージが許可されている (検知漏れ) などです。</span><span class="sxs-lookup"><span data-stu-id="67604-106">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="67604-107">セキュリティ センターのテナント許可/ブロック リストには、&のフィルター操作について手動でオーバーライドする方法が用いました。</span><span class="sxs-lookup"><span data-stu-id="67604-107">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="67604-108">テナント許可/禁止一覧は、メール フロー時と、ユーザーがクリックした時に使用されます。</span><span class="sxs-lookup"><span data-stu-id="67604-108">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="67604-109">テナントの許可/ブロックリストで、許可またはブロックする URL を指定できます。</span><span class="sxs-lookup"><span data-stu-id="67604-109">You can specify URLs to allow or block in the Tenant Allow/Block List.</span></span>

<span data-ttu-id="67604-110">このトピックでは、セキュリティ &/コンプライアンス センターまたは PowerShell (Exchange Online のメールボックスを使用する Microsoft 365 組織の場合は Exchange Online PowerShell、Exchange Online メールボックスを持つ組織の場合はスタンドアロン EOP PowerShell) のエントリの構成方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="67604-110">This topic describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="67604-111">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="67604-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="67604-112"><https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="67604-112">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="67604-113">テナント許可/ブロック リスト **ページに直接移動するには、** 次のコマンドを使用します <https://protection.office.com/tenantAllowBlockList> 。</span><span class="sxs-lookup"><span data-stu-id="67604-113">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="67604-114">使用できる URL 値については、このトピックの [後半にある「テナントの許可/ブロックリスト」の](#url-syntax-for-the-tenant-allowblock-list) URL 構文で説明します。</span><span class="sxs-lookup"><span data-stu-id="67604-114">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this topic.</span></span>

- <span data-ttu-id="67604-115">テナント許可/ブロック リストでは、URL のエントリ数を最大で 500 個に設定できます。</span><span class="sxs-lookup"><span data-stu-id="67604-115">The Tenant Allow/Block List allows a maximum of 500 entries for URLs.</span></span>

- <span data-ttu-id="67604-116">エントリは 15 分以内にアクティブである必要があります。</span><span class="sxs-lookup"><span data-stu-id="67604-116">An entry should be active within 15 minutes.</span></span>

- <span data-ttu-id="67604-117">ブロック エントリは、許可エントリより優先されます。</span><span class="sxs-lookup"><span data-stu-id="67604-117">Block entries take precedence over allow entries.</span></span>

- <span data-ttu-id="67604-118">既定では、テナント許可/禁止一覧のエントリは 30 日後に期限切れになります。</span><span class="sxs-lookup"><span data-stu-id="67604-118">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="67604-119">日付を指定したり、期限を切れないように設定したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="67604-119">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="67604-120">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="67604-120">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="67604-121">スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="67604-121">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="67604-122">このトピックの手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="67604-122">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="67604-123">テナント許可/禁止一覧に対して値を追加および削除するには、次の役割グループのいずれかのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="67604-123">To add and remove values from the Tenant Allow/Block List, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="67604-124">**組織の管理**または[セキュリティ/コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)の**セキュリティ管理者**。</span><span class="sxs-lookup"><span data-stu-id="67604-124">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="67604-125">**組織の管理**または [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) の**検疫管理**。</span><span class="sxs-lookup"><span data-stu-id="67604-125">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="67604-126">テナントの許可/禁止一覧に対する読み取り専用アクセス権を持つには、次の役割グループのいずれかのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="67604-126">For read-only access to the Tenant Allow/Block List, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="67604-127">[セキュリティ/コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)の**セキュリティ閲覧者**。</span><span class="sxs-lookup"><span data-stu-id="67604-127">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="67604-128">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) の**表示限定の組織管理**。</span><span class="sxs-lookup"><span data-stu-id="67604-128">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="67604-129">セキュリティ/コンプライアンス &使用して、テナント許可/ブロック リスト内に URL エントリを作成する</span><span class="sxs-lookup"><span data-stu-id="67604-129">Use the Security & Compliance Center to create URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="67604-130">URL エントリの構文の詳細については、このトピックで後述 [する「テナントの許可/ブロックリスト」の](#url-syntax-for-the-tenant-allowblock-list) URL 構文を参照してください。</span><span class="sxs-lookup"><span data-stu-id="67604-130">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this topic.</span></span>

1. <span data-ttu-id="67604-131">コンプライアンス センター内&で、[脅威管理ポリシー **のテナント** \> **の許可/** \> **ブロック リスト] に移動します**。</span><span class="sxs-lookup"><span data-stu-id="67604-131">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="67604-132">[テナント許可 **/ブロック一覧] ページ** で、[URL] タブが **選択** されたことを確認し、[追加] をクリック **します。**</span><span class="sxs-lookup"><span data-stu-id="67604-132">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Add**</span></span>

3. <span data-ttu-id="67604-133">表示される **新しい URL の** 追加ポップアップで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="67604-133">In the **Add new URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="67604-134">**ワイルドカードを使用して URL を追加します**。1 行に 1 つの URL を入力し、最大 20 の URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="67604-134">**Add URLs with wildcards**: Enter one URL per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="67604-135">**[Block/Allow]:** 指定した URL を**許可するか\*\*\*\*ブロック**するかを選択します。</span><span class="sxs-lookup"><span data-stu-id="67604-135">**Block/Allow**: Select whether you want to **Allow** or **Block** the specified URLs.</span></span>

   - <span data-ttu-id="67604-136">**無期限 :** 次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="67604-136">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="67604-137">設定がオフになっていること (オフに ![ 切り替 ](../../media/scc-toggle-off.png) え) を確認 **し、Expires ボックスを使用** してエントリの有効期限を指定します。</span><span class="sxs-lookup"><span data-stu-id="67604-137">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="67604-138">または</span><span class="sxs-lookup"><span data-stu-id="67604-138">or</span></span>

     - <span data-ttu-id="67604-139">エントリを有効期限切れにしないように設定するには、右に切り替えを移動します。</span><span class="sxs-lookup"><span data-stu-id="67604-139">Move the toggle to the right to configure the entries to never expire:</span></span> ![オンに切り替え](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="67604-141">.</span><span class="sxs-lookup"><span data-stu-id="67604-141">.</span></span>

   - <span data-ttu-id="67604-142">**オプション メモ**: エントリの説明テキストを入力します。</span><span class="sxs-lookup"><span data-stu-id="67604-142">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="67604-143">完了したら、[追加] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="67604-143">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="67604-144">セキュリティ/コンプライアンス センター&を使用して、テナントの許可/ブロック リストのエントリを表示する</span><span class="sxs-lookup"><span data-stu-id="67604-144">Use the Security & Compliance Center to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="67604-145">コンプライアンス センター内&で、[脅威管理ポリシー **のテナント** \> **の許可/** \> **ブロック リスト] に移動します**。</span><span class="sxs-lookup"><span data-stu-id="67604-145">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="67604-146">**[URL] タブを選**びます。</span><span class="sxs-lookup"><span data-stu-id="67604-146">Select the **URLs** tab.</span></span>

<span data-ttu-id="67604-147">次の列見出しをクリックすると、昇順または昇順で並べ替えられます。</span><span class="sxs-lookup"><span data-stu-id="67604-147">Click on the following column headings to sort in ascending or descending order:</span></span>

- <span data-ttu-id="67604-148">**値**</span><span class="sxs-lookup"><span data-stu-id="67604-148">**Value**</span></span>
- <span data-ttu-id="67604-149">**操作**:**ブロックまたは\*\*\*\*許可**。</span><span class="sxs-lookup"><span data-stu-id="67604-149">**Action**: **Block** or **Allow**.</span></span>
- <span data-ttu-id="67604-150">**最終更新日**</span><span class="sxs-lookup"><span data-stu-id="67604-150">**Last updated date**</span></span>
- <span data-ttu-id="67604-151">**有効期限**</span><span class="sxs-lookup"><span data-stu-id="67604-151">**Expiration date**</span></span>
- <span data-ttu-id="67604-152">**注**</span><span class="sxs-lookup"><span data-stu-id="67604-152">**Note**</span></span>

<span data-ttu-id="67604-153">[ **グループ化]** をクリックし、[ **アクション** (ブロックまたは**許可)]** または [なし] **にして**エントリを **グループ化します**。</span><span class="sxs-lookup"><span data-stu-id="67604-153">Click **Group** to group the entries by **Action** (**Block** or **Allow**) or **None**.</span></span>

<span data-ttu-id="67604-154">[ **検索]** をクリックし、値の全体または一部を入力して、Enter キーを押して特定の値を検索します。</span><span class="sxs-lookup"><span data-stu-id="67604-154">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="67604-155">完了したら、[検索のクリア] **アイコンを** ![ クリックします ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) 。</span><span class="sxs-lookup"><span data-stu-id="67604-155">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

<span data-ttu-id="67604-156">フィルター を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="67604-156">Click **Filter**.</span></span> <span data-ttu-id="67604-157">表示される **[フィルター** ] ポップアップで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="67604-157">In the **Filter** flyout that appears, configure any of the following settings:</span></span>

- <span data-ttu-id="67604-158">**操作**: 許可 **、ブロック\*\*\*\*、またはその両方**を選択します。</span><span class="sxs-lookup"><span data-stu-id="67604-158">**Action**: Select **Allow**, **Block** or both.</span></span>

- <span data-ttu-id="67604-159">**有効期限を切れない**: オン (トグ ![ ル ](../../media/scc-toggle-off.png) オフ) またはオン ( ![ トオン) をオンにします ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) 。</span><span class="sxs-lookup"><span data-stu-id="67604-159">**Never expire**: Select off (![Toggle off](../../media/scc-toggle-off.png)) or on (![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)).</span></span>

- <span data-ttu-id="67604-160">**Last updated:** Select a start date (**From),** an end date (**To**) or both.</span><span class="sxs-lookup"><span data-stu-id="67604-160">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span></span>

- <span data-ttu-id="67604-161">**有効期限:** 開始日 ([開始**日])、** 終了日 **(To)、またはその**両方を選択します。</span><span class="sxs-lookup"><span data-stu-id="67604-161">**Expiration date**: Select a start date (**From**), an end date (**To**) or both.</span></span>

<span data-ttu-id="67604-162">完了したら、[適用] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="67604-162">When you're finished, click **Apply**.</span></span>

<span data-ttu-id="67604-163">既存のフィルターをクリアするには **、[フィルター**] をクリックし、表示される **フィルター** ポップアップで [フィルターのクリア] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="67604-163">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="67604-164">セキュリティ コンプライアンス センター&、テナントの許可/ブロック リスト内のエントリを変更する</span><span class="sxs-lookup"><span data-stu-id="67604-164">Use the Security & Compliance Center to modify entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="67604-165">URL 値自体は変更できません。</span><span class="sxs-lookup"><span data-stu-id="67604-165">You can't modify the URL value itself.</span></span> <span data-ttu-id="67604-166">代わりに、入力を削除して再作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="67604-166">Instead, you need to delete the entry and recreate it.</span></span>

1. <span data-ttu-id="67604-167">コンプライアンス センター内&で、[脅威管理ポリシー **のテナント** \> **の許可/** \> **ブロック リスト] に移動します**。</span><span class="sxs-lookup"><span data-stu-id="67604-167">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="67604-168">**[URL] タブを選**びます。</span><span class="sxs-lookup"><span data-stu-id="67604-168">Select the **URLs** tab.</span></span>

3. <span data-ttu-id="67604-169">変更するエントリを選択し、[編集] アイコン **を** ![ クリックします ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) 。</span><span class="sxs-lookup"><span data-stu-id="67604-169">Select the entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span>

4. <span data-ttu-id="67604-170">表示されるポップアップで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="67604-170">In the flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="67604-171">**Block/Allow**: Select **Allow** or **Block**.</span><span class="sxs-lookup"><span data-stu-id="67604-171">**Block/Allow**: Select **Allow** or **Block**.</span></span>

   - <span data-ttu-id="67604-172">**無期限 :** 次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="67604-172">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="67604-173">設定がオフになっていること (オフに ![ 切り替 ](../../media/scc-toggle-off.png) え) を確認 **し、Expires ボックスを使用** してエントリに有効期限を指定します。</span><span class="sxs-lookup"><span data-stu-id="67604-173">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entry.</span></span>

     <span data-ttu-id="67604-174">または</span><span class="sxs-lookup"><span data-stu-id="67604-174">or</span></span>

     - <span data-ttu-id="67604-175">エントリを有効期限切れにしないように設定するには、右に切り替えを切り替えて入力します。</span><span class="sxs-lookup"><span data-stu-id="67604-175">Move the toggle to the right to configure the entry to never expire:</span></span> ![オンに切り替え](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="67604-177">.</span><span class="sxs-lookup"><span data-stu-id="67604-177">.</span></span>

   - <span data-ttu-id="67604-178">**オプション メモ**: エントリの説明テキストを入力します。</span><span class="sxs-lookup"><span data-stu-id="67604-178">**Optional note**: Enter descriptive text for the entry.</span></span>

5. <span data-ttu-id="67604-179">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="67604-179">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="67604-180">セキュリティ/コンプライアンス センター&を使用して、テナント許可/ブロック リストからエントリを削除する</span><span class="sxs-lookup"><span data-stu-id="67604-180">Use the Security & Compliance Center to remove entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="67604-181">コンプライアンス センター内&で、[脅威管理ポリシー **のテナント** \> **の許可/** \> **ブロック リスト] に移動します**。</span><span class="sxs-lookup"><span data-stu-id="67604-181">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="67604-182">**[URL] タブを選**びます。</span><span class="sxs-lookup"><span data-stu-id="67604-182">Select the **URLs** tab.</span></span>

3. <span data-ttu-id="67604-183">削除するエントリを選択し、[削除] アイコンを **クリック** ![ します ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) 。</span><span class="sxs-lookup"><span data-stu-id="67604-183">Select the entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="67604-184">警告ダイアログが表示されたら、[削除] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="67604-184">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="67604-185">Exchange Online PowerShell またはスタンドアロン EOP PowerShell を使用してテナントの許可/ブロック一覧を構成する</span><span class="sxs-lookup"><span data-stu-id="67604-185">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="67604-186">PowerShell を使用してテナントの許可/ブロック リストにエントリを追加する</span><span class="sxs-lookup"><span data-stu-id="67604-186">Use PowerShell to add entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="67604-187">テナント許可/ブロック リストにエントリを追加するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="67604-187">To add entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType Url -Action <Allow | Block> -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="67604-188">この例では、メールボックス コレクションとすべてのサブドメインcontoso.com (たとえば、contoso.com、www.contoso.com) の URL ブロック エントリを xyz.abc.contoso.com追加します。</span><span class="sxs-lookup"><span data-stu-id="67604-188">This example adds a URL block entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="67604-189">ExpirationDate パラメーターまたは NoExpiration パラメーターを使用しないため、30 日後にエントリの有効期限が切れます。</span><span class="sxs-lookup"><span data-stu-id="67604-189">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType Url -Action Block -Entries ~contoso.com
```

<span data-ttu-id="67604-190">構文およびパラメーターの詳細については [、「New-TenantAllowBlockListItems」を参照してください](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="67604-190">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="67604-191">PowerShell を使用してテナントの許可/ブロック リスト内のエントリを表示する</span><span class="sxs-lookup"><span data-stu-id="67604-191">Use PowerShell to view entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="67604-192">テナント許可/ブロック リストのエントリを表示するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="67604-192">To view entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url [-Entry <URLValue>] [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration]
```

<span data-ttu-id="67604-193">この例では、ブロックされているすべての URL を返します。</span><span class="sxs-lookup"><span data-stu-id="67604-193">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Action Block
```

<span data-ttu-id="67604-194">構文およびパラメーターの詳細については [、「Get-TenantAllowBlockListItems」を参照してください](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="67604-194">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="67604-195">PowerShell を使用してテナントの許可/ブロック リスト内のエントリを変更する</span><span class="sxs-lookup"><span data-stu-id="67604-195">Use PowerShell to modify entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="67604-196">URL 値自体は変更できません。</span><span class="sxs-lookup"><span data-stu-id="67604-196">You can't modify the URL value itself.</span></span> <span data-ttu-id="67604-197">代わりに、入力を削除して再作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="67604-197">Instead, you need to delete the entry and recreate it.</span></span>

<span data-ttu-id="67604-198">テナント許可/ブロック リストのエントリを変更するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="67604-198">To modify entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN"> [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="67604-199">この例では、指定したエントリの有効期限を変更します。</span><span class="sxs-lookup"><span data-stu-id="67604-199">This example changes the expiration date of the specified entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

<span data-ttu-id="67604-200">構文およびパラメーターの詳細については [、「Set-TenantAllowBlockListItems」を参照してください](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="67604-200">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="67604-201">PowerShell を使用してテナント許可/ブロック リストからエントリを削除する</span><span class="sxs-lookup"><span data-stu-id="67604-201">Use PowerShell to remove entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="67604-202">テナント許可/ブロック リストからエントリを削除するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="67604-202">To remove entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="67604-203">この例では、指定した URL エントリをテナント許可/ブロック一覧から削除します。</span><span class="sxs-lookup"><span data-stu-id="67604-203">This example removes the specified URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="67604-204">構文およびパラメーターの詳細については [、Remove-TenantAllowBlockListItems を参照してください](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="67604-204">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="67604-205">テナント許可/ブロック リストの URL 構文</span><span class="sxs-lookup"><span data-stu-id="67604-205">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="67604-206">IP4v アドレスおよび IPv6 アドレスは使用できますが、TCP/UDP ポートは使用できません。</span><span class="sxs-lookup"><span data-stu-id="67604-206">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="67604-207">ファイル名拡張子は許可されません (たとえば、test.pdf)。</span><span class="sxs-lookup"><span data-stu-id="67604-207">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="67604-208">Unicode はサポートされていませんが、Punycode はサポートされます。</span><span class="sxs-lookup"><span data-stu-id="67604-208">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="67604-209">次の説明がすべて当たる場合、ホスト名を使用できます。</span><span class="sxs-lookup"><span data-stu-id="67604-209">Hostnames are allowed if all of the following statements are true:</span></span>

  - <span data-ttu-id="67604-210">ホスト名にピリオドが含まれている場合。</span><span class="sxs-lookup"><span data-stu-id="67604-210">The hostname contains a period.</span></span>
  - <span data-ttu-id="67604-211">ピリオドの左側には 1 文字以上が必要です。</span><span class="sxs-lookup"><span data-stu-id="67604-211">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="67604-212">ピリオドの右側には 2 文字以上があります。</span><span class="sxs-lookup"><span data-stu-id="67604-212">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="67604-213">たとえば、許可 `t.co` されている、 `.com` または `contoso.` 許可されていない場合です。</span><span class="sxs-lookup"><span data-stu-id="67604-213">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="67604-214">サブパスは暗黙的にはされません。</span><span class="sxs-lookup"><span data-stu-id="67604-214">Subpaths are not implied.</span></span>

  <span data-ttu-id="67604-215">たとえば、何も `contoso.com` 含まれていません `contoso.com/a` 。</span><span class="sxs-lookup"><span data-stu-id="67604-215">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="67604-216">以下のシナリオでは、ワイルドカード (\*) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="67604-216">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="67604-217">ワイルドカードを左のワイルドカードの後にピリオドで指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="67604-217">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="67604-218">たとえば、許可 `*.contoso.com` されていますが `*contoso.com` 、許可されていません。</span><span class="sxs-lookup"><span data-stu-id="67604-218">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="67604-219">ワイルドカードを指定するには、シャープ (/) の後に適切なワイルドカードを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="67604-219">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="67604-220">たとえば、許可 `contoso.com/*` されている、 `contoso.com*` または `contoso.com/ab*` 許可されていない場合です。</span><span class="sxs-lookup"><span data-stu-id="67604-220">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="67604-221">すべてのサブパスは、右のワイルドカードによって示されるものでない。</span><span class="sxs-lookup"><span data-stu-id="67604-221">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="67604-222">たとえば、何も `contoso.com/*` 含まれていません `contoso.com/a` 。</span><span class="sxs-lookup"><span data-stu-id="67604-222">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="67604-223">`*.com*` 無効なドメインです (解決可能なドメインではありません)。また、右のワイルドカードがスラッシュに従いません)。</span><span class="sxs-lookup"><span data-stu-id="67604-223">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="67604-224">IP アドレスではワイルドカードは使用できません。</span><span class="sxs-lookup"><span data-stu-id="67604-224">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="67604-225">切り記号 (~) は、次のシナリオで利用できます。</span><span class="sxs-lookup"><span data-stu-id="67604-225">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="67604-226">左のタイルを指定すると、ドメインとすべてのサブドメインが適用されます。</span><span class="sxs-lookup"><span data-stu-id="67604-226">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="67604-227">たとえば `~contoso.com` 、includes や `contoso.com` `*.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="67604-227">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="67604-228">URL エントリはすべてのプロトコルに適用されているため、プロトコル ( `http://` たとえば `https://` 、, など) を含む URL エントリ `ftp://` は失敗します。</span><span class="sxs-lookup"><span data-stu-id="67604-228">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="67604-229">ユーザー名やパスワードはサポートされていないか、必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="67604-229">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="67604-230">かつ正しくない文字 (' または ") です。</span><span class="sxs-lookup"><span data-stu-id="67604-230">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="67604-231">URL には、可能な限り、すべてのリダイレクトを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="67604-231">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="67604-232">URL 入力のシナリオ</span><span class="sxs-lookup"><span data-stu-id="67604-232">URL entry scenarios</span></span>

<span data-ttu-id="67604-233">有効な URL エントリとその結果については、以下のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="67604-233">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="67604-234">シナリオ: ワイルドカードなし</span><span class="sxs-lookup"><span data-stu-id="67604-234">Scenario: No wildcards</span></span>

<span data-ttu-id="67604-235">**エントリ**: `contoso.com`</span><span class="sxs-lookup"><span data-stu-id="67604-235">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="67604-236">**マッチを許可**する : contoso.com</span><span class="sxs-lookup"><span data-stu-id="67604-236">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="67604-237">**許可しない**:</span><span class="sxs-lookup"><span data-stu-id="67604-237">**Allow not matched**:</span></span>

  - <span data-ttu-id="67604-238">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="67604-238">abc-contoso.com</span></span>
  - <span data-ttu-id="67604-239">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="67604-239">contoso.com/a</span></span>
  - <span data-ttu-id="67604-240">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="67604-240">payroll.contoso.com</span></span>
  - <span data-ttu-id="67604-241">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="67604-241">test.com/contoso.com</span></span>
  - <span data-ttu-id="67604-242">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="67604-242">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="67604-243">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="67604-243">www.contoso.com</span></span>
  - <span data-ttu-id="67604-244">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="67604-244">www.contoso.com/q=a@contoso.com</span></span>
  
- <span data-ttu-id="67604-245">**ブロックの一致**:</span><span class="sxs-lookup"><span data-stu-id="67604-245">**Block match**:</span></span>

  - <span data-ttu-id="67604-246">contoso.com</span><span class="sxs-lookup"><span data-stu-id="67604-246">contoso.com</span></span>
  - <span data-ttu-id="67604-247">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="67604-247">contoso.com/a</span></span>
  - <span data-ttu-id="67604-248">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="67604-248">payroll.contoso.com</span></span>
  - <span data-ttu-id="67604-249">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="67604-249">test.com/contoso.com</span></span>
  - <span data-ttu-id="67604-250">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="67604-250">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="67604-251">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="67604-251">www.contoso.com</span></span>
  - <span data-ttu-id="67604-252">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="67604-252">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="67604-253">**ブロックが見つかりません**: abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="67604-253">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="67604-254">シナリオ: 左ワイルドカード (サブドメイン)</span><span class="sxs-lookup"><span data-stu-id="67604-254">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="67604-255">**エントリ**: `*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="67604-255">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="67604-256">**マッチとブロック** の **マッチを許可します**:</span><span class="sxs-lookup"><span data-stu-id="67604-256">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="67604-257">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="67604-257">www.contoso.com</span></span>
  - <span data-ttu-id="67604-258">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="67604-258">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="67604-259">**一致およびブロック**禁止**Block not matched**</span><span class="sxs-lookup"><span data-stu-id="67604-259">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="67604-260">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="67604-260">123contoso.com</span></span>
  - <span data-ttu-id="67604-261">contoso.com</span><span class="sxs-lookup"><span data-stu-id="67604-261">contoso.com</span></span>
  - <span data-ttu-id="67604-262">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="67604-262">test.com/contoso.com</span></span>
  - <span data-ttu-id="67604-263">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="67604-263">www.contoso.com/abc</span></span>
  
#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="67604-264">シナリオ: パスの上部にワイルドカード文字をワイルドカード</span><span class="sxs-lookup"><span data-stu-id="67604-264">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="67604-265">**エントリ**: `contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="67604-265">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="67604-266">**マッチとブロック** の **マッチを許可します**:</span><span class="sxs-lookup"><span data-stu-id="67604-266">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="67604-267">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="67604-267">contoso.com/a/b</span></span>
  - <span data-ttu-id="67604-268">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="67604-268">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="67604-269">contoso.com/a/?q=joe@t.com</span><span class="sxs-lookup"><span data-stu-id="67604-269">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="67604-270">**一致およびブロック**禁止**Block not matched**</span><span class="sxs-lookup"><span data-stu-id="67604-270">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="67604-271">contoso.com</span><span class="sxs-lookup"><span data-stu-id="67604-271">contoso.com</span></span>
  - <span data-ttu-id="67604-272">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="67604-272">contoso.com/a</span></span>
  - <span data-ttu-id="67604-273">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="67604-273">www.contoso.com</span></span>
  - <span data-ttu-id="67604-274">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="67604-274">www.contoso.com/q=a@contoso.com</span></span>
  
#### <a name="scenario-left-tilde"></a><span data-ttu-id="67604-275">シナリオ: 左揃え</span><span class="sxs-lookup"><span data-stu-id="67604-275">Scenario: Left tilde</span></span>

<span data-ttu-id="67604-276">**エントリ**: `~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="67604-276">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="67604-277">**マッチとブロック** の **マッチを許可します**:</span><span class="sxs-lookup"><span data-stu-id="67604-277">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="67604-278">contoso.com</span><span class="sxs-lookup"><span data-stu-id="67604-278">contoso.com</span></span>
  - <span data-ttu-id="67604-279">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="67604-279">www.contoso.com</span></span>
  - <span data-ttu-id="67604-280">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="67604-280">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="67604-281">**一致およびブロック**禁止**Block not matched**</span><span class="sxs-lookup"><span data-stu-id="67604-281">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="67604-282">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="67604-282">123contoso.com</span></span>
  - <span data-ttu-id="67604-283">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="67604-283">contoso.com/abc</span></span>
  - <span data-ttu-id="67604-284">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="67604-284">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="67604-285">シナリオ: 右のワイルドカード サフィックス</span><span class="sxs-lookup"><span data-stu-id="67604-285">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="67604-286">**エントリ**: `contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="67604-286">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="67604-287">**マッチとブロック** の **マッチを許可します**:</span><span class="sxs-lookup"><span data-stu-id="67604-287">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="67604-288">contoso.com/?q=whatever@fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="67604-288">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="67604-289">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="67604-289">contoso.com/a</span></span>
  - <span data-ttu-id="67604-290">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="67604-290">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="67604-291">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="67604-291">contoso.com/ab</span></span>
  - <span data-ttu-id="67604-292">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="67604-292">contoso.com/b</span></span>
  - <span data-ttu-id="67604-293">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="67604-293">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="67604-294">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="67604-294">contoso.com/ba</span></span>

- <span data-ttu-id="67604-295">**一致禁止およびブロック\*\*\*\*の禁止**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="67604-295">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="67604-296">シナリオ: 左ワイルドカード サブドメインと、右ワイルドカード サフィックス</span><span class="sxs-lookup"><span data-stu-id="67604-296">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="67604-297">**エントリ**: `*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="67604-297">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="67604-298">**マッチとブロック** の **マッチを許可します**:</span><span class="sxs-lookup"><span data-stu-id="67604-298">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="67604-299">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="67604-299">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="67604-300">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="67604-300">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="67604-301">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="67604-301">www.contoso.com/a</span></span>
  - <span data-ttu-id="67604-302">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="67604-302">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="67604-303">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="67604-303">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="67604-304">**一致しない、または\*\*\*\*ブロックを禁止する**: contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="67604-304">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="67604-305">シナリオ: 左右のシルード</span><span class="sxs-lookup"><span data-stu-id="67604-305">Scenario: Left and right tilde</span></span>

<span data-ttu-id="67604-306">**エントリ**: `~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="67604-306">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="67604-307">**マッチとブロック** の **マッチを許可します**:</span><span class="sxs-lookup"><span data-stu-id="67604-307">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="67604-308">contoso.com</span><span class="sxs-lookup"><span data-stu-id="67604-308">contoso.com</span></span>
  - <span data-ttu-id="67604-309">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="67604-309">contoso.com/a</span></span>
  - <span data-ttu-id="67604-310">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="67604-310">www.contoso.com</span></span>
  - <span data-ttu-id="67604-311">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="67604-311">www.contoso.com/b</span></span>
  - <span data-ttu-id="67604-312">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="67604-312">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="67604-313">**一致およびブロック**禁止**Block not matched**</span><span class="sxs-lookup"><span data-stu-id="67604-313">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="67604-314">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="67604-314">123contoso.com</span></span>
  - <span data-ttu-id="67604-315">contoso.org</span><span class="sxs-lookup"><span data-stu-id="67604-315">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="67604-316">シナリオ: IP アドレス</span><span class="sxs-lookup"><span data-stu-id="67604-316">Scenario: IP address</span></span>

<span data-ttu-id="67604-317">**エントリ**: `1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="67604-317">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="67604-318">**一致を許可\*\*\*\*する一致を許可**する : 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="67604-318">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="67604-319">**一致およびブロック**禁止**Block not matched**</span><span class="sxs-lookup"><span data-stu-id="67604-319">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="67604-320">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="67604-320">1.2.3.4/a</span></span>
  - <span data-ttu-id="67604-321">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="67604-321">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="67604-322">適切なワイルドカードを使用した IP アドレス</span><span class="sxs-lookup"><span data-stu-id="67604-322">IP address with right wildcard</span></span>

<span data-ttu-id="67604-323">**エントリ**: `1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="67604-323">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="67604-324">**マッチとブロック** の **マッチを許可します**:</span><span class="sxs-lookup"><span data-stu-id="67604-324">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="67604-325">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="67604-325">1.2.3.4/b</span></span>
  - <span data-ttu-id="67604-326">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="67604-326">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="67604-327">無効なエントリの例</span><span class="sxs-lookup"><span data-stu-id="67604-327">Examples of invalid entries</span></span>

<span data-ttu-id="67604-328">次のエントリは無効です。</span><span class="sxs-lookup"><span data-stu-id="67604-328">The following entries are invalid:</span></span>

- <span data-ttu-id="67604-329">**ドメインの値が見つからないか、無効です**。</span><span class="sxs-lookup"><span data-stu-id="67604-329">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="67604-330">contoso</span><span class="sxs-lookup"><span data-stu-id="67604-330">contoso</span></span>
  - <span data-ttu-id="67604-331">\*.contoso.\*</span><span class="sxs-lookup"><span data-stu-id="67604-331">\*.contoso.\*</span></span>
  - <span data-ttu-id="67604-332">\*.com</span><span class="sxs-lookup"><span data-stu-id="67604-332">\*.com</span></span>
  - <span data-ttu-id="67604-333">\*.pdf</span><span class="sxs-lookup"><span data-stu-id="67604-333">\*.pdf</span></span>

- <span data-ttu-id="67604-334">**テキスト上のワイルドカードまたは間隔文字なし**:</span><span class="sxs-lookup"><span data-stu-id="67604-334">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="67604-335">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="67604-335">\*contoso.com</span></span>
  - <span data-ttu-id="67604-336">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="67604-336">contoso.com\*</span></span>
  - <span data-ttu-id="67604-337">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="67604-337">\*1.2.3.4</span></span>
  - <span data-ttu-id="67604-338">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="67604-338">1.2.3.4\*</span></span>
  - <span data-ttu-id="67604-339">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="67604-339">contoso.com/a\*</span></span>
  - <span data-ttu-id="67604-340">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="67604-340">contoso.com/ab\*</span></span>

- <span data-ttu-id="67604-341">**ポートを使用した IP アドレス**:</span><span class="sxs-lookup"><span data-stu-id="67604-341">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="67604-342">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="67604-342">contoso.com:443</span></span>
  - <span data-ttu-id="67604-343">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="67604-343">abc.contoso.com:25</span></span>

- <span data-ttu-id="67604-344">**非説明のワイルドカード**:</span><span class="sxs-lookup"><span data-stu-id="67604-344">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="67604-345">\*.\*</span><span class="sxs-lookup"><span data-stu-id="67604-345">\*.\*</span></span>

- <span data-ttu-id="67604-346">**中間ワイルドカード**:</span><span class="sxs-lookup"><span data-stu-id="67604-346">**Middle wildcards**:</span></span>

  - <span data-ttu-id="67604-347">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="67604-347">conto\*so.com</span></span>
  - <span data-ttu-id="67604-348">conto~so.com</span><span class="sxs-lookup"><span data-stu-id="67604-348">conto~so.com</span></span>

- <span data-ttu-id="67604-349">**二重ワイルドカード**</span><span class="sxs-lookup"><span data-stu-id="67604-349">**Double wildcards**</span></span>

  - <span data-ttu-id="67604-350">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="67604-350">contoso.com/\*\*</span></span>
  - <span data-ttu-id="67604-351">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="67604-351">contoso.com/\*/\*</span></span>
