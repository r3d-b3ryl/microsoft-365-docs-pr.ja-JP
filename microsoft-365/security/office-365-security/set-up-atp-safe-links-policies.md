---
title: Office の安全なリンクポリシーを設定する (Microsoft Defender 用) 365
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
description: 管理者は、Microsoft Defender for Office 365 で、安全なリンクポリシーと安全なリンクの設定を表示、作成、変更、および削除する方法について説明します。
ms.openlocfilehash: 550be48d5f1cae490c53c8f4a9fcedb0b9f21f73
ms.sourcegitcommit: d81c7cea85af6ad5fef81d3c930514a51464368c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/04/2020
ms.locfileid: "49572719"
---
# <a name="set-up-safe-links-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="f0b76-103">Office の安全なリンクポリシーを設定する (Microsoft Defender 用) 365</span><span class="sxs-lookup"><span data-stu-id="f0b76-103">Set up Safe Links policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> <span data-ttu-id="f0b76-104">この記事は [、Microsoft Defender For Office 365 を](office-365-atp.md)使用しているビジネスのお客様を対象としています。</span><span class="sxs-lookup"><span data-stu-id="f0b76-104">This article is intended for business customers who have [Microsoft Defender for Office 365](office-365-atp.md).</span></span> <span data-ttu-id="f0b76-105">Outlook の Safelinks に関する情報をお探しのホームユーザーの場合は、「 [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0b76-105">If you are a home user looking for information about Safelinks in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="f0b76-106">「安全なリンク」とは、メールフローで受信電子メールメッセージの URL スキャンを行う [Office 365 の](office-365-atp.md) 機能の1つであり、電子メールメッセージやその他の場所で url とリンクの確認をクリックしたときに表示されるものです。</span><span class="sxs-lookup"><span data-stu-id="f0b76-106">Safe Links is a feature in [Microsoft Defender for Office 365](office-365-atp.md) that provides URL scanning of inbound email messages in mail flow, and time of click verification of URLs and links in email messages and in other locations.</span></span> <span data-ttu-id="f0b76-107">詳細については、「 [Microsoft Defender For Office 365」](atp-safe-links.md)の「安全なリンク」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0b76-107">For more information, see [Safe Links in Microsoft Defender for Office 365](atp-safe-links.md).</span></span>

<span data-ttu-id="f0b76-108">組み込みまたは既定の安全なリンクポリシーはありません。</span><span class="sxs-lookup"><span data-stu-id="f0b76-108">There's no built-in or default Safe Links policy.</span></span> <span data-ttu-id="f0b76-109">Url の安全なリンクスキャンを取得するには、この記事で説明されているように、1つ以上の安全なリンクポリシーを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0b76-109">To get Safe Links scanning of URLs, you need to create one or more Safe Links policies as described in this article.</span></span>

<span data-ttu-id="f0b76-110">セキュリティで保護されたリンクポリシーを構成するには、セキュリティ & コンプライアンスセンターまたは PowerShell (exchange online にメールボックスを持つ資格のある Microsoft 365 組織用の Exchange Online PowerShell、exchange Online メールボックスを持たない組織の場合はスタンドアロンの EOP PowerShell、Office 365 アドオンサブスクリプションの場合は Microsoft Defender) を使用します。</span><span class="sxs-lookup"><span data-stu-id="f0b76-110">You can configure Safe Links policies in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Microsoft Defender for Office 365 add-on subscriptions).</span></span>

<span data-ttu-id="f0b76-111">安全リンクポリシーの基本的な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f0b76-111">The basic elements of a Safe Links policy are:</span></span>

- <span data-ttu-id="f0b76-112">「**安全なリンク」ポリシー**: [安全なリンクの保護] をオンにして、リアルタイムの URL スキャンを有効にし、メッセージを配信する前にリアルタイムスキャンが完了するのを待機するかどうかを指定し、ユーザーが url をスキャンするかどうかを指定し、ユーザーが元の url をクリックできるようにするかどうか</span><span class="sxs-lookup"><span data-stu-id="f0b76-112">**The safe links policy**: Turn on Safe Links protection, turn on real-time URL scanning, specify whether to wait for real-time scanning to complete before delivering the message, turn on scanning for internal messages, specify whether to track user clicks on URLs, and specify whether to allow users to click trough to the original URL.</span></span>
- <span data-ttu-id="f0b76-113">"**安全なリンク" ルール**: 優先順位と受信者フィルター (ポリシーが適用されるユーザー) を指定します。</span><span class="sxs-lookup"><span data-stu-id="f0b76-113">**The safe links rule**: Specifies the priority and recipient filters (who the policy applies to).</span></span>

<span data-ttu-id="f0b76-114">セキュリティ & コンプライアンスセンターで安全なリンクポリシーを管理する場合、これらの2つの要素の違いは明白ではありません。</span><span class="sxs-lookup"><span data-stu-id="f0b76-114">The difference between these two elements isn't obvious when you manage Safe Links polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="f0b76-115">安全なリンクポリシーを作成する場合、実際には、両方の同じ名前を使用して、安全なリンクルールと関連する安全なリンクポリシーを作成しています。</span><span class="sxs-lookup"><span data-stu-id="f0b76-115">When you create a Safe Links policy, you're actually creating a safe links rule and the associated safe links policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="f0b76-116">安全なリンクポリシーを変更する場合、名前、優先度、有効または無効に関連する設定、および受信者フィルターは、安全なリンクのルールを変更します。</span><span class="sxs-lookup"><span data-stu-id="f0b76-116">When you modify a Safe Links policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the safe links rule.</span></span> <span data-ttu-id="f0b76-117">他のすべての設定は、関連する安全なリンクポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="f0b76-117">All other settings modify the associated safe links policy.</span></span>
- <span data-ttu-id="f0b76-118">安全なリンクポリシーを削除すると、"安全なリンク" ルールと、それに関連する安全なリンクポリシーが削除されます。</span><span class="sxs-lookup"><span data-stu-id="f0b76-118">When you remove a Safe Links policy, the safe links rule and the associated safe links policy are removed.</span></span>

<span data-ttu-id="f0b76-119">Exchange Online PowerShell またはスタンドアロン EOP PowerShell では、ポリシーとルールを個別に管理します。</span><span class="sxs-lookup"><span data-stu-id="f0b76-119">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="f0b76-120">詳細については、この記事で後述 [する「Exchange Online の powershell またはスタンドアロンの EOP powershell を使用して安全なリンクポリシーを構成する](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) 」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0b76-120">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Links policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) section later in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="f0b76-121">「安全なリンク」ポリシーの **外部** にある安全なリンク保護のためのグローバル設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="f0b76-121">You configure the global settings for Safe Links protection **outside** of Safe Links policies.</span></span> <span data-ttu-id="f0b76-122">手順については、「 [Microsoft Defender For Office 365 の「安全なリンクのグローバル設定を構成する](configure-global-settings-for-safe-links.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0b76-122">For instructions, see [Configure global settings for Safe Links in Microsoft Defender for Office 365](configure-global-settings-for-safe-links.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f0b76-123">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="f0b76-123">What do you need to know before you begin?</span></span>

- <span data-ttu-id="f0b76-124"><https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="f0b76-124">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="f0b76-125">[ **安全なリンク** ] ページに直接移動するには、を使用 <https://protection.office.com/safelinksv2> します。</span><span class="sxs-lookup"><span data-stu-id="f0b76-125">To go directly to the **Safe Links** page, use <https://protection.office.com/safelinksv2>.</span></span>

- <span data-ttu-id="f0b76-126">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0b76-126">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="f0b76-127">スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0b76-127">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="f0b76-128">この記事の手順を実行する前に、セキュリティ & コンプライアンスセンターでアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0b76-128">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="f0b76-129">安全なリンクポリシーを作成、変更、および削除するには、 **組織の管理** または **セキュリティ管理者** の役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0b76-129">To create, modify, and delete Safe Links policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="f0b76-130">「安全なリンク」ポリシーに対する読み取り専用アクセスの場合は、 **グローバル閲覧** 者または **セキュリティ閲覧** 者の役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0b76-130">For read-only access to Safe Links policies, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="f0b76-131">詳細については、「[セキュリティ/コンプライアンス センターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0b76-131">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="f0b76-132">**注**:</span><span class="sxs-lookup"><span data-stu-id="f0b76-132">**Notes**:</span></span>

  - <span data-ttu-id="f0b76-133">Microsoft 365 管理センターで対応する Azure Active Directory の役割にユーザーを追加すると、セキュリティ & コンプライアンスセンター _および_ microsoft 365 の他の機能に対するアクセス許可で必要なアクセス許可がユーザーに付与されます。</span><span class="sxs-lookup"><span data-stu-id="f0b76-133">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="f0b76-134">詳細については、[「管理者の役割について」](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0b76-134">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="f0b76-135">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)の **表示のみの組織の管理** 役割グループは、機能への読み取り専用アクセス権も付与します。</span><span class="sxs-lookup"><span data-stu-id="f0b76-135">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="f0b76-136">「安全なリンク」ポリシーの推奨設定については、「 [安全なリンクポリシー設定](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0b76-136">For our recommended settings for Safe Links policies, see [Safe Links policy settings](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings).</span></span>

- <span data-ttu-id="f0b76-137">新規または更新されたポリシーが適用されるまで最大30分かかります。</span><span class="sxs-lookup"><span data-stu-id="f0b76-137">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="f0b76-138">[新しい機能は、Microsoft Defender For Office 365 に継続的に追加](office-365-atp.md#new-features-in-microsoft-defender-for-office-365)されています。</span><span class="sxs-lookup"><span data-stu-id="f0b76-138">[New features are continually being added to Microsoft Defender for Office 365](office-365-atp.md#new-features-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="f0b76-139">新機能が追加されたときに、既存の安全なリンクポリシーを調整する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="f0b76-139">As new features are added, you may need to make adjustments to your existing Safe Links policies.</span></span>

## <a name="use-the-security--compliance-center-to-create-safe-links-policies"></a><span data-ttu-id="f0b76-140">セキュリティ & コンプライアンスセンターを使用して安全なリンクポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="f0b76-140">Use the Security & Compliance Center to create Safe Links policies</span></span>

<span data-ttu-id="f0b76-141">セキュリティ & コンプライアンスセンターでカスタムの安全なリンクポリシーを作成すると、両方に同じ名前を使用して、安全なリンクルールと関連する安全なリンクポリシーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="f0b76-141">Creating a custom Safe Links policy in the Security & Compliance Center creates the safe links rule and the associated safe links policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="f0b76-142">[セキュリティ & コンプライアンスセンター] で、[ **脅威管理** \> **ポリシー** \> **ATP セーフリンク**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="f0b76-142">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="f0b76-143">[ **安全なリンク** ] ページで、[ **作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f0b76-143">On the **Safe Links** page, click **Create**.</span></span>

3. <span data-ttu-id="f0b76-144">**新しい安全なリンクポリシー** ウィザードが開きます。</span><span class="sxs-lookup"><span data-stu-id="f0b76-144">The **New Safe Links policy** wizard opens.</span></span> <span data-ttu-id="f0b76-145">[ **ポリシーに名前** をつける] ページで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="f0b76-145">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="f0b76-146">**[名前]**: わかりやすい一意のポリシー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="f0b76-146">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="f0b76-147">**[説明]**: ポリシーについての説明を入力します (オプション)。</span><span class="sxs-lookup"><span data-stu-id="f0b76-147">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="f0b76-148">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f0b76-148">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="f0b76-149">表示される [ **設定** ] ページで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="f0b76-149">On the **Settings** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="f0b76-150">[**メッセージ内の不明な悪意のある url に対するアクション]**: [**オン] を選択して**、電子メールメッセージ内のリンクの安全なリンク保護を有効にします。</span><span class="sxs-lookup"><span data-stu-id="f0b76-150">**Select the action for unknown potentially malicious URLs in messages**: Select **On** to enable Safe Links protection for links in email messages.</span></span>

   - <span data-ttu-id="f0b76-151">[ **Microsoft teams 内の不明または悪意のある url に対するアクション]**: [**オン] を** 選択して、Teams 内のリンクの安全なリンク保護を有効にします。</span><span class="sxs-lookup"><span data-stu-id="f0b76-151">**Select the action for unknown or potentially malicious URLs within Microsoft Teams**: Select **On** to enable Safe Links protection for links in Teams.</span></span>

   - <span data-ttu-id="f0b76-152">[**ファイルを参照する不審なリンクおよびリンクのリアルタイム URL スキャンを適用** する]: 電子メールメッセージ内のリンクをリアルタイムでスキャンできるようにするには、この設定を選択します。</span><span class="sxs-lookup"><span data-stu-id="f0b76-152">**Apply real-time URL scanning for suspicious links and links that point to files**: Select this setting to enable real-time scanning of links in email messages.</span></span>

   - <span data-ttu-id="f0b76-153">**メッセージを配信する前に、url のスキャンが完了するのを待機** します。メッセージを配信する前に、リアルタイムの url のスキャンが完了するのを待機するには、この設定を選択します。</span><span class="sxs-lookup"><span data-stu-id="f0b76-153">**Wait for URL scanning to complete before delivering the message**: Select this setting to wait for real-time URL scanning to complete before delivering the message.</span></span>

   - <span data-ttu-id="f0b76-154">[**組織内で送信された電子メールメッセージに安全なリンクを適用** する]: 内部送信者と内部受信者の間のメッセージに安全なリンクポリシーを適用するには、この設定を選択します。</span><span class="sxs-lookup"><span data-stu-id="f0b76-154">**Apply Safe Links to email messages sent within the organization**: Select this setting to apply the Safe Links policy to messages between internal senders and internal recipients.</span></span>

   - <span data-ttu-id="f0b76-155">[**ユーザーのクリックを追跡** しない]: この設定をオフのままにすると、ユーザーが電子メールメッセージ内の url をクリックできるようになります。</span><span class="sxs-lookup"><span data-stu-id="f0b76-155">**Do not track user clicks**: Leave this setting unselected to enable the tracking user clicks on URLs in email messages.</span></span>

   - <span data-ttu-id="f0b76-156">**[ユーザーが元の url に移動できない** ようにする]: この設定を選択すると、ユーザーが [警告ページ](atp-safe-links.md#warning-pages-from-safe-links)で元の url に移動するのをブロックします。</span><span class="sxs-lookup"><span data-stu-id="f0b76-156">**Do not allow users to click through to original URL**: Select this setting to block users from clicking through to the original URL in [warning pages](atp-safe-links.md#warning-pages-from-safe-links).</span></span>

   - <span data-ttu-id="f0b76-157">**次の url を書き換えないで** ください。それ以外の場合は、安全なリンクによってブロックされる url へのアクセスが許可されます。</span><span class="sxs-lookup"><span data-stu-id="f0b76-157">**Do not rewrite the following URLs**: Allows access the specified URLs that would otherwise be blocked by Safe Links.</span></span>

     <span data-ttu-id="f0b76-158">ボックスに、必要な URL または値を入力して、[</span><span class="sxs-lookup"><span data-stu-id="f0b76-158">In the box, type the URL or value that you want, and then click</span></span> ![[ボタンの追加] アイコン](../../media/ITPro-EAC-AddIcon.png)<span data-ttu-id="f0b76-160">.</span><span class="sxs-lookup"><span data-stu-id="f0b76-160">.</span></span>

     <span data-ttu-id="f0b76-161">既存のエントリを削除するには、そのエントリを選択して [</span><span class="sxs-lookup"><span data-stu-id="f0b76-161">To remove an existing entry, select it and then click</span></span> ![[ボタンの削除] アイコン](../../media/ITPro-EAC-DeleteIcon.png)<span data-ttu-id="f0b76-163">.</span><span class="sxs-lookup"><span data-stu-id="f0b76-163">.</span></span>

     <span data-ttu-id="f0b76-164">エントリの構文については、 [「次の url を書き換えないでください」リストのエントリの構文](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0b76-164">For entry syntax, see [Entry syntax for the "Do not rewrite the following URLs" list](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span></span>

   <span data-ttu-id="f0b76-165">これらの設定の詳細については、「 [Microsoft Teams の](atp-safe-links.md#safe-links-settings-for-microsoft-teams)電子メールメッセージと安全なリンクの設定」[の「安全なリンクの設定](atp-safe-links.md#safe-links-settings-for-email-messages)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0b76-165">For detailed information about these settings, see [Safe Links settings for email messages](atp-safe-links.md#safe-links-settings-for-email-messages) and [Safe Links settings for Microsoft Teams](atp-safe-links.md#safe-links-settings-for-microsoft-teams).</span></span>

   <span data-ttu-id="f0b76-166">標準および厳密なポリシー設定に推奨される値については、「 [安全なリンクポリシー設定](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0b76-166">For more the recommended values for Standard and Strict policy settings, see [Safe Links policy settings](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings).</span></span>

   <span data-ttu-id="f0b76-167">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f0b76-167">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="f0b76-168">表示される [ **適用先** ] ページで、ポリシーが適用される内部の受信者を特定します。</span><span class="sxs-lookup"><span data-stu-id="f0b76-168">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="f0b76-169">各条件や例外は 1 回しか使用できませんが、条件や例外には複数の値を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="f0b76-169">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="f0b76-170">同じ条件や例外に複数の値がある場合、OR ロジック (たとえば、_\<recipient1\>_ または _\<recipient2\>_) が適用されます。</span><span class="sxs-lookup"><span data-stu-id="f0b76-170">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="f0b76-171">a別の条件や例外がある場合は AND ロジック (たとえば、_\<recipient1\>_ かつ _\<member of group 1\>_) が適用されます。</span><span class="sxs-lookup"><span data-stu-id="f0b76-171">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="f0b76-172">[ **条件の追加] を** クリックします。</span><span class="sxs-lookup"><span data-stu-id="f0b76-172">Click **Add a condition**.</span></span> <span data-ttu-id="f0b76-173">表示されるドロップダウンで、[適用済みの **場合**] の条件を選択します。</span><span class="sxs-lookup"><span data-stu-id="f0b76-173">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="f0b76-174">**受信者は** 次のとおりです。組織内で1つ以上のメールボックス、メールユーザー、またはメール連絡先を指定します。</span><span class="sxs-lookup"><span data-stu-id="f0b76-174">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="f0b76-175">**受信者が次のメンバーの** 場合: 組織内の1つまたは複数のグループを指定します。</span><span class="sxs-lookup"><span data-stu-id="f0b76-175">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="f0b76-176">**[受信者のドメインが次の値である]**: 組織内で構成済みの 1 つ以上の承認済みドメイン内の受信者を指定します。</span><span class="sxs-lookup"><span data-stu-id="f0b76-176">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in your organization.</span></span>

   <span data-ttu-id="f0b76-177">条件を選択すると、対応するドロップ **ダウンボックスが** 表示されます。</span><span class="sxs-lookup"><span data-stu-id="f0b76-177">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="f0b76-178">ボックス内をクリックし、値の一覧をスクロールして選択します。</span><span class="sxs-lookup"><span data-stu-id="f0b76-178">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="f0b76-179">ボックス内をクリックして入力を開始し、リストにフィルターを適用して値を選択します。</span><span class="sxs-lookup"><span data-stu-id="f0b76-179">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="f0b76-180">その他の値を追加するには、ボックスの空の領域をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f0b76-180">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="f0b76-181">個々のエントリを削除するには、その値の [削除] アイコン **をクリックし** ![ ](../../media/scc-remove-icon.png) ます。</span><span class="sxs-lookup"><span data-stu-id="f0b76-181">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="f0b76-182">条件全体を削除するには、条件の [削除] アイコン **をクリックし** ![ ](../../media/scc-remove-icon.png) ます。</span><span class="sxs-lookup"><span data-stu-id="f0b76-182">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="f0b76-183">別の条件を追加するには、[ **条件の追加** ] をクリックし、[ **適用** 時] で残りの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="f0b76-183">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="f0b76-184">例外を追加するには、[ **条件の追加** ] をクリックし、 **Except if** で例外を選択します。</span><span class="sxs-lookup"><span data-stu-id="f0b76-184">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="f0b76-185">設定と動作は、条件とまったく同じです。</span><span class="sxs-lookup"><span data-stu-id="f0b76-185">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="f0b76-186">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f0b76-186">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="f0b76-187">表示される [ **設定の確認** ] ページで、設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="f0b76-187">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="f0b76-188">各設定で [ **編集** ] をクリックして、変更を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="f0b76-188">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="f0b76-189">完了したら、 **[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f0b76-189">When you're finished, click **Finish**.</span></span>

## <a name="use-the-security--compliance-center-to-view-safe-links-policies"></a><span data-ttu-id="f0b76-190">セキュリティ & コンプライアンスセンターを使用して、安全なリンクポリシーを表示する</span><span class="sxs-lookup"><span data-stu-id="f0b76-190">Use the Security & Compliance Center to view Safe Links policies</span></span>

1. <span data-ttu-id="f0b76-191">[セキュリティ & コンプライアンスセンター] で、[ **脅威管理** \> **ポリシー** \> **ATP セーフリンク**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="f0b76-191">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="f0b76-192">[ **安全なリンク** ] ページで、リストからポリシーを選択し、それをクリックします (チェックボックスをオンにしないでください)。</span><span class="sxs-lookup"><span data-stu-id="f0b76-192">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

   <span data-ttu-id="f0b76-193">ポリシーの詳細がフライアウトに表示される</span><span class="sxs-lookup"><span data-stu-id="f0b76-193">The policy details appear in a fly out</span></span>

## <a name="use-the-security--compliance-center-to-modify-safe-links-policies"></a><span data-ttu-id="f0b76-194">セキュリティ & コンプライアンスセンターを使用して安全なリンクポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="f0b76-194">Use the Security & Compliance Center to modify Safe Links policies</span></span>

1. <span data-ttu-id="f0b76-195">[セキュリティ & コンプライアンスセンター] で、[ **脅威管理** \> **ポリシー** \> **ATP セーフリンク**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="f0b76-195">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="f0b76-196">[ **安全なリンク** ] ページで、リストからポリシーを選択し、それをクリックします (チェックボックスをオンにしないでください)。</span><span class="sxs-lookup"><span data-stu-id="f0b76-196">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="f0b76-197">[ポリシーの詳細] が表示されたら、[ **ポリシーの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f0b76-197">In the policy details fly out that appears, click **Edit policy**.</span></span>

<span data-ttu-id="f0b76-198">スライドインで使用可能な設定は、「 [セキュリティ & コンプライアンスセンターを使用して安全なリンクポリシーを作成する](#use-the-security--compliance-center-to-create-safe-links-policies) 」セクションで説明されているものと同じです。</span><span class="sxs-lookup"><span data-stu-id="f0b76-198">The available settings in the fly out that appears are identical to those described in the [Use the Security & Compliance Center to create Safe Links policies](#use-the-security--compliance-center-to-create-safe-links-policies) section.</span></span>

<span data-ttu-id="f0b76-199">ポリシーを有効または無効にしたり、ポリシーの優先順位を設定したりするには、以下のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0b76-199">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-safe-links-policies"></a><span data-ttu-id="f0b76-200">安全なリンクポリシーを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="f0b76-200">Enable or disable Safe Links policies</span></span>

1. <span data-ttu-id="f0b76-201">[セキュリティ & コンプライアンスセンター] で、[ **脅威管理** \> **ポリシー** \> **ATP セーフリンク**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="f0b76-201">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="f0b76-202">[ **状態** ] 列の値に注目してください。</span><span class="sxs-lookup"><span data-stu-id="f0b76-202">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="f0b76-203">ポリシーを無効にするには、左に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="f0b76-203">Move the toggle to the left to disable the policy:</span></span> ![ポリシーをオフにする](../../media/scc-toggle-off.png)<span data-ttu-id="f0b76-205">.</span><span class="sxs-lookup"><span data-stu-id="f0b76-205">.</span></span>

   - <span data-ttu-id="f0b76-206">ポリシーを有効にするには、右に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="f0b76-206">Move the toggle to the right to enable the policy:</span></span> ![ポリシーを有効にする](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="f0b76-208">.</span><span class="sxs-lookup"><span data-stu-id="f0b76-208">.</span></span>

### <a name="set-the-priority-of-safe-links-policies"></a><span data-ttu-id="f0b76-209">安全なリンクポリシーの優先度を設定する</span><span class="sxs-lookup"><span data-stu-id="f0b76-209">Set the priority of Safe Links policies</span></span>

<span data-ttu-id="f0b76-210">既定では、「安全なリンク」ポリシーには、作成された順序に基づく優先度が与えられます (新しいポリシーは、古いポリシーよりも優先度が低いです)。</span><span class="sxs-lookup"><span data-stu-id="f0b76-210">By default, Safe Links policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="f0b76-211">優先度番号が小さいほど、ポリシーの優先度が高くなる (0 が最優先) ことを意味し、ポリシーは優先順位に従って処理されます (優先度の高いポリシーは、優先度の低いポリシーよりも先に処理されます)。</span><span class="sxs-lookup"><span data-stu-id="f0b76-211">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="f0b76-212">2つのポリシーが同じ優先順位を持つことはできません。最初のポリシーが適用されると、ポリシーの処理は停止します。</span><span class="sxs-lookup"><span data-stu-id="f0b76-212">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="f0b76-213">優先順位と複数のポリシーを評価し適用する方法の詳細については、「[メール保護の優先順位](how-policies-and-protections-are-combined.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0b76-213">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="f0b76-214">「安全なリンク」ポリシーは、処理順に表示されます (最初のポリシーの **優先度** 値は0になります)。</span><span class="sxs-lookup"><span data-stu-id="f0b76-214">Safe Links policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span>

<span data-ttu-id="f0b76-215">**注**: セキュリティ & コンプライアンスセンターでは、安全なリンクのポリシーを作成した後にのみ、優先度を変更できます。</span><span class="sxs-lookup"><span data-stu-id="f0b76-215">**Note**: In the Security & Compliance Center, you can only change the priority of the Safe Links policy after you create it.</span></span> <span data-ttu-id="f0b76-216">PowerShell では、安全なリンクルールを作成するときに既定の優先順位を上書きできます (既存のルールの優先度に影響する場合があります)。</span><span class="sxs-lookup"><span data-stu-id="f0b76-216">In PowerShell, you can override the default priority when you create the safe links rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="f0b76-217">ポリシーの優先度を変更するには、リスト内で上下に移動させます (セキュリティ/コンプライアンス センター内で直接、**優先順位** 番号を変更することはできません)。</span><span class="sxs-lookup"><span data-stu-id="f0b76-217">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="f0b76-218">[セキュリティ & コンプライアンスセンター] で、[ **脅威管理** \> **ポリシー** \> **ATP セーフリンク**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="f0b76-218">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="f0b76-219">[ **安全なリンク** ] ページで、リストからポリシーを選択し、それをクリックします (チェックボックスをオンにしないでください)。</span><span class="sxs-lookup"><span data-stu-id="f0b76-219">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="f0b76-220">[ポリシーの詳細] が表示されたら、[利用可能な優先度] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="f0b76-220">In the policy details fly out that appears, click the available priority button:</span></span>

   - <span data-ttu-id="f0b76-221">**優先度** の値が **0** の安全なリンクポリシーには、[**優先度を下げる**] ボタンのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f0b76-221">The Safe Links policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="f0b76-222">最も低い **優先度** の値 (たとえば **3**) を持つ安全なリンクポリシーには、[ **優先度を上げる** ] ボタンだけが使用できます。</span><span class="sxs-lookup"><span data-stu-id="f0b76-222">The Safe Links policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="f0b76-223">3つ以上の安全なリンクポリシーがある場合、優先度の最大値と最小値の間のポリシーでは、[優先度を **上げる** ] ボタンと [ **優先度を下げる** ] ボタンの両方を使用できます。</span><span class="sxs-lookup"><span data-stu-id="f0b76-223">If you have three or more Safe Links policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="f0b76-224">[優先 **度を上げる** ] または [ **優先度を下げる** ] をクリックし、 **優先度** の値を変更します。</span><span class="sxs-lookup"><span data-stu-id="f0b76-224">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="f0b76-225">完了したら、**[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f0b76-225">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-safe-links-policies"></a><span data-ttu-id="f0b76-226">セキュリティ & コンプライアンスセンターを使用して安全なリンクポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="f0b76-226">Use the Security & Compliance Center to remove Safe Links policies</span></span>

1. <span data-ttu-id="f0b76-227">[セキュリティ & コンプライアンスセンター] で、[ **脅威管理** \> **ポリシー** \> **ATP セーフリンク**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="f0b76-227">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="f0b76-228">[ **安全なリンク** ] ページで、リストからポリシーを選択し、それをクリックします (チェックボックスをオンにしないでください)。</span><span class="sxs-lookup"><span data-stu-id="f0b76-228">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="f0b76-229">[ポリシーの詳細] が表示されたら、[ **ポリシーの削除**] をクリックし、表示される警告ダイアログで [ **はい** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f0b76-229">In the policy details fly out that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies"></a><span data-ttu-id="f0b76-230">Exchange Online PowerShell またはスタンドアロンの EOP PowerShell を使用して安全なリンクポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="f0b76-230">Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Links policies</span></span>

<span data-ttu-id="f0b76-231">前述したように、安全なリンクポリシーは、安全なリンクポリシーと安全なリンクのルールで構成されます。</span><span class="sxs-lookup"><span data-stu-id="f0b76-231">As previously described, a Safe Links policy consists of a safe links policy and a safe links rule.</span></span>

<span data-ttu-id="f0b76-232">PowerShell では、安全なリンクのポリシーと安全なリンクのルールの違いが明らかです。</span><span class="sxs-lookup"><span data-stu-id="f0b76-232">In PowerShell, the difference between safe links policies and safe links rules is apparent.</span></span> <span data-ttu-id="f0b76-233">「安全なリンク」ポリシーは、 **\* -SafeLinksPolicy** コマンドレットを使用して管理し、 **\* -SafeLinksRule** コマンドレットを使用して安全なリンクルールを管理します。</span><span class="sxs-lookup"><span data-stu-id="f0b76-233">You manage safe links policies by using the **\*-SafeLinksPolicy** cmdlets, and you manage safe links rules by using the **\*-SafeLinksRule** cmdlets.</span></span>

- <span data-ttu-id="f0b76-234">PowerShell では、まず安全なリンクポリシーを作成し、次に、ルールが適用されるポリシーを識別する安全なリンクルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="f0b76-234">In PowerShell, you create the safe links policy first, then you create the safe links rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="f0b76-235">PowerShell では、"安全なリンク" ポリシーと "安全なリンク" ルールの設定を個別に変更します。</span><span class="sxs-lookup"><span data-stu-id="f0b76-235">In PowerShell, you modify the settings in the safe links policy and the safe links rule separately.</span></span>
- <span data-ttu-id="f0b76-236">「安全なリンク」ポリシーを PowerShell から削除しても、対応する安全なリンクのルールは自動的には削除されません。また、その逆も同様です。</span><span class="sxs-lookup"><span data-stu-id="f0b76-236">When you remove a safe links policy from PowerShell, the corresponding safe links rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-safe-links-policies"></a><span data-ttu-id="f0b76-237">PowerShell を使用して安全なリンクポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="f0b76-237">Use PowerShell to create Safe Links policies</span></span>

<span data-ttu-id="f0b76-238">PowerShell で安全なリンクポリシーを作成するには、2つの手順からなるプロセスがあります。</span><span class="sxs-lookup"><span data-stu-id="f0b76-238">Creating a Safe Links policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="f0b76-239">安全なリンクポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="f0b76-239">Create the safe links policy.</span></span>
2. <span data-ttu-id="f0b76-240">ルールを適用する安全なリンクポリシーを指定する安全なリンクルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="f0b76-240">Create the safe links rule that specifies the safe links policy that the rule applies to.</span></span>

 <span data-ttu-id="f0b76-241">**注**:</span><span class="sxs-lookup"><span data-stu-id="f0b76-241">**Notes**:</span></span>

- <span data-ttu-id="f0b76-242">新しい安全なリンクルールを作成し、関連付けられていない既存の安全なリンクポリシーをそのルールに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="f0b76-242">You can create a new safe links rule and assign an existing, unassociated safe links policy to it.</span></span> <span data-ttu-id="f0b76-243">安全なリンクのルールは、複数の安全なリンクポリシーに関連付けることはできません。</span><span class="sxs-lookup"><span data-stu-id="f0b76-243">A safe links rule can't be associated with more than one safe links policy.</span></span>

- <span data-ttu-id="f0b76-244">ポリシーを作成するまでは、セキュリティ & コンプライアンスセンターで利用できない PowerShell の新しい安全なリンクポリシーで、次の設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="f0b76-244">You can configure the following settings on new safe links policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="f0b76-245">新しいポリシーを無効として _Enabled_ 作成し `$false` ます ( **SafeLinksRule** コマンドレットでは有効)。</span><span class="sxs-lookup"><span data-stu-id="f0b76-245">Create the new policy as disabled (_Enabled_ `$false` on the **New-SafeLinksRule** cmdlet).</span></span>
  - <span data-ttu-id="f0b76-246">SafeLinksRule コマンドレットで、作成中にポリシーの優先度を設定します (_優先度_ _\<Number\>_ )。 **New-SafeLinksRule**</span><span class="sxs-lookup"><span data-stu-id="f0b76-246">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-SafeLinksRule** cmdlet).</span></span>

- <span data-ttu-id="f0b76-247">PowerShell で作成した新しい安全なリンクポリシーは、そのポリシーを安全なリンクルールに割り当てるまで、セキュリティ & コンプライアンスセンターに表示されません。</span><span class="sxs-lookup"><span data-stu-id="f0b76-247">A new safe links policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a safe links rule.</span></span>

#### <a name="step-1-use-powershell-to-create-a-safe-links-policy"></a><span data-ttu-id="f0b76-248">手順 1: PowerShell を使用して安全なリンクポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="f0b76-248">Step 1: Use PowerShell to create a safe links policy</span></span>

<span data-ttu-id="f0b76-249">安全なリンクポリシーを作成するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="f0b76-249">To create a safe links policy, use this syntax:</span></span>

```PowerShell
New-SafeLinksPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-IsEnabled <$true | $false>] [-EnableSafeLinksForTeams <$true | $false>] [-ScanUrls <$true | $false>] [-DeliverMessageAfterScan <$true | $false>] [-EnableForInternalSenders <$true | $false>] [-DoNotAllowClickThrough <$true | $false>] [-DoNotTrackUserClicks <$true | $false>] [-DoNotRewriteUrls "Entry1","Entry2",..."EntryN"]
```

<span data-ttu-id="f0b76-250">**注**:</span><span class="sxs-lookup"><span data-stu-id="f0b76-250">**Notes**:</span></span>

- <span data-ttu-id="f0b76-251">上書き _Rewriteurls_ パラメーターに使用するエントリの構文の詳細については、 [「次の url を書き換えないでください」リストのエントリの構文](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0b76-251">For details about the entry syntax to use for the _DoNotRewriteUrls_ parameter, see [Entry syntax for the "Do not rewrite the following URLs" list](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span></span>

- <span data-ttu-id="f0b76-252">**SafeLinksPolicy** コマンドレットを使用して _既存の安全_ なリンクポリシーを変更するときに使用できるその他の構文については、この記事で後述 [する「PowerShell を使用して安全なリンクポリシーを変更](#use-powershell-to-modify-safe-links-policies)する」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0b76-252">For additional syntax that you can use for the _DoNotRewriteUrls_ parameter when you modify existing safe links policies by using the **Set-SafeLinksPolicy** cmdlet, see the [Use PowerShell to modify safe links policies](#use-powershell-to-modify-safe-links-policies) section later in this article.</span></span>

<span data-ttu-id="f0b76-253">この例では、次の値を持つ Contoso All という名前の安全なリンクポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="f0b76-253">This example creates a safe links policy named Contoso All with the following values:</span></span>

- <span data-ttu-id="f0b76-254">電子メールメッセージで URL のスキャンとリライトを有効にします。</span><span class="sxs-lookup"><span data-stu-id="f0b76-254">Turn on URL scanning and rewriting in email messages.</span></span>
- <span data-ttu-id="f0b76-255">Teams での URL スキャンを有効にします ([プレビューのみ] をタップします)。</span><span class="sxs-lookup"><span data-stu-id="f0b76-255">Turn on URL scanning in Teams (TAP Preview only).</span></span>
- <span data-ttu-id="f0b76-256">クリックされた Url のリアルタイムスキャンを有効にします。これには、[ファイル] をクリックするリンクも含まれています。</span><span class="sxs-lookup"><span data-stu-id="f0b76-256">Turn on real-time scanning of clicked URLs, including clicked links that point to files.</span></span>
- <span data-ttu-id="f0b76-257">URL のスキャンが完了するのを待ってから、メッセージを配信します。</span><span class="sxs-lookup"><span data-stu-id="f0b76-257">Wait for URL scanning to complete before delivering the message.</span></span>
- <span data-ttu-id="f0b76-258">内部メッセージの URL スキャンおよびリライトを有効にします。</span><span class="sxs-lookup"><span data-stu-id="f0b76-258">Turn on URL scanning and rewriting for internal messages.</span></span>
- <span data-ttu-id="f0b76-259">「安全なリンクの保護に関連するユーザークリックを追跡する ( _このパラメーターは使用して_ いません。既定値は $false、ユーザークリックが追跡されることを意味します)。</span><span class="sxs-lookup"><span data-stu-id="f0b76-259">Track user clicks related to Safe Links protection (we aren't using the _DoNotTrackUserClicks_ parameter, and the default value is $false, which means user clicks are tracked).</span></span>
- <span data-ttu-id="f0b76-260">ユーザーが元の URL に移動することを許可しません。</span><span class="sxs-lookup"><span data-stu-id="f0b76-260">Do not allow users to click through to the original URL.</span></span>

```PowerShell
New-SafeLinksPolicy -Name "Contoso All" -IsEnabled $true -EnableSafeLinksForTeams $true -ScanUrls $true -DeliverMessageAfterScan $true -EnableForInternalSenders $true -DoNotAllowClickThrough $true
```

<span data-ttu-id="f0b76-261">構文およびパラメーターの詳細については、「 [SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safelinkspolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0b76-261">For detailed syntax and parameter information, see [New-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safelinkspolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-a-safe-links-rule"></a><span data-ttu-id="f0b76-262">手順 2: PowerShell を使用して安全なリンクルールを作成する</span><span class="sxs-lookup"><span data-stu-id="f0b76-262">Step 2: Use PowerShell to create a safe links rule</span></span>

<span data-ttu-id="f0b76-263">安全なリンクルールを作成するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="f0b76-263">To create a safe links rule, use this syntax:</span></span>

```PowerShell
New-SafeLinksRule -Name "<RuleName>" -SafeLinksPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

<span data-ttu-id="f0b76-264">この例では、次の条件を満たす Contoso All という名前の安全なリンクルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="f0b76-264">This example creates a safe links rule named Contoso All with the following conditions:</span></span>

- <span data-ttu-id="f0b76-265">ルールは Contoso All という名前の安全なリンクポリシーに関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="f0b76-265">The rule is associated with the safe links policy named Contoso All.</span></span>
- <span data-ttu-id="f0b76-266">ルールは、contoso.com ドメイン内のすべての受信者に適用されます。</span><span class="sxs-lookup"><span data-stu-id="f0b76-266">The rule applies to all recipients in the contoso.com domain.</span></span>
- <span data-ttu-id="f0b76-267">_Priority_ パラメーターを使用していないので、既定の優先度が使用されます。</span><span class="sxs-lookup"><span data-stu-id="f0b76-267">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>
- <span data-ttu-id="f0b76-268">ルールが有効になっています ( _enabled_ パラメーターは使用していません。既定値はです `$true` )。</span><span class="sxs-lookup"><span data-stu-id="f0b76-268">The rule is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>

```powershell
New-SafeLinksRule -Name "Contoso All" -SafeLinksPolicy "Contoso All" -RecipientDomainIs contoso.com
```

<span data-ttu-id="f0b76-269">構文およびパラメーターの詳細については、「 [SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/new-safelinksrule)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0b76-269">For detailed syntax and parameter information, see [New-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/new-safelinksrule).</span></span>

### <a name="use-powershell-to-view-safe-links-policies"></a><span data-ttu-id="f0b76-270">PowerShell を使用して安全なリンクポリシーを表示する</span><span class="sxs-lookup"><span data-stu-id="f0b76-270">Use PowerShell to view safe links policies</span></span>

<span data-ttu-id="f0b76-271">既存の安全なリンクのポリシーを表示するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="f0b76-271">To view existing safe links policies, use the following syntax:</span></span>

```PowerShell
Get-SafeLinksPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="f0b76-272">この例では、すべての安全なリンクポリシーの要約リストを返します。</span><span class="sxs-lookup"><span data-stu-id="f0b76-272">This example returns a summary list of all safe links policies.</span></span>

```PowerShell
Get-SafeLinksPolicy | Format-Table Name
```

<span data-ttu-id="f0b76-273">この例では、Contoso 重役という名前の安全なリンクポリシーの詳細情報を返します。</span><span class="sxs-lookup"><span data-stu-id="f0b76-273">This example returns detailed information for the safe links policy named Contoso Executives.</span></span>

```PowerShell
Get-SafeLinksPolicy -Identity "Contoso Executives"
```

<span data-ttu-id="f0b76-274">構文およびパラメーターの詳細については、「 [SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/get-safelinkspolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0b76-274">For detailed syntax and parameter information, see [Get-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/get-safelinkspolicy).</span></span>

### <a name="use-powershell-to-view-safe-links-rules"></a><span data-ttu-id="f0b76-275">PowerShell を使用して安全なリンクルールを表示する</span><span class="sxs-lookup"><span data-stu-id="f0b76-275">Use PowerShell to view safe links rules</span></span>

<span data-ttu-id="f0b76-276">既存の安全リンクルールを表示するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="f0b76-276">To view existing safe links rules, use the following syntax:</span></span>

```PowerShell
Get-SafeLinksRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="f0b76-277">この例では、すべての安全なリンクのルールの要約リストが返されます。</span><span class="sxs-lookup"><span data-stu-id="f0b76-277">This example returns a summary list of all safe links rules.</span></span>

```PowerShell
Get-SafeLinksRule | Format-Table Name,State
```

<span data-ttu-id="f0b76-278">ルールを有効または無効にしてリストをフィルター処理するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f0b76-278">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-SafeLinksRule -State Disabled
```

```PowerShell
Get-SafeLinksRule -State Enabled
```

<span data-ttu-id="f0b76-279">この例では、Contoso 重役という名前の安全なリンクルールの詳細情報を返します。</span><span class="sxs-lookup"><span data-stu-id="f0b76-279">This example returns detailed information for the safe links rule named Contoso Executives.</span></span>

```PowerShell
Get-SafeLinksRule -Identity "Contoso Executives"
```

<span data-ttu-id="f0b76-280">構文およびパラメーターの詳細については、「 [SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/get-safelinksrule)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0b76-280">For detailed syntax and parameter information, see [Get-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/get-safelinksrule).</span></span>

### <a name="use-powershell-to-modify-safe-links-policies"></a><span data-ttu-id="f0b76-281">PowerShell を使用して安全なリンクポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="f0b76-281">Use PowerShell to modify safe links policies</span></span>

<span data-ttu-id="f0b76-282">PowerShell で安全なリンクポリシーの名前を変更することはできません ( **SafeLinksPolicy** コマンドレットに _Name_ パラメーターがありません)。</span><span class="sxs-lookup"><span data-stu-id="f0b76-282">You can't rename a safe links policy in PowerShell (the **Set-SafeLinksPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="f0b76-283">セキュリティ & コンプライアンスセンターで安全なリンクポリシーの名前を変更する場合は、安全なリンクの _ルール_ の名前のみを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0b76-283">When you rename a Safe Links policy in the Security & Compliance Center, you're only renaming the safe links _rule_.</span></span>

<span data-ttu-id="f0b76-284">PowerShell で安全なリンクポリシーを変更するための追加の考慮事項は、 ["次の url をリライトしない](atp-safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)" と _いうパラメーターで_ 使用可能な構文です。</span><span class="sxs-lookup"><span data-stu-id="f0b76-284">The only additional consideration for modifying safe links policies in PowerShell is the available syntax for the _DoNotRewriteUrls_ parameter (the ["Do not rewrite the following URLs" list](atp-safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)):</span></span>

- <span data-ttu-id="f0b76-285">既存のエントリを置換する値を追加するには、次の構文を使用し `"Entry1","Entry2,..."EntryN"` ます。</span><span class="sxs-lookup"><span data-stu-id="f0b76-285">To add values that will replace any existing entries, use the following syntax: `"Entry1","Entry2,..."EntryN"`.</span></span>
- <span data-ttu-id="f0b76-286">他の既存のエントリに影響を及ぼさずに値を追加または削除するには、次の構文を使用します。 `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`</span><span class="sxs-lookup"><span data-stu-id="f0b76-286">To add or remove values without affecting other existing entries, use the following syntax: `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`</span></span>

<span data-ttu-id="f0b76-287">それ以外の場合は、この記事の「 [手順 1: PowerShell を使用して安全リンクポリシーを作成する](#step-1-use-powershell-to-create-a-safe-links-policy) 」セクションで説明されているように、安全なリンクポリシーを作成する場合にも同じ設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="f0b76-287">Otherwise, the same settings are available when you create a safe links policy as described in the [Step 1: Use PowerShell to create a safe links policy](#step-1-use-powershell-to-create-a-safe-links-policy) section earlier in this article.</span></span>

<span data-ttu-id="f0b76-288">安全なリンクポリシーを変更するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="f0b76-288">To modify a safe links policy, use this syntax:</span></span>

```PowerShell
Set-SafeLinksPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="f0b76-289">構文およびパラメーターの詳細については、「 [SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0b76-289">For detailed syntax and parameter information, see [Set-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy).</span></span>

### <a name="use-powershell-to-modify-safe-links-rules"></a><span data-ttu-id="f0b76-290">PowerShell を使用して安全なリンクルールを変更する</span><span class="sxs-lookup"><span data-stu-id="f0b76-290">Use PowerShell to modify safe links rules</span></span>

<span data-ttu-id="f0b76-291">PowerShell の安全なリンクのルールを変更するときに使用できない設定は、無効にされたルールを作成できる _有効_ なパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="f0b76-291">The only setting that's not available when you modify a safe links rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="f0b76-292">既存の安全リンクルールを有効または無効にするには、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0b76-292">To enable or disable existing safe links rules, see the next section.</span></span>

<span data-ttu-id="f0b76-293">それ以外の場合は、この記事の「 [手順 2: PowerShell を使用して安全なリンクのルールを作成する](#step-2-use-powershell-to-create-a-safe-links-rule) 」で説明されているように、同じ設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="f0b76-293">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create a safe links rule](#step-2-use-powershell-to-create-a-safe-links-rule) section earlier in this article.</span></span>

<span data-ttu-id="f0b76-294">安全なリンクルールを変更するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="f0b76-294">To modify a safe links rule, use this syntax:</span></span>

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="f0b76-295">構文およびパラメーターの詳細については、「 [SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0b76-295">For detailed syntax and parameter information, see [Set-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-safe-links-rules"></a><span data-ttu-id="f0b76-296">PowerShell を使用して安全なリンクルールを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="f0b76-296">Use PowerShell to enable or disable safe links rules</span></span>

<span data-ttu-id="f0b76-297">PowerShell で安全なリンクルールを有効または無効にすると、安全なリンクポリシー全体 (安全なリンク規則と、割り当てられた安全なリンクポリシー) が有効または無効になります。</span><span class="sxs-lookup"><span data-stu-id="f0b76-297">Enabling or disabling a safe links rule in PowerShell enables or disables the whole Safe Links policy (the safe links rule and the assigned safe links policy).</span></span>

<span data-ttu-id="f0b76-298">PowerShell で安全なリンクルールを有効または無効にするには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="f0b76-298">To enable or disable a safe links rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-SafeLinksRule | Disable-SafeLinksRule> -Identity "<RuleName>"
```

<span data-ttu-id="f0b76-299">この例では、Marketing Department という名前の安全なリンクのルールを無効にします。</span><span class="sxs-lookup"><span data-stu-id="f0b76-299">This example disables the safe links rule named Marketing Department.</span></span>

```PowerShell
Disable-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="f0b76-300">この例では、同じルールを有効化します。</span><span class="sxs-lookup"><span data-stu-id="f0b76-300">This example enables same rule.</span></span>

```PowerShell
Enable-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="f0b76-301">構文およびパラメーターの詳細については、「 [SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/enable-safelinksrule) 」および「 [Disable-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/disable-safelinksrule)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0b76-301">For detailed syntax and parameter information, see [Enable-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/enable-safelinksrule) and [Disable-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/disable-safelinksrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-safe-links-rules"></a><span data-ttu-id="f0b76-302">PowerShell を使用して安全なリンクルールの優先度を設定する</span><span class="sxs-lookup"><span data-stu-id="f0b76-302">Use PowerShell to set the priority of safe links rules</span></span>

<span data-ttu-id="f0b76-303">ルールに設定できる優先度の最高値値は 0 です。</span><span class="sxs-lookup"><span data-stu-id="f0b76-303">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="f0b76-304">設定できる最低値はルールの数に依存します。</span><span class="sxs-lookup"><span data-stu-id="f0b76-304">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="f0b76-305">たとえば、ルールが五つある場合、使用できる優先度の値は 0 から 4 です。</span><span class="sxs-lookup"><span data-stu-id="f0b76-305">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="f0b76-306">既存の一つのルールの優先度を変更すると、他のルールにも連鎖的な影響が起こりえます。</span><span class="sxs-lookup"><span data-stu-id="f0b76-306">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="f0b76-307">たとえば、カスタム ルールが 5 つあって (優先度 0 から 4)、1 つのルールの優先度を 2 に変更した場合には、既存の優先度 2 のルールは優先度 3 に変更され、優先度 3 は優先度 4 に変更されます。</span><span class="sxs-lookup"><span data-stu-id="f0b76-307">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="f0b76-308">PowerShell で安全なリンクのルールの優先度を設定するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="f0b76-308">To set the priority of a safe links rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="f0b76-p123">この例では、Marketing Department というルールの優先度を 2 に設定しています。優先度が 2 以下のすべての既存のルールは、優先度が 1 ずつ下がります (優先度番号が 1 ずつ増加します)。</span><span class="sxs-lookup"><span data-stu-id="f0b76-p123">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-SafeLinksRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="f0b76-311">**注**: 作成時に新しいルールの優先度を設定するには、代わりに **SafeLinksRule** コマンドレットで _priority_ パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="f0b76-311">**Note**: To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-SafeLinksRule** cmdlet instead.</span></span>

<span data-ttu-id="f0b76-312">構文およびパラメーターの詳細については、「 [SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0b76-312">For detailed syntax and parameter information, see [Set-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule).</span></span>

### <a name="use-powershell-to-remove-safe-links-policies"></a><span data-ttu-id="f0b76-313">PowerShell を使用して安全なリンクポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="f0b76-313">Use PowerShell to remove safe links policies</span></span>

<span data-ttu-id="f0b76-314">PowerShell を使用して安全なリンクポリシーを削除しても、対応する安全なリンクのルールは削除されません。</span><span class="sxs-lookup"><span data-stu-id="f0b76-314">When you use PowerShell to remove a safe links policy, the corresponding safe links rule isn't removed.</span></span>

<span data-ttu-id="f0b76-315">PowerShell で安全なリンクポリシーを削除するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="f0b76-315">To remove a safe links policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeLinksPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="f0b76-316">この例では、Marketing Department という名前の安全なリンクポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="f0b76-316">This example removes the safe links policy named Marketing Department.</span></span>

```PowerShell
Remove-SafeLinksPolicy -Identity "Marketing Department"
```

<span data-ttu-id="f0b76-317">構文およびパラメーターの詳細については、「 [SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-safelinkspolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0b76-317">For detailed syntax and parameter information, see [Remove-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-safelinkspolicy).</span></span>

### <a name="use-powershell-to-remove-safe-links-rules"></a><span data-ttu-id="f0b76-318">PowerShell を使用して安全なリンクルールを削除する</span><span class="sxs-lookup"><span data-stu-id="f0b76-318">Use PowerShell to remove safe links rules</span></span>

<span data-ttu-id="f0b76-319">PowerShell を使用して安全なリンクルールを削除しても、対応する安全なリンクポリシーは削除されません。</span><span class="sxs-lookup"><span data-stu-id="f0b76-319">When you use PowerShell to remove a safe links rule, the corresponding safe links policy isn't removed.</span></span>

<span data-ttu-id="f0b76-320">PowerShell で安全なリンクルールを削除するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="f0b76-320">To remove a safe links rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeLinksRule -Identity "<PolicyName>"
```

<span data-ttu-id="f0b76-321">この例では、Marketing Department という名前の安全なリンクのルールを削除します。</span><span class="sxs-lookup"><span data-stu-id="f0b76-321">This example removes the safe links rule named Marketing Department.</span></span>

```PowerShell
Remove-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="f0b76-322">構文およびパラメーターの詳細については、「 [SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/remove-safelinksrule)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0b76-322">For detailed syntax and parameter information, see [Remove-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/remove-safelinksrule).</span></span>

<span data-ttu-id="f0b76-323">安全なリンクがメッセージをスキャンしていることを確認するには、使用可能な Microsoft Defender for Office 365 レポートを確認します。</span><span class="sxs-lookup"><span data-stu-id="f0b76-323">To verify that Safe Links is scanning messages, check the available Microsoft Defender for Office 365 reports.</span></span> <span data-ttu-id="f0b76-324">詳細については、「 [View reports For Office 365](view-reports-for-atp.md) 」および「 [Security & コンプライアンスセンターのエクスプローラーを使用する](threat-explorer.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0b76-324">For more information, see [View reports for Defender for Office 365](view-reports-for-atp.md) and [Use Explorer in the Security & Compliance Center](threat-explorer.md).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="f0b76-325">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="f0b76-325">How do you know these procedures worked?</span></span>

<span data-ttu-id="f0b76-326">安全なリンクポリシーが正常に作成、変更、または削除されたことを確認するには、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f0b76-326">To verify that you've successfully created, modified, or removed Safe Links policies, do any of the following steps:</span></span>

- <span data-ttu-id="f0b76-327">[セキュリティ & コンプライアンスセンター] で、[ **脅威管理** \> **ポリシー** \> **ATP セーフリンク**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="f0b76-327">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span> <span data-ttu-id="f0b76-328">ポリシーの一覧、その **状態** の値、およびその **優先度** の値を確認します。</span><span class="sxs-lookup"><span data-stu-id="f0b76-328">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="f0b76-329">詳細を表示するには、一覧からポリシーを選択し、スライドアウトして詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="f0b76-329">To view more details, select the policy from the list, and view the details in the fly out.</span></span>

- <span data-ttu-id="f0b76-330">Exchange Online PowerShell または Exchange Online Protection PowerShell で、を \<Name\> ポリシーまたはルールの名前に置き換えて、次のコマンドを実行し、設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="f0b76-330">In Exchange Online PowerShell or Exchange Online Protection PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-SafeLinksPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-SafeLinksRule -Identity "<Name>"
  ```
