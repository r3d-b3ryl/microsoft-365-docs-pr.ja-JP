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
ms.openlocfilehash: b3a25458bbde2b3a78cfecc60ccb75fe298013f7
ms.sourcegitcommit: 6746fae2f68400fd985711b1945b66766d2a59a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2020
ms.locfileid: "44419270"
---
# <a name="manage-urls-and-files-in-the-tenant-allowblock-list"></a><span data-ttu-id="39a08-103">テナントの許可/ブロックリストで Url とファイルを管理する</span><span class="sxs-lookup"><span data-stu-id="39a08-103">Manage URLs and files in the Tenant Allow/Block List</span></span>

> [!NOTE]
> <span data-ttu-id="39a08-104">このトピックで説明する機能はプレビュー段階にあり、変更される可能性があり、組織によっては利用できません。</span><span class="sxs-lookup"><span data-stu-id="39a08-104">The features described in this topic are in Preview, are subject to change, and are not available in all organizations.</span></span>

<span data-ttu-id="39a08-105">Exchange online または exchange online メールボックスを使用しない exchange online またはスタンドアロンの Exchange Online Protection (EOP) 組織内にメールボックスを持つ Microsoft 365 組織では、EOP フィルター verdict の使用に同意しない場合があります。</span><span class="sxs-lookup"><span data-stu-id="39a08-105">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="39a08-106">たとえば、良好なメッセージが不良 (誤検知) としてマークされている場合や、無効なメッセージが表示される場合があります (誤検知)。</span><span class="sxs-lookup"><span data-stu-id="39a08-106">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="39a08-107">セキュリティ & コンプライアンスセンターのテナントの許可/禁止リストにより、Microsoft 365 filtering verdicts を手動で上書きすることができます。</span><span class="sxs-lookup"><span data-stu-id="39a08-107">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="39a08-108">テナントの許可/ブロックリストは、メールフローおよびユーザークリック時に使用されます。</span><span class="sxs-lookup"><span data-stu-id="39a08-108">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="39a08-109">テナントの許可/ブロックリストで許可またはブロックする Url とファイルを指定できます。</span><span class="sxs-lookup"><span data-stu-id="39a08-109">You can specify URLs and files to allow or block in the Tenant Allow/Block List.</span></span>

<span data-ttu-id="39a08-110">このトピックでは、セキュリティ & コンプライアンスセンターまたは PowerShell (exchange online にメールボックスがある Microsoft 365 組織の場合は exchange Online PowerShell、exchange online メールボックスを使用しない組織の場合は、スタンドアロン EOP PowerShell) で、テナントの許可/ブロックリストのエントリを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="39a08-110">This topic describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="39a08-111">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="39a08-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="39a08-112"><https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="39a08-112">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="39a08-113">[**テナントの許可/ブロックリスト**] ページに直接移動するには、を使用 <https://protection.office.com/tenantAllowBlockList> します。</span><span class="sxs-lookup"><span data-stu-id="39a08-113">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="39a08-114">ファイルの SHA256 ハッシュ値を使用してファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="39a08-114">You specify files by using the SHA256 hash value of the file.</span></span> <span data-ttu-id="39a08-115">Windows でファイルの SHA256 ハッシュ値を検索するには、コマンドプロンプトで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="39a08-115">To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt:</span></span>

  ```dos
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  <span data-ttu-id="39a08-116">値の例を次に示し `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` ます。</span><span class="sxs-lookup"><span data-stu-id="39a08-116">An example value is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`.</span></span> <span data-ttu-id="39a08-117">知覚ハッシュ (pHash) の値は使用できません。</span><span class="sxs-lookup"><span data-stu-id="39a08-117">Perceptual hash (pHash) values are not allowed.</span></span>

- <span data-ttu-id="39a08-118">使用可能な URL 値については、このトピックで後述する「[テナントの許可/ブロックリスト」セクションの url 構文](#url-syntax-for-the-tenant-allowblock-list)で説明されています。</span><span class="sxs-lookup"><span data-stu-id="39a08-118">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this topic.</span></span>

- <span data-ttu-id="39a08-119">テナントの許可/ブロックリストでは、Url に最大500エントリ、ファイルハッシュには500エントリを使用できます。</span><span class="sxs-lookup"><span data-stu-id="39a08-119">The Tenant Allow/Block List allows a maximum of 500 entries for URLs, and 500 entries for file hashes.</span></span>

- <span data-ttu-id="39a08-120">エントリは15分以内にアクティブである必要があります。</span><span class="sxs-lookup"><span data-stu-id="39a08-120">An entry should be active within 15 minutes.</span></span>

- <span data-ttu-id="39a08-121">禁止エントリは、許可エントリよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="39a08-121">Block entries take precedence over allow entries.</span></span>

- <span data-ttu-id="39a08-122">既定では、テナントの許可/ブロックリストのエントリは30日後に期限切れになります。</span><span class="sxs-lookup"><span data-stu-id="39a08-122">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="39a08-123">日付を指定するか、期限切れにならないように設定できます。</span><span class="sxs-lookup"><span data-stu-id="39a08-123">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="39a08-124">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="39a08-124">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="39a08-125">スタンドアロンの EOP PowerShell に接続するには、「 [Exchange Online Protection の powershell への接続](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="39a08-125">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="39a08-126">これらの手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="39a08-126">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="39a08-127">テナントの許可/禁止リストに値を追加したり、削除したりするには、**組織の管理**または**セキュリティ管理者**の役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="39a08-127">To add and remove values from the Tenant Allow/Block List, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="39a08-128">テナントの許可/禁止リストに対する読み取り専用アクセスの場合は、**セキュリティリーダー**役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="39a08-128">For read-only access to the Tenant Allow/Block List, you need to be a member of the **Security Reader** role group.</span></span> <span data-ttu-id="39a08-129">セキュリティ/コンプライアンス センターの役割グループの詳細については、「[セキュリティ/コンプライアンス センターでのアクセス許可](permissions-in-the-security-and-compliance-center.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="39a08-129">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="39a08-130">セキュリティ & コンプライアンスセンターを使用して、テナントの許可/ブロックリストで URL エントリを作成する</span><span class="sxs-lookup"><span data-stu-id="39a08-130">Use the Security & Compliance Center to create URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="39a08-131">URL エントリの構文の詳細については、このトピックで後述する「[テナントの許可/ブロックリスト」セクションの url 構文](#url-syntax-for-the-tenant-allowblock-list)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="39a08-131">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this topic.</span></span>

1. <span data-ttu-id="39a08-132">[セキュリティ & コンプライアンスセンター] で、[**脅威管理** \> **ポリシー**の \> **テナントの許可/ブロックリスト**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="39a08-132">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="39a08-133">[**テナントの許可/ブロックリスト**] ページで、[ **url** ] タブが選択されていることを確認し、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="39a08-133">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Add**</span></span>

3. <span data-ttu-id="39a08-134">表示される [**新しい url の追加**] ポップアップで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="39a08-134">In the **Add new URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="39a08-135">**ワイルドカードを使用して url を追加**します。1行に1つの url を入力します。最大値は20です。</span><span class="sxs-lookup"><span data-stu-id="39a08-135">**Add URLs with wildcards**: Enter one URL per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="39a08-136">[**ブロック/許可**]: 指定した Url を**許可**または**ブロック**するかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="39a08-136">**Block/Allow**: Select whether you want to **Allow** or **Block** the specified URLs.</span></span>

   - <span data-ttu-id="39a08-137">**無期限: 次**のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="39a08-137">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="39a08-138">設定がオフ (トグルオフ) になっていることを確認 ![ ](../../media/scc-toggle-off.png) し、 **[有効期限**] ボックスを使用して、エントリの有効期限を指定します。</span><span class="sxs-lookup"><span data-stu-id="39a08-138">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="39a08-139">または</span><span class="sxs-lookup"><span data-stu-id="39a08-139">or</span></span>

     - <span data-ttu-id="39a08-140">右にトグルを移動して、期限切れにならないようにエントリを構成します。</span><span class="sxs-lookup"><span data-stu-id="39a08-140">Move the toggle to the right to configure the entries to never expire:</span></span> ![オンに切り替え](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="39a08-142">.</span><span class="sxs-lookup"><span data-stu-id="39a08-142">.</span></span>

   - <span data-ttu-id="39a08-143">**オプションのメモ**: エントリの説明テキストを入力します。</span><span class="sxs-lookup"><span data-stu-id="39a08-143">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="39a08-144">完了したら、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="39a08-144">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="39a08-145">セキュリティ & コンプライアンスセンターを使用して、テナントの許可/ブロックリストでファイルエントリを作成する</span><span class="sxs-lookup"><span data-stu-id="39a08-145">Use the Security & Compliance Center to create file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="39a08-146">[セキュリティ & コンプライアンスセンター] で、[**脅威管理** \> **ポリシー**の \> **テナントの許可/ブロックリスト**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="39a08-146">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="39a08-147">[**テナントの許可/ブロックリスト**] ページで、[**ファイル**] タブを選択し、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="39a08-147">On the **Tenant Allow/Block List** page, select **Files** tab, and then click **Add**.</span></span>

3. <span data-ttu-id="39a08-148">表示される [**新しいファイルの追加**] ポップアップで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="39a08-148">In the **Add new files** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="39a08-149">**ファイルハッシュの追加**: 行ごとに1つの SHA256 ハッシュ値を入力します (最大数は 20)。</span><span class="sxs-lookup"><span data-stu-id="39a08-149">**Add file hashes**: Enter one SHA256 hash value per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="39a08-150">[**ブロック/許可**]: 指定したファイルを**許可**または**ブロック**するかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="39a08-150">**Block/Allow**: Select whether you want to **Allow** or **Block** the specified files.</span></span>

   - <span data-ttu-id="39a08-151">**無期限: 次**のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="39a08-151">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="39a08-152">設定がオフ (トグルオフ) になっていることを確認 ![ ](../../media/scc-toggle-off.png) し、 **[有効期限**] ボックスを使用して、エントリの有効期限を指定します。</span><span class="sxs-lookup"><span data-stu-id="39a08-152">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="39a08-153">または</span><span class="sxs-lookup"><span data-stu-id="39a08-153">or</span></span>

     - <span data-ttu-id="39a08-154">右にトグルを移動して、期限切れにならないようにエントリを構成します。</span><span class="sxs-lookup"><span data-stu-id="39a08-154">Move the toggle to the right to configure the entries to never expire:</span></span> ![オンに切り替え](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="39a08-156">.</span><span class="sxs-lookup"><span data-stu-id="39a08-156">.</span></span>

   - <span data-ttu-id="39a08-157">**オプションのメモ**: エントリの説明テキストを入力します。</span><span class="sxs-lookup"><span data-stu-id="39a08-157">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="39a08-158">完了したら、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="39a08-158">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="39a08-159">セキュリティ & コンプライアンスセンターを使用して、URL およびファイルエントリをテナントの許可/ブロックリストに表示する</span><span class="sxs-lookup"><span data-stu-id="39a08-159">Use the Security & Compliance Center to view URL and file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="39a08-160">[セキュリティ & コンプライアンスセンター] で、[**脅威管理** \> **ポリシー**の \> **テナントの許可/ブロックリスト**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="39a08-160">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="39a08-161">[ **Url** ] タブまたは [**ファイル**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="39a08-161">Select the **URLs** tab or the **Files** tab.</span></span>

<span data-ttu-id="39a08-162">次の列見出しをクリックすると、昇順または降順で並べ替えられます。</span><span class="sxs-lookup"><span data-stu-id="39a08-162">Click on the following column headings to sort in ascending or descending order:</span></span>

- <span data-ttu-id="39a08-163">**値**: URL またはファイルハッシュ。</span><span class="sxs-lookup"><span data-stu-id="39a08-163">**Value**: The URL or the file hash.</span></span>
- <span data-ttu-id="39a08-164">**アクション**:**ブロック**または**許可**。</span><span class="sxs-lookup"><span data-stu-id="39a08-164">**Action**: **Block** or **Allow**.</span></span>
- <span data-ttu-id="39a08-165">**最終更新日**</span><span class="sxs-lookup"><span data-stu-id="39a08-165">**Last updated date**</span></span>
- <span data-ttu-id="39a08-166">**有効期限**</span><span class="sxs-lookup"><span data-stu-id="39a08-166">**Expiration date**</span></span>
- <span data-ttu-id="39a08-167">**注**</span><span class="sxs-lookup"><span data-stu-id="39a08-167">**Note**</span></span>

<span data-ttu-id="39a08-168">[**グループ化**] をクリックして、エントリを**アクション**(**ブロック**または**許可**) または**なし**とグループ化します。</span><span class="sxs-lookup"><span data-stu-id="39a08-168">Click **Group** to group the entries by **Action** (**Block** or **Allow**) or **None**.</span></span>

<span data-ttu-id="39a08-169">[**検索**] をクリックし、URL またはファイル値の全体または一部を入力してから、enter キーを押して特定の値を検索します。</span><span class="sxs-lookup"><span data-stu-id="39a08-169">Click **Search**, enter all or part of a URL or file value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="39a08-170">完了したら、[検索のクリア検索の**クリア**] をクリックし ![ ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) ます。</span><span class="sxs-lookup"><span data-stu-id="39a08-170">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

<span data-ttu-id="39a08-171">[**フィルター**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="39a08-171">Click **Filter**.</span></span> <span data-ttu-id="39a08-172">表示される**フィルター**のポップアップで、次のいずれかの設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="39a08-172">In the **Filter** flyout that appears, configure any of the following settings:</span></span>

- <span data-ttu-id="39a08-173">**アクション**: **Allow**、 **Block** 、または both を選択します。</span><span class="sxs-lookup"><span data-stu-id="39a08-173">**Action**: Select **Allow**, **Block** or both.</span></span>

- <span data-ttu-id="39a08-174">**無期限: オフ**(オフ ![ ](../../media/scc-toggle-off.png) ) またはオン ( ![ トグルオン ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) )。</span><span class="sxs-lookup"><span data-stu-id="39a08-174">**Never expire**: Select off (![Toggle off](../../media/scc-toggle-off.png)) or on (![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)).</span></span>

- <span data-ttu-id="39a08-175">**最終更新**日時: 開始日 (開始**日)、** 終了日 (**To**)、またはその両方を選択します。</span><span class="sxs-lookup"><span data-stu-id="39a08-175">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span></span>

- <span data-ttu-id="39a08-176">[**有効期限**]: 開始日 (開始**日)、** 終了日 (**To**)、またはその両方を選択します。</span><span class="sxs-lookup"><span data-stu-id="39a08-176">**Expiration date**: Select a start date (**From**), an end date (**To**) or both.</span></span>

<span data-ttu-id="39a08-177">完了したら、[**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="39a08-177">When you're finished, click **Apply**.</span></span>

<span data-ttu-id="39a08-178">既存のフィルターをクリアするには、[**フィルター**] をクリックし、表示される**フィルター**のポップアップで [**フィルターのクリア**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="39a08-178">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="39a08-179">セキュリティ & コンプライアンスセンターを使用して、テナントの許可/ブロックリスト内の URL とファイルエントリを変更する</span><span class="sxs-lookup"><span data-stu-id="39a08-179">Use the Security & Compliance Center to modify URL and file entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="39a08-180">URL またはファイルの値自体を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="39a08-180">You can't modify the URL or file value itself.</span></span> <span data-ttu-id="39a08-181">代わりに、エントリを削除して再作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="39a08-181">Instead, you need to delete the entry and recreate it.</span></span>

1. <span data-ttu-id="39a08-182">[セキュリティ & コンプライアンスセンター] で、[**脅威管理** \> **ポリシー**の \> **テナントの許可/ブロックリスト**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="39a08-182">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="39a08-183">[ **Url** ] タブまたは [**ファイル**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="39a08-183">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="39a08-184">変更するエントリを選択し、[編集アイコンの**編集**] をクリックし ![ ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) ます。</span><span class="sxs-lookup"><span data-stu-id="39a08-184">Select the entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span>

4. <span data-ttu-id="39a08-185">表示されたポップアップで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="39a08-185">In the flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="39a08-186">[**ブロック/許可**]: [**許可**] または [**ブロック**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="39a08-186">**Block/Allow**: Select **Allow** or **Block**.</span></span>

   - <span data-ttu-id="39a08-187">**無期限: 次**のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="39a08-187">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="39a08-188">設定がオフ (トグルオフ) になっていることを確認 ![ ](../../media/scc-toggle-off.png) し、 **[有効期限**] ボックスを使用して、エントリの有効期限を指定します。</span><span class="sxs-lookup"><span data-stu-id="39a08-188">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entry.</span></span>

     <span data-ttu-id="39a08-189">または</span><span class="sxs-lookup"><span data-stu-id="39a08-189">or</span></span>

     - <span data-ttu-id="39a08-190">この設定を右に移動して、期限切れにならないようにエントリを構成します。</span><span class="sxs-lookup"><span data-stu-id="39a08-190">Move the toggle to the right to configure the entry to never expire:</span></span> ![オンに切り替え](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="39a08-192">.</span><span class="sxs-lookup"><span data-stu-id="39a08-192">.</span></span>

   - <span data-ttu-id="39a08-193">**オプションのメモ**: エントリの説明テキストを入力します。</span><span class="sxs-lookup"><span data-stu-id="39a08-193">**Optional note**: Enter descriptive text for the entry.</span></span>

5. <span data-ttu-id="39a08-194">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="39a08-194">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-url-and-file-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="39a08-195">セキュリティ & コンプライアンスセンターを使用して、URL とファイルのエントリをテナントの許可/禁止リストから削除する</span><span class="sxs-lookup"><span data-stu-id="39a08-195">Use the Security & Compliance Center to remove URL and file entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="39a08-196">[セキュリティ & コンプライアンスセンター] で、[**脅威管理** \> **ポリシー**の \> **テナントの許可/ブロックリスト**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="39a08-196">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="39a08-197">[ **Url** ] タブまたは [**ファイル**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="39a08-197">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="39a08-198">削除するエントリを選択し、[削除] [削除] アイコン**をクリックし** ![ ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) ます。</span><span class="sxs-lookup"><span data-stu-id="39a08-198">Select the entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="39a08-199">表示される警告ダイアログで、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="39a08-199">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="39a08-200">Exchange Online PowerShell またはスタンドアロンの EOP PowerShell を使用して、テナントの許可/ブロックリストを構成する</span><span class="sxs-lookup"><span data-stu-id="39a08-200">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="39a08-201">PowerShell を使用して、テナントの許可/ブロックリストに URL とファイルエントリを追加する</span><span class="sxs-lookup"><span data-stu-id="39a08-201">Use PowerShell to add URL and file entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="39a08-202">テナントの許可/ブロックリストに URL とファイルエントリを追加するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="39a08-202">To add URL and file entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType <Url | FileHash> -Action <Allow | Block> -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="39a08-203">この例では、contoso.com およびすべてのサブドメイン (たとえば、contoso.com、www.contoso.com、および xyz.abc.contoso.com) の URL ブロックエントリを追加します。</span><span class="sxs-lookup"><span data-stu-id="39a08-203">This example adds a URL block entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="39a08-204">ExpirationDate パラメーターまたは NoExpiration パラメーターを使用していなかったため、エントリは30日後に有効期限が切れます。</span><span class="sxs-lookup"><span data-stu-id="39a08-204">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType Url -Action Block -Entries ~contoso.com
```

```powershell
New-TenantAllowBlockListItem -ListType FileHash -Action Allow -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

<span data-ttu-id="39a08-205">この例では、指定したファイルの有効期限が切れないファイルの許可エントリを追加します。</span><span class="sxs-lookup"><span data-stu-id="39a08-205">This example adds a file allow entry for the specified files that never expires.</span></span>

<span data-ttu-id="39a08-206">構文およびパラメーターの詳細については、「 [TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="39a08-206">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="39a08-207">PowerShell を使用して、テナントの許可/ブロックリスト内の URL とファイルエントリを表示する</span><span class="sxs-lookup"><span data-stu-id="39a08-207">Use PowerShell to view URL and file entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="39a08-208">テナントの許可/ブロックの一覧で URL とファイルエントリを表示するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="39a08-208">To view URL and file entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType <Url | FileHash> [-Entry <URLValue | FileHashValue>] [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration]
```

<span data-ttu-id="39a08-209">この例では、すべてのブロックされた Url を返します。</span><span class="sxs-lookup"><span data-stu-id="39a08-209">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Action Block
```

<span data-ttu-id="39a08-210">この例では、指定したファイルハッシュ値に関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="39a08-210">This example returns information for the specified file hash value.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

<span data-ttu-id="39a08-211">構文およびパラメーターの詳細については、「 [TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="39a08-211">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="39a08-212">PowerShell を使用して、テナントの許可/ブロックリスト内の URL とファイルエントリを変更する</span><span class="sxs-lookup"><span data-stu-id="39a08-212">Use PowerShell to modify URL and file entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="39a08-213">URL またはファイルの値自体を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="39a08-213">You can't modify the URL or file value itself.</span></span> <span data-ttu-id="39a08-214">代わりに、エントリを削除して再作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="39a08-214">Instead, you need to delete the entry and recreate it.</span></span>

<span data-ttu-id="39a08-215">テナントの許可/ブロックの一覧で URL とファイルエントリを変更するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="39a08-215">To modify URL and file entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN"> [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="39a08-216">次の使用例は、指定された項目の有効期限を変更します。</span><span class="sxs-lookup"><span data-stu-id="39a08-216">This example changes the expiration date of the specified entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

<span data-ttu-id="39a08-217">構文およびパラメーターの詳細については、「 [TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="39a08-217">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-url-and-file-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="39a08-218">PowerShell を使用して、テナントの許可/ブロックリストから URL とファイルエントリを削除する</span><span class="sxs-lookup"><span data-stu-id="39a08-218">Use PowerShell to remove URL and file entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="39a08-219">URL とファイルエントリをテナントの許可/禁止リストから削除するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="39a08-219">To remove URL and file entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="39a08-220">この例では、指定した URL エントリをテナントの許可/禁止リストから削除します。</span><span class="sxs-lookup"><span data-stu-id="39a08-220">This example removes the specified URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="39a08-221">構文およびパラメーターの詳細については、「 [TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="39a08-221">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="39a08-222">テナントの許可/ブロックリストの URL 構文</span><span class="sxs-lookup"><span data-stu-id="39a08-222">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="39a08-223">IP4v および IPv6 アドレスは許可されますが、TCP/UDP ポートは許可されません。</span><span class="sxs-lookup"><span data-stu-id="39a08-223">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="39a08-224">ファイル名の拡張子を使用することはできません (たとえば、.pdf)。</span><span class="sxs-lookup"><span data-stu-id="39a08-224">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="39a08-225">Unicode はサポートされていませんが、Punycode はです。</span><span class="sxs-lookup"><span data-stu-id="39a08-225">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="39a08-226">次のすべてのステートメントが true の場合、ホスト名が許可されます。</span><span class="sxs-lookup"><span data-stu-id="39a08-226">Hostnames are allowed if all of the following statements are true:</span></span>

  - <span data-ttu-id="39a08-227">ホスト名にはピリオドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="39a08-227">The hostname contains a period.</span></span>
  - <span data-ttu-id="39a08-228">ピリオドの左側には、少なくとも1つの文字があります。</span><span class="sxs-lookup"><span data-stu-id="39a08-228">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="39a08-229">ピリオドの右側には、少なくとも2つの文字があります。</span><span class="sxs-lookup"><span data-stu-id="39a08-229">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="39a08-230">たとえば、は許可されて `t.co` `.com` いるか、許可され `contoso.` ていません。</span><span class="sxs-lookup"><span data-stu-id="39a08-230">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="39a08-231">サブパスは黙示的ではありません。</span><span class="sxs-lookup"><span data-stu-id="39a08-231">Subpaths are not implied.</span></span>

  <span data-ttu-id="39a08-232">たとえば、にはを `contoso.com` 含めません `contoso.com/a` 。</span><span class="sxs-lookup"><span data-stu-id="39a08-232">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="39a08-233">次のシナリオでは、ワイルドカード (\*) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="39a08-233">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="39a08-234">サブドメインを指定するには、左のワイルドカードの後にピリオドを置く必要があります。</span><span class="sxs-lookup"><span data-stu-id="39a08-234">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="39a08-235">たとえば、 `*.contoso.com` は許可され `*contoso.com` ていません。許可されていません。</span><span class="sxs-lookup"><span data-stu-id="39a08-235">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="39a08-236">右のワイルドカードは、スラッシュ (/) に続けてパスを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="39a08-236">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="39a08-237">たとえば、は許可されて `contoso.com/*` `contoso.com*` いるか、許可され `contoso.com/ab*` ていません。</span><span class="sxs-lookup"><span data-stu-id="39a08-237">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="39a08-238">すべてのサブパスは、右のワイルドカードでは暗黙的には含まれません。</span><span class="sxs-lookup"><span data-stu-id="39a08-238">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="39a08-239">たとえば、にはを `contoso.com/*` 含めません `contoso.com/a` 。</span><span class="sxs-lookup"><span data-stu-id="39a08-239">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="39a08-240">`*.com*`は無効です (解決可能なドメインではなく、右のワイルドカードはスラッシュに従っていません)。</span><span class="sxs-lookup"><span data-stu-id="39a08-240">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="39a08-241">IP アドレスにワイルドカードを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="39a08-241">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="39a08-242">チルダ (~) 文字は、次のシナリオで使用できます。</span><span class="sxs-lookup"><span data-stu-id="39a08-242">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="39a08-243">左チルダは、1つのドメインとすべてのサブドメインを意味します。</span><span class="sxs-lookup"><span data-stu-id="39a08-243">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="39a08-244">たとえば `~contoso.com` `contoso.com` 、とを含み `*.contoso.com` ます。</span><span class="sxs-lookup"><span data-stu-id="39a08-244">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="39a08-245">`http://` `https://` Url エントリはすべてのプロトコルに適用されるため、プロトコル (たとえば、など) を含む url エントリ `ftp://` は失敗します。</span><span class="sxs-lookup"><span data-stu-id="39a08-245">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="39a08-246">ユーザー名またはパスワードがサポートされていないか、または必要です。</span><span class="sxs-lookup"><span data-stu-id="39a08-246">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="39a08-247">引用符 (' または ") は無効な文字です。</span><span class="sxs-lookup"><span data-stu-id="39a08-247">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="39a08-248">可能な場合は、URL にすべてのリダイレクトを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="39a08-248">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="39a08-249">URL エントリのシナリオ</span><span class="sxs-lookup"><span data-stu-id="39a08-249">URL entry scenarios</span></span>

<span data-ttu-id="39a08-250">次のセクションでは、有効な URL エントリとその結果について説明します。</span><span class="sxs-lookup"><span data-stu-id="39a08-250">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="39a08-251">シナリオ: ワイルドカードがありません</span><span class="sxs-lookup"><span data-stu-id="39a08-251">Scenario: No wildcards</span></span>

<span data-ttu-id="39a08-252">**Entry**:`contoso.com`</span><span class="sxs-lookup"><span data-stu-id="39a08-252">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="39a08-253">**Match の許可**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="39a08-253">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="39a08-254">**許可しない**:</span><span class="sxs-lookup"><span data-stu-id="39a08-254">**Allow not matched**:</span></span>

  - <span data-ttu-id="39a08-255">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="39a08-255">abc-contoso.com</span></span>
  - <span data-ttu-id="39a08-256">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="39a08-256">contoso.com/a</span></span>
  - <span data-ttu-id="39a08-257">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="39a08-257">payroll.contoso.com</span></span>
  - <span data-ttu-id="39a08-258">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="39a08-258">test.com/contoso.com</span></span>
  - <span data-ttu-id="39a08-259">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="39a08-259">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="39a08-260">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="39a08-260">www.contoso.com</span></span>
  - <span data-ttu-id="39a08-261">www. .com/q = a@contoso</span><span class="sxs-lookup"><span data-stu-id="39a08-261">www.contoso.com/q=a@contoso.com</span></span>
  
- <span data-ttu-id="39a08-262">**ブロック一致**:</span><span class="sxs-lookup"><span data-stu-id="39a08-262">**Block match**:</span></span>

  - <span data-ttu-id="39a08-263">contoso.com</span><span class="sxs-lookup"><span data-stu-id="39a08-263">contoso.com</span></span>
  - <span data-ttu-id="39a08-264">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="39a08-264">contoso.com/a</span></span>
  - <span data-ttu-id="39a08-265">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="39a08-265">payroll.contoso.com</span></span>
  - <span data-ttu-id="39a08-266">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="39a08-266">test.com/contoso.com</span></span>
  - <span data-ttu-id="39a08-267">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="39a08-267">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="39a08-268">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="39a08-268">www.contoso.com</span></span>
  - <span data-ttu-id="39a08-269">www. .com/q = a@contoso</span><span class="sxs-lookup"><span data-stu-id="39a08-269">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="39a08-270">**ブロックが一致しません**: abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="39a08-270">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="39a08-271">シナリオ: 左ワイルドカード (サブドメイン)</span><span class="sxs-lookup"><span data-stu-id="39a08-271">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="39a08-272">**Entry**:`*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="39a08-272">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="39a08-273">一致と**ブロックの一致**を**許可する**:</span><span class="sxs-lookup"><span data-stu-id="39a08-273">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="39a08-274">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="39a08-274">www.contoso.com</span></span>
  - <span data-ttu-id="39a08-275">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="39a08-275">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="39a08-276">[一致しない] と [**ブロックが一致**し**ません**] を許可します。</span><span class="sxs-lookup"><span data-stu-id="39a08-276">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="39a08-277">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="39a08-277">123contoso.com</span></span>
  - <span data-ttu-id="39a08-278">contoso.com</span><span class="sxs-lookup"><span data-stu-id="39a08-278">contoso.com</span></span>
  - <span data-ttu-id="39a08-279">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="39a08-279">test.com/contoso.com</span></span>
  - <span data-ttu-id="39a08-280">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="39a08-280">www.contoso.com/abc</span></span>
  
#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="39a08-281">シナリオ: パスの上部にあるワイルドカード (右)</span><span class="sxs-lookup"><span data-stu-id="39a08-281">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="39a08-282">**Entry**:`contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="39a08-282">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="39a08-283">一致と**ブロックの一致**を**許可する**:</span><span class="sxs-lookup"><span data-stu-id="39a08-283">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="39a08-284">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="39a08-284">contoso.com/a/b</span></span>
  - <span data-ttu-id="39a08-285">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="39a08-285">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="39a08-286">contoso .com/a/? q = joe@t</span><span class="sxs-lookup"><span data-stu-id="39a08-286">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="39a08-287">[一致しない] と [**ブロックが一致**し**ません**] を許可します。</span><span class="sxs-lookup"><span data-stu-id="39a08-287">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="39a08-288">contoso.com</span><span class="sxs-lookup"><span data-stu-id="39a08-288">contoso.com</span></span>
  - <span data-ttu-id="39a08-289">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="39a08-289">contoso.com/a</span></span>
  - <span data-ttu-id="39a08-290">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="39a08-290">www.contoso.com</span></span>
  - <span data-ttu-id="39a08-291">www. .com/q = a@contoso</span><span class="sxs-lookup"><span data-stu-id="39a08-291">www.contoso.com/q=a@contoso.com</span></span>
  
#### <a name="scenario-left-tilde"></a><span data-ttu-id="39a08-292">シナリオ: 左チルダ</span><span class="sxs-lookup"><span data-stu-id="39a08-292">Scenario: Left tilde</span></span>

<span data-ttu-id="39a08-293">**Entry**:`~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="39a08-293">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="39a08-294">一致と**ブロックの一致**を**許可する**:</span><span class="sxs-lookup"><span data-stu-id="39a08-294">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="39a08-295">contoso.com</span><span class="sxs-lookup"><span data-stu-id="39a08-295">contoso.com</span></span>
  - <span data-ttu-id="39a08-296">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="39a08-296">www.contoso.com</span></span>
  - <span data-ttu-id="39a08-297">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="39a08-297">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="39a08-298">[一致しない] と [**ブロックが一致**し**ません**] を許可します。</span><span class="sxs-lookup"><span data-stu-id="39a08-298">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="39a08-299">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="39a08-299">123contoso.com</span></span>
  - <span data-ttu-id="39a08-300">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="39a08-300">contoso.com/abc</span></span>
  - <span data-ttu-id="39a08-301">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="39a08-301">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="39a08-302">シナリオ: 右ワイルドカードサフィックス</span><span class="sxs-lookup"><span data-stu-id="39a08-302">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="39a08-303">**Entry**:`contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="39a08-303">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="39a08-304">一致と**ブロックの一致**を**許可する**:</span><span class="sxs-lookup"><span data-stu-id="39a08-304">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="39a08-305">contoso .com/? q = whatever@fabrikam</span><span class="sxs-lookup"><span data-stu-id="39a08-305">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="39a08-306">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="39a08-306">contoso.com/a</span></span>
  - <span data-ttu-id="39a08-307">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="39a08-307">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="39a08-308">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="39a08-308">contoso.com/ab</span></span>
  - <span data-ttu-id="39a08-309">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="39a08-309">contoso.com/b</span></span>
  - <span data-ttu-id="39a08-310">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="39a08-310">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="39a08-311">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="39a08-311">contoso.com/ba</span></span>

- <span data-ttu-id="39a08-312">**Allow not 一致**と**ブロック not 一致**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="39a08-312">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="39a08-313">シナリオ: 左ワイルドカードサブドメインと右ワイルドカードサフィックス</span><span class="sxs-lookup"><span data-stu-id="39a08-313">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="39a08-314">**Entry**:`*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="39a08-314">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="39a08-315">一致と**ブロックの一致**を**許可する**:</span><span class="sxs-lookup"><span data-stu-id="39a08-315">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="39a08-316">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="39a08-316">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="39a08-317">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="39a08-317">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="39a08-318">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="39a08-318">www.contoso.com/a</span></span>
  - <span data-ttu-id="39a08-319">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="39a08-319">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="39a08-320">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="39a08-320">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="39a08-321">**Allow not 一致**と**ブロック not 一致**: contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="39a08-321">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="39a08-322">シナリオ: 左と右のチルダ</span><span class="sxs-lookup"><span data-stu-id="39a08-322">Scenario: Left and right tilde</span></span>

<span data-ttu-id="39a08-323">**Entry**:`~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="39a08-323">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="39a08-324">一致と**ブロックの一致**を**許可する**:</span><span class="sxs-lookup"><span data-stu-id="39a08-324">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="39a08-325">contoso.com</span><span class="sxs-lookup"><span data-stu-id="39a08-325">contoso.com</span></span>
  - <span data-ttu-id="39a08-326">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="39a08-326">contoso.com/a</span></span>
  - <span data-ttu-id="39a08-327">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="39a08-327">www.contoso.com</span></span>
  - <span data-ttu-id="39a08-328">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="39a08-328">www.contoso.com/b</span></span>
  - <span data-ttu-id="39a08-329">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="39a08-329">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="39a08-330">[一致しない] と [**ブロックが一致**し**ません**] を許可します。</span><span class="sxs-lookup"><span data-stu-id="39a08-330">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="39a08-331">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="39a08-331">123contoso.com</span></span>
  - <span data-ttu-id="39a08-332">contoso.org</span><span class="sxs-lookup"><span data-stu-id="39a08-332">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="39a08-333">シナリオ: IP アドレス</span><span class="sxs-lookup"><span data-stu-id="39a08-333">Scenario: IP address</span></span>

<span data-ttu-id="39a08-334">**Entry**:`1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="39a08-334">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="39a08-335">Match と**Block match**を**許可する**: 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="39a08-335">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="39a08-336">[一致しない] と [**ブロックが一致**し**ません**] を許可します。</span><span class="sxs-lookup"><span data-stu-id="39a08-336">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="39a08-337">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="39a08-337">1.2.3.4/a</span></span>
  - <span data-ttu-id="39a08-338">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="39a08-338">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="39a08-339">右ワイルドカードを使用した IP アドレス</span><span class="sxs-lookup"><span data-stu-id="39a08-339">IP address with right wildcard</span></span>

<span data-ttu-id="39a08-340">**Entry**:`1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="39a08-340">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="39a08-341">一致と**ブロックの一致**を**許可する**:</span><span class="sxs-lookup"><span data-stu-id="39a08-341">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="39a08-342">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="39a08-342">1.2.3.4/b</span></span>
  - <span data-ttu-id="39a08-343">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="39a08-343">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="39a08-344">無効なエントリの例</span><span class="sxs-lookup"><span data-stu-id="39a08-344">Examples of invalid entries</span></span>

<span data-ttu-id="39a08-345">次のエントリは無効です。</span><span class="sxs-lookup"><span data-stu-id="39a08-345">The following entries are invalid:</span></span>

- <span data-ttu-id="39a08-346">**ドメイン値がないか、または無効**です。</span><span class="sxs-lookup"><span data-stu-id="39a08-346">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="39a08-347">拠点</span><span class="sxs-lookup"><span data-stu-id="39a08-347">contoso</span></span>
  - <span data-ttu-id="39a08-348">\*拠点.\*</span><span class="sxs-lookup"><span data-stu-id="39a08-348">\*.contoso.\*</span></span>
  - <span data-ttu-id="39a08-349">\*.com</span><span class="sxs-lookup"><span data-stu-id="39a08-349">\*.com</span></span>
  - <span data-ttu-id="39a08-350">\*.pdf</span><span class="sxs-lookup"><span data-stu-id="39a08-350">\*.pdf</span></span>

- <span data-ttu-id="39a08-351">**文字列の場合はワイルドカード、文字間隔は使用しませ**ん。</span><span class="sxs-lookup"><span data-stu-id="39a08-351">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="39a08-352">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="39a08-352">\*contoso.com</span></span>
  - <span data-ttu-id="39a08-353">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="39a08-353">contoso.com\*</span></span>
  - <span data-ttu-id="39a08-354">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="39a08-354">\*1.2.3.4</span></span>
  - <span data-ttu-id="39a08-355">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="39a08-355">1.2.3.4\*</span></span>
  - <span data-ttu-id="39a08-356">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="39a08-356">contoso.com/a\*</span></span>
  - <span data-ttu-id="39a08-357">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="39a08-357">contoso.com/ab\*</span></span>

- <span data-ttu-id="39a08-358">**ポートを使用した IP アドレス**:</span><span class="sxs-lookup"><span data-stu-id="39a08-358">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="39a08-359">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="39a08-359">contoso.com:443</span></span>
  - <span data-ttu-id="39a08-360">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="39a08-360">abc.contoso.com:25</span></span>

- <span data-ttu-id="39a08-361">**説明のないワイルドカード**:</span><span class="sxs-lookup"><span data-stu-id="39a08-361">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="39a08-362">\*.\*</span><span class="sxs-lookup"><span data-stu-id="39a08-362">\*.\*</span></span>

- <span data-ttu-id="39a08-363">**中央のワイルドカード**:</span><span class="sxs-lookup"><span data-stu-id="39a08-363">**Middle wildcards**:</span></span>

  - <span data-ttu-id="39a08-364">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="39a08-364">conto\*so.com</span></span>
  - <span data-ttu-id="39a08-365">~ so ~ .com</span><span class="sxs-lookup"><span data-stu-id="39a08-365">conto~so.com</span></span>

- <span data-ttu-id="39a08-366">**2文字のワイルドカード**</span><span class="sxs-lookup"><span data-stu-id="39a08-366">**Double wildcards**</span></span>

  - <span data-ttu-id="39a08-367">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="39a08-367">contoso.com/\*\*</span></span>
  - <span data-ttu-id="39a08-368">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="39a08-368">contoso.com/\*/\*</span></span>
