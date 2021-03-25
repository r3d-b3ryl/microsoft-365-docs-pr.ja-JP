---
title: Microsoft Defender で安全なリンク ポリシーを設定する (Office 365)
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
description: 管理者は、Microsoft Defender for microsoft Defender for Office 365 のセーフ リンク ポリシーとグローバルセーフ リンクの設定を表示、作成、変更、および削除する方法をOfficeできます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c8b2cb8b57dcf630b3e07ac387e96ab099ca7403
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205619"
---
# <a name="set-up-safe-links-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="02182-103">Microsoft Defender で安全なリンク ポリシーを設定する (Office 365)</span><span class="sxs-lookup"><span data-stu-id="02182-103">Set up Safe Links policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="02182-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="02182-104">**Applies to**</span></span>
- [<span data-ttu-id="02182-105">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="02182-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="02182-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="02182-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> <span data-ttu-id="02182-107">この記事は、[Microsoft Defender for Office 365](defender-for-office-365.md) をご利用の法人のお客様を対象としています。</span><span class="sxs-lookup"><span data-stu-id="02182-107">This article is intended for business customers who have [Microsoft Defender for Office 365](defender-for-office-365.md).</span></span> <span data-ttu-id="02182-108">Outlook で Safelinks に関する情報を探しているホーム ユーザーの場合は、「Advanced [Outlook.com セキュリティ」を参照してください](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)。</span><span class="sxs-lookup"><span data-stu-id="02182-108">If you are a home user looking for information about Safelinks in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="02182-109">セーフ リンクは [、Microsoft Defender for Office 365](defender-for-office-365.md) の機能で、メール フロー内の受信電子メール メッセージの URL スキャンと、電子メール メッセージ内の URL とリンクのクリック検証の時間を提供します。</span><span class="sxs-lookup"><span data-stu-id="02182-109">Safe Links is a feature in [Microsoft Defender for Office 365](defender-for-office-365.md) that provides URL scanning of inbound email messages in mail flow, and time of click verification of URLs and links in email messages and in other locations.</span></span> <span data-ttu-id="02182-110">詳細については [、「Safe Links in Microsoft Defender for microsoft Defender for Office 365」を参照してください](safe-links.md)。</span><span class="sxs-lookup"><span data-stu-id="02182-110">For more information, see [Safe Links in Microsoft Defender for Office 365](safe-links.md).</span></span>

<span data-ttu-id="02182-111">組み込みまたは既定のセーフ リンク ポリシーはありません。</span><span class="sxs-lookup"><span data-stu-id="02182-111">There's no built-in or default Safe Links policy.</span></span> <span data-ttu-id="02182-112">URL のセーフ リンク スキャンを取得するには、この記事の説明に従って、1 つ以上のセーフ リンク ポリシーを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="02182-112">To get Safe Links scanning of URLs, you need to create one or more Safe Links policies as described in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="02182-113">セーフ リンク ポリシー以外のセーフ **リンク保護の** グローバル設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="02182-113">You configure the global settings for Safe Links protection **outside** of Safe Links policies.</span></span> <span data-ttu-id="02182-114">手順については [、「Configure global settings for Safe Links in Microsoft Defender for Office 365」 を参照してください](configure-global-settings-for-safe-links.md)。</span><span class="sxs-lookup"><span data-stu-id="02182-114">For instructions, see [Configure global settings for Safe Links in Microsoft Defender for Office 365](configure-global-settings-for-safe-links.md).</span></span>

<span data-ttu-id="02182-115">セーフ リンク ポリシーは、セキュリティ & コンプライアンス センターまたは PowerShell で構成できます (Exchange Online のメールボックスを持つ対象となる Microsoft 365 組織の場合は Exchange Online PowerShell、Exchange Online メールボックスのない組織ではスタンドアロンの EOP PowerShell、Microsoft Defender では Office 365 アドオン サブスクリプション)。</span><span class="sxs-lookup"><span data-stu-id="02182-115">You can configure Safe Links policies in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Microsoft Defender for Office 365 add-on subscriptions).</span></span>

<span data-ttu-id="02182-116">セーフ リンク ポリシーの基本的な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="02182-116">The basic elements of a Safe Links policy are:</span></span>

- <span data-ttu-id="02182-117">安全なリンク **ポリシー:**[安全なリンクの保護] をオンにし、リアルタイムの URL スキャンを有効にし、メッセージを配信する前にリアルタイム スキャンが完了するのを待つかどうかを指定し、内部メッセージのスキャンをオンにし、URL のユーザークリックを追跡するかどうかを指定し、ユーザーが元の URL へのトラフをクリックできるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="02182-117">**The safe links policy**: Turn on Safe Links protection, turn on real-time URL scanning, specify whether to wait for real-time scanning to complete before delivering the message, turn on scanning for internal messages, specify whether to track user clicks on URLs, and specify whether to allow users to click trough to the original URL.</span></span>
- <span data-ttu-id="02182-118">**安全なリンクルール**: 優先度と受信者のフィルター (ポリシーが適用されるユーザー) を指定します。</span><span class="sxs-lookup"><span data-stu-id="02182-118">**The safe links rule**: Specifies the priority and recipient filters (who the policy applies to).</span></span>

<span data-ttu-id="02182-119">セキュリティ コンプライアンス センターでセーフ リンク ポリシーを管理する場合、これら 2 つの要素の違いは&ではありません。</span><span class="sxs-lookup"><span data-stu-id="02182-119">The difference between these two elements isn't obvious when you manage Safe Links polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="02182-120">セーフ リンク ポリシーを作成すると、両方に同じ名前を使用して、安全なリンク ルールと関連付けられた安全なリンク ポリシーを同時に作成します。</span><span class="sxs-lookup"><span data-stu-id="02182-120">When you create a Safe Links policy, you're actually creating a safe links rule and the associated safe links policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="02182-121">セーフ リンク ポリシーを変更すると、名前、優先度、有効または無効、および受信者フィルターに関連する設定によって、セーフ リンク ルールが変更されます。</span><span class="sxs-lookup"><span data-stu-id="02182-121">When you modify a Safe Links policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the safe links rule.</span></span> <span data-ttu-id="02182-122">その他の設定はすべて、関連付けられたセーフ リンク ポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="02182-122">All other settings modify the associated safe links policy.</span></span>
- <span data-ttu-id="02182-123">セーフ リンク ポリシーを削除すると、セーフ リンク ルールと関連付けられたセーフ リンク ポリシーが削除されます。</span><span class="sxs-lookup"><span data-stu-id="02182-123">When you remove a Safe Links policy, the safe links rule and the associated safe links policy are removed.</span></span>

<span data-ttu-id="02182-124">Exchange Online PowerShell またはスタンドアロン EOP PowerShell では、ポリシーとルールを個別に管理します。</span><span class="sxs-lookup"><span data-stu-id="02182-124">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="02182-125">詳細については、この記事の後半の [「Exchange Online PowerShell](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) またはスタンドアロン EOP PowerShell を使用して安全なリンク ポリシーを構成する」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="02182-125">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Links policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) section later in this article.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="02182-126">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="02182-126">What do you need to know before you begin?</span></span>

- <span data-ttu-id="02182-127"><https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="02182-127">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="02182-128">[安全なリンク] ページに **直接移動するには** 、 を使用します <https://protection.office.com/safelinksv2> 。</span><span class="sxs-lookup"><span data-stu-id="02182-128">To go directly to the **Safe Links** page, use <https://protection.office.com/safelinksv2>.</span></span>

- <span data-ttu-id="02182-129">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02182-129">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="02182-130">スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02182-130">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="02182-131">この記事の手順を実行するには、アクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="02182-131">You need to be assigned permissions before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="02182-132">安全なリンク ポリシーを作成、変更、および削除するには、セキュリティ & コンプライアンス センターの組織の管理またはセキュリティ管理者の役割グループのメンバーであり、Exchange Online の組織の管理役割グループのメンバーである必要があります。  </span><span class="sxs-lookup"><span data-stu-id="02182-132">To create, modify, and delete Safe Links policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Security & Compliance Center **and** a member of the **Organization Management** role group in Exchange Online.</span></span>
  - <span data-ttu-id="02182-133">セーフ リンク ポリシーへの読み取り専用アクセスでは、グローバル リーダーまたはセキュリティリーダーの役割グループ **のメンバーである** 必要があります。</span><span class="sxs-lookup"><span data-stu-id="02182-133">For read-only access to Safe Links policies, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="02182-134">詳細については、「セキュリティ コンプライアンス [センターのアクセス許可」と「exchange Online &アクセス](permissions-in-the-security-and-compliance-center.md) 許可 [」を参照してください](/exchange/permissions-exo/permissions-exo)。</span><span class="sxs-lookup"><span data-stu-id="02182-134">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) and [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  > 
  > - <span data-ttu-id="02182-135">Microsoft 365 管理センターで、対応する Azure Active Directory の役割にユーザーを追加すると、ユーザーには、セキュリティ/コンプライアンス センター の必要なアクセス許可 _および_ Microsoft 365 のその他の機能に必要なアクセス許可が付与されます。</span><span class="sxs-lookup"><span data-stu-id="02182-135">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="02182-136">詳細については、「[管理者の役割について](../../admin/add-users/about-admin-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02182-136">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  <span data-ttu-id="02182-137">.</span><span class="sxs-lookup"><span data-stu-id="02182-137">.</span></span> <span data-ttu-id="02182-138">- [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) **の [組織の管理の** 表示のみ] 役割グループは、この機能への読み取り専用アクセスも提供します。</span><span class="sxs-lookup"><span data-stu-id="02182-138">- The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="02182-139">セーフ リンク ポリシーの推奨設定については、「セーフ リンク ポリシー [設定」を参照してください](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings)。</span><span class="sxs-lookup"><span data-stu-id="02182-139">For our recommended settings for Safe Links policies, see [Safe Links policy settings](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings).</span></span>

- <span data-ttu-id="02182-140">新しいポリシーまたは更新されたポリシーを適用するには、最大 30 分かかります。</span><span class="sxs-lookup"><span data-stu-id="02182-140">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="02182-141">[新しい機能は、Microsoft Defender に継続的に 365 Officeされています](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365)。</span><span class="sxs-lookup"><span data-stu-id="02182-141">[New features are continually being added to Microsoft Defender for Office 365](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="02182-142">新しい機能が追加された場合、既存のセーフ リンク ポリシーを調整する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="02182-142">As new features are added, you may need to make adjustments to your existing Safe Links policies.</span></span>

## <a name="use-the-security--compliance-center-to-create-safe-links-policies"></a><span data-ttu-id="02182-143">コンプライアンス センターのセキュリティ &を使用して、安全なリンク ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="02182-143">Use the Security & Compliance Center to create Safe Links policies</span></span>

<span data-ttu-id="02182-144">セキュリティ & コンプライアンス センターでカスタムのセーフ リンク ポリシーを作成すると、両方に同じ名前を使用して、安全なリンク ルールと関連付けられた安全なリンク ポリシーが同時に作成されます。</span><span class="sxs-lookup"><span data-stu-id="02182-144">Creating a custom Safe Links policy in the Security & Compliance Center creates the safe links rule and the associated safe links policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="02182-145">セキュリティ 管理コンプライアンス センター&、脅威管理ポリシー  \> ATP **セーフ リンク** \> **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="02182-145">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="02182-146">[安全な **リンク] ページで** 、[作成] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="02182-146">On the **Safe Links** page, click **Create**.</span></span>

3. <span data-ttu-id="02182-147">[ **新しいセーフ リンク] ポリシー ウィザード** が開きます。</span><span class="sxs-lookup"><span data-stu-id="02182-147">The **New Safe Links policy** wizard opens.</span></span> <span data-ttu-id="02182-148">[ポリシーに **名前を付け] ページ** で、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="02182-148">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="02182-149">**[名前]**: わかりやすい一意のポリシー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="02182-149">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="02182-150">**[説明]**: ポリシーについての説明を入力します (オプション)。</span><span class="sxs-lookup"><span data-stu-id="02182-150">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="02182-151">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="02182-151">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="02182-152">表示される **[設定** ] ページで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="02182-152">On the **Settings** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="02182-153">**メッセージ内の不明な潜在的に悪意** のある URL のアクションを選択します。[ **オン** ] を選択すると、電子メール メッセージ内のリンクに対する安全なリンク保護が有効になります。</span><span class="sxs-lookup"><span data-stu-id="02182-153">**Select the action for unknown potentially malicious URLs in messages**: Select **On** to enable Safe Links protection for links in email messages.</span></span>

   - <span data-ttu-id="02182-154">**Microsoft Teams 内の不明な** URL または潜在的に悪意のある URL のアクションを選択します。[ **オン** ] を選択すると、Teams のリンクに対する安全なリンク保護が有効になります。</span><span class="sxs-lookup"><span data-stu-id="02182-154">**Select the action for unknown or potentially malicious URLs within Microsoft Teams**: Select **On** to enable Safe Links protection for links in Teams.</span></span>

   - <span data-ttu-id="02182-155">**ファイルを指す** 疑わしいリンクやリンクに対してリアルタイム URL スキャンを適用する: この設定を選択すると、電子メール メッセージ内のリンクをリアルタイムでスキャンできます。</span><span class="sxs-lookup"><span data-stu-id="02182-155">**Apply real-time URL scanning for suspicious links and links that point to files**: Select this setting to enable real-time scanning of links in email messages.</span></span>

   - <span data-ttu-id="02182-156">**メッセージを配信する前** に URL のスキャンが完了するのを待つ: この設定を選択すると、メッセージを配信する前にリアルタイムの URL スキャンが完了するのを待ちます。</span><span class="sxs-lookup"><span data-stu-id="02182-156">**Wait for URL scanning to complete before delivering the message**: Select this setting to wait for real-time URL scanning to complete before delivering the message.</span></span>

   - <span data-ttu-id="02182-157">**組織内で送信される電子** メール メッセージに安全なリンクを適用する: この設定を選択して、内部送信者と内部受信者の間のメッセージにセーフ リンク ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="02182-157">**Apply Safe Links to email messages sent within the organization**: Select this setting to apply the Safe Links policy to messages between internal senders and internal recipients.</span></span>

   - <span data-ttu-id="02182-158">**ユーザーのクリックを追跡しない**: この設定を選択しないままにして、電子メール メッセージ内の URL を追跡するユーザーのクリックを有効にします。</span><span class="sxs-lookup"><span data-stu-id="02182-158">**Do not track user clicks**: Leave this setting unselected to enable the tracking user clicks on URLs in email messages.</span></span>

   - <span data-ttu-id="02182-159">**ユーザーに元の URL** へのクリックを許可しない : この設定を選択すると、警告ページ内の元の URL へのユーザーのクリックが [ブロックされます](safe-links.md#warning-pages-from-safe-links)。</span><span class="sxs-lookup"><span data-stu-id="02182-159">**Do not allow users to click through to original URL**: Select this setting to block users from clicking through to the original URL in [warning pages](safe-links.md#warning-pages-from-safe-links).</span></span>

   - <span data-ttu-id="02182-160">**次の URL を書き換えない**: セーフ リンクによってブロックされる指定された URL へのアクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="02182-160">**Do not rewrite the following URLs**: Allows access the specified URLs that would otherwise be blocked by Safe Links.</span></span>

     <span data-ttu-id="02182-161">ボックスに、必要な URL または値を入力し、 をクリックします。</span><span class="sxs-lookup"><span data-stu-id="02182-161">In the box, type the URL or value that you want, and then click</span></span> ![[ボタンの追加] アイコン](../../media/ITPro-EAC-AddIcon.png)<span data-ttu-id="02182-163">.</span><span class="sxs-lookup"><span data-stu-id="02182-163">.</span></span>

     <span data-ttu-id="02182-164">既存のエントリを削除するには、そのエントリを選択して、</span><span class="sxs-lookup"><span data-stu-id="02182-164">To remove an existing entry, select it and then click</span></span> ![[削除] ボタン アイコン](../../media/ITPro-EAC-DeleteIcon.png)<span data-ttu-id="02182-166">.</span><span class="sxs-lookup"><span data-stu-id="02182-166">.</span></span>

     <span data-ttu-id="02182-167">エントリの構文については、「次の URL を書き換えない」リストの Entry 構文 [を参照してください](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)。</span><span class="sxs-lookup"><span data-stu-id="02182-167">For entry syntax, see [Entry syntax for the "Do not rewrite the following URLs" list](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span></span>

   <span data-ttu-id="02182-168">これらの設定の詳細については、「電子メール[](safe-links.md#safe-links-settings-for-email-messages)メッセージのセーフ リンク設定」および「Microsoft Teams のセーフ リンク[設定」を参照してください](safe-links.md#safe-links-settings-for-microsoft-teams)。</span><span class="sxs-lookup"><span data-stu-id="02182-168">For detailed information about these settings, see [Safe Links settings for email messages](safe-links.md#safe-links-settings-for-email-messages) and [Safe Links settings for Microsoft Teams](safe-links.md#safe-links-settings-for-microsoft-teams).</span></span>

   <span data-ttu-id="02182-169">Standard および Strict ポリシー設定の推奨値の詳細については、「セーフ リンク ポリシー設定 [」を参照してください](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings)。</span><span class="sxs-lookup"><span data-stu-id="02182-169">For more the recommended values for Standard and Strict policy settings, see [Safe Links policy settings](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings).</span></span>

   <span data-ttu-id="02182-170">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="02182-170">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="02182-171">表示される **[適用先]** ページで、ポリシーが適用される内部受信者を特定します。</span><span class="sxs-lookup"><span data-stu-id="02182-171">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="02182-172">各条件や例外は 1 回しか使用できませんが、条件や例外には複数の値を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="02182-172">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="02182-173">同じ条件や例外に複数の値がある場合、OR ロジック (たとえば、_\<recipient1\>_ または _\<recipient2\>_) が適用されます。</span><span class="sxs-lookup"><span data-stu-id="02182-173">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="02182-174">a別の条件や例外がある場合は AND ロジック (たとえば、_\<recipient1\>_ かつ _\<member of group 1\>_) が適用されます。</span><span class="sxs-lookup"><span data-stu-id="02182-174">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="02182-175">[条件 **の追加] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="02182-175">Click **Add a condition**.</span></span> <span data-ttu-id="02182-176">表示されるドロップダウンで、[適用する場合] で条件 **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="02182-176">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="02182-177">**受信者は:** 組織内の 1 つ以上のメールボックス、メール ユーザー、またはメール連絡先を指定します。</span><span class="sxs-lookup"><span data-stu-id="02182-177">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="02182-178">**受信者は: のメンバーです**。組織内の 1 つ以上のグループを指定します。</span><span class="sxs-lookup"><span data-stu-id="02182-178">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="02182-179">**[受信者のドメインが次の値である]**: 組織内で構成済みの 1 つ以上の承認済みドメイン内の受信者を指定します。</span><span class="sxs-lookup"><span data-stu-id="02182-179">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in your organization.</span></span>

   <span data-ttu-id="02182-180">条件を選択すると、対応するドロップダウンが [Any of **these] ボックスと一緒に表示** されます。</span><span class="sxs-lookup"><span data-stu-id="02182-180">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="02182-181">ボックス内をクリックし、値の一覧をスクロールして選択します。</span><span class="sxs-lookup"><span data-stu-id="02182-181">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="02182-182">ボックス内をクリックし、入力を開始してリストをフィルター処理し、値を選択します。</span><span class="sxs-lookup"><span data-stu-id="02182-182">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="02182-183">追加の値を追加するには、ボックス内の空の領域をクリックします。</span><span class="sxs-lookup"><span data-stu-id="02182-183">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="02182-184">個々のエントリを削除するには、値 **の [削除]** ![ ](../../media/scc-remove-icon.png) アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="02182-184">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="02182-185">条件全体を削除するには、条件 **の [削除]** ![ ](../../media/scc-remove-icon.png) アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="02182-185">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="02182-186">追加の条件を追加するには、[条件の追加] **をクリックし** 、[適用する場合] で残りの値 **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="02182-186">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="02182-187">例外を追加するには、[条件の追加] **をクリックし** 、[条件を除く] で例外 **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="02182-187">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="02182-188">設定と動作は、条件とまったく同じです。</span><span class="sxs-lookup"><span data-stu-id="02182-188">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="02182-189">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="02182-189">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="02182-190">表示される **[設定の確認]** ページで、設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="02182-190">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="02182-191">各設定で **[編集]** をクリックして変更できます。</span><span class="sxs-lookup"><span data-stu-id="02182-191">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="02182-192">完了したら、 **[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="02182-192">When you're finished, click **Finish**.</span></span>

## <a name="use-the-security--compliance-center-to-view-safe-links-policies"></a><span data-ttu-id="02182-193">セキュリティ コンプライアンス センターを&セーフ リンク ポリシーを表示する</span><span class="sxs-lookup"><span data-stu-id="02182-193">Use the Security & Compliance Center to view Safe Links policies</span></span>

1. <span data-ttu-id="02182-194">セキュリティ 管理コンプライアンス センター&、脅威管理ポリシー  \> ATP **セーフ リンク** \> **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="02182-194">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="02182-195">[安全 **なリンク] ページ** で、一覧からポリシーを選択し、そのポリシーをクリックします (チェック ボックスをオンにしない)。</span><span class="sxs-lookup"><span data-stu-id="02182-195">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

   <span data-ttu-id="02182-196">ポリシーの詳細がフライアウトに表示される</span><span class="sxs-lookup"><span data-stu-id="02182-196">The policy details appear in a fly out</span></span>

## <a name="use-the-security--compliance-center-to-modify-safe-links-policies"></a><span data-ttu-id="02182-197">セキュリティ コンプライアンス センターを&セーフ リンク ポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="02182-197">Use the Security & Compliance Center to modify Safe Links policies</span></span>

1. <span data-ttu-id="02182-198">セキュリティ 管理コンプライアンス センター&、脅威管理ポリシー  \> ATP **セーフ リンク** \> **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="02182-198">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="02182-199">[安全 **なリンク] ページ** で、一覧からポリシーを選択し、そのポリシーをクリックします (チェック ボックスをオンにしない)。</span><span class="sxs-lookup"><span data-stu-id="02182-199">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="02182-200">表示されるポリシーの詳細が表示されたら、[ポリシーの編集] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="02182-200">In the policy details fly out that appears, click **Edit policy**.</span></span>

<span data-ttu-id="02182-201">表示されるフライアウトで使用可能な設定は、「セキュリティ コンプライアンス センターを使用して安全なリンク ポリシー&作成する」セクション [で説明されている設定と同](#use-the-security--compliance-center-to-create-safe-links-policies) じです。</span><span class="sxs-lookup"><span data-stu-id="02182-201">The available settings in the fly out that appears are identical to those described in the [Use the Security & Compliance Center to create Safe Links policies](#use-the-security--compliance-center-to-create-safe-links-policies) section.</span></span>

<span data-ttu-id="02182-202">ポリシーを有効または無効にするか、ポリシーの優先順位を設定するには、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="02182-202">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-safe-links-policies"></a><span data-ttu-id="02182-203">セーフ リンク ポリシーを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="02182-203">Enable or disable Safe Links policies</span></span>

1. <span data-ttu-id="02182-204">セキュリティ 管理コンプライアンス センター&、脅威管理ポリシー  \> ATP **セーフ リンク** \> **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="02182-204">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="02182-205">[状態] 列の値 **に注意** してください。</span><span class="sxs-lookup"><span data-stu-id="02182-205">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="02182-206">ポリシーを無効にするには、左に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="02182-206">Move the toggle to the left to disable the policy:</span></span> ![ポリシーをオフにする](../../media/scc-toggle-off.png)<span data-ttu-id="02182-208">.</span><span class="sxs-lookup"><span data-stu-id="02182-208">.</span></span>

   - <span data-ttu-id="02182-209">ポリシーを有効にするには、右に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="02182-209">Move the toggle to the right to enable the policy:</span></span> ![ポリシーを有効にする](../../media/scc-toggle-on.png)<span data-ttu-id="02182-211">.</span><span class="sxs-lookup"><span data-stu-id="02182-211">.</span></span>

### <a name="set-the-priority-of-safe-links-policies"></a><span data-ttu-id="02182-212">セーフ リンク ポリシーの優先度を設定する</span><span class="sxs-lookup"><span data-stu-id="02182-212">Set the priority of Safe Links policies</span></span>

<span data-ttu-id="02182-213">既定では、セーフ リンク ポリシーには、作成された順序に基づく優先度が与えられる (新しいポリシーは、古いポリシーよりも優先度が低くなります)。</span><span class="sxs-lookup"><span data-stu-id="02182-213">By default, Safe Links policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="02182-214">優先度番号が小さいほど、ポリシーの優先度が高くなる (0 が最優先) ことを意味し、ポリシーは優先順位に従って処理されます (優先度の高いポリシーは、優先度の低いポリシーよりも先に処理されます)。</span><span class="sxs-lookup"><span data-stu-id="02182-214">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="02182-215">2つのポリシーが同じ優先順位を持つことはできません。最初のポリシーが適用されると、ポリシーの処理は停止します。</span><span class="sxs-lookup"><span data-stu-id="02182-215">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="02182-216">優先順位と複数のポリシーを評価し適用する方法の詳細については、「[メール保護の優先順位](how-policies-and-protections-are-combined.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02182-216">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="02182-217">セーフ リンク ポリシーは、処理された順序で表示されます (最初のポリシーの **優先度** の値は 0 です)。</span><span class="sxs-lookup"><span data-stu-id="02182-217">Safe Links policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span>

> [!NOTE]
> <span data-ttu-id="02182-218">セキュリティ コンプライアンス センター&、セーフ リンク ポリシーの優先度を変更できるのは、作成後のみです。</span><span class="sxs-lookup"><span data-stu-id="02182-218">In the Security & Compliance Center, you can only change the priority of the Safe Links policy after you create it.</span></span> <span data-ttu-id="02182-219">PowerShell では、安全なリンク ルールを作成するときに既定の優先度を上書きできます (既存のルールの優先度に影響を与える可能性があります)。</span><span class="sxs-lookup"><span data-stu-id="02182-219">In PowerShell, you can override the default priority when you create the safe links rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="02182-220">ポリシーの優先度を変更するには、リスト内で上下に移動させます (セキュリティ/コンプライアンス センター内で直接、**優先順位** 番号を変更することはできません)。</span><span class="sxs-lookup"><span data-stu-id="02182-220">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="02182-221">セキュリティ 管理コンプライアンス センター&、脅威管理ポリシー  \> ATP **セーフ リンク** \> **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="02182-221">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="02182-222">[安全 **なリンク] ページ** で、一覧からポリシーを選択し、そのポリシーをクリックします (チェック ボックスをオンにしない)。</span><span class="sxs-lookup"><span data-stu-id="02182-222">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="02182-223">表示されるポリシーの詳細が表示されたら、使用可能な優先度ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="02182-223">In the policy details fly out that appears, click the available priority button:</span></span>

   - <span data-ttu-id="02182-224">優先度の値が **0** の **安全なリンク** ポリシーには、[優先度を下がる]**ボタンしか** 使用できません。</span><span class="sxs-lookup"><span data-stu-id="02182-224">The Safe Links policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="02182-225">優先度の値が最も低い安全なリンク **ポリシー** ( **たとえば、3)** には、[優先度の引き上げ] **ボタンのみを** 使用できます。</span><span class="sxs-lookup"><span data-stu-id="02182-225">The Safe Links policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="02182-226">3 つ以上の安全なリンク ポリシーがある場合、優先度の高い値と最も低い優先度の値の間のポリシーには、[優先度の引き上げ] ボタンと [優先度の下げ] ボタンの **両方が用意** されています。</span><span class="sxs-lookup"><span data-stu-id="02182-226">If you have three or more Safe Links policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="02182-227">[優先度 **の増加] または** **[優先度の下げ** ] をクリックして、 **優先度の値を変更** します。</span><span class="sxs-lookup"><span data-stu-id="02182-227">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="02182-228">完了したら、**[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="02182-228">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-safe-links-policies"></a><span data-ttu-id="02182-229">セキュリティ コンプライアンス センターを&セーフ リンク ポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="02182-229">Use the Security & Compliance Center to remove Safe Links policies</span></span>

1. <span data-ttu-id="02182-230">セキュリティ 管理コンプライアンス センター&、脅威管理ポリシー  \> ATP **セーフ リンク** \> **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="02182-230">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="02182-231">[安全 **なリンク] ページ** で、一覧からポリシーを選択し、そのポリシーをクリックします (チェック ボックスをオンにしない)。</span><span class="sxs-lookup"><span data-stu-id="02182-231">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="02182-232">表示されるポリシーの詳細が表示されたら、[ポリシーの削除] をクリックし、表示される警告ダイアログで **[は** い] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="02182-232">In the policy details fly out that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies"></a><span data-ttu-id="02182-233">Exchange Online PowerShell またはスタンドアロン EOP PowerShell を使用してセーフ リンク ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="02182-233">Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Links policies</span></span>

<span data-ttu-id="02182-234">前述したように、セーフ リンク ポリシーは、安全なリンク ポリシーと安全なリンク ルールで構成されます。</span><span class="sxs-lookup"><span data-stu-id="02182-234">As previously described, a Safe Links policy consists of a safe links policy and a safe links rule.</span></span>

<span data-ttu-id="02182-235">PowerShell では、安全なリンク ポリシーと安全なリンク ルールの違いが明らかです。</span><span class="sxs-lookup"><span data-stu-id="02182-235">In PowerShell, the difference between safe links policies and safe links rules is apparent.</span></span> <span data-ttu-id="02182-236">安全なリンク ポリシーは **\* 、-SafeLinksPolicy** コマンドレットを使用して管理し **\* 、-SafeLinksRule** コマンドレットを使用して安全なリンク ルールを管理します。</span><span class="sxs-lookup"><span data-stu-id="02182-236">You manage safe links policies by using the **\*-SafeLinksPolicy** cmdlets, and you manage safe links rules by using the **\*-SafeLinksRule** cmdlets.</span></span>

- <span data-ttu-id="02182-237">PowerShell では、安全なリンク ポリシーを最初に作成してから、ルールが適用されるポリシーを識別する安全なリンク ルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="02182-237">In PowerShell, you create the safe links policy first, then you create the safe links rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="02182-238">PowerShell では、安全なリンク ポリシーの設定と安全なリンク ルールを個別に変更します。</span><span class="sxs-lookup"><span data-stu-id="02182-238">In PowerShell, you modify the settings in the safe links policy and the safe links rule separately.</span></span>
- <span data-ttu-id="02182-239">PowerShell から安全なリンク ポリシーを削除しても、対応する安全なリンク ルールは自動的には削除されません。その逆も同様です。</span><span class="sxs-lookup"><span data-stu-id="02182-239">When you remove a safe links policy from PowerShell, the corresponding safe links rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-safe-links-policies"></a><span data-ttu-id="02182-240">PowerShell を使用して安全なリンク ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="02182-240">Use PowerShell to create Safe Links policies</span></span>

<span data-ttu-id="02182-241">PowerShell で安全なリンク ポリシーを作成するには、次の 2 つの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="02182-241">Creating a Safe Links policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="02182-242">安全なリンク ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="02182-242">Create the safe links policy.</span></span>
2. <span data-ttu-id="02182-243">ルールが適用される安全なリンク ポリシーを指定する安全なリンク ルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="02182-243">Create the safe links rule that specifies the safe links policy that the rule applies to.</span></span>

> [!NOTE]
> 
> - <span data-ttu-id="02182-244">新しいセーフ リンク ルールを作成し、関連付けされていない既存の安全なリンク ポリシーを割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="02182-244">You can create a new safe links rule and assign an existing, unassociated safe links policy to it.</span></span> <span data-ttu-id="02182-245">安全なリンク ルールを複数の安全なリンク ポリシーに関連付けできない。</span><span class="sxs-lookup"><span data-stu-id="02182-245">A safe links rule can't be associated with more than one safe links policy.</span></span>
> 
> - <span data-ttu-id="02182-246">ポリシーを作成するまで、セキュリティ & コンプライアンス センターで使用できない PowerShell の新しい安全なリンク ポリシーで、次の設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="02182-246">You can configure the following settings on new safe links policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>
> 
>   - <span data-ttu-id="02182-247">新しいポリシーを _無効として作成_ します `$false` **(New-SafeLinksRule コマンドレットで有効** )。</span><span class="sxs-lookup"><span data-stu-id="02182-247">Create the new policy as disabled (_Enabled_ `$false` on the **New-SafeLinksRule** cmdlet).</span></span>
>   - <span data-ttu-id="02182-248"> _\<Number\>_ **New-SafeLinksRule** コマンドレットの作成時にポリシーの優先度 (優先度) を設定します。</span><span class="sxs-lookup"><span data-stu-id="02182-248">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-SafeLinksRule** cmdlet).</span></span>
> 
> - <span data-ttu-id="02182-249">PowerShell で作成した新しい安全なリンク ポリシーは、ポリシーを安全なリンク ルールに割り当てるまで、セキュリティ & コンプライアンス センターには表示されません。</span><span class="sxs-lookup"><span data-stu-id="02182-249">A new safe links policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a safe links rule.</span></span>

#### <a name="step-1-use-powershell-to-create-a-safe-links-policy"></a><span data-ttu-id="02182-250">手順 1: PowerShell を使用して安全なリンク ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="02182-250">Step 1: Use PowerShell to create a safe links policy</span></span>

<span data-ttu-id="02182-251">安全なリンク ポリシーを作成するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="02182-251">To create a safe links policy, use this syntax:</span></span>

```PowerShell
New-SafeLinksPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-IsEnabled <$true | $false>] [-EnableSafeLinksForTeams <$true | $false>] [-ScanUrls <$true | $false>] [-DeliverMessageAfterScan <$true | $false>] [-EnableForInternalSenders <$true | $false>] [-DoNotAllowClickThrough <$true | $false>] [-DoNotTrackUserClicks <$true | $false>] [-DoNotRewriteUrls "Entry1","Entry2",..."EntryN"]
```

> [!NOTE]
> 
> - <span data-ttu-id="02182-252">_DoNotRewriteUrls_ パラメーターに使用するエントリ構文の詳細については、「次の URL を書き換えない」リストのエントリ構文を [参照してください](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)。</span><span class="sxs-lookup"><span data-stu-id="02182-252">For details about the entry syntax to use for the _DoNotRewriteUrls_ parameter, see [Entry syntax for the "Do not rewrite the following URLs" list](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span></span>
> 
> - <span data-ttu-id="02182-253">**Set-SafeLinksPolicy** コマンドレットを使用して既存のセーフ リンク ポリシーを変更するときに _DoNotRewriteUrls_ パラメーターに使用できる追加の構文については、この記事の後半の [「PowerShell](#use-powershell-to-modify-safe-links-policies)を使用して安全なリンク ポリシーを変更する」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="02182-253">For additional syntax that you can use for the _DoNotRewriteUrls_ parameter when you modify existing safe links policies by using the **Set-SafeLinksPolicy** cmdlet, see the [Use PowerShell to modify safe links policies](#use-powershell-to-modify-safe-links-policies) section later in this article.</span></span>

<span data-ttu-id="02182-254">この例では、Contoso All という名前の安全なリンク ポリシーを次の値で作成します。</span><span class="sxs-lookup"><span data-stu-id="02182-254">This example creates a safe links policy named Contoso All with the following values:</span></span>

- <span data-ttu-id="02182-255">電子メール メッセージで URL のスキャンと書き換えを有効にする。</span><span class="sxs-lookup"><span data-stu-id="02182-255">Turn on URL scanning and rewriting in email messages.</span></span>
- <span data-ttu-id="02182-256">Teams で URL スキャンを有効にする (TAP プレビューのみ)。</span><span class="sxs-lookup"><span data-stu-id="02182-256">Turn on URL scanning in Teams (TAP Preview only).</span></span>
- <span data-ttu-id="02182-257">クリックした URL (ファイルを指すクリックされたリンクを含む) のリアルタイム スキャンを有効にする。</span><span class="sxs-lookup"><span data-stu-id="02182-257">Turn on real-time scanning of clicked URLs, including clicked links that point to files.</span></span>
- <span data-ttu-id="02182-258">メッセージを配信する前に、URL のスキャンが完了するのを待ちます。</span><span class="sxs-lookup"><span data-stu-id="02182-258">Wait for URL scanning to complete before delivering the message.</span></span>
- <span data-ttu-id="02182-259">内部メッセージの URL スキャンと書き換えを有効にする。</span><span class="sxs-lookup"><span data-stu-id="02182-259">Turn on URL scanning and rewriting for internal messages.</span></span>
- <span data-ttu-id="02182-260">セーフ リンク保護に関連するユーザークリックを追跡します _(DoNotTrackUserClicks_ パラメーターは使用していないので、既定値は $false です。つまり、ユーザーのクリックが追跡されます)。</span><span class="sxs-lookup"><span data-stu-id="02182-260">Track user clicks related to Safe Links protection (we aren't using the _DoNotTrackUserClicks_ parameter, and the default value is $false, which means user clicks are tracked).</span></span>
- <span data-ttu-id="02182-261">ユーザーが元の URL をクリックしてクリックを許可しない。</span><span class="sxs-lookup"><span data-stu-id="02182-261">Do not allow users to click through to the original URL.</span></span>

```PowerShell
New-SafeLinksPolicy -Name "Contoso All" -IsEnabled $true -EnableSafeLinksForTeams $true -ScanUrls $true -DeliverMessageAfterScan $true -EnableForInternalSenders $true -DoNotAllowClickThrough $true
```

<span data-ttu-id="02182-262">構文とパラメーターの詳細については [、「New-SafeLinksPolicy」を参照してください](/powershell/module/exchange/new-safelinkspolicy)。</span><span class="sxs-lookup"><span data-stu-id="02182-262">For detailed syntax and parameter information, see [New-SafeLinksPolicy](/powershell/module/exchange/new-safelinkspolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-a-safe-links-rule"></a><span data-ttu-id="02182-263">手順 2: PowerShell を使用して安全なリンク ルールを作成する</span><span class="sxs-lookup"><span data-stu-id="02182-263">Step 2: Use PowerShell to create a safe links rule</span></span>

<span data-ttu-id="02182-264">安全なリンク ルールを作成するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="02182-264">To create a safe links rule, use this syntax:</span></span>

```PowerShell
New-SafeLinksRule -Name "<RuleName>" -SafeLinksPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

<span data-ttu-id="02182-265">この例では、Contoso All という名前の安全なリンク ルールを次の条件で作成します。</span><span class="sxs-lookup"><span data-stu-id="02182-265">This example creates a safe links rule named Contoso All with the following conditions:</span></span>

- <span data-ttu-id="02182-266">ルールは、Contoso All という名前の安全なリンク ポリシーに関連付けられている。</span><span class="sxs-lookup"><span data-stu-id="02182-266">The rule is associated with the safe links policy named Contoso All.</span></span>
- <span data-ttu-id="02182-267">ルールは、ドメイン内のすべての受信者に contoso.com されます。</span><span class="sxs-lookup"><span data-stu-id="02182-267">The rule applies to all recipients in the contoso.com domain.</span></span>
- <span data-ttu-id="02182-268">Priority パラメーターを使用していないので _、既定_ の優先度が使用されます。</span><span class="sxs-lookup"><span data-stu-id="02182-268">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>
- <span data-ttu-id="02182-269">ルールが有効になっています (Enabled パラメーターは使用しませんが、既定値はです `$true` )。</span><span class="sxs-lookup"><span data-stu-id="02182-269">The rule is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>

```powershell
New-SafeLinksRule -Name "Contoso All" -SafeLinksPolicy "Contoso All" -RecipientDomainIs contoso.com
```

<span data-ttu-id="02182-270">構文とパラメーターの詳細については [、「New-SafeLinksRule」を参照してください](/powershell/module/exchange/new-safelinksrule)。</span><span class="sxs-lookup"><span data-stu-id="02182-270">For detailed syntax and parameter information, see [New-SafeLinksRule](/powershell/module/exchange/new-safelinksrule).</span></span>

### <a name="use-powershell-to-view-safe-links-policies"></a><span data-ttu-id="02182-271">PowerShell を使用して安全なリンク ポリシーを表示する</span><span class="sxs-lookup"><span data-stu-id="02182-271">Use PowerShell to view safe links policies</span></span>

<span data-ttu-id="02182-272">既存の安全なリンク ポリシーを表示するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="02182-272">To view existing safe links policies, use the following syntax:</span></span>

```PowerShell
Get-SafeLinksPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="02182-273">この例では、すべての安全なリンク ポリシーの概要一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="02182-273">This example returns a summary list of all safe links policies.</span></span>

```PowerShell
Get-SafeLinksPolicy | Format-Table Name
```

<span data-ttu-id="02182-274">この例では、Contoso Executives という名前の安全なリンク ポリシーの詳細情報を返します。</span><span class="sxs-lookup"><span data-stu-id="02182-274">This example returns detailed information for the safe links policy named Contoso Executives.</span></span>

```PowerShell
Get-SafeLinksPolicy -Identity "Contoso Executives"
```

<span data-ttu-id="02182-275">構文とパラメーターの詳細については [、「Get-SafeLinksPolicy」を参照してください](/powershell/module/exchange/get-safelinkspolicy)。</span><span class="sxs-lookup"><span data-stu-id="02182-275">For detailed syntax and parameter information, see [Get-SafeLinksPolicy](/powershell/module/exchange/get-safelinkspolicy).</span></span>

### <a name="use-powershell-to-view-safe-links-rules"></a><span data-ttu-id="02182-276">PowerShell を使用して安全なリンク ルールを表示する</span><span class="sxs-lookup"><span data-stu-id="02182-276">Use PowerShell to view safe links rules</span></span>

<span data-ttu-id="02182-277">既存のセーフ リンク ルールを表示するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="02182-277">To view existing safe links rules, use the following syntax:</span></span>

```PowerShell
Get-SafeLinksRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="02182-278">この例では、すべての安全なリンク ルールの概要一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="02182-278">This example returns a summary list of all safe links rules.</span></span>

```PowerShell
Get-SafeLinksRule | Format-Table Name,State
```

<span data-ttu-id="02182-279">ルールを有効または無効にしてリストをフィルター処理するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="02182-279">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-SafeLinksRule -State Disabled
```

```PowerShell
Get-SafeLinksRule -State Enabled
```

<span data-ttu-id="02182-280">この例では、Contoso Executives という名前の安全なリンク ルールの詳細情報を返します。</span><span class="sxs-lookup"><span data-stu-id="02182-280">This example returns detailed information for the safe links rule named Contoso Executives.</span></span>

```PowerShell
Get-SafeLinksRule -Identity "Contoso Executives"
```

<span data-ttu-id="02182-281">構文とパラメーターの詳細については [、「Get-SafeLinksRule」を参照してください](/powershell/module/exchange/get-safelinksrule)。</span><span class="sxs-lookup"><span data-stu-id="02182-281">For detailed syntax and parameter information, see [Get-SafeLinksRule](/powershell/module/exchange/get-safelinksrule).</span></span>

### <a name="use-powershell-to-modify-safe-links-policies"></a><span data-ttu-id="02182-282">PowerShell を使用して安全なリンク ポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="02182-282">Use PowerShell to modify safe links policies</span></span>

<span data-ttu-id="02182-283">PowerShell で安全なリンク ポリシーの名前を変更することはできません **(Set-SafeLinksPolicy** コマンドレットには _Name_ パラメーターはありません)。</span><span class="sxs-lookup"><span data-stu-id="02182-283">You can't rename a safe links policy in PowerShell (the **Set-SafeLinksPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="02182-284">コンプライアンス センターのセキュリティ &リンク ポリシーの名前を変更する場合は、セーフ リンク ルールの名前を変更 _する必要があります_。</span><span class="sxs-lookup"><span data-stu-id="02182-284">When you rename a Safe Links policy in the Security & Compliance Center, you're only renaming the safe links _rule_.</span></span>

<span data-ttu-id="02182-285">PowerShell で安全なリンク ポリシーを変更するための唯一の追加の考慮事項は _、DoNotRewriteUrls_ パラメーターで使用可能な構文です ("次の [URL を](safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)書き換えない" リスト)。</span><span class="sxs-lookup"><span data-stu-id="02182-285">The only additional consideration for modifying safe links policies in PowerShell is the available syntax for the _DoNotRewriteUrls_ parameter (the ["Do not rewrite the following URLs" list](safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)):</span></span>

- <span data-ttu-id="02182-286">既存のエントリを置き換える値を追加するには、次の構文を使用します `"Entry1","Entry2,..."EntryN"` 。</span><span class="sxs-lookup"><span data-stu-id="02182-286">To add values that will replace any existing entries, use the following syntax: `"Entry1","Entry2,..."EntryN"`.</span></span>
- <span data-ttu-id="02182-287">他の既存のエントリに影響を与えることなく値を追加または削除するには、次の構文を使用します。 `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`</span><span class="sxs-lookup"><span data-stu-id="02182-287">To add or remove values without affecting other existing entries, use the following syntax: `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`</span></span>

<span data-ttu-id="02182-288">それ以外の場合は、「手順 [1: PowerShell](#step-1-use-powershell-to-create-a-safe-links-policy) を使用して安全なリンク ポリシーを作成する」のセクションで説明したように、安全なリンク ポリシーを作成するときに同じ設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="02182-288">Otherwise, the same settings are available when you create a safe links policy as described in the [Step 1: Use PowerShell to create a safe links policy](#step-1-use-powershell-to-create-a-safe-links-policy) section earlier in this article.</span></span>

<span data-ttu-id="02182-289">安全なリンク ポリシーを変更するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="02182-289">To modify a safe links policy, use this syntax:</span></span>

```PowerShell
Set-SafeLinksPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="02182-290">構文とパラメーターの詳細については [、「Set-SafeLinksPolicy」を参照してください](/powershell/module/exchange/set-safelinkspolicy)。</span><span class="sxs-lookup"><span data-stu-id="02182-290">For detailed syntax and parameter information, see [Set-SafeLinksPolicy](/powershell/module/exchange/set-safelinkspolicy).</span></span>

### <a name="use-powershell-to-modify-safe-links-rules"></a><span data-ttu-id="02182-291">PowerShell を使用して安全なリンク ルールを変更する</span><span class="sxs-lookup"><span data-stu-id="02182-291">Use PowerShell to modify safe links rules</span></span>

<span data-ttu-id="02182-292">PowerShell で安全なリンク ルールを変更するときに使用できない唯一の設定は、無効なルールを作成できる _Enabled_ パラメーターです。</span><span class="sxs-lookup"><span data-stu-id="02182-292">The only setting that's not available when you modify a safe links rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="02182-293">既存のセーフ リンク ルールを有効または無効にするには、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="02182-293">To enable or disable existing safe links rules, see the next section.</span></span>

<span data-ttu-id="02182-294">それ以外の場合は、「手順 [2: PowerShell](#step-2-use-powershell-to-create-a-safe-links-rule) を使用して安全なリンク ルールを作成する」セクションで説明したように、ルールを作成するときに同じ設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="02182-294">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create a safe links rule](#step-2-use-powershell-to-create-a-safe-links-rule) section earlier in this article.</span></span>

<span data-ttu-id="02182-295">安全なリンク ルールを変更するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="02182-295">To modify a safe links rule, use this syntax:</span></span>

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="02182-296">構文とパラメーターの詳細については [、「Set-SafeLinksRule」を参照してください](/powershell/module/exchange/set-safelinksrule)。</span><span class="sxs-lookup"><span data-stu-id="02182-296">For detailed syntax and parameter information, see [Set-SafeLinksRule](/powershell/module/exchange/set-safelinksrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-safe-links-rules"></a><span data-ttu-id="02182-297">PowerShell を使用して安全なリンク ルールを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="02182-297">Use PowerShell to enable or disable safe links rules</span></span>

<span data-ttu-id="02182-298">PowerShell で安全なリンク ルールを有効または無効にすると、全体のセーフ リンク ポリシー (セーフ リンク ルールと割り当てられた安全なリンク ポリシー) が有効または無効となります。</span><span class="sxs-lookup"><span data-stu-id="02182-298">Enabling or disabling a safe links rule in PowerShell enables or disables the whole Safe Links policy (the safe links rule and the assigned safe links policy).</span></span>

<span data-ttu-id="02182-299">PowerShell で安全なリンク ルールを有効または無効にするには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="02182-299">To enable or disable a safe links rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-SafeLinksRule | Disable-SafeLinksRule> -Identity "<RuleName>"
```

<span data-ttu-id="02182-300">この例では、Marketing Department という名前の安全なリンク ルールを無効にします。</span><span class="sxs-lookup"><span data-stu-id="02182-300">This example disables the safe links rule named Marketing Department.</span></span>

```PowerShell
Disable-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="02182-301">この例では、同じルールを有効化します。</span><span class="sxs-lookup"><span data-stu-id="02182-301">This example enables same rule.</span></span>

```PowerShell
Enable-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="02182-302">構文とパラメーターの詳細については [、「Enable-SafeLinksRule」](/powershell/module/exchange/enable-safelinksrule) および [「Disable-SafeLinksRule」を参照してください](/powershell/module/exchange/disable-safelinksrule)。</span><span class="sxs-lookup"><span data-stu-id="02182-302">For detailed syntax and parameter information, see [Enable-SafeLinksRule](/powershell/module/exchange/enable-safelinksrule) and [Disable-SafeLinksRule](/powershell/module/exchange/disable-safelinksrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-safe-links-rules"></a><span data-ttu-id="02182-303">PowerShell を使用して安全なリンク ルールの優先度を設定する</span><span class="sxs-lookup"><span data-stu-id="02182-303">Use PowerShell to set the priority of safe links rules</span></span>

<span data-ttu-id="02182-304">ルールに設定できる優先度の最高値値は 0 です。</span><span class="sxs-lookup"><span data-stu-id="02182-304">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="02182-305">設定できる最低値はルールの数に依存します。</span><span class="sxs-lookup"><span data-stu-id="02182-305">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="02182-306">たとえば、ルールが五つある場合、使用できる優先度の値は 0 から 4 です。</span><span class="sxs-lookup"><span data-stu-id="02182-306">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="02182-307">既存の一つのルールの優先度を変更すると、他のルールにも連鎖的な影響が起こりえます。</span><span class="sxs-lookup"><span data-stu-id="02182-307">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="02182-308">たとえば、カスタム ルールが 5 つあって (優先度 0 から 4)、1 つのルールの優先度を 2 に変更した場合には、既存の優先度 2 のルールは優先度 3 に変更され、優先度 3 は優先度 4 に変更されます。</span><span class="sxs-lookup"><span data-stu-id="02182-308">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="02182-309">PowerShell で安全なリンク ルールの優先度を設定するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="02182-309">To set the priority of a safe links rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="02182-p123">この例では、Marketing Department というルールの優先度を 2 に設定しています。優先度が 2 以下のすべての既存のルールは、優先度が 1 ずつ下がります (優先度番号が 1 ずつ増加します)。</span><span class="sxs-lookup"><span data-stu-id="02182-p123">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-SafeLinksRule -Identity "Marketing Department" -Priority 2
```

> [!NOTE]
> <span data-ttu-id="02182-312">新しいルールを作成するときに優先度を設定するには **、New-SafeLinksRule** コマンドレットの Priority パラメーターを使用します。 </span><span class="sxs-lookup"><span data-stu-id="02182-312">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-SafeLinksRule** cmdlet instead.</span></span>

<span data-ttu-id="02182-313">構文とパラメーターの詳細については [、「Set-SafeLinksRule」を参照してください](/powershell/module/exchange/set-safelinksrule)。</span><span class="sxs-lookup"><span data-stu-id="02182-313">For detailed syntax and parameter information, see [Set-SafeLinksRule](/powershell/module/exchange/set-safelinksrule).</span></span>

### <a name="use-powershell-to-remove-safe-links-policies"></a><span data-ttu-id="02182-314">PowerShell を使用して安全なリンク ポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="02182-314">Use PowerShell to remove safe links policies</span></span>

<span data-ttu-id="02182-315">PowerShell を使用して安全なリンク ポリシーを削除しても、対応する安全なリンク ルールは削除されません。</span><span class="sxs-lookup"><span data-stu-id="02182-315">When you use PowerShell to remove a safe links policy, the corresponding safe links rule isn't removed.</span></span>

<span data-ttu-id="02182-316">PowerShell で安全なリンク ポリシーを削除するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="02182-316">To remove a safe links policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeLinksPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="02182-317">この例では、Marketing Department という名前の安全なリンク ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="02182-317">This example removes the safe links policy named Marketing Department.</span></span>

```PowerShell
Remove-SafeLinksPolicy -Identity "Marketing Department"
```

<span data-ttu-id="02182-318">構文とパラメーターの詳細については [、「Remove-SafeLinksPolicy」を参照してください](/powershell/module/exchange/remove-safelinkspolicy)。</span><span class="sxs-lookup"><span data-stu-id="02182-318">For detailed syntax and parameter information, see [Remove-SafeLinksPolicy](/powershell/module/exchange/remove-safelinkspolicy).</span></span>

### <a name="use-powershell-to-remove-safe-links-rules"></a><span data-ttu-id="02182-319">PowerShell を使用して安全なリンク ルールを削除する</span><span class="sxs-lookup"><span data-stu-id="02182-319">Use PowerShell to remove safe links rules</span></span>

<span data-ttu-id="02182-320">PowerShell を使用して安全なリンク ルールを削除しても、対応する安全なリンク ポリシーは削除されません。</span><span class="sxs-lookup"><span data-stu-id="02182-320">When you use PowerShell to remove a safe links rule, the corresponding safe links policy isn't removed.</span></span>

<span data-ttu-id="02182-321">PowerShell で安全なリンク ルールを削除するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="02182-321">To remove a safe links rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeLinksRule -Identity "<PolicyName>"
```

<span data-ttu-id="02182-322">この例では、Marketing Department という名前の安全なリンク ルールを削除します。</span><span class="sxs-lookup"><span data-stu-id="02182-322">This example removes the safe links rule named Marketing Department.</span></span>

```PowerShell
Remove-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="02182-323">構文とパラメーターの詳細については [、「Remove-SafeLinksRule」を参照してください](/powershell/module/exchange/remove-safelinksrule)。</span><span class="sxs-lookup"><span data-stu-id="02182-323">For detailed syntax and parameter information, see [Remove-SafeLinksRule](/powershell/module/exchange/remove-safelinksrule).</span></span>

<span data-ttu-id="02182-324">セーフ リンクがメッセージをスキャンしているのを確認するには、使用可能な Microsoft Defender で 365 レポートOffice確認します。</span><span class="sxs-lookup"><span data-stu-id="02182-324">To verify that Safe Links is scanning messages, check the available Microsoft Defender for Office 365 reports.</span></span> <span data-ttu-id="02182-325">詳細については、「View [reports for Defender for Office 365」](view-reports-for-mdo.md) および「Use Explorer in the Security & [コンプライアンス センター」を参照してください](threat-explorer.md)。</span><span class="sxs-lookup"><span data-stu-id="02182-325">For more information, see [View reports for Defender for Office 365](view-reports-for-mdo.md) and [Use Explorer in the Security & Compliance Center](threat-explorer.md).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="02182-326">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="02182-326">How do you know these procedures worked?</span></span>

<span data-ttu-id="02182-327">セーフ リンク ポリシーが正常に作成、変更、または削除されたことを確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="02182-327">To verify that you've successfully created, modified, or removed Safe Links policies, do any of the following steps:</span></span>

- <span data-ttu-id="02182-328">セキュリティ 管理コンプライアンス センター&、脅威管理ポリシー  \> ATP **セーフ リンク** \> **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="02182-328">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span> <span data-ttu-id="02182-329">ポリシー、その状態の値、および **優先度** の値の一覧を **確認** します。</span><span class="sxs-lookup"><span data-stu-id="02182-329">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="02182-330">詳細を表示するには、一覧からポリシーを選択し、詳細をフライアウトで表示します。</span><span class="sxs-lookup"><span data-stu-id="02182-330">To view more details, select the policy from the list, and view the details in the fly out.</span></span>

- <span data-ttu-id="02182-331">Exchange Online PowerShell または Exchange Online Protection PowerShell で、ポリシーまたはルールの名前に置き換え、次のコマンドを実行し、 \<Name\> 設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="02182-331">In Exchange Online PowerShell or Exchange Online Protection PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-SafeLinksPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-SafeLinksRule -Identity "<Name>"
  ```