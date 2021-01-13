---
title: テナントの許可/ブロックリストで許可とブロックを管理する
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
description: 管理者は、セキュリティ ポータルのテナントの許可/ブロックリストで許可とブロックを構成する方法について学習できます。
ms.openlocfilehash: c789b09224d00f5bb41ae29d6d2a6efa64d23a8d
ms.sourcegitcommit: 495b66b77d6dbe6d69e5b06b304089e4e476e568
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49799715"
---
# <a name="managing-allows-and-blocks-in-the-tenant-allowblock-list"></a><span data-ttu-id="81299-103">テナントの許可/ブロックリストでの許可とブロックの管理</span><span class="sxs-lookup"><span data-stu-id="81299-103">Managing allows and blocks in the Tenant Allow/Block List</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> <span data-ttu-id="81299-104">この記事で説明する機能はプレビューであり、変更される可能性があります。また、すべての組織で利用できるではありません。</span><span class="sxs-lookup"><span data-stu-id="81299-104">The features described in this article are in Preview, are subject to change, and are not available in all organizations.</span></span>

<span data-ttu-id="81299-105">Exchange Online または Exchange Online メールボックスのないスタンドアロンの Exchange Online Protection (EOP) 組織にメールボックスがある Microsoft 365 組織では、EOP フィルターの条件に同意しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="81299-105">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="81299-106">たとえば、良いメッセージが悪い (誤検知) とマークされている場合や、悪いメッセージが許可されている (検出誤検知) 場合があります。</span><span class="sxs-lookup"><span data-stu-id="81299-106">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="81299-107">セキュリティ/コンプライアンス センターのテナントの許可/ブロックリスト&、Microsoft 365 フィルターの条件を手動で上書きする方法が提供されます。</span><span class="sxs-lookup"><span data-stu-id="81299-107">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="81299-108">テナントの許可/ブロックリストは、メール フロー中およびユーザーがクリックした時点で使用されます。</span><span class="sxs-lookup"><span data-stu-id="81299-108">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="81299-109">テナントの許可/ブロックリストで許可またはブロックする URL を指定できます。</span><span class="sxs-lookup"><span data-stu-id="81299-109">You can specify URLs to allow or block in the Tenant Allow/Block List.</span></span>

<span data-ttu-id="81299-110">このトピックでは、セキュリティ & コンプライアンス センターまたは PowerShell (Exchange Online のメールボックスを持つ Microsoft 365 組織向け Exchange Online PowerShell、Exchange Online メールボックスのない組織のスタンドアロン EOP PowerShell) のテナント許可/ブロック一覧のエントリを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="81299-110">This topic describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="81299-111">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="81299-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="81299-112"><https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="81299-112">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="81299-113">[テナントの許可/ブロック **リスト] ページに直接移動するには** 、次の値を使用します <https://protection.office.com/tenantAllowBlockList> 。</span><span class="sxs-lookup"><span data-stu-id="81299-113">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="81299-114">使用可能な URL 値については、この記事で後述する「テナントの許可/ブロックリスト」セクションの [URL](#url-syntax-for-the-tenant-allowblock-list) 構文で説明します。</span><span class="sxs-lookup"><span data-stu-id="81299-114">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

- <span data-ttu-id="81299-115">テナントの許可/ブロックリストでは、URL に最大 500 エントリを許可します。</span><span class="sxs-lookup"><span data-stu-id="81299-115">The Tenant Allow/Block List allows a maximum of 500 entries for URLs.</span></span>

- <span data-ttu-id="81299-116">エントリは 15 分以内にアクティブになります。</span><span class="sxs-lookup"><span data-stu-id="81299-116">An entry should be active within 15 minutes.</span></span>

- <span data-ttu-id="81299-117">許可エントリよりもブロック エントリが優先されます。</span><span class="sxs-lookup"><span data-stu-id="81299-117">Block entries take precedence over allow entries.</span></span>

- <span data-ttu-id="81299-118">既定では、テナントの許可/ブロックリストのエントリは 30 日後に期限切れになります。</span><span class="sxs-lookup"><span data-stu-id="81299-118">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="81299-119">日付を指定するか、有効期限が切れない日付に設定できます。</span><span class="sxs-lookup"><span data-stu-id="81299-119">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="81299-120">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="81299-120">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="81299-121">スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="81299-121">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="81299-122">この記事に記載の手順を行うには、セキュリティ/コンプライアンス センターのアクセス許可が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="81299-122">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="81299-123">テナントの許可/ブロックリストに値を追加および削除するには、組織の管理役割グループまたはセキュリティ管理者役割グループのメンバー **である** 必要があります。</span><span class="sxs-lookup"><span data-stu-id="81299-123">To add and remove values from the Tenant Allow/Block List, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="81299-124">テナントの許可/ブロックリストへの読み取り専用アクセスの場合、グローバル閲覧者またはセキュリティ閲覧者の役割グループのメンバー **である必要があります**。</span><span class="sxs-lookup"><span data-stu-id="81299-124">For read-only access to the Tenant Allow/Block List, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="81299-125">詳細については、「[セキュリティ/コンプライアンス センターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="81299-125">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="81299-126">**注**:</span><span class="sxs-lookup"><span data-stu-id="81299-126">**Notes**:</span></span>

  - <span data-ttu-id="81299-127">Microsoft 365 管理センターで、対応する Azure Active Directory の役割にユーザーを追加すると、ユーザーには、セキュリティ/コンプライアンス センター の必要なアクセス許可 _および_ Microsoft 365 のその他の機能に必要なアクセス許可が付与されます。</span><span class="sxs-lookup"><span data-stu-id="81299-127">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="81299-128">詳細については、「[管理者の役割について](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="81299-128">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="81299-129">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)の **閲覧専用の組織管理** の役割グループが この機能への読み取り専用アクセス権も付与します。</span><span class="sxs-lookup"><span data-stu-id="81299-129">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="81299-130">セキュリティ/コンプライアンス センター&使用して、テナントの許可/ブロックリストに URL エントリを作成する</span><span class="sxs-lookup"><span data-stu-id="81299-130">Use the Security & Compliance Center to create URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="81299-131">URL エントリの構文の詳細については、後の「テナントの許可/ブロックリスト」セクションの [URL](#url-syntax-for-the-tenant-allowblock-list) 構文を参照してください。</span><span class="sxs-lookup"><span data-stu-id="81299-131">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

1. <span data-ttu-id="81299-132">セキュリティ/コンプライアンス センター&、脅威 **管理ポリシー** のテナントの許可 \>  \> **/ブロックリストに移動します**。</span><span class="sxs-lookup"><span data-stu-id="81299-132">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="81299-133">[テナント **の許可/ブロックリスト** ] ページで **、[URL]** タブが選択されているのを確認し、[追加] をクリック **します。**</span><span class="sxs-lookup"><span data-stu-id="81299-133">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Add**</span></span>

3. <span data-ttu-id="81299-134">表示される **[新しい URL の追加** ] フライアウトで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="81299-134">In the **Add new URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="81299-135">**ワイルドカードを使用して URL を追加** する : 1 行に 1 つの URL を入力し、最大 20 文字まで入力します。</span><span class="sxs-lookup"><span data-stu-id="81299-135">**Add URLs with wildcards**: Enter one URL per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="81299-136">**ブロック/許可**: 指定した URLを許可またはブロック **するかどうかを** 選択します。</span><span class="sxs-lookup"><span data-stu-id="81299-136">**Block/Allow**: Select whether you want to **Allow** or **Block** the specified URLs.</span></span>

   - <span data-ttu-id="81299-137">**有効期限が切れる** ことはありません: 次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="81299-137">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="81299-138">設定がオフ (トグル オフ) になっていることを確認し、[有効期限] ボックスを使用してエントリの有効期限 ![ ](../../media/scc-toggle-off.png) を指定します。 </span><span class="sxs-lookup"><span data-stu-id="81299-138">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="81299-139">または</span><span class="sxs-lookup"><span data-stu-id="81299-139">or</span></span>

     - <span data-ttu-id="81299-140">切り替えは右に移動して、有効期限が切れなさらないエントリを構成します。</span><span class="sxs-lookup"><span data-stu-id="81299-140">Move the toggle to the right to configure the entries to never expire:</span></span> ![オンに切り替え](../../media/scc-toggle-on.png)<span data-ttu-id="81299-142">.</span><span class="sxs-lookup"><span data-stu-id="81299-142">.</span></span>

   - <span data-ttu-id="81299-143">**省略可能な** メモ : エントリの説明テキストを入力します。</span><span class="sxs-lookup"><span data-stu-id="81299-143">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="81299-144">完了したら、[追加] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="81299-144">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="81299-145">セキュリティ/コンプライアンス センター&使用して、テナントの許可/ブロックの一覧のエントリを表示する</span><span class="sxs-lookup"><span data-stu-id="81299-145">Use the Security & Compliance Center to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="81299-146">セキュリティ/コンプライアンス センター&、脅威 **管理ポリシー** のテナントの許可 \>  \> **/ブロックリストに移動します**。</span><span class="sxs-lookup"><span data-stu-id="81299-146">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="81299-147">**[URL] タブを選択** します。</span><span class="sxs-lookup"><span data-stu-id="81299-147">Select the **URLs** tab.</span></span>

<span data-ttu-id="81299-148">次の列見出しをクリックして、昇順または降順で並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="81299-148">Click on the following column headings to sort in ascending or descending order:</span></span>

- <span data-ttu-id="81299-149">**値**</span><span class="sxs-lookup"><span data-stu-id="81299-149">**Value**</span></span>
- <span data-ttu-id="81299-150">**Action**: **Block** or **Allow**.</span><span class="sxs-lookup"><span data-stu-id="81299-150">**Action**: **Block** or **Allow**.</span></span>
- <span data-ttu-id="81299-151">**最終更新日**</span><span class="sxs-lookup"><span data-stu-id="81299-151">**Last updated date**</span></span>
- <span data-ttu-id="81299-152">**有効期限**</span><span class="sxs-lookup"><span data-stu-id="81299-152">**Expiration date**</span></span>
- <span data-ttu-id="81299-153">**注**</span><span class="sxs-lookup"><span data-stu-id="81299-153">**Note**</span></span>

<span data-ttu-id="81299-154">[**グループ]** をクリックして、**操作 (** ブロックまたは **許可)** または [なし] で **エントリをグループ\*\*\*\*化します**。</span><span class="sxs-lookup"><span data-stu-id="81299-154">Click **Group** to group the entries by **Action** (**Block** or **Allow**) or **None**.</span></span>

<span data-ttu-id="81299-155">[ **検索]** をクリックし、値のすべてまたは一部を入力し、Enter キーを押して特定の値を検索します。</span><span class="sxs-lookup"><span data-stu-id="81299-155">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="81299-156">完了したら、[検索のクリア] **アイコン** ![ をクリックします ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) 。</span><span class="sxs-lookup"><span data-stu-id="81299-156">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

<span data-ttu-id="81299-157">[フィルター **] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="81299-157">Click **Filter**.</span></span> <span data-ttu-id="81299-158">表示される **フィルター** フライアウトで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="81299-158">In the **Filter** flyout that appears, configure any of the following settings:</span></span>

- <span data-ttu-id="81299-159">**操作**: [許可 **] または [ブロック\*\*\*\*] または**[両方] を選択します。</span><span class="sxs-lookup"><span data-stu-id="81299-159">**Action**: Select **Allow**, **Block** or both.</span></span>

- <span data-ttu-id="81299-160">**Never expire**: Select off: ![ Toggle off or ](../../media/scc-toggle-off.png) on: Toggle on ![ ](../../media/scc-toggle-on.png) .</span><span class="sxs-lookup"><span data-stu-id="81299-160">**Never expire**: Select off: ![Toggle off](../../media/scc-toggle-off.png) or on: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

- <span data-ttu-id="81299-161">**Last updated**: Select a start date (**From),** an end date (**To**) or both.</span><span class="sxs-lookup"><span data-stu-id="81299-161">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span></span>

- <span data-ttu-id="81299-162">**有効期限**: 開始日 **(開始日**)、終了日 (**終了日**) または両方を選択します。</span><span class="sxs-lookup"><span data-stu-id="81299-162">**Expiration date**: Select a start date (**From**), an end date (**To**) or both.</span></span>

<span data-ttu-id="81299-163">完了したら、[適用] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="81299-163">When you're finished, click **Apply**.</span></span>

<span data-ttu-id="81299-164">既存のフィルターをクリアするには、[フィルター]**を** クリックし、表示される [フィルター] フライアウトで [フィルターのクリア]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="81299-164">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="81299-165">セキュリティ/コンプライアンス センター&使用して、テナントの許可/ブロックリストのエントリを変更する</span><span class="sxs-lookup"><span data-stu-id="81299-165">Use the Security & Compliance Center to modify entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="81299-166">URL 値自体は変更できない。</span><span class="sxs-lookup"><span data-stu-id="81299-166">You can't modify the URL value itself.</span></span> <span data-ttu-id="81299-167">代わりに、エントリを削除して再作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="81299-167">Instead, you need to delete the entry and recreate it.</span></span>

1. <span data-ttu-id="81299-168">セキュリティ/コンプライアンス センター&、脅威 **管理ポリシー** のテナントの許可 \>  \> **/ブロックリストに移動します**。</span><span class="sxs-lookup"><span data-stu-id="81299-168">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="81299-169">**[URL] タブを選択** します。</span><span class="sxs-lookup"><span data-stu-id="81299-169">Select the **URLs** tab.</span></span>

3. <span data-ttu-id="81299-170">変更するエントリを選択し、[編集] アイコン **を** ![ クリックします ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) 。</span><span class="sxs-lookup"><span data-stu-id="81299-170">Select the entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span>

4. <span data-ttu-id="81299-171">表示されるフライアウトで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="81299-171">In the flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="81299-172">**ブロック/許可**: 許可または **ブロックを** 選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="81299-172">**Block/Allow**: Select **Allow** or **Block**.</span></span>

   - <span data-ttu-id="81299-173">**有効期限が切れる** ことはありません: 次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="81299-173">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="81299-174">設定がオフ (トグル オフ) になっていることを確認し、[有効期限] ボックスを使用してエントリの ![ ](../../media/scc-toggle-off.png) 有効期限を指定します。 </span><span class="sxs-lookup"><span data-stu-id="81299-174">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entry.</span></span>

     <span data-ttu-id="81299-175">または</span><span class="sxs-lookup"><span data-stu-id="81299-175">or</span></span>

     - <span data-ttu-id="81299-176">トグルを右に移動して、有効期限が切れなさらないエントリを構成します。</span><span class="sxs-lookup"><span data-stu-id="81299-176">Move the toggle to the right to configure the entry to never expire:</span></span> ![オンに切り替え](../../media/scc-toggle-on.png)<span data-ttu-id="81299-178">.</span><span class="sxs-lookup"><span data-stu-id="81299-178">.</span></span>

   - <span data-ttu-id="81299-179">**省略可能なメモ**: エントリの説明文を入力します。</span><span class="sxs-lookup"><span data-stu-id="81299-179">**Optional note**: Enter descriptive text for the entry.</span></span>

5. <span data-ttu-id="81299-180">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="81299-180">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="81299-181">セキュリティ/コンプライアンス センター&使用して、テナントの許可/ブロックの一覧からエントリを削除する</span><span class="sxs-lookup"><span data-stu-id="81299-181">Use the Security & Compliance Center to remove entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="81299-182">セキュリティ/コンプライアンス センター&、脅威 **管理ポリシー** のテナントの許可 \>  \> **/ブロックリストに移動します**。</span><span class="sxs-lookup"><span data-stu-id="81299-182">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="81299-183">**[URL] タブを選択** します。</span><span class="sxs-lookup"><span data-stu-id="81299-183">Select the **URLs** tab.</span></span>

3. <span data-ttu-id="81299-184">削除するエントリを選択し、[削除] アイコン **を** ![ クリックします ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) 。</span><span class="sxs-lookup"><span data-stu-id="81299-184">Select the entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="81299-185">警告ダイアログが表示されたら、[削除] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="81299-185">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="81299-186">Exchange Online PowerShell またはスタンドアロンの EOP PowerShell を使用してテナントの許可/ブロックリストを構成する</span><span class="sxs-lookup"><span data-stu-id="81299-186">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="81299-187">PowerShell を使用してテナントの許可/ブロックリストにエントリを追加する</span><span class="sxs-lookup"><span data-stu-id="81299-187">Use PowerShell to add entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="81299-188">テナントの許可/ブロックリストにエントリを追加するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="81299-188">To add entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType Url -Action <Allow | Block> -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="81299-189">この例では、contoso.com およびすべてのサブドメイン (contoso.com、www.contoso.com、および xyz.abc.contoso.com) の URL ブロック エントリを追加します。</span><span class="sxs-lookup"><span data-stu-id="81299-189">This example adds a URL block entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="81299-190">ExpirationDate パラメーターまたは NoExpiration パラメーターを使用しなかったため、エントリは 30 日後に期限切れになります。</span><span class="sxs-lookup"><span data-stu-id="81299-190">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType Url -Action Block -Entries ~contoso.com
```

<span data-ttu-id="81299-191">構文およびパラメーターの詳細については [、「New-TenantAllowBlockListItems」を参照してください](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="81299-191">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="81299-192">PowerShell を使用してテナントの許可/ブロックリストのエントリを表示する</span><span class="sxs-lookup"><span data-stu-id="81299-192">Use PowerShell to view entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="81299-193">テナントの許可/ブロックリストのエントリを表示するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="81299-193">To view entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url [-Entry <URLValue>] [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration]
```

<span data-ttu-id="81299-194">この例では、すべてのブロックされた URL を返します。</span><span class="sxs-lookup"><span data-stu-id="81299-194">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Action Block
```

<span data-ttu-id="81299-195">構文およびパラメーターの詳細については [、「Get-TenantAllowBlockListItems」を参照してください](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="81299-195">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="81299-196">PowerShell を使用してテナントの許可/ブロックリストのエントリを変更する</span><span class="sxs-lookup"><span data-stu-id="81299-196">Use PowerShell to modify entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="81299-197">URL 値自体は変更できない。</span><span class="sxs-lookup"><span data-stu-id="81299-197">You can't modify the URL value itself.</span></span> <span data-ttu-id="81299-198">代わりに、エントリを削除して再作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="81299-198">Instead, you need to delete the entry and recreate it.</span></span>

<span data-ttu-id="81299-199">テナントの許可/ブロックリストのエントリを変更するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="81299-199">To modify entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN"> [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="81299-200">次の使用例は、指定したエントリの有効期限を変更します。</span><span class="sxs-lookup"><span data-stu-id="81299-200">This example changes the expiration date of the specified entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

<span data-ttu-id="81299-201">構文およびパラメーターの詳細については [、「Set-TenantAllowBlockListItems」を参照してください](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="81299-201">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="81299-202">PowerShell を使用してテナントの許可/ブロックリストからエントリを削除する</span><span class="sxs-lookup"><span data-stu-id="81299-202">Use PowerShell to remove entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="81299-203">テナントの許可/ブロックリストからエントリを削除するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="81299-203">To remove entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="81299-204">この例では、指定した URL エントリをテナントの許可/ブロックリストから削除します。</span><span class="sxs-lookup"><span data-stu-id="81299-204">This example removes the specified URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="81299-205">構文およびパラメーターの詳細については [、「Remove-TenantAllowBlockListItems」を参照してください](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="81299-205">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="81299-206">テナントの許可/ブロックリストの URL 構文</span><span class="sxs-lookup"><span data-stu-id="81299-206">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="81299-207">IP4v および IPv6 アドレスは許可されますが、TCP/UDP ポートは許可されません。</span><span class="sxs-lookup"><span data-stu-id="81299-207">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="81299-208">ファイル名拡張子は許可されません (たとえば、test.pdf)。</span><span class="sxs-lookup"><span data-stu-id="81299-208">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="81299-209">Unicode はサポートされていませんが、Punycode はサポートされています。</span><span class="sxs-lookup"><span data-stu-id="81299-209">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="81299-210">ホスト名は、次のステートメントのすべてが当てはまる場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="81299-210">Hostnames are allowed if all of the following statements are true:</span></span>

  - <span data-ttu-id="81299-211">ホスト名にはピリオドが含まれている。</span><span class="sxs-lookup"><span data-stu-id="81299-211">The hostname contains a period.</span></span>
  - <span data-ttu-id="81299-212">ピリオドの左側に少なくとも 1 つの文字があります。</span><span class="sxs-lookup"><span data-stu-id="81299-212">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="81299-213">ピリオドの右側に 2 文字以上あります。</span><span class="sxs-lookup"><span data-stu-id="81299-213">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="81299-214">たとえば、 `t.co` 許可されている、または `.com` `contoso.` 許可されていない。</span><span class="sxs-lookup"><span data-stu-id="81299-214">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="81299-215">サブパスは暗黙的ではありません。</span><span class="sxs-lookup"><span data-stu-id="81299-215">Subpaths are not implied.</span></span>

  <span data-ttu-id="81299-216">たとえば、 `contoso.com` `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="81299-216">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="81299-217">ワイルドカード (\*) は、次のシナリオで使用できます。</span><span class="sxs-lookup"><span data-stu-id="81299-217">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="81299-218">サブドメインを指定するには、左ワイルドカードの後にピリオドを付けなければならない。</span><span class="sxs-lookup"><span data-stu-id="81299-218">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="81299-219">たとえば、 `*.contoso.com` 許可されます。 `*contoso.com` 許可されません。</span><span class="sxs-lookup"><span data-stu-id="81299-219">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="81299-220">パスを指定するには、右のワイルドカードがスラッシュ (/) の後に続く必要があります。</span><span class="sxs-lookup"><span data-stu-id="81299-220">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="81299-221">たとえば、 `contoso.com/*` 許可されている、または `contoso.com*` `contoso.com/ab*` 許可されていない。</span><span class="sxs-lookup"><span data-stu-id="81299-221">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="81299-222">すべてのサブパスは、適切なワイルドカードによって暗黙的に示されるものではありません。</span><span class="sxs-lookup"><span data-stu-id="81299-222">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="81299-223">たとえば、 `contoso.com/*` `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="81299-223">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="81299-224">`*.com*` は無効です (解決可能なドメインではなく、右のワイルドカードがスラッシュに従う必要があります)。</span><span class="sxs-lookup"><span data-stu-id="81299-224">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="81299-225">IP アドレスではワイルドカードを使用できません。</span><span class="sxs-lookup"><span data-stu-id="81299-225">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="81299-226">チルダ (~) 文字は、次のシナリオで使用できます。</span><span class="sxs-lookup"><span data-stu-id="81299-226">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="81299-227">左チルダは、ドメインとすべてのサブドメインを意味します。</span><span class="sxs-lookup"><span data-stu-id="81299-227">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="81299-228">次に例 `~contoso.com` を示 `contoso.com` します `*.contoso.com` 。</span><span class="sxs-lookup"><span data-stu-id="81299-228">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="81299-229">URL エントリは、すべてのプロトコルに適用されるので、プロトコルを含む URL エントリ (たとえば、,, `http://` `https://` `ftp://` または) は失敗します。</span><span class="sxs-lookup"><span data-stu-id="81299-229">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="81299-230">ユーザー名またはパスワードはサポートされていないか、必須です。</span><span class="sxs-lookup"><span data-stu-id="81299-230">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="81299-231">引用符 (' または ") は無効な文字です。</span><span class="sxs-lookup"><span data-stu-id="81299-231">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="81299-232">URL には、可能な限りすべてのリダイレクトを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="81299-232">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="81299-233">URL エントリのシナリオ</span><span class="sxs-lookup"><span data-stu-id="81299-233">URL entry scenarios</span></span>

<span data-ttu-id="81299-234">有効な URL エントリとその結果については、次のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="81299-234">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="81299-235">シナリオ: ワイルドカードなし</span><span class="sxs-lookup"><span data-stu-id="81299-235">Scenario: No wildcards</span></span>

<span data-ttu-id="81299-236">**エントリ**: `contoso.com`</span><span class="sxs-lookup"><span data-stu-id="81299-236">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="81299-237">**一致を許可** する : contoso.com</span><span class="sxs-lookup"><span data-stu-id="81299-237">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="81299-238">**Allow not matched**:</span><span class="sxs-lookup"><span data-stu-id="81299-238">**Allow not matched**:</span></span>

  - <span data-ttu-id="81299-239">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="81299-239">abc-contoso.com</span></span>
  - <span data-ttu-id="81299-240">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="81299-240">contoso.com/a</span></span>
  - <span data-ttu-id="81299-241">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="81299-241">payroll.contoso.com</span></span>
  - <span data-ttu-id="81299-242">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="81299-242">test.com/contoso.com</span></span>
  - <span data-ttu-id="81299-243">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="81299-243">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="81299-244">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="81299-244">www.contoso.com</span></span>
  - <span data-ttu-id="81299-245">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="81299-245">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="81299-246">**ブロック一致**:</span><span class="sxs-lookup"><span data-stu-id="81299-246">**Block match**:</span></span>

  - <span data-ttu-id="81299-247">contoso.com</span><span class="sxs-lookup"><span data-stu-id="81299-247">contoso.com</span></span>
  - <span data-ttu-id="81299-248">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="81299-248">contoso.com/a</span></span>
  - <span data-ttu-id="81299-249">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="81299-249">payroll.contoso.com</span></span>
  - <span data-ttu-id="81299-250">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="81299-250">test.com/contoso.com</span></span>
  - <span data-ttu-id="81299-251">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="81299-251">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="81299-252">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="81299-252">www.contoso.com</span></span>
  - <span data-ttu-id="81299-253">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="81299-253">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="81299-254">**ブロックが一致しません**: abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="81299-254">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="81299-255">シナリオ: 左ワイルドカード (サブドメイン)</span><span class="sxs-lookup"><span data-stu-id="81299-255">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="81299-256">**エントリ**: `*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="81299-256">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="81299-257">**一致とブロック** の一 **致を許可する**:</span><span class="sxs-lookup"><span data-stu-id="81299-257">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="81299-258">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="81299-258">www.contoso.com</span></span>
  - <span data-ttu-id="81299-259">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="81299-259">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="81299-260">**Allow not matched** and **Block not matched**:</span><span class="sxs-lookup"><span data-stu-id="81299-260">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="81299-261">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="81299-261">123contoso.com</span></span>
  - <span data-ttu-id="81299-262">contoso.com</span><span class="sxs-lookup"><span data-stu-id="81299-262">contoso.com</span></span>
  - <span data-ttu-id="81299-263">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="81299-263">test.com/contoso.com</span></span>
  - <span data-ttu-id="81299-264">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="81299-264">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="81299-265">シナリオ: パスの上部に右のワイルドカード</span><span class="sxs-lookup"><span data-stu-id="81299-265">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="81299-266">**エントリ**: `contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="81299-266">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="81299-267">**一致とブロック** の一 **致を許可する**:</span><span class="sxs-lookup"><span data-stu-id="81299-267">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="81299-268">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="81299-268">contoso.com/a/b</span></span>
  - <span data-ttu-id="81299-269">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="81299-269">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="81299-270">contoso.com/a/?q=joe@t.com</span><span class="sxs-lookup"><span data-stu-id="81299-270">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="81299-271">**Allow not matched** and **Block not matched**:</span><span class="sxs-lookup"><span data-stu-id="81299-271">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="81299-272">contoso.com</span><span class="sxs-lookup"><span data-stu-id="81299-272">contoso.com</span></span>
  - <span data-ttu-id="81299-273">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="81299-273">contoso.com/a</span></span>
  - <span data-ttu-id="81299-274">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="81299-274">www.contoso.com</span></span>
  - <span data-ttu-id="81299-275">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="81299-275">www.contoso.com/q=a@contoso.com</span></span>

#### <a name="scenario-left-tilde"></a><span data-ttu-id="81299-276">シナリオ: 左チルダ</span><span class="sxs-lookup"><span data-stu-id="81299-276">Scenario: Left tilde</span></span>

<span data-ttu-id="81299-277">**エントリ**: `~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="81299-277">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="81299-278">**一致とブロック** の一 **致を許可する**:</span><span class="sxs-lookup"><span data-stu-id="81299-278">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="81299-279">contoso.com</span><span class="sxs-lookup"><span data-stu-id="81299-279">contoso.com</span></span>
  - <span data-ttu-id="81299-280">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="81299-280">www.contoso.com</span></span>
  - <span data-ttu-id="81299-281">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="81299-281">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="81299-282">**Allow not matched** and **Block not matched**:</span><span class="sxs-lookup"><span data-stu-id="81299-282">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="81299-283">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="81299-283">123contoso.com</span></span>
  - <span data-ttu-id="81299-284">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="81299-284">contoso.com/abc</span></span>
  - <span data-ttu-id="81299-285">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="81299-285">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="81299-286">シナリオ: 右ワイルドカード サフィックス</span><span class="sxs-lookup"><span data-stu-id="81299-286">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="81299-287">**エントリ**: `contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="81299-287">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="81299-288">**一致とブロック** の一 **致を許可する**:</span><span class="sxs-lookup"><span data-stu-id="81299-288">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="81299-289">contoso.com/?q=whatever@fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="81299-289">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="81299-290">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="81299-290">contoso.com/a</span></span>
  - <span data-ttu-id="81299-291">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="81299-291">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="81299-292">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="81299-292">contoso.com/ab</span></span>
  - <span data-ttu-id="81299-293">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="81299-293">contoso.com/b</span></span>
  - <span data-ttu-id="81299-294">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="81299-294">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="81299-295">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="81299-295">contoso.com/ba</span></span>

- <span data-ttu-id="81299-296">**Allow not matched** and **Block not matched**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="81299-296">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="81299-297">シナリオ: 左ワイルドカード サブドメインと右のワイルドカード サフィックス</span><span class="sxs-lookup"><span data-stu-id="81299-297">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="81299-298">**エントリ**: `*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="81299-298">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="81299-299">**一致とブロック** の一 **致を許可する**:</span><span class="sxs-lookup"><span data-stu-id="81299-299">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="81299-300">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="81299-300">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="81299-301">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="81299-301">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="81299-302">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="81299-302">www.contoso.com/a</span></span>
  - <span data-ttu-id="81299-303">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="81299-303">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="81299-304">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="81299-304">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="81299-305">**Allow not matched** and **Block not matched**: contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="81299-305">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="81299-306">シナリオ: 左右のチルダ</span><span class="sxs-lookup"><span data-stu-id="81299-306">Scenario: Left and right tilde</span></span>

<span data-ttu-id="81299-307">**エントリ**: `~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="81299-307">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="81299-308">**一致とブロック** の一 **致を許可する**:</span><span class="sxs-lookup"><span data-stu-id="81299-308">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="81299-309">contoso.com</span><span class="sxs-lookup"><span data-stu-id="81299-309">contoso.com</span></span>
  - <span data-ttu-id="81299-310">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="81299-310">contoso.com/a</span></span>
  - <span data-ttu-id="81299-311">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="81299-311">www.contoso.com</span></span>
  - <span data-ttu-id="81299-312">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="81299-312">www.contoso.com/b</span></span>
  - <span data-ttu-id="81299-313">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="81299-313">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="81299-314">**Allow not matched** and **Block not matched**:</span><span class="sxs-lookup"><span data-stu-id="81299-314">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="81299-315">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="81299-315">123contoso.com</span></span>
  - <span data-ttu-id="81299-316">contoso.org</span><span class="sxs-lookup"><span data-stu-id="81299-316">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="81299-317">シナリオ: IP アドレス</span><span class="sxs-lookup"><span data-stu-id="81299-317">Scenario: IP address</span></span>

<span data-ttu-id="81299-318">**エントリ**: `1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="81299-318">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="81299-319">**マッチを許可** し **、マッチを** ブロックする : 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="81299-319">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="81299-320">**Allow not matched** and **Block not matched**:</span><span class="sxs-lookup"><span data-stu-id="81299-320">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="81299-321">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="81299-321">1.2.3.4/a</span></span>
  - <span data-ttu-id="81299-322">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="81299-322">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="81299-323">右ワイルドカードを使用した IP アドレス</span><span class="sxs-lookup"><span data-stu-id="81299-323">IP address with right wildcard</span></span>

<span data-ttu-id="81299-324">**エントリ**: `1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="81299-324">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="81299-325">**一致とブロック** の一 **致を許可する**:</span><span class="sxs-lookup"><span data-stu-id="81299-325">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="81299-326">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="81299-326">1.2.3.4/b</span></span>
  - <span data-ttu-id="81299-327">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="81299-327">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="81299-328">無効なエントリの例</span><span class="sxs-lookup"><span data-stu-id="81299-328">Examples of invalid entries</span></span>

<span data-ttu-id="81299-329">次のエントリは無効です。</span><span class="sxs-lookup"><span data-stu-id="81299-329">The following entries are invalid:</span></span>

- <span data-ttu-id="81299-330">**ドメイン値が見つからないか無効です**。</span><span class="sxs-lookup"><span data-stu-id="81299-330">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="81299-331">contoso</span><span class="sxs-lookup"><span data-stu-id="81299-331">contoso</span></span>
  - <span data-ttu-id="81299-332">\*.contoso.\*</span><span class="sxs-lookup"><span data-stu-id="81299-332">\*.contoso.\*</span></span>
  - <span data-ttu-id="81299-333">\*.com</span><span class="sxs-lookup"><span data-stu-id="81299-333">\*.com</span></span>
  - <span data-ttu-id="81299-334">\*.pdf</span><span class="sxs-lookup"><span data-stu-id="81299-334">\*.pdf</span></span>

- <span data-ttu-id="81299-335">**テキストに対するワイルドカード、またはスペースを使用しない文字**:</span><span class="sxs-lookup"><span data-stu-id="81299-335">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="81299-336">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="81299-336">\*contoso.com</span></span>
  - <span data-ttu-id="81299-337">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="81299-337">contoso.com\*</span></span>
  - <span data-ttu-id="81299-338">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="81299-338">\*1.2.3.4</span></span>
  - <span data-ttu-id="81299-339">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="81299-339">1.2.3.4\*</span></span>
  - <span data-ttu-id="81299-340">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="81299-340">contoso.com/a\*</span></span>
  - <span data-ttu-id="81299-341">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="81299-341">contoso.com/ab\*</span></span>

- <span data-ttu-id="81299-342">**ポートを含む IP アドレス**:</span><span class="sxs-lookup"><span data-stu-id="81299-342">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="81299-343">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="81299-343">contoso.com:443</span></span>
  - <span data-ttu-id="81299-344">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="81299-344">abc.contoso.com:25</span></span>

- <span data-ttu-id="81299-345">**説明的でないワイルドカード**:</span><span class="sxs-lookup"><span data-stu-id="81299-345">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="81299-346">\*.\*</span><span class="sxs-lookup"><span data-stu-id="81299-346">\*.\*</span></span>

- <span data-ttu-id="81299-347">**中のワイルドカード**:</span><span class="sxs-lookup"><span data-stu-id="81299-347">**Middle wildcards**:</span></span>

  - <span data-ttu-id="81299-348">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="81299-348">conto\*so.com</span></span>
  - <span data-ttu-id="81299-349">conto~so.com</span><span class="sxs-lookup"><span data-stu-id="81299-349">conto~so.com</span></span>

- <span data-ttu-id="81299-350">**二重ワイルドカード**</span><span class="sxs-lookup"><span data-stu-id="81299-350">**Double wildcards**</span></span>

  - <span data-ttu-id="81299-351">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="81299-351">contoso.com/\*\*</span></span>
  - <span data-ttu-id="81299-352">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="81299-352">contoso.com/\*/\*</span></span>
