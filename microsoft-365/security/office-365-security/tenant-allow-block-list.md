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
ms.openlocfilehash: 960fbf26b610485fb46c935b04aedcc593b85752
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/03/2021
ms.locfileid: "50407252"
---
# <a name="manage-the-tenant-allowblock-list"></a><span data-ttu-id="ca8bd-103">テナントの許可/禁止リストの URL を管理する</span><span class="sxs-lookup"><span data-stu-id="ca8bd-103">Manage the Tenant Allow/Block List</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="ca8bd-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="ca8bd-104">**Applies to**</span></span>
- [<span data-ttu-id="ca8bd-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="ca8bd-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="ca8bd-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="ca8bd-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="ca8bd-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ca8bd-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

> [!NOTE]
>
> <span data-ttu-id="ca8bd-108">この記事で説明する機能はプレビューで、変更される可能性があります。一部の組織では利用できません。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-108">The features described in this article are in Preview, are subject to change, and are not available in all organizations.</span></span>
>
> <span data-ttu-id="ca8bd-109">現時点 **では、テナント** 許可/ブロック一覧で許可アイテムを構成できません。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-109">You can't **configure** allowed items in the Tenant Allow/Block List at this time.</span></span>

<span data-ttu-id="ca8bd-110">Exchange Online またはスタンドアロンの Exchange Online Protection (EOP) 組織に Exchange Online メールボックスがない Microsoft 365 組織では、EOP フィルターの評決に同意しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-110">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="ca8bd-111">たとえば、メッセージが正しい (誤検知) とマークされている場合や、悪いメッセージが許可される場合があります (偽陰性)。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-111">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="ca8bd-112">セキュリティ コンプライアンス センターのテナント許可/ブロック一覧&、Microsoft 365 フィルターの評決を手動で上書きする方法が提供されます。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-112">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="ca8bd-113">テナント許可/ブロック一覧は、メール フロー中およびユーザークリック時に使用されます。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-113">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="ca8bd-114">常にブロックする URL またはファイルを指定できます。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-114">You can specify URLs or files to always block.</span></span>

<span data-ttu-id="ca8bd-115">この記事では、セキュリティ & コンプライアンス センターまたは PowerShell (Exchange Online のメールボックスを持つ Microsoft 365 組織向け Exchange Online PowerShell、Exchange Online メールボックスのない組織のスタンドアロン EOP PowerShell) のテナント許可/ブロック一覧のエントリを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-115">This article describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="ca8bd-116">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="ca8bd-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="ca8bd-117"><https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-117">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="ca8bd-118">[テナントの許可/ブロック **リスト] ページに直接移動するには** 、 を使用します <https://protection.office.com/tenantAllowBlockList> 。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-118">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="ca8bd-119">ファイルを指定するには、ファイルの SHA256 ハッシュ値を使用します。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-119">You specify files by using the SHA256 hash value of the file.</span></span> <span data-ttu-id="ca8bd-120">Windows でファイルの SHA256 ハッシュ値を検索するには、コマンド プロンプトで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-120">To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt:</span></span>

  ```dos
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  <span data-ttu-id="ca8bd-121">値の例は、 です `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` 。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-121">An example value is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`.</span></span> <span data-ttu-id="ca8bd-122">知覚ハッシュ (pHash) の値はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-122">Perceptual hash (pHash) values are not supported.</span></span>

- <span data-ttu-id="ca8bd-123">使用可能な URL 値については、この記事の後半の「 [テナント許可/](#url-syntax-for-the-tenant-allowblock-list) ブロック一覧」セクションの URL 構文で説明します。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-123">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

- <span data-ttu-id="ca8bd-124">テナント許可/ブロック一覧では、URL に対して最大 500 エントリ、ファイル ハッシュのエントリを 500 エントリまで使用できます。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-124">The Tenant Allow/Block List allows a maximum of 500 entries for URLs, and 500 entries for file hashes.</span></span>

- <span data-ttu-id="ca8bd-125">エントリは 15 分以内にアクティブである必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-125">An entry should be active within 15 minutes.</span></span>

- <span data-ttu-id="ca8bd-126">既定では、テナント許可/ブロック一覧のエントリは 30 日後に期限切れになります。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-126">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="ca8bd-127">日付を指定するか、有効期限が切れることはありません。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-127">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="ca8bd-128">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-128">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="ca8bd-129">スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-129">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="ca8bd-130">この記事の手順を実行するには **、Exchange Online** でアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-130">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="ca8bd-131">テナント許可/ブロック一覧の値を追加および削除するには、組織の管理またはセキュリティ管理者の役割グループのメンバー **である** 必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-131">To add and remove values from the Tenant Allow/Block List, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="ca8bd-132">テナント許可/ブロック一覧への読み取り専用アクセスでは、グローバル リーダーまたはセキュリティリーダーの役割グループの **メンバーである** 必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-132">For read-only access to the Tenant Allow/Block List, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="ca8bd-133">詳細については、「[Exchange Online のアクセス許可](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-133">For more information, see [Permissions in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="ca8bd-134">**注**:</span><span class="sxs-lookup"><span data-stu-id="ca8bd-134">**Notes**:</span></span>

  - <span data-ttu-id="ca8bd-135">Microsoft 365 管理センターの対応する Azure Active Directory ロールにユーザーを追加すると、Microsoft 365 の他の機能に必要なアクセス許可とアクセス許可がユーザーに付与されます。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-135">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="ca8bd-136">詳細については、「[管理者の役割について](../../admin/add-users/about-admin-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-136">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="ca8bd-137">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)の **閲覧専用の組織管理** の役割グループが この機能への読み取り専用アクセス権も付与します。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-137">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="ca8bd-138">テナント許可/&リストに URL エントリを作成するには、セキュリティ コンプライアンス センターを使用します。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-138">Use the Security & Compliance Center to create URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="ca8bd-139">URL エントリの構文の詳細については、この記事の後半の「テナント許可/ブロック一覧」セクションの [URL](#url-syntax-for-the-tenant-allowblock-list) 構文を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-139">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

1. <span data-ttu-id="ca8bd-140">セキュリティ 管理コンプライアンス センター&、[**脅威管理ポリシー** ] [テナントの許可 \>  \> **/ブロックリスト] に移動します**。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-140">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="ca8bd-141">[テナントの **許可/ブロック一覧** ] ページで **、[URL]** タブが選択されているのを確認し、[ブロック] を **クリックします。**</span><span class="sxs-lookup"><span data-stu-id="ca8bd-141">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Block**</span></span>

3. <span data-ttu-id="ca8bd-142">表示される **[URL のブロック]** フライアウトで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-142">In the **Block URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="ca8bd-143">**ブロックする URL を追加する**: 1 行に 1 つの URL を入力し、最大 20 を入力します。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-143">**Add URLs to block**: Enter one URL per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="ca8bd-144">**有効期限が切れる** ことはありません: 次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-144">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="ca8bd-145">設定がオフ (トグルオフ) になっていることを確認し、[有効期限] ボックスを使用してエントリの有効期限 ![ ](../../media/scc-toggle-off.png) を指定します。 </span><span class="sxs-lookup"><span data-stu-id="ca8bd-145">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="ca8bd-146">または</span><span class="sxs-lookup"><span data-stu-id="ca8bd-146">or</span></span>

     - <span data-ttu-id="ca8bd-147">切り替えボタンを右に移動して、有効期限が切れなきエントリを構成します。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-147">Move the toggle to the right to configure the entries to never expire:</span></span> ![オンに切り替え](../../media/scc-toggle-on.png)<span data-ttu-id="ca8bd-149">.</span><span class="sxs-lookup"><span data-stu-id="ca8bd-149">.</span></span>

   - <span data-ttu-id="ca8bd-150">**省略可能な** メモ: エントリの説明テキストを入力します。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-150">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="ca8bd-151">完了したら、**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-151">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="ca8bd-152">テナント許可/&リストにファイル エントリを作成するには、セキュリティ コンプライアンス センターを使用します。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-152">Use the Security & Compliance Center to create file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="ca8bd-153">セキュリティ 管理コンプライアンス センター&、[**脅威管理ポリシー** ] [テナントの許可 \>  \> **/ブロックリスト] に移動します**。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-153">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="ca8bd-154">[テナントの **許可/ブロックリスト] ページで** 、[ **ファイル]** タブを選択し、[ブロック] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-154">On the **Tenant Allow/Block List** page, select **Files** tab, and then click **Block**.</span></span>

3. <span data-ttu-id="ca8bd-155">表示される **[ファイルを追加してブロック** する] フライアウトで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-155">In the **Add files to block** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="ca8bd-156">**ファイル ハッシュの追加**: 1 行に 1 つの SHA256 ハッシュ値を入力し、最大 20 を入力します。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-156">**Add file hashes**: Enter one SHA256 hash value per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="ca8bd-157">**有効期限が切れる** ことはありません: 次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-157">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="ca8bd-158">設定がオフ (トグルオフ) になっていることを確認し、[有効期限] ボックスを使用してエントリの有効期限 ![ ](../../media/scc-toggle-off.png) を指定します。 </span><span class="sxs-lookup"><span data-stu-id="ca8bd-158">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="ca8bd-159">または</span><span class="sxs-lookup"><span data-stu-id="ca8bd-159">or</span></span>

     - <span data-ttu-id="ca8bd-160">切り替えボタンを右に移動して、有効期限が切れなきエントリを構成します。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-160">Move the toggle to the right to configure the entries to never expire:</span></span> ![オンに切り替え](../../media/scc-toggle-on.png)<span data-ttu-id="ca8bd-162">.</span><span class="sxs-lookup"><span data-stu-id="ca8bd-162">.</span></span>

   - <span data-ttu-id="ca8bd-163">**省略可能な** メモ: エントリの説明テキストを入力します。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-163">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="ca8bd-164">完了したら、**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-164">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="ca8bd-165">テナント許可/&リストのエントリを表示するには、セキュリティ コンプライアンス センターを使用します。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-165">Use the Security & Compliance Center to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="ca8bd-166">セキュリティ 管理コンプライアンス センター&、[**脅威管理ポリシー** ] [テナントの許可 \>  \> **/ブロックリスト] に移動します**。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-166">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="ca8bd-167">**[URL] タブまたは [** ファイル] タブ **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-167">Select the **URLs** tab or the **Files** tab.</span></span>

<span data-ttu-id="ca8bd-168">昇順または降順で並べ替えるには、次の列見出しをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-168">Click on the following column headings to sort in ascending or descending order:</span></span>

- <span data-ttu-id="ca8bd-169">**値**: URL またはファイル ハッシュ。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-169">**Value**: The URL or the file hash.</span></span>
- <span data-ttu-id="ca8bd-170">**最終更新日**</span><span class="sxs-lookup"><span data-stu-id="ca8bd-170">**Last updated date**</span></span>
- <span data-ttu-id="ca8bd-171">**有効期限**</span><span class="sxs-lookup"><span data-stu-id="ca8bd-171">**Expiration date**</span></span>
- <span data-ttu-id="ca8bd-172">**注**</span><span class="sxs-lookup"><span data-stu-id="ca8bd-172">**Note**</span></span>

<span data-ttu-id="ca8bd-173">[ **検索]** をクリックし、値のすべてまたは一部を入力し、Enter キーを押して特定の値を検索します。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-173">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="ca8bd-174">完了したら、[検索のクリア] **アイコン** ![ をクリックします ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) 。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-174">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

<span data-ttu-id="ca8bd-175">[フィルター **] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-175">Click **Filter**.</span></span> <span data-ttu-id="ca8bd-176">表示される **[フィルター** ] フライアウトで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-176">In the **Filter** flyout that appears, configure any of the following settings:</span></span>

- <span data-ttu-id="ca8bd-177">**有効期限が切** れることはありません: [オフ] を ![ 選択します。オフ ](../../media/scc-toggle-off.png) またはオンに切り替えます。 ![ ](../../media/scc-toggle-on.png)</span><span class="sxs-lookup"><span data-stu-id="ca8bd-177">**Never expire**: Select off: ![Toggle off](../../media/scc-toggle-off.png) or on: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

- <span data-ttu-id="ca8bd-178">**最終更新日 :** 開始日 ( From **)**、終了日 (**To**) または両方を選択します。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-178">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span></span>

- <span data-ttu-id="ca8bd-179">**有効期限 :** 開始日 **(** From ) 、終了日 (**To**) または両方を選択します。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-179">**Expiration date**: Select a start date (**From**), an end date (**To**) or both.</span></span>

<span data-ttu-id="ca8bd-180">完了したら、[適用] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-180">When you're finished, click **Apply**.</span></span>

<span data-ttu-id="ca8bd-181">既存のフィルターをクリアするには、[**フィルター**] をクリックし、表示される [フィルター] フライアウトで 、[フィルターのクリア]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-181">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-block-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="ca8bd-182">テナント許可/&リストのブロック エントリを変更するには、セキュリティ コンプライアンス センターを使用します。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-182">Use the Security & Compliance Center to modify block entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="ca8bd-183">エントリ内の既存のブロックされた URL またはファイル値を変更できない。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-183">You can't modify the existing blocked URL or file values within an entry.</span></span> <span data-ttu-id="ca8bd-184">これらの値を変更するには、エントリを削除して再作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-184">To modify these values, you need to delete and recreate the entry.</span></span>

1. <span data-ttu-id="ca8bd-185">セキュリティ 管理コンプライアンス センター&、[**脅威管理ポリシー** ] [テナントの許可 \>  \> **/ブロックリスト] に移動します**。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-185">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="ca8bd-186">**[URL] タブまたは [** ファイル] タブ **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-186">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="ca8bd-187">変更するブロック エントリを選択し、[編集] アイコン **を** ![ クリックします ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) 。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-187">Select the block entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span>

4. <span data-ttu-id="ca8bd-188">表示されるフライアウトで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-188">In the flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="ca8bd-189">**有効期限が切れる** ことはありません: 次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-189">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="ca8bd-190">設定がオフ (トグルオフ) になっていることを確認し、[有効期限] ボックスを使用してエントリの ![ ](../../media/scc-toggle-off.png) 有効期限を指定します。 </span><span class="sxs-lookup"><span data-stu-id="ca8bd-190">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entry.</span></span>

     <span data-ttu-id="ca8bd-191">または</span><span class="sxs-lookup"><span data-stu-id="ca8bd-191">or</span></span>

     - <span data-ttu-id="ca8bd-192">切り替えボタンを右に移動して、有効期限が切れなきエントリを構成します。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-192">Move the toggle to the right to configure the entry to never expire:</span></span> ![オンに切り替え](../../media/scc-toggle-on.png)<span data-ttu-id="ca8bd-194">.</span><span class="sxs-lookup"><span data-stu-id="ca8bd-194">.</span></span>

   - <span data-ttu-id="ca8bd-195">**省略可能なメモ**: エントリの説明テキストを入力します。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-195">**Optional note**: Enter descriptive text for the entry.</span></span>

5. <span data-ttu-id="ca8bd-196">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-196">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-block-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="ca8bd-197">テナント許可/&リストからブロック エントリを削除するには、セキュリティ コンプライアンス センターを使用します。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-197">Use the Security & Compliance Center to remove block entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="ca8bd-198">セキュリティ 管理コンプライアンス センター&、[**脅威管理ポリシー** ] [テナントの許可 \>  \> **/ブロックリスト] に移動します**。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-198">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="ca8bd-199">**[URL] タブまたは [** ファイル] タブ **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-199">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="ca8bd-200">削除するブロック エントリを選択し、[削除] アイコン **を** ![ クリックします ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) 。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-200">Select the block entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="ca8bd-201">表示される警告ダイアログで、[削除] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-201">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="ca8bd-202">Exchange Online PowerShell またはスタンドアロン EOP PowerShell を使用してテナントの許可/ブロックリストを構成する</span><span class="sxs-lookup"><span data-stu-id="ca8bd-202">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-block-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="ca8bd-203">PowerShell を使用してテナント許可/ブロック一覧にブロック エントリを追加する</span><span class="sxs-lookup"><span data-stu-id="ca8bd-203">Use PowerShell to add block entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="ca8bd-204">テナント許可/ブロック一覧にブロック エントリを追加するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-204">To add block entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType <Url | FileHash> -Block -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="ca8bd-205">次の使用例は、contoso.com およびすべてのサブドメイン (contoso.com、www.contoso.com、および xyz.abc.contoso.com) のブロック URL エントリを追加します。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-205">This example adds a block URL entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="ca8bd-206">ExpirationDate パラメーターまたは NoExpiration パラメーターを使用しないので、エントリは 30 日後に期限切れになります。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-206">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType Url -Block -Entries ~contoso.com
```

<span data-ttu-id="ca8bd-207">次の使用例は、有効期限が切れることはありません指定したファイルのブロック ファイル エントリを追加します。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-207">This example adds a block file entry for the specified files that never expires.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

<span data-ttu-id="ca8bd-208">構文とパラメーターの詳細については [、「New-TenantAllowBlockListItems」を参照してください](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-208">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="ca8bd-209">PowerShell を使用してテナント許可/ブロック一覧のエントリを表示する</span><span class="sxs-lookup"><span data-stu-id="ca8bd-209">Use PowerShell to view entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="ca8bd-210">テナント許可/ブロック一覧のエントリを表示するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-210">To view entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType <Url | FileHash> [-Entry <URLValue | FileHashValue>] [-Block] [-ExpirationDate <DateTime>] [-NoExpiration]
```

<span data-ttu-id="ca8bd-211">この例では、ブロックされているすべての URL を返します。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-211">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Block
```

<span data-ttu-id="ca8bd-212">次の使用例は、指定したファイル ハッシュ値の情報を返します。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-212">This example returns information for the specified file hash value.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

<span data-ttu-id="ca8bd-213">構文とパラメーターの詳細については [、「Get-TenantAllowBlockListItems」を参照してください](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-213">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-block-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="ca8bd-214">PowerShell を使用してテナント許可/ブロック一覧のブロック エントリを変更する</span><span class="sxs-lookup"><span data-stu-id="ca8bd-214">Use PowerShell to modify block entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="ca8bd-215">ブロック エントリ内の既存の URL またはファイル値を変更できない。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-215">You can't modify the existing URL or file values within a block entry.</span></span> <span data-ttu-id="ca8bd-216">これらの値を変更するには、エントリを削除して再作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-216">To modify these values, you need to delete and recreate the entry.</span></span>

<span data-ttu-id="ca8bd-217">テナント許可/ブロック一覧のブロック エントリを変更するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-217">To modify block entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN"> [-Block] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="ca8bd-218">次の使用例は、指定したブロック エントリの有効期限を変更します。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-218">This example changes the expiration date of the specified block entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

<span data-ttu-id="ca8bd-219">構文とパラメーターの詳細については [、「Set-TenantAllowBlockListItems」を参照してください](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-219">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-block-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="ca8bd-220">PowerShell を使用してテナント許可/ブロック一覧からブロック エントリを削除する</span><span class="sxs-lookup"><span data-stu-id="ca8bd-220">Use PowerShell to remove block entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="ca8bd-221">テナント許可/ブロック一覧からブロック エントリを削除するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-221">To remove block entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="ca8bd-222">次の使用例は、指定したブロック URL エントリをテナント許可/ブロック一覧から削除します。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-222">This example removes the specified block URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="ca8bd-223">構文とパラメーターの詳細については [、「Remove-TenantAllowBlockListItems」を参照してください](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-223">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="ca8bd-224">テナント許可/ブロック一覧の URL 構文</span><span class="sxs-lookup"><span data-stu-id="ca8bd-224">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="ca8bd-225">IP4v および IPv6 アドレスは許可されますが、TCP/UDP ポートは許可されません。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-225">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="ca8bd-226">ファイル名の拡張子は許可されません (たとえば、test.pdf)。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-226">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="ca8bd-227">Unicode はサポートされていませんが、Punycode はです。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-227">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="ca8bd-228">ホスト名は、次のすべてのステートメントが true の場合に許可されます。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-228">Hostnames are allowed if all of the following statements are true:</span></span>
  - <span data-ttu-id="ca8bd-229">ホスト名にはピリオドが含まれる。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-229">The hostname contains a period.</span></span>
  - <span data-ttu-id="ca8bd-230">ピリオドの左側に少なくとも 1 つの文字があります。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-230">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="ca8bd-231">ピリオドの右側には、少なくとも 2 つの文字があります。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-231">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="ca8bd-232">たとえば、 `t.co` 許可されている、または `.com` `contoso.` 許可されない。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-232">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="ca8bd-233">サブパスは暗黙的ではありません。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-233">Subpaths are not implied.</span></span>

  <span data-ttu-id="ca8bd-234">たとえば、 `contoso.com` は含めではありません `contoso.com/a` 。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-234">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="ca8bd-235">ワイルドカード (\*) は、次のシナリオで使用できます。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-235">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="ca8bd-236">サブドメインを指定するには、左のワイルドカードの後にピリオドを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-236">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="ca8bd-237">たとえば、 `*.contoso.com` 許可されます。 `*contoso.com` 許可されません。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-237">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="ca8bd-238">パスを指定するには、右のワイルドカードがスラッシュ (/) に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-238">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="ca8bd-239">たとえば、 `contoso.com/*` 許可されている、または `contoso.com*` `contoso.com/ab*` 許可されない。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-239">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="ca8bd-240">すべてのサブパスは、適切なワイルドカードによって暗示されるものではありません。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-240">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="ca8bd-241">たとえば、 `contoso.com/*` は含めではありません `contoso.com/a` 。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-241">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="ca8bd-242">`*.com*` は無効です (解決可能なドメインではなく、右のワイルドカードはスラッシュに従います)。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-242">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="ca8bd-243">IP アドレスではワイルドカードは使用できません。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-243">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="ca8bd-244">チルダ (~) 文字は、次のシナリオで使用できます。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-244">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="ca8bd-245">左チルダは、ドメインとすべてのサブドメインを意味します。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-245">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="ca8bd-246">たとえば `~contoso.com` 、includes `contoso.com` と `*.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="ca8bd-246">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="ca8bd-247">URL エントリは、すべてのプロトコルに適用されるので、プロトコルを含む URL エントリ (たとえば `http://` `https://` `ftp://` 、) は失敗します。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-247">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="ca8bd-248">ユーザー名またはパスワードはサポートされていないか、必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-248">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="ca8bd-249">引用符 (' または ") は無効な文字です。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-249">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="ca8bd-250">URL には、可能な限りすべてのリダイレクトが含まれる必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-250">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="ca8bd-251">URL エントリのシナリオ</span><span class="sxs-lookup"><span data-stu-id="ca8bd-251">URL entry scenarios</span></span>

<span data-ttu-id="ca8bd-252">有効な URL エントリとその結果については、次のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-252">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="ca8bd-253">シナリオ: ワイルドカードなし</span><span class="sxs-lookup"><span data-stu-id="ca8bd-253">Scenario: No wildcards</span></span>

<span data-ttu-id="ca8bd-254">**エントリ**: `contoso.com`</span><span class="sxs-lookup"><span data-stu-id="ca8bd-254">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="ca8bd-255">**一致を許可** する : contoso.com</span><span class="sxs-lookup"><span data-stu-id="ca8bd-255">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="ca8bd-256">**[一致しない] を許可します**。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-256">**Allow not matched**:</span></span>

  - <span data-ttu-id="ca8bd-257">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="ca8bd-257">abc-contoso.com</span></span>
  - <span data-ttu-id="ca8bd-258">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="ca8bd-258">contoso.com/a</span></span>
  - <span data-ttu-id="ca8bd-259">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ca8bd-259">payroll.contoso.com</span></span>
  - <span data-ttu-id="ca8bd-260">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="ca8bd-260">test.com/contoso.com</span></span>
  - <span data-ttu-id="ca8bd-261">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="ca8bd-261">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="ca8bd-262">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ca8bd-262">www.contoso.com</span></span>
  - <span data-ttu-id="ca8bd-263">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="ca8bd-263">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="ca8bd-264">**ブロック一致**:</span><span class="sxs-lookup"><span data-stu-id="ca8bd-264">**Block match**:</span></span>

  - <span data-ttu-id="ca8bd-265">contoso.com</span><span class="sxs-lookup"><span data-stu-id="ca8bd-265">contoso.com</span></span>
  - <span data-ttu-id="ca8bd-266">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="ca8bd-266">contoso.com/a</span></span>
  - <span data-ttu-id="ca8bd-267">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ca8bd-267">payroll.contoso.com</span></span>
  - <span data-ttu-id="ca8bd-268">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="ca8bd-268">test.com/contoso.com</span></span>
  - <span data-ttu-id="ca8bd-269">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="ca8bd-269">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="ca8bd-270">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ca8bd-270">www.contoso.com</span></span>
  - <span data-ttu-id="ca8bd-271">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="ca8bd-271">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="ca8bd-272">**ブロックが一致しない**: abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="ca8bd-272">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="ca8bd-273">シナリオ: 左ワイルドカード (サブドメイン)</span><span class="sxs-lookup"><span data-stu-id="ca8bd-273">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="ca8bd-274">**エントリ**: `*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="ca8bd-274">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="ca8bd-275">**一致とブロック** の **一致を許可する**:</span><span class="sxs-lookup"><span data-stu-id="ca8bd-275">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="ca8bd-276">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ca8bd-276">www.contoso.com</span></span>
  - <span data-ttu-id="ca8bd-277">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ca8bd-277">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="ca8bd-278">**[一致しない] と** [ **ブロックが一致しない] を許可します**。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-278">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="ca8bd-279">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="ca8bd-279">123contoso.com</span></span>
  - <span data-ttu-id="ca8bd-280">contoso.com</span><span class="sxs-lookup"><span data-stu-id="ca8bd-280">contoso.com</span></span>
  - <span data-ttu-id="ca8bd-281">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="ca8bd-281">test.com/contoso.com</span></span>
  - <span data-ttu-id="ca8bd-282">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="ca8bd-282">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="ca8bd-283">シナリオ: パスの上部にある右のワイルドカード</span><span class="sxs-lookup"><span data-stu-id="ca8bd-283">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="ca8bd-284">**エントリ**: `contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="ca8bd-284">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="ca8bd-285">**一致とブロック** の **一致を許可する**:</span><span class="sxs-lookup"><span data-stu-id="ca8bd-285">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="ca8bd-286">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="ca8bd-286">contoso.com/a/b</span></span>
  - <span data-ttu-id="ca8bd-287">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="ca8bd-287">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="ca8bd-288">contoso.com/a/?q=joe@t.com</span><span class="sxs-lookup"><span data-stu-id="ca8bd-288">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="ca8bd-289">**[一致しない] と** [ **ブロックが一致しない] を許可します**。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-289">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="ca8bd-290">contoso.com</span><span class="sxs-lookup"><span data-stu-id="ca8bd-290">contoso.com</span></span>
  - <span data-ttu-id="ca8bd-291">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="ca8bd-291">contoso.com/a</span></span>
  - <span data-ttu-id="ca8bd-292">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ca8bd-292">www.contoso.com</span></span>
  - <span data-ttu-id="ca8bd-293">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="ca8bd-293">www.contoso.com/q=a@contoso.com</span></span>

#### <a name="scenario-left-tilde"></a><span data-ttu-id="ca8bd-294">シナリオ: 左チルダ</span><span class="sxs-lookup"><span data-stu-id="ca8bd-294">Scenario: Left tilde</span></span>

<span data-ttu-id="ca8bd-295">**エントリ**: `~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="ca8bd-295">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="ca8bd-296">**一致とブロック** の **一致を許可する**:</span><span class="sxs-lookup"><span data-stu-id="ca8bd-296">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="ca8bd-297">contoso.com</span><span class="sxs-lookup"><span data-stu-id="ca8bd-297">contoso.com</span></span>
  - <span data-ttu-id="ca8bd-298">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ca8bd-298">www.contoso.com</span></span>
  - <span data-ttu-id="ca8bd-299">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ca8bd-299">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="ca8bd-300">**[一致しない] と** [ **ブロックが一致しない] を許可します**。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-300">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="ca8bd-301">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="ca8bd-301">123contoso.com</span></span>
  - <span data-ttu-id="ca8bd-302">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="ca8bd-302">contoso.com/abc</span></span>
  - <span data-ttu-id="ca8bd-303">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="ca8bd-303">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="ca8bd-304">シナリオ: 右のワイルドカード サフィックス</span><span class="sxs-lookup"><span data-stu-id="ca8bd-304">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="ca8bd-305">**エントリ**: `contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="ca8bd-305">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="ca8bd-306">**一致とブロック** の **一致を許可する**:</span><span class="sxs-lookup"><span data-stu-id="ca8bd-306">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="ca8bd-307">contoso.com/?q=whatever@fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="ca8bd-307">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="ca8bd-308">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="ca8bd-308">contoso.com/a</span></span>
  - <span data-ttu-id="ca8bd-309">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="ca8bd-309">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="ca8bd-310">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="ca8bd-310">contoso.com/ab</span></span>
  - <span data-ttu-id="ca8bd-311">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="ca8bd-311">contoso.com/b</span></span>
  - <span data-ttu-id="ca8bd-312">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="ca8bd-312">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="ca8bd-313">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="ca8bd-313">contoso.com/ba</span></span>

- <span data-ttu-id="ca8bd-314">**[一致しない] と** **[ブロックが一致しない**] : contoso.com</span><span class="sxs-lookup"><span data-stu-id="ca8bd-314">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="ca8bd-315">シナリオ: 左ワイルドカード サブドメインと右のワイルドカード サフィックス</span><span class="sxs-lookup"><span data-stu-id="ca8bd-315">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="ca8bd-316">**エントリ**: `*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="ca8bd-316">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="ca8bd-317">**一致とブロック** の **一致を許可する**:</span><span class="sxs-lookup"><span data-stu-id="ca8bd-317">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="ca8bd-318">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="ca8bd-318">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="ca8bd-319">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="ca8bd-319">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="ca8bd-320">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="ca8bd-320">www.contoso.com/a</span></span>
  - <span data-ttu-id="ca8bd-321">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="ca8bd-321">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="ca8bd-322">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="ca8bd-322">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="ca8bd-323">**[一致しない] と** **[ブロックが一致しない**] : contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="ca8bd-323">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="ca8bd-324">シナリオ: 左右のチルダ</span><span class="sxs-lookup"><span data-stu-id="ca8bd-324">Scenario: Left and right tilde</span></span>

<span data-ttu-id="ca8bd-325">**エントリ**: `~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="ca8bd-325">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="ca8bd-326">**一致とブロック** の **一致を許可する**:</span><span class="sxs-lookup"><span data-stu-id="ca8bd-326">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="ca8bd-327">contoso.com</span><span class="sxs-lookup"><span data-stu-id="ca8bd-327">contoso.com</span></span>
  - <span data-ttu-id="ca8bd-328">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="ca8bd-328">contoso.com/a</span></span>
  - <span data-ttu-id="ca8bd-329">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ca8bd-329">www.contoso.com</span></span>
  - <span data-ttu-id="ca8bd-330">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="ca8bd-330">www.contoso.com/b</span></span>
  - <span data-ttu-id="ca8bd-331">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ca8bd-331">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="ca8bd-332">**[一致しない] と** [ **ブロックが一致しない] を許可します**。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-332">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="ca8bd-333">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="ca8bd-333">123contoso.com</span></span>
  - <span data-ttu-id="ca8bd-334">contoso.org</span><span class="sxs-lookup"><span data-stu-id="ca8bd-334">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="ca8bd-335">シナリオ: IP アドレス</span><span class="sxs-lookup"><span data-stu-id="ca8bd-335">Scenario: IP address</span></span>

<span data-ttu-id="ca8bd-336">**エントリ**: `1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="ca8bd-336">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="ca8bd-337">**一致と\*\*\*\*ブロックの一** 致を許可する : 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="ca8bd-337">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="ca8bd-338">**[一致しない] と** [ **ブロックが一致しない] を許可します**。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-338">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="ca8bd-339">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="ca8bd-339">1.2.3.4/a</span></span>
  - <span data-ttu-id="ca8bd-340">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="ca8bd-340">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="ca8bd-341">適切なワイルドカードを持つ IP アドレス</span><span class="sxs-lookup"><span data-stu-id="ca8bd-341">IP address with right wildcard</span></span>

<span data-ttu-id="ca8bd-342">**エントリ**: `1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="ca8bd-342">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="ca8bd-343">**一致とブロック** の **一致を許可する**:</span><span class="sxs-lookup"><span data-stu-id="ca8bd-343">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="ca8bd-344">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="ca8bd-344">1.2.3.4/b</span></span>
  - <span data-ttu-id="ca8bd-345">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="ca8bd-345">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="ca8bd-346">無効なエントリの例</span><span class="sxs-lookup"><span data-stu-id="ca8bd-346">Examples of invalid entries</span></span>

<span data-ttu-id="ca8bd-347">次のエントリが無効です。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-347">The following entries are invalid:</span></span>

- <span data-ttu-id="ca8bd-348">**ドメイン値が見つからないか無効です**。</span><span class="sxs-lookup"><span data-stu-id="ca8bd-348">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="ca8bd-349">contoso</span><span class="sxs-lookup"><span data-stu-id="ca8bd-349">contoso</span></span>
  - <span data-ttu-id="ca8bd-350">\*.contoso.\*</span><span class="sxs-lookup"><span data-stu-id="ca8bd-350">\*.contoso.\*</span></span>
  - <span data-ttu-id="ca8bd-351">\*.com</span><span class="sxs-lookup"><span data-stu-id="ca8bd-351">\*.com</span></span>
  - <span data-ttu-id="ca8bd-352">\*.pdf</span><span class="sxs-lookup"><span data-stu-id="ca8bd-352">\*.pdf</span></span>

- <span data-ttu-id="ca8bd-353">**テキストまたはスペース文字なしのワイルドカード**:</span><span class="sxs-lookup"><span data-stu-id="ca8bd-353">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="ca8bd-354">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="ca8bd-354">\*contoso.com</span></span>
  - <span data-ttu-id="ca8bd-355">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="ca8bd-355">contoso.com\*</span></span>
  - <span data-ttu-id="ca8bd-356">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="ca8bd-356">\*1.2.3.4</span></span>
  - <span data-ttu-id="ca8bd-357">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="ca8bd-357">1.2.3.4\*</span></span>
  - <span data-ttu-id="ca8bd-358">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="ca8bd-358">contoso.com/a\*</span></span>
  - <span data-ttu-id="ca8bd-359">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="ca8bd-359">contoso.com/ab\*</span></span>

- <span data-ttu-id="ca8bd-360">**ポートを含む IP アドレス**:</span><span class="sxs-lookup"><span data-stu-id="ca8bd-360">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="ca8bd-361">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="ca8bd-361">contoso.com:443</span></span>
  - <span data-ttu-id="ca8bd-362">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="ca8bd-362">abc.contoso.com:25</span></span>

- <span data-ttu-id="ca8bd-363">**説明的でないワイルドカード**:</span><span class="sxs-lookup"><span data-stu-id="ca8bd-363">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="ca8bd-364">\*.\*</span><span class="sxs-lookup"><span data-stu-id="ca8bd-364">\*.\*</span></span>

- <span data-ttu-id="ca8bd-365">**中央のワイルドカード**:</span><span class="sxs-lookup"><span data-stu-id="ca8bd-365">**Middle wildcards**:</span></span>

  - <span data-ttu-id="ca8bd-366">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="ca8bd-366">conto\*so.com</span></span>
  - <span data-ttu-id="ca8bd-367">conto~so.com</span><span class="sxs-lookup"><span data-stu-id="ca8bd-367">conto~so.com</span></span>

- <span data-ttu-id="ca8bd-368">**2 つのワイルドカード**</span><span class="sxs-lookup"><span data-stu-id="ca8bd-368">**Double wildcards**</span></span>

  - <span data-ttu-id="ca8bd-369">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="ca8bd-369">contoso.com/\*\*</span></span>
  - <span data-ttu-id="ca8bd-370">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="ca8bd-370">contoso.com/\*/\*</span></span>
