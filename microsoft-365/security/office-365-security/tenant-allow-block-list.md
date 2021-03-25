---
title: テナント許可/ブロック一覧で許可とブロックを管理する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 管理者は、セキュリティ ポータルのテナント許可/ブロック一覧で許可とブロックを構成する方法について学習できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 55116ddac8fa25b63e50b7fba73f668855e2858d
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206440"
---
# <a name="manage-the-tenant-allowblock-list"></a><span data-ttu-id="9d83a-103">テナントの許可/禁止リストの URL を管理する</span><span class="sxs-lookup"><span data-stu-id="9d83a-103">Manage the Tenant Allow/Block List</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="9d83a-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="9d83a-104">**Applies to**</span></span>
- [<span data-ttu-id="9d83a-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="9d83a-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="9d83a-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="9d83a-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="9d83a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9d83a-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
>
> <span data-ttu-id="9d83a-108">この記事で説明する機能はプレビューで、変更される可能性があります。一部の組織では利用できません。</span><span class="sxs-lookup"><span data-stu-id="9d83a-108">The features described in this article are in Preview, are subject to change, and are not available in all organizations.</span></span>
>
> <span data-ttu-id="9d83a-109">現時点 **では、テナント** 許可/ブロック一覧で許可アイテムを構成できません。</span><span class="sxs-lookup"><span data-stu-id="9d83a-109">You can't **configure** allowed items in the Tenant Allow/Block List at this time.</span></span>

<span data-ttu-id="9d83a-110">Exchange Online またはスタンドアロンの Exchange Online Protection (EOP) 組織に Exchange Online メールボックスがない Microsoft 365 組織では、EOP フィルターの評決に同意しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9d83a-110">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="9d83a-111">たとえば、メッセージが正しい (誤検知) とマークされている場合や、悪いメッセージが許可される場合があります (偽陰性)。</span><span class="sxs-lookup"><span data-stu-id="9d83a-111">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="9d83a-112">セキュリティ コンプライアンス センターのテナント許可/ブロック一覧&、Microsoft 365 フィルターの評決を手動で上書きする方法が提供されます。</span><span class="sxs-lookup"><span data-stu-id="9d83a-112">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="9d83a-113">テナント許可/ブロック一覧は、メール フロー中およびユーザークリック時に使用されます。</span><span class="sxs-lookup"><span data-stu-id="9d83a-113">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="9d83a-114">常にブロックする URL またはファイルを指定できます。</span><span class="sxs-lookup"><span data-stu-id="9d83a-114">You can specify URLs or files to always block.</span></span>

<span data-ttu-id="9d83a-115">この記事では、セキュリティ & コンプライアンス センターまたは PowerShell (Exchange Online のメールボックスを持つ Microsoft 365 組織向け Exchange Online PowerShell、Exchange Online メールボックスのない組織のスタンドアロン EOP PowerShell) のテナント許可/ブロック一覧のエントリを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9d83a-115">This article describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="9d83a-116">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="9d83a-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="9d83a-117"><https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="9d83a-117">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="9d83a-118">[テナントの許可/ブロック **リスト] ページに直接移動するには** 、 を使用します <https://protection.office.com/tenantAllowBlockList> 。</span><span class="sxs-lookup"><span data-stu-id="9d83a-118">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="9d83a-119">ファイルを指定するには、ファイルの SHA256 ハッシュ値を使用します。</span><span class="sxs-lookup"><span data-stu-id="9d83a-119">You specify files by using the SHA256 hash value of the file.</span></span> <span data-ttu-id="9d83a-120">Windows でファイルの SHA256 ハッシュ値を検索するには、コマンド プロンプトで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9d83a-120">To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt:</span></span>

  ```console
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  <span data-ttu-id="9d83a-121">値の例は、 です `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` 。</span><span class="sxs-lookup"><span data-stu-id="9d83a-121">An example value is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`.</span></span> <span data-ttu-id="9d83a-122">知覚ハッシュ (pHash) の値はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="9d83a-122">Perceptual hash (pHash) values are not supported.</span></span>

- <span data-ttu-id="9d83a-123">使用可能な URL 値については、この記事の後半の「 [テナント許可/](#url-syntax-for-the-tenant-allowblock-list) ブロック一覧」セクションの URL 構文で説明します。</span><span class="sxs-lookup"><span data-stu-id="9d83a-123">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

- <span data-ttu-id="9d83a-124">テナント許可/ブロック一覧では、URL に対して最大 500 エントリ、ファイル ハッシュのエントリを 500 エントリまで使用できます。</span><span class="sxs-lookup"><span data-stu-id="9d83a-124">The Tenant Allow/Block List allows a maximum of 500 entries for URLs, and 500 entries for file hashes.</span></span>

- <span data-ttu-id="9d83a-125">各エントリの最大文字数は次の値です。</span><span class="sxs-lookup"><span data-stu-id="9d83a-125">The maximum number of characters for each entry is:</span></span>
  - <span data-ttu-id="9d83a-126">ファイル ハッシュ = 64</span><span class="sxs-lookup"><span data-stu-id="9d83a-126">File hashes = 64</span></span>
  - <span data-ttu-id="9d83a-127">URL = 250</span><span class="sxs-lookup"><span data-stu-id="9d83a-127">URL = 250</span></span>

- <span data-ttu-id="9d83a-128">エントリは 30 分以内にアクティブである必要があります。</span><span class="sxs-lookup"><span data-stu-id="9d83a-128">An entry should be active within 30 minutes.</span></span>

- <span data-ttu-id="9d83a-129">既定では、テナント許可/ブロック一覧のエントリは 30 日後に期限切れになります。</span><span class="sxs-lookup"><span data-stu-id="9d83a-129">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="9d83a-130">日付を指定するか、有効期限が切れることはありません。</span><span class="sxs-lookup"><span data-stu-id="9d83a-130">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="9d83a-131">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9d83a-131">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="9d83a-132">スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9d83a-132">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="9d83a-133">この記事の手順を実行する際には、あらかじめ **Exchange Online** でアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="9d83a-133">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="9d83a-134">テナント許可/ブロック一覧の値を追加および削除するには、組織の管理またはセキュリティ管理者の役割グループのメンバー **である** 必要があります。</span><span class="sxs-lookup"><span data-stu-id="9d83a-134">To add and remove values from the Tenant Allow/Block List, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="9d83a-135">テナント許可/ブロック一覧への読み取り専用アクセスでは、グローバル リーダーまたはセキュリティリーダーの役割グループの **メンバーである** 必要があります。</span><span class="sxs-lookup"><span data-stu-id="9d83a-135">For read-only access to the Tenant Allow/Block List, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="9d83a-136">詳細については、「[Exchange Online のアクセス許可](/exchange/permissions-exo/permissions-exo)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9d83a-136">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  > 
  > - <span data-ttu-id="9d83a-137">Microsoft 365 管理センターで、対応する Azure Active Directory の役割にユーザーを追加すると、ユーザーには、必要なアクセス許可 _および_ Microsoft 365 のその他の機能に必要なアクセス許可が付与されます。</span><span class="sxs-lookup"><span data-stu-id="9d83a-137">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="9d83a-138">詳細については、「[管理者の役割について](../../admin/add-users/about-admin-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9d83a-138">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  > - <span data-ttu-id="9d83a-139">[Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) の **閲覧専用の組織管理** の役割グループが この機能への読み取り専用アクセス権も付与します。</span><span class="sxs-lookup"><span data-stu-id="9d83a-139">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="9d83a-140">テナント許可/&リストに URL エントリを作成するには、セキュリティ コンプライアンス センターを使用します。</span><span class="sxs-lookup"><span data-stu-id="9d83a-140">Use the Security & Compliance Center to create URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="9d83a-141">URL エントリの構文の詳細については、この記事の後半の「テナント許可/ブロック一覧」セクションの [URL](#url-syntax-for-the-tenant-allowblock-list) 構文を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9d83a-141">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

1. <span data-ttu-id="9d83a-142">セキュリティ 管理コンプライアンス センター&、[**脅威管理ポリシー** ] [テナントの許可 \>  \> **/ブロックリスト] に移動します**。</span><span class="sxs-lookup"><span data-stu-id="9d83a-142">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="9d83a-143">[テナントの **許可/ブロック一覧** ] ページで **、[URL]** タブが選択されているのを確認し、[ブロック] を **クリックします。**</span><span class="sxs-lookup"><span data-stu-id="9d83a-143">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Block**</span></span>

3. <span data-ttu-id="9d83a-144">表示される **[URL のブロック]** フライアウトで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="9d83a-144">In the **Block URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="9d83a-145">**ブロックする URL を追加する**: 1 行に 1 つの URL を入力し、最大 20 を入力します。</span><span class="sxs-lookup"><span data-stu-id="9d83a-145">**Add URLs to block**: Enter one URL per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="9d83a-146">**有効期限が切れる** ことはありません: 次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="9d83a-146">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="9d83a-147">設定がオフ (トグルオフ) になっていることを確認し、[有効期限] ボックスを使用してエントリの有効期限 ![ ](../../media/scc-toggle-off.png) を指定します。 </span><span class="sxs-lookup"><span data-stu-id="9d83a-147">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

       <span data-ttu-id="9d83a-148">または</span><span class="sxs-lookup"><span data-stu-id="9d83a-148">or</span></span>

     - <span data-ttu-id="9d83a-149">切り替えボタンを右に移動して、有効期限が切れなきエントリを構成します。</span><span class="sxs-lookup"><span data-stu-id="9d83a-149">Move the toggle to the right to configure the entries to never expire:</span></span> ![オンに切り替え](../../media/scc-toggle-on.png)<span data-ttu-id="9d83a-151">.</span><span class="sxs-lookup"><span data-stu-id="9d83a-151">.</span></span>

   - <span data-ttu-id="9d83a-152">**省略可能な** メモ: エントリの説明テキストを入力します。</span><span class="sxs-lookup"><span data-stu-id="9d83a-152">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="9d83a-153">完了したら、**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9d83a-153">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="9d83a-154">テナント許可/&リストにファイル エントリを作成するには、セキュリティ コンプライアンス センターを使用します。</span><span class="sxs-lookup"><span data-stu-id="9d83a-154">Use the Security & Compliance Center to create file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="9d83a-155">セキュリティ 管理コンプライアンス センター&、[**脅威管理ポリシー** ] [テナントの許可 \>  \> **/ブロックリスト] に移動します**。</span><span class="sxs-lookup"><span data-stu-id="9d83a-155">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="9d83a-156">[テナントの **許可/ブロックリスト] ページで** 、[ **ファイル]** タブを選択し、[ブロック] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="9d83a-156">On the **Tenant Allow/Block List** page, select **Files** tab, and then click **Block**.</span></span>

3. <span data-ttu-id="9d83a-157">表示される **[ファイルを追加してブロック** する] フライアウトで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="9d83a-157">In the **Add files to block** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="9d83a-158">**ファイル ハッシュの追加**: 1 行に 1 つの SHA256 ハッシュ値を入力し、最大 20 を入力します。</span><span class="sxs-lookup"><span data-stu-id="9d83a-158">**Add file hashes**: Enter one SHA256 hash value per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="9d83a-159">**有効期限が切れる** ことはありません: 次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="9d83a-159">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="9d83a-160">設定がオフ (トグルオフ) になっていることを確認し、[有効期限] ボックスを使用してエントリの有効期限 ![ ](../../media/scc-toggle-off.png) を指定します。 </span><span class="sxs-lookup"><span data-stu-id="9d83a-160">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="9d83a-161">または</span><span class="sxs-lookup"><span data-stu-id="9d83a-161">or</span></span>

     - <span data-ttu-id="9d83a-162">切り替えボタンを右に移動して、有効期限が切れなきエントリを構成します。</span><span class="sxs-lookup"><span data-stu-id="9d83a-162">Move the toggle to the right to configure the entries to never expire:</span></span> ![オンに切り替え](../../media/scc-toggle-on.png)<span data-ttu-id="9d83a-164">.</span><span class="sxs-lookup"><span data-stu-id="9d83a-164">.</span></span>

   - <span data-ttu-id="9d83a-165">**省略可能な** メモ: エントリの説明テキストを入力します。</span><span class="sxs-lookup"><span data-stu-id="9d83a-165">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="9d83a-166">完了したら、**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9d83a-166">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="9d83a-167">テナント許可/&リストのエントリを表示するには、セキュリティ コンプライアンス センターを使用します。</span><span class="sxs-lookup"><span data-stu-id="9d83a-167">Use the Security & Compliance Center to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="9d83a-168">セキュリティ 管理コンプライアンス センター&、[**脅威管理ポリシー** ] [テナントの許可 \>  \> **/ブロックリスト] に移動します**。</span><span class="sxs-lookup"><span data-stu-id="9d83a-168">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="9d83a-169">**[URL] タブまたは [** ファイル] タブ **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="9d83a-169">Select the **URLs** tab or the **Files** tab.</span></span>

<span data-ttu-id="9d83a-170">昇順または降順で並べ替えるには、次の列見出しをクリックします。</span><span class="sxs-lookup"><span data-stu-id="9d83a-170">Click on the following column headings to sort in ascending or descending order:</span></span>

- <span data-ttu-id="9d83a-171">**値**: URL またはファイル ハッシュ。</span><span class="sxs-lookup"><span data-stu-id="9d83a-171">**Value**: The URL or the file hash.</span></span>
- <span data-ttu-id="9d83a-172">**最終更新日**</span><span class="sxs-lookup"><span data-stu-id="9d83a-172">**Last updated date**</span></span>
- <span data-ttu-id="9d83a-173">**有効期限**</span><span class="sxs-lookup"><span data-stu-id="9d83a-173">**Expiration date**</span></span>
- <span data-ttu-id="9d83a-174">**注**</span><span class="sxs-lookup"><span data-stu-id="9d83a-174">**Note**</span></span>

<span data-ttu-id="9d83a-175">[ **検索]** をクリックし、値のすべてまたは一部を入力し、Enter キーを押して特定の値を検索します。</span><span class="sxs-lookup"><span data-stu-id="9d83a-175">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="9d83a-176">完了したら、[検索のクリア] **アイコン** ![ をクリックします ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) 。</span><span class="sxs-lookup"><span data-stu-id="9d83a-176">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

<span data-ttu-id="9d83a-177">[フィルター **] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="9d83a-177">Click **Filter**.</span></span> <span data-ttu-id="9d83a-178">表示される **[フィルター** ] フライアウトで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="9d83a-178">In the **Filter** flyout that appears, configure any of the following settings:</span></span>

- <span data-ttu-id="9d83a-179">**有効期限が切** れることはありません: [オフ] を ![ 選択します。オフ ](../../media/scc-toggle-off.png) またはオンに切り替えます。 ![ ](../../media/scc-toggle-on.png)</span><span class="sxs-lookup"><span data-stu-id="9d83a-179">**Never expire**: Select off: ![Toggle off](../../media/scc-toggle-off.png) or on: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

- <span data-ttu-id="9d83a-180">**最終更新日 :** 開始日 ( From **)**、終了日 (**To**) または両方を選択します。</span><span class="sxs-lookup"><span data-stu-id="9d83a-180">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span></span>

- <span data-ttu-id="9d83a-181">**有効期限 :** 開始日 **(** From ) 、終了日 (**To**) または両方を選択します。</span><span class="sxs-lookup"><span data-stu-id="9d83a-181">**Expiration date**: Select a start date (**From**), an end date (**To**) or both.</span></span>

<span data-ttu-id="9d83a-182">完了したら、[適用] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="9d83a-182">When you're finished, click **Apply**.</span></span>

<span data-ttu-id="9d83a-183">既存のフィルターをクリアするには、[**フィルター**] をクリックし、表示される [フィルター] フライアウトで 、[フィルターのクリア]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="9d83a-183">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-block-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="9d83a-184">テナント許可/&リストのブロック エントリを変更するには、セキュリティ コンプライアンス センターを使用します。</span><span class="sxs-lookup"><span data-stu-id="9d83a-184">Use the Security & Compliance Center to modify block entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="9d83a-185">エントリ内の既存のブロックされた URL またはファイル値を変更できない。</span><span class="sxs-lookup"><span data-stu-id="9d83a-185">You can't modify the existing blocked URL or file values within an entry.</span></span> <span data-ttu-id="9d83a-186">これらの値を変更するには、エントリを削除して再作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9d83a-186">To modify these values, you need to delete and recreate the entry.</span></span>

1. <span data-ttu-id="9d83a-187">セキュリティ 管理コンプライアンス センター&、[**脅威管理ポリシー** ] [テナントの許可 \>  \> **/ブロックリスト] に移動します**。</span><span class="sxs-lookup"><span data-stu-id="9d83a-187">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="9d83a-188">**[URL] タブまたは [** ファイル] タブ **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="9d83a-188">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="9d83a-189">変更するブロック エントリを選択し、[編集] アイコン **を** ![ クリックします ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) 。</span><span class="sxs-lookup"><span data-stu-id="9d83a-189">Select the block entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span>

4. <span data-ttu-id="9d83a-190">表示されるフライアウトで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="9d83a-190">In the flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="9d83a-191">**有効期限が切れる** ことはありません: 次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="9d83a-191">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="9d83a-192">設定がオフ (トグルオフ) になっていることを確認し、[有効期限] ボックスを使用してエントリの ![ ](../../media/scc-toggle-off.png) 有効期限を指定します。 </span><span class="sxs-lookup"><span data-stu-id="9d83a-192">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entry.</span></span>

       <span data-ttu-id="9d83a-193">または</span><span class="sxs-lookup"><span data-stu-id="9d83a-193">or</span></span>

     - <span data-ttu-id="9d83a-194">切り替えボタンを右に移動して、有効期限が切れなきエントリを構成します。</span><span class="sxs-lookup"><span data-stu-id="9d83a-194">Move the toggle to the right to configure the entry to never expire:</span></span> ![オンに切り替え](../../media/scc-toggle-on.png)<span data-ttu-id="9d83a-196">.</span><span class="sxs-lookup"><span data-stu-id="9d83a-196">.</span></span>

   - <span data-ttu-id="9d83a-197">**省略可能なメモ**: エントリの説明テキストを入力します。</span><span class="sxs-lookup"><span data-stu-id="9d83a-197">**Optional note**: Enter descriptive text for the entry.</span></span>

5. <span data-ttu-id="9d83a-198">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9d83a-198">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-block-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="9d83a-199">テナント許可/&リストからブロック エントリを削除するには、セキュリティ コンプライアンス センターを使用します。</span><span class="sxs-lookup"><span data-stu-id="9d83a-199">Use the Security & Compliance Center to remove block entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="9d83a-200">セキュリティ 管理コンプライアンス センター&、[**脅威管理ポリシー** ] [テナントの許可 \>  \> **/ブロックリスト] に移動します**。</span><span class="sxs-lookup"><span data-stu-id="9d83a-200">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="9d83a-201">**[URL] タブまたは [** ファイル] タブ **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="9d83a-201">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="9d83a-202">削除するブロック エントリを選択し、[削除] アイコン **を** ![ クリックします ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) 。</span><span class="sxs-lookup"><span data-stu-id="9d83a-202">Select the block entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="9d83a-203">表示される警告ダイアログで、[削除] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="9d83a-203">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="9d83a-204">Exchange Online PowerShell またはスタンドアロン EOP PowerShell を使用してテナントの許可/ブロックリストを構成する</span><span class="sxs-lookup"><span data-stu-id="9d83a-204">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-block-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="9d83a-205">PowerShell を使用してテナント許可/ブロック一覧にブロック エントリを追加する</span><span class="sxs-lookup"><span data-stu-id="9d83a-205">Use PowerShell to add block entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="9d83a-206">テナント許可/ブロック一覧にブロック エントリを追加するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="9d83a-206">To add block entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType <Url | FileHash> -Block -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="9d83a-207">次の使用例は、contoso.com およびすべてのサブドメイン (contoso.com、www.contoso.com、および xyz.abc.contoso.com) のブロック URL エントリを追加します。</span><span class="sxs-lookup"><span data-stu-id="9d83a-207">This example adds a block URL entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="9d83a-208">ExpirationDate パラメーターまたは NoExpiration パラメーターを使用しないので、エントリは 30 日後に期限切れになります。</span><span class="sxs-lookup"><span data-stu-id="9d83a-208">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItems -ListType Url -Block -Entries ~contoso.com
```

<span data-ttu-id="9d83a-209">次の使用例は、有効期限が切れることはありません指定したファイルのブロック ファイル エントリを追加します。</span><span class="sxs-lookup"><span data-stu-id="9d83a-209">This example adds a block file entry for the specified files that never expires.</span></span>

```powershell
New-TenantAllowBlockListItems -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

<span data-ttu-id="9d83a-210">構文とパラメーターの詳細については [、「New-TenantAllowBlockListItems」を参照してください](/powershell/module/exchange/new-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="9d83a-210">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="9d83a-211">PowerShell を使用してテナント許可/ブロック一覧のエントリを表示する</span><span class="sxs-lookup"><span data-stu-id="9d83a-211">Use PowerShell to view entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="9d83a-212">テナント許可/ブロック一覧のエントリを表示するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="9d83a-212">To view entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType <Url | FileHash> [-Entry <URLValue | FileHashValue>] [-Block] [-ExpirationDate <DateTime>] [-NoExpiration]
```

<span data-ttu-id="9d83a-213">この例では、ブロックされているすべての URL を返します。</span><span class="sxs-lookup"><span data-stu-id="9d83a-213">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Block
```

<span data-ttu-id="9d83a-214">次の使用例は、指定したファイル ハッシュ値の情報を返します。</span><span class="sxs-lookup"><span data-stu-id="9d83a-214">This example returns information for the specified file hash value.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

<span data-ttu-id="9d83a-215">構文とパラメーターの詳細については [、「Get-TenantAllowBlockListItems」を参照してください](/powershell/module/exchange/get-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="9d83a-215">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-block-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="9d83a-216">PowerShell を使用してテナント許可/ブロック一覧のブロック エントリを変更する</span><span class="sxs-lookup"><span data-stu-id="9d83a-216">Use PowerShell to modify block entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="9d83a-217">ブロック エントリ内の既存の URL またはファイル値を変更できない。</span><span class="sxs-lookup"><span data-stu-id="9d83a-217">You can't modify the existing URL or file values within a block entry.</span></span> <span data-ttu-id="9d83a-218">これらの値を変更するには、エントリを削除して再作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9d83a-218">To modify these values, you need to delete and recreate the entry.</span></span>

<span data-ttu-id="9d83a-219">テナント許可/ブロック一覧のブロック エントリを変更するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="9d83a-219">To modify block entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN"> [-Block] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="9d83a-220">次の使用例は、指定したブロック エントリの有効期限を変更します。</span><span class="sxs-lookup"><span data-stu-id="9d83a-220">This example changes the expiration date of the specified block entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

<span data-ttu-id="9d83a-221">構文とパラメーターの詳細については [、「Set-TenantAllowBlockListItems」を参照してください](/powershell/module/exchange/set-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="9d83a-221">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-block-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="9d83a-222">PowerShell を使用してテナント許可/ブロック一覧からブロック エントリを削除する</span><span class="sxs-lookup"><span data-stu-id="9d83a-222">Use PowerShell to remove block entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="9d83a-223">テナント許可/ブロック一覧からブロック エントリを削除するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="9d83a-223">To remove block entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="9d83a-224">次の使用例は、指定したブロック URL エントリをテナント許可/ブロック一覧から削除します。</span><span class="sxs-lookup"><span data-stu-id="9d83a-224">This example removes the specified block URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="9d83a-225">構文とパラメーターの詳細については [、「Remove-TenantAllowBlockListItems」を参照してください](/powershell/module/exchange/remove-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="9d83a-225">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="9d83a-226">テナント許可/ブロック一覧の URL 構文</span><span class="sxs-lookup"><span data-stu-id="9d83a-226">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="9d83a-227">IP4v および IPv6 アドレスは許可されますが、TCP/UDP ポートは許可されません。</span><span class="sxs-lookup"><span data-stu-id="9d83a-227">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="9d83a-228">ファイル名の拡張子は許可されません (たとえば、test.pdf)。</span><span class="sxs-lookup"><span data-stu-id="9d83a-228">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="9d83a-229">Unicode はサポートされていませんが、Punycode はです。</span><span class="sxs-lookup"><span data-stu-id="9d83a-229">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="9d83a-230">ホスト名は、次のすべてのステートメントが true の場合に許可されます。</span><span class="sxs-lookup"><span data-stu-id="9d83a-230">Hostnames are allowed if all of the following statements are true:</span></span>
  - <span data-ttu-id="9d83a-231">ホスト名にはピリオドが含まれる。</span><span class="sxs-lookup"><span data-stu-id="9d83a-231">The hostname contains a period.</span></span>
  - <span data-ttu-id="9d83a-232">ピリオドの左側に少なくとも 1 つの文字があります。</span><span class="sxs-lookup"><span data-stu-id="9d83a-232">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="9d83a-233">ピリオドの右側には、少なくとも 2 つの文字があります。</span><span class="sxs-lookup"><span data-stu-id="9d83a-233">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="9d83a-234">たとえば、 `t.co` 許可されている、または `.com` `contoso.` 許可されない。</span><span class="sxs-lookup"><span data-stu-id="9d83a-234">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="9d83a-235">サブパスは暗黙的ではありません。</span><span class="sxs-lookup"><span data-stu-id="9d83a-235">Subpaths are not implied.</span></span>

  <span data-ttu-id="9d83a-236">たとえば、 `contoso.com` は含めではありません `contoso.com/a` 。</span><span class="sxs-lookup"><span data-stu-id="9d83a-236">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="9d83a-237">ワイルドカード (\*) は、次のシナリオで使用できます。</span><span class="sxs-lookup"><span data-stu-id="9d83a-237">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="9d83a-238">サブドメインを指定するには、左のワイルドカードの後にピリオドを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9d83a-238">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="9d83a-239">たとえば、 `*.contoso.com` 許可されます。 `*contoso.com` 許可されません。</span><span class="sxs-lookup"><span data-stu-id="9d83a-239">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="9d83a-240">パスを指定するには、右のワイルドカードがスラッシュ (/) に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="9d83a-240">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="9d83a-241">たとえば、 `contoso.com/*` 許可されている、または `contoso.com*` `contoso.com/ab*` 許可されない。</span><span class="sxs-lookup"><span data-stu-id="9d83a-241">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="9d83a-242">すべてのサブパスは、適切なワイルドカードによって暗示されるものではありません。</span><span class="sxs-lookup"><span data-stu-id="9d83a-242">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="9d83a-243">たとえば、 `contoso.com/*` は含めではありません `contoso.com/a` 。</span><span class="sxs-lookup"><span data-stu-id="9d83a-243">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="9d83a-244">`*.com*` は無効です (解決可能なドメインではなく、右のワイルドカードはスラッシュに従います)。</span><span class="sxs-lookup"><span data-stu-id="9d83a-244">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="9d83a-245">IP アドレスではワイルドカードは使用できません。</span><span class="sxs-lookup"><span data-stu-id="9d83a-245">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="9d83a-246">チルダ (~) 文字は、次のシナリオで使用できます。</span><span class="sxs-lookup"><span data-stu-id="9d83a-246">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="9d83a-247">左チルダは、ドメインとすべてのサブドメインを意味します。</span><span class="sxs-lookup"><span data-stu-id="9d83a-247">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="9d83a-248">たとえば `~contoso.com` 、includes `contoso.com` と `*.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="9d83a-248">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="9d83a-249">URL エントリは、すべてのプロトコルに適用されるので、プロトコルを含む URL エントリ (たとえば `http://` `https://` `ftp://` 、) は失敗します。</span><span class="sxs-lookup"><span data-stu-id="9d83a-249">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="9d83a-250">ユーザー名またはパスワードはサポートされていないか、必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="9d83a-250">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="9d83a-251">引用符 (' または ") は無効な文字です。</span><span class="sxs-lookup"><span data-stu-id="9d83a-251">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="9d83a-252">URL には、可能な限りすべてのリダイレクトが含まれる必要があります。</span><span class="sxs-lookup"><span data-stu-id="9d83a-252">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="9d83a-253">URL エントリのシナリオ</span><span class="sxs-lookup"><span data-stu-id="9d83a-253">URL entry scenarios</span></span>

<span data-ttu-id="9d83a-254">有効な URL エントリとその結果については、次のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="9d83a-254">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="9d83a-255">シナリオ: ワイルドカードなし</span><span class="sxs-lookup"><span data-stu-id="9d83a-255">Scenario: No wildcards</span></span>

<span data-ttu-id="9d83a-256">**エントリ**: `contoso.com`</span><span class="sxs-lookup"><span data-stu-id="9d83a-256">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="9d83a-257">**一致を許可** する : contoso.com</span><span class="sxs-lookup"><span data-stu-id="9d83a-257">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="9d83a-258">**[一致しない] を許可します**。</span><span class="sxs-lookup"><span data-stu-id="9d83a-258">**Allow not matched**:</span></span>

  - <span data-ttu-id="9d83a-259">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="9d83a-259">abc-contoso.com</span></span>
  - <span data-ttu-id="9d83a-260">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="9d83a-260">contoso.com/a</span></span>
  - <span data-ttu-id="9d83a-261">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9d83a-261">payroll.contoso.com</span></span>
  - <span data-ttu-id="9d83a-262">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="9d83a-262">test.com/contoso.com</span></span>
  - <span data-ttu-id="9d83a-263">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="9d83a-263">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="9d83a-264">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9d83a-264">www.contoso.com</span></span>
  - <span data-ttu-id="9d83a-265">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="9d83a-265">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="9d83a-266">**ブロック一致**:</span><span class="sxs-lookup"><span data-stu-id="9d83a-266">**Block match**:</span></span>

  - <span data-ttu-id="9d83a-267">contoso.com</span><span class="sxs-lookup"><span data-stu-id="9d83a-267">contoso.com</span></span>
  - <span data-ttu-id="9d83a-268">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="9d83a-268">contoso.com/a</span></span>
  - <span data-ttu-id="9d83a-269">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9d83a-269">payroll.contoso.com</span></span>
  - <span data-ttu-id="9d83a-270">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="9d83a-270">test.com/contoso.com</span></span>
  - <span data-ttu-id="9d83a-271">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="9d83a-271">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="9d83a-272">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9d83a-272">www.contoso.com</span></span>
  - <span data-ttu-id="9d83a-273">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="9d83a-273">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="9d83a-274">**ブロックが一致しない**: abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="9d83a-274">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="9d83a-275">シナリオ: 左ワイルドカード (サブドメイン)</span><span class="sxs-lookup"><span data-stu-id="9d83a-275">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="9d83a-276">**エントリ**: `*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="9d83a-276">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="9d83a-277">**一致とブロック** の **一致を許可する**:</span><span class="sxs-lookup"><span data-stu-id="9d83a-277">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="9d83a-278">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9d83a-278">www.contoso.com</span></span>
  - <span data-ttu-id="9d83a-279">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9d83a-279">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="9d83a-280">**[一致しない] と** [ **ブロックが一致しない] を許可します**。</span><span class="sxs-lookup"><span data-stu-id="9d83a-280">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="9d83a-281">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="9d83a-281">123contoso.com</span></span>
  - <span data-ttu-id="9d83a-282">contoso.com</span><span class="sxs-lookup"><span data-stu-id="9d83a-282">contoso.com</span></span>
  - <span data-ttu-id="9d83a-283">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="9d83a-283">test.com/contoso.com</span></span>
  - <span data-ttu-id="9d83a-284">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="9d83a-284">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="9d83a-285">シナリオ: パスの上部にある右のワイルドカード</span><span class="sxs-lookup"><span data-stu-id="9d83a-285">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="9d83a-286">**エントリ**: `contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="9d83a-286">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="9d83a-287">**一致とブロック** の **一致を許可する**:</span><span class="sxs-lookup"><span data-stu-id="9d83a-287">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="9d83a-288">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="9d83a-288">contoso.com/a/b</span></span>
  - <span data-ttu-id="9d83a-289">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="9d83a-289">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="9d83a-290">contoso.com/a/?q=joe@t.com</span><span class="sxs-lookup"><span data-stu-id="9d83a-290">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="9d83a-291">**[一致しない] と** [ **ブロックが一致しない] を許可します**。</span><span class="sxs-lookup"><span data-stu-id="9d83a-291">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="9d83a-292">contoso.com</span><span class="sxs-lookup"><span data-stu-id="9d83a-292">contoso.com</span></span>
  - <span data-ttu-id="9d83a-293">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="9d83a-293">contoso.com/a</span></span>
  - <span data-ttu-id="9d83a-294">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9d83a-294">www.contoso.com</span></span>
  - <span data-ttu-id="9d83a-295">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="9d83a-295">www.contoso.com/q=a@contoso.com</span></span>

#### <a name="scenario-left-tilde"></a><span data-ttu-id="9d83a-296">シナリオ: 左チルダ</span><span class="sxs-lookup"><span data-stu-id="9d83a-296">Scenario: Left tilde</span></span>

<span data-ttu-id="9d83a-297">**エントリ**: `~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="9d83a-297">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="9d83a-298">**一致とブロック** の **一致を許可する**:</span><span class="sxs-lookup"><span data-stu-id="9d83a-298">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="9d83a-299">contoso.com</span><span class="sxs-lookup"><span data-stu-id="9d83a-299">contoso.com</span></span>
  - <span data-ttu-id="9d83a-300">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9d83a-300">www.contoso.com</span></span>
  - <span data-ttu-id="9d83a-301">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9d83a-301">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="9d83a-302">**[一致しない] と** [ **ブロックが一致しない] を許可します**。</span><span class="sxs-lookup"><span data-stu-id="9d83a-302">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="9d83a-303">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="9d83a-303">123contoso.com</span></span>
  - <span data-ttu-id="9d83a-304">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="9d83a-304">contoso.com/abc</span></span>
  - <span data-ttu-id="9d83a-305">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="9d83a-305">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="9d83a-306">シナリオ: 右のワイルドカード サフィックス</span><span class="sxs-lookup"><span data-stu-id="9d83a-306">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="9d83a-307">**エントリ**: `contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="9d83a-307">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="9d83a-308">**一致とブロック** の **一致を許可する**:</span><span class="sxs-lookup"><span data-stu-id="9d83a-308">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="9d83a-309">contoso.com/?q=whatever@fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="9d83a-309">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="9d83a-310">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="9d83a-310">contoso.com/a</span></span>
  - <span data-ttu-id="9d83a-311">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="9d83a-311">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="9d83a-312">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="9d83a-312">contoso.com/ab</span></span>
  - <span data-ttu-id="9d83a-313">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="9d83a-313">contoso.com/b</span></span>
  - <span data-ttu-id="9d83a-314">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="9d83a-314">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="9d83a-315">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="9d83a-315">contoso.com/ba</span></span>

- <span data-ttu-id="9d83a-316">**[一致しない] と** **[ブロックが一致しない**] : contoso.com</span><span class="sxs-lookup"><span data-stu-id="9d83a-316">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="9d83a-317">シナリオ: 左ワイルドカード サブドメインと右のワイルドカード サフィックス</span><span class="sxs-lookup"><span data-stu-id="9d83a-317">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="9d83a-318">**エントリ**: `*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="9d83a-318">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="9d83a-319">**一致とブロック** の **一致を許可する**:</span><span class="sxs-lookup"><span data-stu-id="9d83a-319">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="9d83a-320">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="9d83a-320">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="9d83a-321">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="9d83a-321">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="9d83a-322">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="9d83a-322">www.contoso.com/a</span></span>
  - <span data-ttu-id="9d83a-323">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="9d83a-323">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="9d83a-324">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="9d83a-324">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="9d83a-325">**[一致しない] と** **[ブロックが一致しない**] : contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="9d83a-325">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="9d83a-326">シナリオ: 左右のチルダ</span><span class="sxs-lookup"><span data-stu-id="9d83a-326">Scenario: Left and right tilde</span></span>

<span data-ttu-id="9d83a-327">**エントリ**: `~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="9d83a-327">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="9d83a-328">**一致とブロック** の **一致を許可する**:</span><span class="sxs-lookup"><span data-stu-id="9d83a-328">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="9d83a-329">contoso.com</span><span class="sxs-lookup"><span data-stu-id="9d83a-329">contoso.com</span></span>
  - <span data-ttu-id="9d83a-330">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="9d83a-330">contoso.com/a</span></span>
  - <span data-ttu-id="9d83a-331">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9d83a-331">www.contoso.com</span></span>
  - <span data-ttu-id="9d83a-332">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="9d83a-332">www.contoso.com/b</span></span>
  - <span data-ttu-id="9d83a-333">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9d83a-333">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="9d83a-334">**[一致しない] と** [ **ブロックが一致しない] を許可します**。</span><span class="sxs-lookup"><span data-stu-id="9d83a-334">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="9d83a-335">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="9d83a-335">123contoso.com</span></span>
  - <span data-ttu-id="9d83a-336">contoso.org</span><span class="sxs-lookup"><span data-stu-id="9d83a-336">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="9d83a-337">シナリオ: IP アドレス</span><span class="sxs-lookup"><span data-stu-id="9d83a-337">Scenario: IP address</span></span>

<span data-ttu-id="9d83a-338">**エントリ**: `1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="9d83a-338">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="9d83a-339">**一致と\*\*\*\*ブロックの一** 致を許可する : 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="9d83a-339">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="9d83a-340">**[一致しない] と** [ **ブロックが一致しない] を許可します**。</span><span class="sxs-lookup"><span data-stu-id="9d83a-340">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="9d83a-341">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="9d83a-341">1.2.3.4/a</span></span>
  - <span data-ttu-id="9d83a-342">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="9d83a-342">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="9d83a-343">適切なワイルドカードを持つ IP アドレス</span><span class="sxs-lookup"><span data-stu-id="9d83a-343">IP address with right wildcard</span></span>

<span data-ttu-id="9d83a-344">**エントリ**: `1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="9d83a-344">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="9d83a-345">**一致とブロック** の **一致を許可する**:</span><span class="sxs-lookup"><span data-stu-id="9d83a-345">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="9d83a-346">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="9d83a-346">1.2.3.4/b</span></span>
  - <span data-ttu-id="9d83a-347">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="9d83a-347">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="9d83a-348">無効なエントリの例</span><span class="sxs-lookup"><span data-stu-id="9d83a-348">Examples of invalid entries</span></span>

<span data-ttu-id="9d83a-349">次のエントリが無効です。</span><span class="sxs-lookup"><span data-stu-id="9d83a-349">The following entries are invalid:</span></span>

- <span data-ttu-id="9d83a-350">**ドメイン値が見つからないか無効です**。</span><span class="sxs-lookup"><span data-stu-id="9d83a-350">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="9d83a-351">contoso</span><span class="sxs-lookup"><span data-stu-id="9d83a-351">contoso</span></span>
  - <span data-ttu-id="9d83a-352">\*.contoso.\*</span><span class="sxs-lookup"><span data-stu-id="9d83a-352">\*.contoso.\*</span></span>
  - <span data-ttu-id="9d83a-353">\*.com</span><span class="sxs-lookup"><span data-stu-id="9d83a-353">\*.com</span></span>
  - <span data-ttu-id="9d83a-354">\*.pdf</span><span class="sxs-lookup"><span data-stu-id="9d83a-354">\*.pdf</span></span>

- <span data-ttu-id="9d83a-355">**テキストまたはスペース文字なしのワイルドカード**:</span><span class="sxs-lookup"><span data-stu-id="9d83a-355">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="9d83a-356">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="9d83a-356">\*contoso.com</span></span>
  - <span data-ttu-id="9d83a-357">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="9d83a-357">contoso.com\*</span></span>
  - <span data-ttu-id="9d83a-358">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="9d83a-358">\*1.2.3.4</span></span>
  - <span data-ttu-id="9d83a-359">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="9d83a-359">1.2.3.4\*</span></span>
  - <span data-ttu-id="9d83a-360">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="9d83a-360">contoso.com/a\*</span></span>
  - <span data-ttu-id="9d83a-361">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="9d83a-361">contoso.com/ab\*</span></span>

- <span data-ttu-id="9d83a-362">**ポートを含む IP アドレス**:</span><span class="sxs-lookup"><span data-stu-id="9d83a-362">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="9d83a-363">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="9d83a-363">contoso.com:443</span></span>
  - <span data-ttu-id="9d83a-364">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="9d83a-364">abc.contoso.com:25</span></span>

- <span data-ttu-id="9d83a-365">**説明的でないワイルドカード**:</span><span class="sxs-lookup"><span data-stu-id="9d83a-365">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="9d83a-366">\*.\*</span><span class="sxs-lookup"><span data-stu-id="9d83a-366">\*.\*</span></span>

- <span data-ttu-id="9d83a-367">**中央のワイルドカード**:</span><span class="sxs-lookup"><span data-stu-id="9d83a-367">**Middle wildcards**:</span></span>

  - <span data-ttu-id="9d83a-368">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="9d83a-368">conto\*so.com</span></span>
  - <span data-ttu-id="9d83a-369">conto~so.com</span><span class="sxs-lookup"><span data-stu-id="9d83a-369">conto~so.com</span></span>

- <span data-ttu-id="9d83a-370">**2 つのワイルドカード**</span><span class="sxs-lookup"><span data-stu-id="9d83a-370">**Double wildcards**</span></span>

  - <span data-ttu-id="9d83a-371">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="9d83a-371">contoso.com/\*\*</span></span>
  - <span data-ttu-id="9d83a-372">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="9d83a-372">contoso.com/\*/\*</span></span>