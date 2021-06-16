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
ms.openlocfilehash: 40ae52cfce53c3fa14253a94e72f1a2bccda9a86
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/14/2021
ms.locfileid: "52929829"
---
# <a name="set-up-safe-links-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="bac86-103">Microsoft Defender セーフのリンク ポリシーを設定Office 365</span><span class="sxs-lookup"><span data-stu-id="bac86-103">Set up Safe Links policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="bac86-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="bac86-104">**Applies to**</span></span>
- [<span data-ttu-id="bac86-105">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="bac86-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="bac86-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bac86-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> <span data-ttu-id="bac86-107">この記事は、[Microsoft Defender for Office 365](defender-for-office-365.md) をご利用の法人のお客様を対象としています。</span><span class="sxs-lookup"><span data-stu-id="bac86-107">This article is intended for business customers who have [Microsoft Defender for Office 365](defender-for-office-365.md).</span></span> <span data-ttu-id="bac86-108">セーフリンクに関する情報を探しているホーム ユーザーの場合は、「Advanced [Outlook Outlook.com セキュリティ」を参照してください](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)。</span><span class="sxs-lookup"><span data-stu-id="bac86-108">If you are a home user looking for information about Safelinks in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="bac86-109">セーフ[リンクは、Microsoft Defender for Office 365](defender-for-office-365.md)の機能で、メール フロー内の受信電子メール メッセージの URL スキャン、および電子メール メッセージ内の URL とリンクのクリック検証の時間を提供します。</span><span class="sxs-lookup"><span data-stu-id="bac86-109">Safe Links is a feature in [Microsoft Defender for Office 365](defender-for-office-365.md) that provides URL scanning of inbound email messages in mail flow, and time of click verification of URLs and links in email messages and in other locations.</span></span> <span data-ttu-id="bac86-110">詳細については[、「Microsoft Defender セーフリンク」を参照Office 365。](safe-links.md)</span><span class="sxs-lookup"><span data-stu-id="bac86-110">For more information, see [Safe Links in Microsoft Defender for Office 365](safe-links.md).</span></span>

<span data-ttu-id="bac86-111">リンク ポリシーに組み込みまたは既定セーフはありません。</span><span class="sxs-lookup"><span data-stu-id="bac86-111">There's no built-in or default Safe Links policy.</span></span> <span data-ttu-id="bac86-112">URL のセーフを取得するには、この記事で説明するように 1 つ以上の セーフリンク ポリシーを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bac86-112">To get Safe Links scanning of URLs, you need to create one or more Safe Links policies as described in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="bac86-113">リンクの保護のグローバル設定は、セーフリンク ポリシー以外セーフ構成します。</span><span class="sxs-lookup"><span data-stu-id="bac86-113">You configure the global settings for Safe Links protection **outside** of Safe Links policies.</span></span> <span data-ttu-id="bac86-114">手順については、「Microsoft Defender for セーフリンクのグローバル設定を構成する[」を参照Office 365。](configure-global-settings-for-safe-links.md)</span><span class="sxs-lookup"><span data-stu-id="bac86-114">For instructions, see [Configure global settings for Safe Links in Microsoft Defender for Office 365](configure-global-settings-for-safe-links.md).</span></span>

<span data-ttu-id="bac86-115">セーフ Links ポリシーは、Microsoft 365 Defender ポータルまたは PowerShell (Exchange Online PowerShell で、Exchange Online のメールボックスを持つ対象の Microsoft 365 組織、Exchange Online メールボックスのない組織のスタンドアロン EOP PowerShell、microsoft Defender for Office 365 アドオン サブスクリプション) で構成できます。</span><span class="sxs-lookup"><span data-stu-id="bac86-115">You can configure Safe Links policies in the Microsoft 365 Defender portal or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Microsoft Defender for Office 365 add-on subscriptions).</span></span>

<span data-ttu-id="bac86-116">リンク ポリシーの基本的なセーフは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="bac86-116">The basic elements of a Safe Links policy are:</span></span>

- <span data-ttu-id="bac86-117">安全なリンク **ポリシー:** セーフ リンク保護を有効にし、リアルタイム URL スキャンを有効にし、メッセージを配信する前にリアルタイム スキャンが完了するのを待つかどうかを指定し、内部メッセージのスキャンをオンにし、URL のユーザークリックを追跡するかどうかを指定し、ユーザーが元の URL へのトラフをクリックできるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="bac86-117">**The safe links policy**: Turn on Safe Links protection, turn on real-time URL scanning, specify whether to wait for real-time scanning to complete before delivering the message, turn on scanning for internal messages, specify whether to track user clicks on URLs, and specify whether to allow users to click trough to the original URL.</span></span>
- <span data-ttu-id="bac86-118">**安全なリンクルール**: 優先度と受信者のフィルター (ポリシーが適用されるユーザー) を指定します。</span><span class="sxs-lookup"><span data-stu-id="bac86-118">**The safe links rule**: Specifies the priority and recipient filters (who the policy applies to).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bac86-119">管理者は、SafeLinks の異なる構成設定を検討する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bac86-119">Admins should consider the different configuration settings for SafeLinks.</span></span> <span data-ttu-id="bac86-120">使用できるオプションの 1 つは、ユーザー識別可能な情報を SafeLinks に含める方法です。</span><span class="sxs-lookup"><span data-stu-id="bac86-120">One of the available options is to include user identifiable information in SafeLinks.</span></span> <span data-ttu-id="bac86-121">この機能により *、セキュリティ Ops チームは* 、潜在的なユーザー侵害を調査し、是正措置を取り、コストのかかる侵害を制限できます。</span><span class="sxs-lookup"><span data-stu-id="bac86-121">This feature enables *Security Ops teams* to investigate potential user compromise, take corrective action, and limit costly breaches.</span></span>

<span data-ttu-id="bac86-122">これらの 2 つの要素の違いは、Defender ポータルでリンク セーフポリシーを管理Microsoft 365ではありません。</span><span class="sxs-lookup"><span data-stu-id="bac86-122">The difference between these two elements isn't obvious when you manage Safe Links polices in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="bac86-123">セーフ リンク ポリシーを作成するときに、両方に同じ名前を使用して、安全なリンク ルールと関連付けられた安全なリンク ポリシーを同時に作成します。</span><span class="sxs-lookup"><span data-stu-id="bac86-123">When you create a Safe Links policy, you're actually creating a safe links rule and the associated safe links policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="bac86-124">リンク ポリシーを変更セーフ、名前、優先度、有効または無効、および受信者フィルターに関連する設定によって、安全なリンク ルールが変更されます。</span><span class="sxs-lookup"><span data-stu-id="bac86-124">When you modify a Safe Links policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the safe links rule.</span></span> <span data-ttu-id="bac86-125">その他の設定はすべて、関連付けられたセーフ リンク ポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="bac86-125">All other settings modify the associated safe links policy.</span></span>
- <span data-ttu-id="bac86-126">リンク ポリシーを削除セーフ、セーフ リンク ルールと関連付けられたセーフ リンク ポリシーが削除されます。</span><span class="sxs-lookup"><span data-stu-id="bac86-126">When you remove a Safe Links policy, the safe links rule and the associated safe links policy are removed.</span></span>

<span data-ttu-id="bac86-127">Exchange Online PowerShell またはスタンドアロン EOP PowerShell では、ポリシーとルールを個別に管理します。</span><span class="sxs-lookup"><span data-stu-id="bac86-127">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="bac86-128">詳細については、この記事の後半Exchange Online「PowerShell またはスタンドアロン[EOP PowerShell](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies)を使用して セーフリンク ポリシーを構成する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bac86-128">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Links policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) section later in this article.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="bac86-129">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="bac86-129">What do you need to know before you begin?</span></span>

- <span data-ttu-id="bac86-130"><https://security.microsoft.com/> で Microsoft 365 Defender ポータルを開きます。</span><span class="sxs-lookup"><span data-stu-id="bac86-130">You open the Microsoft 365 Defender portal at <https://security.microsoft.com/>.</span></span> <span data-ttu-id="bac86-131">[リンク] ページに直接 **移動セーフを** 使用します <https://security.microsoft.com/safelinksv2> 。</span><span class="sxs-lookup"><span data-stu-id="bac86-131">To go directly to the **Safe Links** page, use <https://security.microsoft.com/safelinksv2>.</span></span>

- <span data-ttu-id="bac86-132">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bac86-132">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="bac86-133">スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bac86-133">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="bac86-134">この記事の手順を実行するには、アクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="bac86-134">You need to be assigned permissions before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="bac86-135">セーフ リンク ポリシーを作成、変更、および削除するには、Microsoft 365 Defender ポータルの組織の管理またはセキュリティ管理者の役割グループのメンバーであり、Exchange Online の組織の管理役割グループのメンバーである必要があります。 </span><span class="sxs-lookup"><span data-stu-id="bac86-135">To create, modify, and delete Safe Links policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Microsoft 365 Defender portal **and** a member of the **Organization Management** role group in Exchange Online.</span></span>
  - <span data-ttu-id="bac86-136">リンク ポリシーへの読み取りセーフアクセスするには、グローバル リーダーまたはセキュリティ リーダーの役割グループのメンバー **である** 必要があります。</span><span class="sxs-lookup"><span data-stu-id="bac86-136">For read-only access to Safe Links policies, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="bac86-137">詳細については、「Microsoft 365 [Defender](permissions-in-the-security-and-compliance-center.md)ポータルのアクセス許可」および「Exchange Online」[を参照してください](/exchange/permissions-exo/permissions-exo)。</span><span class="sxs-lookup"><span data-stu-id="bac86-137">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-in-the-security-and-compliance-center.md) and [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  > 
  > - <span data-ttu-id="bac86-138">Microsoft 365 管理センターの対応する Azure Active Directory ロールにユーザーを追加すると、Microsoft 365 Defender ポータルで必要なアクセス許可と、Microsoft 365の他の機能に対するアクセス許可がユーザーに付与されます。</span><span class="sxs-lookup"><span data-stu-id="bac86-138">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="bac86-139">詳細については、「[管理者の役割について](../../admin/add-users/about-admin-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bac86-139">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  <span data-ttu-id="bac86-140">.</span><span class="sxs-lookup"><span data-stu-id="bac86-140">.</span></span> <span data-ttu-id="bac86-141">- ビュー **専用の組織の管理** 役割グループ [](/Exchange/permissions-exo/permissions-exo#role-groups)は、Exchange Online機能への読み取り専用アクセスも提供します。</span><span class="sxs-lookup"><span data-stu-id="bac86-141">- The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="bac86-142">リンク ポリシーの推奨設定についてはセーフリンク ポリシー[のセーフを参照してください](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings)。</span><span class="sxs-lookup"><span data-stu-id="bac86-142">For our recommended settings for Safe Links policies, see [Safe Links policy settings](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings).</span></span>

- <span data-ttu-id="bac86-143">新しいポリシーまたは更新されたポリシーを適用するには、最大 30 分かかります。</span><span class="sxs-lookup"><span data-stu-id="bac86-143">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="bac86-144">[新しい機能は、Microsoft Defender](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365)に継続的に追加Office 365。</span><span class="sxs-lookup"><span data-stu-id="bac86-144">[New features are continually being added to Microsoft Defender for Office 365](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="bac86-145">新しい機能が追加された場合、既存のリンク ポリシーを調整するセーフがあります。</span><span class="sxs-lookup"><span data-stu-id="bac86-145">As new features are added, you may need to make adjustments to your existing Safe Links policies.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-create-safe-links-policies"></a><span data-ttu-id="bac86-146">Defender ポータルMicrosoft 365を使用して、リンク ポリシーセーフ作成する</span><span class="sxs-lookup"><span data-stu-id="bac86-146">Use the Microsoft 365 Defender portal to create Safe Links policies</span></span>

<span data-ttu-id="bac86-147">Microsoft 365 Defender ポータルでカスタム セーフ リンク ポリシーを作成すると、両方に同じ名前を使用して、安全なリンク ルールと関連付けられた安全なリンク ポリシーが同時に作成されます。</span><span class="sxs-lookup"><span data-stu-id="bac86-147">Creating a custom Safe Links policy in the Microsoft 365 Defender portal creates the safe links rule and the associated safe links policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="bac86-148">[Defender Microsoft 365] ポータルで、[ポリシー] **&[** 脅威ポリシー] セーフリンク] \>  \> **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="bac86-148">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Safe Links**.</span></span>

2. <span data-ttu-id="bac86-149">[リンクの **セーフ] ページで、[** 作成] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="bac86-149">On the **Safe Links** page, click **Create**.</span></span>

3. <span data-ttu-id="bac86-150">[**新しいリンクセーフ] ポリシー ウィザードが** 開きます。</span><span class="sxs-lookup"><span data-stu-id="bac86-150">The **New Safe Links policy** wizard opens.</span></span> <span data-ttu-id="bac86-151">[ポリシーに **名前を付け] ページ** で、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="bac86-151">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="bac86-152">**[名前]**: わかりやすい一意のポリシー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="bac86-152">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="bac86-153">**[説明]**: ポリシーについての説明を入力します (オプション)。</span><span class="sxs-lookup"><span data-stu-id="bac86-153">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="bac86-154">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bac86-154">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="bac86-155">表示される **[設定]** ページで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="bac86-155">On the **Settings** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="bac86-156">**メッセージ内の不明な潜在的に** 悪意のある URL のアクションを選択します:[**オン**] を選択して、セーフリンク保護を有効にします。</span><span class="sxs-lookup"><span data-stu-id="bac86-156">**Select the action for unknown potentially malicious URLs in messages**: Select **On** to enable Safe Links protection for links in email messages.</span></span>

   - <span data-ttu-id="bac86-157">**[リンク内の不明な** URL または潜在的に悪意のある URLのアクションをMicrosoft Teams: [オン] を選択して、セーフ リンクの保護を有効Teams。</span><span class="sxs-lookup"><span data-stu-id="bac86-157">**Select the action for unknown or potentially malicious URLs within Microsoft Teams**: Select **On** to enable Safe Links protection for links in Teams.</span></span>

   - <span data-ttu-id="bac86-158">**ファイルを指す** 疑わしいリンクやリンクに対してリアルタイム URL スキャンを適用する: この設定を選択すると、電子メール メッセージ内のリンクをリアルタイムでスキャンできます。</span><span class="sxs-lookup"><span data-stu-id="bac86-158">**Apply real-time URL scanning for suspicious links and links that point to files**: Select this setting to enable real-time scanning of links in email messages.</span></span>

   - <span data-ttu-id="bac86-159">**メッセージを配信する前** に URL のスキャンが完了するのを待つ: この設定を選択すると、メッセージを配信する前にリアルタイムの URL スキャンが完了するのを待ちます。</span><span class="sxs-lookup"><span data-stu-id="bac86-159">**Wait for URL scanning to complete before delivering the message**: Select this setting to wait for real-time URL scanning to complete before delivering the message.</span></span>

   - <span data-ttu-id="bac86-160">**[セーフ** 組織内で送信された電子メール メッセージへのリンクを適用する: この設定を選択して、セーフ リンク ポリシーを内部送信者と内部受信者の間のメッセージに適用します。</span><span class="sxs-lookup"><span data-stu-id="bac86-160">**Apply Safe Links to email messages sent within the organization**: Select this setting to apply the Safe Links policy to messages between internal senders and internal recipients.</span></span>

   - <span data-ttu-id="bac86-161">**ユーザーのクリックを追跡しない**: この設定を選択しないままにして、電子メール メッセージ内の URL を追跡するユーザーのクリックを有効にします。</span><span class="sxs-lookup"><span data-stu-id="bac86-161">**Do not track user clicks**: Leave this setting unselected to enable the tracking user clicks on URLs in email messages.</span></span>

   - <span data-ttu-id="bac86-162">**ユーザーに元の URL** へのクリックを許可しない : この設定を選択すると、警告ページ内の元の URL へのユーザーのクリックが [ブロックされます](safe-links.md#warning-pages-from-safe-links)。</span><span class="sxs-lookup"><span data-stu-id="bac86-162">**Do not allow users to click through to original URL**: Select this setting to block users from clicking through to the original URL in [warning pages](safe-links.md#warning-pages-from-safe-links).</span></span>

   - <span data-ttu-id="bac86-163">**次の URL を書き換えない**: 指定された URL にアクセスし、それ以外の場合はリンクによってブロックセーフします。</span><span class="sxs-lookup"><span data-stu-id="bac86-163">**Do not rewrite the following URLs**: Allows access the specified URLs that would otherwise be blocked by Safe Links.</span></span>

     <span data-ttu-id="bac86-164">ボックスに、必要な URL または値を入力し、 をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bac86-164">In the box, type the URL or value that you want, and then click</span></span> ![[ボタンの追加] アイコン](../../media/ITPro-EAC-AddIcon.png)<span data-ttu-id="bac86-166">.</span><span class="sxs-lookup"><span data-stu-id="bac86-166">.</span></span>

     <span data-ttu-id="bac86-167">既存のエントリを削除するには、そのエントリを選択して、</span><span class="sxs-lookup"><span data-stu-id="bac86-167">To remove an existing entry, select it and then click</span></span> ![[削除] ボタン アイコン](../../media/ITPro-EAC-DeleteIcon.png)<span data-ttu-id="bac86-169">.</span><span class="sxs-lookup"><span data-stu-id="bac86-169">.</span></span>

     <span data-ttu-id="bac86-170">エントリの構文については、「次の URL を書き換えない」リストの Entry 構文 [を参照してください](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)。</span><span class="sxs-lookup"><span data-stu-id="bac86-170">For entry syntax, see [Entry syntax for the "Do not rewrite the following URLs" list](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span></span>

   <span data-ttu-id="bac86-171">これらの設定の詳細については、「電子メール[](safe-links.md#safe-links-settings-for-email-messages)メッセージセーフリンクの設定」および「セーフリンクの設定」[を参照](safe-links.md#safe-links-settings-for-microsoft-teams)Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="bac86-171">For detailed information about these settings, see [Safe Links settings for email messages](safe-links.md#safe-links-settings-for-email-messages) and [Safe Links settings for Microsoft Teams](safe-links.md#safe-links-settings-for-microsoft-teams).</span></span>

   <span data-ttu-id="bac86-172">Standard および Strict ポリシー設定の推奨値の詳細については、「リンク[ポリシー設定セーフを参照してください](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings)。</span><span class="sxs-lookup"><span data-stu-id="bac86-172">For more the recommended values for Standard and Strict policy settings, see [Safe Links policy settings](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings).</span></span>

   <span data-ttu-id="bac86-173">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bac86-173">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="bac86-174">表示される **[適用先]** ページで、ポリシーが適用される内部受信者を特定します。</span><span class="sxs-lookup"><span data-stu-id="bac86-174">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="bac86-175">各条件や例外は 1 回しか使用できませんが、条件や例外には複数の値を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="bac86-175">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="bac86-176">同じ条件や例外に複数の値がある場合、OR ロジック (たとえば、_\<recipient1\>_ または _\<recipient2\>_) が適用されます。</span><span class="sxs-lookup"><span data-stu-id="bac86-176">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="bac86-177">a別の条件や例外がある場合は AND ロジック (たとえば、_\<recipient1\>_ かつ _\<member of group 1\>_) が適用されます。</span><span class="sxs-lookup"><span data-stu-id="bac86-177">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="bac86-178">[条件 **の追加] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="bac86-178">Click **Add a condition**.</span></span> <span data-ttu-id="bac86-179">表示されるドロップダウンで、[適用する場合] で条件 **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="bac86-179">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="bac86-180">**受信者は:** 組織内の 1 つ以上のメールボックス、メール ユーザー、またはメール連絡先を指定します。</span><span class="sxs-lookup"><span data-stu-id="bac86-180">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="bac86-181">**受信者は: のメンバーです**。組織内の 1 つ以上のグループを指定します。</span><span class="sxs-lookup"><span data-stu-id="bac86-181">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="bac86-182">**[受信者のドメインが次の値である]**: 組織内で構成済みの 1 つ以上の承認済みドメイン内の受信者を指定します。</span><span class="sxs-lookup"><span data-stu-id="bac86-182">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in your organization.</span></span>

   <span data-ttu-id="bac86-183">条件を選択すると、対応するドロップダウンが [Any of **these] ボックスと一緒に表示** されます。</span><span class="sxs-lookup"><span data-stu-id="bac86-183">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="bac86-184">ボックス内をクリックし、値の一覧をスクロールして選択します。</span><span class="sxs-lookup"><span data-stu-id="bac86-184">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="bac86-185">ボックス内をクリックし、入力を開始してリストをフィルター処理し、値を選択します。</span><span class="sxs-lookup"><span data-stu-id="bac86-185">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="bac86-186">追加の値を追加するには、ボックス内の空の領域をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bac86-186">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="bac86-187">個々のエントリを削除するには、値 **の [削除]** ![ ](../../media/scc-remove-icon.png) アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="bac86-187">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="bac86-188">条件全体を削除するには、条件 **の [削除]** ![ ](../../media/scc-remove-icon.png) アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="bac86-188">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="bac86-189">追加の条件を追加するには、[条件の追加] **をクリックし** 、[適用する場合] で残りの値 **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="bac86-189">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="bac86-190">例外を追加するには、[条件の追加] **をクリックし** 、[条件を除く] で例外 **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="bac86-190">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="bac86-191">設定と動作は、条件とまったく同じです。</span><span class="sxs-lookup"><span data-stu-id="bac86-191">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="bac86-192">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bac86-192">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="bac86-193">表示される **[設定の確認]** ページで、設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="bac86-193">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="bac86-194">各設定で **[編集]** をクリックして変更できます。</span><span class="sxs-lookup"><span data-stu-id="bac86-194">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="bac86-195">完了したら、 **[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bac86-195">When you're finished, click **Finish**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-view-safe-links-policies"></a><span data-ttu-id="bac86-196">Defender ポータルMicrosoft 365を使用して、リンク ポリシーセーフ表示する</span><span class="sxs-lookup"><span data-stu-id="bac86-196">Use the Microsoft 365 Defender portal to view Safe Links policies</span></span>

1. <span data-ttu-id="bac86-197">[Defender Microsoft 365] ポータルで、[ポリシー] **&[** 脅威ポリシー] セーフリンク] \>  \> **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="bac86-197">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Safe Links**.</span></span>

2. <span data-ttu-id="bac86-198">[リンク **セーフ] ページ** で、一覧からポリシーを選択してクリックします (チェック ボックスをオンにしない)。</span><span class="sxs-lookup"><span data-stu-id="bac86-198">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

   <span data-ttu-id="bac86-199">ポリシーの詳細がフライアウトに表示される</span><span class="sxs-lookup"><span data-stu-id="bac86-199">The policy details appear in a fly out</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-modify-safe-links-policies"></a><span data-ttu-id="bac86-200">Defender ポータルをMicrosoft 365して、リンク ポリシーセーフ変更する</span><span class="sxs-lookup"><span data-stu-id="bac86-200">Use the Microsoft 365 Defender portal to modify Safe Links policies</span></span>

1. <span data-ttu-id="bac86-201">Defender ポータルMicrosoft 365に **移動し、[** ポリシー] &脅威ポリシーとリンクセーフ \>  \> **します**。</span><span class="sxs-lookup"><span data-stu-id="bac86-201">In the Microsoft 365 Defender portal, go to \***Policies & rules** \> **Threat Policies** \> **Safe Links**.</span></span>

2. <span data-ttu-id="bac86-202">[リンク **セーフ] ページ** で、一覧からポリシーを選択してクリックします (チェック ボックスをオンにしない)。</span><span class="sxs-lookup"><span data-stu-id="bac86-202">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="bac86-203">表示されるポリシーの詳細が表示されたら、[ポリシーの編集] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="bac86-203">In the policy details fly out that appears, click **Edit policy**.</span></span>

<span data-ttu-id="bac86-204">表示されるフライアウトで使用可能な設定は、「Microsoft 365 Defender ポータルを使用してリンク ポリシーを作成する」セクションセーフ[同](#use-the-microsoft-365-defender-portal-to-create-safe-links-policies)じです。</span><span class="sxs-lookup"><span data-stu-id="bac86-204">The available settings in the fly out that appears are identical to those described in the [Use the Microsoft 365 Defender portal to create Safe Links policies](#use-the-microsoft-365-defender-portal-to-create-safe-links-policies) section.</span></span>

<span data-ttu-id="bac86-205">ポリシーを有効または無効にするか、ポリシーの優先順位を設定するには、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="bac86-205">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-safe-links-policies"></a><span data-ttu-id="bac86-206">リンク ポリシーを有効セーフ無効にする</span><span class="sxs-lookup"><span data-stu-id="bac86-206">Enable or disable Safe Links policies</span></span>

1. <span data-ttu-id="bac86-207">[Defender Microsoft 365] ポータルで、[ポリシー] **&[** 脅威ポリシー] セーフリンク] \>  \> **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="bac86-207">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Safe Links**.</span></span>

2. <span data-ttu-id="bac86-208">[状態] 列の値 **に注意** してください。</span><span class="sxs-lookup"><span data-stu-id="bac86-208">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="bac86-209">ポリシーを無効にするには、左に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="bac86-209">Move the toggle to the left to disable the policy:</span></span> ![ポリシーをオフにする](../../media/scc-toggle-off.png)<span data-ttu-id="bac86-211">.</span><span class="sxs-lookup"><span data-stu-id="bac86-211">.</span></span>

   - <span data-ttu-id="bac86-212">ポリシーを有効にするには、右に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="bac86-212">Move the toggle to the right to enable the policy:</span></span> ![ポリシーを有効にする](../../media/scc-toggle-on.png)<span data-ttu-id="bac86-214">.</span><span class="sxs-lookup"><span data-stu-id="bac86-214">.</span></span>

### <a name="set-the-priority-of-safe-links-policies"></a><span data-ttu-id="bac86-215">リンク ポリシーの優先度セーフ設定する</span><span class="sxs-lookup"><span data-stu-id="bac86-215">Set the priority of Safe Links policies</span></span>

<span data-ttu-id="bac86-216">既定では、セーフリンク ポリシーには、作成された順序に基づく優先度が与えられる (新しいポリシーは、以前のポリシーよりも優先度が低くなります)。</span><span class="sxs-lookup"><span data-stu-id="bac86-216">By default, Safe Links policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="bac86-217">優先度番号が小さいほど、ポリシーの優先度が高くなる (0 が最優先) ことを意味し、ポリシーは優先順位に従って処理されます (優先度の高いポリシーは、優先度の低いポリシーよりも先に処理されます)。</span><span class="sxs-lookup"><span data-stu-id="bac86-217">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="bac86-218">2つのポリシーが同じ優先順位を持つことはできません。最初のポリシーが適用されると、ポリシーの処理は停止します。</span><span class="sxs-lookup"><span data-stu-id="bac86-218">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="bac86-219">優先順位と複数のポリシーを評価し適用する方法の詳細については、「[メール保護の優先順位](how-policies-and-protections-are-combined.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bac86-219">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="bac86-220">セーフリンク ポリシーは、処理された順序で表示されます (最初のポリシーの **優先度** の値は 0 です)。</span><span class="sxs-lookup"><span data-stu-id="bac86-220">Safe Links policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span>

> [!NOTE]
> <span data-ttu-id="bac86-221">Defender ポータルMicrosoft 365、ポリシーを作成した後にのみ、セーフリンク ポリシーの優先度を変更できます。</span><span class="sxs-lookup"><span data-stu-id="bac86-221">In the Microsoft 365 Defender portal, you can only change the priority of the Safe Links policy after you create it.</span></span> <span data-ttu-id="bac86-222">PowerShell では、安全なリンク ルールを作成するときに既定の優先度を上書きできます (既存のルールの優先度に影響を与える可能性があります)。</span><span class="sxs-lookup"><span data-stu-id="bac86-222">In PowerShell, you can override the default priority when you create the safe links rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="bac86-223">ポリシーの優先度を変更するには、リスト内でポリシーを上または下に移動します (ポリシー Defender ポータルの優先度Microsoft 365することはできません)。</span><span class="sxs-lookup"><span data-stu-id="bac86-223">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Microsoft 365 Defender portal).</span></span>

1. <span data-ttu-id="bac86-224">[Defender Microsoft 365] ポータルで、[ポリシー] **&[** 脅威ポリシー] セーフリンク] \>  \> **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="bac86-224">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Safe Links**.</span></span>

2. <span data-ttu-id="bac86-225">[リンク **セーフ] ページ** で、一覧からポリシーを選択してクリックします (チェック ボックスをオンにしない)。</span><span class="sxs-lookup"><span data-stu-id="bac86-225">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="bac86-226">表示されるポリシーの詳細が表示されたら、使用可能な優先度ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="bac86-226">In the policy details fly out that appears, click the available priority button:</span></span>

   - <span data-ttu-id="bac86-227">優先度セーフ **0** の [リンク] ポリシーには、[優先度の下がる]**ボタンのみを** 使用できます。</span><span class="sxs-lookup"><span data-stu-id="bac86-227">The Safe Links policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="bac86-228">[セーフの優先度] の値が最も低い [リンク] ポリシー (**たとえば、3)** には、[優先度の引き上げ]**ボタンだけが** 使用できます。</span><span class="sxs-lookup"><span data-stu-id="bac86-228">The Safe Links policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="bac86-229">リンク ポリシーが 3 つ以上セーフ場合、優先度の高い値と最も低い優先度の値の間のポリシーには、[優先度の引き上げ] ボタンと [優先度の下げ] ボタンの **両方があります。**</span><span class="sxs-lookup"><span data-stu-id="bac86-229">If you have three or more Safe Links policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="bac86-230">[優先度 **の増加] または** **[優先度の下げ** ] をクリックして、 **優先度の値を変更** します。</span><span class="sxs-lookup"><span data-stu-id="bac86-230">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="bac86-231">完了したら、**[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bac86-231">When you're finished, click **Close**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-remove-safe-links-policies"></a><span data-ttu-id="bac86-232">Defender ポータルMicrosoft 365を使用して、リンク ポリシーセーフ削除する</span><span class="sxs-lookup"><span data-stu-id="bac86-232">Use the Microsoft 365 Defender portal to remove Safe Links policies</span></span>

1. <span data-ttu-id="bac86-233">[Defender Microsoft 365] ポータルで、[ポリシー] **&[** 脅威ポリシー] セーフリンク] \>  \> **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="bac86-233">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Safe Links**.</span></span>

2. <span data-ttu-id="bac86-234">[リンク **セーフ] ページ** で、一覧からポリシーを選択してクリックします (チェック ボックスをオンにしない)。</span><span class="sxs-lookup"><span data-stu-id="bac86-234">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="bac86-235">表示されるポリシーの詳細が表示されたら、[ポリシーの削除] をクリックし、表示される警告ダイアログで **[は** い] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bac86-235">In the policy details fly out that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies"></a><span data-ttu-id="bac86-236">PowerShell Exchange Onlineスタンドアロン EOP PowerShell を使用して、リンク ポリシーセーフ構成する</span><span class="sxs-lookup"><span data-stu-id="bac86-236">Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Links policies</span></span>

<span data-ttu-id="bac86-237">前に説明したように、セーフリンク ポリシーは、安全なリンク ポリシーと安全なリンク ルールで構成されます。</span><span class="sxs-lookup"><span data-stu-id="bac86-237">As previously described, a Safe Links policy consists of a safe links policy and a safe links rule.</span></span>

<span data-ttu-id="bac86-238">PowerShell では、安全なリンク ポリシーと安全なリンク ルールの違いが明らかです。</span><span class="sxs-lookup"><span data-stu-id="bac86-238">In PowerShell, the difference between safe links policies and safe links rules is apparent.</span></span> <span data-ttu-id="bac86-239">安全なリンク ポリシーは **\* 、-SafeLinksPolicy** コマンドレットを使用して管理し **\* 、-SafeLinksRule** コマンドレットを使用して安全なリンク ルールを管理します。</span><span class="sxs-lookup"><span data-stu-id="bac86-239">You manage safe links policies by using the **\*-SafeLinksPolicy** cmdlets, and you manage safe links rules by using the **\*-SafeLinksRule** cmdlets.</span></span>

- <span data-ttu-id="bac86-240">PowerShell では、安全なリンク ポリシーを最初に作成してから、ルールが適用されるポリシーを識別する安全なリンク ルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="bac86-240">In PowerShell, you create the safe links policy first, then you create the safe links rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="bac86-241">PowerShell では、安全なリンク ポリシーの設定と安全なリンク ルールを個別に変更します。</span><span class="sxs-lookup"><span data-stu-id="bac86-241">In PowerShell, you modify the settings in the safe links policy and the safe links rule separately.</span></span>
- <span data-ttu-id="bac86-242">PowerShell から安全なリンク ポリシーを削除しても、対応する安全なリンク ルールは自動的には削除されません。その逆も同様です。</span><span class="sxs-lookup"><span data-stu-id="bac86-242">When you remove a safe links policy from PowerShell, the corresponding safe links rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-safe-links-policies"></a><span data-ttu-id="bac86-243">PowerShell を使用してリンク ポリシーセーフ作成する</span><span class="sxs-lookup"><span data-stu-id="bac86-243">Use PowerShell to create Safe Links policies</span></span>

<span data-ttu-id="bac86-244">PowerShell で セーフリンク ポリシーを作成するには、次の 2 つの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="bac86-244">Creating a Safe Links policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="bac86-245">安全なリンク ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="bac86-245">Create the safe links policy.</span></span>
2. <span data-ttu-id="bac86-246">ルールが適用される安全なリンク ポリシーを指定する安全なリンク ルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="bac86-246">Create the safe links rule that specifies the safe links policy that the rule applies to.</span></span>

> [!NOTE]
> 
> - <span data-ttu-id="bac86-247">新しいセーフ リンク ルールを作成し、関連付けされていない既存の安全なリンク ポリシーを割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="bac86-247">You can create a new safe links rule and assign an existing, unassociated safe links policy to it.</span></span> <span data-ttu-id="bac86-248">安全なリンク ルールを複数の安全なリンク ポリシーに関連付けできない。</span><span class="sxs-lookup"><span data-stu-id="bac86-248">A safe links rule can't be associated with more than one safe links policy.</span></span>
> 
> - <span data-ttu-id="bac86-249">ポリシーの作成後まで、Microsoft 365 Defender ポータルでは使用できない PowerShell の新しいセーフ リンク ポリシーで、次の設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="bac86-249">You can configure the following settings on new safe links policies in PowerShell that aren't available in the Microsoft 365 Defender portal until after you create the policy:</span></span>
> 
>   - <span data-ttu-id="bac86-250">新しいポリシーを _無効として作成_ します `$false` **(New-SafeLinksRule コマンドレットで有効** )。</span><span class="sxs-lookup"><span data-stu-id="bac86-250">Create the new policy as disabled (_Enabled_ `$false` on the **New-SafeLinksRule** cmdlet).</span></span>
>   - <span data-ttu-id="bac86-251"> _\<Number\>_ **New-SafeLinksRule** コマンドレットの作成時にポリシーの優先度 (優先度) を設定します。</span><span class="sxs-lookup"><span data-stu-id="bac86-251">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-SafeLinksRule** cmdlet).</span></span>
> 
> - <span data-ttu-id="bac86-252">PowerShell で作成した新しい安全なリンク ポリシーは、ポリシーを安全なリンク ルールに割り当てるMicrosoft 365 Defender ポータルには表示されません。</span><span class="sxs-lookup"><span data-stu-id="bac86-252">A new safe links policy that you create in PowerShell isn't visible in the Microsoft 365 Defender portal until you assign the policy to a safe links rule.</span></span>

#### <a name="step-1-use-powershell-to-create-a-safe-links-policy"></a><span data-ttu-id="bac86-253">手順 1: PowerShell を使用して安全なリンク ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="bac86-253">Step 1: Use PowerShell to create a safe links policy</span></span>

<span data-ttu-id="bac86-254">安全なリンク ポリシーを作成するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="bac86-254">To create a safe links policy, use this syntax:</span></span>

```PowerShell
New-SafeLinksPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-IsEnabled <$true | $false>] [-EnableSafeLinksForTeams <$true | $false>] [-ScanUrls <$true | $false>] [-DeliverMessageAfterScan <$true | $false>] [-EnableForInternalSenders <$true | $false>] [-DoNotAllowClickThrough <$true | $false>] [-DoNotTrackUserClicks <$true | $false>] [-DoNotRewriteUrls "Entry1","Entry2",..."EntryN"]
```

> [!NOTE]
> 
> - <span data-ttu-id="bac86-255">_DoNotRewriteUrls_ パラメーターに使用するエントリ構文の詳細については、「次の URL を書き換えない」リストのエントリ構文を [参照してください](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)。</span><span class="sxs-lookup"><span data-stu-id="bac86-255">For details about the entry syntax to use for the _DoNotRewriteUrls_ parameter, see [Entry syntax for the "Do not rewrite the following URLs" list](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span></span>
> 
> - <span data-ttu-id="bac86-256">**Set-SafeLinksPolicy** コマンドレットを使用して既存のセーフ リンク ポリシーを変更するときに _DoNotRewriteUrls_ パラメーターに使用できる追加の構文については、この記事の後半の [「PowerShell](#use-powershell-to-modify-safe-links-policies)を使用して安全なリンク ポリシーを変更する」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="bac86-256">For additional syntax that you can use for the _DoNotRewriteUrls_ parameter when you modify existing safe links policies by using the **Set-SafeLinksPolicy** cmdlet, see the [Use PowerShell to modify safe links policies](#use-powershell-to-modify-safe-links-policies) section later in this article.</span></span>

<span data-ttu-id="bac86-257">この例では、Contoso All という名前の安全なリンク ポリシーを次の値で作成します。</span><span class="sxs-lookup"><span data-stu-id="bac86-257">This example creates a safe links policy named Contoso All with the following values:</span></span>

- <span data-ttu-id="bac86-258">電子メール メッセージで URL のスキャンと書き換えを有効にする。</span><span class="sxs-lookup"><span data-stu-id="bac86-258">Turn on URL scanning and rewriting in email messages.</span></span>
- <span data-ttu-id="bac86-259">[URL のスキャン] を [Teamsオンにする (TAP プレビューのみ)。</span><span class="sxs-lookup"><span data-stu-id="bac86-259">Turn on URL scanning in Teams (TAP Preview only).</span></span>
- <span data-ttu-id="bac86-260">クリックした URL (ファイルを指すクリックされたリンクを含む) のリアルタイム スキャンを有効にする。</span><span class="sxs-lookup"><span data-stu-id="bac86-260">Turn on real-time scanning of clicked URLs, including clicked links that point to files.</span></span>
- <span data-ttu-id="bac86-261">メッセージを配信する前に、URL のスキャンが完了するのを待ちます。</span><span class="sxs-lookup"><span data-stu-id="bac86-261">Wait for URL scanning to complete before delivering the message.</span></span>
- <span data-ttu-id="bac86-262">内部メッセージの URL スキャンと書き換えを有効にする。</span><span class="sxs-lookup"><span data-stu-id="bac86-262">Turn on URL scanning and rewriting for internal messages.</span></span>
- <span data-ttu-id="bac86-263">セーフ Links 保護に関連するユーザークリックを追跡します _(DoNotTrackUserClicks_ パラメーターは使用していないので、既定値は $false です。つまり、ユーザーのクリックが追跡されます)。</span><span class="sxs-lookup"><span data-stu-id="bac86-263">Track user clicks related to Safe Links protection (we aren't using the _DoNotTrackUserClicks_ parameter, and the default value is $false, which means user clicks are tracked).</span></span>
- <span data-ttu-id="bac86-264">ユーザーが元の URL をクリックしてクリックを許可しない。</span><span class="sxs-lookup"><span data-stu-id="bac86-264">Do not allow users to click through to the original URL.</span></span>

```PowerShell
New-SafeLinksPolicy -Name "Contoso All" -IsEnabled $true -EnableSafeLinksForTeams $true -ScanUrls $true -DeliverMessageAfterScan $true -EnableForInternalSenders $true -DoNotAllowClickThrough $true
```

<span data-ttu-id="bac86-265">構文とパラメーターの詳細については [、「New-SafeLinksPolicy」を参照してください](/powershell/module/exchange/new-safelinkspolicy)。</span><span class="sxs-lookup"><span data-stu-id="bac86-265">For detailed syntax and parameter information, see [New-SafeLinksPolicy](/powershell/module/exchange/new-safelinkspolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-a-safe-links-rule"></a><span data-ttu-id="bac86-266">手順 2: PowerShell を使用して安全なリンク ルールを作成する</span><span class="sxs-lookup"><span data-stu-id="bac86-266">Step 2: Use PowerShell to create a safe links rule</span></span>

<span data-ttu-id="bac86-267">安全なリンク ルールを作成するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="bac86-267">To create a safe links rule, use this syntax:</span></span>

```PowerShell
New-SafeLinksRule -Name "<RuleName>" -SafeLinksPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

<span data-ttu-id="bac86-268">この例では、Contoso All という名前の安全なリンク ルールを次の条件で作成します。</span><span class="sxs-lookup"><span data-stu-id="bac86-268">This example creates a safe links rule named Contoso All with the following conditions:</span></span>

- <span data-ttu-id="bac86-269">ルールは、Contoso All という名前の安全なリンク ポリシーに関連付けられている。</span><span class="sxs-lookup"><span data-stu-id="bac86-269">The rule is associated with the safe links policy named Contoso All.</span></span>
- <span data-ttu-id="bac86-270">ルールは、ドメイン内のすべての受信者に contoso.com されます。</span><span class="sxs-lookup"><span data-stu-id="bac86-270">The rule applies to all recipients in the contoso.com domain.</span></span>
- <span data-ttu-id="bac86-271">Priority パラメーターを使用していないので _、既定_ の優先度が使用されます。</span><span class="sxs-lookup"><span data-stu-id="bac86-271">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>
- <span data-ttu-id="bac86-272">ルールが有効になっています (Enabled パラメーターは使用しませんが、既定値はです `$true` )。</span><span class="sxs-lookup"><span data-stu-id="bac86-272">The rule is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>

```powershell
New-SafeLinksRule -Name "Contoso All" -SafeLinksPolicy "Contoso All" -RecipientDomainIs contoso.com
```

<span data-ttu-id="bac86-273">構文とパラメーターの詳細については [、「New-SafeLinksRule」を参照してください](/powershell/module/exchange/new-safelinksrule)。</span><span class="sxs-lookup"><span data-stu-id="bac86-273">For detailed syntax and parameter information, see [New-SafeLinksRule](/powershell/module/exchange/new-safelinksrule).</span></span>

### <a name="use-powershell-to-view-safe-links-policies"></a><span data-ttu-id="bac86-274">PowerShell を使用して安全なリンク ポリシーを表示する</span><span class="sxs-lookup"><span data-stu-id="bac86-274">Use PowerShell to view safe links policies</span></span>

<span data-ttu-id="bac86-275">既存の安全なリンク ポリシーを表示するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="bac86-275">To view existing safe links policies, use the following syntax:</span></span>

```PowerShell
Get-SafeLinksPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="bac86-276">この例では、すべての安全なリンク ポリシーの概要一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="bac86-276">This example returns a summary list of all safe links policies.</span></span>

```PowerShell
Get-SafeLinksPolicy | Format-Table Name
```

<span data-ttu-id="bac86-277">この例では、Contoso Executives という名前の安全なリンク ポリシーの詳細情報を返します。</span><span class="sxs-lookup"><span data-stu-id="bac86-277">This example returns detailed information for the safe links policy named Contoso Executives.</span></span>

```PowerShell
Get-SafeLinksPolicy -Identity "Contoso Executives"
```

<span data-ttu-id="bac86-278">構文とパラメーターの詳細については [、「Get-SafeLinksPolicy」を参照してください](/powershell/module/exchange/get-safelinkspolicy)。</span><span class="sxs-lookup"><span data-stu-id="bac86-278">For detailed syntax and parameter information, see [Get-SafeLinksPolicy](/powershell/module/exchange/get-safelinkspolicy).</span></span>

### <a name="use-powershell-to-view-safe-links-rules"></a><span data-ttu-id="bac86-279">PowerShell を使用して安全なリンク ルールを表示する</span><span class="sxs-lookup"><span data-stu-id="bac86-279">Use PowerShell to view safe links rules</span></span>

<span data-ttu-id="bac86-280">既存のセーフ リンク ルールを表示するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="bac86-280">To view existing safe links rules, use the following syntax:</span></span>

```PowerShell
Get-SafeLinksRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="bac86-281">この例では、すべての安全なリンク ルールの概要一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="bac86-281">This example returns a summary list of all safe links rules.</span></span>

```PowerShell
Get-SafeLinksRule | Format-Table Name,State
```

<span data-ttu-id="bac86-282">ルールを有効または無効にしてリストをフィルター処理するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="bac86-282">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-SafeLinksRule -State Disabled
```

```PowerShell
Get-SafeLinksRule -State Enabled
```

<span data-ttu-id="bac86-283">この例では、Contoso Executives という名前の安全なリンク ルールの詳細情報を返します。</span><span class="sxs-lookup"><span data-stu-id="bac86-283">This example returns detailed information for the safe links rule named Contoso Executives.</span></span>

```PowerShell
Get-SafeLinksRule -Identity "Contoso Executives"
```

<span data-ttu-id="bac86-284">構文とパラメーターの詳細については [、「Get-SafeLinksRule」を参照してください](/powershell/module/exchange/get-safelinksrule)。</span><span class="sxs-lookup"><span data-stu-id="bac86-284">For detailed syntax and parameter information, see [Get-SafeLinksRule](/powershell/module/exchange/get-safelinksrule).</span></span>

### <a name="use-powershell-to-modify-safe-links-policies"></a><span data-ttu-id="bac86-285">PowerShell を使用して安全なリンク ポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="bac86-285">Use PowerShell to modify safe links policies</span></span>

<span data-ttu-id="bac86-286">PowerShell で安全なリンク ポリシーの名前を変更することはできません **(Set-SafeLinksPolicy** コマンドレットには _Name_ パラメーターはありません)。</span><span class="sxs-lookup"><span data-stu-id="bac86-286">You can't rename a safe links policy in PowerShell (the **Set-SafeLinksPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="bac86-287">Defender ポータルで セーフ リンク ポリシーの名前を変更Microsoft 365、セーフ リンク ルールの名前を変更 _するのみです_。</span><span class="sxs-lookup"><span data-stu-id="bac86-287">When you rename a Safe Links policy in the Microsoft 365 Defender portal, you're only renaming the safe links _rule_.</span></span>

<span data-ttu-id="bac86-288">PowerShell で安全なリンク ポリシーを変更するための唯一の追加の考慮事項は _、DoNotRewriteUrls_ パラメーターで使用可能な構文です ("次の [URL を](safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)書き換えない" リスト)。</span><span class="sxs-lookup"><span data-stu-id="bac86-288">The only additional consideration for modifying safe links policies in PowerShell is the available syntax for the _DoNotRewriteUrls_ parameter (the ["Do not rewrite the following URLs" list](safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)):</span></span>

- <span data-ttu-id="bac86-289">既存のエントリを置き換える値を追加するには、次の構文を使用します `"Entry1","Entry2,..."EntryN"` 。</span><span class="sxs-lookup"><span data-stu-id="bac86-289">To add values that will replace any existing entries, use the following syntax: `"Entry1","Entry2,..."EntryN"`.</span></span>
- <span data-ttu-id="bac86-290">他の既存のエントリに影響を与えることなく値を追加または削除するには、次の構文を使用します。 `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`</span><span class="sxs-lookup"><span data-stu-id="bac86-290">To add or remove values without affecting other existing entries, use the following syntax: `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`</span></span>

<span data-ttu-id="bac86-291">それ以外の場合は、「手順 [1: PowerShell](#step-1-use-powershell-to-create-a-safe-links-policy) を使用して安全なリンク ポリシーを作成する」のセクションで説明したように、安全なリンク ポリシーを作成するときに同じ設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="bac86-291">Otherwise, the same settings are available when you create a safe links policy as described in the [Step 1: Use PowerShell to create a safe links policy](#step-1-use-powershell-to-create-a-safe-links-policy) section earlier in this article.</span></span>

<span data-ttu-id="bac86-292">安全なリンク ポリシーを変更するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="bac86-292">To modify a safe links policy, use this syntax:</span></span>

```PowerShell
Set-SafeLinksPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="bac86-293">構文とパラメーターの詳細については [、「Set-SafeLinksPolicy」を参照してください](/powershell/module/exchange/set-safelinkspolicy)。</span><span class="sxs-lookup"><span data-stu-id="bac86-293">For detailed syntax and parameter information, see [Set-SafeLinksPolicy](/powershell/module/exchange/set-safelinkspolicy).</span></span>

### <a name="use-powershell-to-modify-safe-links-rules"></a><span data-ttu-id="bac86-294">PowerShell を使用して安全なリンク ルールを変更する</span><span class="sxs-lookup"><span data-stu-id="bac86-294">Use PowerShell to modify safe links rules</span></span>

<span data-ttu-id="bac86-295">PowerShell で安全なリンク ルールを変更するときに使用できない唯一の設定は、無効なルールを作成できる _Enabled_ パラメーターです。</span><span class="sxs-lookup"><span data-stu-id="bac86-295">The only setting that's not available when you modify a safe links rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="bac86-296">既存のセーフ リンク ルールを有効または無効にするには、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="bac86-296">To enable or disable existing safe links rules, see the next section.</span></span>

<span data-ttu-id="bac86-297">それ以外の場合は、「手順 [2: PowerShell](#step-2-use-powershell-to-create-a-safe-links-rule) を使用して安全なリンク ルールを作成する」セクションで説明したように、ルールを作成するときに同じ設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="bac86-297">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create a safe links rule](#step-2-use-powershell-to-create-a-safe-links-rule) section earlier in this article.</span></span>

<span data-ttu-id="bac86-298">安全なリンク ルールを変更するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="bac86-298">To modify a safe links rule, use this syntax:</span></span>

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="bac86-299">構文とパラメーターの詳細については [、「Set-SafeLinksRule」を参照してください](/powershell/module/exchange/set-safelinksrule)。</span><span class="sxs-lookup"><span data-stu-id="bac86-299">For detailed syntax and parameter information, see [Set-SafeLinksRule](/powershell/module/exchange/set-safelinksrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-safe-links-rules"></a><span data-ttu-id="bac86-300">PowerShell を使用して安全なリンク ルールを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="bac86-300">Use PowerShell to enable or disable safe links rules</span></span>

<span data-ttu-id="bac86-301">PowerShell で安全なリンク ルールを有効または無効にすると、セーフ リンク ポリシー全体 (セーフ リンク ルールと割り当てられた安全なリンク ポリシー) が有効または無効となります。</span><span class="sxs-lookup"><span data-stu-id="bac86-301">Enabling or disabling a safe links rule in PowerShell enables or disables the whole Safe Links policy (the safe links rule and the assigned safe links policy).</span></span>

<span data-ttu-id="bac86-302">PowerShell で安全なリンク ルールを有効または無効にするには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="bac86-302">To enable or disable a safe links rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-SafeLinksRule | Disable-SafeLinksRule> -Identity "<RuleName>"
```

<span data-ttu-id="bac86-303">この例では、Marketing Department という名前の安全なリンク ルールを無効にします。</span><span class="sxs-lookup"><span data-stu-id="bac86-303">This example disables the safe links rule named Marketing Department.</span></span>

```PowerShell
Disable-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="bac86-304">この例では、同じルールを有効化します。</span><span class="sxs-lookup"><span data-stu-id="bac86-304">This example enables same rule.</span></span>

```PowerShell
Enable-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="bac86-305">構文とパラメーターの詳細については [、「Enable-SafeLinksRule」](/powershell/module/exchange/enable-safelinksrule) および [「Disable-SafeLinksRule」を参照してください](/powershell/module/exchange/disable-safelinksrule)。</span><span class="sxs-lookup"><span data-stu-id="bac86-305">For detailed syntax and parameter information, see [Enable-SafeLinksRule](/powershell/module/exchange/enable-safelinksrule) and [Disable-SafeLinksRule](/powershell/module/exchange/disable-safelinksrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-safe-links-rules"></a><span data-ttu-id="bac86-306">PowerShell を使用して安全なリンク ルールの優先度を設定する</span><span class="sxs-lookup"><span data-stu-id="bac86-306">Use PowerShell to set the priority of safe links rules</span></span>

<span data-ttu-id="bac86-p123">ルールに設定できる優先度の最高値値は 0 です。設定できる最低値はルールの数に依存します。たとえば、ルールが五つある場合、使用できる優先度の値は 0 から 4 です。既存の一つのルールの優先度を変更すると、他のルールにも連鎖的な影響が起こりえます。たとえば、カスタム ルールが五つある場合 (優先度 0 から 4) に、一つのルールの優先度を 2 に変更した場合、既存の優先度 2 のルールは優先度 3 に変更され、優先度 3 は優先度 4 に変更されます。</span><span class="sxs-lookup"><span data-stu-id="bac86-p123">The highest priority value you can set on a rule is 0. The lowest value you can set depends on the number of rules. For example, if you have five rules, you can use the priority values 0 through 4. Changing the priority of an existing rule can have a cascading effect on other rules. For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="bac86-312">PowerShell で安全なリンク ルールの優先度を設定するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="bac86-312">To set the priority of a safe links rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="bac86-p124">この例では、Marketing Department というルールの優先度を 2 に設定しています。優先度が 2 以下のすべての既存のルールは、優先度が 1 ずつ下がります (優先度番号が 1 ずつ増加します)。</span><span class="sxs-lookup"><span data-stu-id="bac86-p124">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-SafeLinksRule -Identity "Marketing Department" -Priority 2
```

> [!NOTE]
> <span data-ttu-id="bac86-315">新しいルールを作成するときに優先度を設定するには **、New-SafeLinksRule** コマンドレットの Priority パラメーターを使用します。 </span><span class="sxs-lookup"><span data-stu-id="bac86-315">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-SafeLinksRule** cmdlet instead.</span></span>

<span data-ttu-id="bac86-316">構文とパラメーターの詳細については [、「Set-SafeLinksRule」を参照してください](/powershell/module/exchange/set-safelinksrule)。</span><span class="sxs-lookup"><span data-stu-id="bac86-316">For detailed syntax and parameter information, see [Set-SafeLinksRule](/powershell/module/exchange/set-safelinksrule).</span></span>

### <a name="use-powershell-to-remove-safe-links-policies"></a><span data-ttu-id="bac86-317">PowerShell を使用して安全なリンク ポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="bac86-317">Use PowerShell to remove safe links policies</span></span>

<span data-ttu-id="bac86-318">PowerShell を使用して安全なリンク ポリシーを削除しても、対応する安全なリンク ルールは削除されません。</span><span class="sxs-lookup"><span data-stu-id="bac86-318">When you use PowerShell to remove a safe links policy, the corresponding safe links rule isn't removed.</span></span>

<span data-ttu-id="bac86-319">PowerShell で安全なリンク ポリシーを削除するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="bac86-319">To remove a safe links policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeLinksPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="bac86-320">この例では、Marketing Department という名前の安全なリンク ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="bac86-320">This example removes the safe links policy named Marketing Department.</span></span>

```PowerShell
Remove-SafeLinksPolicy -Identity "Marketing Department"
```

<span data-ttu-id="bac86-321">構文とパラメーターの詳細については [、「Remove-SafeLinksPolicy」を参照してください](/powershell/module/exchange/remove-safelinkspolicy)。</span><span class="sxs-lookup"><span data-stu-id="bac86-321">For detailed syntax and parameter information, see [Remove-SafeLinksPolicy](/powershell/module/exchange/remove-safelinkspolicy).</span></span>

### <a name="use-powershell-to-remove-safe-links-rules"></a><span data-ttu-id="bac86-322">PowerShell を使用して安全なリンク ルールを削除する</span><span class="sxs-lookup"><span data-stu-id="bac86-322">Use PowerShell to remove safe links rules</span></span>

<span data-ttu-id="bac86-323">PowerShell を使用して安全なリンク ルールを削除しても、対応する安全なリンク ポリシーは削除されません。</span><span class="sxs-lookup"><span data-stu-id="bac86-323">When you use PowerShell to remove a safe links rule, the corresponding safe links policy isn't removed.</span></span>

<span data-ttu-id="bac86-324">PowerShell で安全なリンク ルールを削除するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="bac86-324">To remove a safe links rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeLinksRule -Identity "<PolicyName>"
```

<span data-ttu-id="bac86-325">この例では、Marketing Department という名前の安全なリンク ルールを削除します。</span><span class="sxs-lookup"><span data-stu-id="bac86-325">This example removes the safe links rule named Marketing Department.</span></span>

```PowerShell
Remove-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="bac86-326">構文とパラメーターの詳細については [、「Remove-SafeLinksRule」を参照してください](/powershell/module/exchange/remove-safelinksrule)。</span><span class="sxs-lookup"><span data-stu-id="bac86-326">For detailed syntax and parameter information, see [Remove-SafeLinksRule](/powershell/module/exchange/remove-safelinksrule).</span></span>

<span data-ttu-id="bac86-327">リンクがメッセージセーフ確認するには、使用可能な Microsoft Defender のレポートをOffice 365してください。</span><span class="sxs-lookup"><span data-stu-id="bac86-327">To verify that Safe Links is scanning messages, check the available Microsoft Defender for Office 365 reports.</span></span> <span data-ttu-id="bac86-328">詳細については、「View [reports for Defender for Office 365」](view-reports-for-mdo.md)および「Use Explorer in [the defender portal」をMicrosoft 365してください](threat-explorer.md)。</span><span class="sxs-lookup"><span data-stu-id="bac86-328">For more information, see [View reports for Defender for Office 365](view-reports-for-mdo.md) and [Use Explorer in the Microsoft 365 Defender portal](threat-explorer.md).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="bac86-329">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="bac86-329">How do you know these procedures worked?</span></span>

<span data-ttu-id="bac86-330">リンク ポリシーが正常に作成、変更、または削除されたことを確認するには、セーフ手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="bac86-330">To verify that you've successfully created, modified, or removed Safe Links policies, do any of the following steps:</span></span>

- <span data-ttu-id="bac86-331">[Defender Microsoft 365] ポータルの [ポリシー] & \> **脅威ポリシーと** リンク \> **セーフします**。</span><span class="sxs-lookup"><span data-stu-id="bac86-331">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat policies** \> **Safe Links**.</span></span> <span data-ttu-id="bac86-332">ポリシー、その状態の値、および **優先度** の値の一覧を **確認** します。</span><span class="sxs-lookup"><span data-stu-id="bac86-332">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="bac86-333">詳細を表示するには、一覧からポリシーを選択し、詳細をフライアウトで表示します。</span><span class="sxs-lookup"><span data-stu-id="bac86-333">To view more details, select the policy from the list, and view the details in the fly out.</span></span>

- <span data-ttu-id="bac86-334">PowerShell Exchange Onlineまたは PowerShell Exchange Online Protectionで、ポリシーまたはルールの名前に置き換え、次のコマンドを実行し、 \<Name\> 設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="bac86-334">In Exchange Online PowerShell or Exchange Online Protection PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-SafeLinksPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-SafeLinksRule -Identity "<Name>"
  ```