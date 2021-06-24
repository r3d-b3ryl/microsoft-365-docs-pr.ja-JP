---
title: Microsoft Defender セーフの添付ファイル ポリシーをセットアップOffice 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 078eb946-819a-4e13-8673-fe0c0ad3a775
ms.collection:
- M365-security-compliance
description: メール内の悪意のあるファイルセーフ組織を保護するために、添付ファイルポリシーを定義する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e516a16ff28c762e154fd908312df65ea48699bc
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108225"
---
# <a name="set-up-safe-attachments-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="6bcc4-103">Microsoft Defender セーフの添付ファイル ポリシーをセットアップOffice 365</span><span class="sxs-lookup"><span data-stu-id="6bcc4-103">Set up Safe Attachments policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="6bcc4-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="6bcc4-104">**Applies to**</span></span>
- [<span data-ttu-id="6bcc4-105">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="6bcc4-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="6bcc4-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6bcc4-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> <span data-ttu-id="6bcc4-107">この記事は、[Microsoft Defender for Office 365](whats-new-in-defender-for-office-365.md) をご利用の法人のお客様を対象としています。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-107">This article is intended for business customers who have [Microsoft Defender for Office 365](whats-new-in-defender-for-office-365.md).</span></span> <span data-ttu-id="6bcc4-108">ホーム ユーザーが Outlookファイルの添付ファイルのスキャンに関する情報を探している場合は[、「Advanced Outlook.com セキュリティ」を参照してください](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-108">If you're a home user looking for information about attachment scanning in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="6bcc4-109">セーフ添付ファイルは[、Exchange Online Protection (EOP)](anti-malware-protection.md)でマルウェア対策保護によってスキャンされた後、受信者に配信する前に、仮想環境を使用して受信メール メッセージの添付ファイルを確認する Microsoft Defender for [Office 365](whats-new-in-defender-for-office-365.md)の機能です。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-109">Safe Attachments is a feature in [Microsoft Defender for Office 365](whats-new-in-defender-for-office-365.md) that uses a virtual environment to check attachments in inbound email messages after they've been scanned by [anti-malware protection in Exchange Online Protection (EOP)](anti-malware-protection.md), but before delivery to recipients.</span></span> <span data-ttu-id="6bcc4-110">詳細については、「Microsoft [Defender セーフ添付ファイル」を参照Office 365。](safe-attachments.md)</span><span class="sxs-lookup"><span data-stu-id="6bcc4-110">For more information, see [Safe Attachments in Microsoft Defender for Office 365](safe-attachments.md).</span></span>

<span data-ttu-id="6bcc4-111">組み込みまたは既定の添付ファイル ポリシーセーフはありません。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-111">There's no built-in or default Safe Attachments policy.</span></span> <span data-ttu-id="6bcc4-112">電子メール セーフの添付ファイルスキャンを取得するには、この記事で説明するように 1 つ以上セーフ添付ファイル ポリシーを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-112">To get Safe Attachments scanning of email message attachments, you need to create one or more Safe Attachments policies as described in this article.</span></span>

<span data-ttu-id="6bcc4-113">セーフ 添付ファイル ポリシーは、Microsoft 365 Defender ポータルまたは PowerShell (Exchange Online のメールボックスを持つ適格な Microsoft 365 組織の場合は Exchange Online PowerShell、Exchange Online メールボックスを持つ組織ではスタンドアロンの EOP PowerShell、Office 365 アドオン サブスクリプションの場合は Defender を使用) で構成できます。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-113">You can configure Safe Attachments policies in the Microsoft 365 Defender portal or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Defender for Office 365 add-on subscriptions).</span></span>

<span data-ttu-id="6bcc4-114">添付ファイル ポリシーのセーフは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-114">The basic elements of a Safe Attachments policy are:</span></span>

- <span data-ttu-id="6bcc4-115">安全 **な** 添付ファイル ポリシー: 不明なマルウェア検出のアクション、マルウェアの添付ファイルを含むメッセージを指定した電子メール アドレスに送信するかどうか、および セーフ 添付ファイルのスキャンが完了できない場合にメッセージを配信するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-115">**The safe attachment policy**: Specifies the actions for unknown malware detections, whether to send messages with malware attachments to a specified email address, and whether to deliver messages if Safe Attachments scanning can't complete.</span></span>
- <span data-ttu-id="6bcc4-116">**安全な添付ファイルルール**: 優先度と受信者フィルター (ポリシーが適用されるユーザー) を指定します。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-116">**The safe attachment rule**: Specifies the priority and recipient filters (who the policy applies to).</span></span>

<span data-ttu-id="6bcc4-117">これらの 2 つの要素の違いは、セーフの添付ファイル ポリシーを管理するときにMicrosoft 365 Defenderされません。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-117">The difference between these two elements isn't obvious when you manage Safe Attachments policies in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="6bcc4-118">セーフ添付ファイル ポリシーを作成するときに、両方に同じ名前を使用して、実際に安全な添付ファイル ルールと関連付けられた安全な添付ファイル ポリシーを同時に作成します。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-118">When you create a Safe Attachments policy, you're actually creating a safe attachment rule and the associated safe attachment policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="6bcc4-119">[添付ファイル] セーフ変更すると、名前、優先度、有効または無効、および受信者フィルターに関連する設定によって、安全な添付ファイル ルールが変更されます。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-119">When you modify a Safe Attachments policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the safe attachment rule.</span></span> <span data-ttu-id="6bcc4-120">その他の設定はすべて、関連付けられた安全な添付ファイル ポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-120">All other settings modify the associated safe attachment policy.</span></span>
- <span data-ttu-id="6bcc4-121">添付ファイル ポリシーをセーフすると、安全な添付ファイル ルールと関連付けられた安全な添付ファイル ポリシーが削除されます。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-121">When you remove a Safe Attachments policy, the safe attachment rule and the associated safe attachment policy are removed.</span></span>

<span data-ttu-id="6bcc4-122">Exchange Online PowerShell またはスタンドアロン EOP PowerShell では、ポリシーとルールを個別に管理します。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-122">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="6bcc4-123">詳細については、この記事の後半Exchange Online「PowerShell またはスタンドアロン[EOP PowerShell](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies)を使用して添付ファイルポリシーセーフ構成する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-123">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Attachments policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies) section later in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="6bcc4-124">[添付ファイル] 設定のセーフ領域で、添付ファイル ポリシーに依存しない機能セーフ構成します。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-124">In the global settings area of Safe Attachments settings, you configure features that are not dependent on Safe Attachments policies.</span></span> <span data-ttu-id="6bcc4-125">手順については、「セーフ ドキュメントの[SharePoint、OneDrive、Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md)および セーフ 添付ファイルを有効にする」を[参照Microsoft 365 E5。](safe-docs.md)</span><span class="sxs-lookup"><span data-stu-id="6bcc4-125">For instructions see [Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md) and [Safe Documents in Microsoft 365 E5](safe-docs.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="6bcc4-126">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="6bcc4-126">What do you need to know before you begin?</span></span>

- <span data-ttu-id="6bcc4-127"><https://security.microsoft.com> で Microsoft 365 Defender ポータルを開きます。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-127">You open the Microsoft 365 Defender portal at <https://security.microsoft.com>.</span></span> <span data-ttu-id="6bcc4-128">[添付ファイル] ページに **直接移動セーフを** 使用します <https://security.microsoft.com/safeattachmentv2> 。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-128">To go directly to the **Safe Attachments** page, use <https://security.microsoft.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="6bcc4-129">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-129">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="6bcc4-130">スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-130">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="6bcc4-131">この記事の手順を実行するには、アクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-131">You need permissions before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="6bcc4-132">セーフ 添付ファイル ポリシーを作成、変更、および削除するには、Microsoft 365 Defender ポータルの組織の管理またはセキュリティ管理者の役割グループのメンバーであり、Exchange Online の組織の管理役割グループのメンバーである必要があります。 </span><span class="sxs-lookup"><span data-stu-id="6bcc4-132">To create, modify, and delete Safe Attachments policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Microsoft 365 Defender portal **and** a member of the **Organization Management** role group in Exchange Online.</span></span>
  - <span data-ttu-id="6bcc4-133">添付ファイル ポリシーへの読み取りセーフアクセスするには、ポータルでグローバル リーダーまたはセキュリティ リーダーの役割グループのメンバー Microsoft 365 Defender必要があります。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-133">For read-only access to Safe Attachments policies, you need to be a member of the **Global Reader** or **Security Reader** role groups in the Microsoft 365 Defender portal.</span></span>

  <span data-ttu-id="6bcc4-134">詳細については、「Microsoft 365 Defender[](permissions-microsoft-365-security-center.md)ポータルのアクセス許可」および「Exchange Online」[を参照してください](/exchange/permissions-exo/permissions-exo)。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-134">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md) and [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="6bcc4-135">**注**:</span><span class="sxs-lookup"><span data-stu-id="6bcc4-135">**Notes**:</span></span>

  - <span data-ttu-id="6bcc4-136">Microsoft 365 管理センター の対応する Azure Active Directory ロールにユーザーを追加すると、Microsoft 365 Defender ポータルで必要なアクセス許可と、Microsoft 365の他の機能に対するアクセス許可が付与されます。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-136">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="6bcc4-137">詳細については、「[管理者の役割について](../../admin/add-users/about-admin-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-137">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="6bcc4-138">[Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups)の **閲覧専用の組織管理** の役割グループが この機能への読み取り専用アクセス権も付与します。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-138">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="6bcc4-139">添付ファイル ポリシーの推奨設定セーフ、添付ファイルの設定[セーフ参照してください](recommended-settings-for-eop-and-office365.md#safe-attachments-settings)。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-139">For our recommended settings for Safe Attachments policies, see [Safe Attachments settings](recommended-settings-for-eop-and-office365.md#safe-attachments-settings).</span></span>

- <span data-ttu-id="6bcc4-140">新しいポリシーまたは更新されたポリシーを適用するには、最大 30 分かかります。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-140">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-create-safe-attachments-policies"></a><span data-ttu-id="6bcc4-141">添付ファイル ポリシー Microsoft 365 Defender作成するには、セーフポータルを使用します。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-141">Use the Microsoft 365 Defender portal to create Safe Attachments policies</span></span>

<span data-ttu-id="6bcc4-142">Microsoft 365 Defender ポータルでカスタム セーフ 添付ファイル ポリシーを作成すると、両方に同じ名前を使用して、安全な添付ファイル ルールと関連付けられた安全な添付ファイル ポリシーが同時に作成されます。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-142">Creating a custom Safe Attachments policy in the Microsoft 365 Defender portal creates the safe attachment rule and the associated safe attachment policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="6bcc4-143">このポータルMicrosoft 365 Defender、[電子メール グループ &ルールの脅威ポリシー&ポリシー] セクションの [添付ファイル] に \>  \>  \>  \> **セーフします**。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-143">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Safe Attachments**.</span></span>

2. <span data-ttu-id="6bcc4-144">[添付ファイル **セーフ] ページで**、[作成] ![ アイコン [作成] を ](../../media/m365-cc-sc-create-icon.png) **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-144">On the **Safe Attachments** page, click ![Create icon](../../media/m365-cc-sc-create-icon.png) **Create**.</span></span>

3. <span data-ttu-id="6bcc4-145">ポリシー ウィザードが開きます。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-145">The policy wizard opens.</span></span> <span data-ttu-id="6bcc4-146">[ポリシーに **名前を付け] ページ** で、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-146">On the **Name your policy** page, configure the following settings:</span></span>
   - <span data-ttu-id="6bcc4-147">**[名前]**: わかりやすい一意のポリシー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-147">**Name**: Enter a unique, descriptive name for the policy.</span></span>
   - <span data-ttu-id="6bcc4-148">**[説明]**: ポリシーについての説明を入力します (オプション)。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-148">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="6bcc4-149">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-149">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="6bcc4-150">表示される **[ユーザーとドメイン] ページ** で、ポリシーが適用される内部受信者 (受信者の条件) を特定します。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-150">On the **Users and domains** page that appears, identify the internal recipients that the policy applies to (recipient conditions):</span></span>
   - <span data-ttu-id="6bcc4-151">**ユーザー**: 組織内で指定された 1 つ以上のメールボックス、メール ユーザー、またはメール連絡先。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-151">**Users**: The specified mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="6bcc4-152">**グループ**: 組織内で指定された配布グループ、メール対応セキュリティ グループ、または Microsoft 365 グループ。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-152">**Groups**: The specified distribution groups, mail-enabled security groups, or Microsoft 365 Groups in your organization.</span></span>
   - <span data-ttu-id="6bcc4-153">**ドメイン**: 組織内で指定された [承認済みドメイン](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)のすべての受信者。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-153">**Domains**: All recipients in the specified [accepted domains](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) in your organization.</span></span>

   <span data-ttu-id="6bcc4-154">適正なボックスをクリックし、値の入力を開始し、結果で希望する値を選択します。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-154">Click in the appropriate box, start typing a value, and select the value that you want from the results.</span></span> <span data-ttu-id="6bcc4-155">必要な回数だけこの処理を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-155">Repeat this process as many times as necessary.</span></span> <span data-ttu-id="6bcc4-156">既存の値を削除するには、削除をクリックします</span><span class="sxs-lookup"><span data-stu-id="6bcc4-156">To remove an existing value, click remove</span></span> ![[削除] アイコン](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="6bcc4-158">値の隣。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-158">next to the value.</span></span>

   <span data-ttu-id="6bcc4-159">ユーザーやグループには、ほとんどの識別子 (名前、表示名、エイリアス、メールアドレス、アカウント名など) を使用できますが、対応する表示名が結果に表示されます。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-159">For users or groups, you can use most identifiers (name, display name, alias, email address, account name, etc.), but the corresponding display name is shown in the results.</span></span> <span data-ttu-id="6bcc4-160">ユーザーの場合、アスタリスク (\*) を単独で入力すると、使用可能なすべての値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-160">For users, enter an asterisk (\*) by itself to see all available values.</span></span>

   <span data-ttu-id="6bcc4-161">同じ条件に複数の値がある場合、OR ロジック (たとえば、_\<recipient1\>_ または _\<recipient2\>_) が適用されます。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-161">Multiple values in the same condition use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="6bcc4-162">別の条件では、AND ロジック (たとえば、_\<recipient1\>_ かつ _\<member of group 1\>_) を使用します。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-162">Different conditions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   - <span data-ttu-id="6bcc4-163">**これらのユーザー、グループ、およびドメインを除外する**: ポリシーが適用される内部の受信者に関する例外 (受信者の例外) を追加するには、このオプションを選択して例外を構成します。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-163">**Exclude these users, groups, and domains**: To add exceptions for the internal recipients that the policy applies to (recpient exceptions), select this option and configure the exceptions.</span></span> <span data-ttu-id="6bcc4-164">設定と動作は、条件とまったく同じです。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-164">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="6bcc4-165">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-165">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="6bcc4-166">[設定]**設定** で、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-166">On the **Settings** page, configure the following settings:</span></span>

   - <span data-ttu-id="6bcc4-167">**セーフ添付ファイルの不明なマルウェアの応答**: 次のいずれかの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-167">**Safe Attachments unknown malware response**: Select one of the following values:</span></span>
     - <span data-ttu-id="6bcc4-168">**Off**: 通常、この値はお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-168">**Off**: Typically, we don't recommend this value.</span></span>
     - <span data-ttu-id="6bcc4-169">**モニター**</span><span class="sxs-lookup"><span data-stu-id="6bcc4-169">**Monitor**</span></span>
     - <span data-ttu-id="6bcc4-170">**ブロック**: これは既定値で、Standard および Strict の事前設定されたセキュリティ ポリシーで [推奨される値です](preset-security-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-170">**Block**: This is the default value, and the recommended value in Standard and Strict [preset security policies](preset-security-policies.md).</span></span>
     - <span data-ttu-id="6bcc4-171">**Replace**</span><span class="sxs-lookup"><span data-stu-id="6bcc4-171">**Replace**</span></span>
     - <span data-ttu-id="6bcc4-172">**動的配信 (プレビュー機能)**</span><span class="sxs-lookup"><span data-stu-id="6bcc4-172">**Dynamic Delivery (Preview Feature)**</span></span>

     <span data-ttu-id="6bcc4-173">これらの値については、「添付ファイルポリシー[セーフ」で説明します](safe-attachments.md#safe-attachments-policy-settings)。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-173">These values are explained in [Safe Attachments policy settings](safe-attachments.md#safe-attachments-policy-settings).</span></span>

   - <span data-ttu-id="6bcc4-174">検出された添付ファイルを含むメッセージをリダイレクト **する**: [リダイレクトを有効にする]を選択した場合は、[ブロック、監視、または置換された添付ファイルを含むメール アドレスを指定して指定した電子メール アドレス] ボックスに電子メール アドレスを指定して、分析と調査のためにマルウェア添付ファイルを含むメッセージを送信できます。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-174">**Redirect messages with detected attachments**: If you select **Enable redirect**, you can specify an email address in the **Send messages that contain blocked, monitored, or replaced attachments to the specified email address** box to send messages that contain malware attachments for analysis and investigation.</span></span>

     <span data-ttu-id="6bcc4-175">標準ポリシーと厳密なポリシー設定の推奨事項は、リダイレクトを有効にしてください。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-175">The recommendation for Standard and Strict policy settings is to enable redirection.</span></span> <span data-ttu-id="6bcc4-176">詳細については、「添付ファイルの[設定セーフ参照してください](recommended-settings-for-eop-and-office365.md#safe-attachments-settings)。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-176">For more information, see [Safe Attachments settings](recommended-settings-for-eop-and-office365.md#safe-attachments-settings).</span></span>

   - <span data-ttu-id="6bcc4-177">スキャンが **完了できない**(タイムアウトまたはエラー) 場合は、セーフ 添付ファイル検出応答を適用します。セーフ 添付ファイルの不明なマルウェア応答で指定されたアクションは **、セーフ** 添付ファイルのスキャンが完了できない場合でもメッセージに対して実行されます。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-177">**Apply the Safe Attachments detection response if scanning can't complete (timeout or errors)**: The action specified by **Safe Attachments unknown malware response** is taken on messages even when Safe Attachments scanning can't complete.</span></span> <span data-ttu-id="6bcc4-178">このオプションを選択した場合は、常に [リダイレクトを有効にする] **を** 選択し、マルウェアの添付ファイルを含むメッセージを送信する電子メール アドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-178">If you selected this option, always select **Enable redirect** and specify an email address to send messages that contain malware attachments.</span></span> <span data-ttu-id="6bcc4-179">それ以外の場合、メッセージが失われる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-179">Otherwise, messages might be lost.</span></span>

   <span data-ttu-id="6bcc4-180">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-180">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="6bcc4-181">表示された **[レビュー]** ページで、設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-181">On the **Review** page that appears, review your settings.</span></span> <span data-ttu-id="6bcc4-182">各セクションで **[編集]** を選択して、そのセクション内の設定を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-182">You can select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="6bcc4-183">または、**[戻る]** をクリックするか、ウィザードで特定のページを選択します。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-183">Or you can click **Back** or select the specific page in the wizard.</span></span>

   <span data-ttu-id="6bcc4-184">完了したら、**[送信]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-184">When you're finished, click **Submit**.</span></span>

7. <span data-ttu-id="6bcc4-185">表示された [確認]ページで、**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-185">On the confirmation page that appears, click **Done**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-view-safe-attachments-policies"></a><span data-ttu-id="6bcc4-186">添付ファイル ポリシー Microsoft 365 Defenderを表示するには、セーフポータルを使用します。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-186">Use the Microsoft 365 Defender portal to view Safe Attachments policies</span></span>

1. <span data-ttu-id="6bcc4-187">このポータルMicrosoft 365 Defender、[電子メール グループ &ルールの脅威ポリシー&ポリシー] セクションの [添付ファイル] に \>  \>  \>  \> **セーフします**。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-187">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Safe Attachments**.</span></span>

2. <span data-ttu-id="6bcc4-188">[添付 **セーフ] ページ** で、ポリシーの一覧に次のプロパティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-188">On the **Safe Attachments** page, the following properties are displayed in the list of policies:</span></span>
   - <span data-ttu-id="6bcc4-189">**名前**</span><span class="sxs-lookup"><span data-stu-id="6bcc4-189">**Name**</span></span>
   - <span data-ttu-id="6bcc4-190">**状態**</span><span class="sxs-lookup"><span data-stu-id="6bcc4-190">**Status**</span></span>
   - <span data-ttu-id="6bcc4-191">**優先度**</span><span class="sxs-lookup"><span data-stu-id="6bcc4-191">**Priority**</span></span>

3. <span data-ttu-id="6bcc4-192">名前をクリックしてポリシーを選択すると、ポリシー設定がフライアウトに表示されます。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-192">When you select a policy by clicking on the name, the policy settings are displayed in a flyout.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-modify-safe-attachments-policies"></a><span data-ttu-id="6bcc4-193">添付ファイル ポリシー Microsoft 365 Defender変更するには、セーフポータルを使用します。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-193">Use the Microsoft 365 Defender portal to modify Safe Attachments policies</span></span>

1. <span data-ttu-id="6bcc4-194">このポータルMicrosoft 365 Defender、[電子メール グループ &ルールの脅威ポリシー&ポリシー] セクションの [添付ファイル] に \>  \>  \>  \> **セーフします**。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-194">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Safe Attachments**.</span></span>

2. <span data-ttu-id="6bcc4-195">[添付 **ファイルセーフ]** ページで、名前をクリックして一覧からポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-195">On the **Safe Attachments** page, select a policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="6bcc4-196">表示されるポリシーの詳細ポップアップで、各セクションで **[編集]** を選択して、そのセクション内の設定を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-196">In the policy details flyout that appears, select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="6bcc4-197">設定の詳細については、この記事の前[](#use-the-microsoft-365-defender-portal-to-create-safe-attachments-policies)の「Microsoft 365 Defenderを使用して添付セーフポリシーを作成する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-197">For more information about the settings, see the [Use the Microsoft 365 Defender portal to create Safe Attachments policies](#use-the-microsoft-365-defender-portal-to-create-safe-attachments-policies) section earlier in this article.</span></span>  

<span data-ttu-id="6bcc4-198">ポリシーを有効または無効にするか、ポリシーの優先順位を設定するには、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-198">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-safe-attachments-policies"></a><span data-ttu-id="6bcc4-199">添付ファイル ポリシーのセーフまたは無効にする</span><span class="sxs-lookup"><span data-stu-id="6bcc4-199">Enable or disable Safe Attachments policies</span></span>

1. <span data-ttu-id="6bcc4-200">このポータルMicrosoft 365 Defender、[電子メール グループ &ルールの脅威ポリシー&ポリシー] セクションの [添付ファイル] に \>  \>  \>  \> **セーフします**。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-200">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Safe Attachments**.</span></span>

2. <span data-ttu-id="6bcc4-201">[添付 **ファイルセーフ]** ページで、名前をクリックして一覧からポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-201">On the **Safe Attachments** page, select a policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="6bcc4-202">表示されるポリシーの詳細ポップアップの上部には、以下のいずれかの値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-202">At the top of the policy details flyout that appears, you'll see one of the following values:</span></span>
   - <span data-ttu-id="6bcc4-203">**ポリシー オフ**: ポリシーをオンにするには、![[アイコンをオンにする]](../../media/m365-cc-sc-turn-on-off-icon.png)、**[オンにする]** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-203">**Policy off**: To turn on the policy, click ![Turn on icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn on** .</span></span>
   - <span data-ttu-id="6bcc4-204">**ポリシー オン**: ポリシーをオフにするには、![[アイコンをオフにする]](../../media/m365-cc-sc-turn-on-off-icon.png)、**[オフにする]** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-204">**Policy on**: To turn off the policy, click ![Turn off icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn off**.</span></span>

4. <span data-ttu-id="6bcc4-205">確認ダイアログ ボックスが表示されたら、**[オンにする]** または **[オフにする]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-205">In the confirmation dialog that appears, click **Turn on** or **Turn off**.</span></span>

5. <span data-ttu-id="6bcc4-206">ポリシーの詳細ポップアップで **[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-206">Click **Close** in the policy details flyout.</span></span>

<span data-ttu-id="6bcc4-207">ポリシーのメイン ページに戻ると、ポリシーの **[状態]** の値が **[オン]** または **[オフ]** になります。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-207">Back on the main policy page, the **Status** value of the policy will be **On** or **Off**.</span></span>

### <a name="set-the-priority-of-safe-attachments-policies"></a><span data-ttu-id="6bcc4-208">添付ファイル ポリシーのセーフ設定する</span><span class="sxs-lookup"><span data-stu-id="6bcc4-208">Set the priority of Safe Attachments policies</span></span>

<span data-ttu-id="6bcc4-209">既定では、セーフ添付ファイル ポリシーには、作成された順序に基づく優先度が与えられる (新しいポリシーは、以前のポリシーよりも優先度が低くなります)。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-209">By default, Safe Attachments policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="6bcc4-210">優先度番号が小さいほど、ポリシーの優先度が高くなる (0 が最優先) ことを意味し、ポリシーは優先順位に従って処理されます (優先度の高いポリシーは、優先度の低いポリシーよりも先に処理されます)。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-210">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="6bcc4-211">2つのポリシーが同じ優先順位を持つことはできません。最初のポリシーが適用されると、ポリシーの処理は停止します。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-211">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="6bcc4-212">優先順位と複数のポリシーを評価し適用する方法の詳細については、「[メール保護の優先順位](how-policies-and-protections-are-combined.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-212">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="6bcc4-213">セーフ添付ファイル ポリシーは、処理順に表示されます (最初のポリシーの **優先度** の値は 0 です)。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-213">Safe Attachments policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span>

<span data-ttu-id="6bcc4-214">**注**: このポータルMicrosoft 365 Defender、添付ファイル ポリシーの優先度を変更できるのは、セーフ後のみです。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-214">**Note**: In the Microsoft 365 Defender portal, you can only change the priority of the Safe Attachments policy after you create it.</span></span> <span data-ttu-id="6bcc4-215">PowerShell では、安全な添付ファイル ルールを作成するときに既定の優先度を上書きできます (既存のルールの優先度に影響を与える可能性があります)。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-215">In PowerShell, you can override the default priority when you create the safe attachment rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="6bcc4-216">ポリシーの優先度を変更するには、ポリシーのプロパティで **[優先度を上げる]** または **[優先度を下げる]** をクリックします (Microsoft 365 Defender ポータルの **[優先度]** の数値を直接変更することはできません)。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-216">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Microsoft 365 Defender portal).</span></span> <span data-ttu-id="6bcc4-217">ポリシーの優先度を変更することは、複数のポリシーを所有している場合にのみ意味があります。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-217">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="6bcc4-218">このポータルMicrosoft 365 Defender、[電子メール グループ &ルールの脅威ポリシー&ポリシー] セクションの [添付ファイル] に \>  \>  \>  \> **セーフします**。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-218">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Safe Attachments**.</span></span>

2. <span data-ttu-id="6bcc4-219">[添付 **ファイルセーフ]** ページで、名前をクリックして一覧からポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-219">On the **Safe Attachments** page, select a policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="6bcc4-220">表示されるポリシー詳細のフライアウトの上部に、現在の優先度の値とポリシーの数に基づいて[優先度の増加] または [優先度の下げ] が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-220">At the top of the policy details flyout that appears, you'll see **Increase priority** or **Decrease priority** based on the current priority value and the number of policies:</span></span>
   - <span data-ttu-id="6bcc4-221">優先度の値が **0** **のポリシー** には、[優先度を下にする]**オプションしか** 使用できません。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-221">The policy with the **Priority** value **0** has only the **Decrease priority** option available.</span></span>
   - <span data-ttu-id="6bcc4-222">優先度の値が最も **低い** ポリシー ( **たとえば、3)** には、[優先度の引き上げ] **オプション** しか使用できません。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-222">The policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** option available.</span></span>
   - <span data-ttu-id="6bcc4-223">3 つ以上のポリシーがある場合、優先度の高い値と最も低い優先度の値の間のポリシーには、[優先度の引き上げ] オプションと [優先度の下 **げ]** の両方 **のオプションがあります** 。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-223">If you have three or more policies, the policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** options available.</span></span>

   <span data-ttu-id="6bcc4-224">![[優先度を上げる] アイコン](../../media/m365-cc-sc-increase-icon.png)、**[優先度を上げる]** の順にクリックするか、または ![[優先度を下げる] アイコン](../../media/m365-cc-sc-decrease-icon.png)、**[優先度を下げる]** の順にクリックして、**優先度** 値を変更します。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-224">Click ![Increase priority icon](../../media/m365-cc-sc-increase-icon.png) **Increase priority** or ![Decrease priority icon](../../media/m365-cc-sc-decrease-icon.png) **Decrease priority** to change the **Priority** value.</span></span>

4. <span data-ttu-id="6bcc4-225">完了したら、ポリシーの詳細ポップアップで **[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-225">When you're finished, click **Close** in the policy details flyout.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-remove-safe-attachments-policies"></a><span data-ttu-id="6bcc4-226">添付ファイル ポリシー Microsoft 365 Defender削除するには、セーフポータルを使用します。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-226">Use the Microsoft 365 Defender portal to remove Safe Attachments policies</span></span>

1. <span data-ttu-id="6bcc4-227">このポータルMicrosoft 365 Defender、[電子メール グループ &ルールの脅威ポリシー&ポリシー] セクションの [添付ファイル] に \>  \>  \>  \> **セーフします**。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-227">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Safe Attachments**.</span></span>

2. <span data-ttu-id="6bcc4-228">[添付 **セーフ] ページ** で、ポリシーの名前をクリックして、一覧からカスタム ポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-228">On the **Safe Attachments** page, select a custom policy from the list by clicking on the name of the policy.</span></span>

3. <span data-ttu-id="6bcc4-229">表示されるポリシーの詳細ポップアウトの上部で、![[その他の操作] アイコン](../../media/m365-cc-sc-more-actions-icon.png)、**[その他の操作]** \>、![[ポリシーの削除] アイコン](../../media/m365-cc-sc-delete-icon.png)、**[ポリシーの削除]** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-229">At the top of the policy details flyout that appears, click ![More actions icon](../../media/m365-cc-sc-more-actions-icon.png) **More actions** \> ![Delete policy icon](../../media/m365-cc-sc-delete-icon.png) **Delete policy**.</span></span>

4. <span data-ttu-id="6bcc4-230">確認ダイアログ ボックスが表示されたら、**[はい]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-230">In the confirmation dialog that appears, click **Yes**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies"></a><span data-ttu-id="6bcc4-231">PowerShell Exchange Onlineスタンドアロン EOP PowerShell を使用して添付ファイル ポリシーセーフ構成する</span><span class="sxs-lookup"><span data-stu-id="6bcc4-231">Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Attachments policies</span></span>

<span data-ttu-id="6bcc4-232">前に説明したように、セーフ添付ファイル ポリシーは、安全な添付ファイル ポリシーと安全な添付ファイル ルールで構成されます。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-232">As previously described, a Safe Attachments policy consists of a safe attachment policy and a safe attachment rule.</span></span>

<span data-ttu-id="6bcc4-233">PowerShell では、安全な添付ファイル ポリシーと安全な添付ファイルルールの違いが明らかです。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-233">In PowerShell, the difference between safe attachment policies and safe attachment rules is apparent.</span></span> <span data-ttu-id="6bcc4-234">**\* -SafeAttachmentPolicy** コマンドレットを使用して安全な添付ファイル ポリシーを管理し **\* 、-SafeAttachmentRule** コマンドレットを使用して安全な添付ファイル ルールを管理します。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-234">You manage safe attachment policies by using the **\*-SafeAttachmentPolicy** cmdlets, and you manage safe attachment rules by using the **\*-SafeAttachmentRule** cmdlets.</span></span>

- <span data-ttu-id="6bcc4-235">PowerShell では、最初に安全な添付ファイル ポリシーを作成してから、ルールが適用されるポリシーを識別する安全な添付ファイル ルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-235">In PowerShell, you create the safe attachment policy first, then you create the safe attachment rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="6bcc4-236">PowerShell では、安全な添付ファイル ポリシーと安全な添付ファイルルールの設定を個別に変更します。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-236">In PowerShell, you modify the settings in the safe attachment policy and the safe attachment rule separately.</span></span>
- <span data-ttu-id="6bcc4-237">PowerShell から安全な添付ファイル ポリシーを削除しても、対応する安全な添付ファイル ルールは自動的には削除されません。その逆も同様です。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-237">When you remove a safe attachment policy from PowerShell, the corresponding safe attachment rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-safe-attachments-policies"></a><span data-ttu-id="6bcc4-238">PowerShell を使用して添付ファイル ポリシーセーフ作成する</span><span class="sxs-lookup"><span data-stu-id="6bcc4-238">Use PowerShell to create Safe Attachments policies</span></span>

<span data-ttu-id="6bcc4-239">PowerShell でセーフ添付ファイル ポリシーを作成するには、次の 2 つの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-239">Creating a Safe Attachments policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="6bcc4-240">安全な添付ファイル ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-240">Create the safe attachment policy.</span></span>
2. <span data-ttu-id="6bcc4-241">ルールが適用される安全な添付ファイル ポリシーを指定する安全な添付ファイル ルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-241">Create the safe attachment rule that specifies the safe attachment policy that the rule applies to.</span></span>

 <span data-ttu-id="6bcc4-242">**注**:</span><span class="sxs-lookup"><span data-stu-id="6bcc4-242">**Notes**:</span></span>

- <span data-ttu-id="6bcc4-243">新しい安全な添付ファイル ルールを作成し、関連付けされていない既存の安全な添付ファイル ポリシーを割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-243">You can create a new safe attachment rule and assign an existing, unassociated safe attachment policy to it.</span></span> <span data-ttu-id="6bcc4-244">安全な添付ファイル ルールを複数の安全な添付ファイル ポリシーに関連付けできない。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-244">A safe attachment rule can't be associated with more than one safe attachment policy.</span></span>

- <span data-ttu-id="6bcc4-245">PowerShell の新しい安全な添付ファイル ポリシーで、ポリシーの作成後まで、Microsoft 365 Defender ポータルで使用できない次の設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-245">You can configure the following settings on new safe attachment policies in PowerShell that aren't available in the Microsoft 365 Defender portal until after you create the policy:</span></span>
  - <span data-ttu-id="6bcc4-246">新しいポリシーを無効として作成 _します_ `$false` **(New-SafeAttachmentRule コマンドレットで有効** )。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-246">Create the new policy as disabled (_Enabled_ `$false` on the **New-SafeAttachmentRule** cmdlet).</span></span>
  - <span data-ttu-id="6bcc4-247"> _\<Number\>_ **New-SafeAttachmentRule** コマンドレットの作成時にポリシーの優先度 (優先度) を設定します。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-247">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-SafeAttachmentRule** cmdlet).</span></span>

- <span data-ttu-id="6bcc4-248">PowerShell で作成した新しい安全な添付ファイル ポリシーは、ポリシーを安全な添付ファイル ルールに割り当てるMicrosoft 365 Defenderポータルには表示されません。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-248">A new safe attachment policy that you create in PowerShell isn't visible in the Microsoft 365 Defender portal until you assign the policy to a safe attachment rule.</span></span>

#### <a name="step-1-use-powershell-to-create-a-safe-attachment-policy"></a><span data-ttu-id="6bcc4-249">手順 1: PowerShell を使用して安全な添付ファイル ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="6bcc4-249">Step 1: Use PowerShell to create a safe attachment policy</span></span>

<span data-ttu-id="6bcc4-250">安全な添付ファイル ポリシーを作成するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-250">To create a safe attachment policy, use this syntax:</span></span>

```PowerShell
New-SafeAttachmentPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-Action <Allow | Block | Replace | DynamicDelivery>] [-Redirect <$true | $false>] [-RedirectAddress <SMTPEmailAddress>] [-ActionOnError <$true | $false>]
```

<span data-ttu-id="6bcc4-251">この例では、Contoso All という名前の安全な添付ファイル ポリシーを次の値で作成します。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-251">This example creates a safe attachment policy named Contoso All with the following values:</span></span>

- <span data-ttu-id="6bcc4-252">[ドキュメント] スキャンによってマルウェアがセーフ検出されたメッセージをブロックします _(Action_ パラメーターは使用していないので、既定値はです `Block` )。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-252">Block messages that are found to contain malware by Safe Documents scanning (we aren't using the _Action_ parameter, and the default value is `Block`).</span></span>
- <span data-ttu-id="6bcc4-253">リダイレクトが有効になっていると、マルウェアが含まれていると検出されたメッセージは、分析と調査のために sec-ops@contoso.com に送信されます。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-253">Redirection is enabled, and messages that are found to contain malware are sent to sec-ops@contoso.com for analysis and investigation.</span></span>
- <span data-ttu-id="6bcc4-254">添付セーフスキャンが使用できない場合、またはエラーが発生した場合は、メッセージを配信しません _(ActionOnError_ パラメーターは使用していないので、既定値はです `$true` )。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-254">If Safe Attachments scanning isn't available or encounters errors, don't deliver the message (we aren't using the _ActionOnError_ parameter, and the default value is `$true`).</span></span>

```PowerShell
New-SafeAttachmentPolicy -Name "Contoso All" -Redirect $true -RedirectAddress sec-ops@contoso.com
```

<span data-ttu-id="6bcc4-255">構文とパラメーターの詳細については [、「New-SafeAttachmentPolicy」を参照してください](/powershell/module/exchange/new-safeattachmentpolicy)。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-255">For detailed syntax and parameter information, see [New-SafeAttachmentPolicy](/powershell/module/exchange/new-safeattachmentpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-a-safe-attachment-rule"></a><span data-ttu-id="6bcc4-256">手順 2: PowerShell を使用して安全な添付ファイル ルールを作成する</span><span class="sxs-lookup"><span data-stu-id="6bcc4-256">Step 2: Use PowerShell to create a safe attachment rule</span></span>

<span data-ttu-id="6bcc4-257">安全な添付ファイル ルールを作成するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-257">To create a safe attachment rule, use this syntax:</span></span>

```PowerShell
New-SafeAttachmentRule -Name "<RuleName>" -SafeAttachmentPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

<span data-ttu-id="6bcc4-258">この例では、Contoso All という名前の安全な添付ファイル ルールを次の条件で作成します。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-258">This example creates a safe attachment rule named Contoso All with the following conditions:</span></span>

- <span data-ttu-id="6bcc4-259">このルールは、Contoso All という名前の安全な添付ファイル ポリシーに関連付けられている。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-259">The rule is associated with the safe attachment policy named Contoso All.</span></span>
- <span data-ttu-id="6bcc4-260">ルールは、ドメイン内のすべての受信者に contoso.com されます。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-260">The rule applies to all recipients in the contoso.com domain.</span></span>
- <span data-ttu-id="6bcc4-261">Priority パラメーターを使用していないので _、既定_ の優先度が使用されます。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-261">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>
- <span data-ttu-id="6bcc4-262">ルールが有効になっています (Enabled パラメーターは使用しませんが、既定値はです `$true` )。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-262">The rule is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>

```powershell
New-SafeAttachmentRule -Name "Contoso All" -SafeAttachmentPolicy "Contoso All" -RecipientDomainIs contoso.com
```

<span data-ttu-id="6bcc4-263">構文とパラメーターの詳細については [、「New-SafeAttachmentRule」を参照してください](/powershell/module/exchange/new-safeattachmentrule)。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-263">For detailed syntax and parameter information, see [New-SafeAttachmentRule](/powershell/module/exchange/new-safeattachmentrule).</span></span>

### <a name="use-powershell-to-view-safe-attachment-policies"></a><span data-ttu-id="6bcc4-264">PowerShell を使用して安全な添付ファイル ポリシーを表示する</span><span class="sxs-lookup"><span data-stu-id="6bcc4-264">Use PowerShell to view safe attachment policies</span></span>

<span data-ttu-id="6bcc4-265">既存の安全な添付ファイル ポリシーを表示するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-265">To view existing safe attachment policies, use the following syntax:</span></span>

```PowerShell
Get-SafeAttachmentPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="6bcc4-266">この例では、すべての安全な添付ファイル ポリシーの概要一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-266">This example returns a summary list of all safe attachment policies.</span></span>

```PowerShell
Get-SafeAttachmentPolicy
```

<span data-ttu-id="6bcc4-267">この例では、Contoso Executives という名前の安全な添付ファイル ポリシーの詳細情報を返します。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-267">This example returns detailed information for the safe attachment policy named Contoso Executives.</span></span>

```PowerShell
Get-SafeAttachmentPolicy -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="6bcc4-268">構文とパラメーターの詳細については [、「Get-SafeAttachmentPolicy」を参照してください](/powershell/module/exchange/get-safeattachmentpolicy)。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-268">For detailed syntax and parameter information, see [Get-SafeAttachmentPolicy](/powershell/module/exchange/get-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-view-safe-attachment-rules"></a><span data-ttu-id="6bcc4-269">PowerShell を使用して安全な添付ファイル ルールを表示する</span><span class="sxs-lookup"><span data-stu-id="6bcc4-269">Use PowerShell to view safe attachment rules</span></span>

<span data-ttu-id="6bcc4-270">既存の安全な添付ファイル ルールを表示するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-270">To view existing safe attachment rules, use the following syntax:</span></span>

```PowerShell
Get-SafeAttachmentRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="6bcc4-271">次の使用例は、すべての安全な添付ファイル ルールの概要リストを返します。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-271">This example returns a summary list of all safe attachment rules.</span></span>

```PowerShell
Get-SafeAttachmentRule
```

<span data-ttu-id="6bcc4-272">ルールを有効または無効にしてリストをフィルター処理するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-272">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-SafeAttachmentRule -State Disabled
```

```PowerShell
Get-SafeAttachmentRule -State Enabled
```

<span data-ttu-id="6bcc4-273">この例では、Contoso Executives という名前の安全な添付ファイル ルールの詳細情報を返します。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-273">This example returns detailed information for the safe attachment rule named Contoso Executives.</span></span>

```PowerShell
Get-SafeAttachmentRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="6bcc4-274">構文とパラメーターの詳細については [、「Get-SafeAttachmentRule」を参照してください](/powershell/module/exchange/get-safeattachmentrule)。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-274">For detailed syntax and parameter information, see [Get-SafeAttachmentRule](/powershell/module/exchange/get-safeattachmentrule).</span></span>

### <a name="use-powershell-to-modify-safe-attachment-policies"></a><span data-ttu-id="6bcc4-275">PowerShell を使用して安全な添付ファイル ポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="6bcc4-275">Use PowerShell to modify safe attachment policies</span></span>

<span data-ttu-id="6bcc4-276">PowerShell で安全な添付ファイル ポリシーの名前を変更することはできません **(Set-SafeAttachmentPolicy** コマンドレットには _Name_ パラメーターはありません)。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-276">You can't rename a safe attachment policy in PowerShell (the **Set-SafeAttachmentPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="6bcc4-277">新しい添付ファイル セーフポリシーの名前を変更Microsoft 365 Defender、安全な添付ファイル ルールの名前を変更 _する必要があります_。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-277">When you rename a Safe Attachments policy in the Microsoft 365 Defender portal, you're only renaming the safe attachment _rule_.</span></span>

<span data-ttu-id="6bcc4-278">それ以外の場合は、この記事の「手順 [1: PowerShell](#step-1-use-powershell-to-create-a-safe-attachment-policy) を使用して安全な添付ファイル ポリシーを作成する」セクションで説明したように、安全な添付ファイル ポリシーを作成するときに同じ設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-278">Otherwise, the same settings are available when you create a safe attachment policy as described in the [Step 1: Use PowerShell to create a safe attachment policy](#step-1-use-powershell-to-create-a-safe-attachment-policy) section earlier in this article.</span></span>

<span data-ttu-id="6bcc4-279">安全な添付ファイル ポリシーを変更するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-279">To modify a safe attachment policy, use this syntax:</span></span>

```PowerShell
Set-SafeAttachmentPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="6bcc4-280">構文とパラメーターの詳細については [、「Set-SafeAttachmentPolicy」を参照してください](/powershell/module/exchange/set-safeattachmentpolicy)。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-280">For detailed syntax and parameter information, see [Set-SafeAttachmentPolicy](/powershell/module/exchange/set-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-modify-safe-attachment-rules"></a><span data-ttu-id="6bcc4-281">PowerShell を使用して安全な添付ファイル ルールを変更する</span><span class="sxs-lookup"><span data-stu-id="6bcc4-281">Use PowerShell to modify safe attachment rules</span></span>

<span data-ttu-id="6bcc4-282">PowerShell で安全な添付ファイル ルールを変更するときに使用できない唯一の設定は、無効なルールを作成できる _Enabled_ パラメーターです。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-282">The only setting that's not available when you modify a safe attachment rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="6bcc4-283">既存の安全な添付ファイル ルールを有効または無効にするには、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-283">To enable or disable existing safe attachment rules, see the next section.</span></span>

<span data-ttu-id="6bcc4-284">それ以外の場合は、「手順 [2: PowerShell](#step-2-use-powershell-to-create-a-safe-attachment-rule) を使用して安全な添付ファイルルールを作成する」セクションで説明したように、ルールを作成するときに同じ設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-284">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create a safe attachment rule](#step-2-use-powershell-to-create-a-safe-attachment-rule) section earlier in this article.</span></span>

<span data-ttu-id="6bcc4-285">安全な添付ファイル ルールを変更するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-285">To modify a safe attachment rule, use this syntax:</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="6bcc4-286">構文とパラメーターの詳細については [、「Set-SafeAttachmentRule」を参照してください](/powershell/module/exchange/set-safeattachmentrule)。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-286">For detailed syntax and parameter information, see [Set-SafeAttachmentRule](/powershell/module/exchange/set-safeattachmentrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-safe-attachment-rules"></a><span data-ttu-id="6bcc4-287">PowerShell を使用して安全な添付ファイル ルールを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="6bcc4-287">Use PowerShell to enable or disable safe attachment rules</span></span>

<span data-ttu-id="6bcc4-288">PowerShell で安全な添付ファイル ルールを有効または無効にすると、セーフ 添付ファイル ポリシー (安全な添付ファイル ルールと割り当てられた安全な添付ファイル ポリシー) 全体が有効または無効となります。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-288">Enabling or disabling a safe attachment rule in PowerShell enables or disables the whole Safe Attachments policy (the safe attachment rule and the assigned safe attachment policy).</span></span>

<span data-ttu-id="6bcc4-289">PowerShell で安全な添付ファイル ルールを有効または無効にするには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-289">To enable or disable a safe attachment rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-SafeAttachmentRule | Disable-SafeAttachmentRule> -Identity "<RuleName>"
```

<span data-ttu-id="6bcc4-290">この例では、Marketing Department という名前の安全な添付ファイル ルールを無効にします。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-290">This example disables the safe attachment rule named Marketing Department.</span></span>

```PowerShell
Disable-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="6bcc4-291">この例では、同じルールを有効化します。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-291">This example enables same rule.</span></span>

```PowerShell
Enable-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="6bcc4-292">構文とパラメーターの詳細については [、「Enable-SafeAttachmentRule」](/powershell/module/exchange/enable-safeattachmentrule) および [「Disable-SafeAttachmentRule」を参照してください](/powershell/module/exchange/disable-safeattachmentrule)。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-292">For detailed syntax and parameter information, see [Enable-SafeAttachmentRule](/powershell/module/exchange/enable-safeattachmentrule) and [Disable-SafeAttachmentRule](/powershell/module/exchange/disable-safeattachmentrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-safe-attachment-rules"></a><span data-ttu-id="6bcc4-293">PowerShell を使用して安全な添付ファイル ルールの優先度を設定する</span><span class="sxs-lookup"><span data-stu-id="6bcc4-293">Use PowerShell to set the priority of safe attachment rules</span></span>

<span data-ttu-id="6bcc4-p126">ルールに設定できる優先度の最高値値は 0 です。設定できる最低値はルールの数に依存します。たとえば、ルールが五つある場合、使用できる優先度の値は 0 から 4 です。既存の一つのルールの優先度を変更すると、他のルールにも連鎖的な影響が起こりえます。たとえば、カスタム ルールが五つある場合 (優先度 0 から 4) に、一つのルールの優先度を 2 に変更した場合、既存の優先度 2 のルールは優先度 3 に変更され、優先度 3 は優先度 4 に変更されます。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-p126">The highest priority value you can set on a rule is 0. The lowest value you can set depends on the number of rules. For example, if you have five rules, you can use the priority values 0 through 4. Changing the priority of an existing rule can have a cascading effect on other rules. For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="6bcc4-299">PowerShell で安全な添付ファイル ルールの優先度を設定するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-299">To set the priority of a safe attachment rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="6bcc4-p127">この例では、Marketing Department というルールの優先度を 2 に設定しています。優先度が 2 以下のすべての既存のルールは、優先度が 1 ずつ下がります (優先度番号が 1 ずつ増加します)。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-p127">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="6bcc4-302">**注**: 新しいルールを作成するときに優先度を設定するには **、New-SafeAttachmentRule** コマンドレットの Priority パラメーターを使用します。 </span><span class="sxs-lookup"><span data-stu-id="6bcc4-302">**Note**: To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-SafeAttachmentRule** cmdlet instead.</span></span>

<span data-ttu-id="6bcc4-303">構文とパラメーターの詳細については [、「Set-SafeAttachmentRule」を参照してください](/powershell/module/exchange/set-safeattachmentrule)。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-303">For detailed syntax and parameter information, see [Set-SafeAttachmentRule](/powershell/module/exchange/set-safeattachmentrule).</span></span>

### <a name="use-powershell-to-remove-safe-attachment-policies"></a><span data-ttu-id="6bcc4-304">PowerShell を使用して安全な添付ファイル ポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="6bcc4-304">Use PowerShell to remove safe attachment policies</span></span>

<span data-ttu-id="6bcc4-305">PowerShell を使用して安全な添付ファイル ポリシーを削除しても、対応する安全な添付ファイル ルールは削除されません。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-305">When you use PowerShell to remove a safe attachment policy, the corresponding safe attachment rule isn't removed.</span></span>

<span data-ttu-id="6bcc4-306">PowerShell で安全な添付ファイル ポリシーを削除するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-306">To remove a safe attachment policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeAttachmentPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="6bcc4-307">この例では、Marketing Department という名前の安全な添付ファイル ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-307">This example removes the safe attachment policy named Marketing Department.</span></span>

```PowerShell
Remove-SafeAttachmentPolicy -Identity "Marketing Department"
```

<span data-ttu-id="6bcc4-308">構文とパラメーターの詳細については [、「Remove-SafeAttachmentPolicy」を参照してください](/powershell/module/exchange/remove-safeattachmentpolicy)。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-308">For detailed syntax and parameter information, see [Remove-SafeAttachmentPolicy](/powershell/module/exchange/remove-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-remove-safe-attachment-rules"></a><span data-ttu-id="6bcc4-309">PowerShell を使用して安全な添付ファイル ルールを削除する</span><span class="sxs-lookup"><span data-stu-id="6bcc4-309">Use PowerShell to remove safe attachment rules</span></span>

<span data-ttu-id="6bcc4-310">PowerShell を使用して安全な添付ファイル ルールを削除しても、対応する安全な添付ファイル ポリシーは削除されません。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-310">When you use PowerShell to remove a safe attachment rule, the corresponding safe attachment policy isn't removed.</span></span>

<span data-ttu-id="6bcc4-311">PowerShell で安全な添付ファイル ルールを削除するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-311">To remove a safe attachment rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeAttachmentRule -Identity "<PolicyName>"
```

<span data-ttu-id="6bcc4-312">この例では、Marketing Department という名前の安全な添付ファイル ルールを削除します。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-312">This example removes the safe attachment rule named Marketing Department.</span></span>

```PowerShell
Remove-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="6bcc4-313">構文とパラメーターの詳細については [、「Remove-SafeAttachmentRule」を参照してください](/powershell/module/exchange/remove-safeattachmentrule)。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-313">For detailed syntax and parameter information, see [Remove-SafeAttachmentRule](/powershell/module/exchange/remove-safeattachmentrule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="6bcc4-314">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="6bcc4-314">How do you know these procedures worked?</span></span>

<span data-ttu-id="6bcc4-315">添付ファイル ポリシーが正常に作成、変更、または削除されたことを確認するにはセーフ手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-315">To verify that you've successfully created, modified, or removed Safe Attachments policies, do any of the following steps:</span></span>

- <span data-ttu-id="6bcc4-316">このポータルMicrosoft 365 Defender、[電子メール グループ &ルールの脅威ポリシー&ポリシー] セクションの [添付ファイル] に \>  \>  \>  \> **セーフします**。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-316">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Safe Attachments**.</span></span> <span data-ttu-id="6bcc4-317">ポリシー、その状態の値、および **優先度** の値の一覧を **確認** します。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-317">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="6bcc4-318">詳細を表示するには、名前をクリックして一覧からポリシーを選択し、詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-318">To view more details, select the policy from the list by clicking on the name, and view the details in the fly out.</span></span>

- <span data-ttu-id="6bcc4-319">PowerShell Exchange Onlineまたは PowerShell Exchange Online Protectionで、ポリシーまたはルールの名前に置き換え、次のコマンドを実行し、 \<Name\> 設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-319">In Exchange Online PowerShell or Exchange Online Protection PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-SafeAttachmentPolicy -Identity "<Name>" | Format-List
  ```

  ```PowerShell
  Get-SafeAttachmentRule -Identity "<Name>" | Format-List
  ```

<span data-ttu-id="6bcc4-320">[添付ファイル] セーフスキャンメッセージを確認するには、使用可能な Defender でレポートをOffice 365します。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-320">To verify that Safe Attachments is scanning messages, check the available Defender for Office 365 reports.</span></span> <span data-ttu-id="6bcc4-321">詳細については、「View [reports for Defender for Office 365」](view-reports-for-mdo.md)および「Use Explorer in the [Microsoft 365 Defender ポータル」を参照してください](threat-explorer.md)。</span><span class="sxs-lookup"><span data-stu-id="6bcc4-321">For more information, see [View reports for Defender for Office 365](view-reports-for-mdo.md) and [Use Explorer in the Microsoft 365 Defender portal](threat-explorer.md).</span></span>
