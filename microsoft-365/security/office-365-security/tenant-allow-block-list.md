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
ms.openlocfilehash: dbd4694a7442b3898d24304dc78fc95c28c9a905
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "53394955"
---
# <a name="manage-the-tenant-allowblock-list"></a><span data-ttu-id="d5189-103">テナントの許可/禁止リストの URL を管理する</span><span class="sxs-lookup"><span data-stu-id="d5189-103">Manage the Tenant Allow/Block List</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="d5189-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="d5189-104">**Applies to**</span></span>
- [<span data-ttu-id="d5189-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="d5189-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="d5189-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="d5189-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="d5189-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d5189-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
>
> <span data-ttu-id="d5189-108">この記事で説明する機能はプレビューで、変更される可能性があります。一部の組織では利用できません。</span><span class="sxs-lookup"><span data-stu-id="d5189-108">The features described in this article are in Preview, are subject to change, and are not available in all organizations.</span></span>  <span data-ttu-id="d5189-109">この記事で説明するスプーフィング機能が組織に存在しない場合は [、「EOP](walkthrough-spoof-intelligence-insight.md)のスプーフィング インテリジェンス ポリシーとスプーフィング インテリジェンスインサイトを使用してスプーフィング送信者を管理する」で、以前のスプーフィング管理エクスペリエンスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d5189-109">If your organization does not have the spoof features as described in this article, see the older spoof management experience at [Manage spoofed senders using the spoof intelligence policy and spoof intelligence insight in EOP](walkthrough-spoof-intelligence-insight.md).</span></span>
>
> <span data-ttu-id="d5189-110">現時点 **では、テナント** 許可/ブロック一覧で許可された URL またはファイル アイテムを構成できません。</span><span class="sxs-lookup"><span data-stu-id="d5189-110">You can't **configure** allowed URL or file items in the Tenant Allow/Block List at this time.</span></span>

<span data-ttu-id="d5189-111">Microsoft 365 Exchange Online またはスタンドアロン Exchange Online Protection (EOP) 組織に Exchange Online メールボックスがない組織では、EOP フィルターの評決に同意しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d5189-111">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="d5189-112">たとえば、メッセージが正しい (誤検知) とマークされている場合や、悪いメッセージが許可される場合があります (偽陰性)。</span><span class="sxs-lookup"><span data-stu-id="d5189-112">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="d5189-113">ポータルのテナント許可/ブロックリストMicrosoft 365 Defender、フィルター処理の評決を手動で上書Microsoft 365できます。</span><span class="sxs-lookup"><span data-stu-id="d5189-113">The Tenant Allow/Block List in the Microsoft 365 Defender portal gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="d5189-114">テナント許可/ブロック一覧は、受信メッセージのメール フロー (組織内メッセージには適用されません) およびユーザーのクリック時に使用されます。</span><span class="sxs-lookup"><span data-stu-id="d5189-114">The Tenant Allow/Block List is used during mail flow for incoming messages (does not apply to intra-org messages) and at the time of user clicks.</span></span> <span data-ttu-id="d5189-115">次の種類のオーバーライドを指定できます。</span><span class="sxs-lookup"><span data-stu-id="d5189-115">You can specify the following types of overrides:</span></span>

- <span data-ttu-id="d5189-116">ブロックする URL。</span><span class="sxs-lookup"><span data-stu-id="d5189-116">URLs to block.</span></span>
- <span data-ttu-id="d5189-117">ブロックするファイル。</span><span class="sxs-lookup"><span data-stu-id="d5189-117">Files to block.</span></span>
- <span data-ttu-id="d5189-118">許可またはブロックするスプーフィングされた送信者。</span><span class="sxs-lookup"><span data-stu-id="d5189-118">Spoofed senders to allow or block.</span></span> <span data-ttu-id="d5189-119">スプーフィング インテリジェンスインサイトで許可またはブロックの[](learn-about-spoof-intelligence.md)評決を上書きすると、スプーフィングされた送信者は、テナント許可/ブロック一覧の [スプーフィング] タブにのみ表示される手動の許可またはブロックエントリになります。</span><span class="sxs-lookup"><span data-stu-id="d5189-119">If you override the allow or block verdict in the [spoof intelligence insight](learn-about-spoof-intelligence.md), the spoofed sender becomes a manual allow or block entry that only appears on the **Spoof** tab in the Tenant Allow/Block List.</span></span> <span data-ttu-id="d5189-120">スプーフィング インテリジェンスによって検出される前に、スプーフィングされた送信者のエントリを手動で作成またはブロックすることもできます。</span><span class="sxs-lookup"><span data-stu-id="d5189-120">You can also manually create allow or block entries for spoofed senders here before they're detected by spoof intelligence.</span></span>

<span data-ttu-id="d5189-121">この記事では、Microsoft 365 Defender ポータルまたは PowerShell (Exchange Online のメールボックスを持つ Microsoft 365 組織の Exchange Online PowerShell、Exchange Online メールボックスのない組織のスタンドアロン EOP PowerShell) でエントリを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d5189-121">This article describes how to configure entries in the Tenant Allow/Block List in the Microsoft 365 Defender portal or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="d5189-122">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="d5189-122">What do you need to know before you begin?</span></span>

- <span data-ttu-id="d5189-123"><https://security.microsoft.com/> で Microsoft 365 Defender ポータルを開きます。</span><span class="sxs-lookup"><span data-stu-id="d5189-123">You open the Microsoft 365 Defender portal at <https://security.microsoft.com/>.</span></span> <span data-ttu-id="d5189-124">[テナントの許可/ブロックリスト **] ページに直接移動するには** 、 を使用します <https://security.microsoft.com/tenantAllowBlockList> 。</span><span class="sxs-lookup"><span data-stu-id="d5189-124">To go directly to the **Tenant Allow/Block Lists** page, use <https://security.microsoft.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="d5189-125">ファイルを指定するには、ファイルの SHA256 ハッシュ値を使用します。</span><span class="sxs-lookup"><span data-stu-id="d5189-125">You specify files by using the SHA256 hash value of the file.</span></span> <span data-ttu-id="d5189-126">ファイルの SHA256 ハッシュ値をWindowsコマンド プロンプトで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="d5189-126">To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt:</span></span>

  ```console
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  <span data-ttu-id="d5189-127">値の例は、 です `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` 。</span><span class="sxs-lookup"><span data-stu-id="d5189-127">An example value is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`.</span></span> <span data-ttu-id="d5189-128">知覚ハッシュ (pHash) の値はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="d5189-128">Perceptual hash (pHash) values are not supported.</span></span>

- <span data-ttu-id="d5189-129">使用可能な URL 値については、この記事の後半の「 [テナント許可/](#url-syntax-for-the-tenant-allowblock-list) ブロック一覧」セクションの URL 構文で説明します。</span><span class="sxs-lookup"><span data-stu-id="d5189-129">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

- <span data-ttu-id="d5189-130">テナント許可/ブロック一覧では、URL に対して最大 500 エントリ、ファイル ハッシュのエントリを 500 エントリまで使用できます。</span><span class="sxs-lookup"><span data-stu-id="d5189-130">The Tenant Allow/Block List allows a maximum of 500 entries for URLs, and 500 entries for file hashes.</span></span>

- <span data-ttu-id="d5189-131">各エントリの最大文字数は次の値です。</span><span class="sxs-lookup"><span data-stu-id="d5189-131">The maximum number of characters for each entry is:</span></span>
  - <span data-ttu-id="d5189-132">ファイル ハッシュ = 64</span><span class="sxs-lookup"><span data-stu-id="d5189-132">File hashes = 64</span></span>
  - <span data-ttu-id="d5189-133">URL = 250</span><span class="sxs-lookup"><span data-stu-id="d5189-133">URL = 250</span></span>

- <span data-ttu-id="d5189-134">エントリは 30 分以内にアクティブである必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5189-134">An entry should be active within 30 minutes.</span></span>

- <span data-ttu-id="d5189-135">既定では、テナント許可/ブロック一覧のエントリは 30 日後に期限切れになります。</span><span class="sxs-lookup"><span data-stu-id="d5189-135">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="d5189-136">日付を指定するか、有効期限が切れることはありません。</span><span class="sxs-lookup"><span data-stu-id="d5189-136">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="d5189-137">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d5189-137">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="d5189-138">スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d5189-138">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="d5189-139">この記事の手順を実行する際には、あらかじめExchange Online でアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5189-139">You need to be assigned permissions in Exchange Online before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="d5189-140">**URL とファイル**:</span><span class="sxs-lookup"><span data-stu-id="d5189-140">**URLs and files**:</span></span>
    - <span data-ttu-id="d5189-141">テナント許可/ブロック一覧の値を追加および削除するには、組織の管理またはセキュリティ管理者の役割グループのメンバー **である** 必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5189-141">To add and remove values from the Tenant Allow/Block List, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
    - <span data-ttu-id="d5189-142">テナント許可/ブロック一覧への読み取り専用アクセスでは、グローバル リーダーまたはセキュリティリーダーの役割グループの **メンバーである** 必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5189-142">For read-only access to the Tenant Allow/Block List, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>
  - <span data-ttu-id="d5189-143">**スプーフィン** グ: 次のいずれかの組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="d5189-143">**Spoofing**: One of the following combinations:</span></span>
    - <span data-ttu-id="d5189-144">**組織の管理**</span><span class="sxs-lookup"><span data-stu-id="d5189-144">**Organization Management**</span></span>
    - <span data-ttu-id="d5189-145">**セキュリティ管理者**<u>と</u>**表示のみ構成または\*\*\*\*表示のみ可能な組織の管理**。</span><span class="sxs-lookup"><span data-stu-id="d5189-145">**Security Administrator** <u>and</u> **View-Only Configuration** or **View-Only Organization Management**.</span></span>

  <span data-ttu-id="d5189-146">詳細については、「[Exchange Online のアクセス許可](/exchange/permissions-exo/permissions-exo)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d5189-146">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  >
  > - <span data-ttu-id="d5189-147">Microsoft 365 管理センターで、対応する Azure Active Directory の役割にユーザーを追加すると、ユーザーには、必要なアクセス許可 _および_ Microsoft 365 のその他の機能に必要なアクセス許可が付与されます。</span><span class="sxs-lookup"><span data-stu-id="d5189-147">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="d5189-148">詳細については、「[管理者の役割について](../../admin/add-users/about-admin-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d5189-148">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  >
  > - <span data-ttu-id="d5189-149">[Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) の **閲覧専用の組織管理** の役割グループが この機能への読み取り専用アクセス権も付与します。</span><span class="sxs-lookup"><span data-stu-id="d5189-149">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-create-block-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="d5189-150">テナント許可/Microsoft 365 Defenderリストにブロック URL エントリを作成するには、ポータルを使用します。</span><span class="sxs-lookup"><span data-stu-id="d5189-150">Use the Microsoft 365 Defender portal to create block URL entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="d5189-151">このポータルMicrosoft 365 Defender、[ポリシー] & **[** 脅威ポリシー ルール] セクションの [テナントの許可/ブロックリスト \>  \>  \> **] に移動します**。</span><span class="sxs-lookup"><span data-stu-id="d5189-151">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Rules** section \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="d5189-152">[テナントの **許可/ブロック一覧** ] ページで **、[URL]** タブが選択されているのを確認し、[ブロック] アイコン [ブロック] ![ を ](../../media/m365-cc-sc-create-icon.png) **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="d5189-152">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click ![Block icon](../../media/m365-cc-sc-create-icon.png) **Block**.</span></span>

3. <span data-ttu-id="d5189-153">表示される **[URL のブロック]** フライアウトで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="d5189-153">In the **Block URLs** flyout that appears, configure the following settings:</span></span>
   - <span data-ttu-id="d5189-154">**ワイルドカードを含む URL を追加する**: 1 行に 1 つの URL を入力し、最大 20 を入力します。</span><span class="sxs-lookup"><span data-stu-id="d5189-154">**Add URLs with wildcards**: Enter one URL per line, up to a maximum of 20.</span></span> <span data-ttu-id="d5189-155">URL エントリの構文の詳細については、この記事の後半の「テナント許可/ブロック一覧」セクションの [URL](#url-syntax-for-the-tenant-allowblock-list) 構文を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d5189-155">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>
   - <span data-ttu-id="d5189-156">**有効期限が切れる** ことはありません: 次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="d5189-156">**Never expire**: Do one of the following steps:</span></span>
     - <span data-ttu-id="d5189-157">設定がオフ (トグルオフ) になっていることを確認し、[削除] ボックスを使用してエントリの有効期限 ![ ](../../media/scc-toggle-off.png) を指定します。 </span><span class="sxs-lookup"><span data-stu-id="d5189-157">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Remove on** box to specify the expiration date for the entries.</span></span>

       <span data-ttu-id="d5189-158">または</span><span class="sxs-lookup"><span data-stu-id="d5189-158">or</span></span>

     - <span data-ttu-id="d5189-159">切り替えボタンを右に移動して、有効期限が切れなきエントリを構成します。</span><span class="sxs-lookup"><span data-stu-id="d5189-159">Move the toggle to the right to configure the entries to never expire:</span></span> ![オンに切り替え](../../media/scc-toggle-on.png)<span data-ttu-id="d5189-161">.</span><span class="sxs-lookup"><span data-stu-id="d5189-161">.</span></span>
   - <span data-ttu-id="d5189-162">**省略可能な** メモ: エントリの説明テキストを入力します。</span><span class="sxs-lookup"><span data-stu-id="d5189-162">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="d5189-163">完了したら、**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5189-163">When you're finished, click **Add**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-create-block-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="d5189-164">テナント許可/Microsoft 365 Defenderリストにブロック ファイル エントリを作成するには、このポータルを使用します。</span><span class="sxs-lookup"><span data-stu-id="d5189-164">Use the Microsoft 365 Defender portal to create block file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="d5189-165">このポータルMicrosoft 365 Defender、[ポリシー] & **[** 脅威ポリシー ルール] セクションの [テナントの許可/ブロックリスト \>  \>  \> **] に移動します**。</span><span class="sxs-lookup"><span data-stu-id="d5189-165">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Rules** section \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="d5189-166">[テナントの **許可/ブロック一覧**] ページで、[ファイル] タブを選択し、[ブロック] アイコン [ブロック] ![ を ](../../media/m365-cc-sc-create-icon.png) **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="d5189-166">On the **Tenant Allow/Block List** page, select the **Files** tab, and then click ![Block icon](../../media/m365-cc-sc-create-icon.png) **Block**.</span></span>

3. <span data-ttu-id="d5189-167">表示される **[ファイルのブロック** ] フライアウトで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="d5189-167">In the **Block files** flyout that appears, configure the following settings:</span></span>
   - <span data-ttu-id="d5189-168">**ファイル ハッシュの追加**: 1 行に 1 つの SHA256 ハッシュ値を入力し、最大 20 を入力します。</span><span class="sxs-lookup"><span data-stu-id="d5189-168">**Add file hashes**: Enter one SHA256 hash value per line, up to a maximum of 20.</span></span>
   - <span data-ttu-id="d5189-169">**有効期限が切れる** ことはありません: 次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="d5189-169">**Never expire**: Do one of the following steps:</span></span>
     - <span data-ttu-id="d5189-170">設定がオフ (トグルオフ) になっていることを確認し、[削除] ボックスを使用してエントリの有効期限 ![ ](../../media/scc-toggle-off.png) を指定します。 </span><span class="sxs-lookup"><span data-stu-id="d5189-170">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Remove on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="d5189-171">または</span><span class="sxs-lookup"><span data-stu-id="d5189-171">or</span></span>

     - <span data-ttu-id="d5189-172">切り替えボタンを右に移動して、有効期限が切れなきエントリを構成します。</span><span class="sxs-lookup"><span data-stu-id="d5189-172">Move the toggle to the right to configure the entries to never expire:</span></span> ![オンに切り替え](../../media/scc-toggle-on.png)<span data-ttu-id="d5189-174">.</span><span class="sxs-lookup"><span data-stu-id="d5189-174">.</span></span>
   - <span data-ttu-id="d5189-175">**省略可能な** メモ: エントリの説明テキストを入力します。</span><span class="sxs-lookup"><span data-stu-id="d5189-175">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="d5189-176">完了したら、**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5189-176">When you're finished, click **Add**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-create-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="d5189-177">テナント許可Microsoft 365 Defenderリストでスプーフィングされた送信者エントリを作成またはブロックするには、Microsoft 365 Defender ポータルを使用します。</span><span class="sxs-lookup"><span data-stu-id="d5189-177">Use the Microsoft 365 Defender portal to create allow or block spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="d5189-178">**注意**:</span><span class="sxs-lookup"><span data-stu-id="d5189-178">**Notes**:</span></span>

- <span data-ttu-id="d5189-179">スプー _フィング_ されたユーザーと、ドメイン ペアで定義されている送信インフラストラクチャの組み合わせだけが、スプーフィングを許可またはブロックされます。</span><span class="sxs-lookup"><span data-stu-id="d5189-179">Only the _combination_ of the spoofed user _and_ the sending infrastructure as defined in the domain pair is specifically allowed or blocked from spoofing.</span></span>
- <span data-ttu-id="d5189-180">ドメイン ペアの許可エントリまたはブロック エントリを構成すると、そのドメイン ペアからのメッセージはスプーフィング インテリジェンスインサイトに表示されなくなりました。</span><span class="sxs-lookup"><span data-stu-id="d5189-180">When you configure an allow or block entry for a domain pair, messages from that domain pair no longer appear in the spoof intelligence insight.</span></span>
- <span data-ttu-id="d5189-181">スプーフィングされた送信者のエントリは有効期限が切れることはありません。</span><span class="sxs-lookup"><span data-stu-id="d5189-181">Entries for spoofed senders never expire.</span></span>

1. <span data-ttu-id="d5189-182">このポータルMicrosoft 365 Defender、[ポリシー] & **[** 脅威ポリシー ルール] セクションの [テナントの許可/ブロックリスト \>  \>  \> **] に移動します**。</span><span class="sxs-lookup"><span data-stu-id="d5189-182">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Rules** section \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="d5189-183">[テナントの **許可/ブロックリスト] ページで** 、[スプーフィング] タブ **を選択** し、[ブロック] アイコン ![ [追加] を ](../../media/m365-cc-sc-create-icon.png) **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="d5189-183">On the **Tenant Allow/Block List** page, select the **Spoofing** tab, and then click ![Block icon](../../media/m365-cc-sc-create-icon.png) **Add**.</span></span>

3. <span data-ttu-id="d5189-184">表示される **[新しいドメイン ペアの追加** ] フライアウトで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="d5189-184">In the **Add new domain pairs** flyout that appears, configure the following settings:</span></span>
   - <span data-ttu-id="d5189-185">**ワイルドカードを使用して新しいドメイン ペア** を追加する: 1 行に 1 つのドメイン ペアを入力し、最大 20 まで入力します。</span><span class="sxs-lookup"><span data-stu-id="d5189-185">**Add new domain pairs with wildcards**: Enter one domain pair per line, up to a maximum of 20.</span></span> <span data-ttu-id="d5189-186">スプーフィングされた送信者エントリの構文の詳細については、この記事の後半の「テナント許可 [/](#domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list) ブロックリスト」セクションの「スプーフィングされた送信者エントリのドメインペア構文」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d5189-186">For details about the syntax for spoofed sender entries, see the [Domain pair syntax for spoofed sender entries in the Tenant Allow/Block List](#domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list) section later in this article.</span></span>
   - <span data-ttu-id="d5189-187">**スプーフィング** の種類: 次のいずれかの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="d5189-187">**Spoof type**: Select one of the following values:</span></span>
     - <span data-ttu-id="d5189-188">**内部**: スプーフィングされた送信者は、組織 (受け入れドメイン) に属する [ドメイン内にいます](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)。</span><span class="sxs-lookup"><span data-stu-id="d5189-188">**Internal**: The spoofed sender is in a domain that belongs to your organization (an [accepted domain](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)).</span></span>
     - <span data-ttu-id="d5189-189">**外部**: スプーフィングされた送信者が外部ドメイン内にある。</span><span class="sxs-lookup"><span data-stu-id="d5189-189">**External**: The spoofed sender is in an external domain.</span></span>
   - <span data-ttu-id="d5189-190">**アクション**: [許可] **または [ブロック]** **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="d5189-190">**Action**: Select **Allow** or **Block**.</span></span>

4. <span data-ttu-id="d5189-191">完了したら、**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5189-191">When you're finished, click **Add**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="d5189-192">テナント許可/Microsoft 365 Defenderリストのエントリを表示するには、ポータルを使用します。</span><span class="sxs-lookup"><span data-stu-id="d5189-192">Use the Microsoft 365 Defender portal to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="d5189-193">このポータルMicrosoft 365 Defender、[ポリシー] & **[** 脅威ポリシー ルール] セクションの [テナントの許可/ブロックリスト \>  \>  \> **] に移動します**。</span><span class="sxs-lookup"><span data-stu-id="d5189-193">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Rules** section \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="d5189-194">必要なタブを選択します。</span><span class="sxs-lookup"><span data-stu-id="d5189-194">Select the tab you want.</span></span> <span data-ttu-id="d5189-195">使用可能な列は、選択したタブによって異なる。</span><span class="sxs-lookup"><span data-stu-id="d5189-195">The columns that are available depend on the tab you selected:</span></span>

   - <span data-ttu-id="d5189-196">**URL**:</span><span class="sxs-lookup"><span data-stu-id="d5189-196">**URLs**:</span></span>
     - <span data-ttu-id="d5189-197">**値**: URL。</span><span class="sxs-lookup"><span data-stu-id="d5189-197">**Value**: The URL.</span></span>
     - <span data-ttu-id="d5189-198">**Action**: 値 **Block**.</span><span class="sxs-lookup"><span data-stu-id="d5189-198">**Action**: The value **Block**.</span></span>
     - <span data-ttu-id="d5189-199">**最終更新日時**</span><span class="sxs-lookup"><span data-stu-id="d5189-199">**Last updated**</span></span>
     - <span data-ttu-id="d5189-200">**Remove on**</span><span class="sxs-lookup"><span data-stu-id="d5189-200">**Remove on**</span></span>
     - <span data-ttu-id="d5189-201">**注**</span><span class="sxs-lookup"><span data-stu-id="d5189-201">**Notes**</span></span>
   - <span data-ttu-id="d5189-202">**Files**</span><span class="sxs-lookup"><span data-stu-id="d5189-202">**Files**</span></span>
     - <span data-ttu-id="d5189-203">**値**: ファイル ハッシュ。</span><span class="sxs-lookup"><span data-stu-id="d5189-203">**Value**: The file hash.</span></span>
     - <span data-ttu-id="d5189-204">**Action**: 値 **Block**.</span><span class="sxs-lookup"><span data-stu-id="d5189-204">**Action**: The value **Block**.</span></span>
     - <span data-ttu-id="d5189-205">**最終更新日時**</span><span class="sxs-lookup"><span data-stu-id="d5189-205">**Last updated**</span></span>
     - <span data-ttu-id="d5189-206">**Remove on**</span><span class="sxs-lookup"><span data-stu-id="d5189-206">**Remove on**</span></span>
     - <span data-ttu-id="d5189-207">**注**</span><span class="sxs-lookup"><span data-stu-id="d5189-207">**Notes**</span></span>
   - <span data-ttu-id="d5189-208">「**スプーフィング**」</span><span class="sxs-lookup"><span data-stu-id="d5189-208">**Spoofing**</span></span>
     - <span data-ttu-id="d5189-209">**スプーフィングされたユーザー**</span><span class="sxs-lookup"><span data-stu-id="d5189-209">**Spoofed user**</span></span>
     - <span data-ttu-id="d5189-210">**インフラストラクチャの送信**</span><span class="sxs-lookup"><span data-stu-id="d5189-210">**Sending infrastructure**</span></span>
     - <span data-ttu-id="d5189-211">**スプーフィングの** 種類 : **値 Internal または** **External** です。</span><span class="sxs-lookup"><span data-stu-id="d5189-211">**Spoof type**: The value **Internal** or **External**.</span></span>
     - <span data-ttu-id="d5189-212">**Action**: 値 Block **or** **Allow**.</span><span class="sxs-lookup"><span data-stu-id="d5189-212">**Action**: The value **Block** or **Allow**.</span></span>

   <span data-ttu-id="d5189-213">列見出しをクリックすると、昇順または降順で並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="d5189-213">You can click on a column heading to sort in ascending or descending order.</span></span>

   <span data-ttu-id="d5189-214">[グループ化] **をクリック** すると、結果をグループ化できます。</span><span class="sxs-lookup"><span data-stu-id="d5189-214">You can click **Group** to group the results.</span></span> <span data-ttu-id="d5189-215">使用可能な値は、選択したタブによって異なる。</span><span class="sxs-lookup"><span data-stu-id="d5189-215">The values that are available depend on the tab you selected:</span></span>

   - <span data-ttu-id="d5189-216">**URL :** アクションで結果をグループ化 **できます**。</span><span class="sxs-lookup"><span data-stu-id="d5189-216">**URLs**: You can group the results by **Action**.</span></span>
   - <span data-ttu-id="d5189-217">**ファイル**: アクションで結果をグループ **化できます**。</span><span class="sxs-lookup"><span data-stu-id="d5189-217">**Files**: You can group the results by **Action**.</span></span>
   - <span data-ttu-id="d5189-218">**スプーフィン** グ : アクションまたはスプーフィングの種類 **で結果** を **グループ化できます**。</span><span class="sxs-lookup"><span data-stu-id="d5189-218">**Spoofing**: You can group the results by **Action** or **Spoof type**.</span></span>

   <span data-ttu-id="d5189-219">[ **検索]** をクリックし、値のすべてまたは一部を入力し、Enter キーを押して特定の値を検索します。</span><span class="sxs-lookup"><span data-stu-id="d5189-219">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="d5189-220">完了したら、[検索のクリア] アイコン [検索のクリア] ![ ](../../media/m365-cc-sc-close-icon.png) **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="d5189-220">When you're finished, click ![Clear search icon](../../media/m365-cc-sc-close-icon.png) **Clear search**.</span></span>

   <span data-ttu-id="d5189-221">[フィルター **] をクリック** して結果をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="d5189-221">Click **Filter** to filter the results.</span></span> <span data-ttu-id="d5189-222">表示されるフィルター フライアウト **で** 使用できる値は、選択したタブによって異なる。</span><span class="sxs-lookup"><span data-stu-id="d5189-222">The values that are available in **Filter** flyout that appears depend on the tab you selected:</span></span>

   - <span data-ttu-id="d5189-223">**URL**</span><span class="sxs-lookup"><span data-stu-id="d5189-223">**URLs**</span></span>
     - <span data-ttu-id="d5189-224">**Action**</span><span class="sxs-lookup"><span data-stu-id="d5189-224">**Action**</span></span>
     - <span data-ttu-id="d5189-225">**有効期限が切れることはありません**</span><span class="sxs-lookup"><span data-stu-id="d5189-225">**Never expire**</span></span>
     - <span data-ttu-id="d5189-226">**最終更新日**</span><span class="sxs-lookup"><span data-stu-id="d5189-226">**Last updated date**</span></span>
     - <span data-ttu-id="d5189-227">**Remove on**</span><span class="sxs-lookup"><span data-stu-id="d5189-227">**Remove on**</span></span>
   - <span data-ttu-id="d5189-228">**Files**</span><span class="sxs-lookup"><span data-stu-id="d5189-228">**Files**</span></span>
     - <span data-ttu-id="d5189-229">**Action**</span><span class="sxs-lookup"><span data-stu-id="d5189-229">**Action**</span></span>
     - <span data-ttu-id="d5189-230">**有効期限が切れることはありません**</span><span class="sxs-lookup"><span data-stu-id="d5189-230">**Never expire**</span></span>
     - <span data-ttu-id="d5189-231">**最終更新日時**</span><span class="sxs-lookup"><span data-stu-id="d5189-231">**Last updated**</span></span>
     - <span data-ttu-id="d5189-232">**Remove on**</span><span class="sxs-lookup"><span data-stu-id="d5189-232">**Remove on**</span></span>
   - <span data-ttu-id="d5189-233">「**スプーフィング**」</span><span class="sxs-lookup"><span data-stu-id="d5189-233">**Spoofing**</span></span>
     - <span data-ttu-id="d5189-234">**Action**</span><span class="sxs-lookup"><span data-stu-id="d5189-234">**Action**</span></span>
     - <span data-ttu-id="d5189-235">**スプーフィングの種類**</span><span class="sxs-lookup"><span data-stu-id="d5189-235">**Spoof type**</span></span>

   <span data-ttu-id="d5189-236">完了したら、[適用] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="d5189-236">When you're finished, click **Apply**.</span></span> <span data-ttu-id="d5189-237">既存のフィルターをクリアするには、[**フィルター**] をクリックし、表示される [フィルター] フライアウトで 、[フィルターのクリア]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="d5189-237">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="d5189-238">テナント許可/Microsoft 365 Defenderリストのエントリを変更するには、ポータルを使用します。</span><span class="sxs-lookup"><span data-stu-id="d5189-238">Use the Microsoft 365 Defender portal to modify entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="d5189-239">このポータルMicrosoft 365 Defender、[ポリシー] & **[** 脅威ポリシー ルール] セクションの [テナントの許可/ブロックリスト \>  \>  \> **] に移動します**。</span><span class="sxs-lookup"><span data-stu-id="d5189-239">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Rules** section \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="d5189-240">変更するエントリの種類を含むタブを選択します。</span><span class="sxs-lookup"><span data-stu-id="d5189-240">Select the tab that contains the type of entry that you want to modify:</span></span>
   - <span data-ttu-id="d5189-241">**URL**</span><span class="sxs-lookup"><span data-stu-id="d5189-241">**URLs**</span></span>
   - <span data-ttu-id="d5189-242">**Files**</span><span class="sxs-lookup"><span data-stu-id="d5189-242">**Files**</span></span>
   - <span data-ttu-id="d5189-243">「**スプーフィング**」</span><span class="sxs-lookup"><span data-stu-id="d5189-243">**Spoofing**</span></span>

3. <span data-ttu-id="d5189-244">変更するエントリを選択し、[編集] アイコン [編集] ![ を ](../../media/m365-cc-sc-edit-icon.png) **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="d5189-244">Select the entry that you want to modify, and then click ![Edit icon](../../media/m365-cc-sc-edit-icon.png) **Edit**.</span></span> <span data-ttu-id="d5189-245">表示されるフライアウトで変更できる値は、前の手順で選択したタブによって異なっています。</span><span class="sxs-lookup"><span data-stu-id="d5189-245">The values that you are able to modify in the flyout that appears depend on the tab you selected in the previous step:</span></span>
   - <span data-ttu-id="d5189-246">**URL**</span><span class="sxs-lookup"><span data-stu-id="d5189-246">**URLs**</span></span>
     - <span data-ttu-id="d5189-247">**有効期限や有効期限** はありません。</span><span class="sxs-lookup"><span data-stu-id="d5189-247">**Never expire** and/or expiration date.</span></span>
     - <span data-ttu-id="d5189-248">**省略可能なメモ**</span><span class="sxs-lookup"><span data-stu-id="d5189-248">**Optional note**</span></span>
   - <span data-ttu-id="d5189-249">**Files**</span><span class="sxs-lookup"><span data-stu-id="d5189-249">**Files**</span></span>
     - <span data-ttu-id="d5189-250">**有効期限や有効期限** はありません。</span><span class="sxs-lookup"><span data-stu-id="d5189-250">**Never expire** and/or expiration date.</span></span>
     - <span data-ttu-id="d5189-251">**省略可能なメモ**</span><span class="sxs-lookup"><span data-stu-id="d5189-251">**Optional note**</span></span>
   - <span data-ttu-id="d5189-252">「**スプーフィング**」</span><span class="sxs-lookup"><span data-stu-id="d5189-252">**Spoofing**</span></span>
     - <span data-ttu-id="d5189-253">**アクション**: 値を [許可] または [ブロック **] に\*\*\*\*変更できます**。</span><span class="sxs-lookup"><span data-stu-id="d5189-253">**Action**: You can change the value to **Allow** or **Block**.</span></span>
4. <span data-ttu-id="d5189-254">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5189-254">When you're finished, click **Save**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="d5189-255">テナント許可/Microsoft 365 Defenderリストからエントリを削除するには、ポータルポータルを使用します。</span><span class="sxs-lookup"><span data-stu-id="d5189-255">Use the Microsoft 365 Defender portal to remove entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="d5189-256">このポータルMicrosoft 365 Defender、[ポリシー] & **[** 脅威ポリシー ルール] セクションの [テナントの許可/ブロックリスト \>  \>  \> **] に移動します**。</span><span class="sxs-lookup"><span data-stu-id="d5189-256">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Rules** section \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="d5189-257">削除するエントリの種類を含むタブを選択します。</span><span class="sxs-lookup"><span data-stu-id="d5189-257">Select the tab that contains the type of entry that you want to remove:</span></span>
   - <span data-ttu-id="d5189-258">**URL**</span><span class="sxs-lookup"><span data-stu-id="d5189-258">**URLs**</span></span>
   - <span data-ttu-id="d5189-259">**Files**</span><span class="sxs-lookup"><span data-stu-id="d5189-259">**Files**</span></span>
   - <span data-ttu-id="d5189-260">「**スプーフィング**」</span><span class="sxs-lookup"><span data-stu-id="d5189-260">**Spoofing**</span></span>

3. <span data-ttu-id="d5189-261">削除するエントリを選択し、[削除] アイコン [削除] ![ を ](../../media/m365-cc-sc-delete-icon.png) **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="d5189-261">Select the entry that you want to remove, and then click ![Delete icon](../../media/m365-cc-sc-delete-icon.png) **Delete**.</span></span>

4. <span data-ttu-id="d5189-262">表示される警告ダイアログで、[削除] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="d5189-262">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="d5189-263">PowerShell Exchange Onlineスタンドアロン EOP PowerShell を使用してテナント許可/ブロック一覧を構成する</span><span class="sxs-lookup"><span data-stu-id="d5189-263">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-block-file-or-url-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="d5189-264">PowerShell を使用して、テナントの許可/ブロックリストにブロック ファイルまたは URL エントリを追加する</span><span class="sxs-lookup"><span data-stu-id="d5189-264">Use PowerShell to add block file or URL entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="d5189-265">テナント許可/ブロック一覧にブロック ファイルまたは URL エントリを追加するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="d5189-265">To add block file or URL entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType <FileHash | Url> -Block -Entries "Value1","Value2",..."ValueN" <-ExpirationDate Date | -NoExpiration> [-Notes <String>]
```

<span data-ttu-id="d5189-266">次の使用例は、有効期限が切れることはありません指定したファイルのブロック ファイル エントリを追加します。</span><span class="sxs-lookup"><span data-stu-id="d5189-266">This example adds a block file entry for the specified files that never expires.</span></span>

```powershell
New-TenantAllowBlockListItems -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

<span data-ttu-id="d5189-267">次の使用例は、contoso.com およびすべてのサブドメイン (contoso.com、www.contoso.com、および xyz.abc.contoso.com) のブロック URL エントリを追加します。</span><span class="sxs-lookup"><span data-stu-id="d5189-267">This example adds a block URL entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="d5189-268">ExpirationDate パラメーターまたは NoExpiration パラメーターを使用しないので、エントリは 30 日後に期限切れになります。</span><span class="sxs-lookup"><span data-stu-id="d5189-268">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItems -ListType Url -Block -Entries ~contoso.com
```

<span data-ttu-id="d5189-269">構文とパラメーターの詳細については [、「New-TenantAllowBlockListItems」を参照してください](/powershell/module/exchange/new-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="d5189-269">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-add-allow-or-block-spoofed-sender-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="d5189-270">PowerShell を使用して、スプーフィングされた送信者エントリをテナント許可/ブロックリストに追加またはブロックする</span><span class="sxs-lookup"><span data-stu-id="d5189-270">Use PowerShell to add allow or block spoofed sender entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="d5189-271">テナント許可/ブロック一覧にスプーフィングされた送信者エントリを追加するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="d5189-271">To add spoofed sender entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListSpoofItems -SpoofedUser <Domain | EmailAddress | *> -SendingInfrastructure <Domain | IPAddress/24> -SpoofType <External | Internal> -Action <Allow | Block>
```

<span data-ttu-id="d5189-272">構文とパラメーターの詳細については [、「New-TenantAllowBlockListSpoofItems」を参照してください](/powershell/module/exchange/new-tenantallowblocklistspoofitems)。</span><span class="sxs-lookup"><span data-stu-id="d5189-272">For detailed syntax and parameter information, see [New-TenantAllowBlockListSpoofItems](/powershell/module/exchange/new-tenantallowblocklistspoofitems).</span></span>

### <a name="use-powershell-to-view-block-file-or-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="d5189-273">PowerShell を使用して、テナント許可/ブロック一覧のブロック ファイルまたは URL エントリを表示する</span><span class="sxs-lookup"><span data-stu-id="d5189-273">Use PowerShell to view block file or URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="d5189-274">テナント許可/ブロック一覧でブロック ファイルまたは URL エントリを表示するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="d5189-274">To view block file or URL entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType <FileHash | URL> [-Entry <FileHashValue | URLValue>] [<-ExpirationDate Date | -NoExpiration>]
```

<span data-ttu-id="d5189-275">次の使用例は、指定したファイル ハッシュ値の情報を返します。</span><span class="sxs-lookup"><span data-stu-id="d5189-275">This example returns information for the specified file hash value.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

<span data-ttu-id="d5189-276">この例では、ブロックされているすべての URL を返します。</span><span class="sxs-lookup"><span data-stu-id="d5189-276">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Block
```

<span data-ttu-id="d5189-277">構文とパラメーターの詳細については [、「Get-TenantAllowBlockListItems」を参照してください](/powershell/module/exchange/get-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="d5189-277">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="d5189-278">PowerShell を使用して、テナント許可/ブロック一覧でスプーフィングされた送信者エントリを表示またはブロックする</span><span class="sxs-lookup"><span data-stu-id="d5189-278">Use PowerShell to view allow or block spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="d5189-279">テナント許可/ブロック一覧でスプーフィングされた送信者エントリを表示するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="d5189-279">To view spoofed sender entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems [-Action <Allow | Block>] [-SpoofType <External | Internal>
```

<span data-ttu-id="d5189-280">この例では、テナント許可/ブロック一覧のすべてのスプーフィングされた送信者エントリを返します。</span><span class="sxs-lookup"><span data-stu-id="d5189-280">This example returns all spoofed sender entries in the Tenant Allow/Block List.</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems
```

<span data-ttu-id="d5189-281">次の使用例は、内部のスプーフィングされた送信者エントリをすべて返します。</span><span class="sxs-lookup"><span data-stu-id="d5189-281">This example returns all allow spoofed sender entries that are internal.</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems -Action Allow -SpoofType Internal
```

<span data-ttu-id="d5189-282">次の使用例は、外部のすべてのスプーフィングされた送信者エントリを返します。</span><span class="sxs-lookup"><span data-stu-id="d5189-282">This example returns all blocked spoofed sender entries that are external.</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems -Action Block -SpoofType External
```

<span data-ttu-id="d5189-283">構文とパラメーターの詳細については [、「Get-TenantAllowBlockListSpoofItems」を参照してください](/powershell/module/exchange/get-tenantallowblocklistspoofitems)。</span><span class="sxs-lookup"><span data-stu-id="d5189-283">For detailed syntax and parameter information, see [Get-TenantAllowBlockListSpoofItems](/powershell/module/exchange/get-tenantallowblocklistspoofitems).</span></span>

### <a name="use-powershell-to-modify-block-file-and-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="d5189-284">PowerShell を使用して、テナント許可/ブロック一覧のブロック ファイルと URL エントリを変更する</span><span class="sxs-lookup"><span data-stu-id="d5189-284">Use PowerShell to modify block file and URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="d5189-285">テナント許可/ブロック一覧のブロック ファイルと URL エントリを変更するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="d5189-285">To modify block file and URL entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType <FileHash | Url> -Ids <"Id1","Id2",..."IdN"> [<-ExpirationDate Date | -NoExpiration>] [-Notes <String>]
```

<span data-ttu-id="d5189-286">次の使用例は、指定したブロック URL エントリの有効期限を変更します。</span><span class="sxs-lookup"><span data-stu-id="d5189-286">This example changes the expiration date of the specified block URL entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate "5/30/2020"
```

<span data-ttu-id="d5189-287">構文とパラメーターの詳細については [、「Set-TenantAllowBlockListItems」を参照してください](/powershell/module/exchange/set-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="d5189-287">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="d5189-288">PowerShell を使用して、テナント許可/ブロック一覧のスプーフィングされた送信者エントリを変更またはブロックする</span><span class="sxs-lookup"><span data-stu-id="d5189-288">Use PowerShell to modify allow or block spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="d5189-289">テナント許可/ブロック一覧でスプーフィングされた送信者エントリの許可またはブロックを変更するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="d5189-289">To modify allow or block spoofed sender entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN"> -Action <Allow | Block>
```

<span data-ttu-id="d5189-290">次の使用例は、スプーフィングされた送信者エントリを許可からブロックに変更します。</span><span class="sxs-lookup"><span data-stu-id="d5189-290">This example changes spoofed sender entry from allow to block.</span></span>

```powershell
Set-TenantAllowBlockListItems -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -Action Block
```

<span data-ttu-id="d5189-291">構文とパラメーターの詳細については [、「Set-TenantAllowBlockListSpoofItems」を参照してください](/powershell/module/exchange/set-tenantallowblocklistspoofitems)。</span><span class="sxs-lookup"><span data-stu-id="d5189-291">For detailed syntax and parameter information, see [Set-TenantAllowBlockListSpoofItems](/powershell/module/exchange/set-tenantallowblocklistspoofitems).</span></span>

### <a name="use-powershell-to-remove-url-or-file-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="d5189-292">PowerShell を使用してテナント許可/ブロック一覧から URL またはファイル エントリを削除する</span><span class="sxs-lookup"><span data-stu-id="d5189-292">Use PowerShell to remove URL or file entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="d5189-293">テナント許可/ブロック一覧からファイルエントリと URL エントリを削除するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="d5189-293">To remove file and URL entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType <FileHash | Url> -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="d5189-294">次の使用例は、指定したブロック URL エントリをテナント許可/ブロック一覧から削除します。</span><span class="sxs-lookup"><span data-stu-id="d5189-294">This example removes the specified block URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="d5189-295">構文とパラメーターの詳細については [、「Remove-TenantAllowBlockListItems」を参照してください](/powershell/module/exchange/remove-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="d5189-295">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-allow-or-block-spoofed-sender-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="d5189-296">PowerShell を使用して、テナント許可/ブロック一覧からスプーフィングされた送信者エントリの許可またはブロックを削除する</span><span class="sxs-lookup"><span data-stu-id="d5189-296">Use PowerShell to remove allow or block spoofed sender entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="d5189-297">テナント許可/ブロック一覧からスプーフィング送信者エントリを許可またはブロックするには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="d5189-297">To remove allow or block spoof sender entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="d5189-298">構文とパラメーターの詳細については [、「Remove-TenantAllowBlockListSpoofItems」を参照してください](/powershell/module/exchange/remove-tenantallowblocklistspoofitems)。</span><span class="sxs-lookup"><span data-stu-id="d5189-298">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListSpoofItems](/powershell/module/exchange/remove-tenantallowblocklistspoofitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="d5189-299">テナント許可/ブロック一覧の URL 構文</span><span class="sxs-lookup"><span data-stu-id="d5189-299">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="d5189-300">IP4v および IPv6 アドレスは許可されますが、TCP/UDP ポートは許可されません。</span><span class="sxs-lookup"><span data-stu-id="d5189-300">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="d5189-301">ファイル名の拡張子は許可されません (たとえば、test.pdf)。</span><span class="sxs-lookup"><span data-stu-id="d5189-301">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="d5189-302">Unicode はサポートされていませんが、Punycode はです。</span><span class="sxs-lookup"><span data-stu-id="d5189-302">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="d5189-303">ホスト名は、次のすべてのステートメントが true の場合に許可されます。</span><span class="sxs-lookup"><span data-stu-id="d5189-303">Hostnames are allowed if all of the following statements are true:</span></span>
  - <span data-ttu-id="d5189-304">ホスト名にはピリオドが含まれる。</span><span class="sxs-lookup"><span data-stu-id="d5189-304">The hostname contains a period.</span></span>
  - <span data-ttu-id="d5189-305">ピリオドの左側に少なくとも 1 つの文字があります。</span><span class="sxs-lookup"><span data-stu-id="d5189-305">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="d5189-306">ピリオドの右側には、少なくとも 2 つの文字があります。</span><span class="sxs-lookup"><span data-stu-id="d5189-306">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="d5189-307">たとえば、 `t.co` 許可されている、または `.com` `contoso.` 許可されない。</span><span class="sxs-lookup"><span data-stu-id="d5189-307">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="d5189-308">サブパスは暗黙的ではありません。</span><span class="sxs-lookup"><span data-stu-id="d5189-308">Subpaths are not implied.</span></span>

  <span data-ttu-id="d5189-309">たとえば、 `contoso.com` は含めではありません `contoso.com/a` 。</span><span class="sxs-lookup"><span data-stu-id="d5189-309">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="d5189-310">ワイルドカード (\*) は、次のシナリオで使用できます。</span><span class="sxs-lookup"><span data-stu-id="d5189-310">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="d5189-311">サブドメインを指定するには、左のワイルドカードの後にピリオドを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5189-311">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="d5189-312">たとえば、 `*.contoso.com` 許可されます。 `*contoso.com` 許可されません。</span><span class="sxs-lookup"><span data-stu-id="d5189-312">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="d5189-313">パスを指定するには、右のワイルドカードがスラッシュ (/) に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5189-313">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="d5189-314">たとえば、 `contoso.com/*` 許可されている、または `contoso.com*` `contoso.com/ab*` 許可されない。</span><span class="sxs-lookup"><span data-stu-id="d5189-314">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="d5189-315">すべてのサブパスは、適切なワイルドカードによって暗示されるものではありません。</span><span class="sxs-lookup"><span data-stu-id="d5189-315">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="d5189-316">たとえば、 `contoso.com/*` は含めではありません `contoso.com/a` 。</span><span class="sxs-lookup"><span data-stu-id="d5189-316">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="d5189-317">`*.com*` は無効です (解決可能なドメインではなく、右のワイルドカードはスラッシュに従います)。</span><span class="sxs-lookup"><span data-stu-id="d5189-317">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="d5189-318">IP アドレスではワイルドカードは使用できません。</span><span class="sxs-lookup"><span data-stu-id="d5189-318">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="d5189-319">チルダ (~) 文字は、次のシナリオで使用できます。</span><span class="sxs-lookup"><span data-stu-id="d5189-319">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="d5189-320">左チルダは、ドメインとすべてのサブドメインを意味します。</span><span class="sxs-lookup"><span data-stu-id="d5189-320">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="d5189-321">たとえば `~contoso.com` 、includes `contoso.com` と `*.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="d5189-321">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="d5189-322">URL エントリは、すべてのプロトコルに適用されるので、プロトコルを含む URL エントリ (たとえば `http://` `https://` `ftp://` 、) は失敗します。</span><span class="sxs-lookup"><span data-stu-id="d5189-322">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="d5189-323">ユーザー名またはパスワードはサポートされていないか、必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="d5189-323">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="d5189-324">引用符 (' または ") は無効な文字です。</span><span class="sxs-lookup"><span data-stu-id="d5189-324">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="d5189-325">URL には、可能な限りすべてのリダイレクトが含まれる必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5189-325">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="d5189-326">URL エントリのシナリオ</span><span class="sxs-lookup"><span data-stu-id="d5189-326">URL entry scenarios</span></span>

<span data-ttu-id="d5189-327">有効な URL エントリとその結果については、次のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="d5189-327">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="d5189-328">シナリオ: ワイルドカードなし</span><span class="sxs-lookup"><span data-stu-id="d5189-328">Scenario: No wildcards</span></span>

<span data-ttu-id="d5189-329">**エントリ**: `contoso.com`</span><span class="sxs-lookup"><span data-stu-id="d5189-329">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="d5189-330">**一致を許可** する : contoso.com</span><span class="sxs-lookup"><span data-stu-id="d5189-330">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="d5189-331">**[一致しない] を許可します**。</span><span class="sxs-lookup"><span data-stu-id="d5189-331">**Allow not matched**:</span></span>

  - <span data-ttu-id="d5189-332">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="d5189-332">abc-contoso.com</span></span>
  - <span data-ttu-id="d5189-333">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="d5189-333">contoso.com/a</span></span>
  - <span data-ttu-id="d5189-334">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d5189-334">payroll.contoso.com</span></span>
  - <span data-ttu-id="d5189-335">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="d5189-335">test.com/contoso.com</span></span>
  - <span data-ttu-id="d5189-336">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="d5189-336">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="d5189-337">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d5189-337">www.contoso.com</span></span>
  - <span data-ttu-id="d5189-338">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="d5189-338">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="d5189-339">**ブロック一致**:</span><span class="sxs-lookup"><span data-stu-id="d5189-339">**Block match**:</span></span>

  - <span data-ttu-id="d5189-340">contoso.com</span><span class="sxs-lookup"><span data-stu-id="d5189-340">contoso.com</span></span>
  - <span data-ttu-id="d5189-341">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="d5189-341">contoso.com/a</span></span>
  - <span data-ttu-id="d5189-342">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d5189-342">payroll.contoso.com</span></span>
  - <span data-ttu-id="d5189-343">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="d5189-343">test.com/contoso.com</span></span>
  - <span data-ttu-id="d5189-344">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="d5189-344">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="d5189-345">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d5189-345">www.contoso.com</span></span>
  - <span data-ttu-id="d5189-346">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="d5189-346">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="d5189-347">**ブロックが一致しない**: abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="d5189-347">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="d5189-348">シナリオ: 左ワイルドカード (サブドメイン)</span><span class="sxs-lookup"><span data-stu-id="d5189-348">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="d5189-349">**エントリ**: `*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="d5189-349">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="d5189-350">**一致とブロック** の **一致を許可する**:</span><span class="sxs-lookup"><span data-stu-id="d5189-350">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="d5189-351">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d5189-351">www.contoso.com</span></span>
  - <span data-ttu-id="d5189-352">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d5189-352">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="d5189-353">**[一致しない] と** [ **ブロックが一致しない] を許可します**。</span><span class="sxs-lookup"><span data-stu-id="d5189-353">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="d5189-354">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="d5189-354">123contoso.com</span></span>
  - <span data-ttu-id="d5189-355">contoso.com</span><span class="sxs-lookup"><span data-stu-id="d5189-355">contoso.com</span></span>
  - <span data-ttu-id="d5189-356">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="d5189-356">test.com/contoso.com</span></span>
  - <span data-ttu-id="d5189-357">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="d5189-357">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="d5189-358">シナリオ: パスの上部にある右のワイルドカード</span><span class="sxs-lookup"><span data-stu-id="d5189-358">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="d5189-359">**エントリ**: `contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="d5189-359">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="d5189-360">**一致とブロック** の **一致を許可する**:</span><span class="sxs-lookup"><span data-stu-id="d5189-360">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="d5189-361">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="d5189-361">contoso.com/a/b</span></span>
  - <span data-ttu-id="d5189-362">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="d5189-362">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="d5189-363">contoso.com/a/?q=joe@t.com</span><span class="sxs-lookup"><span data-stu-id="d5189-363">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="d5189-364">**[一致しない] と** [ **ブロックが一致しない] を許可します**。</span><span class="sxs-lookup"><span data-stu-id="d5189-364">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="d5189-365">contoso.com</span><span class="sxs-lookup"><span data-stu-id="d5189-365">contoso.com</span></span>
  - <span data-ttu-id="d5189-366">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="d5189-366">contoso.com/a</span></span>
  - <span data-ttu-id="d5189-367">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d5189-367">www.contoso.com</span></span>
  - <span data-ttu-id="d5189-368">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="d5189-368">www.contoso.com/q=a@contoso.com</span></span>

#### <a name="scenario-left-tilde"></a><span data-ttu-id="d5189-369">シナリオ: 左チルダ</span><span class="sxs-lookup"><span data-stu-id="d5189-369">Scenario: Left tilde</span></span>

<span data-ttu-id="d5189-370">**エントリ**: `~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="d5189-370">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="d5189-371">**一致とブロック** の **一致を許可する**:</span><span class="sxs-lookup"><span data-stu-id="d5189-371">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="d5189-372">contoso.com</span><span class="sxs-lookup"><span data-stu-id="d5189-372">contoso.com</span></span>
  - <span data-ttu-id="d5189-373">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d5189-373">www.contoso.com</span></span>
  - <span data-ttu-id="d5189-374">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d5189-374">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="d5189-375">**[一致しない] と** [ **ブロックが一致しない] を許可します**。</span><span class="sxs-lookup"><span data-stu-id="d5189-375">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="d5189-376">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="d5189-376">123contoso.com</span></span>
  - <span data-ttu-id="d5189-377">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="d5189-377">contoso.com/abc</span></span>
  - <span data-ttu-id="d5189-378">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="d5189-378">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="d5189-379">シナリオ: 右のワイルドカード サフィックス</span><span class="sxs-lookup"><span data-stu-id="d5189-379">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="d5189-380">**エントリ**: `contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="d5189-380">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="d5189-381">**一致とブロック** の **一致を許可する**:</span><span class="sxs-lookup"><span data-stu-id="d5189-381">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="d5189-382">contoso.com/?q=whatever@fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="d5189-382">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="d5189-383">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="d5189-383">contoso.com/a</span></span>
  - <span data-ttu-id="d5189-384">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="d5189-384">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="d5189-385">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="d5189-385">contoso.com/ab</span></span>
  - <span data-ttu-id="d5189-386">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="d5189-386">contoso.com/b</span></span>
  - <span data-ttu-id="d5189-387">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="d5189-387">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="d5189-388">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="d5189-388">contoso.com/ba</span></span>

- <span data-ttu-id="d5189-389">**[一致しない] と** **[ブロックが一致しない**] : contoso.com</span><span class="sxs-lookup"><span data-stu-id="d5189-389">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="d5189-390">シナリオ: 左ワイルドカード サブドメインと右のワイルドカード サフィックス</span><span class="sxs-lookup"><span data-stu-id="d5189-390">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="d5189-391">**エントリ**: `*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="d5189-391">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="d5189-392">**一致とブロック** の **一致を許可する**:</span><span class="sxs-lookup"><span data-stu-id="d5189-392">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="d5189-393">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="d5189-393">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="d5189-394">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="d5189-394">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="d5189-395">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="d5189-395">www.contoso.com/a</span></span>
  - <span data-ttu-id="d5189-396">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="d5189-396">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="d5189-397">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="d5189-397">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="d5189-398">**[一致しない] と** **[ブロックが一致しない**] : contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="d5189-398">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="d5189-399">シナリオ: 左右のチルダ</span><span class="sxs-lookup"><span data-stu-id="d5189-399">Scenario: Left and right tilde</span></span>

<span data-ttu-id="d5189-400">**エントリ**: `~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="d5189-400">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="d5189-401">**一致とブロック** の **一致を許可する**:</span><span class="sxs-lookup"><span data-stu-id="d5189-401">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="d5189-402">contoso.com</span><span class="sxs-lookup"><span data-stu-id="d5189-402">contoso.com</span></span>
  - <span data-ttu-id="d5189-403">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="d5189-403">contoso.com/a</span></span>
  - <span data-ttu-id="d5189-404">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d5189-404">www.contoso.com</span></span>
  - <span data-ttu-id="d5189-405">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="d5189-405">www.contoso.com/b</span></span>
  - <span data-ttu-id="d5189-406">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d5189-406">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="d5189-407">**[一致しない] と** [ **ブロックが一致しない] を許可します**。</span><span class="sxs-lookup"><span data-stu-id="d5189-407">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="d5189-408">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="d5189-408">123contoso.com</span></span>
  - <span data-ttu-id="d5189-409">contoso.org</span><span class="sxs-lookup"><span data-stu-id="d5189-409">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="d5189-410">シナリオ: IP アドレス</span><span class="sxs-lookup"><span data-stu-id="d5189-410">Scenario: IP address</span></span>

<span data-ttu-id="d5189-411">**エントリ**: `1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="d5189-411">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="d5189-412">**一致と\*\*\*\*ブロックの一** 致を許可する : 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="d5189-412">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="d5189-413">**[一致しない] と** [ **ブロックが一致しない] を許可します**。</span><span class="sxs-lookup"><span data-stu-id="d5189-413">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="d5189-414">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="d5189-414">1.2.3.4/a</span></span>
  - <span data-ttu-id="d5189-415">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="d5189-415">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="d5189-416">適切なワイルドカードを持つ IP アドレス</span><span class="sxs-lookup"><span data-stu-id="d5189-416">IP address with right wildcard</span></span>

<span data-ttu-id="d5189-417">**エントリ**: `1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="d5189-417">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="d5189-418">**一致とブロック** の **一致を許可する**:</span><span class="sxs-lookup"><span data-stu-id="d5189-418">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="d5189-419">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="d5189-419">1.2.3.4/b</span></span>
  - <span data-ttu-id="d5189-420">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="d5189-420">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="d5189-421">無効なエントリの例</span><span class="sxs-lookup"><span data-stu-id="d5189-421">Examples of invalid entries</span></span>

<span data-ttu-id="d5189-422">次のエントリが無効です。</span><span class="sxs-lookup"><span data-stu-id="d5189-422">The following entries are invalid:</span></span>

- <span data-ttu-id="d5189-423">**ドメイン値が見つからないか無効です**。</span><span class="sxs-lookup"><span data-stu-id="d5189-423">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="d5189-424">contoso</span><span class="sxs-lookup"><span data-stu-id="d5189-424">contoso</span></span>
  - <span data-ttu-id="d5189-425">\*.contoso.\*</span><span class="sxs-lookup"><span data-stu-id="d5189-425">\*.contoso.\*</span></span>
  - <span data-ttu-id="d5189-426">\*.com</span><span class="sxs-lookup"><span data-stu-id="d5189-426">\*.com</span></span>
  - <span data-ttu-id="d5189-427">\*.pdf</span><span class="sxs-lookup"><span data-stu-id="d5189-427">\*.pdf</span></span>

- <span data-ttu-id="d5189-428">**テキストまたはスペース文字なしのワイルドカード**:</span><span class="sxs-lookup"><span data-stu-id="d5189-428">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="d5189-429">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="d5189-429">\*contoso.com</span></span>
  - <span data-ttu-id="d5189-430">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="d5189-430">contoso.com\*</span></span>
  - <span data-ttu-id="d5189-431">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="d5189-431">\*1.2.3.4</span></span>
  - <span data-ttu-id="d5189-432">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="d5189-432">1.2.3.4\*</span></span>
  - <span data-ttu-id="d5189-433">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="d5189-433">contoso.com/a\*</span></span>
  - <span data-ttu-id="d5189-434">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="d5189-434">contoso.com/ab\*</span></span>

- <span data-ttu-id="d5189-435">**ポートを含む IP アドレス**:</span><span class="sxs-lookup"><span data-stu-id="d5189-435">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="d5189-436">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="d5189-436">contoso.com:443</span></span>
  - <span data-ttu-id="d5189-437">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="d5189-437">abc.contoso.com:25</span></span>

- <span data-ttu-id="d5189-438">**説明的でないワイルドカード**:</span><span class="sxs-lookup"><span data-stu-id="d5189-438">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="d5189-439">\*.\*</span><span class="sxs-lookup"><span data-stu-id="d5189-439">\*.\*</span></span>

- <span data-ttu-id="d5189-440">**中央のワイルドカード**:</span><span class="sxs-lookup"><span data-stu-id="d5189-440">**Middle wildcards**:</span></span>

  - <span data-ttu-id="d5189-441">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="d5189-441">conto\*so.com</span></span>
  - <span data-ttu-id="d5189-442">conto~so.com</span><span class="sxs-lookup"><span data-stu-id="d5189-442">conto~so.com</span></span>

- <span data-ttu-id="d5189-443">**2 つのワイルドカード**</span><span class="sxs-lookup"><span data-stu-id="d5189-443">**Double wildcards**</span></span>

  - <span data-ttu-id="d5189-444">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="d5189-444">contoso.com/\*\*</span></span>
  - <span data-ttu-id="d5189-445">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="d5189-445">contoso.com/\*/\*</span></span>

## <a name="domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="d5189-446">テナント許可/ブロック一覧のスプーフィングされた送信者エントリのドメインペア構文</span><span class="sxs-lookup"><span data-stu-id="d5189-446">Domain pair syntax for spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="d5189-447">テナント許可/ブロック一覧のスプーフィング送信者のドメイン ペアは、次の構文を使用します `<Spoofed user>, <Sending infrastructure>` 。</span><span class="sxs-lookup"><span data-stu-id="d5189-447">A domain pair for a spoofed sender in the Tenant Allow/Block List uses the following syntax: `<Spoofed user>, <Sending infrastructure>`.</span></span>

- <span data-ttu-id="d5189-448">**スプーフィングされた** ユーザー: この値には、メール クライアントの [From] ボックスに表示されるスプーフィングされたユーザーの電子メール アドレスが含まれる。</span><span class="sxs-lookup"><span data-stu-id="d5189-448">**Spoofed user**: This value involves the email address of the spoofed user that's displayed in the **From** box in email clients.</span></span> <span data-ttu-id="d5189-449">このアドレスは、アドレスとも呼 `5322.From` ばれる。</span><span class="sxs-lookup"><span data-stu-id="d5189-449">This address is also known as the `5322.From` address.</span></span> <span data-ttu-id="d5189-450">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d5189-450">Valid values include:</span></span>
  - <span data-ttu-id="d5189-451">個々の電子メール アドレス (たとえば、chris@contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="d5189-451">An individual email address (for example, chris@contoso.com).</span></span>
  - <span data-ttu-id="d5189-452">電子メール ドメイン (たとえば、contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="d5189-452">An email domain (for example, contoso.com).</span></span>
  - <span data-ttu-id="d5189-453">ワイルドカード文字 (たとえば \* )。</span><span class="sxs-lookup"><span data-stu-id="d5189-453">The wildcard character (for example, \*).</span></span>

- <span data-ttu-id="d5189-454">**送信インフラストラクチャ**: この値は、スプーフィングされたユーザーからのメッセージのソースを示します。</span><span class="sxs-lookup"><span data-stu-id="d5189-454">**Sending infrastructure**: This value indicates the source of messages from the spoofed user.</span></span> <span data-ttu-id="d5189-455">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d5189-455">Valid values include:</span></span>
  - <span data-ttu-id="d5189-456">送信元電子メール サーバーの IP アドレスの逆引き DNS 参照 (PTR レコード) で見つかったドメイン (たとえば、fabrikam.com)。</span><span class="sxs-lookup"><span data-stu-id="d5189-456">The domain found in a reverse DNS lookup (PTR record) of the source email server's IP address (for example, fabrikam.com).</span></span>
  - <span data-ttu-id="d5189-457">送信元 IP アドレスに PTR レコードがない場合、送信インフラストラクチャは \<source IP\> /24 として識別されます (たとえば、192.168.100.100/24 など)。</span><span class="sxs-lookup"><span data-stu-id="d5189-457">If the source IP address has no PTR record, then the sending infrastructure is identified as \<source IP\>/24 (for example, 192.168.100.100/24).</span></span>

<span data-ttu-id="d5189-458">スプーフィングされた送信者を識別するための有効なドメイン ペアの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="d5189-458">Here are some examples of valid domain pairs to identify spoofed senders:</span></span>

- `contoso.com, 192.168.100.100/24`
- `chris@contoso.com, fabrikam.com`
- `*, contoso.net`

<span data-ttu-id="d5189-459">スプーフィングされた送信者エントリの最大数は 1000 です。</span><span class="sxs-lookup"><span data-stu-id="d5189-459">The maximum number of spoofed sender entries is 1000.</span></span>

<span data-ttu-id="d5189-460">ドメイン ペアを追加すると、スプーフィングされたユーザーと送信インフラストラクチャの組み合わせだけが許可またはブロックされます。</span><span class="sxs-lookup"><span data-stu-id="d5189-460">Adding a domain pair only allows or blocks the *combination* of the spoofed user *and* the sending infrastructure.</span></span> <span data-ttu-id="d5189-461">スプーフィングされたユーザーからのメールを任意のソースから許可したり、スプーフィングされたユーザーに対して送信インフラストラクチャ ソースからのメールを許可したりはしない。</span><span class="sxs-lookup"><span data-stu-id="d5189-461">It does not allow email from the spoofed user from any source, nor does it allow email from the sending infrastructure source for any spoofed user.</span></span> 

<span data-ttu-id="d5189-462">たとえば、次のドメインペアの許可エントリを追加します。</span><span class="sxs-lookup"><span data-stu-id="d5189-462">For example, you add an allow entry for the following domain pair:</span></span>

- <span data-ttu-id="d5189-463">**ドメイン**: gmail.com</span><span class="sxs-lookup"><span data-stu-id="d5189-463">**Domain**: gmail.com</span></span>
- <span data-ttu-id="d5189-464">**インフラストラクチャ**: tms.mx.com</span><span class="sxs-lookup"><span data-stu-id="d5189-464">**Infrastructure**: tms.mx.com</span></span>

<span data-ttu-id="d5189-465">スプーフィングを許可できるのは、そのドメインと送信インフラストラクチャ のペアからのメッセージのみです。</span><span class="sxs-lookup"><span data-stu-id="d5189-465">Only messages from that domain *and* sending infrastructure pair are allowed to spoof.</span></span> <span data-ttu-id="d5189-466">スプーフィングを試みる gmail.com 送信者は許可されません。</span><span class="sxs-lookup"><span data-stu-id="d5189-466">Other senders attempting to spoof gmail.com aren't allowed.</span></span> <span data-ttu-id="d5189-467">ユーザーから発信される他のドメインの送信者からの tms.mx.com スプーフィング インテリジェンスによってチェックされます。</span><span class="sxs-lookup"><span data-stu-id="d5189-467">Messages from senders in other domains originating from tms.mx.com are checked by spoof intelligence.</span></span>
