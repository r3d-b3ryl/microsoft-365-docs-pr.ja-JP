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
ms.openlocfilehash: 103ddc9aa0858f9203582ac07a655fd7f5506cf3
ms.sourcegitcommit: 987f70e44e406ab6b1dd35f336a9d0c228032794
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/05/2021
ms.locfileid: "51587589"
---
# <a name="manage-the-tenant-allowblock-list"></a><span data-ttu-id="f9650-103">テナントの許可/禁止リストの URL を管理する</span><span class="sxs-lookup"><span data-stu-id="f9650-103">Manage the Tenant Allow/Block List</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="f9650-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="f9650-104">**Applies to**</span></span>
- [<span data-ttu-id="f9650-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="f9650-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="f9650-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="f9650-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="f9650-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f9650-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="f9650-108">現時点 **では、テナント** 許可/ブロック一覧で許可アイテムを構成できません。</span><span class="sxs-lookup"><span data-stu-id="f9650-108">You can't **configure** allowed items in the Tenant Allow/Block List at this time.</span></span>

<span data-ttu-id="f9650-109">Exchange Online またはスタンドアロンの Exchange Online Protection (EOP) 組織に Exchange Online メールボックスがない Microsoft 365 組織では、EOP フィルターの評決に同意しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f9650-109">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="f9650-110">たとえば、メッセージが正しい (誤検知) とマークされている場合や、悪いメッセージが許可される場合があります (偽陰性)。</span><span class="sxs-lookup"><span data-stu-id="f9650-110">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="f9650-111">セキュリティ コンプライアンス センターのテナント許可/ブロック一覧&、Microsoft 365 フィルターの評決を手動で上書きする方法が提供されます。</span><span class="sxs-lookup"><span data-stu-id="f9650-111">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="f9650-112">テナント許可/ブロック一覧は、メール フロー中およびユーザークリック時に使用されます。</span><span class="sxs-lookup"><span data-stu-id="f9650-112">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="f9650-113">常にブロックする URL またはファイルを指定できます。</span><span class="sxs-lookup"><span data-stu-id="f9650-113">You can specify URLs or files to always block.</span></span>

<span data-ttu-id="f9650-114">この記事では、セキュリティ & コンプライアンス センターまたは PowerShell (Exchange Online のメールボックスを持つ Microsoft 365 組織向け Exchange Online PowerShell、Exchange Online メールボックスのない組織のスタンドアロン EOP PowerShell) のテナント許可/ブロック一覧のエントリを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f9650-114">This article describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f9650-115">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="f9650-115">What do you need to know before you begin?</span></span>

- <span data-ttu-id="f9650-116"><https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="f9650-116">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="f9650-117">[テナントの許可/ブロック **リスト] ページに直接移動するには** 、 を使用します <https://protection.office.com/tenantAllowBlockList> 。</span><span class="sxs-lookup"><span data-stu-id="f9650-117">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="f9650-118">ファイルを指定するには、ファイルの SHA256 ハッシュ値を使用します。</span><span class="sxs-lookup"><span data-stu-id="f9650-118">You specify files by using the SHA256 hash value of the file.</span></span> <span data-ttu-id="f9650-119">Windows でファイルの SHA256 ハッシュ値を検索するには、コマンド プロンプトで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f9650-119">To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt:</span></span>

  ```console
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  <span data-ttu-id="f9650-120">値の例は、 です `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` 。</span><span class="sxs-lookup"><span data-stu-id="f9650-120">An example value is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`.</span></span> <span data-ttu-id="f9650-121">知覚ハッシュ (pHash) の値はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="f9650-121">Perceptual hash (pHash) values are not supported.</span></span>

- <span data-ttu-id="f9650-122">使用可能な URL 値については、この記事の後半の「 [テナント許可/](#url-syntax-for-the-tenant-allowblock-list) ブロック一覧」セクションの URL 構文で説明します。</span><span class="sxs-lookup"><span data-stu-id="f9650-122">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

- <span data-ttu-id="f9650-123">テナント許可/ブロック一覧では、URL に対して最大 500 エントリ、ファイル ハッシュのエントリを 500 エントリまで使用できます。</span><span class="sxs-lookup"><span data-stu-id="f9650-123">The Tenant Allow/Block List allows a maximum of 500 entries for URLs, and 500 entries for file hashes.</span></span>

- <span data-ttu-id="f9650-124">各エントリの最大文字数は次の値です。</span><span class="sxs-lookup"><span data-stu-id="f9650-124">The maximum number of characters for each entry is:</span></span>
  - <span data-ttu-id="f9650-125">ファイル ハッシュ = 64</span><span class="sxs-lookup"><span data-stu-id="f9650-125">File hashes = 64</span></span>
  - <span data-ttu-id="f9650-126">URL = 250</span><span class="sxs-lookup"><span data-stu-id="f9650-126">URL = 250</span></span>

- <span data-ttu-id="f9650-127">エントリは 30 分以内にアクティブである必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9650-127">An entry should be active within 30 minutes.</span></span>

- <span data-ttu-id="f9650-128">既定では、テナント許可/ブロック一覧のエントリは 30 日後に期限切れになります。</span><span class="sxs-lookup"><span data-stu-id="f9650-128">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="f9650-129">日付を指定するか、有効期限が切れることはありません。</span><span class="sxs-lookup"><span data-stu-id="f9650-129">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="f9650-130">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f9650-130">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="f9650-131">スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f9650-131">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="f9650-132">この記事の手順を実行する際には、あらかじめ **Exchange Online** でアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9650-132">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="f9650-133">テナント許可/ブロック一覧の値を追加および削除するには、組織の管理またはセキュリティ管理者の役割グループのメンバー **である** 必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9650-133">To add and remove values from the Tenant Allow/Block List, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="f9650-134">テナント許可/ブロック一覧への読み取り専用アクセスでは、グローバル リーダーまたはセキュリティリーダーの役割グループの **メンバーである** 必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9650-134">For read-only access to the Tenant Allow/Block List, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="f9650-135">詳細については、「[Exchange Online のアクセス許可](/exchange/permissions-exo/permissions-exo)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f9650-135">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  > 
  > - <span data-ttu-id="f9650-136">Microsoft 365 管理センターで、対応する Azure Active Directory の役割にユーザーを追加すると、ユーザーには、必要なアクセス許可 _および_ Microsoft 365 のその他の機能に必要なアクセス許可が付与されます。</span><span class="sxs-lookup"><span data-stu-id="f9650-136">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="f9650-137">詳細については、「[管理者の役割について](../../admin/add-users/about-admin-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f9650-137">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  > - <span data-ttu-id="f9650-138">[Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) の **閲覧専用の組織管理** の役割グループが この機能への読み取り専用アクセス権も付与します。</span><span class="sxs-lookup"><span data-stu-id="f9650-138">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="f9650-139">テナント許可/&リストに URL エントリを作成するには、セキュリティ コンプライアンス センターを使用します。</span><span class="sxs-lookup"><span data-stu-id="f9650-139">Use the Security & Compliance Center to create URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="f9650-140">URL エントリの構文の詳細については、この記事の後半の「テナント許可/ブロック一覧」セクションの [URL](#url-syntax-for-the-tenant-allowblock-list) 構文を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f9650-140">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

1. <span data-ttu-id="f9650-141">セキュリティ 管理コンプライアンス センター&、[**脅威管理ポリシー** ] [テナントの許可 \>  \> **/ブロックリスト] に移動します**。</span><span class="sxs-lookup"><span data-stu-id="f9650-141">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="f9650-142">[テナントの **許可/ブロック一覧** ] ページで **、[URL]** タブが選択されているのを確認し、[ブロック] を **クリックします。**</span><span class="sxs-lookup"><span data-stu-id="f9650-142">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Block**</span></span>

3. <span data-ttu-id="f9650-143">表示される **[URL のブロック]** フライアウトで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="f9650-143">In the **Block URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="f9650-144">**ブロックする URL を追加する**: 1 行に 1 つの URL を入力し、最大 20 を入力します。</span><span class="sxs-lookup"><span data-stu-id="f9650-144">**Add URLs to block**: Enter one URL per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="f9650-145">**有効期限が切れる** ことはありません: 次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f9650-145">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="f9650-146">設定がオフ (トグルオフ) になっていることを確認し、[有効期限] ボックスを使用してエントリの有効期限 ![ ](../../media/scc-toggle-off.png) を指定します。 </span><span class="sxs-lookup"><span data-stu-id="f9650-146">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

       <span data-ttu-id="f9650-147">または</span><span class="sxs-lookup"><span data-stu-id="f9650-147">or</span></span>

     - <span data-ttu-id="f9650-148">切り替えボタンを右に移動して、有効期限が切れなきエントリを構成します。</span><span class="sxs-lookup"><span data-stu-id="f9650-148">Move the toggle to the right to configure the entries to never expire:</span></span> ![オンに切り替え](../../media/scc-toggle-on.png)<span data-ttu-id="f9650-150">.</span><span class="sxs-lookup"><span data-stu-id="f9650-150">.</span></span>

   - <span data-ttu-id="f9650-151">**省略可能な** メモ: エントリの説明テキストを入力します。</span><span class="sxs-lookup"><span data-stu-id="f9650-151">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="f9650-152">完了したら、**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f9650-152">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="f9650-153">テナント許可/&リストにファイル エントリを作成するには、セキュリティ コンプライアンス センターを使用します。</span><span class="sxs-lookup"><span data-stu-id="f9650-153">Use the Security & Compliance Center to create file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="f9650-154">セキュリティ 管理コンプライアンス センター&、[**脅威管理ポリシー** ] [テナントの許可 \>  \> **/ブロックリスト] に移動します**。</span><span class="sxs-lookup"><span data-stu-id="f9650-154">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="f9650-155">[テナントの **許可/ブロックリスト] ページで** 、[ **ファイル]** タブを選択し、[ブロック] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="f9650-155">On the **Tenant Allow/Block List** page, select **Files** tab, and then click **Block**.</span></span>

3. <span data-ttu-id="f9650-156">表示される **[ファイルを追加してブロック** する] フライアウトで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="f9650-156">In the **Add files to block** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="f9650-157">**ファイル ハッシュの追加**: 1 行に 1 つの SHA256 ハッシュ値を入力し、最大 20 を入力します。</span><span class="sxs-lookup"><span data-stu-id="f9650-157">**Add file hashes**: Enter one SHA256 hash value per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="f9650-158">**有効期限が切れる** ことはありません: 次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f9650-158">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="f9650-159">設定がオフ (トグルオフ) になっていることを確認し、[有効期限] ボックスを使用してエントリの有効期限 ![ ](../../media/scc-toggle-off.png) を指定します。 </span><span class="sxs-lookup"><span data-stu-id="f9650-159">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="f9650-160">または</span><span class="sxs-lookup"><span data-stu-id="f9650-160">or</span></span>

     - <span data-ttu-id="f9650-161">切り替えボタンを右に移動して、有効期限が切れなきエントリを構成します。</span><span class="sxs-lookup"><span data-stu-id="f9650-161">Move the toggle to the right to configure the entries to never expire:</span></span> ![オンに切り替え](../../media/scc-toggle-on.png)<span data-ttu-id="f9650-163">.</span><span class="sxs-lookup"><span data-stu-id="f9650-163">.</span></span>

   - <span data-ttu-id="f9650-164">**省略可能な** メモ: エントリの説明テキストを入力します。</span><span class="sxs-lookup"><span data-stu-id="f9650-164">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="f9650-165">完了したら、**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f9650-165">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="f9650-166">テナント許可/&リストのエントリを表示するには、セキュリティ コンプライアンス センターを使用します。</span><span class="sxs-lookup"><span data-stu-id="f9650-166">Use the Security & Compliance Center to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="f9650-167">セキュリティ 管理コンプライアンス センター&、[**脅威管理ポリシー** ] [テナントの許可 \>  \> **/ブロックリスト] に移動します**。</span><span class="sxs-lookup"><span data-stu-id="f9650-167">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="f9650-168">**[URL] タブまたは [** ファイル] タブ **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="f9650-168">Select the **URLs** tab or the **Files** tab.</span></span>

<span data-ttu-id="f9650-169">昇順または降順で並べ替えるには、次の列見出しをクリックします。</span><span class="sxs-lookup"><span data-stu-id="f9650-169">Click on the following column headings to sort in ascending or descending order:</span></span>

- <span data-ttu-id="f9650-170">**値**: URL またはファイル ハッシュ。</span><span class="sxs-lookup"><span data-stu-id="f9650-170">**Value**: The URL or the file hash.</span></span>
- <span data-ttu-id="f9650-171">**最終更新日**</span><span class="sxs-lookup"><span data-stu-id="f9650-171">**Last updated date**</span></span>
- <span data-ttu-id="f9650-172">**有効期限**</span><span class="sxs-lookup"><span data-stu-id="f9650-172">**Expiration date**</span></span>
- <span data-ttu-id="f9650-173">**注**</span><span class="sxs-lookup"><span data-stu-id="f9650-173">**Note**</span></span>

<span data-ttu-id="f9650-174">[ **検索]** をクリックし、値のすべてまたは一部を入力し、Enter キーを押して特定の値を検索します。</span><span class="sxs-lookup"><span data-stu-id="f9650-174">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="f9650-175">完了したら、[検索のクリア] **アイコン** ![ をクリックします ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) 。</span><span class="sxs-lookup"><span data-stu-id="f9650-175">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

<span data-ttu-id="f9650-176">[フィルター **] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="f9650-176">Click **Filter**.</span></span> <span data-ttu-id="f9650-177">表示される **[フィルター** ] フライアウトで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="f9650-177">In the **Filter** flyout that appears, configure any of the following settings:</span></span>

- <span data-ttu-id="f9650-178">**有効期限が切** れることはありません: [オフ] を ![ 選択します。オフ ](../../media/scc-toggle-off.png) またはオンに切り替えます。 ![ ](../../media/scc-toggle-on.png)</span><span class="sxs-lookup"><span data-stu-id="f9650-178">**Never expire**: Select off: ![Toggle off](../../media/scc-toggle-off.png) or on: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

- <span data-ttu-id="f9650-179">**最終更新日 :** 開始日 ( From **)**、終了日 (**To**) または両方を選択します。</span><span class="sxs-lookup"><span data-stu-id="f9650-179">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span></span>

- <span data-ttu-id="f9650-180">**有効期限 :** 開始日 **(** From ) 、終了日 (**To**) または両方を選択します。</span><span class="sxs-lookup"><span data-stu-id="f9650-180">**Expiration date**: Select a start date (**From**), an end date (**To**) or both.</span></span>

<span data-ttu-id="f9650-181">完了したら、[適用] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="f9650-181">When you're finished, click **Apply**.</span></span>

<span data-ttu-id="f9650-182">既存のフィルターをクリアするには、[**フィルター**] をクリックし、表示される [フィルター] フライアウトで 、[フィルターのクリア]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="f9650-182">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-block-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="f9650-183">テナント許可/&リストのブロック エントリを変更するには、セキュリティ コンプライアンス センターを使用します。</span><span class="sxs-lookup"><span data-stu-id="f9650-183">Use the Security & Compliance Center to modify block entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="f9650-184">エントリ内の既存のブロックされた URL またはファイル値を変更できない。</span><span class="sxs-lookup"><span data-stu-id="f9650-184">You can't modify the existing blocked URL or file values within an entry.</span></span> <span data-ttu-id="f9650-185">これらの値を変更するには、エントリを削除して再作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9650-185">To modify these values, you need to delete and recreate the entry.</span></span>

1. <span data-ttu-id="f9650-186">セキュリティ 管理コンプライアンス センター&、[**脅威管理ポリシー** ] [テナントの許可 \>  \> **/ブロックリスト] に移動します**。</span><span class="sxs-lookup"><span data-stu-id="f9650-186">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="f9650-187">**[URL] タブまたは [** ファイル] タブ **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="f9650-187">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="f9650-188">変更するブロック エントリを選択し、[編集] アイコン **を** ![ クリックします ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) 。</span><span class="sxs-lookup"><span data-stu-id="f9650-188">Select the block entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span>

4. <span data-ttu-id="f9650-189">表示されるフライアウトで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="f9650-189">In the flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="f9650-190">**有効期限が切れる** ことはありません: 次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f9650-190">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="f9650-191">設定がオフ (トグルオフ) になっていることを確認し、[有効期限] ボックスを使用してエントリの ![ ](../../media/scc-toggle-off.png) 有効期限を指定します。 </span><span class="sxs-lookup"><span data-stu-id="f9650-191">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entry.</span></span>

       <span data-ttu-id="f9650-192">または</span><span class="sxs-lookup"><span data-stu-id="f9650-192">or</span></span>

     - <span data-ttu-id="f9650-193">切り替えボタンを右に移動して、有効期限が切れなきエントリを構成します。</span><span class="sxs-lookup"><span data-stu-id="f9650-193">Move the toggle to the right to configure the entry to never expire:</span></span> ![オンに切り替え](../../media/scc-toggle-on.png)<span data-ttu-id="f9650-195">.</span><span class="sxs-lookup"><span data-stu-id="f9650-195">.</span></span>

   - <span data-ttu-id="f9650-196">**省略可能なメモ**: エントリの説明テキストを入力します。</span><span class="sxs-lookup"><span data-stu-id="f9650-196">**Optional note**: Enter descriptive text for the entry.</span></span>

5. <span data-ttu-id="f9650-197">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f9650-197">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-block-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="f9650-198">テナント許可/&リストからブロック エントリを削除するには、セキュリティ コンプライアンス センターを使用します。</span><span class="sxs-lookup"><span data-stu-id="f9650-198">Use the Security & Compliance Center to remove block entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="f9650-199">セキュリティ 管理コンプライアンス センター&、[**脅威管理ポリシー** ] [テナントの許可 \>  \> **/ブロックリスト] に移動します**。</span><span class="sxs-lookup"><span data-stu-id="f9650-199">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="f9650-200">**[URL] タブまたは [** ファイル] タブ **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="f9650-200">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="f9650-201">削除するブロック エントリを選択し、[削除] アイコン **を** ![ クリックします ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) 。</span><span class="sxs-lookup"><span data-stu-id="f9650-201">Select the block entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="f9650-202">表示される警告ダイアログで、[削除] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="f9650-202">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="f9650-203">Exchange Online PowerShell またはスタンドアロン EOP PowerShell を使用してテナントの許可/ブロックリストを構成する</span><span class="sxs-lookup"><span data-stu-id="f9650-203">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-block-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="f9650-204">PowerShell を使用してテナント許可/ブロック一覧にブロック エントリを追加する</span><span class="sxs-lookup"><span data-stu-id="f9650-204">Use PowerShell to add block entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="f9650-205">テナント許可/ブロック一覧にブロック エントリを追加するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="f9650-205">To add block entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType <Url | FileHash> -Block -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="f9650-206">次の使用例は、contoso.com およびすべてのサブドメイン (contoso.com、www.contoso.com、および xyz.abc.contoso.com) のブロック URL エントリを追加します。</span><span class="sxs-lookup"><span data-stu-id="f9650-206">This example adds a block URL entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="f9650-207">ExpirationDate パラメーターまたは NoExpiration パラメーターを使用しないので、エントリは 30 日後に期限切れになります。</span><span class="sxs-lookup"><span data-stu-id="f9650-207">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItems -ListType Url -Block -Entries ~contoso.com
```

<span data-ttu-id="f9650-208">次の使用例は、有効期限が切れることはありません指定したファイルのブロック ファイル エントリを追加します。</span><span class="sxs-lookup"><span data-stu-id="f9650-208">This example adds a block file entry for the specified files that never expires.</span></span>

```powershell
New-TenantAllowBlockListItems -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

<span data-ttu-id="f9650-209">構文とパラメーターの詳細については [、「New-TenantAllowBlockListItems」を参照してください](/powershell/module/exchange/new-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="f9650-209">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="f9650-210">PowerShell を使用してテナント許可/ブロック一覧のエントリを表示する</span><span class="sxs-lookup"><span data-stu-id="f9650-210">Use PowerShell to view entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="f9650-211">テナント許可/ブロック一覧のエントリを表示するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="f9650-211">To view entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType <Url | FileHash> [-Entry <URLValue | FileHashValue>] [-Block] [-ExpirationDate <DateTime>] [-NoExpiration]
```

<span data-ttu-id="f9650-212">この例では、ブロックされているすべての URL を返します。</span><span class="sxs-lookup"><span data-stu-id="f9650-212">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Block
```

<span data-ttu-id="f9650-213">次の使用例は、指定したファイル ハッシュ値の情報を返します。</span><span class="sxs-lookup"><span data-stu-id="f9650-213">This example returns information for the specified file hash value.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

<span data-ttu-id="f9650-214">構文とパラメーターの詳細については [、「Get-TenantAllowBlockListItems」を参照してください](/powershell/module/exchange/get-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="f9650-214">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-block-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="f9650-215">PowerShell を使用してテナント許可/ブロック一覧のブロック エントリを変更する</span><span class="sxs-lookup"><span data-stu-id="f9650-215">Use PowerShell to modify block entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="f9650-216">ブロック エントリ内の既存の URL またはファイル値を変更できない。</span><span class="sxs-lookup"><span data-stu-id="f9650-216">You can't modify the existing URL or file values within a block entry.</span></span> <span data-ttu-id="f9650-217">これらの値を変更するには、エントリを削除して再作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9650-217">To modify these values, you need to delete and recreate the entry.</span></span>

<span data-ttu-id="f9650-218">テナント許可/ブロック一覧のブロック エントリを変更するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="f9650-218">To modify block entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN"> [-Block] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="f9650-219">次の使用例は、指定したブロック エントリの有効期限を変更します。</span><span class="sxs-lookup"><span data-stu-id="f9650-219">This example changes the expiration date of the specified block entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

<span data-ttu-id="f9650-220">構文とパラメーターの詳細については [、「Set-TenantAllowBlockListItems」を参照してください](/powershell/module/exchange/set-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="f9650-220">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-block-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="f9650-221">PowerShell を使用してテナント許可/ブロック一覧からブロック エントリを削除する</span><span class="sxs-lookup"><span data-stu-id="f9650-221">Use PowerShell to remove block entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="f9650-222">テナント許可/ブロック一覧からブロック エントリを削除するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="f9650-222">To remove block entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="f9650-223">次の使用例は、指定したブロック URL エントリをテナント許可/ブロック一覧から削除します。</span><span class="sxs-lookup"><span data-stu-id="f9650-223">This example removes the specified block URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="f9650-224">構文とパラメーターの詳細については [、「Remove-TenantAllowBlockListItems」を参照してください](/powershell/module/exchange/remove-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="f9650-224">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="f9650-225">テナント許可/ブロック一覧の URL 構文</span><span class="sxs-lookup"><span data-stu-id="f9650-225">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="f9650-226">IP4v および IPv6 アドレスは許可されますが、TCP/UDP ポートは許可されません。</span><span class="sxs-lookup"><span data-stu-id="f9650-226">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="f9650-227">ファイル名の拡張子は許可されません (たとえば、test.pdf)。</span><span class="sxs-lookup"><span data-stu-id="f9650-227">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="f9650-228">Unicode はサポートされていませんが、Punycode はです。</span><span class="sxs-lookup"><span data-stu-id="f9650-228">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="f9650-229">ホスト名は、次のすべてのステートメントが true の場合に許可されます。</span><span class="sxs-lookup"><span data-stu-id="f9650-229">Hostnames are allowed if all of the following statements are true:</span></span>
  - <span data-ttu-id="f9650-230">ホスト名にはピリオドが含まれる。</span><span class="sxs-lookup"><span data-stu-id="f9650-230">The hostname contains a period.</span></span>
  - <span data-ttu-id="f9650-231">ピリオドの左側に少なくとも 1 つの文字があります。</span><span class="sxs-lookup"><span data-stu-id="f9650-231">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="f9650-232">ピリオドの右側には、少なくとも 2 つの文字があります。</span><span class="sxs-lookup"><span data-stu-id="f9650-232">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="f9650-233">たとえば、 `t.co` 許可されている、または `.com` `contoso.` 許可されない。</span><span class="sxs-lookup"><span data-stu-id="f9650-233">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="f9650-234">サブパスは暗黙的ではありません。</span><span class="sxs-lookup"><span data-stu-id="f9650-234">Subpaths are not implied.</span></span>

  <span data-ttu-id="f9650-235">たとえば、 `contoso.com` は含めではありません `contoso.com/a` 。</span><span class="sxs-lookup"><span data-stu-id="f9650-235">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="f9650-236">ワイルドカード (\*) は、次のシナリオで使用できます。</span><span class="sxs-lookup"><span data-stu-id="f9650-236">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="f9650-237">サブドメインを指定するには、左のワイルドカードの後にピリオドを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9650-237">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="f9650-238">たとえば、 `*.contoso.com` 許可されます。 `*contoso.com` 許可されません。</span><span class="sxs-lookup"><span data-stu-id="f9650-238">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="f9650-239">パスを指定するには、右のワイルドカードがスラッシュ (/) に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9650-239">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="f9650-240">たとえば、 `contoso.com/*` 許可されている、または `contoso.com*` `contoso.com/ab*` 許可されない。</span><span class="sxs-lookup"><span data-stu-id="f9650-240">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="f9650-241">すべてのサブパスは、適切なワイルドカードによって暗示されるものではありません。</span><span class="sxs-lookup"><span data-stu-id="f9650-241">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="f9650-242">たとえば、 `contoso.com/*` は含めではありません `contoso.com/a` 。</span><span class="sxs-lookup"><span data-stu-id="f9650-242">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="f9650-243">`*.com*` は無効です (解決可能なドメインではなく、右のワイルドカードはスラッシュに従います)。</span><span class="sxs-lookup"><span data-stu-id="f9650-243">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="f9650-244">IP アドレスではワイルドカードは使用できません。</span><span class="sxs-lookup"><span data-stu-id="f9650-244">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="f9650-245">チルダ (~) 文字は、次のシナリオで使用できます。</span><span class="sxs-lookup"><span data-stu-id="f9650-245">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="f9650-246">左チルダは、ドメインとすべてのサブドメインを意味します。</span><span class="sxs-lookup"><span data-stu-id="f9650-246">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="f9650-247">たとえば `~contoso.com` 、includes `contoso.com` と `*.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="f9650-247">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="f9650-248">URL エントリは、すべてのプロトコルに適用されるので、プロトコルを含む URL エントリ (たとえば `http://` `https://` `ftp://` 、) は失敗します。</span><span class="sxs-lookup"><span data-stu-id="f9650-248">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="f9650-249">ユーザー名またはパスワードはサポートされていないか、必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="f9650-249">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="f9650-250">引用符 (' または ") は無効な文字です。</span><span class="sxs-lookup"><span data-stu-id="f9650-250">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="f9650-251">URL には、可能な限りすべてのリダイレクトが含まれる必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9650-251">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="f9650-252">URL エントリのシナリオ</span><span class="sxs-lookup"><span data-stu-id="f9650-252">URL entry scenarios</span></span>

<span data-ttu-id="f9650-253">有効な URL エントリとその結果については、次のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="f9650-253">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="f9650-254">シナリオ: ワイルドカードなし</span><span class="sxs-lookup"><span data-stu-id="f9650-254">Scenario: No wildcards</span></span>

<span data-ttu-id="f9650-255">**エントリ**: `contoso.com`</span><span class="sxs-lookup"><span data-stu-id="f9650-255">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="f9650-256">**一致を許可** する : contoso.com</span><span class="sxs-lookup"><span data-stu-id="f9650-256">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="f9650-257">**[一致しない] を許可します**。</span><span class="sxs-lookup"><span data-stu-id="f9650-257">**Allow not matched**:</span></span>

  - <span data-ttu-id="f9650-258">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="f9650-258">abc-contoso.com</span></span>
  - <span data-ttu-id="f9650-259">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="f9650-259">contoso.com/a</span></span>
  - <span data-ttu-id="f9650-260">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f9650-260">payroll.contoso.com</span></span>
  - <span data-ttu-id="f9650-261">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="f9650-261">test.com/contoso.com</span></span>
  - <span data-ttu-id="f9650-262">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="f9650-262">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="f9650-263">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f9650-263">www.contoso.com</span></span>
  - <span data-ttu-id="f9650-264">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="f9650-264">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="f9650-265">**ブロック一致**:</span><span class="sxs-lookup"><span data-stu-id="f9650-265">**Block match**:</span></span>

  - <span data-ttu-id="f9650-266">contoso.com</span><span class="sxs-lookup"><span data-stu-id="f9650-266">contoso.com</span></span>
  - <span data-ttu-id="f9650-267">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="f9650-267">contoso.com/a</span></span>
  - <span data-ttu-id="f9650-268">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f9650-268">payroll.contoso.com</span></span>
  - <span data-ttu-id="f9650-269">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="f9650-269">test.com/contoso.com</span></span>
  - <span data-ttu-id="f9650-270">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="f9650-270">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="f9650-271">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f9650-271">www.contoso.com</span></span>
  - <span data-ttu-id="f9650-272">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="f9650-272">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="f9650-273">**ブロックが一致しない**: abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="f9650-273">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="f9650-274">シナリオ: 左ワイルドカード (サブドメイン)</span><span class="sxs-lookup"><span data-stu-id="f9650-274">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="f9650-275">**エントリ**: `*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="f9650-275">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="f9650-276">**一致とブロック** の **一致を許可する**:</span><span class="sxs-lookup"><span data-stu-id="f9650-276">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="f9650-277">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f9650-277">www.contoso.com</span></span>
  - <span data-ttu-id="f9650-278">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f9650-278">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="f9650-279">**[一致しない] と** [ **ブロックが一致しない] を許可します**。</span><span class="sxs-lookup"><span data-stu-id="f9650-279">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="f9650-280">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="f9650-280">123contoso.com</span></span>
  - <span data-ttu-id="f9650-281">contoso.com</span><span class="sxs-lookup"><span data-stu-id="f9650-281">contoso.com</span></span>
  - <span data-ttu-id="f9650-282">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="f9650-282">test.com/contoso.com</span></span>
  - <span data-ttu-id="f9650-283">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="f9650-283">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="f9650-284">シナリオ: パスの上部にある右のワイルドカード</span><span class="sxs-lookup"><span data-stu-id="f9650-284">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="f9650-285">**エントリ**: `contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="f9650-285">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="f9650-286">**一致とブロック** の **一致を許可する**:</span><span class="sxs-lookup"><span data-stu-id="f9650-286">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="f9650-287">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="f9650-287">contoso.com/a/b</span></span>
  - <span data-ttu-id="f9650-288">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="f9650-288">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="f9650-289">contoso.com/a/?q=joe@t.com</span><span class="sxs-lookup"><span data-stu-id="f9650-289">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="f9650-290">**[一致しない] と** [ **ブロックが一致しない] を許可します**。</span><span class="sxs-lookup"><span data-stu-id="f9650-290">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="f9650-291">contoso.com</span><span class="sxs-lookup"><span data-stu-id="f9650-291">contoso.com</span></span>
  - <span data-ttu-id="f9650-292">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="f9650-292">contoso.com/a</span></span>
  - <span data-ttu-id="f9650-293">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f9650-293">www.contoso.com</span></span>
  - <span data-ttu-id="f9650-294">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="f9650-294">www.contoso.com/q=a@contoso.com</span></span>

#### <a name="scenario-left-tilde"></a><span data-ttu-id="f9650-295">シナリオ: 左チルダ</span><span class="sxs-lookup"><span data-stu-id="f9650-295">Scenario: Left tilde</span></span>

<span data-ttu-id="f9650-296">**エントリ**: `~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="f9650-296">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="f9650-297">**一致とブロック** の **一致を許可する**:</span><span class="sxs-lookup"><span data-stu-id="f9650-297">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="f9650-298">contoso.com</span><span class="sxs-lookup"><span data-stu-id="f9650-298">contoso.com</span></span>
  - <span data-ttu-id="f9650-299">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f9650-299">www.contoso.com</span></span>
  - <span data-ttu-id="f9650-300">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f9650-300">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="f9650-301">**[一致しない] と** [ **ブロックが一致しない] を許可します**。</span><span class="sxs-lookup"><span data-stu-id="f9650-301">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="f9650-302">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="f9650-302">123contoso.com</span></span>
  - <span data-ttu-id="f9650-303">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="f9650-303">contoso.com/abc</span></span>
  - <span data-ttu-id="f9650-304">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="f9650-304">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="f9650-305">シナリオ: 右のワイルドカード サフィックス</span><span class="sxs-lookup"><span data-stu-id="f9650-305">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="f9650-306">**エントリ**: `contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="f9650-306">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="f9650-307">**一致とブロック** の **一致を許可する**:</span><span class="sxs-lookup"><span data-stu-id="f9650-307">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="f9650-308">contoso.com/?q=whatever@fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="f9650-308">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="f9650-309">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="f9650-309">contoso.com/a</span></span>
  - <span data-ttu-id="f9650-310">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="f9650-310">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="f9650-311">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="f9650-311">contoso.com/ab</span></span>
  - <span data-ttu-id="f9650-312">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="f9650-312">contoso.com/b</span></span>
  - <span data-ttu-id="f9650-313">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="f9650-313">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="f9650-314">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="f9650-314">contoso.com/ba</span></span>

- <span data-ttu-id="f9650-315">**[一致しない] と** **[ブロックが一致しない**] : contoso.com</span><span class="sxs-lookup"><span data-stu-id="f9650-315">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="f9650-316">シナリオ: 左ワイルドカード サブドメインと右のワイルドカード サフィックス</span><span class="sxs-lookup"><span data-stu-id="f9650-316">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="f9650-317">**エントリ**: `*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="f9650-317">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="f9650-318">**一致とブロック** の **一致を許可する**:</span><span class="sxs-lookup"><span data-stu-id="f9650-318">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="f9650-319">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="f9650-319">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="f9650-320">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="f9650-320">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="f9650-321">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="f9650-321">www.contoso.com/a</span></span>
  - <span data-ttu-id="f9650-322">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="f9650-322">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="f9650-323">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="f9650-323">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="f9650-324">**[一致しない] と** **[ブロックが一致しない**] : contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="f9650-324">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="f9650-325">シナリオ: 左右のチルダ</span><span class="sxs-lookup"><span data-stu-id="f9650-325">Scenario: Left and right tilde</span></span>

<span data-ttu-id="f9650-326">**エントリ**: `~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="f9650-326">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="f9650-327">**一致とブロック** の **一致を許可する**:</span><span class="sxs-lookup"><span data-stu-id="f9650-327">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="f9650-328">contoso.com</span><span class="sxs-lookup"><span data-stu-id="f9650-328">contoso.com</span></span>
  - <span data-ttu-id="f9650-329">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="f9650-329">contoso.com/a</span></span>
  - <span data-ttu-id="f9650-330">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f9650-330">www.contoso.com</span></span>
  - <span data-ttu-id="f9650-331">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="f9650-331">www.contoso.com/b</span></span>
  - <span data-ttu-id="f9650-332">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f9650-332">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="f9650-333">**[一致しない] と** [ **ブロックが一致しない] を許可します**。</span><span class="sxs-lookup"><span data-stu-id="f9650-333">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="f9650-334">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="f9650-334">123contoso.com</span></span>
  - <span data-ttu-id="f9650-335">contoso.org</span><span class="sxs-lookup"><span data-stu-id="f9650-335">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="f9650-336">シナリオ: IP アドレス</span><span class="sxs-lookup"><span data-stu-id="f9650-336">Scenario: IP address</span></span>

<span data-ttu-id="f9650-337">**エントリ**: `1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="f9650-337">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="f9650-338">**一致と\*\*\*\*ブロックの一** 致を許可する : 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="f9650-338">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="f9650-339">**[一致しない] と** [ **ブロックが一致しない] を許可します**。</span><span class="sxs-lookup"><span data-stu-id="f9650-339">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="f9650-340">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="f9650-340">1.2.3.4/a</span></span>
  - <span data-ttu-id="f9650-341">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="f9650-341">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="f9650-342">適切なワイルドカードを持つ IP アドレス</span><span class="sxs-lookup"><span data-stu-id="f9650-342">IP address with right wildcard</span></span>

<span data-ttu-id="f9650-343">**エントリ**: `1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="f9650-343">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="f9650-344">**一致とブロック** の **一致を許可する**:</span><span class="sxs-lookup"><span data-stu-id="f9650-344">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="f9650-345">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="f9650-345">1.2.3.4/b</span></span>
  - <span data-ttu-id="f9650-346">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="f9650-346">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="f9650-347">無効なエントリの例</span><span class="sxs-lookup"><span data-stu-id="f9650-347">Examples of invalid entries</span></span>

<span data-ttu-id="f9650-348">次のエントリが無効です。</span><span class="sxs-lookup"><span data-stu-id="f9650-348">The following entries are invalid:</span></span>

- <span data-ttu-id="f9650-349">**ドメイン値が見つからないか無効です**。</span><span class="sxs-lookup"><span data-stu-id="f9650-349">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="f9650-350">contoso</span><span class="sxs-lookup"><span data-stu-id="f9650-350">contoso</span></span>
  - <span data-ttu-id="f9650-351">\*.contoso.\*</span><span class="sxs-lookup"><span data-stu-id="f9650-351">\*.contoso.\*</span></span>
  - <span data-ttu-id="f9650-352">\*.com</span><span class="sxs-lookup"><span data-stu-id="f9650-352">\*.com</span></span>
  - <span data-ttu-id="f9650-353">\*.pdf</span><span class="sxs-lookup"><span data-stu-id="f9650-353">\*.pdf</span></span>

- <span data-ttu-id="f9650-354">**テキストまたはスペース文字なしのワイルドカード**:</span><span class="sxs-lookup"><span data-stu-id="f9650-354">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="f9650-355">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="f9650-355">\*contoso.com</span></span>
  - <span data-ttu-id="f9650-356">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="f9650-356">contoso.com\*</span></span>
  - <span data-ttu-id="f9650-357">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="f9650-357">\*1.2.3.4</span></span>
  - <span data-ttu-id="f9650-358">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="f9650-358">1.2.3.4\*</span></span>
  - <span data-ttu-id="f9650-359">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="f9650-359">contoso.com/a\*</span></span>
  - <span data-ttu-id="f9650-360">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="f9650-360">contoso.com/ab\*</span></span>

- <span data-ttu-id="f9650-361">**ポートを含む IP アドレス**:</span><span class="sxs-lookup"><span data-stu-id="f9650-361">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="f9650-362">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="f9650-362">contoso.com:443</span></span>
  - <span data-ttu-id="f9650-363">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="f9650-363">abc.contoso.com:25</span></span>

- <span data-ttu-id="f9650-364">**説明的でないワイルドカード**:</span><span class="sxs-lookup"><span data-stu-id="f9650-364">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="f9650-365">\*.\*</span><span class="sxs-lookup"><span data-stu-id="f9650-365">\*.\*</span></span>

- <span data-ttu-id="f9650-366">**中央のワイルドカード**:</span><span class="sxs-lookup"><span data-stu-id="f9650-366">**Middle wildcards**:</span></span>

  - <span data-ttu-id="f9650-367">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="f9650-367">conto\*so.com</span></span>
  - <span data-ttu-id="f9650-368">conto~so.com</span><span class="sxs-lookup"><span data-stu-id="f9650-368">conto~so.com</span></span>

- <span data-ttu-id="f9650-369">**2 つのワイルドカード**</span><span class="sxs-lookup"><span data-stu-id="f9650-369">**Double wildcards**</span></span>

  - <span data-ttu-id="f9650-370">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="f9650-370">contoso.com/\*\*</span></span>
  - <span data-ttu-id="f9650-371">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="f9650-371">contoso.com/\*/\*</span></span>
