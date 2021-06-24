---
title: Microsoft Defender セーフのリンク ポリシーを設定Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: ''
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: bdd5372d-775e-4442-9c1b-609627b94b5d
ms.collection:
- M365-security-compliance
description: 管理者は、Microsoft Defender for microsoft Defender の セーフ リンク ポリシーとグローバル セーフ リンクの設定を表示、作成、変更、および削除する方法をOffice 365。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8d42051d2ca4f26758cbe7334d427f3f93178f97
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108213"
---
# <a name="set-up-safe-links-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="b5fbc-103">Microsoft Defender セーフのリンク ポリシーを設定Office 365</span><span class="sxs-lookup"><span data-stu-id="b5fbc-103">Set up Safe Links policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="b5fbc-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="b5fbc-104">**Applies to**</span></span>
- [<span data-ttu-id="b5fbc-105">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="b5fbc-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="b5fbc-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b5fbc-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> <span data-ttu-id="b5fbc-107">この記事は、[Microsoft Defender for Office 365](defender-for-office-365.md) をご利用の法人のお客様を対象としています。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-107">This article is intended for business customers who have [Microsoft Defender for Office 365](defender-for-office-365.md).</span></span> <span data-ttu-id="b5fbc-108">セーフリンクに関する情報を探しているホーム ユーザーの場合は、「Advanced [Outlook Outlook.com セキュリティ」を参照してください](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-108">If you are a home user looking for information about Safelinks in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="b5fbc-109">セーフMicrosoft [Defender for Office 365 のリンクは、](defender-for-office-365.md)メール フロー内の受信メール メッセージの URL スキャン、および電子メール メッセージ内の URL とリンクのクリック検証の時間を提供します。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-109">Safe Links in [Microsoft Defender for Office 365](defender-for-office-365.md) provides URL scanning of inbound email messages in mail flow, and time of click verification of URLs and links in email messages and in other locations.</span></span> <span data-ttu-id="b5fbc-110">詳細については[、「Microsoft Defender セーフリンク」を参照Office 365。](safe-links.md)</span><span class="sxs-lookup"><span data-stu-id="b5fbc-110">For more information, see [Safe Links in Microsoft Defender for Office 365](safe-links.md).</span></span>

<span data-ttu-id="b5fbc-111">リンク ポリシーに組み込みまたは既定セーフはありません。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-111">There's no built-in or default Safe Links policy.</span></span> <span data-ttu-id="b5fbc-112">URL のセーフを取得するには、この記事で説明するように 1 つ以上の セーフリンク ポリシーを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-112">To get Safe Links scanning of URLs, you need to create one or more Safe Links policies as described in this article.</span></span>

> [!NOTE]
>
> <span data-ttu-id="b5fbc-113">リンクの保護のグローバル設定は、セーフリンク ポリシー以外セーフ構成します。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-113">You configure the global settings for Safe Links protection **outside** of Safe Links policies.</span></span> <span data-ttu-id="b5fbc-114">手順については、「Microsoft Defender for セーフリンクのグローバル設定を構成する[」を参照Office 365。](configure-global-settings-for-safe-links.md)</span><span class="sxs-lookup"><span data-stu-id="b5fbc-114">For instructions, see [Configure global settings for Safe Links in Microsoft Defender for Office 365](configure-global-settings-for-safe-links.md).</span></span>
>
> <span data-ttu-id="b5fbc-115">管理者は、リンクに関するさまざまな構成設定を検討セーフ必要があります。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-115">Admins should consider the different configuration settings for Safe Links.</span></span> <span data-ttu-id="b5fbc-116">使用可能なオプションの 1 つは、ユーザー識別可能な情報を [リンク] セーフします。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-116">One of the available options is to include user identifiable information in Safe Links.</span></span> <span data-ttu-id="b5fbc-117">この機能により *、セキュリティ Ops チームは* 、潜在的なユーザー侵害を調査し、是正措置を取り、コストのかかる侵害を制限できます。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-117">This feature enables *Security Ops teams* to investigate potential user compromise, take corrective action, and limit costly breaches.</span></span>

<span data-ttu-id="b5fbc-118">セーフ リンク ポリシーは、Microsoft 365 Defender ポータルまたは PowerShell (Exchange Online のメールボックスを持つ適格な Microsoft 365 組織の場合は Exchange Online PowerShell、Exchange Online メールボックスのない組織ではスタンドアロンの EOP PowerShell、Office 365 アドオン サブスクリプションの場合は Microsoft Defender を使用) で構成できます。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-118">You can configure Safe Links policies in the Microsoft 365 Defender portal or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Microsoft Defender for Office 365 add-on subscriptions).</span></span>

<span data-ttu-id="b5fbc-119">リンク ポリシーの基本的なセーフは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-119">The basic elements of a Safe Links policy are:</span></span>

- <span data-ttu-id="b5fbc-120">安全なリンク **ポリシー:** セーフ リンク保護を有効にし、リアルタイム URL スキャンを有効にし、メッセージを配信する前にリアルタイム スキャンが完了するのを待つかどうかを指定し、内部メッセージのスキャンをオンにし、URL のユーザークリックを追跡するかどうかを指定し、ユーザーが元の URL へのトラフをクリックできるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-120">**The safe links policy**: Turn on Safe Links protection, turn on real-time URL scanning, specify whether to wait for real-time scanning to complete before delivering the message, turn on scanning for internal messages, specify whether to track user clicks on URLs, and specify whether to allow users to click trough to the original URL.</span></span>
- <span data-ttu-id="b5fbc-121">**安全なリンクルール**: 優先度と受信者のフィルター (ポリシーが適用されるユーザー) を指定します。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-121">**The safe links rule**: Specifies the priority and recipient filters (who the policy applies to).</span></span>

<span data-ttu-id="b5fbc-122">これらの 2 つの要素の違いは、セーフ ポータルでリンク ポリシーを管理Microsoft 365 Defenderではありません。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-122">The difference between these two elements isn't obvious when you manage Safe Links policies in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="b5fbc-123">セーフ リンク ポリシーを作成するときに、両方に同じ名前を使用して、安全なリンク ルールと関連付けられた安全なリンク ポリシーを同時に作成します。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-123">When you create a Safe Links policy, you're actually creating a safe links rule and the associated safe links policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="b5fbc-124">リンク ポリシーを変更セーフ、名前、優先度、有効または無効、および受信者フィルターに関連する設定によって、安全なリンク ルールが変更されます。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-124">When you modify a Safe Links policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the safe links rule.</span></span> <span data-ttu-id="b5fbc-125">その他の設定はすべて、関連付けられたセーフ リンク ポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-125">All other settings modify the associated safe links policy.</span></span>
- <span data-ttu-id="b5fbc-126">リンク ポリシーを削除セーフ、セーフ リンク ルールと関連付けられたセーフ リンク ポリシーが削除されます。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-126">When you remove a Safe Links policy, the safe links rule and the associated safe links policy are removed.</span></span>

<span data-ttu-id="b5fbc-127">Exchange Online PowerShell またはスタンドアロン EOP PowerShell では、ポリシーとルールを個別に管理します。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-127">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="b5fbc-128">詳細については、この記事の後半Exchange Online「PowerShell またはスタンドアロン[EOP PowerShell](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies)を使用して セーフリンク ポリシーを構成する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-128">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Links policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) section later in this article.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="b5fbc-129">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="b5fbc-129">What do you need to know before you begin?</span></span>

- <span data-ttu-id="b5fbc-130"><https://security.microsoft.com/> で Microsoft 365 Defender ポータルを開きます。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-130">You open the Microsoft 365 Defender portal at <https://security.microsoft.com/>.</span></span> <span data-ttu-id="b5fbc-131">[リンク] ページに直接 **移動セーフを** 使用します <https://security.microsoft.com/safelinksv2> 。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-131">To go directly to the **Safe Links** page, use <https://security.microsoft.com/safelinksv2>.</span></span>

- <span data-ttu-id="b5fbc-132">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-132">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="b5fbc-133">スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-133">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="b5fbc-134">この記事の手順を実行するには、アクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-134">You need to be assigned permissions before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="b5fbc-135">セーフ リンク ポリシーを作成、変更、および削除するには、Microsoft 365 Defender ポータルの組織の管理またはセキュリティ管理者の役割グループのメンバーであり、Exchange Online の組織の管理役割グループのメンバーである必要があります。 </span><span class="sxs-lookup"><span data-stu-id="b5fbc-135">To create, modify, and delete Safe Links policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Microsoft 365 Defender portal **and** a member of the **Organization Management** role group in Exchange Online.</span></span>
  - <span data-ttu-id="b5fbc-136">リンク ポリシーへの読み取りセーフアクセスするには、グローバル リーダーまたはセキュリティ リーダーの役割グループのメンバー **である** 必要があります。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-136">For read-only access to Safe Links policies, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="b5fbc-137">詳細については、「Microsoft 365 Defender[](permissions-microsoft-365-security-center.md)ポータルのアクセス許可」および「Exchange Online」[を参照してください](/exchange/permissions-exo/permissions-exo)。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-137">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md) and [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  >
  > - <span data-ttu-id="b5fbc-138">Microsoft 365 管理センター の対応する Azure Active Directory ロールにユーザーを追加すると、Microsoft 365 Defender ポータルで必要なアクセス許可と、Microsoft 365の他の機能に対するアクセス許可が付与されます。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-138">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="b5fbc-139">詳細については、「[管理者の役割について](../../admin/add-users/about-admin-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-139">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  <span data-ttu-id="b5fbc-140">.</span><span class="sxs-lookup"><span data-stu-id="b5fbc-140">.</span></span> <span data-ttu-id="b5fbc-141">- ビュー **専用の組織の管理** 役割グループ [](/Exchange/permissions-exo/permissions-exo#role-groups)は、Exchange Online機能への読み取り専用アクセスも提供します。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-141">- The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="b5fbc-142">リンク ポリシーの推奨設定についてはセーフリンク ポリシー[のセーフを参照してください](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings)。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-142">For our recommended settings for Safe Links policies, see [Safe Links policy settings](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings).</span></span>

- <span data-ttu-id="b5fbc-143">新しいポリシーまたは更新されたポリシーを適用するには、最大 30 分かかります。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-143">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="b5fbc-144">[新しい機能は、Microsoft Defender](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365)に継続的に追加Office 365。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-144">[New features are continually being added to Microsoft Defender for Office 365](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="b5fbc-145">新しい機能が追加された場合、既存のリンク ポリシーを調整するセーフがあります。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-145">As new features are added, you may need to make adjustments to your existing Safe Links policies.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-create-safe-links-policies"></a><span data-ttu-id="b5fbc-146">リンク ポリシーをMicrosoft 365 Defenderするには、セーフ ポータルを使用します。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-146">Use the Microsoft 365 Defender portal to create Safe Links policies</span></span>

<span data-ttu-id="b5fbc-147">Microsoft 365 Defender ポータルでカスタム セーフ リンク ポリシーを作成すると、両方に同じ名前を使用して、安全なリンク ルールと関連付けられた安全なリンク ポリシーが同時に作成されます。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-147">Creating a custom Safe Links policy in the Microsoft 365 Defender portal creates the safe links rule and the associated safe links policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="b5fbc-148">このポータルMicrosoft 365 Defender、[ポリシー] **&[** 脅威ポリシー ポリシー] セクションの [リンク \>  \>  \> **] セーフ移動します**。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-148">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Policies** section \> **Safe Links**.</span></span>

2. <span data-ttu-id="b5fbc-149">[リンクの **セーフ] ページで**、[作成] アイコン ![ [作成] を ](../../media/m365-cc-sc-create-icon.png) **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-149">On the **Safe Links** page, click ![Create icon](../../media/m365-cc-sc-create-icon.png) **Create**.</span></span>

3. <span data-ttu-id="b5fbc-150">[**新しいリンクセーフ] ポリシー ウィザードが** 開きます。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-150">The **New Safe Links policy** wizard opens.</span></span> <span data-ttu-id="b5fbc-151">[ポリシーに **名前を付け] ページ** で、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-151">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="b5fbc-152">**[名前]**: わかりやすい一意のポリシー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-152">**Name**: Enter a unique, descriptive name for the policy.</span></span>
   - <span data-ttu-id="b5fbc-153">**[説明]**: ポリシーについての説明を入力します (オプション)。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-153">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="b5fbc-154">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-154">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="b5fbc-155">表示される **[ユーザーとドメイン] ページ** で、ポリシーが適用される内部受信者 (受信者の条件) を特定します。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-155">On the **Users and domains** page that appears, identify the internal recipients that the policy applies to (recipient conditions):</span></span>
   - <span data-ttu-id="b5fbc-156">**ユーザー**: 組織内で指定された 1 つ以上のメールボックス、メール ユーザー、またはメール連絡先。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-156">**Users**: The specified mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="b5fbc-157">**グループ**: 組織内で指定された配布グループ、メール対応セキュリティ グループ、または Microsoft 365 グループ。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-157">**Groups**: The specified distribution groups, mail-enabled security groups, or Microsoft 365 Groups in your organization.</span></span>
   - <span data-ttu-id="b5fbc-158">**ドメイン**: 組織内で指定された [承認済みドメイン](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)のすべての受信者。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-158">**Domains**: All recipients in the specified [accepted domains](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) in your organization.</span></span>

   <span data-ttu-id="b5fbc-159">適正なボックスをクリックし、値の入力を開始し、結果で希望する値を選択します。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-159">Click in the appropriate box, start typing a value, and select the value that you want from the results.</span></span> <span data-ttu-id="b5fbc-160">必要な回数だけこの処理を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-160">Repeat this process as many times as necessary.</span></span> <span data-ttu-id="b5fbc-161">既存の値を削除するには、削除をクリックします</span><span class="sxs-lookup"><span data-stu-id="b5fbc-161">To remove an existing value, click remove</span></span> ![[削除] アイコン](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="b5fbc-163">値の隣。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-163">next to the value.</span></span>

   <span data-ttu-id="b5fbc-164">ユーザーやグループには、ほとんどの識別子 (名前、表示名、エイリアス、メールアドレス、アカウント名など) を使用できますが、対応する表示名が結果に表示されます。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-164">For users or groups, you can use most identifiers (name, display name, alias, email address, account name, etc.), but the corresponding display name is shown in the results.</span></span> <span data-ttu-id="b5fbc-165">ユーザーの場合、アスタリスク (\*) を単独で入力すると、使用可能なすべての値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-165">For users, enter an asterisk (\*) by itself to see all available values.</span></span>

   <span data-ttu-id="b5fbc-166">同じ条件に複数の値がある場合、OR ロジック (たとえば、_\<recipient1\>_ または _\<recipient2\>_) が適用されます。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-166">Multiple values in the same condition use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="b5fbc-167">別の条件では、AND ロジック (たとえば、_\<recipient1\>_ かつ _\<member of group 1\>_) を使用します。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-167">Different conditions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   - <span data-ttu-id="b5fbc-168">**これらのユーザー、グループ**、およびドメインを除外する : ポリシーが適用される内部受信者 (受信者の例外) に例外を追加するには、このオプションを選択し、例外を構成します。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-168">**Exclude these users, groups, and domains**: To add exceptions for the internal recipients that the policy applies to (recipient exceptions), select this option and configure the exceptions.</span></span> <span data-ttu-id="b5fbc-169">設定と動作は、条件とまったく同じです。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-169">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="b5fbc-170">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-170">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="b5fbc-171">表示される **[保護の設定** ] ページで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-171">On the **Protection settings** page that appears, configure the following settings:</span></span>
   - <span data-ttu-id="b5fbc-172">**メッセージ内の不明な潜在的に** 悪意のある URL のアクションを選択します:[**オン**] を選択して、セーフリンク保護を有効にします。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-172">**Select the action for unknown potentially malicious URLs in messages**: Select **On** to enable Safe Links protection for links in email messages.</span></span> <span data-ttu-id="b5fbc-173">この設定を有効にすると、次の設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-173">If you turn this setting on, the following settings are available:</span></span>
     - <span data-ttu-id="b5fbc-174">**ファイルを指す** 疑わしいリンクやリンクのリアルタイム URL スキャンを適用する: 電子メール メッセージ内のリンクのリアルタイム スキャンを有効にするには、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-174">**Apply real-time URL scanning for suspicious links and links that point to files**: Select this option to enable real-time scanning of links in email messages.</span></span> <span data-ttu-id="b5fbc-175">この設定を次の設定で有効にした場合は、次の設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-175">If you turn this setting on the following setting is available:</span></span>
       - <span data-ttu-id="b5fbc-176">**メッセージを配信する前** に URL のスキャンが完了するのを待つ: このオプションを選択すると、メッセージを配信する前にリアルタイム URL スキャンが完了するのを待ちます。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-176">**Wait for URL scanning to complete before delivering the message**: Select this option to wait for real-time URL scanning to complete before delivering the message.</span></span>
     - <span data-ttu-id="b5fbc-177">**[セーフ組織内** で送信された電子メール メッセージへのリンクを適用する: 内部送信者と内部受信者の間のメッセージに セーフ リンク ポリシーを適用するには、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-177">**Apply Safe Links to email messages sent within the organization**: Select this option to apply the Safe Links policy to messages between internal senders and internal recipients.</span></span>
   - <span data-ttu-id="b5fbc-178">**[リンク内の不明な** URL または潜在的に悪意のある URLのアクションをMicrosoft Teams: [オン] を選択して、セーフ リンクの保護を有効Teams。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-178">**Select the action for unknown or potentially malicious URLs within Microsoft Teams**: Select **On** to enable Safe Links protection for links in Teams.</span></span>
   - <span data-ttu-id="b5fbc-179">**ユーザーのクリックを追跡しない**: この設定を選択しないままにして、電子メール メッセージ内の URL を追跡するユーザーのクリックを有効にします。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-179">**Do not track user clicks**: Leave this setting unselected to enable the tracking user clicks on URLs in email messages.</span></span>
   - <span data-ttu-id="b5fbc-180">**ユーザーに元の URL** へのクリックを許可しない : このオプションを選択すると、警告ページでユーザーが元の URL をクリックしてクリックを [ブロックできます](safe-links.md#warning-pages-from-safe-links)。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-180">**Do not allow users to click through to original URL**: Select this option to block users from clicking through to the original URL in [warning pages](safe-links.md#warning-pages-from-safe-links).</span></span>
   - <span data-ttu-id="b5fbc-181">**次の URL を書き換えない**: 指定された URL にアクセスし、それ以外の場合はリンクによってブロックセーフします。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-181">**Do not rewrite the following URLs**: Allows access the specified URLs that would otherwise be blocked by Safe Links.</span></span>

     <span data-ttu-id="b5fbc-182">ボックスに、必要な URL または値を入力し、[追加] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-182">In the box, type the URL or value that you want, and then click **Add**.</span></span> <span data-ttu-id="b5fbc-183">必要な回数だけこの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-183">Repeat this step as many times as necessary.</span></span>

     <span data-ttu-id="b5fbc-184">既存のエントリを削除するには、</span><span class="sxs-lookup"><span data-stu-id="b5fbc-184">To remove an existing entry, click</span></span> ![[削除] アイコン](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="b5fbc-186">をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-186">next to the entry.</span></span>

     <span data-ttu-id="b5fbc-187">エントリの構文については、「次の URL を書き換えない」リストの Entry 構文 [を参照してください](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-187">For entry syntax, see [Entry syntax for the "Do not rewrite the following URLs" list](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span></span>

   <span data-ttu-id="b5fbc-188">これらの設定の詳細については、「電子メール[](safe-links.md#safe-links-settings-for-email-messages)メッセージセーフリンクの設定」および「セーフリンクの設定」[を参照](safe-links.md#safe-links-settings-for-microsoft-teams)Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-188">For detailed information about these settings, see [Safe Links settings for email messages](safe-links.md#safe-links-settings-for-email-messages) and [Safe Links settings for Microsoft Teams](safe-links.md#safe-links-settings-for-microsoft-teams).</span></span>

   <span data-ttu-id="b5fbc-189">Standard および Strict ポリシー設定の推奨値の詳細については、「リンク[ポリシー設定セーフを参照してください](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings)。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-189">For more the recommended values for Standard and Strict policy settings, see [Safe Links policy settings](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings).</span></span>

   <span data-ttu-id="b5fbc-190">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-190">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="b5fbc-191">表示される **[通知** ] ページで、[ユーザーに通知する方法] で次のいずれかの **値を選択します**。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-191">On the **Notification** page that appears, select one of the following values for **How would you like to notify your users?**:</span></span>
   - <span data-ttu-id="b5fbc-192">**既定の通知テキストを使用する**</span><span class="sxs-lookup"><span data-stu-id="b5fbc-192">**Use the default notification text**</span></span>
   - <span data-ttu-id="b5fbc-193">**カスタム通知テキストを使用** する: この値を選択すると (長さは 200 文字を超えることはできません)、次の設定が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-193">**Use custom notification text**: If you select this value (the length cannot exceed 200 characters), the following settings appear:</span></span>
     - <span data-ttu-id="b5fbc-194">**自動ローカライズMicrosoft 翻訳ツールを使用する**</span><span class="sxs-lookup"><span data-stu-id="b5fbc-194">**Use Microsoft Translator for automatic localization**</span></span>
     - <span data-ttu-id="b5fbc-195">**カスタム通知テキスト**: このボックスにカスタム通知テキストを入力します。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-195">**Custom notification text**: Enter the custom notification text in this box.</span></span>

   <span data-ttu-id="b5fbc-196">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-196">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="b5fbc-197">表示された **[レビュー]** ページで、設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-197">On the **Review** page that appears, review your settings.</span></span> <span data-ttu-id="b5fbc-198">各セクションで **[編集]** を選択して、そのセクション内の設定を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-198">You can select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="b5fbc-199">または、**[戻る]** をクリックするか、ウィザードで特定のページを選択します。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-199">Or you can click **Back** or select the specific page in the wizard.</span></span>

   <span data-ttu-id="b5fbc-200">完了したら、**[送信]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-200">When you're finished, click **Submit**.</span></span>

8. <span data-ttu-id="b5fbc-201">表示された [確認]ページで、**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-201">On the confirmation page that appears, click **Done**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-view-safe-links-policies"></a><span data-ttu-id="b5fbc-202">[リンク] Microsoft 365 Defenderを表示するには、セーフポータルを使用します。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-202">Use the Microsoft 365 Defender portal to view Safe Links policies</span></span>

1. <span data-ttu-id="b5fbc-203">このポータルMicrosoft 365 Defender、[ポリシー] **&[** 脅威ポリシー ポリシー] セクションの [リンク \>  \>  \> **] セーフ移動します**。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-203">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Policies** section \> **Safe Links**.</span></span>

2. <span data-ttu-id="b5fbc-204">[リンク **セーフ] ページ** では、リンク ポリシーの一覧に次のプロパティセーフ表示されます。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-204">On the **Safe Links** page, the following properties are displayed in the list of Safe Links policies:</span></span>
   - <span data-ttu-id="b5fbc-205">**名前**</span><span class="sxs-lookup"><span data-stu-id="b5fbc-205">**Name**</span></span>
   - <span data-ttu-id="b5fbc-206">**状態**</span><span class="sxs-lookup"><span data-stu-id="b5fbc-206">**Status**</span></span>
   - <span data-ttu-id="b5fbc-207">**優先度**</span><span class="sxs-lookup"><span data-stu-id="b5fbc-207">**Priority**</span></span>

3. <span data-ttu-id="b5fbc-208">名前をクリックしてポリシーを選択すると、ポリシー設定がフライアウトに表示されます。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-208">When you select a policy by clicking on the name, the policy settings are displayed in a flyout.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-modify-safe-links-policies"></a><span data-ttu-id="b5fbc-209">リンク ポリシーをMicrosoft 365 Defenderするには、セーフ ポータルを使用します。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-209">Use the Microsoft 365 Defender portal to modify Safe Links policies</span></span>

1. <span data-ttu-id="b5fbc-210">このポータルMicrosoft 365 Defender、[ポリシー] **&[** 脅威ポリシー ポリシー] セクションの [リンク \>  \>  \> **] セーフ移動します**。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-210">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Policies** section \> **Safe Links**.</span></span>

2. <span data-ttu-id="b5fbc-211">[リンク **セーフ] ページ** で、名前をクリックして一覧からポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-211">On the **Safe Links** page, select a policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="b5fbc-212">表示されるポリシーの詳細ポップアップで、各セクションで **[編集]** を選択して、そのセクション内の設定を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-212">In the policy details flyout that appears, select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="b5fbc-213">設定の詳細については、この記事の「Microsoft 365 Defenderリンク ポリシーを作成[セーフ](#use-the-microsoft-365-defender-portal-to-create-safe-links-policies)ポータルを使用する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-213">For more information about the settings, see the previous [Use the Microsoft 365 Defender portal to create Safe Links policies](#use-the-microsoft-365-defender-portal-to-create-safe-links-policies) section in this article.</span></span>  

<span data-ttu-id="b5fbc-214">ポリシーを有効または無効にするか、ポリシーの優先順位を設定するには、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-214">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-safe-links-policies"></a><span data-ttu-id="b5fbc-215">リンク ポリシーを有効セーフ無効にする</span><span class="sxs-lookup"><span data-stu-id="b5fbc-215">Enable or disable Safe Links policies</span></span>

1. <span data-ttu-id="b5fbc-216">このポータルMicrosoft 365 Defender、[メール グループ グループ &**ルール** の脅威ポリシー] ページ& [ポリシー] セクションの [リンク] に \>  \>  \>  \> **移動セーフします**。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-216">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Safe Links**.</span></span>

2. <span data-ttu-id="b5fbc-217">[リンク **セーフ] ページ** で、名前をクリックして一覧からポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-217">On the **Safe Links** page, select a policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="b5fbc-218">表示されるポリシーの詳細ポップアップの上部には、以下のいずれかの値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-218">At the top of the policy details flyout that appears, you'll see one of the following values:</span></span>
   - <span data-ttu-id="b5fbc-219">**ポリシー オフ**: ポリシーをオンにするには、![[アイコンをオンにする]](../../media/m365-cc-sc-turn-on-off-icon.png)、**[オンにする]** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-219">**Policy off**: To turn on the policy, click ![Turn on icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn on** .</span></span>
   - <span data-ttu-id="b5fbc-220">**ポリシー オン**: ポリシーをオフにするには、![[アイコンをオフにする]](../../media/m365-cc-sc-turn-on-off-icon.png)、**[オフにする]** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-220">**Policy on**: To turn off the policy, click ![Turn off icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn off**.</span></span>

4. <span data-ttu-id="b5fbc-221">確認ダイアログ ボックスが表示されたら、**[オンにする]** または **[オフにする]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-221">In the confirmation dialog that appears, click **Turn on** or **Turn off**.</span></span>

5. <span data-ttu-id="b5fbc-222">ポリシーの詳細ポップアップで **[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-222">Click **Close** in the policy details flyout.</span></span>

<span data-ttu-id="b5fbc-223">ポリシーのメイン ページに戻ると、ポリシーの **[状態]** の値が **[オン]** または **[オフ]** になります。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-223">Back on the main policy page, the **Status** value of the policy will be **On** or **Off**.</span></span>

### <a name="set-the-priority-of-safe-links-policies"></a><span data-ttu-id="b5fbc-224">リンク ポリシーの優先度セーフ設定する</span><span class="sxs-lookup"><span data-stu-id="b5fbc-224">Set the priority of Safe Links policies</span></span>

<span data-ttu-id="b5fbc-225">既定では、セーフリンクには、作成された順序に基づく優先度が与えられる (新しいポリシーは、以前のポリシーよりも優先度が低くなります)。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-225">By default, Safe Links are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="b5fbc-226">優先度番号が小さいほど、ポリシーの優先度が高くなる (0 が最優先) ことを意味し、ポリシーは優先順位に従って処理されます (優先度の高いポリシーは、優先度の低いポリシーよりも先に処理されます)。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-226">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="b5fbc-227">2つのポリシーが同じ優先順位を持つことはできません。最初のポリシーが適用されると、ポリシーの処理は停止します。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-227">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="b5fbc-228">ポリシーの優先度を変更するには、ポリシーのプロパティで **[優先度を上げる]** または **[優先度を下げる]** をクリックします (Microsoft 365 Defender ポータルの **[優先度]** の数値を直接変更することはできません)。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-228">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Microsoft 365 Defender portal).</span></span> <span data-ttu-id="b5fbc-229">ポリシーの優先度を変更することは、複数のポリシーを所有している場合にのみ意味があります。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-229">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

<span data-ttu-id="b5fbc-230">**注**:</span><span class="sxs-lookup"><span data-stu-id="b5fbc-230">**Note**:</span></span>

- <span data-ttu-id="b5fbc-231">このポータルMicrosoft 365 Defender、リンク ポリシーを作成した後にのみ、セーフポリシーの優先度を変更できます。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-231">In the Microsoft 365 Defender portal, you can only change the priority of the Safe Links policy after you create it.</span></span> <span data-ttu-id="b5fbc-232">PowerShell では、安全なリンク ルールを作成するときに既定の優先度を上書きできます (既存のルールの優先度に影響を与える可能性があります)。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-232">In PowerShell, you can override the default priority when you create the safe links rule (which can affect the priority of existing rules).</span></span>
- <span data-ttu-id="b5fbc-233">セーフリンク ポリシーは、表示順に処理されます (最初のポリシーの **優先度** の値は 0 です)。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-233">Safe Links policies are processed in the order that they're displayed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="b5fbc-234">優先順位と複数のポリシーを評価し適用する方法の詳細については、「[メール保護の優先順位](how-policies-and-protections-are-combined.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-234">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

1. <span data-ttu-id="b5fbc-235">このポータルMicrosoft 365 Defender、[メール グループ グループ &**ルール** の脅威ポリシー] ページ& [ポリシー] セクションの [リンク] に \>  \>  \>  \> **移動セーフします**。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-235">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Safe Links**.</span></span>

2. <span data-ttu-id="b5fbc-236">[リンク **セーフ] ページ** で、名前をクリックして一覧からポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-236">On the **Safe Links** page, select a policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="b5fbc-237">表示されるポリシーの詳細ポップアップの上部には、現在の優先度の値とカスタム ポリシーの数に基づいて、**[優先度を上げる]** または **[優先度を下げる]** が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-237">At the top of the policy details flyout that appears, you'll see **Increase priority** or **Decrease priority** based on the current priority value and the number of custom policies:</span></span>
   - <span data-ttu-id="b5fbc-238">優先度の値が **0** **のポリシー** には、[優先度を下にする]**オプションしか** 使用できません。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-238">The policy with the **Priority** value **0** has only the **Decrease priority** option available.</span></span>
   - <span data-ttu-id="b5fbc-239">優先度の値が最も **低い** ポリシー ( **たとえば、3)** には、[優先度の引き上げ] **オプション** しか使用できません。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-239">The policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** option available.</span></span>
   - <span data-ttu-id="b5fbc-240">3 つ以上のポリシーがある場合、優先度の高い値と最も低い優先度の値の間のポリシーには、[優先度の引き上げ] オプションと [優先度の下 **げ]** の両方 **のオプションがあります** 。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-240">If you have three or more policies, the policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** options available.</span></span>

   <span data-ttu-id="b5fbc-241">![[優先度を上げる] アイコン](../../media/m365-cc-sc-increase-icon.png)、**[優先度を上げる]** の順にクリックするか、または ![[優先度を下げる] アイコン](../../media/m365-cc-sc-decrease-icon.png)、**[優先度を下げる]** の順にクリックして、**優先度** 値を変更します。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-241">Click ![Increase priority icon](../../media/m365-cc-sc-increase-icon.png) **Increase priority** or ![Decrease priority icon](../../media/m365-cc-sc-decrease-icon.png) **Decrease priority** to change the **Priority** value.</span></span>

4. <span data-ttu-id="b5fbc-242">完了したら、ポリシーの詳細ポップアップで **[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-242">When you're finished, click **Close** in the policy details flyout.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-remove-safe-links-policies"></a><span data-ttu-id="b5fbc-243">リンク ポリシーをMicrosoft 365 Defenderするには、セーフ ポータルを使用します。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-243">Use the Microsoft 365 Defender portal to remove Safe Links policies</span></span>

1. <span data-ttu-id="b5fbc-244">このポータルMicrosoft 365 Defender、[メール グループ グループ &**ルール** の脅威ポリシー] ページ& [ポリシー] セクションの [リンク] に \>  \>  \>  \> **移動セーフします**。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-244">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Safe Links**.</span></span>

2. <span data-ttu-id="b5fbc-245">[リンク **セーフ] ページ** で、名前をクリックして一覧からポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-245">On the **Safe Links** page, select a policy from the list by clicking on the name.</span></span> <span data-ttu-id="b5fbc-246">表示されるポリシーの詳細ポップアウトの上部で、![[その他の操作] アイコン](../../media/m365-cc-sc-more-actions-icon.png)、**[その他の操作]** \>、![[ポリシーの削除] アイコン](../../media/m365-cc-sc-delete-icon.png)、**[ポリシーの削除]** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-246">At the top of the policy details flyout that appears, click ![More actions icon](../../media/m365-cc-sc-more-actions-icon.png) **More actions** \> ![Delete policy icon](../../media/m365-cc-sc-delete-icon.png) **Delete policy**.</span></span>

3. <span data-ttu-id="b5fbc-247">確認ダイアログ ボックスが表示されたら、**[はい]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-247">In the confirmation dialog that appears, click **Yes**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies"></a><span data-ttu-id="b5fbc-248">PowerShell Exchange Onlineスタンドアロン EOP PowerShell を使用して、リンク ポリシーセーフ構成する</span><span class="sxs-lookup"><span data-stu-id="b5fbc-248">Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Links policies</span></span>

<span data-ttu-id="b5fbc-249">前に説明したように、セーフリンク ポリシーは、安全なリンク ポリシーと安全なリンク ルールで構成されます。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-249">As previously described, a Safe Links policy consists of a safe links policy and a safe links rule.</span></span>

<span data-ttu-id="b5fbc-250">PowerShell では、安全なリンク ポリシーと安全なリンク ルールの違いが明らかです。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-250">In PowerShell, the difference between safe links policies and safe links rules is apparent.</span></span> <span data-ttu-id="b5fbc-251">安全なリンク ポリシーは **\* 、-SafeLinksPolicy** コマンドレットを使用して管理し **\* 、-SafeLinksRule** コマンドレットを使用して安全なリンク ルールを管理します。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-251">You manage safe links policies by using the **\*-SafeLinksPolicy** cmdlets, and you manage safe links rules by using the **\*-SafeLinksRule** cmdlets.</span></span>

- <span data-ttu-id="b5fbc-252">PowerShell では、安全なリンク ポリシーを最初に作成してから、ルールが適用されるポリシーを識別する安全なリンク ルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-252">In PowerShell, you create the safe links policy first, then you create the safe links rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="b5fbc-253">PowerShell では、安全なリンク ポリシーの設定と安全なリンク ルールを個別に変更します。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-253">In PowerShell, you modify the settings in the safe links policy and the safe links rule separately.</span></span>
- <span data-ttu-id="b5fbc-254">PowerShell から安全なリンク ポリシーを削除しても、対応する安全なリンク ルールは自動的には削除されません。その逆も同様です。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-254">When you remove a safe links policy from PowerShell, the corresponding safe links rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-safe-links-policies"></a><span data-ttu-id="b5fbc-255">PowerShell を使用してリンク ポリシーセーフ作成する</span><span class="sxs-lookup"><span data-stu-id="b5fbc-255">Use PowerShell to create Safe Links policies</span></span>

<span data-ttu-id="b5fbc-256">PowerShell で セーフリンク ポリシーを作成するには、次の 2 つの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-256">Creating a Safe Links policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="b5fbc-257">安全なリンク ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-257">Create the safe links policy.</span></span>
2. <span data-ttu-id="b5fbc-258">ルールが適用される安全なリンク ポリシーを指定する安全なリンク ルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-258">Create the safe links rule that specifies the safe links policy that the rule applies to.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="b5fbc-259">新しいセーフ リンク ルールを作成し、関連付けされていない既存の安全なリンク ポリシーを割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-259">You can create a new safe links rule and assign an existing, unassociated safe links policy to it.</span></span> <span data-ttu-id="b5fbc-260">安全なリンク ルールを複数の安全なリンク ポリシーに関連付けできない。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-260">A safe links rule can't be associated with more than one safe links policy.</span></span>
>
> - <span data-ttu-id="b5fbc-261">ポリシーを作成するまで、PowerShell の新しい安全なリンク ポリシーで、Microsoft 365 Defender ポータルで使用できない次の設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-261">You can configure the following settings on new safe links policies in PowerShell that aren't available in the Microsoft 365 Defender portal until after you create the policy:</span></span>
>   - <span data-ttu-id="b5fbc-262">新しいポリシーを _無効として作成_ します `$false` **(New-SafeLinksRule コマンドレットで有効** )。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-262">Create the new policy as disabled (_Enabled_ `$false` on the **New-SafeLinksRule** cmdlet).</span></span>
>   - <span data-ttu-id="b5fbc-263"> _\<Number\>_ **New-SafeLinksRule** コマンドレットの作成時にポリシーの優先度 (優先度) を設定します。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-263">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-SafeLinksRule** cmdlet).</span></span>
>
> - <span data-ttu-id="b5fbc-264">PowerShell で作成した新しい安全なリンク ポリシーは、ポリシーを安全なリンク ルールに割り当てるMicrosoft 365 Defenderポータルには表示されません。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-264">A new safe links policy that you create in PowerShell isn't visible in the Microsoft 365 Defender portal until you assign the policy to a safe links rule.</span></span>

#### <a name="step-1-use-powershell-to-create-a-safe-links-policy"></a><span data-ttu-id="b5fbc-265">手順 1: PowerShell を使用して安全なリンク ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="b5fbc-265">Step 1: Use PowerShell to create a safe links policy</span></span>

<span data-ttu-id="b5fbc-266">安全なリンク ポリシーを作成するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-266">To create a safe links policy, use this syntax:</span></span>

```PowerShell
New-SafeLinksPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-IsEnabled <$true | $false>] [-EnableSafeLinksForTeams <$true | $false>] [-ScanUrls <$true | $false>] [-DeliverMessageAfterScan <$true | $false>] [-EnableForInternalSenders <$true | $false>] [-DoNotAllowClickThrough <$true | $false>] [-DoNotTrackUserClicks <$true | $false>] [-DoNotRewriteUrls "Entry1","Entry2",..."EntryN"]
```

> [!NOTE]
>
> - <span data-ttu-id="b5fbc-267">_DoNotRewriteUrls_ パラメーターに使用するエントリ構文の詳細については、「次の URL を書き換えない」リストのエントリ構文を [参照してください](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-267">For details about the entry syntax to use for the _DoNotRewriteUrls_ parameter, see [Entry syntax for the "Do not rewrite the following URLs" list](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span></span>
>
> - <span data-ttu-id="b5fbc-268">**Set-SafeLinksPolicy** コマンドレットを使用して既存のセーフ リンク ポリシーを変更するときに _DoNotRewriteUrls_ パラメーターに使用できる追加の構文については、この記事の後半の [「PowerShell](#use-powershell-to-modify-safe-links-policies)を使用して安全なリンク ポリシーを変更する」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-268">For additional syntax that you can use for the _DoNotRewriteUrls_ parameter when you modify existing safe links policies by using the **Set-SafeLinksPolicy** cmdlet, see the [Use PowerShell to modify safe links policies](#use-powershell-to-modify-safe-links-policies) section later in this article.</span></span>

<span data-ttu-id="b5fbc-269">この例では、Contoso All という名前の安全なリンク ポリシーを次の値で作成します。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-269">This example creates a safe links policy named Contoso All with the following values:</span></span>

- <span data-ttu-id="b5fbc-270">電子メール メッセージで URL のスキャンと書き換えを有効にする。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-270">Turn on URL scanning and rewriting in email messages.</span></span>
- <span data-ttu-id="b5fbc-271">[URL のスキャン] を [Teamsオンにする (TAP プレビューのみ)。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-271">Turn on URL scanning in Teams (TAP Preview only).</span></span>
- <span data-ttu-id="b5fbc-272">クリックした URL (ファイルを指すクリックされたリンクを含む) のリアルタイム スキャンを有効にする。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-272">Turn on real-time scanning of clicked URLs, including clicked links that point to files.</span></span>
- <span data-ttu-id="b5fbc-273">メッセージを配信する前に、URL のスキャンが完了するのを待ちます。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-273">Wait for URL scanning to complete before delivering the message.</span></span>
- <span data-ttu-id="b5fbc-274">内部メッセージの URL スキャンと書き換えを有効にする。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-274">Turn on URL scanning and rewriting for internal messages.</span></span>
- <span data-ttu-id="b5fbc-275">セーフ Links 保護に関連するユーザークリックを追跡します _(DoNotTrackUserClicks_ パラメーターは使用していないので、既定値は $false です。つまり、ユーザーのクリックが追跡されます)。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-275">Track user clicks related to Safe Links protection (we aren't using the _DoNotTrackUserClicks_ parameter, and the default value is $false, which means user clicks are tracked).</span></span>
- <span data-ttu-id="b5fbc-276">ユーザーが元の URL をクリックしてクリックを許可しない。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-276">Do not allow users to click through to the original URL.</span></span>

```PowerShell
New-SafeLinksPolicy -Name "Contoso All" -IsEnabled $true -EnableSafeLinksForTeams $true -ScanUrls $true -DeliverMessageAfterScan $true -EnableForInternalSenders $true -DoNotAllowClickThrough $true
```

<span data-ttu-id="b5fbc-277">構文とパラメーターの詳細については [、「New-SafeLinksPolicy」を参照してください](/powershell/module/exchange/new-safelinkspolicy)。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-277">For detailed syntax and parameter information, see [New-SafeLinksPolicy](/powershell/module/exchange/new-safelinkspolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-a-safe-links-rule"></a><span data-ttu-id="b5fbc-278">手順 2: PowerShell を使用して安全なリンク ルールを作成する</span><span class="sxs-lookup"><span data-stu-id="b5fbc-278">Step 2: Use PowerShell to create a safe links rule</span></span>

<span data-ttu-id="b5fbc-279">安全なリンク ルールを作成するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-279">To create a safe links rule, use this syntax:</span></span>

```PowerShell
New-SafeLinksRule -Name "<RuleName>" -SafeLinksPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

<span data-ttu-id="b5fbc-280">この例では、Contoso All という名前の安全なリンク ルールを次の条件で作成します。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-280">This example creates a safe links rule named Contoso All with the following conditions:</span></span>

- <span data-ttu-id="b5fbc-281">ルールは、Contoso All という名前の安全なリンク ポリシーに関連付けられている。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-281">The rule is associated with the safe links policy named Contoso All.</span></span>
- <span data-ttu-id="b5fbc-282">ルールは、ドメイン内のすべての受信者に contoso.com されます。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-282">The rule applies to all recipients in the contoso.com domain.</span></span>
- <span data-ttu-id="b5fbc-283">Priority パラメーターを使用していないので _、既定_ の優先度が使用されます。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-283">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>
- <span data-ttu-id="b5fbc-284">ルールが有効になっています (Enabled パラメーターは使用しませんが、既定値はです `$true` )。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-284">The rule is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>

```powershell
New-SafeLinksRule -Name "Contoso All" -SafeLinksPolicy "Contoso All" -RecipientDomainIs contoso.com
```

<span data-ttu-id="b5fbc-285">構文とパラメーターの詳細については [、「New-SafeLinksRule」を参照してください](/powershell/module/exchange/new-safelinksrule)。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-285">For detailed syntax and parameter information, see [New-SafeLinksRule](/powershell/module/exchange/new-safelinksrule).</span></span>

### <a name="use-powershell-to-view-safe-links-policies"></a><span data-ttu-id="b5fbc-286">PowerShell を使用して安全なリンク ポリシーを表示する</span><span class="sxs-lookup"><span data-stu-id="b5fbc-286">Use PowerShell to view safe links policies</span></span>

<span data-ttu-id="b5fbc-287">既存の安全なリンク ポリシーを表示するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-287">To view existing safe links policies, use the following syntax:</span></span>

```PowerShell
Get-SafeLinksPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="b5fbc-288">この例では、すべての安全なリンク ポリシーの概要一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-288">This example returns a summary list of all safe links policies.</span></span>

```PowerShell
Get-SafeLinksPolicy | Format-Table Name
```

<span data-ttu-id="b5fbc-289">この例では、Contoso Executives という名前の安全なリンク ポリシーの詳細情報を返します。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-289">This example returns detailed information for the safe links policy named Contoso Executives.</span></span>

```PowerShell
Get-SafeLinksPolicy -Identity "Contoso Executives"
```

<span data-ttu-id="b5fbc-290">構文とパラメーターの詳細については [、「Get-SafeLinksPolicy」を参照してください](/powershell/module/exchange/get-safelinkspolicy)。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-290">For detailed syntax and parameter information, see [Get-SafeLinksPolicy](/powershell/module/exchange/get-safelinkspolicy).</span></span>

### <a name="use-powershell-to-view-safe-links-rules"></a><span data-ttu-id="b5fbc-291">PowerShell を使用して安全なリンク ルールを表示する</span><span class="sxs-lookup"><span data-stu-id="b5fbc-291">Use PowerShell to view safe links rules</span></span>

<span data-ttu-id="b5fbc-292">既存のセーフ リンク ルールを表示するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-292">To view existing safe links rules, use the following syntax:</span></span>

```PowerShell
Get-SafeLinksRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="b5fbc-293">この例では、すべての安全なリンク ルールの概要一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-293">This example returns a summary list of all safe links rules.</span></span>

```PowerShell
Get-SafeLinksRule | Format-Table Name,State
```

<span data-ttu-id="b5fbc-294">ルールを有効または無効にしてリストをフィルター処理するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-294">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-SafeLinksRule -State Disabled
```

```PowerShell
Get-SafeLinksRule -State Enabled
```

<span data-ttu-id="b5fbc-295">この例では、Contoso Executives という名前の安全なリンク ルールの詳細情報を返します。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-295">This example returns detailed information for the safe links rule named Contoso Executives.</span></span>

```PowerShell
Get-SafeLinksRule -Identity "Contoso Executives"
```

<span data-ttu-id="b5fbc-296">構文とパラメーターの詳細については [、「Get-SafeLinksRule」を参照してください](/powershell/module/exchange/get-safelinksrule)。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-296">For detailed syntax and parameter information, see [Get-SafeLinksRule](/powershell/module/exchange/get-safelinksrule).</span></span>

### <a name="use-powershell-to-modify-safe-links-policies"></a><span data-ttu-id="b5fbc-297">PowerShell を使用して安全なリンク ポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="b5fbc-297">Use PowerShell to modify safe links policies</span></span>

<span data-ttu-id="b5fbc-298">PowerShell で安全なリンク ポリシーの名前を変更することはできません **(Set-SafeLinksPolicy** コマンドレットには _Name_ パラメーターはありません)。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-298">You can't rename a safe links policy in PowerShell (the **Set-SafeLinksPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="b5fbc-299">ポータルで セーフ リンク ポリシーの名前を変更Microsoft 365 Defender、安全なリンク ルールの名前を変更 _するのみです_。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-299">When you rename a Safe Links policy in the Microsoft 365 Defender portal, you're only renaming the safe links _rule_.</span></span>

<span data-ttu-id="b5fbc-300">PowerShell で安全なリンク ポリシーを変更するための唯一の追加の考慮事項は _、DoNotRewriteUrls_ パラメーターで使用可能な構文です ("次の [URL を](safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)書き換えない" リスト)。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-300">The only additional consideration for modifying safe links policies in PowerShell is the available syntax for the _DoNotRewriteUrls_ parameter (the ["Do not rewrite the following URLs" list](safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)):</span></span>

- <span data-ttu-id="b5fbc-301">既存のエントリを置き換える値を追加するには、次の構文を使用します `"Entry1","Entry2,..."EntryN"` 。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-301">To add values that will replace any existing entries, use the following syntax: `"Entry1","Entry2,..."EntryN"`.</span></span>
- <span data-ttu-id="b5fbc-302">他の既存のエントリに影響を与えることなく値を追加または削除するには、次の構文を使用します。 `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`</span><span class="sxs-lookup"><span data-stu-id="b5fbc-302">To add or remove values without affecting other existing entries, use the following syntax: `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`</span></span>

<span data-ttu-id="b5fbc-303">それ以外の場合は、「手順 [1: PowerShell](#step-1-use-powershell-to-create-a-safe-links-policy) を使用して安全なリンク ポリシーを作成する」のセクションで説明したように、安全なリンク ポリシーを作成するときに同じ設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-303">Otherwise, the same settings are available when you create a safe links policy as described in the [Step 1: Use PowerShell to create a safe links policy](#step-1-use-powershell-to-create-a-safe-links-policy) section earlier in this article.</span></span>

<span data-ttu-id="b5fbc-304">安全なリンク ポリシーを変更するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-304">To modify a safe links policy, use this syntax:</span></span>

```PowerShell
Set-SafeLinksPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="b5fbc-305">構文とパラメーターの詳細については [、「Set-SafeLinksPolicy」を参照してください](/powershell/module/exchange/set-safelinkspolicy)。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-305">For detailed syntax and parameter information, see [Set-SafeLinksPolicy](/powershell/module/exchange/set-safelinkspolicy).</span></span>

### <a name="use-powershell-to-modify-safe-links-rules"></a><span data-ttu-id="b5fbc-306">PowerShell を使用して安全なリンク ルールを変更する</span><span class="sxs-lookup"><span data-stu-id="b5fbc-306">Use PowerShell to modify safe links rules</span></span>

<span data-ttu-id="b5fbc-307">PowerShell で安全なリンク ルールを変更するときに使用できない唯一の設定は、無効なルールを作成できる _Enabled_ パラメーターです。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-307">The only setting that's not available when you modify a safe links rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="b5fbc-308">既存のセーフ リンク ルールを有効または無効にするには、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-308">To enable or disable existing safe links rules, see the next section.</span></span>

<span data-ttu-id="b5fbc-309">それ以外の場合は、「手順 [2: PowerShell](#step-2-use-powershell-to-create-a-safe-links-rule) を使用して安全なリンク ルールを作成する」セクションで説明したように、ルールを作成するときに同じ設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-309">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create a safe links rule](#step-2-use-powershell-to-create-a-safe-links-rule) section earlier in this article.</span></span>

<span data-ttu-id="b5fbc-310">安全なリンク ルールを変更するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-310">To modify a safe links rule, use this syntax:</span></span>

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="b5fbc-311">構文とパラメーターの詳細については [、「Set-SafeLinksRule」を参照してください](/powershell/module/exchange/set-safelinksrule)。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-311">For detailed syntax and parameter information, see [Set-SafeLinksRule](/powershell/module/exchange/set-safelinksrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-safe-links-rules"></a><span data-ttu-id="b5fbc-312">PowerShell を使用して安全なリンク ルールを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="b5fbc-312">Use PowerShell to enable or disable safe links rules</span></span>

<span data-ttu-id="b5fbc-313">PowerShell で安全なリンク ルールを有効または無効にすると、セーフ リンク ポリシー全体 (セーフ リンク ルールと割り当てられた安全なリンク ポリシー) が有効または無効となります。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-313">Enabling or disabling a safe links rule in PowerShell enables or disables the whole Safe Links policy (the safe links rule and the assigned safe links policy).</span></span>

<span data-ttu-id="b5fbc-314">PowerShell で安全なリンク ルールを有効または無効にするには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-314">To enable or disable a safe links rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-SafeLinksRule | Disable-SafeLinksRule> -Identity "<RuleName>"
```

<span data-ttu-id="b5fbc-315">この例では、Marketing Department という名前の安全なリンク ルールを無効にします。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-315">This example disables the safe links rule named Marketing Department.</span></span>

```PowerShell
Disable-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="b5fbc-316">この例では、同じルールを有効化します。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-316">This example enables same rule.</span></span>

```PowerShell
Enable-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="b5fbc-317">構文とパラメーターの詳細については [、「Enable-SafeLinksRule」](/powershell/module/exchange/enable-safelinksrule) および [「Disable-SafeLinksRule」を参照してください](/powershell/module/exchange/disable-safelinksrule)。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-317">For detailed syntax and parameter information, see [Enable-SafeLinksRule](/powershell/module/exchange/enable-safelinksrule) and [Disable-SafeLinksRule](/powershell/module/exchange/disable-safelinksrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-safe-links-rules"></a><span data-ttu-id="b5fbc-318">PowerShell を使用して安全なリンク ルールの優先度を設定する</span><span class="sxs-lookup"><span data-stu-id="b5fbc-318">Use PowerShell to set the priority of safe links rules</span></span>

<span data-ttu-id="b5fbc-p131">ルールに設定できる優先度の最高値値は 0 です。設定できる最低値はルールの数に依存します。たとえば、ルールが五つある場合、使用できる優先度の値は 0 から 4 です。既存の一つのルールの優先度を変更すると、他のルールにも連鎖的な影響が起こりえます。たとえば、カスタム ルールが五つある場合 (優先度 0 から 4) に、一つのルールの優先度を 2 に変更した場合、既存の優先度 2 のルールは優先度 3 に変更され、優先度 3 は優先度 4 に変更されます。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-p131">The highest priority value you can set on a rule is 0. The lowest value you can set depends on the number of rules. For example, if you have five rules, you can use the priority values 0 through 4. Changing the priority of an existing rule can have a cascading effect on other rules. For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="b5fbc-324">PowerShell で安全なリンク ルールの優先度を設定するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-324">To set the priority of a safe links rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="b5fbc-p132">この例では、Marketing Department というルールの優先度を 2 に設定しています。優先度が 2 以下のすべての既存のルールは、優先度が 1 ずつ下がります (優先度番号が 1 ずつ増加します)。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-p132">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-SafeLinksRule -Identity "Marketing Department" -Priority 2
```

> [!NOTE]
> <span data-ttu-id="b5fbc-327">新しいルールを作成するときに優先度を設定するには **、New-SafeLinksRule** コマンドレットの Priority パラメーターを使用します。 </span><span class="sxs-lookup"><span data-stu-id="b5fbc-327">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-SafeLinksRule** cmdlet instead.</span></span>

<span data-ttu-id="b5fbc-328">構文とパラメーターの詳細については [、「Set-SafeLinksRule」を参照してください](/powershell/module/exchange/set-safelinksrule)。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-328">For detailed syntax and parameter information, see [Set-SafeLinksRule](/powershell/module/exchange/set-safelinksrule).</span></span>

### <a name="use-powershell-to-remove-safe-links-policies"></a><span data-ttu-id="b5fbc-329">PowerShell を使用して安全なリンク ポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="b5fbc-329">Use PowerShell to remove safe links policies</span></span>

<span data-ttu-id="b5fbc-330">PowerShell を使用して安全なリンク ポリシーを削除しても、対応する安全なリンク ルールは削除されません。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-330">When you use PowerShell to remove a safe links policy, the corresponding safe links rule isn't removed.</span></span>

<span data-ttu-id="b5fbc-331">PowerShell で安全なリンク ポリシーを削除するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-331">To remove a safe links policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeLinksPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="b5fbc-332">この例では、Marketing Department という名前の安全なリンク ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-332">This example removes the safe links policy named Marketing Department.</span></span>

```PowerShell
Remove-SafeLinksPolicy -Identity "Marketing Department"
```

<span data-ttu-id="b5fbc-333">構文とパラメーターの詳細については [、「Remove-SafeLinksPolicy」を参照してください](/powershell/module/exchange/remove-safelinkspolicy)。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-333">For detailed syntax and parameter information, see [Remove-SafeLinksPolicy](/powershell/module/exchange/remove-safelinkspolicy).</span></span>

### <a name="use-powershell-to-remove-safe-links-rules"></a><span data-ttu-id="b5fbc-334">PowerShell を使用して安全なリンク ルールを削除する</span><span class="sxs-lookup"><span data-stu-id="b5fbc-334">Use PowerShell to remove safe links rules</span></span>

<span data-ttu-id="b5fbc-335">PowerShell を使用して安全なリンク ルールを削除しても、対応する安全なリンク ポリシーは削除されません。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-335">When you use PowerShell to remove a safe links rule, the corresponding safe links policy isn't removed.</span></span>

<span data-ttu-id="b5fbc-336">PowerShell で安全なリンク ルールを削除するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-336">To remove a safe links rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeLinksRule -Identity "<PolicyName>"
```

<span data-ttu-id="b5fbc-337">この例では、Marketing Department という名前の安全なリンク ルールを削除します。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-337">This example removes the safe links rule named Marketing Department.</span></span>

```PowerShell
Remove-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="b5fbc-338">構文とパラメーターの詳細については [、「Remove-SafeLinksRule」を参照してください](/powershell/module/exchange/remove-safelinksrule)。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-338">For detailed syntax and parameter information, see [Remove-SafeLinksRule](/powershell/module/exchange/remove-safelinksrule).</span></span>

<span data-ttu-id="b5fbc-339">リンクがメッセージセーフ確認するには、使用可能な Microsoft Defender のレポートをOffice 365してください。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-339">To verify that Safe Links is scanning messages, check the available Microsoft Defender for Office 365 reports.</span></span> <span data-ttu-id="b5fbc-340">詳細については、「View [reports for Defender for Office 365」](view-reports-for-mdo.md)および「Use Explorer in the [Microsoft 365 Defender ポータル」を参照してください](threat-explorer.md)。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-340">For more information, see [View reports for Defender for Office 365](view-reports-for-mdo.md) and [Use Explorer in the Microsoft 365 Defender portal](threat-explorer.md).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="b5fbc-341">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="b5fbc-341">How do you know these procedures worked?</span></span>

<span data-ttu-id="b5fbc-342">リンク ポリシーが正常に作成、変更、または削除されたことを確認するには、セーフ手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-342">To verify that you've successfully created, modified, or removed Safe Links policies, do any of the following steps:</span></span>

- <span data-ttu-id="b5fbc-343">このポータルMicrosoft 365 Defender、[ポリシー] & **[** リンク] に \>  \> **セーフします**。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-343">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat policies** \> **Safe Links**.</span></span> <span data-ttu-id="b5fbc-344">ポリシー、その状態の値、および **優先度** の値の一覧を **確認** します。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-344">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="b5fbc-345">詳細を表示するには、一覧からポリシーを選択し、詳細をフライアウトで表示します。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-345">To view more details, select the policy from the list, and view the details in the fly out.</span></span>

- <span data-ttu-id="b5fbc-346">PowerShell Exchange Onlineまたは PowerShell Exchange Online Protectionで、ポリシーまたはルールの名前に置き換え、次のコマンドを実行し、 \<Name\> 設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="b5fbc-346">In Exchange Online PowerShell or Exchange Online Protection PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-SafeLinksPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-SafeLinksRule -Identity "<Name>"
  ```
