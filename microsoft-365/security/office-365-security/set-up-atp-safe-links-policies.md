---
title: Microsoft Defender で安全なリンク ポリシーを Office 365 用にセットアップする
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: bdd5372d-775e-4442-9c1b-609627b94b5d
ms.collection:
- M365-security-compliance
description: 管理者は、Microsoft Defender for Office 365 の安全なリンク ポリシーとグローバルな安全なリンクの設定を表示、作成、変更、削除する方法について説明します。
ms.openlocfilehash: 8a6d8a7ad567b658f04cb0b28800d4edbc33ec67
ms.sourcegitcommit: f81ca61f74f11a7436a6172538c3bda81b484d62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/15/2020
ms.locfileid: "49675243"
---
# <a name="set-up-safe-links-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="a1561-103">Microsoft Defender で安全なリンク ポリシーを Office 365 用にセットアップする</span><span class="sxs-lookup"><span data-stu-id="a1561-103">Set up Safe Links policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> <span data-ttu-id="a1561-104">この記事は、[Microsoft Defender for Office 365](office-365-atp.md) をご利用の法人のお客様を対象としています。</span><span class="sxs-lookup"><span data-stu-id="a1561-104">This article is intended for business customers who have [Microsoft Defender for Office 365](office-365-atp.md).</span></span> <span data-ttu-id="a1561-105">If you are a home user looking for information about Safelinks in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span><span class="sxs-lookup"><span data-stu-id="a1561-105">If you are a home user looking for information about Safelinks in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="a1561-106">「安全なリンク」は [、Microsoft Defender for Office 365](office-365-atp.md) の機能で、メール フロー内の受信メール メッセージの URL スキャンや、電子メール メッセージや他の場所での URL とリンクのクリック検証の時間を提供します。</span><span class="sxs-lookup"><span data-stu-id="a1561-106">Safe Links is a feature in [Microsoft Defender for Office 365](office-365-atp.md) that provides URL scanning of inbound email messages in mail flow, and time of click verification of URLs and links in email messages and in other locations.</span></span> <span data-ttu-id="a1561-107">詳細については [、Microsoft Defender の 「安全なリンク」を参照してください。Office 365](atp-safe-links.md).</span><span class="sxs-lookup"><span data-stu-id="a1561-107">For more information, see [Safe Links in Microsoft Defender for Office 365](atp-safe-links.md).</span></span>

<span data-ttu-id="a1561-108">組み込みまたは既定の安全なリンク ポリシーはありません。</span><span class="sxs-lookup"><span data-stu-id="a1561-108">There's no built-in or default Safe Links policy.</span></span> <span data-ttu-id="a1561-109">URL の安全なリンクのスキャンを取得するには、この記事で説明するように、1 つ以上の安全なリンク ポリシーを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a1561-109">To get Safe Links scanning of URLs, you need to create one or more Safe Links policies as described in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="a1561-110">「安全なリンク」ポリシーの外部で、安全なリンク **保護** のグローバル設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="a1561-110">You configure the global settings for Safe Links protection **outside** of Safe Links policies.</span></span> <span data-ttu-id="a1561-111">手順については、「Microsoft Defender で安全なリンクのグローバル設定を構成する (Office [365)」を参照](configure-global-settings-for-safe-links.md)してください。</span><span class="sxs-lookup"><span data-stu-id="a1561-111">For instructions, see [Configure global settings for Safe Links in Microsoft Defender for Office 365](configure-global-settings-for-safe-links.md).</span></span>

<span data-ttu-id="a1561-112">安全なリンクポリシーは、セキュリティ & コンプライアンス センターまたは PowerShell で構成できます (Exchange Online のメールボックスを持つ対象の Microsoft 365 組織の場合は Exchange Online PowerShell、Exchange Online メールボックスのない組織の場合はスタンドアロンの EOP PowerShell、Microsoft Defender for Office 365 アドオン サブスクリプションの場合)。</span><span class="sxs-lookup"><span data-stu-id="a1561-112">You can configure Safe Links policies in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Microsoft Defender for Office 365 add-on subscriptions).</span></span>

<span data-ttu-id="a1561-113">安全なリンク ポリシーの基本的な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a1561-113">The basic elements of a Safe Links policy are:</span></span>

- <span data-ttu-id="a1561-114">安全なリンクの **ポリシー:** 安全なリンク保護を有効にする、リアルタイムの URL スキャンを有効にする、メッセージを配信する前にリアルタイム スキャンが完了するのを待つかどうかを指定する、内部メッセージのスキャンを有効にする、URL をクリックしたユーザーを追跡するかどうかを指定する、元の URL に対してユーザーが trough をクリックできるかどうかを指定する。</span><span class="sxs-lookup"><span data-stu-id="a1561-114">**The safe links policy**: Turn on Safe Links protection, turn on real-time URL scanning, specify whether to wait for real-time scanning to complete before delivering the message, turn on scanning for internal messages, specify whether to track user clicks on URLs, and specify whether to allow users to click trough to the original URL.</span></span>
- <span data-ttu-id="a1561-115">**安全なリンクルール**: 優先度と受信者フィルター (ポリシーが適用されるユーザー) を指定します。</span><span class="sxs-lookup"><span data-stu-id="a1561-115">**The safe links rule**: Specifies the priority and recipient filters (who the policy applies to).</span></span>

<span data-ttu-id="a1561-116">セキュリティ/コンプライアンス センターで安全なリンク ポリシーを管理する場合、これら 2 つの要素の違い&明らかではありません。</span><span class="sxs-lookup"><span data-stu-id="a1561-116">The difference between these two elements isn't obvious when you manage Safe Links polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="a1561-117">安全なリンク ポリシーを作成する場合、実際には安全なリンク ルールと関連付けられた安全なリンク ポリシーを、両方に同じ名前を使用して同時に作成します。</span><span class="sxs-lookup"><span data-stu-id="a1561-117">When you create a Safe Links policy, you're actually creating a safe links rule and the associated safe links policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="a1561-118">安全なリンク ポリシーを変更すると、名前、優先度、有効または無効、および受信者フィルターに関連する設定によって、安全なリンク ルールが変更されます。</span><span class="sxs-lookup"><span data-stu-id="a1561-118">When you modify a Safe Links policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the safe links rule.</span></span> <span data-ttu-id="a1561-119">その他のすべての設定では、関連付けられている安全なリンク ポリシーが変更されます。</span><span class="sxs-lookup"><span data-stu-id="a1561-119">All other settings modify the associated safe links policy.</span></span>
- <span data-ttu-id="a1561-120">安全なリンク ポリシーを削除すると、安全なリンク ルールと関連付けられている安全なリンク ポリシーが削除されます。</span><span class="sxs-lookup"><span data-stu-id="a1561-120">When you remove a Safe Links policy, the safe links rule and the associated safe links policy are removed.</span></span>

<span data-ttu-id="a1561-121">Exchange Online PowerShell またはスタンドアロン EOP PowerShell では、ポリシーとルールを個別に管理します。</span><span class="sxs-lookup"><span data-stu-id="a1561-121">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="a1561-122">詳細については、後の [「Exchange Online PowerShell またはスタンドアロンの EOP PowerShell](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) を使用して安全なリンク ポリシーを構成する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a1561-122">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Links policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) section later in this article.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="a1561-123">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="a1561-123">What do you need to know before you begin?</span></span>

- <span data-ttu-id="a1561-124"><https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="a1561-124">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="a1561-125">[安全なリンク] ページ **に直接移動するには** 、次の値を使用します <https://protection.office.com/safelinksv2> 。</span><span class="sxs-lookup"><span data-stu-id="a1561-125">To go directly to the **Safe Links** page, use <https://protection.office.com/safelinksv2>.</span></span>

- <span data-ttu-id="a1561-126">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a1561-126">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="a1561-127">スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a1561-127">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="a1561-128">この記事に記載の手順を行うには、セキュリティ/コンプライアンス センターのアクセス許可が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a1561-128">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="a1561-129">安全なリンク ポリシーを作成、変更、および削除するには、組織の管理役割グループまたはセキュリティ管理者役割グループのメンバー **である** 必要があります。</span><span class="sxs-lookup"><span data-stu-id="a1561-129">To create, modify, and delete Safe Links policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="a1561-130">安全なリンク ポリシーに読み取り専用でアクセスするには、グローバル閲覧者またはセキュリティ閲覧者の役割グループのメンバー **である** 必要があります。</span><span class="sxs-lookup"><span data-stu-id="a1561-130">For read-only access to Safe Links policies, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="a1561-131">詳細については、「[セキュリティ/コンプライアンス センターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a1561-131">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="a1561-132">**注**:</span><span class="sxs-lookup"><span data-stu-id="a1561-132">**Notes**:</span></span>

  - <span data-ttu-id="a1561-133">Microsoft 365 管理センターで、対応する Azure Active Directory の役割にユーザーを追加すると、ユーザーには、セキュリティ/コンプライアンス センター の必要なアクセス許可 _および_ Microsoft 365 のその他の機能に必要なアクセス許可が付与されます。</span><span class="sxs-lookup"><span data-stu-id="a1561-133">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="a1561-134">詳細については、「[管理者の役割について](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a1561-134">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="a1561-135">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) の **閲覧専用の組織管理** の役割グループが この機能への読み取り専用アクセス権も付与します。</span><span class="sxs-lookup"><span data-stu-id="a1561-135">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="a1561-136">安全なリンク ポリシーの推奨設定については、「安全なリンクのポリシー [設定」を参照してください](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings)。</span><span class="sxs-lookup"><span data-stu-id="a1561-136">For our recommended settings for Safe Links policies, see [Safe Links policy settings](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings).</span></span>

- <span data-ttu-id="a1561-137">新しいポリシーまたは更新されたポリシーを適用するには、最大 30 分かかります。</span><span class="sxs-lookup"><span data-stu-id="a1561-137">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="a1561-138">[新しい機能は、Microsoft Defender for Office 365](office-365-atp.md#new-features-in-microsoft-defender-for-office-365)に継続的に追加されています。</span><span class="sxs-lookup"><span data-stu-id="a1561-138">[New features are continually being added to Microsoft Defender for Office 365](office-365-atp.md#new-features-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="a1561-139">新機能が追加された場合は、既存の安全なリンク ポリシーの調整が必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="a1561-139">As new features are added, you may need to make adjustments to your existing Safe Links policies.</span></span>

## <a name="use-the-security--compliance-center-to-create-safe-links-policies"></a><span data-ttu-id="a1561-140">セキュリティ/コンプライアンス センター&使用して安全なリンク ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="a1561-140">Use the Security & Compliance Center to create Safe Links policies</span></span>

<span data-ttu-id="a1561-141">セキュリティ & コンプライアンス センターでカスタムの安全なリンク ポリシーを作成すると、両方に同じ名前を使用して、安全なリンク ルールと関連付けられた安全なリンク ポリシーが同時に作成されます。</span><span class="sxs-lookup"><span data-stu-id="a1561-141">Creating a custom Safe Links policy in the Security & Compliance Center creates the safe links rule and the associated safe links policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="a1561-142">セキュリティ/コンプライアンス センター&、**脅威管理ポリシー** ATP の安全なリンク \>  \> **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="a1561-142">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="a1561-143">[安全な **リンク] ページで** 、[作成] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="a1561-143">On the **Safe Links** page, click **Create**.</span></span>

3. <span data-ttu-id="a1561-144">安全 **なリンクの新しいポリシー** ウィザードが開きます。</span><span class="sxs-lookup"><span data-stu-id="a1561-144">The **New Safe Links policy** wizard opens.</span></span> <span data-ttu-id="a1561-145">[ポリシー **に名前を付け] ページ** で、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="a1561-145">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="a1561-146">**[名前]**: わかりやすい一意のポリシー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="a1561-146">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="a1561-147">**[説明]**: ポリシーについての説明を入力します (オプション)。</span><span class="sxs-lookup"><span data-stu-id="a1561-147">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="a1561-148">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a1561-148">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="a1561-149">表示される **[設定** ] ページで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="a1561-149">On the **Settings** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="a1561-150">**メッセージ内の悪意のある可能性** のある不明な URL に対するアクションを選択します。[ **オン** ] を選択すると、電子メール メッセージ内のリンクに対する安全なリンク保護が有効になります。</span><span class="sxs-lookup"><span data-stu-id="a1561-150">**Select the action for unknown potentially malicious URLs in messages**: Select **On** to enable Safe Links protection for links in email messages.</span></span>

   - <span data-ttu-id="a1561-151">**Microsoft Teams 内の不明な URL** または悪意のある可能性のある URL に対するアクションを選択します。[ **オン** ] を選択すると、Teams のリンクに対する安全なリンク保護が有効になります。</span><span class="sxs-lookup"><span data-stu-id="a1561-151">**Select the action for unknown or potentially malicious URLs within Microsoft Teams**: Select **On** to enable Safe Links protection for links in Teams.</span></span>

   - <span data-ttu-id="a1561-152">**疑わしいリンク** やファイルを指すリンクに対してリアルタイム URL スキャンを適用する: 電子メール メッセージ内のリンクのリアルタイム スキャンを有効にするには、この設定を選択します。</span><span class="sxs-lookup"><span data-stu-id="a1561-152">**Apply real-time URL scanning for suspicious links and links that point to files**: Select this setting to enable real-time scanning of links in email messages.</span></span>

   - <span data-ttu-id="a1561-153">**メッセージを配信する前** に URL のスキャンが完了するのを待つ: この設定を選択すると、リアルタイム URL スキャンが完了してからメッセージが配信されます。</span><span class="sxs-lookup"><span data-stu-id="a1561-153">**Wait for URL scanning to complete before delivering the message**: Select this setting to wait for real-time URL scanning to complete before delivering the message.</span></span>

   - <span data-ttu-id="a1561-154">**組織内で送信される電子** メール メッセージに安全なリンクを適用する : この設定を選択すると、内部送信者と内部受信者の間のメッセージに安全なリンク ポリシーが適用されます。</span><span class="sxs-lookup"><span data-stu-id="a1561-154">**Apply Safe Links to email messages sent within the organization**: Select this setting to apply the Safe Links policy to messages between internal senders and internal recipients.</span></span>

   - <span data-ttu-id="a1561-155">**ユーザーのクリックを追跡しない**: この設定をオフのままにして、メール メッセージ内の URL を追跡するユーザーのクリックを有効にします。</span><span class="sxs-lookup"><span data-stu-id="a1561-155">**Do not track user clicks**: Leave this setting unselected to enable the tracking user clicks on URLs in email messages.</span></span>

   - <span data-ttu-id="a1561-156">**ユーザーがクリックして元** の URL にアクセスできない: この設定を選択すると、ユーザーが警告ページ内の元の URL にクリックスルー [されるのをブロックします](atp-safe-links.md#warning-pages-from-safe-links)。</span><span class="sxs-lookup"><span data-stu-id="a1561-156">**Do not allow users to click through to original URL**: Select this setting to block users from clicking through to the original URL in [warning pages](atp-safe-links.md#warning-pages-from-safe-links).</span></span>

   - <span data-ttu-id="a1561-157">**次の URL を書き換え** ない: 安全なリンクによってブロックされる指定された URL へのアクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="a1561-157">**Do not rewrite the following URLs**: Allows access the specified URLs that would otherwise be blocked by Safe Links.</span></span>

     <span data-ttu-id="a1561-158">ボックスに必要な URL または値を入力し、</span><span class="sxs-lookup"><span data-stu-id="a1561-158">In the box, type the URL or value that you want, and then click</span></span> ![[追加] ボタン アイコン](../../media/ITPro-EAC-AddIcon.png)<span data-ttu-id="a1561-160">.</span><span class="sxs-lookup"><span data-stu-id="a1561-160">.</span></span>

     <span data-ttu-id="a1561-161">既存のエントリを削除するには、そのエントリを選択し、</span><span class="sxs-lookup"><span data-stu-id="a1561-161">To remove an existing entry, select it and then click</span></span> ![[削除] ボタン アイコン](../../media/ITPro-EAC-DeleteIcon.png)<span data-ttu-id="a1561-163">.</span><span class="sxs-lookup"><span data-stu-id="a1561-163">.</span></span>

     <span data-ttu-id="a1561-164">エントリ構文については、「次の URL を書き換えない」の一覧のエントリ [構文を参照してください](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)。</span><span class="sxs-lookup"><span data-stu-id="a1561-164">For entry syntax, see [Entry syntax for the "Do not rewrite the following URLs" list](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span></span>

   <span data-ttu-id="a1561-165">これらの設定の詳細については、「電子メール メッセージの安全なリンクの設定 [」](atp-safe-links.md#safe-links-settings-for-email-messages) および「Microsoft Teams の安全なリンクの [設定」を参照してください](atp-safe-links.md#safe-links-settings-for-microsoft-teams)。</span><span class="sxs-lookup"><span data-stu-id="a1561-165">For detailed information about these settings, see [Safe Links settings for email messages](atp-safe-links.md#safe-links-settings-for-email-messages) and [Safe Links settings for Microsoft Teams](atp-safe-links.md#safe-links-settings-for-microsoft-teams).</span></span>

   <span data-ttu-id="a1561-166">Standard および Strict ポリシー設定の推奨値の詳細については、「安全なリンクのポリシー [設定」を参照してください](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings)。</span><span class="sxs-lookup"><span data-stu-id="a1561-166">For more the recommended values for Standard and Strict policy settings, see [Safe Links policy settings](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings).</span></span>

   <span data-ttu-id="a1561-167">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a1561-167">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="a1561-168">表示される **[適用先** ] ページで、ポリシーが適用される内部受信者を特定します。</span><span class="sxs-lookup"><span data-stu-id="a1561-168">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="a1561-169">各条件や例外は 1 回しか使用できませんが、条件や例外には複数の値を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="a1561-169">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="a1561-170">同じ条件や例外に複数の値がある場合、OR ロジック (たとえば、_\<recipient1\>_ または _\<recipient2\>_) が適用されます。</span><span class="sxs-lookup"><span data-stu-id="a1561-170">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="a1561-171">a別の条件や例外がある場合は AND ロジック (たとえば、_\<recipient1\>_ かつ _\<member of group 1\>_) が適用されます。</span><span class="sxs-lookup"><span data-stu-id="a1561-171">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="a1561-172">[条件 **の追加] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="a1561-172">Click **Add a condition**.</span></span> <span data-ttu-id="a1561-173">表示されるドロップダウンで、[適用] の下の条件を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="a1561-173">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="a1561-174">**受信者は、** 組織内の 1 つ以上のメールボックス、メール ユーザー、またはメール連絡先を指定します。</span><span class="sxs-lookup"><span data-stu-id="a1561-174">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="a1561-175">**受信者が次のメンバーである**: 組織内の 1 つ以上のグループを指定します。</span><span class="sxs-lookup"><span data-stu-id="a1561-175">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="a1561-176">**[受信者のドメインが次の値である]**: 組織内で構成済みの 1 つ以上の承認済みドメイン内の受信者を指定します。</span><span class="sxs-lookup"><span data-stu-id="a1561-176">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in your organization.</span></span>

   <span data-ttu-id="a1561-177">条件を選択すると、対応するドロップダウンが [任意] ボックス **と一緒に表示** されます。</span><span class="sxs-lookup"><span data-stu-id="a1561-177">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="a1561-178">ボックス内をクリックし、値の一覧をスクロールして選択します。</span><span class="sxs-lookup"><span data-stu-id="a1561-178">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="a1561-179">ボックス内をクリックし、入力を開始してリストをフィルター処理し、値を選択します。</span><span class="sxs-lookup"><span data-stu-id="a1561-179">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="a1561-180">値を追加するには、ボックス内の空の領域をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a1561-180">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="a1561-181">個々のエントリを削除するには、値の **[削除]** ![ ](../../media/scc-remove-icon.png) アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="a1561-181">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="a1561-182">条件全体を削除するには、条件の **[削除**] ![ ](../../media/scc-remove-icon.png) アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="a1561-182">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="a1561-183">追加の条件を追加するには、[条件の追加] **をクリック** し、[適用する条件] の下の残りの値 **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="a1561-183">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="a1561-184">例外を追加するには、[条件の追加] をクリックし、[条件以外] で例外 **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="a1561-184">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="a1561-185">設定と動作は、条件とまったく同じです。</span><span class="sxs-lookup"><span data-stu-id="a1561-185">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="a1561-186">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a1561-186">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="a1561-187">表示される **[設定の確認** ] ページで、設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="a1561-187">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="a1561-188">各設定で **[編集]** をクリックして変更できます。</span><span class="sxs-lookup"><span data-stu-id="a1561-188">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="a1561-189">完了したら、 **[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a1561-189">When you're finished, click **Finish**.</span></span>

## <a name="use-the-security--compliance-center-to-view-safe-links-policies"></a><span data-ttu-id="a1561-190">セキュリティ/コンプライアンス センター&使用して安全なリンク ポリシーを表示する</span><span class="sxs-lookup"><span data-stu-id="a1561-190">Use the Security & Compliance Center to view Safe Links policies</span></span>

1. <span data-ttu-id="a1561-191">セキュリティ/コンプライアンス センター&、**脅威管理ポリシー** ATP の安全なリンク \>  \> **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="a1561-191">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="a1561-192">[安全 **なリンク** ] ページで、一覧からポリシーを選択し、それをクリックします (チェック ボックスはオンにしない)。</span><span class="sxs-lookup"><span data-stu-id="a1561-192">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

   <span data-ttu-id="a1561-193">ポリシーの詳細がフライアウトに表示される</span><span class="sxs-lookup"><span data-stu-id="a1561-193">The policy details appear in a fly out</span></span>

## <a name="use-the-security--compliance-center-to-modify-safe-links-policies"></a><span data-ttu-id="a1561-194">セキュリティ/コンプライアンス センター&使用して安全なリンク ポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="a1561-194">Use the Security & Compliance Center to modify Safe Links policies</span></span>

1. <span data-ttu-id="a1561-195">セキュリティ/コンプライアンス センター&、**脅威管理ポリシー** ATP の安全なリンク \>  \> **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="a1561-195">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="a1561-196">[安全 **なリンク** ] ページで、一覧からポリシーを選択し、それをクリックします (チェック ボックスはオンにしない)。</span><span class="sxs-lookup"><span data-stu-id="a1561-196">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="a1561-197">表示されたポリシーの詳細が表示されたら、[ポリシーの編集] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="a1561-197">In the policy details fly out that appears, click **Edit policy**.</span></span>

<span data-ttu-id="a1561-198">表示されるフライアウトで使用可能な設定は、「セキュリティ/コンプライアンス センターを使用して安全なリンク ポリシーを作成する」セクション& [説明されている設定と同](#use-the-security--compliance-center-to-create-safe-links-policies) じです。</span><span class="sxs-lookup"><span data-stu-id="a1561-198">The available settings in the fly out that appears are identical to those described in the [Use the Security & Compliance Center to create Safe Links policies](#use-the-security--compliance-center-to-create-safe-links-policies) section.</span></span>

<span data-ttu-id="a1561-199">ポリシーを有効または無効にするか、ポリシーの優先順位を設定するには、以下のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a1561-199">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-safe-links-policies"></a><span data-ttu-id="a1561-200">安全なリンク ポリシーを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="a1561-200">Enable or disable Safe Links policies</span></span>

1. <span data-ttu-id="a1561-201">セキュリティ/コンプライアンス センター&、**脅威管理ポリシー** ATP の安全なリンク \>  \> **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="a1561-201">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="a1561-202">[状態] 列の値 **に注意** してください。</span><span class="sxs-lookup"><span data-stu-id="a1561-202">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="a1561-203">ポリシーを無効にするには、左に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="a1561-203">Move the toggle to the left to disable the policy:</span></span> ![ポリシーをオフにする](../../media/scc-toggle-off.png)<span data-ttu-id="a1561-205">.</span><span class="sxs-lookup"><span data-stu-id="a1561-205">.</span></span>

   - <span data-ttu-id="a1561-206">ポリシーを有効にするには、右に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="a1561-206">Move the toggle to the right to enable the policy:</span></span> ![ポリシーを有効にする](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="a1561-208">.</span><span class="sxs-lookup"><span data-stu-id="a1561-208">.</span></span>

### <a name="set-the-priority-of-safe-links-policies"></a><span data-ttu-id="a1561-209">安全なリンク ポリシーの優先度を設定する</span><span class="sxs-lookup"><span data-stu-id="a1561-209">Set the priority of Safe Links policies</span></span>

<span data-ttu-id="a1561-210">既定では、安全なリンク ポリシーには、作成された順序に基づく優先度が設定されます (新しいポリシーは、古いポリシーよりも優先度が低くなります)。</span><span class="sxs-lookup"><span data-stu-id="a1561-210">By default, Safe Links policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="a1561-211">優先度番号が小さいほど、ポリシーの優先度が高くなる (0 が最優先) ことを意味し、ポリシーは優先順位に従って処理されます (優先度の高いポリシーは、優先度の低いポリシーよりも先に処理されます)。</span><span class="sxs-lookup"><span data-stu-id="a1561-211">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="a1561-212">2つのポリシーが同じ優先順位を持つことはできません。最初のポリシーが適用されると、ポリシーの処理は停止します。</span><span class="sxs-lookup"><span data-stu-id="a1561-212">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="a1561-213">優先順位と複数のポリシーを評価し適用する方法の詳細については、「[メール保護の優先順位](how-policies-and-protections-are-combined.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a1561-213">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="a1561-214">安全なリンク ポリシーは、処理順に表示されます (最初のポリシーの **優先度** の値は 0 です)。</span><span class="sxs-lookup"><span data-stu-id="a1561-214">Safe Links policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span>

<span data-ttu-id="a1561-215">**注**: セキュリティ/コンプライアンス センター&、安全なリンク ポリシーの優先度は、作成後にのみ変更できます。</span><span class="sxs-lookup"><span data-stu-id="a1561-215">**Note**: In the Security & Compliance Center, you can only change the priority of the Safe Links policy after you create it.</span></span> <span data-ttu-id="a1561-216">PowerShell では、安全なリンク ルールを作成するときに既定の優先度を上書きできます (既存のルールの優先度に影響を与える可能性があります)。</span><span class="sxs-lookup"><span data-stu-id="a1561-216">In PowerShell, you can override the default priority when you create the safe links rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="a1561-217">ポリシーの優先度を変更するには、リスト内で上下に移動させます (セキュリティ/コンプライアンス センター内で直接、**優先順位** 番号を変更することはできません)。</span><span class="sxs-lookup"><span data-stu-id="a1561-217">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="a1561-218">セキュリティ/コンプライアンス センター&、**脅威管理ポリシー** ATP の安全なリンク \>  \> **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="a1561-218">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="a1561-219">[安全 **なリンク** ] ページで、一覧からポリシーを選択し、それをクリックします (チェック ボックスはオンにしない)。</span><span class="sxs-lookup"><span data-stu-id="a1561-219">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="a1561-220">ポリシーの詳細が表示されたら、使用可能な優先度ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="a1561-220">In the policy details fly out that appears, click the available priority button:</span></span>

   - <span data-ttu-id="a1561-221">優先度の値が **0** の安全なリンク **ポリシー** では、[優先度を下がる]**ボタン** しか使用できません。</span><span class="sxs-lookup"><span data-stu-id="a1561-221">The Safe Links policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="a1561-222">優先度の値が最も低い安全なリンク **ポリシー** ( **たとえば、3)** には、[優先度の引き上げ] **ボタン** しか使用できません。</span><span class="sxs-lookup"><span data-stu-id="a1561-222">The Safe Links policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="a1561-223">3 つ以上の安全なリンク ポリシーがある場合は、優先度の高い値と最も低い値の間のポリシーの [優先度の引き上げ] ボタンと [優先度の下げ] ボタンの **両方を使用** できます。</span><span class="sxs-lookup"><span data-stu-id="a1561-223">If you have three or more Safe Links policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="a1561-224">[優先度 **の引き上げ** ] または **[優先度の下げ** ] をクリックして、[優先度] の **値を変更** します。</span><span class="sxs-lookup"><span data-stu-id="a1561-224">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="a1561-225">完了したら、**[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a1561-225">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-safe-links-policies"></a><span data-ttu-id="a1561-226">セキュリティ/コンプライアンス センター&使用して安全なリンク ポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="a1561-226">Use the Security & Compliance Center to remove Safe Links policies</span></span>

1. <span data-ttu-id="a1561-227">セキュリティ/コンプライアンス センター&、**脅威管理ポリシー** ATP の安全なリンク \>  \> **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="a1561-227">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="a1561-228">[安全 **なリンク** ] ページで、一覧からポリシーを選択し、それをクリックします (チェック ボックスはオンにしない)。</span><span class="sxs-lookup"><span data-stu-id="a1561-228">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="a1561-229">表示されたポリシーの詳細が表示されたら、[ポリシーの削除] をクリックし、表示される警告ダイアログで [はい] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a1561-229">In the policy details fly out that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies"></a><span data-ttu-id="a1561-230">Exchange Online PowerShell またはスタンドアロンの EOP PowerShell を使用して安全なリンク ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="a1561-230">Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Links policies</span></span>

<span data-ttu-id="a1561-231">前述のように、安全なリンク ポリシーは、安全なリンク ポリシーと安全なリンク ルールで構成されます。</span><span class="sxs-lookup"><span data-stu-id="a1561-231">As previously described, a Safe Links policy consists of a safe links policy and a safe links rule.</span></span>

<span data-ttu-id="a1561-232">PowerShell では、安全なリンク ポリシーと安全なリンクルールの違いは明白です。</span><span class="sxs-lookup"><span data-stu-id="a1561-232">In PowerShell, the difference between safe links policies and safe links rules is apparent.</span></span> <span data-ttu-id="a1561-233">**\* -SafeLinksPolicy** コマンドレットを使用して安全なリンク ポリシーを管理し **\* 、-SafeLinksRule** コマンドレットを使用して安全なリンク ルールを管理します。</span><span class="sxs-lookup"><span data-stu-id="a1561-233">You manage safe links policies by using the **\*-SafeLinksPolicy** cmdlets, and you manage safe links rules by using the **\*-SafeLinksRule** cmdlets.</span></span>

- <span data-ttu-id="a1561-234">PowerShell では、最初に安全なリンク ポリシーを作成してから、ルールが適用されるポリシーを識別する安全なリンク ルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="a1561-234">In PowerShell, you create the safe links policy first, then you create the safe links rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="a1561-235">PowerShell では、安全なリンク ポリシーと安全なリンクルールの設定を個別に変更します。</span><span class="sxs-lookup"><span data-stu-id="a1561-235">In PowerShell, you modify the settings in the safe links policy and the safe links rule separately.</span></span>
- <span data-ttu-id="a1561-236">PowerShell から安全なリンク ポリシーを削除しても、対応する安全なリンクルールは自動的には削除されません。その逆も同様です。</span><span class="sxs-lookup"><span data-stu-id="a1561-236">When you remove a safe links policy from PowerShell, the corresponding safe links rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-safe-links-policies"></a><span data-ttu-id="a1561-237">PowerShell を使用して安全なリンク ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="a1561-237">Use PowerShell to create Safe Links policies</span></span>

<span data-ttu-id="a1561-238">PowerShell で安全なリンク ポリシーを作成するには、次の 2 つの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="a1561-238">Creating a Safe Links policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="a1561-239">安全なリンク ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="a1561-239">Create the safe links policy.</span></span>
2. <span data-ttu-id="a1561-240">ルールが適用される安全なリンク ポリシーを指定する安全なリンク ルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="a1561-240">Create the safe links rule that specifies the safe links policy that the rule applies to.</span></span>

 <span data-ttu-id="a1561-241">**注**:</span><span class="sxs-lookup"><span data-stu-id="a1561-241">**Notes**:</span></span>

- <span data-ttu-id="a1561-242">新しい安全リンク ルールを作成し、関連付けされていない既存の安全なリンク ポリシーをそのルールに割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="a1561-242">You can create a new safe links rule and assign an existing, unassociated safe links policy to it.</span></span> <span data-ttu-id="a1561-243">安全なリンク ルールは、複数の安全なリンク ポリシーに関連付け設定できます。</span><span class="sxs-lookup"><span data-stu-id="a1561-243">A safe links rule can't be associated with more than one safe links policy.</span></span>

- <span data-ttu-id="a1561-244">ポリシーを作成するまでセキュリティ & コンプライアンス センターでは使用できない、PowerShell の新しい安全なリンク ポリシーに関する次の設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="a1561-244">You can configure the following settings on new safe links policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="a1561-245">無効な新しいポリシーを作成します `$false` **(New-SafeLinksRule コマンドレットで有効**)。</span><span class="sxs-lookup"><span data-stu-id="a1561-245">Create the new policy as disabled (_Enabled_ `$false` on the **New-SafeLinksRule** cmdlet).</span></span>
  - <span data-ttu-id="a1561-246"> _\<Number\>_ **New-SafeLinksRule** コマンドレットで、作成時のポリシーの優先度 (優先度) を設定します。</span><span class="sxs-lookup"><span data-stu-id="a1561-246">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-SafeLinksRule** cmdlet).</span></span>

- <span data-ttu-id="a1561-247">PowerShell で作成した新しい安全なリンク ポリシーは、ポリシーを安全なリンク ルールに割り当てるまで、セキュリティ & コンプライアンス センターに表示されません。</span><span class="sxs-lookup"><span data-stu-id="a1561-247">A new safe links policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a safe links rule.</span></span>

#### <a name="step-1-use-powershell-to-create-a-safe-links-policy"></a><span data-ttu-id="a1561-248">手順 1: PowerShell を使用して安全なリンク ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="a1561-248">Step 1: Use PowerShell to create a safe links policy</span></span>

<span data-ttu-id="a1561-249">安全なリンク ポリシーを作成するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="a1561-249">To create a safe links policy, use this syntax:</span></span>

```PowerShell
New-SafeLinksPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-IsEnabled <$true | $false>] [-EnableSafeLinksForTeams <$true | $false>] [-ScanUrls <$true | $false>] [-DeliverMessageAfterScan <$true | $false>] [-EnableForInternalSenders <$true | $false>] [-DoNotAllowClickThrough <$true | $false>] [-DoNotTrackUserClicks <$true | $false>] [-DoNotRewriteUrls "Entry1","Entry2",..."EntryN"]
```

<span data-ttu-id="a1561-250">**注**:</span><span class="sxs-lookup"><span data-stu-id="a1561-250">**Notes**:</span></span>

- <span data-ttu-id="a1561-251">_DoNotRewriteUrls_ パラメーターに使用するエントリ構文の詳細については、「次の URL を書き換えない」の一覧のエントリ構文を [参照してください](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)。</span><span class="sxs-lookup"><span data-stu-id="a1561-251">For details about the entry syntax to use for the _DoNotRewriteUrls_ parameter, see [Entry syntax for the "Do not rewrite the following URLs" list](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span></span>

- <span data-ttu-id="a1561-252">**Set-SafeLinksPolicy** コマンドレットを使用して既存の安全なリンク ポリシーを変更するときに _DoNotRewriteUrls_ パラメーターに使用できるその他の構文については、この記事の後半の [「PowerShell](#use-powershell-to-modify-safe-links-policies)を使用して安全なリンク ポリシーを変更する」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a1561-252">For additional syntax that you can use for the _DoNotRewriteUrls_ parameter when you modify existing safe links policies by using the **Set-SafeLinksPolicy** cmdlet, see the [Use PowerShell to modify safe links policies](#use-powershell-to-modify-safe-links-policies) section later in this article.</span></span>

<span data-ttu-id="a1561-253">この例では、Contoso All という名前の安全なリンク ポリシーを次の値で作成します。</span><span class="sxs-lookup"><span data-stu-id="a1561-253">This example creates a safe links policy named Contoso All with the following values:</span></span>

- <span data-ttu-id="a1561-254">電子メール メッセージで URL のスキャンと書き換えを有効にする。</span><span class="sxs-lookup"><span data-stu-id="a1561-254">Turn on URL scanning and rewriting in email messages.</span></span>
- <span data-ttu-id="a1561-255">Teams で URL スキャンを有効にする (TAP プレビューのみ)。</span><span class="sxs-lookup"><span data-stu-id="a1561-255">Turn on URL scanning in Teams (TAP Preview only).</span></span>
- <span data-ttu-id="a1561-256">クリックされた URL のリアルタイム スキャン (ファイルをポイントするクリックされたリンクを含む) を有効にする。</span><span class="sxs-lookup"><span data-stu-id="a1561-256">Turn on real-time scanning of clicked URLs, including clicked links that point to files.</span></span>
- <span data-ttu-id="a1561-257">メッセージを配信する前に、URL のスキャンが完了するのを待ちます。</span><span class="sxs-lookup"><span data-stu-id="a1561-257">Wait for URL scanning to complete before delivering the message.</span></span>
- <span data-ttu-id="a1561-258">内部メッセージの URL のスキャンと書き換えを有効にする。</span><span class="sxs-lookup"><span data-stu-id="a1561-258">Turn on URL scanning and rewriting for internal messages.</span></span>
- <span data-ttu-id="a1561-259">安全なリンク保護に関連するユーザー クリックを追跡します _(DoNotTrackUserClicks_ パラメーターは使用していないので、既定値は $false です。つまり、ユーザーのクリックが追跡されます)。</span><span class="sxs-lookup"><span data-stu-id="a1561-259">Track user clicks related to Safe Links protection (we aren't using the _DoNotTrackUserClicks_ parameter, and the default value is $false, which means user clicks are tracked).</span></span>
- <span data-ttu-id="a1561-260">ユーザーがクリックして元の URL にアクセスできない。</span><span class="sxs-lookup"><span data-stu-id="a1561-260">Do not allow users to click through to the original URL.</span></span>

```PowerShell
New-SafeLinksPolicy -Name "Contoso All" -IsEnabled $true -EnableSafeLinksForTeams $true -ScanUrls $true -DeliverMessageAfterScan $true -EnableForInternalSenders $true -DoNotAllowClickThrough $true
```

<span data-ttu-id="a1561-261">構文およびパラメーターの詳細については [、「New-SafeLinksPolicy」を参照してください](https://docs.microsoft.com/powershell/module/exchange/new-safelinkspolicy)。</span><span class="sxs-lookup"><span data-stu-id="a1561-261">For detailed syntax and parameter information, see [New-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safelinkspolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-a-safe-links-rule"></a><span data-ttu-id="a1561-262">手順 2: PowerShell を使用して安全なリンク ルールを作成する</span><span class="sxs-lookup"><span data-stu-id="a1561-262">Step 2: Use PowerShell to create a safe links rule</span></span>

<span data-ttu-id="a1561-263">安全なリンク ルールを作成するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="a1561-263">To create a safe links rule, use this syntax:</span></span>

```PowerShell
New-SafeLinksRule -Name "<RuleName>" -SafeLinksPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

<span data-ttu-id="a1561-264">この例では、Contoso All という名前の安全なリンク ルールを次の条件で作成します。</span><span class="sxs-lookup"><span data-stu-id="a1561-264">This example creates a safe links rule named Contoso All with the following conditions:</span></span>

- <span data-ttu-id="a1561-265">ルールは、Contoso All という名前の安全なリンク ポリシーに関連付けられている。</span><span class="sxs-lookup"><span data-stu-id="a1561-265">The rule is associated with the safe links policy named Contoso All.</span></span>
- <span data-ttu-id="a1561-266">ルールは、ドメイン内のすべての受信者にcontoso.comされます。</span><span class="sxs-lookup"><span data-stu-id="a1561-266">The rule applies to all recipients in the contoso.com domain.</span></span>
- <span data-ttu-id="a1561-267">_Priority_ パラメーターを使用していないので、既定の優先度が使用されます。</span><span class="sxs-lookup"><span data-stu-id="a1561-267">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>
- <span data-ttu-id="a1561-268">ルールは有効です _(Enabled_ パラメーターは使用しません。既定値は有効です `$true` )。</span><span class="sxs-lookup"><span data-stu-id="a1561-268">The rule is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>

```powershell
New-SafeLinksRule -Name "Contoso All" -SafeLinksPolicy "Contoso All" -RecipientDomainIs contoso.com
```

<span data-ttu-id="a1561-269">構文およびパラメーターの詳細については [、「New-SafeLinksRule」を参照してください](https://docs.microsoft.com/powershell/module/exchange/new-safelinksrule)。</span><span class="sxs-lookup"><span data-stu-id="a1561-269">For detailed syntax and parameter information, see [New-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/new-safelinksrule).</span></span>

### <a name="use-powershell-to-view-safe-links-policies"></a><span data-ttu-id="a1561-270">PowerShell を使用して安全なリンク ポリシーを表示する</span><span class="sxs-lookup"><span data-stu-id="a1561-270">Use PowerShell to view safe links policies</span></span>

<span data-ttu-id="a1561-271">既存の安全なリンク ポリシーを表示するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="a1561-271">To view existing safe links policies, use the following syntax:</span></span>

```PowerShell
Get-SafeLinksPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="a1561-272">この例では、すべての安全なリンク ポリシーの要約リストを返します。</span><span class="sxs-lookup"><span data-stu-id="a1561-272">This example returns a summary list of all safe links policies.</span></span>

```PowerShell
Get-SafeLinksPolicy | Format-Table Name
```

<span data-ttu-id="a1561-273">この例では、Contoso Executives という名前の安全なリンク ポリシーの詳細情報を返します。</span><span class="sxs-lookup"><span data-stu-id="a1561-273">This example returns detailed information for the safe links policy named Contoso Executives.</span></span>

```PowerShell
Get-SafeLinksPolicy -Identity "Contoso Executives"
```

<span data-ttu-id="a1561-274">構文およびパラメーターの詳細については [、「Get-SafeLinksPolicy」を参照してください](https://docs.microsoft.com/powershell/module/exchange/get-safelinkspolicy)。</span><span class="sxs-lookup"><span data-stu-id="a1561-274">For detailed syntax and parameter information, see [Get-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/get-safelinkspolicy).</span></span>

### <a name="use-powershell-to-view-safe-links-rules"></a><span data-ttu-id="a1561-275">PowerShell を使用して安全なリンク ルールを表示する</span><span class="sxs-lookup"><span data-stu-id="a1561-275">Use PowerShell to view safe links rules</span></span>

<span data-ttu-id="a1561-276">既存の安全なリンク ルールを表示するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="a1561-276">To view existing safe links rules, use the following syntax:</span></span>

```PowerShell
Get-SafeLinksRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="a1561-277">この例では、すべての安全なリンク ルールの要約リストを返します。</span><span class="sxs-lookup"><span data-stu-id="a1561-277">This example returns a summary list of all safe links rules.</span></span>

```PowerShell
Get-SafeLinksRule | Format-Table Name,State
```

<span data-ttu-id="a1561-278">ルールを有効または無効にしてリストをフィルター処理するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="a1561-278">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-SafeLinksRule -State Disabled
```

```PowerShell
Get-SafeLinksRule -State Enabled
```

<span data-ttu-id="a1561-279">この例では、Contoso Executives という名前の安全なリンク ルールの詳細情報を返します。</span><span class="sxs-lookup"><span data-stu-id="a1561-279">This example returns detailed information for the safe links rule named Contoso Executives.</span></span>

```PowerShell
Get-SafeLinksRule -Identity "Contoso Executives"
```

<span data-ttu-id="a1561-280">構文およびパラメーターの詳細については [、「Get-SafeLinksRule」を参照してください](https://docs.microsoft.com/powershell/module/exchange/get-safelinksrule)。</span><span class="sxs-lookup"><span data-stu-id="a1561-280">For detailed syntax and parameter information, see [Get-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/get-safelinksrule).</span></span>

### <a name="use-powershell-to-modify-safe-links-policies"></a><span data-ttu-id="a1561-281">PowerShell を使用して安全なリンク ポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="a1561-281">Use PowerShell to modify safe links policies</span></span>

<span data-ttu-id="a1561-282">PowerShell で安全なリンク ポリシーの名前を変更することはできません **(Set-SafeLinksPolicy** コマンドレットには _Name_ パラメーターはありません)。</span><span class="sxs-lookup"><span data-stu-id="a1561-282">You can't rename a safe links policy in PowerShell (the **Set-SafeLinksPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="a1561-283">セキュリティ/コンプライアンス センターで安全なリンク ポリシーの名前を変更&、安全なリンクルールの名前を変更 _するのみです_。</span><span class="sxs-lookup"><span data-stu-id="a1561-283">When you rename a Safe Links policy in the Security & Compliance Center, you're only renaming the safe links _rule_.</span></span>

<span data-ttu-id="a1561-284">PowerShell で安全なリンク ポリシーを変更するための唯一の追加の考慮事項は _、DoNotRewriteUrls_ パラメーターに使用できる構文です (「次の [URL](atp-safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)を書き換えない」の一覧)。</span><span class="sxs-lookup"><span data-stu-id="a1561-284">The only additional consideration for modifying safe links policies in PowerShell is the available syntax for the _DoNotRewriteUrls_ parameter (the ["Do not rewrite the following URLs" list](atp-safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)):</span></span>

- <span data-ttu-id="a1561-285">既存のエントリを置き換える値を追加するには、次の構文を使用します `"Entry1","Entry2,..."EntryN"` 。</span><span class="sxs-lookup"><span data-stu-id="a1561-285">To add values that will replace any existing entries, use the following syntax: `"Entry1","Entry2,..."EntryN"`.</span></span>
- <span data-ttu-id="a1561-286">他の既存のエントリに影響を及ぼさずに値を追加または削除するには、次の構文を使用します。 `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`</span><span class="sxs-lookup"><span data-stu-id="a1561-286">To add or remove values without affecting other existing entries, use the following syntax: `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`</span></span>

<span data-ttu-id="a1561-287">それ以外の場合は、「手順 [1: PowerShell](#step-1-use-powershell-to-create-a-safe-links-policy) を使用して安全なリンク ポリシーを作成する」セクションで説明したように、安全なリンク ポリシーを作成する場合と同じ設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="a1561-287">Otherwise, the same settings are available when you create a safe links policy as described in the [Step 1: Use PowerShell to create a safe links policy](#step-1-use-powershell-to-create-a-safe-links-policy) section earlier in this article.</span></span>

<span data-ttu-id="a1561-288">安全なリンク ポリシーを変更するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="a1561-288">To modify a safe links policy, use this syntax:</span></span>

```PowerShell
Set-SafeLinksPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="a1561-289">構文およびパラメーターの詳細については [、「Set-SafeLinksPolicy」を参照してください](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy)。</span><span class="sxs-lookup"><span data-stu-id="a1561-289">For detailed syntax and parameter information, see [Set-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy).</span></span>

### <a name="use-powershell-to-modify-safe-links-rules"></a><span data-ttu-id="a1561-290">PowerShell を使用して安全なリンク ルールを変更する</span><span class="sxs-lookup"><span data-stu-id="a1561-290">Use PowerShell to modify safe links rules</span></span>

<span data-ttu-id="a1561-291">PowerShell で安全なリンク ルールを変更する場合に使用できない唯一の設定は、無効にされたルールを作成できる _Enabled_ パラメーターです。</span><span class="sxs-lookup"><span data-stu-id="a1561-291">The only setting that's not available when you modify a safe links rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="a1561-292">既存の安全なリンク ルールを有効または無効にするには、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a1561-292">To enable or disable existing safe links rules, see the next section.</span></span>

<span data-ttu-id="a1561-293">それ以外の場合は、「手順 [2: PowerShell](#step-2-use-powershell-to-create-a-safe-links-rule) を使用して安全なリンク ルールを作成する」セクションで説明したルールを作成する場合と同じ設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="a1561-293">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create a safe links rule](#step-2-use-powershell-to-create-a-safe-links-rule) section earlier in this article.</span></span>

<span data-ttu-id="a1561-294">安全なリンク ルールを変更するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="a1561-294">To modify a safe links rule, use this syntax:</span></span>

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="a1561-295">構文およびパラメーターの詳細については [、「Set-SafeLinksRule」を参照してください](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule)。</span><span class="sxs-lookup"><span data-stu-id="a1561-295">For detailed syntax and parameter information, see [Set-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-safe-links-rules"></a><span data-ttu-id="a1561-296">PowerShell を使用して安全なリンク ルールを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="a1561-296">Use PowerShell to enable or disable safe links rules</span></span>

<span data-ttu-id="a1561-297">PowerShell で安全なリンク ルールを有効または無効にすると、安全なリンクポリシー全体 (安全なリンクルールと割り当てられた安全なリンク ポリシー) を有効または無効にできます。</span><span class="sxs-lookup"><span data-stu-id="a1561-297">Enabling or disabling a safe links rule in PowerShell enables or disables the whole Safe Links policy (the safe links rule and the assigned safe links policy).</span></span>

<span data-ttu-id="a1561-298">PowerShell で安全なリンク ルールを有効または無効にするには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="a1561-298">To enable or disable a safe links rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-SafeLinksRule | Disable-SafeLinksRule> -Identity "<RuleName>"
```

<span data-ttu-id="a1561-299">この例では、Marketing Department という名前の安全なリンク ルールを無効にします。</span><span class="sxs-lookup"><span data-stu-id="a1561-299">This example disables the safe links rule named Marketing Department.</span></span>

```PowerShell
Disable-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="a1561-300">この例では、同じルールを有効化します。</span><span class="sxs-lookup"><span data-stu-id="a1561-300">This example enables same rule.</span></span>

```PowerShell
Enable-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="a1561-301">構文およびパラメーターの詳細については [、「Enable-SafeLinksRule」](https://docs.microsoft.com/powershell/module/exchange/enable-safelinksrule) および [「Disable-SafeLinksRule」を参照してください](https://docs.microsoft.com/powershell/module/exchange/disable-safelinksrule)。</span><span class="sxs-lookup"><span data-stu-id="a1561-301">For detailed syntax and parameter information, see [Enable-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/enable-safelinksrule) and [Disable-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/disable-safelinksrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-safe-links-rules"></a><span data-ttu-id="a1561-302">PowerShell を使用して安全なリンク ルールの優先度を設定する</span><span class="sxs-lookup"><span data-stu-id="a1561-302">Use PowerShell to set the priority of safe links rules</span></span>

<span data-ttu-id="a1561-303">ルールに設定できる優先度の最高値値は 0 です。</span><span class="sxs-lookup"><span data-stu-id="a1561-303">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="a1561-304">設定できる最低値はルールの数に依存します。</span><span class="sxs-lookup"><span data-stu-id="a1561-304">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="a1561-305">たとえば、ルールが五つある場合、使用できる優先度の値は 0 から 4 です。</span><span class="sxs-lookup"><span data-stu-id="a1561-305">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="a1561-306">既存の一つのルールの優先度を変更すると、他のルールにも連鎖的な影響が起こりえます。</span><span class="sxs-lookup"><span data-stu-id="a1561-306">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="a1561-307">たとえば、カスタム ルールが 5 つあって (優先度 0 から 4)、1 つのルールの優先度を 2 に変更した場合には、既存の優先度 2 のルールは優先度 3 に変更され、優先度 3 は優先度 4 に変更されます。</span><span class="sxs-lookup"><span data-stu-id="a1561-307">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="a1561-308">PowerShell で安全なリンク ルールの優先度を設定するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="a1561-308">To set the priority of a safe links rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="a1561-p123">この例では、Marketing Department というルールの優先度を 2 に設定しています。優先度が 2 以下のすべての既存のルールは、優先度が 1 ずつ下がります (優先度番号が 1 ずつ増加します)。</span><span class="sxs-lookup"><span data-stu-id="a1561-p123">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-SafeLinksRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="a1561-311">**注**: 新しいルールを作成するときに優先度を設定するには、代わりに **New-SafeLinksRule** コマンドレットの _Priority_ パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="a1561-311">**Note**: To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-SafeLinksRule** cmdlet instead.</span></span>

<span data-ttu-id="a1561-312">構文およびパラメーターの詳細については [、「Set-SafeLinksRule」を参照してください](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule)。</span><span class="sxs-lookup"><span data-stu-id="a1561-312">For detailed syntax and parameter information, see [Set-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule).</span></span>

### <a name="use-powershell-to-remove-safe-links-policies"></a><span data-ttu-id="a1561-313">PowerShell を使用して安全なリンク ポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="a1561-313">Use PowerShell to remove safe links policies</span></span>

<span data-ttu-id="a1561-314">PowerShell を使用して安全なリンク ポリシーを削除する場合、対応する安全なリンクルールは削除されません。</span><span class="sxs-lookup"><span data-stu-id="a1561-314">When you use PowerShell to remove a safe links policy, the corresponding safe links rule isn't removed.</span></span>

<span data-ttu-id="a1561-315">PowerShell で安全なリンク ポリシーを削除するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="a1561-315">To remove a safe links policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeLinksPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="a1561-316">この例では、Marketing Department という名前の安全なリンク ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="a1561-316">This example removes the safe links policy named Marketing Department.</span></span>

```PowerShell
Remove-SafeLinksPolicy -Identity "Marketing Department"
```

<span data-ttu-id="a1561-317">構文およびパラメーターの詳細については [、「Remove-SafeLinksPolicy」を参照してください](https://docs.microsoft.com/powershell/module/exchange/remove-safelinkspolicy)。</span><span class="sxs-lookup"><span data-stu-id="a1561-317">For detailed syntax and parameter information, see [Remove-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-safelinkspolicy).</span></span>

### <a name="use-powershell-to-remove-safe-links-rules"></a><span data-ttu-id="a1561-318">PowerShell を使用して安全なリンク ルールを削除する</span><span class="sxs-lookup"><span data-stu-id="a1561-318">Use PowerShell to remove safe links rules</span></span>

<span data-ttu-id="a1561-319">PowerShell を使用して安全なリンク ルールを削除する場合、対応する安全なリンク ポリシーは削除されません。</span><span class="sxs-lookup"><span data-stu-id="a1561-319">When you use PowerShell to remove a safe links rule, the corresponding safe links policy isn't removed.</span></span>

<span data-ttu-id="a1561-320">PowerShell で安全なリンク ルールを削除するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="a1561-320">To remove a safe links rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeLinksRule -Identity "<PolicyName>"
```

<span data-ttu-id="a1561-321">この例では、Marketing Department という名前の安全なリンク ルールを削除します。</span><span class="sxs-lookup"><span data-stu-id="a1561-321">This example removes the safe links rule named Marketing Department.</span></span>

```PowerShell
Remove-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="a1561-322">構文およびパラメーターの詳細については [、「Remove-SafeLinksRule」を参照してください](https://docs.microsoft.com/powershell/module/exchange/remove-safelinksrule)。</span><span class="sxs-lookup"><span data-stu-id="a1561-322">For detailed syntax and parameter information, see [Remove-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/remove-safelinksrule).</span></span>

<span data-ttu-id="a1561-323">安全なリンクがメッセージをスキャンしているのを確認するには、365 レポートで利用可能な Microsoft Defender Office確認します。</span><span class="sxs-lookup"><span data-stu-id="a1561-323">To verify that Safe Links is scanning messages, check the available Microsoft Defender for Office 365 reports.</span></span> <span data-ttu-id="a1561-324">詳細については、「Defender [for Office 365](view-reports-for-atp.md) のレポートを表示する」および「セキュリティ/コンプライアンス センターでエクスプローラー [&参照してください](threat-explorer.md)。</span><span class="sxs-lookup"><span data-stu-id="a1561-324">For more information, see [View reports for Defender for Office 365](view-reports-for-atp.md) and [Use Explorer in the Security & Compliance Center](threat-explorer.md).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="a1561-325">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="a1561-325">How do you know these procedures worked?</span></span>

<span data-ttu-id="a1561-326">安全なリンク ポリシーが正常に作成、変更、または削除されたことを確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="a1561-326">To verify that you've successfully created, modified, or removed Safe Links policies, do any of the following steps:</span></span>

- <span data-ttu-id="a1561-327">セキュリティ/コンプライアンス センター&、**脅威管理ポリシー** ATP の安全なリンク \>  \> **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="a1561-327">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span> <span data-ttu-id="a1561-328">ポリシーの一覧、その状態の値、 **および優先度** の値を **確認** します。</span><span class="sxs-lookup"><span data-stu-id="a1561-328">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="a1561-329">詳細を表示するには、一覧からポリシーを選択し、詳細をフライアウトで表示します。</span><span class="sxs-lookup"><span data-stu-id="a1561-329">To view more details, select the policy from the list, and view the details in the fly out.</span></span>

- <span data-ttu-id="a1561-330">Exchange Online PowerShell または Exchange Online Protection PowerShell で、ポリシーまたはルールの名前に置き換え、次のコマンドを実行して、設定 \<Name\> を確認します。</span><span class="sxs-lookup"><span data-stu-id="a1561-330">In Exchange Online PowerShell or Exchange Online Protection PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-SafeLinksPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-SafeLinksRule -Identity "<Name>"
  ```
