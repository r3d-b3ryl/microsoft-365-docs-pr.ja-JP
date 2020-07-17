---
title: 許可または禁止する Url とファイルをテナントの許可/ブロックリストで管理する
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
ROBOTS: NOINDEX, NOFOLLOW
description: 管理者は、セキュリティ & コンプライアンスセンターのテナントの許可/ブロックリストで URL とファイルエントリを構成する方法について説明します。
ms.openlocfilehash: 742a44c7ed63c8a3037e2ada295c94f89afa9c93
ms.sourcegitcommit: df6cc8c2eb2a65c7668f2953b0f7ec783a596d15
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/13/2020
ms.locfileid: "44726815"
---
# <a name="manage-urls-and-files-in-the-tenant-allowblock-list"></a><span data-ttu-id="94eaa-103">テナントの許可/ブロックリストで Url とファイルを管理する</span><span class="sxs-lookup"><span data-stu-id="94eaa-103">Manage URLs and files in the Tenant Allow/Block List</span></span>

> [!NOTE]
> <span data-ttu-id="94eaa-104">このトピックで説明する機能はプレビュー段階にあり、変更される可能性があり、組織によっては利用できません。</span><span class="sxs-lookup"><span data-stu-id="94eaa-104">The features described in this topic are in Preview, are subject to change, and are not available in all organizations.</span></span>

<span data-ttu-id="94eaa-105">Exchange online または exchange online メールボックスを使用しない exchange online またはスタンドアロンの Exchange Online Protection (EOP) 組織内にメールボックスを持つ Microsoft 365 組織では、EOP フィルター verdict の使用に同意しない場合があります。</span><span class="sxs-lookup"><span data-stu-id="94eaa-105">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="94eaa-106">たとえば、良好なメッセージが不良 (誤検知) としてマークされている場合や、無効なメッセージが表示される場合があります (誤検知)。</span><span class="sxs-lookup"><span data-stu-id="94eaa-106">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="94eaa-107">セキュリティ & コンプライアンスセンターのテナントの許可/禁止リストにより、Microsoft 365 filtering verdicts を手動で上書きすることができます。</span><span class="sxs-lookup"><span data-stu-id="94eaa-107">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="94eaa-108">テナントの許可/ブロックリストは、メールフローおよびユーザークリック時に使用されます。</span><span class="sxs-lookup"><span data-stu-id="94eaa-108">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="94eaa-109">テナントの許可/ブロックリストで許可またはブロックする Url とファイルを指定できます。</span><span class="sxs-lookup"><span data-stu-id="94eaa-109">You can specify URLs and files to allow or block in the Tenant Allow/Block List.</span></span>

<span data-ttu-id="94eaa-110">このトピックでは、セキュリティ & コンプライアンスセンターまたは PowerShell (exchange online にメールボックスがある Microsoft 365 組織の場合は exchange Online PowerShell、exchange online メールボックスを使用しない組織の場合は、スタンドアロン EOP PowerShell) で、テナントの許可/ブロックリストのエントリを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="94eaa-110">This topic describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="94eaa-111">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="94eaa-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="94eaa-112"><https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="94eaa-112">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="94eaa-113">[**テナントの許可/ブロックリスト**] ページに直接移動するには、を使用 <https://protection.office.com/tenantAllowBlockList> します。</span><span class="sxs-lookup"><span data-stu-id="94eaa-113">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="94eaa-114">ファイルの SHA256 ハッシュ値を使用してファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="94eaa-114">You specify files by using the SHA256 hash value of the file.</span></span> <span data-ttu-id="94eaa-115">Windows でファイルの SHA256 ハッシュ値を検索するには、コマンドプロンプトで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="94eaa-115">To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt:</span></span>

  ```dos
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  <span data-ttu-id="94eaa-116">値の例を次に示し `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` ます。</span><span class="sxs-lookup"><span data-stu-id="94eaa-116">An example value is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`.</span></span> <span data-ttu-id="94eaa-117">知覚ハッシュ (pHash) の値は使用できません。</span><span class="sxs-lookup"><span data-stu-id="94eaa-117">Perceptual hash (pHash) values are not allowed.</span></span>

- <span data-ttu-id="94eaa-118">使用可能な URL 値については、このトピックで後述する「[テナントの許可/ブロックリスト」セクションの url 構文](#url-syntax-for-the-tenant-allowblock-list)で説明されています。</span><span class="sxs-lookup"><span data-stu-id="94eaa-118">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this topic.</span></span>

- <span data-ttu-id="94eaa-119">テナントの許可/ブロックリストでは、Url に最大500エントリ、ファイルハッシュには500エントリを使用できます。</span><span class="sxs-lookup"><span data-stu-id="94eaa-119">The Tenant Allow/Block List allows a maximum of 500 entries for URLs, and 500 entries for file hashes.</span></span>

- <span data-ttu-id="94eaa-120">エントリは15分以内にアクティブである必要があります。</span><span class="sxs-lookup"><span data-stu-id="94eaa-120">An entry should be active within 15 minutes.</span></span>

- <span data-ttu-id="94eaa-121">禁止エントリは、許可エントリよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="94eaa-121">Block entries take precedence over allow entries.</span></span>

- <span data-ttu-id="94eaa-122">既定では、テナントの許可/ブロックリストのエントリは30日後に期限切れになります。</span><span class="sxs-lookup"><span data-stu-id="94eaa-122">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="94eaa-123">日付を指定するか、期限切れにならないように設定できます。</span><span class="sxs-lookup"><span data-stu-id="94eaa-123">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="94eaa-124">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="94eaa-124">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="94eaa-125">スタンドアロンの EOP PowerShell に接続するには、「 [Exchange Online Protection の powershell への接続](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="94eaa-125">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="94eaa-126">このトピックの手順を実行する前に、アクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="94eaa-126">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="94eaa-127">テナントの許可/禁止リストの値を追加および削除するには、次のいずれかの役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="94eaa-127">To add and remove values from the Tenant Allow/Block List, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="94eaa-128">[セキュリティ & コンプライアンスセンター](permissions-in-the-security-and-compliance-center.md)の**組織管理**または**セキュリティ管理者**。</span><span class="sxs-lookup"><span data-stu-id="94eaa-128">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="94eaa-129">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)での**組織の管理**または**検疫の管理**。</span><span class="sxs-lookup"><span data-stu-id="94eaa-129">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="94eaa-130">テナントの許可/禁止リストに対する読み取り専用アクセスの場合は、次のいずれかの役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="94eaa-130">For read-only access to the Tenant Allow/Block List, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="94eaa-131">[セキュリティ & コンプライアンスセンター](permissions-in-the-security-and-compliance-center.md)の**セキュリティリーダ**。</span><span class="sxs-lookup"><span data-stu-id="94eaa-131">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="94eaa-132">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)での**表示のみの組織の管理**。</span><span class="sxs-lookup"><span data-stu-id="94eaa-132">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="94eaa-133">セキュリティ & コンプライアンスセンターを使用して、テナントの許可/ブロックリストで URL エントリを作成する</span><span class="sxs-lookup"><span data-stu-id="94eaa-133">Use the Security & Compliance Center to create URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="94eaa-134">URL エントリの構文の詳細については、このトピックで後述する「[テナントの許可/ブロックリスト」セクションの url 構文](#url-syntax-for-the-tenant-allowblock-list)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="94eaa-134">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this topic.</span></span>

1. <span data-ttu-id="94eaa-135">[セキュリティ & コンプライアンスセンター] で、[**脅威管理** \> **ポリシー**の \> **テナントの許可/ブロックリスト**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="94eaa-135">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="94eaa-136">[**テナントの許可/ブロックリスト**] ページで、[ **url** ] タブが選択されていることを確認し、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94eaa-136">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Add**</span></span>

3. <span data-ttu-id="94eaa-137">表示される [**新しい url の追加**] ポップアップで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="94eaa-137">In the **Add new URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="94eaa-138">**ワイルドカードを使用して url を追加**します。1行に1つの url を入力します。最大値は20です。</span><span class="sxs-lookup"><span data-stu-id="94eaa-138">**Add URLs with wildcards**: Enter one URL per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="94eaa-139">[**ブロック/許可**]: 指定した Url を**許可**または**ブロック**するかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="94eaa-139">**Block/Allow**: Select whether you want to **Allow** or **Block** the specified URLs.</span></span>

   - <span data-ttu-id="94eaa-140">**無期限: 次**のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="94eaa-140">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="94eaa-141">設定がオフ (トグルオフ) になっていることを確認 ![ ](../../media/scc-toggle-off.png) し、 **[有効期限**] ボックスを使用して、エントリの有効期限を指定します。</span><span class="sxs-lookup"><span data-stu-id="94eaa-141">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="94eaa-142">または</span><span class="sxs-lookup"><span data-stu-id="94eaa-142">or</span></span>

     - <span data-ttu-id="94eaa-143">右にトグルを移動して、期限切れにならないようにエントリを構成します。</span><span class="sxs-lookup"><span data-stu-id="94eaa-143">Move the toggle to the right to configure the entries to never expire:</span></span> ![オンに切り替え](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="94eaa-145">.</span><span class="sxs-lookup"><span data-stu-id="94eaa-145">.</span></span>

   - <span data-ttu-id="94eaa-146">**オプションのメモ**: エントリの説明テキストを入力します。</span><span class="sxs-lookup"><span data-stu-id="94eaa-146">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="94eaa-147">完了したら、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94eaa-147">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="94eaa-148">セキュリティ & コンプライアンスセンターを使用して、テナントの許可/ブロックリストでファイルエントリを作成する</span><span class="sxs-lookup"><span data-stu-id="94eaa-148">Use the Security & Compliance Center to create file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="94eaa-149">[セキュリティ & コンプライアンスセンター] で、[**脅威管理** \> **ポリシー**の \> **テナントの許可/ブロックリスト**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="94eaa-149">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="94eaa-150">[**テナントの許可/ブロックリスト**] ページで、[**ファイル**] タブを選択し、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94eaa-150">On the **Tenant Allow/Block List** page, select **Files** tab, and then click **Add**.</span></span>

3. <span data-ttu-id="94eaa-151">表示される [**新しいファイルの追加**] ポップアップで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="94eaa-151">In the **Add new files** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="94eaa-152">**ファイルハッシュの追加**: 行ごとに1つの SHA256 ハッシュ値を入力します (最大数は 20)。</span><span class="sxs-lookup"><span data-stu-id="94eaa-152">**Add file hashes**: Enter one SHA256 hash value per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="94eaa-153">[**ブロック/許可**]: 指定したファイルを**許可**または**ブロック**するかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="94eaa-153">**Block/Allow**: Select whether you want to **Allow** or **Block** the specified files.</span></span>

   - <span data-ttu-id="94eaa-154">**無期限: 次**のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="94eaa-154">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="94eaa-155">設定がオフ (トグルオフ) になっていることを確認 ![ ](../../media/scc-toggle-off.png) し、 **[有効期限**] ボックスを使用して、エントリの有効期限を指定します。</span><span class="sxs-lookup"><span data-stu-id="94eaa-155">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="94eaa-156">または</span><span class="sxs-lookup"><span data-stu-id="94eaa-156">or</span></span>

     - <span data-ttu-id="94eaa-157">右にトグルを移動して、期限切れにならないようにエントリを構成します。</span><span class="sxs-lookup"><span data-stu-id="94eaa-157">Move the toggle to the right to configure the entries to never expire:</span></span> ![オンに切り替え](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="94eaa-159">.</span><span class="sxs-lookup"><span data-stu-id="94eaa-159">.</span></span>

   - <span data-ttu-id="94eaa-160">**オプションのメモ**: エントリの説明テキストを入力します。</span><span class="sxs-lookup"><span data-stu-id="94eaa-160">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="94eaa-161">完了したら、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94eaa-161">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="94eaa-162">セキュリティ & コンプライアンスセンターを使用して、URL およびファイルエントリをテナントの許可/ブロックリストに表示する</span><span class="sxs-lookup"><span data-stu-id="94eaa-162">Use the Security & Compliance Center to view URL and file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="94eaa-163">[セキュリティ & コンプライアンスセンター] で、[**脅威管理** \> **ポリシー**の \> **テナントの許可/ブロックリスト**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="94eaa-163">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="94eaa-164">[ **Url** ] タブまたは [**ファイル**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="94eaa-164">Select the **URLs** tab or the **Files** tab.</span></span>

<span data-ttu-id="94eaa-165">次の列見出しをクリックすると、昇順または降順で並べ替えられます。</span><span class="sxs-lookup"><span data-stu-id="94eaa-165">Click on the following column headings to sort in ascending or descending order:</span></span>

- <span data-ttu-id="94eaa-166">**値**: URL またはファイルハッシュ。</span><span class="sxs-lookup"><span data-stu-id="94eaa-166">**Value**: The URL or the file hash.</span></span>
- <span data-ttu-id="94eaa-167">**アクション**:**ブロック**または**許可**。</span><span class="sxs-lookup"><span data-stu-id="94eaa-167">**Action**: **Block** or **Allow**.</span></span>
- <span data-ttu-id="94eaa-168">**最終更新日**</span><span class="sxs-lookup"><span data-stu-id="94eaa-168">**Last updated date**</span></span>
- <span data-ttu-id="94eaa-169">**有効期限**</span><span class="sxs-lookup"><span data-stu-id="94eaa-169">**Expiration date**</span></span>
- <span data-ttu-id="94eaa-170">**注**</span><span class="sxs-lookup"><span data-stu-id="94eaa-170">**Note**</span></span>

<span data-ttu-id="94eaa-171">[**グループ化**] をクリックして、エントリを**アクション**(**ブロック**または**許可**) または**なし**とグループ化します。</span><span class="sxs-lookup"><span data-stu-id="94eaa-171">Click **Group** to group the entries by **Action** (**Block** or **Allow**) or **None**.</span></span>

<span data-ttu-id="94eaa-172">[**検索**] をクリックし、URL またはファイル値の全体または一部を入力してから、enter キーを押して特定の値を検索します。</span><span class="sxs-lookup"><span data-stu-id="94eaa-172">Click **Search**, enter all or part of a URL or file value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="94eaa-173">完了したら、[検索のクリア検索の**クリア**] をクリックし ![ ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) ます。</span><span class="sxs-lookup"><span data-stu-id="94eaa-173">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

<span data-ttu-id="94eaa-174">[**フィルター**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94eaa-174">Click **Filter**.</span></span> <span data-ttu-id="94eaa-175">表示される**フィルター**のポップアップで、次のいずれかの設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="94eaa-175">In the **Filter** flyout that appears, configure any of the following settings:</span></span>

- <span data-ttu-id="94eaa-176">**アクション**: **Allow**、 **Block** 、または both を選択します。</span><span class="sxs-lookup"><span data-stu-id="94eaa-176">**Action**: Select **Allow**, **Block** or both.</span></span>

- <span data-ttu-id="94eaa-177">**無期限: オフ**(オフ ![ ](../../media/scc-toggle-off.png) ) またはオン ( ![ トグルオン ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) )。</span><span class="sxs-lookup"><span data-stu-id="94eaa-177">**Never expire**: Select off (![Toggle off](../../media/scc-toggle-off.png)) or on (![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)).</span></span>

- <span data-ttu-id="94eaa-178">**最終更新**日時: 開始日 (開始**日)、** 終了日 (**To**)、またはその両方を選択します。</span><span class="sxs-lookup"><span data-stu-id="94eaa-178">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span></span>

- <span data-ttu-id="94eaa-179">[**有効期限**]: 開始日 (開始**日)、** 終了日 (**To**)、またはその両方を選択します。</span><span class="sxs-lookup"><span data-stu-id="94eaa-179">**Expiration date**: Select a start date (**From**), an end date (**To**) or both.</span></span>

<span data-ttu-id="94eaa-180">完了したら、[**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94eaa-180">When you're finished, click **Apply**.</span></span>

<span data-ttu-id="94eaa-181">既存のフィルターをクリアするには、[**フィルター**] をクリックし、表示される**フィルター**のポップアップで [**フィルターのクリア**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94eaa-181">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="94eaa-182">セキュリティ & コンプライアンスセンターを使用して、テナントの許可/ブロックリスト内の URL とファイルエントリを変更する</span><span class="sxs-lookup"><span data-stu-id="94eaa-182">Use the Security & Compliance Center to modify URL and file entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="94eaa-183">URL またはファイルの値自体を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="94eaa-183">You can't modify the URL or file value itself.</span></span> <span data-ttu-id="94eaa-184">代わりに、エントリを削除して再作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="94eaa-184">Instead, you need to delete the entry and recreate it.</span></span>

1. <span data-ttu-id="94eaa-185">[セキュリティ & コンプライアンスセンター] で、[**脅威管理** \> **ポリシー**の \> **テナントの許可/ブロックリスト**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="94eaa-185">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="94eaa-186">[ **Url** ] タブまたは [**ファイル**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="94eaa-186">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="94eaa-187">変更するエントリを選択し、[編集アイコンの**編集**] をクリックし ![ ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) ます。</span><span class="sxs-lookup"><span data-stu-id="94eaa-187">Select the entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span>

4. <span data-ttu-id="94eaa-188">表示されたポップアップで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="94eaa-188">In the flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="94eaa-189">[**ブロック/許可**]: [**許可**] または [**ブロック**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="94eaa-189">**Block/Allow**: Select **Allow** or **Block**.</span></span>

   - <span data-ttu-id="94eaa-190">**無期限: 次**のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="94eaa-190">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="94eaa-191">設定がオフ (トグルオフ) になっていることを確認 ![ ](../../media/scc-toggle-off.png) し、 **[有効期限**] ボックスを使用して、エントリの有効期限を指定します。</span><span class="sxs-lookup"><span data-stu-id="94eaa-191">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entry.</span></span>

     <span data-ttu-id="94eaa-192">または</span><span class="sxs-lookup"><span data-stu-id="94eaa-192">or</span></span>

     - <span data-ttu-id="94eaa-193">この設定を右に移動して、期限切れにならないようにエントリを構成します。</span><span class="sxs-lookup"><span data-stu-id="94eaa-193">Move the toggle to the right to configure the entry to never expire:</span></span> ![オンに切り替え](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="94eaa-195">.</span><span class="sxs-lookup"><span data-stu-id="94eaa-195">.</span></span>

   - <span data-ttu-id="94eaa-196">**オプションのメモ**: エントリの説明テキストを入力します。</span><span class="sxs-lookup"><span data-stu-id="94eaa-196">**Optional note**: Enter descriptive text for the entry.</span></span>

5. <span data-ttu-id="94eaa-197">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94eaa-197">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-url-and-file-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="94eaa-198">セキュリティ & コンプライアンスセンターを使用して、URL とファイルのエントリをテナントの許可/禁止リストから削除する</span><span class="sxs-lookup"><span data-stu-id="94eaa-198">Use the Security & Compliance Center to remove URL and file entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="94eaa-199">[セキュリティ & コンプライアンスセンター] で、[**脅威管理** \> **ポリシー**の \> **テナントの許可/ブロックリスト**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="94eaa-199">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="94eaa-200">[ **Url** ] タブまたは [**ファイル**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="94eaa-200">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="94eaa-201">削除するエントリを選択し、[削除] [削除] アイコン**をクリックし** ![ ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) ます。</span><span class="sxs-lookup"><span data-stu-id="94eaa-201">Select the entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="94eaa-202">表示される警告ダイアログで、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94eaa-202">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="94eaa-203">Exchange Online PowerShell またはスタンドアロンの EOP PowerShell を使用して、テナントの許可/ブロックリストを構成する</span><span class="sxs-lookup"><span data-stu-id="94eaa-203">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="94eaa-204">PowerShell を使用して、テナントの許可/ブロックリストに URL とファイルエントリを追加する</span><span class="sxs-lookup"><span data-stu-id="94eaa-204">Use PowerShell to add URL and file entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="94eaa-205">テナントの許可/ブロックリストに URL とファイルエントリを追加するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="94eaa-205">To add URL and file entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType <Url | FileHash> -Action <Allow | Block> -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="94eaa-206">この例では、contoso.com およびすべてのサブドメイン (たとえば、contoso.com、www.contoso.com、および xyz.abc.contoso.com) の URL ブロックエントリを追加します。</span><span class="sxs-lookup"><span data-stu-id="94eaa-206">This example adds a URL block entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="94eaa-207">ExpirationDate パラメーターまたは NoExpiration パラメーターを使用していなかったため、エントリは30日後に有効期限が切れます。</span><span class="sxs-lookup"><span data-stu-id="94eaa-207">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType Url -Action Block -Entries ~contoso.com
```

```powershell
New-TenantAllowBlockListItem -ListType FileHash -Action Allow -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

<span data-ttu-id="94eaa-208">この例では、指定したファイルの有効期限が切れないファイルの許可エントリを追加します。</span><span class="sxs-lookup"><span data-stu-id="94eaa-208">This example adds a file allow entry for the specified files that never expires.</span></span>

<span data-ttu-id="94eaa-209">構文およびパラメーターの詳細については、「 [TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="94eaa-209">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="94eaa-210">PowerShell を使用して、テナントの許可/ブロックリスト内の URL とファイルエントリを表示する</span><span class="sxs-lookup"><span data-stu-id="94eaa-210">Use PowerShell to view URL and file entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="94eaa-211">テナントの許可/ブロックの一覧で URL とファイルエントリを表示するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="94eaa-211">To view URL and file entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType <Url | FileHash> [-Entry <URLValue | FileHashValue>] [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration]
```

<span data-ttu-id="94eaa-212">この例では、すべてのブロックされた Url を返します。</span><span class="sxs-lookup"><span data-stu-id="94eaa-212">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Action Block
```

<span data-ttu-id="94eaa-213">この例では、指定したファイルハッシュ値に関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="94eaa-213">This example returns information for the specified file hash value.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

<span data-ttu-id="94eaa-214">構文およびパラメーターの詳細については、「 [TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="94eaa-214">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="94eaa-215">PowerShell を使用して、テナントの許可/ブロックリスト内の URL とファイルエントリを変更する</span><span class="sxs-lookup"><span data-stu-id="94eaa-215">Use PowerShell to modify URL and file entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="94eaa-216">URL またはファイルの値自体を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="94eaa-216">You can't modify the URL or file value itself.</span></span> <span data-ttu-id="94eaa-217">代わりに、エントリを削除して再作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="94eaa-217">Instead, you need to delete the entry and recreate it.</span></span>

<span data-ttu-id="94eaa-218">テナントの許可/ブロックの一覧で URL とファイルエントリを変更するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="94eaa-218">To modify URL and file entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN"> [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="94eaa-219">次の使用例は、指定された項目の有効期限を変更します。</span><span class="sxs-lookup"><span data-stu-id="94eaa-219">This example changes the expiration date of the specified entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

<span data-ttu-id="94eaa-220">構文およびパラメーターの詳細については、「 [TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="94eaa-220">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-url-and-file-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="94eaa-221">PowerShell を使用して、テナントの許可/ブロックリストから URL とファイルエントリを削除する</span><span class="sxs-lookup"><span data-stu-id="94eaa-221">Use PowerShell to remove URL and file entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="94eaa-222">URL とファイルエントリをテナントの許可/禁止リストから削除するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="94eaa-222">To remove URL and file entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="94eaa-223">この例では、指定した URL エントリをテナントの許可/禁止リストから削除します。</span><span class="sxs-lookup"><span data-stu-id="94eaa-223">This example removes the specified URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="94eaa-224">構文およびパラメーターの詳細については、「 [TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="94eaa-224">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="94eaa-225">テナントの許可/ブロックリストの URL 構文</span><span class="sxs-lookup"><span data-stu-id="94eaa-225">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="94eaa-226">IP4v および IPv6 アドレスは許可されますが、TCP/UDP ポートは許可されません。</span><span class="sxs-lookup"><span data-stu-id="94eaa-226">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="94eaa-227">ファイル名拡張子を使用することはできません (test.pdf など)。</span><span class="sxs-lookup"><span data-stu-id="94eaa-227">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="94eaa-228">Unicode はサポートされていませんが、Punycode はです。</span><span class="sxs-lookup"><span data-stu-id="94eaa-228">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="94eaa-229">次のすべてのステートメントが true の場合、ホスト名が許可されます。</span><span class="sxs-lookup"><span data-stu-id="94eaa-229">Hostnames are allowed if all of the following statements are true:</span></span>

  - <span data-ttu-id="94eaa-230">ホスト名にはピリオドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="94eaa-230">The hostname contains a period.</span></span>
  - <span data-ttu-id="94eaa-231">ピリオドの左側には、少なくとも1つの文字があります。</span><span class="sxs-lookup"><span data-stu-id="94eaa-231">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="94eaa-232">ピリオドの右側には、少なくとも2つの文字があります。</span><span class="sxs-lookup"><span data-stu-id="94eaa-232">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="94eaa-233">たとえば、は許可されて `t.co` `.com` いるか、許可され `contoso.` ていません。</span><span class="sxs-lookup"><span data-stu-id="94eaa-233">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="94eaa-234">サブパスは黙示的ではありません。</span><span class="sxs-lookup"><span data-stu-id="94eaa-234">Subpaths are not implied.</span></span>

  <span data-ttu-id="94eaa-235">たとえば、にはを `contoso.com` 含めません `contoso.com/a` 。</span><span class="sxs-lookup"><span data-stu-id="94eaa-235">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="94eaa-236">次のシナリオでは、ワイルドカード (\*) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="94eaa-236">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="94eaa-237">サブドメインを指定するには、左のワイルドカードの後にピリオドを置く必要があります。</span><span class="sxs-lookup"><span data-stu-id="94eaa-237">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="94eaa-238">たとえば、 `*.contoso.com` は許可され `*contoso.com` ていません。許可されていません。</span><span class="sxs-lookup"><span data-stu-id="94eaa-238">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="94eaa-239">右のワイルドカードは、スラッシュ (/) に続けてパスを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="94eaa-239">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="94eaa-240">たとえば、は許可されて `contoso.com/*` `contoso.com*` いるか、許可され `contoso.com/ab*` ていません。</span><span class="sxs-lookup"><span data-stu-id="94eaa-240">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="94eaa-241">すべてのサブパスは、右のワイルドカードでは暗黙的には含まれません。</span><span class="sxs-lookup"><span data-stu-id="94eaa-241">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="94eaa-242">たとえば、にはを `contoso.com/*` 含めません `contoso.com/a` 。</span><span class="sxs-lookup"><span data-stu-id="94eaa-242">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="94eaa-243">`*.com*`は無効です (解決可能なドメインではなく、右のワイルドカードはスラッシュに従っていません)。</span><span class="sxs-lookup"><span data-stu-id="94eaa-243">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="94eaa-244">IP アドレスにワイルドカードを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="94eaa-244">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="94eaa-245">チルダ (~) 文字は、次のシナリオで使用できます。</span><span class="sxs-lookup"><span data-stu-id="94eaa-245">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="94eaa-246">左チルダは、1つのドメインとすべてのサブドメインを意味します。</span><span class="sxs-lookup"><span data-stu-id="94eaa-246">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="94eaa-247">たとえば `~contoso.com` `contoso.com` 、とを含み `*.contoso.com` ます。</span><span class="sxs-lookup"><span data-stu-id="94eaa-247">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="94eaa-248">`http://` `https://` Url エントリはすべてのプロトコルに適用されるため、プロトコル (たとえば、など) を含む url エントリ `ftp://` は失敗します。</span><span class="sxs-lookup"><span data-stu-id="94eaa-248">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="94eaa-249">ユーザー名またはパスワードがサポートされていないか、または必要です。</span><span class="sxs-lookup"><span data-stu-id="94eaa-249">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="94eaa-250">引用符 (' または ") は無効な文字です。</span><span class="sxs-lookup"><span data-stu-id="94eaa-250">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="94eaa-251">可能な場合は、URL にすべてのリダイレクトを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="94eaa-251">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="94eaa-252">URL エントリのシナリオ</span><span class="sxs-lookup"><span data-stu-id="94eaa-252">URL entry scenarios</span></span>

<span data-ttu-id="94eaa-253">次のセクションでは、有効な URL エントリとその結果について説明します。</span><span class="sxs-lookup"><span data-stu-id="94eaa-253">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="94eaa-254">シナリオ: ワイルドカードがありません</span><span class="sxs-lookup"><span data-stu-id="94eaa-254">Scenario: No wildcards</span></span>

<span data-ttu-id="94eaa-255">**Entry**:`contoso.com`</span><span class="sxs-lookup"><span data-stu-id="94eaa-255">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="94eaa-256">**Match の許可**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="94eaa-256">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="94eaa-257">**許可しない**:</span><span class="sxs-lookup"><span data-stu-id="94eaa-257">**Allow not matched**:</span></span>

  - <span data-ttu-id="94eaa-258">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="94eaa-258">abc-contoso.com</span></span>
  - <span data-ttu-id="94eaa-259">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="94eaa-259">contoso.com/a</span></span>
  - <span data-ttu-id="94eaa-260">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="94eaa-260">payroll.contoso.com</span></span>
  - <span data-ttu-id="94eaa-261">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="94eaa-261">test.com/contoso.com</span></span>
  - <span data-ttu-id="94eaa-262">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="94eaa-262">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="94eaa-263">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="94eaa-263">www.contoso.com</span></span>
  - <span data-ttu-id="94eaa-264">www. .com/q = a@contoso</span><span class="sxs-lookup"><span data-stu-id="94eaa-264">www.contoso.com/q=a@contoso.com</span></span>
  
- <span data-ttu-id="94eaa-265">**ブロック一致**:</span><span class="sxs-lookup"><span data-stu-id="94eaa-265">**Block match**:</span></span>

  - <span data-ttu-id="94eaa-266">contoso.com</span><span class="sxs-lookup"><span data-stu-id="94eaa-266">contoso.com</span></span>
  - <span data-ttu-id="94eaa-267">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="94eaa-267">contoso.com/a</span></span>
  - <span data-ttu-id="94eaa-268">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="94eaa-268">payroll.contoso.com</span></span>
  - <span data-ttu-id="94eaa-269">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="94eaa-269">test.com/contoso.com</span></span>
  - <span data-ttu-id="94eaa-270">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="94eaa-270">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="94eaa-271">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="94eaa-271">www.contoso.com</span></span>
  - <span data-ttu-id="94eaa-272">www. .com/q = a@contoso</span><span class="sxs-lookup"><span data-stu-id="94eaa-272">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="94eaa-273">**ブロックが一致しません**: abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="94eaa-273">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="94eaa-274">シナリオ: 左ワイルドカード (サブドメイン)</span><span class="sxs-lookup"><span data-stu-id="94eaa-274">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="94eaa-275">**Entry**:`*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="94eaa-275">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="94eaa-276">一致と**ブロックの一致**を**許可する**:</span><span class="sxs-lookup"><span data-stu-id="94eaa-276">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="94eaa-277">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="94eaa-277">www.contoso.com</span></span>
  - <span data-ttu-id="94eaa-278">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="94eaa-278">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="94eaa-279">[一致しない] と [**ブロックが一致**し**ません**] を許可します。</span><span class="sxs-lookup"><span data-stu-id="94eaa-279">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="94eaa-280">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="94eaa-280">123contoso.com</span></span>
  - <span data-ttu-id="94eaa-281">contoso.com</span><span class="sxs-lookup"><span data-stu-id="94eaa-281">contoso.com</span></span>
  - <span data-ttu-id="94eaa-282">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="94eaa-282">test.com/contoso.com</span></span>
  - <span data-ttu-id="94eaa-283">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="94eaa-283">www.contoso.com/abc</span></span>
  
#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="94eaa-284">シナリオ: パスの上部にあるワイルドカード (右)</span><span class="sxs-lookup"><span data-stu-id="94eaa-284">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="94eaa-285">**Entry**:`contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="94eaa-285">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="94eaa-286">一致と**ブロックの一致**を**許可する**:</span><span class="sxs-lookup"><span data-stu-id="94eaa-286">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="94eaa-287">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="94eaa-287">contoso.com/a/b</span></span>
  - <span data-ttu-id="94eaa-288">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="94eaa-288">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="94eaa-289">contoso .com/a/? q = joe@t</span><span class="sxs-lookup"><span data-stu-id="94eaa-289">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="94eaa-290">[一致しない] と [**ブロックが一致**し**ません**] を許可します。</span><span class="sxs-lookup"><span data-stu-id="94eaa-290">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="94eaa-291">contoso.com</span><span class="sxs-lookup"><span data-stu-id="94eaa-291">contoso.com</span></span>
  - <span data-ttu-id="94eaa-292">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="94eaa-292">contoso.com/a</span></span>
  - <span data-ttu-id="94eaa-293">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="94eaa-293">www.contoso.com</span></span>
  - <span data-ttu-id="94eaa-294">www. .com/q = a@contoso</span><span class="sxs-lookup"><span data-stu-id="94eaa-294">www.contoso.com/q=a@contoso.com</span></span>
  
#### <a name="scenario-left-tilde"></a><span data-ttu-id="94eaa-295">シナリオ: 左チルダ</span><span class="sxs-lookup"><span data-stu-id="94eaa-295">Scenario: Left tilde</span></span>

<span data-ttu-id="94eaa-296">**Entry**:`~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="94eaa-296">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="94eaa-297">一致と**ブロックの一致**を**許可する**:</span><span class="sxs-lookup"><span data-stu-id="94eaa-297">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="94eaa-298">contoso.com</span><span class="sxs-lookup"><span data-stu-id="94eaa-298">contoso.com</span></span>
  - <span data-ttu-id="94eaa-299">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="94eaa-299">www.contoso.com</span></span>
  - <span data-ttu-id="94eaa-300">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="94eaa-300">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="94eaa-301">[一致しない] と [**ブロックが一致**し**ません**] を許可します。</span><span class="sxs-lookup"><span data-stu-id="94eaa-301">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="94eaa-302">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="94eaa-302">123contoso.com</span></span>
  - <span data-ttu-id="94eaa-303">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="94eaa-303">contoso.com/abc</span></span>
  - <span data-ttu-id="94eaa-304">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="94eaa-304">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="94eaa-305">シナリオ: 右ワイルドカードサフィックス</span><span class="sxs-lookup"><span data-stu-id="94eaa-305">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="94eaa-306">**Entry**:`contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="94eaa-306">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="94eaa-307">一致と**ブロックの一致**を**許可する**:</span><span class="sxs-lookup"><span data-stu-id="94eaa-307">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="94eaa-308">contoso .com/? q = whatever@fabrikam</span><span class="sxs-lookup"><span data-stu-id="94eaa-308">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="94eaa-309">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="94eaa-309">contoso.com/a</span></span>
  - <span data-ttu-id="94eaa-310">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="94eaa-310">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="94eaa-311">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="94eaa-311">contoso.com/ab</span></span>
  - <span data-ttu-id="94eaa-312">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="94eaa-312">contoso.com/b</span></span>
  - <span data-ttu-id="94eaa-313">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="94eaa-313">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="94eaa-314">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="94eaa-314">contoso.com/ba</span></span>

- <span data-ttu-id="94eaa-315">**Allow not 一致**と**ブロック not 一致**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="94eaa-315">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="94eaa-316">シナリオ: 左ワイルドカードサブドメインと右ワイルドカードサフィックス</span><span class="sxs-lookup"><span data-stu-id="94eaa-316">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="94eaa-317">**Entry**:`*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="94eaa-317">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="94eaa-318">一致と**ブロックの一致**を**許可する**:</span><span class="sxs-lookup"><span data-stu-id="94eaa-318">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="94eaa-319">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="94eaa-319">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="94eaa-320">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="94eaa-320">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="94eaa-321">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="94eaa-321">www.contoso.com/a</span></span>
  - <span data-ttu-id="94eaa-322">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="94eaa-322">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="94eaa-323">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="94eaa-323">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="94eaa-324">**Allow not 一致**と**ブロック not 一致**: contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="94eaa-324">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="94eaa-325">シナリオ: 左と右のチルダ</span><span class="sxs-lookup"><span data-stu-id="94eaa-325">Scenario: Left and right tilde</span></span>

<span data-ttu-id="94eaa-326">**Entry**:`~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="94eaa-326">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="94eaa-327">一致と**ブロックの一致**を**許可する**:</span><span class="sxs-lookup"><span data-stu-id="94eaa-327">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="94eaa-328">contoso.com</span><span class="sxs-lookup"><span data-stu-id="94eaa-328">contoso.com</span></span>
  - <span data-ttu-id="94eaa-329">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="94eaa-329">contoso.com/a</span></span>
  - <span data-ttu-id="94eaa-330">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="94eaa-330">www.contoso.com</span></span>
  - <span data-ttu-id="94eaa-331">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="94eaa-331">www.contoso.com/b</span></span>
  - <span data-ttu-id="94eaa-332">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="94eaa-332">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="94eaa-333">[一致しない] と [**ブロックが一致**し**ません**] を許可します。</span><span class="sxs-lookup"><span data-stu-id="94eaa-333">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="94eaa-334">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="94eaa-334">123contoso.com</span></span>
  - <span data-ttu-id="94eaa-335">contoso.org</span><span class="sxs-lookup"><span data-stu-id="94eaa-335">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="94eaa-336">シナリオ: IP アドレス</span><span class="sxs-lookup"><span data-stu-id="94eaa-336">Scenario: IP address</span></span>

<span data-ttu-id="94eaa-337">**Entry**:`1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="94eaa-337">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="94eaa-338">Match と**Block match**を**許可する**: 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="94eaa-338">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="94eaa-339">[一致しない] と [**ブロックが一致**し**ません**] を許可します。</span><span class="sxs-lookup"><span data-stu-id="94eaa-339">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="94eaa-340">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="94eaa-340">1.2.3.4/a</span></span>
  - <span data-ttu-id="94eaa-341">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="94eaa-341">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="94eaa-342">右ワイルドカードを使用した IP アドレス</span><span class="sxs-lookup"><span data-stu-id="94eaa-342">IP address with right wildcard</span></span>

<span data-ttu-id="94eaa-343">**Entry**:`1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="94eaa-343">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="94eaa-344">一致と**ブロックの一致**を**許可する**:</span><span class="sxs-lookup"><span data-stu-id="94eaa-344">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="94eaa-345">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="94eaa-345">1.2.3.4/b</span></span>
  - <span data-ttu-id="94eaa-346">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="94eaa-346">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="94eaa-347">無効なエントリの例</span><span class="sxs-lookup"><span data-stu-id="94eaa-347">Examples of invalid entries</span></span>

<span data-ttu-id="94eaa-348">次のエントリは無効です。</span><span class="sxs-lookup"><span data-stu-id="94eaa-348">The following entries are invalid:</span></span>

- <span data-ttu-id="94eaa-349">**ドメイン値がないか、または無効**です。</span><span class="sxs-lookup"><span data-stu-id="94eaa-349">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="94eaa-350">拠点</span><span class="sxs-lookup"><span data-stu-id="94eaa-350">contoso</span></span>
  - <span data-ttu-id="94eaa-351">\*拠点.\*</span><span class="sxs-lookup"><span data-stu-id="94eaa-351">\*.contoso.\*</span></span>
  - <span data-ttu-id="94eaa-352">\*.com</span><span class="sxs-lookup"><span data-stu-id="94eaa-352">\*.com</span></span>
  - <span data-ttu-id="94eaa-353">\*.pdf</span><span class="sxs-lookup"><span data-stu-id="94eaa-353">\*.pdf</span></span>

- <span data-ttu-id="94eaa-354">**文字列の場合はワイルドカード、文字間隔は使用しませ**ん。</span><span class="sxs-lookup"><span data-stu-id="94eaa-354">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="94eaa-355">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="94eaa-355">\*contoso.com</span></span>
  - <span data-ttu-id="94eaa-356">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="94eaa-356">contoso.com\*</span></span>
  - <span data-ttu-id="94eaa-357">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="94eaa-357">\*1.2.3.4</span></span>
  - <span data-ttu-id="94eaa-358">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="94eaa-358">1.2.3.4\*</span></span>
  - <span data-ttu-id="94eaa-359">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="94eaa-359">contoso.com/a\*</span></span>
  - <span data-ttu-id="94eaa-360">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="94eaa-360">contoso.com/ab\*</span></span>

- <span data-ttu-id="94eaa-361">**ポートを使用した IP アドレス**:</span><span class="sxs-lookup"><span data-stu-id="94eaa-361">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="94eaa-362">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="94eaa-362">contoso.com:443</span></span>
  - <span data-ttu-id="94eaa-363">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="94eaa-363">abc.contoso.com:25</span></span>

- <span data-ttu-id="94eaa-364">**説明のないワイルドカード**:</span><span class="sxs-lookup"><span data-stu-id="94eaa-364">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="94eaa-365">\*.\*</span><span class="sxs-lookup"><span data-stu-id="94eaa-365">\*.\*</span></span>

- <span data-ttu-id="94eaa-366">**中央のワイルドカード**:</span><span class="sxs-lookup"><span data-stu-id="94eaa-366">**Middle wildcards**:</span></span>

  - <span data-ttu-id="94eaa-367">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="94eaa-367">conto\*so.com</span></span>
  - <span data-ttu-id="94eaa-368">~ so ~ .com</span><span class="sxs-lookup"><span data-stu-id="94eaa-368">conto~so.com</span></span>

- <span data-ttu-id="94eaa-369">**2文字のワイルドカード**</span><span class="sxs-lookup"><span data-stu-id="94eaa-369">**Double wildcards**</span></span>

  - <span data-ttu-id="94eaa-370">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="94eaa-370">contoso.com/\*\*</span></span>
  - <span data-ttu-id="94eaa-371">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="94eaa-371">contoso.com/\*/\*</span></span>
