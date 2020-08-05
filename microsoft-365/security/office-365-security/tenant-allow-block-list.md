---
title: 許可または禁止する Url をテナントの許可/ブロックリストで管理する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 管理者は、セキュリティ & コンプライアンスセンターのテナントの許可/ブロックリストで URL エントリを構成する方法について説明します。
ms.openlocfilehash: 5ff34cca922f18a015bd9da847facc8177cf8790
ms.sourcegitcommit: 89178b8f20d59ca88cfca303a13062b91fbeae9d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/04/2020
ms.locfileid: "46552552"
---
# <a name="manage-urls-in-the-tenant-allowblock-list"></a><span data-ttu-id="f6f7b-103">テナントの許可/ブロックリストの Url を管理する</span><span class="sxs-lookup"><span data-stu-id="f6f7b-103">Manage URLs in the Tenant Allow/Block List</span></span>

> [!NOTE]
> <span data-ttu-id="f6f7b-104">このトピックで説明する機能はプレビュー段階にあり、変更される可能性があり、組織によっては利用できません。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-104">The features described in this topic are in Preview, are subject to change, and are not available in all organizations.</span></span>

<span data-ttu-id="f6f7b-105">Exchange online または exchange online メールボックスを使用しない exchange online またはスタンドアロンの Exchange Online Protection (EOP) 組織内にメールボックスを持つ Microsoft 365 組織では、EOP フィルター verdict の使用に同意しない場合があります。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-105">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="f6f7b-106">たとえば、良好なメッセージが不良 (誤検知) としてマークされている場合や、無効なメッセージが表示される場合があります (誤検知)。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-106">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="f6f7b-107">セキュリティ & コンプライアンスセンターのテナントの許可/禁止リストにより、Microsoft 365 filtering verdicts を手動で上書きすることができます。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-107">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="f6f7b-108">テナントの許可/ブロックリストは、メールフローおよびユーザークリック時に使用されます。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-108">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="f6f7b-109">テナントの許可/ブロックリストで許可またはブロックする Url を指定できます。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-109">You can specify URLs to allow or block in the Tenant Allow/Block List.</span></span>

<span data-ttu-id="f6f7b-110">このトピックでは、セキュリティ & コンプライアンスセンターまたは PowerShell (exchange online にメールボックスがある Microsoft 365 組織の場合は exchange Online PowerShell、exchange online メールボックスを使用しない組織の場合は、スタンドアロン EOP PowerShell) で、テナントの許可/ブロックリストのエントリを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-110">This topic describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f6f7b-111">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="f6f7b-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="f6f7b-112"><https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-112">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="f6f7b-113">[**テナントの許可/ブロックリスト**] ページに直接移動するには、を使用 <https://protection.office.com/tenantAllowBlockList> します。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-113">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="f6f7b-114">使用可能な URL 値については、このトピックで後述する「[テナントの許可/ブロックリスト」セクションの url 構文](#url-syntax-for-the-tenant-allowblock-list)で説明されています。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-114">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this topic.</span></span>

- <span data-ttu-id="f6f7b-115">テナントの許可/ブロックリストでは、URLss に最大500エントリを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-115">The Tenant Allow/Block List allows a maximum of 500 entries for URLss.</span></span>

- <span data-ttu-id="f6f7b-116">エントリは15分以内にアクティブである必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-116">An entry should be active within 15 minutes.</span></span>

- <span data-ttu-id="f6f7b-117">禁止エントリは、許可エントリよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-117">Block entries take precedence over allow entries.</span></span>

- <span data-ttu-id="f6f7b-118">既定では、テナントの許可/ブロックリストのエントリは30日後に期限切れになります。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-118">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="f6f7b-119">日付を指定するか、期限切れにならないように設定できます。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-119">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="f6f7b-120">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-120">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="f6f7b-121">スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-121">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="f6f7b-122">このトピックの手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-122">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="f6f7b-123">テナントの許可/禁止リストの値を追加および削除するには、次のいずれかの役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-123">To add and remove values from the Tenant Allow/Block List, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="f6f7b-124">**組織の管理**または[セキュリティ/コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)の**セキュリティ管理者**。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-124">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="f6f7b-125">**組織の管理**または [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) の**検疫管理**。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-125">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="f6f7b-126">テナントの許可/禁止リストに対する読み取り専用アクセスの場合は、次のいずれかの役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-126">For read-only access to the Tenant Allow/Block List, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="f6f7b-127">[セキュリティ/コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)の**セキュリティ閲覧者**。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-127">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="f6f7b-128">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) の**表示限定の組織管理**。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-128">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="f6f7b-129">セキュリティ & コンプライアンスセンターを使用して、テナントの許可/ブロックリストで URL エントリを作成する</span><span class="sxs-lookup"><span data-stu-id="f6f7b-129">Use the Security & Compliance Center to create URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="f6f7b-130">URL エントリの構文の詳細については、このトピックで後述する「[テナントの許可/ブロックリスト」セクションの url 構文](#url-syntax-for-the-tenant-allowblock-list)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-130">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this topic.</span></span>

1. <span data-ttu-id="f6f7b-131">[セキュリティ & コンプライアンスセンター] で、[**脅威管理** \> **ポリシー**の \> **テナントの許可/ブロックリスト**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-131">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="f6f7b-132">[**テナントの許可/ブロックリスト**] ページで、[ **url** ] タブが選択されていることを確認し、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-132">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Add**</span></span>

3. <span data-ttu-id="f6f7b-133">表示される [**新しい url の追加**] ポップアップで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-133">In the **Add new URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="f6f7b-134">**ワイルドカードを使用して url を追加**します。1行に1つの url を入力します。最大値は20です。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-134">**Add URLs with wildcards**: Enter one URL per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="f6f7b-135">[**ブロック/許可**]: 指定した Url を**許可**または**ブロック**するかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-135">**Block/Allow**: Select whether you want to **Allow** or **Block** the specified URLs.</span></span>

   - <span data-ttu-id="f6f7b-136">**無期限: 次**のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-136">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="f6f7b-137">設定がオフ (トグルオフ) になっていることを確認 ![ ](../../media/scc-toggle-off.png) し、 **[有効期限**] ボックスを使用して、エントリの有効期限を指定します。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-137">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="f6f7b-138">または</span><span class="sxs-lookup"><span data-stu-id="f6f7b-138">or</span></span>

     - <span data-ttu-id="f6f7b-139">右にトグルを移動して、期限切れにならないようにエントリを構成します。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-139">Move the toggle to the right to configure the entries to never expire:</span></span> ![オンに切り替え](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="f6f7b-141">.</span><span class="sxs-lookup"><span data-stu-id="f6f7b-141">.</span></span>

   - <span data-ttu-id="f6f7b-142">**オプションのメモ**: エントリの説明テキストを入力します。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-142">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="f6f7b-143">完了したら、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-143">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="f6f7b-144">セキュリティ & コンプライアンスセンターを使用して、テナントの許可/ブロックリストのエントリを表示する</span><span class="sxs-lookup"><span data-stu-id="f6f7b-144">Use the Security & Compliance Center to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="f6f7b-145">[セキュリティ & コンプライアンスセンター] で、[**脅威管理** \> **ポリシー**の \> **テナントの許可/ブロックリスト**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-145">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="f6f7b-146">[ **Url** ] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-146">Select the **URLs** tab.</span></span>

<span data-ttu-id="f6f7b-147">次の列見出しをクリックすると、昇順または降順で並べ替えられます。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-147">Click on the following column headings to sort in ascending or descending order:</span></span>

- <span data-ttu-id="f6f7b-148">**値**</span><span class="sxs-lookup"><span data-stu-id="f6f7b-148">**Value**</span></span>
- <span data-ttu-id="f6f7b-149">**アクション**:**ブロック**または**許可**。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-149">**Action**: **Block** or **Allow**.</span></span>
- <span data-ttu-id="f6f7b-150">**最終更新日**</span><span class="sxs-lookup"><span data-stu-id="f6f7b-150">**Last updated date**</span></span>
- <span data-ttu-id="f6f7b-151">**有効期限**</span><span class="sxs-lookup"><span data-stu-id="f6f7b-151">**Expiration date**</span></span>
- <span data-ttu-id="f6f7b-152">**注**</span><span class="sxs-lookup"><span data-stu-id="f6f7b-152">**Note**</span></span>

<span data-ttu-id="f6f7b-153">[**グループ化**] をクリックして、エントリを**アクション**(**ブロック**または**許可**) または**なし**とグループ化します。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-153">Click **Group** to group the entries by **Action** (**Block** or **Allow**) or **None**.</span></span>

<span data-ttu-id="f6f7b-154">[**検索**] をクリックして、値の全体または一部を入力し、enter キーを押して特定の値を検索します。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-154">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="f6f7b-155">完了したら、[検索のクリア検索の**クリア**] をクリックし ![ ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) ます。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-155">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

<span data-ttu-id="f6f7b-156">[**フィルター**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-156">Click **Filter**.</span></span> <span data-ttu-id="f6f7b-157">表示される**フィルター**のポップアップで、次のいずれかの設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-157">In the **Filter** flyout that appears, configure any of the following settings:</span></span>

- <span data-ttu-id="f6f7b-158">**アクション**: **Allow**、 **Block** 、または both を選択します。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-158">**Action**: Select **Allow**, **Block** or both.</span></span>

- <span data-ttu-id="f6f7b-159">**無期限: オフ**(オフ ![ ](../../media/scc-toggle-off.png) ) またはオン ( ![ トグルオン ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) )。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-159">**Never expire**: Select off (![Toggle off](../../media/scc-toggle-off.png)) or on (![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)).</span></span>

- <span data-ttu-id="f6f7b-160">**最終更新**日時: 開始日 (開始**日)、** 終了日 (**To**)、またはその両方を選択します。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-160">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span></span>

- <span data-ttu-id="f6f7b-161">[**有効期限**]: 開始日 (開始**日)、** 終了日 (**To**)、またはその両方を選択します。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-161">**Expiration date**: Select a start date (**From**), an end date (**To**) or both.</span></span>

<span data-ttu-id="f6f7b-162">完了したら、[**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-162">When you're finished, click **Apply**.</span></span>

<span data-ttu-id="f6f7b-163">既存のフィルターをクリアするには、[**フィルター**] をクリックし、表示される**フィルター**のポップアップで [**フィルターのクリア**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-163">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="f6f7b-164">セキュリティ & コンプライアンスセンターを使用して、テナントの許可/ブロックリストのエントリを変更する</span><span class="sxs-lookup"><span data-stu-id="f6f7b-164">Use the Security & Compliance Center to modify entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="f6f7b-165">URL の値自体を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-165">You can't modify the URL value itself.</span></span> <span data-ttu-id="f6f7b-166">代わりに、エントリを削除して再作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-166">Instead, you need to delete the entry and recreate it.</span></span>

1. <span data-ttu-id="f6f7b-167">[セキュリティ & コンプライアンスセンター] で、[**脅威管理** \> **ポリシー**の \> **テナントの許可/ブロックリスト**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-167">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="f6f7b-168">[ **Url** ] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-168">Select the **URLs** tab.</span></span>

3. <span data-ttu-id="f6f7b-169">変更するエントリを選択し、[編集アイコンの**編集**] をクリックし ![ ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) ます。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-169">Select the entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span>

4. <span data-ttu-id="f6f7b-170">表示されたポップアップで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-170">In the flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="f6f7b-171">[**ブロック/許可**]: [**許可**] または [**ブロック**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-171">**Block/Allow**: Select **Allow** or **Block**.</span></span>

   - <span data-ttu-id="f6f7b-172">**無期限: 次**のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-172">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="f6f7b-173">設定がオフ (トグルオフ) になっていることを確認 ![ ](../../media/scc-toggle-off.png) し、 **[有効期限**] ボックスを使用して、エントリの有効期限を指定します。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-173">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entry.</span></span>

     <span data-ttu-id="f6f7b-174">または</span><span class="sxs-lookup"><span data-stu-id="f6f7b-174">or</span></span>

     - <span data-ttu-id="f6f7b-175">この設定を右に移動して、期限切れにならないようにエントリを構成します。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-175">Move the toggle to the right to configure the entry to never expire:</span></span> ![オンに切り替え](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="f6f7b-177">.</span><span class="sxs-lookup"><span data-stu-id="f6f7b-177">.</span></span>

   - <span data-ttu-id="f6f7b-178">**オプションのメモ**: エントリの説明テキストを入力します。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-178">**Optional note**: Enter descriptive text for the entry.</span></span>

5. <span data-ttu-id="f6f7b-179">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-179">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="f6f7b-180">セキュリティ & コンプライアンスセンターを使用して、テナントの許可/ブロックリストからエントリを削除する</span><span class="sxs-lookup"><span data-stu-id="f6f7b-180">Use the Security & Compliance Center to remove entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="f6f7b-181">[セキュリティ & コンプライアンスセンター] で、[**脅威管理** \> **ポリシー**の \> **テナントの許可/ブロックリスト**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-181">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="f6f7b-182">[ **Url** ] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-182">Select the **URLs** tab.</span></span>

3. <span data-ttu-id="f6f7b-183">削除するエントリを選択し、[削除] [削除] アイコン**をクリックし** ![ ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) ます。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-183">Select the entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="f6f7b-184">表示される警告ダイアログで、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-184">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="f6f7b-185">Exchange Online PowerShell またはスタンドアロンの EOP PowerShell を使用して、テナントの許可/ブロックリストを構成する</span><span class="sxs-lookup"><span data-stu-id="f6f7b-185">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="f6f7b-186">PowerShell を使用して、テナントの許可/ブロックリストにエントリを追加する</span><span class="sxs-lookup"><span data-stu-id="f6f7b-186">Use PowerShell to add entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="f6f7b-187">テナントの許可/ブロックリストにエントリを追加するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-187">To add entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType Url -Action <Allow | Block> -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="f6f7b-188">この例では、contoso.com およびすべてのサブドメイン (たとえば、contoso.com、www.contoso.com、および xyz.abc.contoso.com) の URL ブロックエントリを追加します。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-188">This example adds a URL block entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="f6f7b-189">ExpirationDate パラメーターまたは NoExpiration パラメーターを使用していなかったため、エントリは30日後に有効期限が切れます。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-189">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType Url -Action Block -Entries ~contoso.com
```

<span data-ttu-id="f6f7b-190">構文およびパラメーターの詳細については、「 [TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-190">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="f6f7b-191">PowerShell を使用して、テナントの許可/ブロックリストのエントリを表示する</span><span class="sxs-lookup"><span data-stu-id="f6f7b-191">Use PowerShell to view entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="f6f7b-192">テナントの許可/ブロックリストのエントリを表示するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-192">To view entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url [-Entry <URLValue>] [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration]
```

<span data-ttu-id="f6f7b-193">この例では、すべてのブロックされた Url を返します。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-193">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Action Block
```

<span data-ttu-id="f6f7b-194">構文およびパラメーターの詳細については、「 [TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-194">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="f6f7b-195">PowerShell を使用して、テナントの許可/ブロックリストのエントリを変更する</span><span class="sxs-lookup"><span data-stu-id="f6f7b-195">Use PowerShell to modify entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="f6f7b-196">URL の値自体を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-196">You can't modify the URL value itself.</span></span> <span data-ttu-id="f6f7b-197">代わりに、エントリを削除して再作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-197">Instead, you need to delete the entry and recreate it.</span></span>

<span data-ttu-id="f6f7b-198">テナントの許可/ブロックリストのエントリを変更するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-198">To modify entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN"> [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="f6f7b-199">次の使用例は、指定された項目の有効期限を変更します。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-199">This example changes the expiration date of the specified entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

<span data-ttu-id="f6f7b-200">構文およびパラメーターの詳細については、「 [TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-200">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="f6f7b-201">PowerShell を使用して、テナントの許可/ブロックリストからエントリを削除する</span><span class="sxs-lookup"><span data-stu-id="f6f7b-201">Use PowerShell to remove entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="f6f7b-202">テナントの許可/禁止リストからエントリを削除するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-202">To remove entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="f6f7b-203">この例では、指定した URL エントリをテナントの許可/禁止リストから削除します。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-203">This example removes the specified URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="f6f7b-204">構文およびパラメーターの詳細については、「 [TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-204">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="f6f7b-205">テナントの許可/ブロックリストの URL 構文</span><span class="sxs-lookup"><span data-stu-id="f6f7b-205">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="f6f7b-206">IP4v および IPv6 アドレスは許可されますが、TCP/UDP ポートは許可されません。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-206">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="f6f7b-207">ファイル名拡張子を使用することはできません (test.pdf など)。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-207">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="f6f7b-208">Unicode はサポートされていませんが、Punycode はです。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-208">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="f6f7b-209">次のすべてのステートメントが true の場合、ホスト名が許可されます。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-209">Hostnames are allowed if all of the following statements are true:</span></span>

  - <span data-ttu-id="f6f7b-210">ホスト名にはピリオドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-210">The hostname contains a period.</span></span>
  - <span data-ttu-id="f6f7b-211">ピリオドの左側には、少なくとも1つの文字があります。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-211">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="f6f7b-212">ピリオドの右側には、少なくとも2つの文字があります。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-212">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="f6f7b-213">たとえば、は許可されて `t.co` `.com` いるか、許可され `contoso.` ていません。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-213">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="f6f7b-214">サブパスは黙示的ではありません。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-214">Subpaths are not implied.</span></span>

  <span data-ttu-id="f6f7b-215">たとえば、にはを `contoso.com` 含めません `contoso.com/a` 。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-215">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="f6f7b-216">次のシナリオでは、ワイルドカード (\*) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-216">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="f6f7b-217">サブドメインを指定するには、左のワイルドカードの後にピリオドを置く必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-217">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="f6f7b-218">たとえば、 `*.contoso.com` は許可され `*contoso.com` ていません。許可されていません。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-218">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="f6f7b-219">右のワイルドカードは、スラッシュ (/) に続けてパスを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-219">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="f6f7b-220">たとえば、は許可されて `contoso.com/*` `contoso.com*` いるか、許可され `contoso.com/ab*` ていません。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-220">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="f6f7b-221">すべてのサブパスは、右のワイルドカードでは暗黙的には含まれません。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-221">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="f6f7b-222">たとえば、にはを `contoso.com/*` 含めません `contoso.com/a` 。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-222">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="f6f7b-223">`*.com*`は無効です (解決可能なドメインではなく、右のワイルドカードはスラッシュに従っていません)。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-223">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="f6f7b-224">IP アドレスにワイルドカードを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-224">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="f6f7b-225">チルダ (~) 文字は、次のシナリオで使用できます。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-225">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="f6f7b-226">左チルダは、1つのドメインとすべてのサブドメインを意味します。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-226">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="f6f7b-227">たとえば `~contoso.com` `contoso.com` 、とを含み `*.contoso.com` ます。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-227">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="f6f7b-228">`http://` `https://` Url エントリはすべてのプロトコルに適用されるため、プロトコル (たとえば、など) を含む url エントリ `ftp://` は失敗します。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-228">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="f6f7b-229">ユーザー名またはパスワードがサポートされていないか、または必要です。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-229">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="f6f7b-230">引用符 (' または ") は無効な文字です。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-230">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="f6f7b-231">可能な場合は、URL にすべてのリダイレクトを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-231">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="f6f7b-232">URL エントリのシナリオ</span><span class="sxs-lookup"><span data-stu-id="f6f7b-232">URL entry scenarios</span></span>

<span data-ttu-id="f6f7b-233">次のセクションでは、有効な URL エントリとその結果について説明します。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-233">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="f6f7b-234">シナリオ: ワイルドカードがありません</span><span class="sxs-lookup"><span data-stu-id="f6f7b-234">Scenario: No wildcards</span></span>

<span data-ttu-id="f6f7b-235">**Entry**:`contoso.com`</span><span class="sxs-lookup"><span data-stu-id="f6f7b-235">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="f6f7b-236">**Match の許可**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="f6f7b-236">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="f6f7b-237">**許可しない**:</span><span class="sxs-lookup"><span data-stu-id="f6f7b-237">**Allow not matched**:</span></span>

  - <span data-ttu-id="f6f7b-238">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="f6f7b-238">abc-contoso.com</span></span>
  - <span data-ttu-id="f6f7b-239">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="f6f7b-239">contoso.com/a</span></span>
  - <span data-ttu-id="f6f7b-240">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f6f7b-240">payroll.contoso.com</span></span>
  - <span data-ttu-id="f6f7b-241">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="f6f7b-241">test.com/contoso.com</span></span>
  - <span data-ttu-id="f6f7b-242">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="f6f7b-242">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="f6f7b-243">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f6f7b-243">www.contoso.com</span></span>
  - <span data-ttu-id="f6f7b-244">www. .com/q = a@contoso</span><span class="sxs-lookup"><span data-stu-id="f6f7b-244">www.contoso.com/q=a@contoso.com</span></span>
  
- <span data-ttu-id="f6f7b-245">**ブロック一致**:</span><span class="sxs-lookup"><span data-stu-id="f6f7b-245">**Block match**:</span></span>

  - <span data-ttu-id="f6f7b-246">contoso.com</span><span class="sxs-lookup"><span data-stu-id="f6f7b-246">contoso.com</span></span>
  - <span data-ttu-id="f6f7b-247">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="f6f7b-247">contoso.com/a</span></span>
  - <span data-ttu-id="f6f7b-248">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f6f7b-248">payroll.contoso.com</span></span>
  - <span data-ttu-id="f6f7b-249">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="f6f7b-249">test.com/contoso.com</span></span>
  - <span data-ttu-id="f6f7b-250">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="f6f7b-250">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="f6f7b-251">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f6f7b-251">www.contoso.com</span></span>
  - <span data-ttu-id="f6f7b-252">www. .com/q = a@contoso</span><span class="sxs-lookup"><span data-stu-id="f6f7b-252">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="f6f7b-253">**ブロックが一致しません**: abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="f6f7b-253">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="f6f7b-254">シナリオ: 左ワイルドカード (サブドメイン)</span><span class="sxs-lookup"><span data-stu-id="f6f7b-254">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="f6f7b-255">**Entry**:`*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="f6f7b-255">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="f6f7b-256">一致と**ブロックの一致**を**許可する**:</span><span class="sxs-lookup"><span data-stu-id="f6f7b-256">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="f6f7b-257">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f6f7b-257">www.contoso.com</span></span>
  - <span data-ttu-id="f6f7b-258">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f6f7b-258">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="f6f7b-259">[一致しない] と [**ブロックが一致**し**ません**] を許可します。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-259">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="f6f7b-260">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="f6f7b-260">123contoso.com</span></span>
  - <span data-ttu-id="f6f7b-261">contoso.com</span><span class="sxs-lookup"><span data-stu-id="f6f7b-261">contoso.com</span></span>
  - <span data-ttu-id="f6f7b-262">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="f6f7b-262">test.com/contoso.com</span></span>
  - <span data-ttu-id="f6f7b-263">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="f6f7b-263">www.contoso.com/abc</span></span>
  
#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="f6f7b-264">シナリオ: パスの上部にあるワイルドカード (右)</span><span class="sxs-lookup"><span data-stu-id="f6f7b-264">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="f6f7b-265">**Entry**:`contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="f6f7b-265">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="f6f7b-266">一致と**ブロックの一致**を**許可する**:</span><span class="sxs-lookup"><span data-stu-id="f6f7b-266">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="f6f7b-267">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="f6f7b-267">contoso.com/a/b</span></span>
  - <span data-ttu-id="f6f7b-268">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="f6f7b-268">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="f6f7b-269">contoso .com/a/? q = joe@t</span><span class="sxs-lookup"><span data-stu-id="f6f7b-269">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="f6f7b-270">[一致しない] と [**ブロックが一致**し**ません**] を許可します。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-270">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="f6f7b-271">contoso.com</span><span class="sxs-lookup"><span data-stu-id="f6f7b-271">contoso.com</span></span>
  - <span data-ttu-id="f6f7b-272">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="f6f7b-272">contoso.com/a</span></span>
  - <span data-ttu-id="f6f7b-273">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f6f7b-273">www.contoso.com</span></span>
  - <span data-ttu-id="f6f7b-274">www. .com/q = a@contoso</span><span class="sxs-lookup"><span data-stu-id="f6f7b-274">www.contoso.com/q=a@contoso.com</span></span>
  
#### <a name="scenario-left-tilde"></a><span data-ttu-id="f6f7b-275">シナリオ: 左チルダ</span><span class="sxs-lookup"><span data-stu-id="f6f7b-275">Scenario: Left tilde</span></span>

<span data-ttu-id="f6f7b-276">**Entry**:`~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="f6f7b-276">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="f6f7b-277">一致と**ブロックの一致**を**許可する**:</span><span class="sxs-lookup"><span data-stu-id="f6f7b-277">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="f6f7b-278">contoso.com</span><span class="sxs-lookup"><span data-stu-id="f6f7b-278">contoso.com</span></span>
  - <span data-ttu-id="f6f7b-279">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f6f7b-279">www.contoso.com</span></span>
  - <span data-ttu-id="f6f7b-280">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f6f7b-280">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="f6f7b-281">[一致しない] と [**ブロックが一致**し**ません**] を許可します。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-281">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="f6f7b-282">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="f6f7b-282">123contoso.com</span></span>
  - <span data-ttu-id="f6f7b-283">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="f6f7b-283">contoso.com/abc</span></span>
  - <span data-ttu-id="f6f7b-284">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="f6f7b-284">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="f6f7b-285">シナリオ: 右ワイルドカードサフィックス</span><span class="sxs-lookup"><span data-stu-id="f6f7b-285">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="f6f7b-286">**Entry**:`contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="f6f7b-286">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="f6f7b-287">一致と**ブロックの一致**を**許可する**:</span><span class="sxs-lookup"><span data-stu-id="f6f7b-287">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="f6f7b-288">contoso .com/? q = whatever@fabrikam</span><span class="sxs-lookup"><span data-stu-id="f6f7b-288">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="f6f7b-289">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="f6f7b-289">contoso.com/a</span></span>
  - <span data-ttu-id="f6f7b-290">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="f6f7b-290">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="f6f7b-291">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="f6f7b-291">contoso.com/ab</span></span>
  - <span data-ttu-id="f6f7b-292">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="f6f7b-292">contoso.com/b</span></span>
  - <span data-ttu-id="f6f7b-293">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="f6f7b-293">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="f6f7b-294">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="f6f7b-294">contoso.com/ba</span></span>

- <span data-ttu-id="f6f7b-295">**Allow not 一致**と**ブロック not 一致**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="f6f7b-295">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="f6f7b-296">シナリオ: 左ワイルドカードサブドメインと右ワイルドカードサフィックス</span><span class="sxs-lookup"><span data-stu-id="f6f7b-296">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="f6f7b-297">**Entry**:`*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="f6f7b-297">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="f6f7b-298">一致と**ブロックの一致**を**許可する**:</span><span class="sxs-lookup"><span data-stu-id="f6f7b-298">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="f6f7b-299">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="f6f7b-299">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="f6f7b-300">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="f6f7b-300">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="f6f7b-301">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="f6f7b-301">www.contoso.com/a</span></span>
  - <span data-ttu-id="f6f7b-302">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="f6f7b-302">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="f6f7b-303">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="f6f7b-303">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="f6f7b-304">**Allow not 一致**と**ブロック not 一致**: contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="f6f7b-304">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="f6f7b-305">シナリオ: 左と右のチルダ</span><span class="sxs-lookup"><span data-stu-id="f6f7b-305">Scenario: Left and right tilde</span></span>

<span data-ttu-id="f6f7b-306">**Entry**:`~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="f6f7b-306">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="f6f7b-307">一致と**ブロックの一致**を**許可する**:</span><span class="sxs-lookup"><span data-stu-id="f6f7b-307">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="f6f7b-308">contoso.com</span><span class="sxs-lookup"><span data-stu-id="f6f7b-308">contoso.com</span></span>
  - <span data-ttu-id="f6f7b-309">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="f6f7b-309">contoso.com/a</span></span>
  - <span data-ttu-id="f6f7b-310">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f6f7b-310">www.contoso.com</span></span>
  - <span data-ttu-id="f6f7b-311">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="f6f7b-311">www.contoso.com/b</span></span>
  - <span data-ttu-id="f6f7b-312">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f6f7b-312">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="f6f7b-313">[一致しない] と [**ブロックが一致**し**ません**] を許可します。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-313">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="f6f7b-314">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="f6f7b-314">123contoso.com</span></span>
  - <span data-ttu-id="f6f7b-315">contoso.org</span><span class="sxs-lookup"><span data-stu-id="f6f7b-315">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="f6f7b-316">シナリオ: IP アドレス</span><span class="sxs-lookup"><span data-stu-id="f6f7b-316">Scenario: IP address</span></span>

<span data-ttu-id="f6f7b-317">**Entry**:`1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="f6f7b-317">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="f6f7b-318">Match と**Block match**を**許可する**: 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="f6f7b-318">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="f6f7b-319">[一致しない] と [**ブロックが一致**し**ません**] を許可します。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-319">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="f6f7b-320">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="f6f7b-320">1.2.3.4/a</span></span>
  - <span data-ttu-id="f6f7b-321">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="f6f7b-321">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="f6f7b-322">右ワイルドカードを使用した IP アドレス</span><span class="sxs-lookup"><span data-stu-id="f6f7b-322">IP address with right wildcard</span></span>

<span data-ttu-id="f6f7b-323">**Entry**:`1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="f6f7b-323">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="f6f7b-324">一致と**ブロックの一致**を**許可する**:</span><span class="sxs-lookup"><span data-stu-id="f6f7b-324">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="f6f7b-325">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="f6f7b-325">1.2.3.4/b</span></span>
  - <span data-ttu-id="f6f7b-326">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="f6f7b-326">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="f6f7b-327">無効なエントリの例</span><span class="sxs-lookup"><span data-stu-id="f6f7b-327">Examples of invalid entries</span></span>

<span data-ttu-id="f6f7b-328">次のエントリは無効です。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-328">The following entries are invalid:</span></span>

- <span data-ttu-id="f6f7b-329">**ドメイン値がないか、または無効**です。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-329">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="f6f7b-330">拠点</span><span class="sxs-lookup"><span data-stu-id="f6f7b-330">contoso</span></span>
  - <span data-ttu-id="f6f7b-331">\*拠点.\*</span><span class="sxs-lookup"><span data-stu-id="f6f7b-331">\*.contoso.\*</span></span>
  - <span data-ttu-id="f6f7b-332">\*.com</span><span class="sxs-lookup"><span data-stu-id="f6f7b-332">\*.com</span></span>
  - <span data-ttu-id="f6f7b-333">\*.pdf</span><span class="sxs-lookup"><span data-stu-id="f6f7b-333">\*.pdf</span></span>

- <span data-ttu-id="f6f7b-334">**文字列の場合はワイルドカード、文字間隔は使用しませ**ん。</span><span class="sxs-lookup"><span data-stu-id="f6f7b-334">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="f6f7b-335">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="f6f7b-335">\*contoso.com</span></span>
  - <span data-ttu-id="f6f7b-336">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="f6f7b-336">contoso.com\*</span></span>
  - <span data-ttu-id="f6f7b-337">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="f6f7b-337">\*1.2.3.4</span></span>
  - <span data-ttu-id="f6f7b-338">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="f6f7b-338">1.2.3.4\*</span></span>
  - <span data-ttu-id="f6f7b-339">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="f6f7b-339">contoso.com/a\*</span></span>
  - <span data-ttu-id="f6f7b-340">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="f6f7b-340">contoso.com/ab\*</span></span>

- <span data-ttu-id="f6f7b-341">**ポートを使用した IP アドレス**:</span><span class="sxs-lookup"><span data-stu-id="f6f7b-341">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="f6f7b-342">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="f6f7b-342">contoso.com:443</span></span>
  - <span data-ttu-id="f6f7b-343">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="f6f7b-343">abc.contoso.com:25</span></span>

- <span data-ttu-id="f6f7b-344">**説明のないワイルドカード**:</span><span class="sxs-lookup"><span data-stu-id="f6f7b-344">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="f6f7b-345">\*.\*</span><span class="sxs-lookup"><span data-stu-id="f6f7b-345">\*.\*</span></span>

- <span data-ttu-id="f6f7b-346">**中央のワイルドカード**:</span><span class="sxs-lookup"><span data-stu-id="f6f7b-346">**Middle wildcards**:</span></span>

  - <span data-ttu-id="f6f7b-347">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="f6f7b-347">conto\*so.com</span></span>
  - <span data-ttu-id="f6f7b-348">~ so ~ .com</span><span class="sxs-lookup"><span data-stu-id="f6f7b-348">conto~so.com</span></span>

- <span data-ttu-id="f6f7b-349">**2文字のワイルドカード**</span><span class="sxs-lookup"><span data-stu-id="f6f7b-349">**Double wildcards**</span></span>

  - <span data-ttu-id="f6f7b-350">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="f6f7b-350">contoso.com/\*\*</span></span>
  - <span data-ttu-id="f6f7b-351">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="f6f7b-351">contoso.com/\*/\*</span></span>
