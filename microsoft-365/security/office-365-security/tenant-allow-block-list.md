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
ms.openlocfilehash: 270e38d65857de2f4d06460fb3bb77f72a165ecf
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538965"
---
# <a name="manage-the-tenant-allowblock-list"></a><span data-ttu-id="61b33-103">テナントの許可/禁止リストの URL を管理する</span><span class="sxs-lookup"><span data-stu-id="61b33-103">Manage the Tenant Allow/Block List</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="61b33-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="61b33-104">**Applies to**</span></span>
- [<span data-ttu-id="61b33-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="61b33-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="61b33-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="61b33-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="61b33-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="61b33-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
>
> <span data-ttu-id="61b33-108">この記事で説明する機能はプレビューで、変更される可能性があります。一部の組織では利用できません。</span><span class="sxs-lookup"><span data-stu-id="61b33-108">The features described in this article are in Preview, are subject to change, and are not available in all organizations.</span></span>  <span data-ttu-id="61b33-109">この記事で説明するスプーフィング機能が組織に存在しない場合は [、「EOP](walkthrough-spoof-intelligence-insight.md)のスプーフィング インテリジェンス ポリシーとスプーフィング インテリジェンスインサイトを使用してスプーフィング送信者を管理する」で、以前のスプーフィング管理エクスペリエンスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="61b33-109">If your organization does not have the spoof features as described in this article, see the older spoof management experience at [Manage spoofed senders using the spoof intelligence policy and spoof intelligence insight in EOP](walkthrough-spoof-intelligence-insight.md).</span></span>
>
> <span data-ttu-id="61b33-110">現時点 **では、テナント** 許可/ブロック一覧で許可された URL またはファイル アイテムを構成できません。</span><span class="sxs-lookup"><span data-stu-id="61b33-110">You can't **configure** allowed URL or file items in the Tenant Allow/Block List at this time.</span></span>

<span data-ttu-id="61b33-111">Microsoft 365 Exchange Online またはスタンドアロン Exchange Online Protection (EOP) 組織に Exchange Online メールボックスがない組織では、EOP フィルターの評決に同意しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="61b33-111">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="61b33-112">たとえば、メッセージが正しい (誤検知) とマークされている場合や、悪いメッセージが許可される場合があります (偽陰性)。</span><span class="sxs-lookup"><span data-stu-id="61b33-112">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="61b33-113">セキュリティ コンプライアンス センターのテナント許可/ブロック一覧&を使用すると、フィルター処理のMicrosoft 365を手動で上書きできます。</span><span class="sxs-lookup"><span data-stu-id="61b33-113">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="61b33-114">テナント許可/ブロック一覧は、メール フロー中およびユーザークリック時に使用されます。</span><span class="sxs-lookup"><span data-stu-id="61b33-114">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="61b33-115">次の種類のオーバーライドを指定できます。</span><span class="sxs-lookup"><span data-stu-id="61b33-115">You can specify the following types of overrides:</span></span>

- <span data-ttu-id="61b33-116">ブロックする URL。</span><span class="sxs-lookup"><span data-stu-id="61b33-116">URLs to block.</span></span>
- <span data-ttu-id="61b33-117">ブロックするファイル。</span><span class="sxs-lookup"><span data-stu-id="61b33-117">Files to block.</span></span>
- <span data-ttu-id="61b33-118">許可するメール送信者ドメインを一括送信します。</span><span class="sxs-lookup"><span data-stu-id="61b33-118">Bulk mail sender domains to allow.</span></span> <span data-ttu-id="61b33-119">バルク メール、バルク信頼レベル (BCL)、スパム対策ポリシーによるバルク メール フィルターの詳細については、「EOP のバルク 苦情レベル [(BCL)」を参照してください](bulk-complaint-level-values.md)。</span><span class="sxs-lookup"><span data-stu-id="61b33-119">For more information about bulk mail, the bulk confidence level (BCL), and bulk mail filtering by anti-spam policies, see [Bulk complaint level (BCL) in EOP](bulk-complaint-level-values.md).</span></span>
- <span data-ttu-id="61b33-120">許可またはブロックするスプーフィングされた送信者。</span><span class="sxs-lookup"><span data-stu-id="61b33-120">Spoofed senders to allow or block.</span></span> <span data-ttu-id="61b33-121">スプーフィング インテリジェンスインサイトで許可またはブロックの[](learn-about-spoof-intelligence.md)評決を上書きすると、スプーフィングされた送信者は、テナント許可/ブロック一覧の [スプーフィング] タブにのみ表示される手動の許可またはブロックエントリになります。</span><span class="sxs-lookup"><span data-stu-id="61b33-121">If you override the allow or block verdict in the [spoof intelligence insight](learn-about-spoof-intelligence.md), the spoofed sender becomes a manual allow or block entry that only appears on the **Spoof** tab in the Tenant Allow/Block List.</span></span> <span data-ttu-id="61b33-122">スプーフィング インテリジェンスによって検出される前に、スプーフィングされた送信者のエントリを手動で作成またはブロックすることもできます。</span><span class="sxs-lookup"><span data-stu-id="61b33-122">You can also manually create allow or block entries for spoofed senders here before they're detected by spoof intelligence.</span></span>

<span data-ttu-id="61b33-123">この記事では、セキュリティ & コンプライアンス センターまたは PowerShell (Exchange Online のメールボックスを持つ Microsoft 365 組織の Exchange Online PowerShell、Exchange Online メールボックスのない組織のスタンドアロン EOP PowerShell) のテナント許可/ブロック一覧のエントリを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="61b33-123">This article describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="61b33-124">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="61b33-124">What do you need to know before you begin?</span></span>

- <span data-ttu-id="61b33-125"><https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="61b33-125">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="61b33-126">[テナントの許可/ブロック **リスト] ページに直接移動するには** 、 を使用します <https://protection.office.com/tenantAllowBlockList> 。</span><span class="sxs-lookup"><span data-stu-id="61b33-126">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="61b33-127">ファイルを指定するには、ファイルの SHA256 ハッシュ値を使用します。</span><span class="sxs-lookup"><span data-stu-id="61b33-127">You specify files by using the SHA256 hash value of the file.</span></span> <span data-ttu-id="61b33-128">ファイルの SHA256 ハッシュ値をWindowsコマンド プロンプトで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="61b33-128">To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt:</span></span>

  ```console
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  <span data-ttu-id="61b33-129">値の例は、 です `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` 。</span><span class="sxs-lookup"><span data-stu-id="61b33-129">An example value is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`.</span></span> <span data-ttu-id="61b33-130">知覚ハッシュ (pHash) の値はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="61b33-130">Perceptual hash (pHash) values are not supported.</span></span>

- <span data-ttu-id="61b33-131">使用可能な URL 値については、この記事の後半の「 [テナント許可/](#url-syntax-for-the-tenant-allowblock-list) ブロック一覧」セクションの URL 構文で説明します。</span><span class="sxs-lookup"><span data-stu-id="61b33-131">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

- <span data-ttu-id="61b33-132">テナント許可/ブロック一覧では、URL に対して最大 500 エントリ、ファイル ハッシュのエントリを 500 エントリまで使用できます。</span><span class="sxs-lookup"><span data-stu-id="61b33-132">The Tenant Allow/Block List allows a maximum of 500 entries for URLs, and 500 entries for file hashes.</span></span>

- <span data-ttu-id="61b33-133">各エントリの最大文字数は次の値です。</span><span class="sxs-lookup"><span data-stu-id="61b33-133">The maximum number of characters for each entry is:</span></span>
  - <span data-ttu-id="61b33-134">ファイル ハッシュ = 64</span><span class="sxs-lookup"><span data-stu-id="61b33-134">File hashes = 64</span></span>
  - <span data-ttu-id="61b33-135">URL = 250</span><span class="sxs-lookup"><span data-stu-id="61b33-135">URL = 250</span></span>

- <span data-ttu-id="61b33-136">エントリは 30 分以内にアクティブである必要があります。</span><span class="sxs-lookup"><span data-stu-id="61b33-136">An entry should be active within 30 minutes.</span></span>

- <span data-ttu-id="61b33-137">既定では、テナント許可/ブロック一覧のエントリは 30 日後に期限切れになります。</span><span class="sxs-lookup"><span data-stu-id="61b33-137">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="61b33-138">日付を指定するか、有効期限が切れることはありません。</span><span class="sxs-lookup"><span data-stu-id="61b33-138">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="61b33-139">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="61b33-139">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="61b33-140">スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="61b33-140">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="61b33-141">この記事の手順を実行する際には、あらかじめExchange Online でアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="61b33-141">You need to be assigned permissions in Exchange Online before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="61b33-142">**URL、ファイル、および一括送信者の許可**:</span><span class="sxs-lookup"><span data-stu-id="61b33-142">**URLs, files, and allow bulk senders**:</span></span>
    - <span data-ttu-id="61b33-143">テナント許可/ブロック一覧の値を追加および削除するには、組織の管理またはセキュリティ管理者の役割グループのメンバー **である** 必要があります。</span><span class="sxs-lookup"><span data-stu-id="61b33-143">To add and remove values from the Tenant Allow/Block List, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
    - <span data-ttu-id="61b33-144">テナント許可/ブロック一覧への読み取り専用アクセスでは、グローバル リーダーまたはセキュリティリーダーの役割グループの **メンバーである** 必要があります。</span><span class="sxs-lookup"><span data-stu-id="61b33-144">For read-only access to the Tenant Allow/Block List, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>
  - <span data-ttu-id="61b33-145">**スプーフィン** グ: 次のいずれかの組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="61b33-145">**Spoofing**: One of the following combinations:</span></span>
    - <span data-ttu-id="61b33-146">**組織の管理**</span><span class="sxs-lookup"><span data-stu-id="61b33-146">**Organization Management**</span></span>
    - <span data-ttu-id="61b33-147">**セキュリティ管理者**<u>と</u>**表示のみ構成または\*\*\*\*表示のみ可能な組織の管理**。</span><span class="sxs-lookup"><span data-stu-id="61b33-147">**Security Administrator** <u>and</u> **View-Only Configuration** or **View-Only Organization Management**.</span></span>

  <span data-ttu-id="61b33-148">詳細については、「[Exchange Online のアクセス許可](/exchange/permissions-exo/permissions-exo)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="61b33-148">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  >
  > - <span data-ttu-id="61b33-149">Microsoft 365 管理センターで、対応する Azure Active Directory の役割にユーザーを追加すると、ユーザーには、必要なアクセス許可 _および_ Microsoft 365 のその他の機能に必要なアクセス許可が付与されます。</span><span class="sxs-lookup"><span data-stu-id="61b33-149">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="61b33-150">詳細については、「[管理者の役割について](../../admin/add-users/about-admin-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="61b33-150">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  >
  > - <span data-ttu-id="61b33-151">[Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) の **閲覧専用の組織管理** の役割グループが この機能への読み取り専用アクセス権も付与します。</span><span class="sxs-lookup"><span data-stu-id="61b33-151">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-security--compliance-center-to-create-block-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="61b33-152">テナント許可/&リストにブロック URL エントリを作成するには、セキュリティ コンプライアンス センターを使用します。</span><span class="sxs-lookup"><span data-stu-id="61b33-152">Use the Security & Compliance Center to create block URL entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="61b33-153">セキュリティ 管理コンプライアンス センター&、[**脅威管理ポリシー** ] [テナントの許可 \>  \> **/ブロックリスト] に移動します**。</span><span class="sxs-lookup"><span data-stu-id="61b33-153">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="61b33-154">[テナントの **許可/ブロック一覧** ] ページで **、[URL]** タブが選択されているのを確認し、[ブロック] を **クリックします。**</span><span class="sxs-lookup"><span data-stu-id="61b33-154">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Block**</span></span>

3. <span data-ttu-id="61b33-155">表示される **[URL のブロック]** フライアウトで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="61b33-155">In the **Block URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="61b33-156">**ブロックする URL を追加する**: 1 行に 1 つの URL を入力し、最大 20 を入力します。</span><span class="sxs-lookup"><span data-stu-id="61b33-156">**Add URLs to block**: Enter one URL per line, up to a maximum of 20.</span></span> <span data-ttu-id="61b33-157">URL エントリの構文の詳細については、この記事の後半の「テナント許可/ブロック一覧」セクションの [URL](#url-syntax-for-the-tenant-allowblock-list) 構文を参照してください。</span><span class="sxs-lookup"><span data-stu-id="61b33-157">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

   - <span data-ttu-id="61b33-158">**有効期限が切れる** ことはありません: 次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="61b33-158">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="61b33-159">設定がオフ (トグルオフ) になっていることを確認し、[有効期限] ボックスを使用してエントリの有効期限 ![ ](../../media/scc-toggle-off.png) を指定します。 </span><span class="sxs-lookup"><span data-stu-id="61b33-159">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

       <span data-ttu-id="61b33-160">または</span><span class="sxs-lookup"><span data-stu-id="61b33-160">or</span></span>

     - <span data-ttu-id="61b33-161">切り替えボタンを右に移動して、有効期限が切れなきエントリを構成します。</span><span class="sxs-lookup"><span data-stu-id="61b33-161">Move the toggle to the right to configure the entries to never expire:</span></span> ![オンに切り替え](../../media/scc-toggle-on.png)<span data-ttu-id="61b33-163">.</span><span class="sxs-lookup"><span data-stu-id="61b33-163">.</span></span>

   - <span data-ttu-id="61b33-164">**省略可能な** メモ: エントリの説明テキストを入力します。</span><span class="sxs-lookup"><span data-stu-id="61b33-164">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="61b33-165">完了したら、**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="61b33-165">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-block-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="61b33-166">コンプライアンス センターのセキュリティ &使用して、テナント許可/ブロック一覧にブロック ファイル エントリを作成する</span><span class="sxs-lookup"><span data-stu-id="61b33-166">Use the Security & Compliance Center to create block file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="61b33-167">セキュリティ 管理コンプライアンス センター&、[**脅威管理ポリシー** ] [テナントの許可 \>  \> **/ブロックリスト] に移動します**。</span><span class="sxs-lookup"><span data-stu-id="61b33-167">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="61b33-168">[テナントの **許可/ブロック一覧] ページで**、[ファイル] タブを選択し、[ブロック] を **クリックします**。 </span><span class="sxs-lookup"><span data-stu-id="61b33-168">On the **Tenant Allow/Block List** page, select the **Files** tab, and then click **Block**.</span></span>

3. <span data-ttu-id="61b33-169">表示される **[ファイルを追加してブロック** する] フライアウトで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="61b33-169">In the **Add files to block** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="61b33-170">**ファイル ハッシュの追加**: 1 行に 1 つの SHA256 ハッシュ値を入力し、最大 20 を入力します。</span><span class="sxs-lookup"><span data-stu-id="61b33-170">**Add file hashes**: Enter one SHA256 hash value per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="61b33-171">**有効期限が切れる** ことはありません: 次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="61b33-171">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="61b33-172">設定がオフ (トグルオフ) になっていることを確認し、[有効期限] ボックスを使用してエントリの有効期限 ![ ](../../media/scc-toggle-off.png) を指定します。 </span><span class="sxs-lookup"><span data-stu-id="61b33-172">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="61b33-173">または</span><span class="sxs-lookup"><span data-stu-id="61b33-173">or</span></span>

     - <span data-ttu-id="61b33-174">切り替えボタンを右に移動して、有効期限が切れなきエントリを構成します。</span><span class="sxs-lookup"><span data-stu-id="61b33-174">Move the toggle to the right to configure the entries to never expire:</span></span> ![オンに切り替え](../../media/scc-toggle-on.png)<span data-ttu-id="61b33-176">.</span><span class="sxs-lookup"><span data-stu-id="61b33-176">.</span></span>

   - <span data-ttu-id="61b33-177">**省略可能な** メモ: エントリの説明テキストを入力します。</span><span class="sxs-lookup"><span data-stu-id="61b33-177">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="61b33-178">完了したら、**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="61b33-178">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-allow-bulk-mail-sender-domain-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="61b33-179">コンプライアンス センターのセキュリティ &を使用して、テナントの許可/ブロック一覧にバルク メール送信者ドメイン エントリを作成する</span><span class="sxs-lookup"><span data-stu-id="61b33-179">Use the Security & Compliance Center to create allow bulk mail sender domain entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="61b33-180">セキュリティ 管理コンプライアンス センター&、[**脅威管理ポリシー** ] [テナントの許可 \>  \> **/ブロックリスト] に移動します**。</span><span class="sxs-lookup"><span data-stu-id="61b33-180">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="61b33-181">[テナントの **許可/ブロック一覧** ] ページで **、[BCL** バイパスの送信者ドメイン] タブを選択し、[追加] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="61b33-181">On the **Tenant Allow/Block List** page, select the **Sender domains for BCL bypass** tab, and then click **Add**.</span></span>

3. <span data-ttu-id="61b33-182">表示される **BCL バイパス フライアウトの送信者** ドメインの追加で、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="61b33-182">In the **Add sender domain for BCL bypass** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="61b33-183">**BCL バイパスの送信者ドメインを** 追加する: 1 行に 1 つの適切なバルク メールのソース ドメインを 1 つ入力し、最大 20 まで入力します。</span><span class="sxs-lookup"><span data-stu-id="61b33-183">**Add sender domains for BCL bypass**: Enter one source domain of good bulk mail per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="61b33-184">**有効期限が切れる** ことはありません: 次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="61b33-184">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="61b33-185">設定がオフ (トグルオフ) になっていることを確認し、[有効期限] ボックスを使用してエントリの有効期限 ![ ](../../media/scc-toggle-off.png) を指定します。 </span><span class="sxs-lookup"><span data-stu-id="61b33-185">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="61b33-186">または</span><span class="sxs-lookup"><span data-stu-id="61b33-186">or</span></span>

     - <span data-ttu-id="61b33-187">切り替えボタンを右に移動して、有効期限が切れなきエントリを構成します。</span><span class="sxs-lookup"><span data-stu-id="61b33-187">Move the toggle to the right to configure the entries to never expire:</span></span> ![オンに切り替え](../../media/scc-toggle-on.png)<span data-ttu-id="61b33-189">.</span><span class="sxs-lookup"><span data-stu-id="61b33-189">.</span></span>

4. <span data-ttu-id="61b33-190">完了したら、**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="61b33-190">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="61b33-191">セキュリティ コンプライアンス センター&使用して、テナント許可/ブロック一覧でスプーフィングされた送信者エントリを作成またはブロックする</span><span class="sxs-lookup"><span data-stu-id="61b33-191">Use the Security & Compliance Center to create allow or block spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="61b33-192">**注**:</span><span class="sxs-lookup"><span data-stu-id="61b33-192">**Notes**:</span></span>

- <span data-ttu-id="61b33-193">スプー _フィング_ されたユーザーと、ドメイン ペアで定義されている送信インフラストラクチャの組み合わせだけが、スプーフィングを許可またはブロックされます。</span><span class="sxs-lookup"><span data-stu-id="61b33-193">Only the _combination_ of the spoofed user _and_ the sending infrastructure as defined in the domain pair is specifically allowed or blocked from spoofing.</span></span>
- <span data-ttu-id="61b33-194">ドメイン ペアの許可エントリまたはブロック エントリを構成すると、そのドメイン ペアからのメッセージはスプーフィング インテリジェンスインサイトに表示されなくなりました。</span><span class="sxs-lookup"><span data-stu-id="61b33-194">When you configure an allow or block entry for a domain pair, messages from that domain pair no longer appear in the spoof intelligence insight.</span></span>
- <span data-ttu-id="61b33-195">スプーフィングされた送信者のエントリは有効期限が切れることはありません。</span><span class="sxs-lookup"><span data-stu-id="61b33-195">Entries for spoofed senders never expire.</span></span>

1. <span data-ttu-id="61b33-196">セキュリティ 管理コンプライアンス センター&、[**脅威管理ポリシー** ] [テナントの許可 \>  \> **/ブロックリスト] に移動します**。</span><span class="sxs-lookup"><span data-stu-id="61b33-196">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="61b33-197">[テナントの **許可/ブロックリスト] ページで** 、[スプーフィング] タブ **を選択** し、[追加] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="61b33-197">On the **Tenant Allow/Block List** page, select the **Spoofing** tab, and then click **Add**.</span></span>

3. <span data-ttu-id="61b33-198">表示される **[新しいドメイン ペアの追加** ] フライアウトで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="61b33-198">In the **Add new domain pairs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="61b33-199">**ワイルドカードを使用して新しいドメイン ペア** を追加する: 1 行に 1 つのドメイン ペアを入力し、最大 20 まで入力します。</span><span class="sxs-lookup"><span data-stu-id="61b33-199">**Add new domain pairs with wildcards**: Enter one domain pair per line, up to a maximum of 20.</span></span> <span data-ttu-id="61b33-200">スプーフィングされた送信者エントリの構文の詳細については、この記事の後半の「テナント許可 [/](#domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list) ブロックリスト」セクションの「スプーフィングされた送信者エントリのドメインペア構文」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="61b33-200">For details about the syntax for spoofed sender entries, see the [Domain pair syntax for spoofed sender entries in the Tenant Allow/Block List](#domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list) section later in this article.</span></span>

   - <span data-ttu-id="61b33-201">**スプーフィング** の種類: 次のいずれかの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="61b33-201">**Spoof type**: Select one of the following values:</span></span>
     - <span data-ttu-id="61b33-202">**内部**: スプーフィングされた送信者は、組織 (受け入れドメイン) に属する [ドメイン内にいます](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)。</span><span class="sxs-lookup"><span data-stu-id="61b33-202">**Internal**: The spoofed sender is in a domain that belongs to your organization (an [accepted domain](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)).</span></span>
     - <span data-ttu-id="61b33-203">**外部**: スプーフィングされた送信者が外部ドメイン内にある。</span><span class="sxs-lookup"><span data-stu-id="61b33-203">**External**: The spoofed sender is in an external domain.</span></span>

   - <span data-ttu-id="61b33-204">**アクション**: [許可] **または [ブロック]** **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="61b33-204">**Action**: Select **Allow** or **Block**.</span></span>

4. <span data-ttu-id="61b33-205">完了したら、**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="61b33-205">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="61b33-206">テナント許可/&リストのエントリを表示するには、セキュリティ コンプライアンス センターを使用します。</span><span class="sxs-lookup"><span data-stu-id="61b33-206">Use the Security & Compliance Center to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="61b33-207">セキュリティ 管理コンプライアンス センター&、[**脅威管理ポリシー** ] [テナントの許可 \>  \> **/ブロックリスト] に移動します**。</span><span class="sxs-lookup"><span data-stu-id="61b33-207">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="61b33-208">必要なタブを選択します。</span><span class="sxs-lookup"><span data-stu-id="61b33-208">Select the tab you want.</span></span> <span data-ttu-id="61b33-209">使用可能な列は、選択したタブによって異なる。</span><span class="sxs-lookup"><span data-stu-id="61b33-209">The columns that are available depend on the tab you selected:</span></span>

   - <span data-ttu-id="61b33-210">**URL**:</span><span class="sxs-lookup"><span data-stu-id="61b33-210">**URLs**:</span></span>
     - <span data-ttu-id="61b33-211">**値**: URL。</span><span class="sxs-lookup"><span data-stu-id="61b33-211">**Value**: The URL.</span></span>
     - <span data-ttu-id="61b33-212">**Action**: 値 **Block**.</span><span class="sxs-lookup"><span data-stu-id="61b33-212">**Action**: The value **Block**.</span></span>
     - <span data-ttu-id="61b33-213">**最終更新日**</span><span class="sxs-lookup"><span data-stu-id="61b33-213">**Last updated date**</span></span>
     - <span data-ttu-id="61b33-214">**有効期限**</span><span class="sxs-lookup"><span data-stu-id="61b33-214">**Expiration date**</span></span>
     - <span data-ttu-id="61b33-215">**注**</span><span class="sxs-lookup"><span data-stu-id="61b33-215">**Note**</span></span>

   - <span data-ttu-id="61b33-216">**Files**</span><span class="sxs-lookup"><span data-stu-id="61b33-216">**Files**</span></span>
     - <span data-ttu-id="61b33-217">**値**: ファイル ハッシュ。</span><span class="sxs-lookup"><span data-stu-id="61b33-217">**Value**: The file hash.</span></span>
     - <span data-ttu-id="61b33-218">**Action**: 値 **Block**.</span><span class="sxs-lookup"><span data-stu-id="61b33-218">**Action**: The value **Block**.</span></span>
     - <span data-ttu-id="61b33-219">**最終更新日**</span><span class="sxs-lookup"><span data-stu-id="61b33-219">**Last updated date**</span></span>
     - <span data-ttu-id="61b33-220">**有効期限**</span><span class="sxs-lookup"><span data-stu-id="61b33-220">**Expiration date**</span></span>
     - <span data-ttu-id="61b33-221">**注**</span><span class="sxs-lookup"><span data-stu-id="61b33-221">**Note**</span></span>

   - <span data-ttu-id="61b33-222">**BCL バイパスの送信者ドメイン**</span><span class="sxs-lookup"><span data-stu-id="61b33-222">**Sender domains for BCL bypass**</span></span>
     - <span data-ttu-id="61b33-223">**値**: バルク メール送信者のドメイン。</span><span class="sxs-lookup"><span data-stu-id="61b33-223">**Value**: The bulk mail sender's domain.</span></span>
     - <span data-ttu-id="61b33-224">**最終更新日**</span><span class="sxs-lookup"><span data-stu-id="61b33-224">**Last updated date**</span></span>
     - <span data-ttu-id="61b33-225">**有効期限**</span><span class="sxs-lookup"><span data-stu-id="61b33-225">**Expiration date**</span></span>

   - <span data-ttu-id="61b33-226">「**スプーフィング**」</span><span class="sxs-lookup"><span data-stu-id="61b33-226">**Spoofing**</span></span>
     - <span data-ttu-id="61b33-227">**スプーフィングされたユーザー**</span><span class="sxs-lookup"><span data-stu-id="61b33-227">**Spoofed user**</span></span>
     - <span data-ttu-id="61b33-228">**インフラストラクチャの送信**</span><span class="sxs-lookup"><span data-stu-id="61b33-228">**Sending infrastructure**</span></span>
     - <span data-ttu-id="61b33-229">**スプーフィングの** 種類 : **値 Internal または** **External** です。</span><span class="sxs-lookup"><span data-stu-id="61b33-229">**Spoof type**: The value **Internal** or **External**.</span></span>
     - <span data-ttu-id="61b33-230">**Action**: 値 Block **or** **Allow**.</span><span class="sxs-lookup"><span data-stu-id="61b33-230">**Action**: The value **Block** or **Allow**.</span></span>

   <span data-ttu-id="61b33-231">列見出しをクリックすると、昇順または降順で並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="61b33-231">You can click on a column heading to sort in ascending or descending order.</span></span>

   <span data-ttu-id="61b33-232">[グループ化] **をクリック** すると、結果をグループ化できます。</span><span class="sxs-lookup"><span data-stu-id="61b33-232">You can click **Group** to group the results.</span></span> <span data-ttu-id="61b33-233">使用可能な値は、選択したタブによって異なる。</span><span class="sxs-lookup"><span data-stu-id="61b33-233">The values that are available depend on the tab you selected:</span></span>

   - <span data-ttu-id="61b33-234">**URL :** アクションで結果をグループ化 **できます**。</span><span class="sxs-lookup"><span data-stu-id="61b33-234">**URLs**: You can group the results by **Action**.</span></span>
   - <span data-ttu-id="61b33-235">**ファイル**: アクションで結果をグループ **化できます**。</span><span class="sxs-lookup"><span data-stu-id="61b33-235">**Files**: You can group the results by **Action**.</span></span>
   - <span data-ttu-id="61b33-236">**BCL バイパスの送信者ドメイン**: **グループ** は、このタブでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="61b33-236">**Sender domains for BCL bypass**: **Group** is not available on this tab.</span></span>
   - <span data-ttu-id="61b33-237">**スプーフィン** グ : アクションまたはスプーフィングの種類 **で結果** を **グループ化できます**。</span><span class="sxs-lookup"><span data-stu-id="61b33-237">**Spoofing**: You can group the results by **Action** or **Spoof type**.</span></span>

   <span data-ttu-id="61b33-238">[ **検索]** をクリックし、値のすべてまたは一部を入力し、Enter キーを押して特定の値を検索します。</span><span class="sxs-lookup"><span data-stu-id="61b33-238">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="61b33-239">完了したら、[検索のクリア] **アイコン** ![ をクリックします ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) 。</span><span class="sxs-lookup"><span data-stu-id="61b33-239">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

   <span data-ttu-id="61b33-240">[フィルター **] をクリック** して結果をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="61b33-240">Click **Filter** to filter the results.</span></span> <span data-ttu-id="61b33-241">表示されるフィルター フライアウト **で** 使用できる値は、選択したタブによって異なる。</span><span class="sxs-lookup"><span data-stu-id="61b33-241">The values that are available in **Filter** flyout that appears depend on the tab you selected:</span></span>

   - <span data-ttu-id="61b33-242">**URL**</span><span class="sxs-lookup"><span data-stu-id="61b33-242">**URLs**</span></span>
     - <span data-ttu-id="61b33-243">**Action**</span><span class="sxs-lookup"><span data-stu-id="61b33-243">**Action**</span></span>
     - <span data-ttu-id="61b33-244">**有効期限が切れることはありません**</span><span class="sxs-lookup"><span data-stu-id="61b33-244">**Never expire**</span></span>
     - <span data-ttu-id="61b33-245">**最終更新日**</span><span class="sxs-lookup"><span data-stu-id="61b33-245">**Last updated date**</span></span>
     - <span data-ttu-id="61b33-246">**有効期限**</span><span class="sxs-lookup"><span data-stu-id="61b33-246">**Expiration date**</span></span>

   - <span data-ttu-id="61b33-247">**Files**</span><span class="sxs-lookup"><span data-stu-id="61b33-247">**Files**</span></span>
     - <span data-ttu-id="61b33-248">**Action**</span><span class="sxs-lookup"><span data-stu-id="61b33-248">**Action**</span></span>
     - <span data-ttu-id="61b33-249">**有効期限が切れることはありません**</span><span class="sxs-lookup"><span data-stu-id="61b33-249">**Never expire**</span></span>
     - <span data-ttu-id="61b33-250">**最終更新日**</span><span class="sxs-lookup"><span data-stu-id="61b33-250">**Last updated date**</span></span>
     - <span data-ttu-id="61b33-251">**有効期限**</span><span class="sxs-lookup"><span data-stu-id="61b33-251">**Expiration date**</span></span>

   - <span data-ttu-id="61b33-252">**BCL バイパスの送信者ドメイン**</span><span class="sxs-lookup"><span data-stu-id="61b33-252">**Sender domains for BCL bypass**</span></span>
     - <span data-ttu-id="61b33-253">**有効期限が切れることはありません**</span><span class="sxs-lookup"><span data-stu-id="61b33-253">**Never expire**</span></span>
     - <span data-ttu-id="61b33-254">**最終更新日**</span><span class="sxs-lookup"><span data-stu-id="61b33-254">**Last updated date**</span></span>
     - <span data-ttu-id="61b33-255">**有効期限**</span><span class="sxs-lookup"><span data-stu-id="61b33-255">**Expiration date**</span></span>

   - <span data-ttu-id="61b33-256">「**スプーフィング**」</span><span class="sxs-lookup"><span data-stu-id="61b33-256">**Spoofing**</span></span>
     - <span data-ttu-id="61b33-257">**Action**</span><span class="sxs-lookup"><span data-stu-id="61b33-257">**Action**</span></span>
     - <span data-ttu-id="61b33-258">**スプーフィングの種類**</span><span class="sxs-lookup"><span data-stu-id="61b33-258">**Spoof type**</span></span>

   <span data-ttu-id="61b33-259">完了したら、[適用] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="61b33-259">When you're finished, click **Apply**.</span></span> <span data-ttu-id="61b33-260">既存のフィルターをクリアするには、[**フィルター**] をクリックし、表示される [フィルター] フライアウトで 、[フィルターのクリア]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="61b33-260">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="61b33-261">テナント許可/&リストのエントリを変更するには、セキュリティ コンプライアンス センターを使用します。</span><span class="sxs-lookup"><span data-stu-id="61b33-261">Use the Security & Compliance Center to modify entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="61b33-262">セキュリティ 管理コンプライアンス センター&、[**脅威管理ポリシー** ] [テナントの許可 \>  \> **/ブロックリスト] に移動します**。</span><span class="sxs-lookup"><span data-stu-id="61b33-262">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="61b33-263">変更するエントリの種類を含むタブを選択します。</span><span class="sxs-lookup"><span data-stu-id="61b33-263">Select the tab that contains the type of entry that you want to modify:</span></span>
   - <span data-ttu-id="61b33-264">**URL**</span><span class="sxs-lookup"><span data-stu-id="61b33-264">**URLs**</span></span>
   - <span data-ttu-id="61b33-265">**Files**</span><span class="sxs-lookup"><span data-stu-id="61b33-265">**Files**</span></span>
   - <span data-ttu-id="61b33-266">**BCL バイパスの送信者ドメイン**</span><span class="sxs-lookup"><span data-stu-id="61b33-266">**Sender domains for BCL bypass**</span></span>
   - <span data-ttu-id="61b33-267">「**スプーフィング**」</span><span class="sxs-lookup"><span data-stu-id="61b33-267">**Spoofing**</span></span>

3. <span data-ttu-id="61b33-268">変更するエントリを選択し、[編集] アイコン **を** ![ クリックします ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) 。</span><span class="sxs-lookup"><span data-stu-id="61b33-268">Select the entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span> <span data-ttu-id="61b33-269">表示されるフライアウトで変更できる値は、前の手順で選択したタブによって異なっています。</span><span class="sxs-lookup"><span data-stu-id="61b33-269">The values that you are able to modify in the flyout that appears depend on the tab you selected in the previous step:</span></span>

   - <span data-ttu-id="61b33-270">**URL**</span><span class="sxs-lookup"><span data-stu-id="61b33-270">**URLs**</span></span>
     - <span data-ttu-id="61b33-271">**有効期限や有効期限** はありません。</span><span class="sxs-lookup"><span data-stu-id="61b33-271">**Never expire** and/or expiration date.</span></span>
     - <span data-ttu-id="61b33-272">**省略可能なメモ**</span><span class="sxs-lookup"><span data-stu-id="61b33-272">**Optional note**</span></span>

   - <span data-ttu-id="61b33-273">**Files**</span><span class="sxs-lookup"><span data-stu-id="61b33-273">**Files**</span></span>
     - <span data-ttu-id="61b33-274">**有効期限や有効期限** はありません。</span><span class="sxs-lookup"><span data-stu-id="61b33-274">**Never expire** and/or expiration date.</span></span>
     - <span data-ttu-id="61b33-275">**省略可能なメモ**</span><span class="sxs-lookup"><span data-stu-id="61b33-275">**Optional note**</span></span>

   - <span data-ttu-id="61b33-276">**BCL バイパスの送信者ドメイン**</span><span class="sxs-lookup"><span data-stu-id="61b33-276">**Sender domains for BCL bypass**</span></span>
     - <span data-ttu-id="61b33-277">**有効期限や有効期限** はありません。</span><span class="sxs-lookup"><span data-stu-id="61b33-277">**Never expire** and/or expiration date.</span></span>

   - <span data-ttu-id="61b33-278">「**スプーフィング**」</span><span class="sxs-lookup"><span data-stu-id="61b33-278">**Spoofing**</span></span>
     - <span data-ttu-id="61b33-279">**アクション**: 値を [許可] または [ブロック **] に\*\*\*\*変更できます**。</span><span class="sxs-lookup"><span data-stu-id="61b33-279">**Action**: You can change the value to **Allow** or **Block**.</span></span>

4. <span data-ttu-id="61b33-280">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="61b33-280">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="61b33-281">テナント許可/&リストからエントリを削除するには、セキュリティ コンプライアンス センターを使用します。</span><span class="sxs-lookup"><span data-stu-id="61b33-281">Use the Security & Compliance Center to remove entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="61b33-282">セキュリティ 管理コンプライアンス センター&、[**脅威管理ポリシー** ] [テナントの許可 \>  \> **/ブロックリスト] に移動します**。</span><span class="sxs-lookup"><span data-stu-id="61b33-282">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="61b33-283">削除するエントリの種類を含むタブを選択します。</span><span class="sxs-lookup"><span data-stu-id="61b33-283">Select the tab that contains the type of entry that you want to remove:</span></span>
   - <span data-ttu-id="61b33-284">**URL**</span><span class="sxs-lookup"><span data-stu-id="61b33-284">**URLs**</span></span>
   - <span data-ttu-id="61b33-285">**Files**</span><span class="sxs-lookup"><span data-stu-id="61b33-285">**Files**</span></span>
   - <span data-ttu-id="61b33-286">**BCL バイパスの送信者ドメイン**</span><span class="sxs-lookup"><span data-stu-id="61b33-286">**Sender domains for BCL bypass**</span></span>
   - <span data-ttu-id="61b33-287">「**スプーフィング**」</span><span class="sxs-lookup"><span data-stu-id="61b33-287">**Spoofing**</span></span>

3. <span data-ttu-id="61b33-288">削除するエントリを選択し、[削除] アイコン **を** ![ クリックします ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) 。</span><span class="sxs-lookup"><span data-stu-id="61b33-288">Select the entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="61b33-289">表示される警告ダイアログで、[削除] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="61b33-289">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="61b33-290">PowerShell Exchange Onlineスタンドアロン EOP PowerShell を使用してテナント許可/ブロック一覧を構成する</span><span class="sxs-lookup"><span data-stu-id="61b33-290">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-block-file-or-url-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="61b33-291">PowerShell を使用して、テナントの許可/ブロックリストにブロック ファイルまたは URL エントリを追加する</span><span class="sxs-lookup"><span data-stu-id="61b33-291">Use PowerShell to add block file or URL entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="61b33-292">テナント許可/ブロック一覧にブロック ファイルまたは URL エントリを追加するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="61b33-292">To add block file or URL entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType <FileHash | Url> -Block -Entries "Value1","Value2",..."ValueN" <-ExpirationDate Date | -NoExpiration> [-Notes <String>]
```

<span data-ttu-id="61b33-293">次の使用例は、有効期限が切れることはありません指定したファイルのブロック ファイル エントリを追加します。</span><span class="sxs-lookup"><span data-stu-id="61b33-293">This example adds a block file entry for the specified files that never expires.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

<span data-ttu-id="61b33-294">次の使用例は、contoso.com およびすべてのサブドメイン (contoso.com、www.contoso.com、および xyz.abc.contoso.com) のブロック URL エントリを追加します。</span><span class="sxs-lookup"><span data-stu-id="61b33-294">This example adds a block URL entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="61b33-295">ExpirationDate パラメーターまたは NoExpiration パラメーターを使用しないので、エントリは 30 日後に期限切れになります。</span><span class="sxs-lookup"><span data-stu-id="61b33-295">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItems -ListType Url -Block -Entries ~contoso.com
```

<span data-ttu-id="61b33-296">構文とパラメーターの詳細については [、「New-TenantAllowBlockListItems」を参照してください](/powershell/module/exchange/new-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="61b33-296">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-add-allow-bulk-mail-sender-domain-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="61b33-297">PowerShell を使用して、一括メール送信者ドメイン エントリをテナント許可/ブロックリストに追加する</span><span class="sxs-lookup"><span data-stu-id="61b33-297">Use PowerShell to add allow bulk mail sender domain entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="61b33-298">テナント許可/ブロック一覧にバルク メール送信者ドメイン エントリを追加するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="61b33-298">To add allow bulk mail sender domain entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType BulkSender -Block:$false -Entries "Value1","Value2",..."ValueN" <-ExpirationDate Date | -NoExpiration> [-Notes <String>]
```

<span data-ttu-id="61b33-299">次の使用例は、有効期限が切れることはありません、指定したドメインの許可された一括送信者エントリを追加します。</span><span class="sxs-lookup"><span data-stu-id="61b33-299">This example adds an allowed bulk sender entry for the specified domain that never expires.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType BulkSender -Block:$false -Entries contosodailydeals.com
New-TenantAllowBlockListItems -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

<span data-ttu-id="61b33-300">構文とパラメーターの詳細については [、「New-TenantAllowBlockListItems」を参照してください](/powershell/module/exchange/new-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="61b33-300">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-add-allow-or-block-spoofed-sender-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="61b33-301">PowerShell を使用して、スプーフィングされた送信者エントリをテナント許可/ブロックリストに追加またはブロックする</span><span class="sxs-lookup"><span data-stu-id="61b33-301">Use PowerShell to add allow or block spoofed sender entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="61b33-302">テナント許可/ブロック一覧にスプーフィングされた送信者エントリを追加するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="61b33-302">To add spoofed sender entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListSpoofItems -SpoofedUser <Domain | EmailAddress | *> -SendingInfrastructure <Domain | IPAddress/24> -SpoofType <External | Internal> -Action <Allow | Block>
```

<span data-ttu-id="61b33-303">構文とパラメーターの詳細については [、「New-TenantAllowBlockListSpoofItems」を参照してください](/powershell/module/exchange/new-tenantallowblocklistspoofitems)。</span><span class="sxs-lookup"><span data-stu-id="61b33-303">For detailed syntax and parameter information, see [New-TenantAllowBlockListSpoofItems](/powershell/module/exchange/new-tenantallowblocklistspoofitems).</span></span>

### <a name="use-powershell-to-view-block-file-or-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="61b33-304">PowerShell を使用して、テナント許可/ブロック一覧のブロック ファイルまたは URL エントリを表示する</span><span class="sxs-lookup"><span data-stu-id="61b33-304">Use PowerShell to view block file or URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="61b33-305">テナント許可/ブロック一覧でブロック ファイルまたは URL エントリを表示するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="61b33-305">To view block file or URL entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType <FileHash | URL> [-Entry <FileHashValue | URLValue>] [<-ExpirationDate Date | -NoExpiration>]
```

<span data-ttu-id="61b33-306">次の使用例は、指定したファイル ハッシュ値の情報を返します。</span><span class="sxs-lookup"><span data-stu-id="61b33-306">This example returns information for the specified file hash value.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

<span data-ttu-id="61b33-307">この例では、ブロックされているすべての URL を返します。</span><span class="sxs-lookup"><span data-stu-id="61b33-307">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Block
```

<span data-ttu-id="61b33-308">構文とパラメーターの詳細については [、「Get-TenantAllowBlockListItems」を参照してください](/powershell/module/exchange/get-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="61b33-308">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-allow-bulk-mail-sender-domain-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="61b33-309">PowerShell を使用して、テナント許可/ブロック一覧でバルク メール送信者ドメイン エントリを表示する</span><span class="sxs-lookup"><span data-stu-id="61b33-309">Use PowerShell to view allow bulk mail sender domain entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="61b33-310">テナント許可/ブロック一覧でバルク メール送信者ドメイン エントリを表示するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="61b33-310">To view allow bulk mail sender domain entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType BulkSender [-Entry <BulkSenderDomainValue>] [<-ExpirationDate Date | -NoExpiration>]
```

<span data-ttu-id="61b33-311">次の使用例は、許可されている一括メール送信者ドメインを返します。</span><span class="sxs-lookup"><span data-stu-id="61b33-311">This example returns all allowed bulk mail sender domains.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType BulkSender
```

<span data-ttu-id="61b33-312">次の使用例は、指定された一括送信者ドメインの情報を返します。</span><span class="sxs-lookup"><span data-stu-id="61b33-312">This example returns information for the specified bulk sender domain.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "contosodailydeals.com"
```

<span data-ttu-id="61b33-313">構文とパラメーターの詳細については [、「Get-TenantAllowBlockListItems」を参照してください](/powershell/module/exchange/get-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="61b33-313">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="61b33-314">PowerShell を使用して、テナント許可/ブロック一覧でスプーフィングされた送信者エントリを表示またはブロックする</span><span class="sxs-lookup"><span data-stu-id="61b33-314">Use PowerShell to view allow or block spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="61b33-315">テナント許可/ブロック一覧でスプーフィングされた送信者エントリを表示するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="61b33-315">To view spoofed sender entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems [-Action <Allow | Block>] [-SpoofType <External | Internal>
```

<span data-ttu-id="61b33-316">この例では、テナント許可/ブロック一覧のすべてのスプーフィングされた送信者エントリを返します。</span><span class="sxs-lookup"><span data-stu-id="61b33-316">This example returns all spoofed sender entries in the Tenant Allow/Block List.</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems
```

<span data-ttu-id="61b33-317">次の使用例は、内部のスプーフィングされた送信者エントリをすべて返します。</span><span class="sxs-lookup"><span data-stu-id="61b33-317">This example returns all allow spoofed sender entries that are internal.</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems -Action Allow -SpoofType Internal
```

<span data-ttu-id="61b33-318">次の使用例は、外部のすべてのスプーフィングされた送信者エントリを返します。</span><span class="sxs-lookup"><span data-stu-id="61b33-318">This example returns all blocked spoofed sender entries that are external.</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems -Action Block -SpoofType External
```

<span data-ttu-id="61b33-319">構文とパラメーターの詳細については [、「Get-TenantAllowBlockListSpoofItems」を参照してください](/powershell/module/exchange/get-tenantallowblocklistspoofitems)。</span><span class="sxs-lookup"><span data-stu-id="61b33-319">For detailed syntax and parameter information, see [Get-TenantAllowBlockListSpoofItems](/powershell/module/exchange/get-tenantallowblocklistspoofitems).</span></span>

### <a name="use-powershell-to-modify-block-file-and-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="61b33-320">PowerShell を使用して、テナント許可/ブロック一覧のブロック ファイルと URL エントリを変更する</span><span class="sxs-lookup"><span data-stu-id="61b33-320">Use PowerShell to modify block file and URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="61b33-321">テナント許可/ブロック一覧のブロック ファイルと URL エントリを変更するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="61b33-321">To modify block file and URL entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType <FileHash | Url> -Ids <"Id1","Id2",..."IdN"> [<-ExpirationDate Date | -NoExpiration>] [-Notes <String>]
```

<span data-ttu-id="61b33-322">次の使用例は、指定したブロック URL エントリの有効期限を変更します。</span><span class="sxs-lookup"><span data-stu-id="61b33-322">This example changes the expiration date of the specified block URL entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate "5/30/2020"
```

<span data-ttu-id="61b33-323">構文とパラメーターの詳細については [、「Set-TenantAllowBlockListItems」を参照してください](/powershell/module/exchange/set-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="61b33-323">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-allow-bulk-mail-sender-domain-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="61b33-324">PowerShell を使用して、テナント許可/ブロック一覧のバルク メール送信者ドメイン エントリを変更する</span><span class="sxs-lookup"><span data-stu-id="61b33-324">Use PowerShell to modify allow bulk mail sender domain entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="61b33-325">テナント許可/ブロック一覧のバルク メール送信者ドメイン エントリを変更するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="61b33-325">To modify allow bulk mail sender domain entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType BulkSender -Ids <"Id1","Id2",..."IdN"> [<-ExpirationDate Date | -NoExpiration>] [-Notes <String>]
```

<span data-ttu-id="61b33-326">次の使用例は、指定した許可バルク メール送信者ドメイン エントリの有効期限を変更します。</span><span class="sxs-lookup"><span data-stu-id="61b33-326">This example changes the expiration of the specified allow bulk mail sender domain entry to never expire.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType BulkSender -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -NoExpiration
```

<span data-ttu-id="61b33-327">構文とパラメーターの詳細については [、「Get-TenantAllowBlockListItems」を参照してください](/powershell/module/exchange/get-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="61b33-327">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="61b33-328">PowerShell を使用して、テナント許可/ブロック一覧のスプーフィングされた送信者エントリを変更またはブロックする</span><span class="sxs-lookup"><span data-stu-id="61b33-328">Use PowerShell to modify allow or block spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="61b33-329">テナント許可/ブロック一覧でスプーフィングされた送信者エントリの許可またはブロックを変更するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="61b33-329">To modify allow or block spoofed sender entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN"> -Action <Allow | Block>
```

<span data-ttu-id="61b33-330">次の使用例は、スプーフィングされた送信者エントリを許可からブロックに変更します。</span><span class="sxs-lookup"><span data-stu-id="61b33-330">This example changes spoofed sender entry from allow to block.</span></span>

```powershell
Set-TenantAllowBlockListItems -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -Action Block
```

<span data-ttu-id="61b33-331">構文とパラメーターの詳細については [、「Set-TenantAllowBlockListSpoofItems」を参照してください](/powershell/module/exchange/set-tenantallowblocklistspoofitems)。</span><span class="sxs-lookup"><span data-stu-id="61b33-331">For detailed syntax and parameter information, see [Set-TenantAllowBlockListSpoofItems](/powershell/module/exchange/set-tenantallowblocklistspoofitems).</span></span>

### <a name="use-powershell-to-remove-bulk-mail-sender-domain-file-and-domain-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="61b33-332">PowerShell を使用して、一括メール送信者ドメイン、ファイル、およびドメイン エントリをテナント許可/ブロック一覧から削除する</span><span class="sxs-lookup"><span data-stu-id="61b33-332">Use PowerShell to remove bulk mail sender domain, file, and domain entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="61b33-333">一括メール送信者ドメイン エントリの許可、ファイル エントリのブロック、およびテナント許可/ブロックリストからの URL エントリのブロックを削除するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="61b33-333">To remove allow bulk mail sender domain entries, block file entries, and block URL entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType <BulkSender | FileHash | Url> -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="61b33-334">次の使用例は、指定したブロック URL エントリをテナント許可/ブロック一覧から削除します。</span><span class="sxs-lookup"><span data-stu-id="61b33-334">This example removes the specified block URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="61b33-335">構文とパラメーターの詳細については [、「Remove-TenantAllowBlockListItems」を参照してください](/powershell/module/exchange/remove-tenantallowblocklistitems)。</span><span class="sxs-lookup"><span data-stu-id="61b33-335">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-allow-or-block-spoofed-sender-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="61b33-336">PowerShell を使用して、テナント許可/ブロック一覧からスプーフィングされた送信者エントリの許可またはブロックを削除する</span><span class="sxs-lookup"><span data-stu-id="61b33-336">Use PowerShell to remove allow or block spoofed sender entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="61b33-337">テナント許可/ブロック一覧からスプーフィング送信者エントリを許可またはブロックするには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="61b33-337">To remove allow or block spoof sender entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="61b33-338">構文とパラメーターの詳細については [、「Remove-TenantAllowBlockListSpoofItems」を参照してください](/powershell/module/exchange/remove-tenantallowblocklistspoofitems)。</span><span class="sxs-lookup"><span data-stu-id="61b33-338">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListSpoofItems](/powershell/module/exchange/remove-tenantallowblocklistspoofitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="61b33-339">テナント許可/ブロック一覧の URL 構文</span><span class="sxs-lookup"><span data-stu-id="61b33-339">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="61b33-340">IP4v および IPv6 アドレスは許可されますが、TCP/UDP ポートは許可されません。</span><span class="sxs-lookup"><span data-stu-id="61b33-340">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="61b33-341">ファイル名の拡張子は許可されません (たとえば、test.pdf)。</span><span class="sxs-lookup"><span data-stu-id="61b33-341">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="61b33-342">Unicode はサポートされていませんが、Punycode はです。</span><span class="sxs-lookup"><span data-stu-id="61b33-342">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="61b33-343">ホスト名は、次のすべてのステートメントが true の場合に許可されます。</span><span class="sxs-lookup"><span data-stu-id="61b33-343">Hostnames are allowed if all of the following statements are true:</span></span>
  - <span data-ttu-id="61b33-344">ホスト名にはピリオドが含まれる。</span><span class="sxs-lookup"><span data-stu-id="61b33-344">The hostname contains a period.</span></span>
  - <span data-ttu-id="61b33-345">ピリオドの左側に少なくとも 1 つの文字があります。</span><span class="sxs-lookup"><span data-stu-id="61b33-345">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="61b33-346">ピリオドの右側には、少なくとも 2 つの文字があります。</span><span class="sxs-lookup"><span data-stu-id="61b33-346">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="61b33-347">たとえば、 `t.co` 許可されている、または `.com` `contoso.` 許可されない。</span><span class="sxs-lookup"><span data-stu-id="61b33-347">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="61b33-348">サブパスは暗黙的ではありません。</span><span class="sxs-lookup"><span data-stu-id="61b33-348">Subpaths are not implied.</span></span>

  <span data-ttu-id="61b33-349">たとえば、 `contoso.com` は含めではありません `contoso.com/a` 。</span><span class="sxs-lookup"><span data-stu-id="61b33-349">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="61b33-350">ワイルドカード (\*) は、次のシナリオで使用できます。</span><span class="sxs-lookup"><span data-stu-id="61b33-350">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="61b33-351">サブドメインを指定するには、左のワイルドカードの後にピリオドを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="61b33-351">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="61b33-352">たとえば、 `*.contoso.com` 許可されます。 `*contoso.com` 許可されません。</span><span class="sxs-lookup"><span data-stu-id="61b33-352">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="61b33-353">パスを指定するには、右のワイルドカードがスラッシュ (/) に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="61b33-353">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="61b33-354">たとえば、 `contoso.com/*` 許可されている、または `contoso.com*` `contoso.com/ab*` 許可されない。</span><span class="sxs-lookup"><span data-stu-id="61b33-354">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="61b33-355">すべてのサブパスは、適切なワイルドカードによって暗示されるものではありません。</span><span class="sxs-lookup"><span data-stu-id="61b33-355">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="61b33-356">たとえば、 `contoso.com/*` は含めではありません `contoso.com/a` 。</span><span class="sxs-lookup"><span data-stu-id="61b33-356">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="61b33-357">`*.com*` は無効です (解決可能なドメインではなく、右のワイルドカードはスラッシュに従います)。</span><span class="sxs-lookup"><span data-stu-id="61b33-357">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="61b33-358">IP アドレスではワイルドカードは使用できません。</span><span class="sxs-lookup"><span data-stu-id="61b33-358">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="61b33-359">チルダ (~) 文字は、次のシナリオで使用できます。</span><span class="sxs-lookup"><span data-stu-id="61b33-359">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="61b33-360">左チルダは、ドメインとすべてのサブドメインを意味します。</span><span class="sxs-lookup"><span data-stu-id="61b33-360">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="61b33-361">たとえば `~contoso.com` 、includes `contoso.com` と `*.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="61b33-361">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="61b33-362">URL エントリは、すべてのプロトコルに適用されるので、プロトコルを含む URL エントリ (たとえば `http://` `https://` `ftp://` 、) は失敗します。</span><span class="sxs-lookup"><span data-stu-id="61b33-362">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="61b33-363">ユーザー名またはパスワードはサポートされていないか、必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="61b33-363">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="61b33-364">引用符 (' または ") は無効な文字です。</span><span class="sxs-lookup"><span data-stu-id="61b33-364">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="61b33-365">URL には、可能な限りすべてのリダイレクトが含まれる必要があります。</span><span class="sxs-lookup"><span data-stu-id="61b33-365">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="61b33-366">URL エントリのシナリオ</span><span class="sxs-lookup"><span data-stu-id="61b33-366">URL entry scenarios</span></span>

<span data-ttu-id="61b33-367">有効な URL エントリとその結果については、次のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="61b33-367">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="61b33-368">シナリオ: ワイルドカードなし</span><span class="sxs-lookup"><span data-stu-id="61b33-368">Scenario: No wildcards</span></span>

<span data-ttu-id="61b33-369">**エントリ**: `contoso.com`</span><span class="sxs-lookup"><span data-stu-id="61b33-369">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="61b33-370">**一致を許可** する : contoso.com</span><span class="sxs-lookup"><span data-stu-id="61b33-370">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="61b33-371">**[一致しない] を許可します**。</span><span class="sxs-lookup"><span data-stu-id="61b33-371">**Allow not matched**:</span></span>

  - <span data-ttu-id="61b33-372">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="61b33-372">abc-contoso.com</span></span>
  - <span data-ttu-id="61b33-373">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="61b33-373">contoso.com/a</span></span>
  - <span data-ttu-id="61b33-374">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="61b33-374">payroll.contoso.com</span></span>
  - <span data-ttu-id="61b33-375">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="61b33-375">test.com/contoso.com</span></span>
  - <span data-ttu-id="61b33-376">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="61b33-376">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="61b33-377">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="61b33-377">www.contoso.com</span></span>
  - <span data-ttu-id="61b33-378">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="61b33-378">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="61b33-379">**ブロック一致**:</span><span class="sxs-lookup"><span data-stu-id="61b33-379">**Block match**:</span></span>

  - <span data-ttu-id="61b33-380">contoso.com</span><span class="sxs-lookup"><span data-stu-id="61b33-380">contoso.com</span></span>
  - <span data-ttu-id="61b33-381">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="61b33-381">contoso.com/a</span></span>
  - <span data-ttu-id="61b33-382">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="61b33-382">payroll.contoso.com</span></span>
  - <span data-ttu-id="61b33-383">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="61b33-383">test.com/contoso.com</span></span>
  - <span data-ttu-id="61b33-384">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="61b33-384">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="61b33-385">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="61b33-385">www.contoso.com</span></span>
  - <span data-ttu-id="61b33-386">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="61b33-386">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="61b33-387">**ブロックが一致しない**: abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="61b33-387">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="61b33-388">シナリオ: 左ワイルドカード (サブドメイン)</span><span class="sxs-lookup"><span data-stu-id="61b33-388">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="61b33-389">**エントリ**: `*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="61b33-389">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="61b33-390">**一致とブロック** の **一致を許可する**:</span><span class="sxs-lookup"><span data-stu-id="61b33-390">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="61b33-391">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="61b33-391">www.contoso.com</span></span>
  - <span data-ttu-id="61b33-392">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="61b33-392">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="61b33-393">**[一致しない] と** [ **ブロックが一致しない] を許可します**。</span><span class="sxs-lookup"><span data-stu-id="61b33-393">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="61b33-394">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="61b33-394">123contoso.com</span></span>
  - <span data-ttu-id="61b33-395">contoso.com</span><span class="sxs-lookup"><span data-stu-id="61b33-395">contoso.com</span></span>
  - <span data-ttu-id="61b33-396">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="61b33-396">test.com/contoso.com</span></span>
  - <span data-ttu-id="61b33-397">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="61b33-397">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="61b33-398">シナリオ: パスの上部にある右のワイルドカード</span><span class="sxs-lookup"><span data-stu-id="61b33-398">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="61b33-399">**エントリ**: `contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="61b33-399">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="61b33-400">**一致とブロック** の **一致を許可する**:</span><span class="sxs-lookup"><span data-stu-id="61b33-400">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="61b33-401">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="61b33-401">contoso.com/a/b</span></span>
  - <span data-ttu-id="61b33-402">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="61b33-402">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="61b33-403">contoso.com/a/?q=joe@t.com</span><span class="sxs-lookup"><span data-stu-id="61b33-403">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="61b33-404">**[一致しない] と** [ **ブロックが一致しない] を許可します**。</span><span class="sxs-lookup"><span data-stu-id="61b33-404">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="61b33-405">contoso.com</span><span class="sxs-lookup"><span data-stu-id="61b33-405">contoso.com</span></span>
  - <span data-ttu-id="61b33-406">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="61b33-406">contoso.com/a</span></span>
  - <span data-ttu-id="61b33-407">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="61b33-407">www.contoso.com</span></span>
  - <span data-ttu-id="61b33-408">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="61b33-408">www.contoso.com/q=a@contoso.com</span></span>

#### <a name="scenario-left-tilde"></a><span data-ttu-id="61b33-409">シナリオ: 左チルダ</span><span class="sxs-lookup"><span data-stu-id="61b33-409">Scenario: Left tilde</span></span>

<span data-ttu-id="61b33-410">**エントリ**: `~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="61b33-410">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="61b33-411">**一致とブロック** の **一致を許可する**:</span><span class="sxs-lookup"><span data-stu-id="61b33-411">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="61b33-412">contoso.com</span><span class="sxs-lookup"><span data-stu-id="61b33-412">contoso.com</span></span>
  - <span data-ttu-id="61b33-413">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="61b33-413">www.contoso.com</span></span>
  - <span data-ttu-id="61b33-414">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="61b33-414">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="61b33-415">**[一致しない] と** [ **ブロックが一致しない] を許可します**。</span><span class="sxs-lookup"><span data-stu-id="61b33-415">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="61b33-416">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="61b33-416">123contoso.com</span></span>
  - <span data-ttu-id="61b33-417">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="61b33-417">contoso.com/abc</span></span>
  - <span data-ttu-id="61b33-418">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="61b33-418">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="61b33-419">シナリオ: 右のワイルドカード サフィックス</span><span class="sxs-lookup"><span data-stu-id="61b33-419">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="61b33-420">**エントリ**: `contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="61b33-420">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="61b33-421">**一致とブロック** の **一致を許可する**:</span><span class="sxs-lookup"><span data-stu-id="61b33-421">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="61b33-422">contoso.com/?q=whatever@fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="61b33-422">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="61b33-423">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="61b33-423">contoso.com/a</span></span>
  - <span data-ttu-id="61b33-424">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="61b33-424">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="61b33-425">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="61b33-425">contoso.com/ab</span></span>
  - <span data-ttu-id="61b33-426">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="61b33-426">contoso.com/b</span></span>
  - <span data-ttu-id="61b33-427">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="61b33-427">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="61b33-428">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="61b33-428">contoso.com/ba</span></span>

- <span data-ttu-id="61b33-429">**[一致しない] と** **[ブロックが一致しない**] : contoso.com</span><span class="sxs-lookup"><span data-stu-id="61b33-429">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="61b33-430">シナリオ: 左ワイルドカード サブドメインと右のワイルドカード サフィックス</span><span class="sxs-lookup"><span data-stu-id="61b33-430">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="61b33-431">**エントリ**: `*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="61b33-431">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="61b33-432">**一致とブロック** の **一致を許可する**:</span><span class="sxs-lookup"><span data-stu-id="61b33-432">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="61b33-433">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="61b33-433">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="61b33-434">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="61b33-434">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="61b33-435">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="61b33-435">www.contoso.com/a</span></span>
  - <span data-ttu-id="61b33-436">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="61b33-436">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="61b33-437">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="61b33-437">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="61b33-438">**[一致しない] と** **[ブロックが一致しない**] : contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="61b33-438">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="61b33-439">シナリオ: 左右のチルダ</span><span class="sxs-lookup"><span data-stu-id="61b33-439">Scenario: Left and right tilde</span></span>

<span data-ttu-id="61b33-440">**エントリ**: `~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="61b33-440">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="61b33-441">**一致とブロック** の **一致を許可する**:</span><span class="sxs-lookup"><span data-stu-id="61b33-441">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="61b33-442">contoso.com</span><span class="sxs-lookup"><span data-stu-id="61b33-442">contoso.com</span></span>
  - <span data-ttu-id="61b33-443">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="61b33-443">contoso.com/a</span></span>
  - <span data-ttu-id="61b33-444">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="61b33-444">www.contoso.com</span></span>
  - <span data-ttu-id="61b33-445">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="61b33-445">www.contoso.com/b</span></span>
  - <span data-ttu-id="61b33-446">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="61b33-446">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="61b33-447">**[一致しない] と** [ **ブロックが一致しない] を許可します**。</span><span class="sxs-lookup"><span data-stu-id="61b33-447">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="61b33-448">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="61b33-448">123contoso.com</span></span>
  - <span data-ttu-id="61b33-449">contoso.org</span><span class="sxs-lookup"><span data-stu-id="61b33-449">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="61b33-450">シナリオ: IP アドレス</span><span class="sxs-lookup"><span data-stu-id="61b33-450">Scenario: IP address</span></span>

<span data-ttu-id="61b33-451">**エントリ**: `1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="61b33-451">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="61b33-452">**一致と\*\*\*\*ブロックの一** 致を許可する : 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="61b33-452">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="61b33-453">**[一致しない] と** [ **ブロックが一致しない] を許可します**。</span><span class="sxs-lookup"><span data-stu-id="61b33-453">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="61b33-454">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="61b33-454">1.2.3.4/a</span></span>
  - <span data-ttu-id="61b33-455">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="61b33-455">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="61b33-456">適切なワイルドカードを持つ IP アドレス</span><span class="sxs-lookup"><span data-stu-id="61b33-456">IP address with right wildcard</span></span>

<span data-ttu-id="61b33-457">**エントリ**: `1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="61b33-457">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="61b33-458">**一致とブロック** の **一致を許可する**:</span><span class="sxs-lookup"><span data-stu-id="61b33-458">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="61b33-459">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="61b33-459">1.2.3.4/b</span></span>
  - <span data-ttu-id="61b33-460">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="61b33-460">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="61b33-461">無効なエントリの例</span><span class="sxs-lookup"><span data-stu-id="61b33-461">Examples of invalid entries</span></span>

<span data-ttu-id="61b33-462">次のエントリが無効です。</span><span class="sxs-lookup"><span data-stu-id="61b33-462">The following entries are invalid:</span></span>

- <span data-ttu-id="61b33-463">**ドメイン値が見つからないか無効です**。</span><span class="sxs-lookup"><span data-stu-id="61b33-463">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="61b33-464">contoso</span><span class="sxs-lookup"><span data-stu-id="61b33-464">contoso</span></span>
  - <span data-ttu-id="61b33-465">\*.contoso.\*</span><span class="sxs-lookup"><span data-stu-id="61b33-465">\*.contoso.\*</span></span>
  - <span data-ttu-id="61b33-466">\*.com</span><span class="sxs-lookup"><span data-stu-id="61b33-466">\*.com</span></span>
  - <span data-ttu-id="61b33-467">\*.pdf</span><span class="sxs-lookup"><span data-stu-id="61b33-467">\*.pdf</span></span>

- <span data-ttu-id="61b33-468">**テキストまたはスペース文字なしのワイルドカード**:</span><span class="sxs-lookup"><span data-stu-id="61b33-468">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="61b33-469">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="61b33-469">\*contoso.com</span></span>
  - <span data-ttu-id="61b33-470">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="61b33-470">contoso.com\*</span></span>
  - <span data-ttu-id="61b33-471">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="61b33-471">\*1.2.3.4</span></span>
  - <span data-ttu-id="61b33-472">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="61b33-472">1.2.3.4\*</span></span>
  - <span data-ttu-id="61b33-473">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="61b33-473">contoso.com/a\*</span></span>
  - <span data-ttu-id="61b33-474">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="61b33-474">contoso.com/ab\*</span></span>

- <span data-ttu-id="61b33-475">**ポートを含む IP アドレス**:</span><span class="sxs-lookup"><span data-stu-id="61b33-475">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="61b33-476">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="61b33-476">contoso.com:443</span></span>
  - <span data-ttu-id="61b33-477">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="61b33-477">abc.contoso.com:25</span></span>

- <span data-ttu-id="61b33-478">**説明的でないワイルドカード**:</span><span class="sxs-lookup"><span data-stu-id="61b33-478">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="61b33-479">\*.\*</span><span class="sxs-lookup"><span data-stu-id="61b33-479">\*.\*</span></span>

- <span data-ttu-id="61b33-480">**中央のワイルドカード**:</span><span class="sxs-lookup"><span data-stu-id="61b33-480">**Middle wildcards**:</span></span>

  - <span data-ttu-id="61b33-481">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="61b33-481">conto\*so.com</span></span>
  - <span data-ttu-id="61b33-482">conto~so.com</span><span class="sxs-lookup"><span data-stu-id="61b33-482">conto~so.com</span></span>

- <span data-ttu-id="61b33-483">**2 つのワイルドカード**</span><span class="sxs-lookup"><span data-stu-id="61b33-483">**Double wildcards**</span></span>

  - <span data-ttu-id="61b33-484">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="61b33-484">contoso.com/\*\*</span></span>
  - <span data-ttu-id="61b33-485">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="61b33-485">contoso.com/\*/\*</span></span>

## <a name="domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="61b33-486">テナント許可/ブロック一覧のスプーフィングされた送信者エントリのドメインペア構文</span><span class="sxs-lookup"><span data-stu-id="61b33-486">Domain pair syntax for spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="61b33-487">テナント許可/ブロック一覧のスプーフィング送信者のドメイン ペアは、次の構文を使用します `<Spoofed user>, <Sending infrastructure>` 。</span><span class="sxs-lookup"><span data-stu-id="61b33-487">A domain pair for a spoofed sender in the Tenant Allow/Block List uses the following syntax: `<Spoofed user>, <Sending infrastructure>`.</span></span>

- <span data-ttu-id="61b33-488">**スプーフィングされた** ユーザー: この値には、メール クライアントの [From] ボックスに表示されるスプーフィングされたユーザーの電子メール アドレスが含まれる。</span><span class="sxs-lookup"><span data-stu-id="61b33-488">**Spoofed user**: This value involves the email address of the spoofed user that's displayed in the **From** box in email clients.</span></span> <span data-ttu-id="61b33-489">このアドレスは、アドレスとも呼 `5322.From` ばれる。</span><span class="sxs-lookup"><span data-stu-id="61b33-489">This address is also known as the `5322.From` address.</span></span> <span data-ttu-id="61b33-490">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="61b33-490">Valid values include:</span></span>
  - <span data-ttu-id="61b33-491">個々の電子メール アドレス (たとえば、chris@contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="61b33-491">An individual email address (for example, chris@contoso.com).</span></span>
  - <span data-ttu-id="61b33-492">電子メール ドメイン (たとえば、contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="61b33-492">An email domain (for example, contoso.com).</span></span>
  - <span data-ttu-id="61b33-493">ワイルドカード文字 (たとえば \* )。</span><span class="sxs-lookup"><span data-stu-id="61b33-493">The wildcard character (for example, \*).</span></span>

- <span data-ttu-id="61b33-494">**送信インフラストラクチャ**: この値は、スプーフィングされたユーザーからのメッセージのソースを示します。</span><span class="sxs-lookup"><span data-stu-id="61b33-494">**Sending infrastructure**: This value indicates the source of messages from the spoofed user.</span></span> <span data-ttu-id="61b33-495">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="61b33-495">Valid values include:</span></span>
  - <span data-ttu-id="61b33-496">送信元電子メール サーバーの IP アドレスの逆引き DNS 参照 (PTR レコード) で見つかったドメイン (たとえば、fabrikam.com)。</span><span class="sxs-lookup"><span data-stu-id="61b33-496">The domain found in a reverse DNS lookup (PTR record) of the source email server's IP address (for example, fabrikam.com).</span></span>
  - <span data-ttu-id="61b33-497">送信元 IP アドレスに PTR レコードがない場合、送信インフラストラクチャは \<source IP\> /24 として識別されます (たとえば、192.168.100.100/24 など)。</span><span class="sxs-lookup"><span data-stu-id="61b33-497">If the source IP address has no PTR record, then the sending infrastructure is identified as \<source IP\>/24 (for example, 192.168.100.100/24).</span></span>

<span data-ttu-id="61b33-498">スプーフィングされた送信者を識別するための有効なドメイン ペアの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="61b33-498">Here are some examples of valid domain pairs to identify spoofed senders:</span></span>

- `contoso.com, 192.168.100.100/24`
- `chris@contoso.com, fabrikam.com`
- `*, contoso.net`

<span data-ttu-id="61b33-499">ドメイン ペアを追加すると、スプーフィングされたユーザーと送信インフラストラクチャの組み合わせだけが許可またはブロックされます。</span><span class="sxs-lookup"><span data-stu-id="61b33-499">Adding a domain pair only allows or blocks the *combination* of the spoofed user *and* the sending infrastructure.</span></span> <span data-ttu-id="61b33-500">スプーフィングされたユーザーからのメールを任意のソースから許可したり、スプーフィングされたユーザーに対して送信インフラストラクチャ ソースからのメールを許可したりはしない。</span><span class="sxs-lookup"><span data-stu-id="61b33-500">It does not allow email from the spoofed user from any source, nor does it allow email from the sending infrastructure source for any spoofed user.</span></span>

<span data-ttu-id="61b33-501">たとえば、次のドメインペアの許可エントリを追加します。</span><span class="sxs-lookup"><span data-stu-id="61b33-501">For example, you add an allow entry for the following domain pair:</span></span>

- <span data-ttu-id="61b33-502">**ドメイン**: gmail.com</span><span class="sxs-lookup"><span data-stu-id="61b33-502">**Domain**: gmail.com</span></span>
- <span data-ttu-id="61b33-503">**インフラストラクチャ**: tms.mx.com</span><span class="sxs-lookup"><span data-stu-id="61b33-503">**Infrastructure**: tms.mx.com</span></span>

<span data-ttu-id="61b33-504">スプーフィングを許可できるのは、そのドメインと送信インフラストラクチャ のペアからのメッセージのみです。</span><span class="sxs-lookup"><span data-stu-id="61b33-504">Only messages from that domain *and* sending infrastructure pair are allowed to spoof.</span></span> <span data-ttu-id="61b33-505">スプーフィングを試みる gmail.com 送信者は許可されません。</span><span class="sxs-lookup"><span data-stu-id="61b33-505">Other senders attempting to spoof gmail.com aren't allowed.</span></span> <span data-ttu-id="61b33-506">ユーザーから発信される他のドメインの送信者からの tms.mx.com スプーフィング インテリジェンスによってチェックされます。</span><span class="sxs-lookup"><span data-stu-id="61b33-506">Messages from senders in other domains originating from tms.mx.com are checked by spoof intelligence.</span></span>
