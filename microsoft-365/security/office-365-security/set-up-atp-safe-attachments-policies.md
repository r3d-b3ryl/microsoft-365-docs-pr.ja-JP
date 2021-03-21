---
title: Microsoft Defender で安全な添付ファイル ポリシーを設定する (Office 365)
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
description: 電子メール内の悪意のあるファイルから組織を保護するために安全な添付ファイル ポリシーを定義する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d48e373dc95aaa65d0f436f99208d926477aacd6
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918716"
---
# <a name="set-up-safe-attachments-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="89560-103">Microsoft Defender で安全な添付ファイル ポリシーを設定する (Office 365)</span><span class="sxs-lookup"><span data-stu-id="89560-103">Set up Safe Attachments policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="89560-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="89560-104">**Applies to**</span></span>
- [<span data-ttu-id="89560-105">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="89560-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="89560-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="89560-106">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

> [!IMPORTANT]
> <span data-ttu-id="89560-107">この記事は、[Microsoft Defender for Office 365](office-365-atp.md) をご利用の法人のお客様を対象としています。</span><span class="sxs-lookup"><span data-stu-id="89560-107">This article is intended for business customers who have [Microsoft Defender for Office 365](office-365-atp.md).</span></span> <span data-ttu-id="89560-108">Outlook で添付ファイルのスキャンに関する情報を探しているホーム ユーザーの場合は [、「Advanced Outlook.com セキュリティ」を参照してください](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)。</span><span class="sxs-lookup"><span data-stu-id="89560-108">If you're a home user looking for information about attachment scanning in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="89560-109">安全な添付ファイルは [、Microsoft Defender for Office 365](office-365-atp.md) の機能で、Exchange [Online Protection (EOP)](anti-malware-protection.md)でマルウェア対策保護によってスキャンされた後、受信者に配信する前に、仮想環境を使用して受信メール メッセージの添付ファイルを確認します。</span><span class="sxs-lookup"><span data-stu-id="89560-109">Safe Attachments is a feature in [Microsoft Defender for Office 365](office-365-atp.md) that uses a virtual environment to check attachments in inbound email messages after they've been scanned by [anti-malware protection in Exchange Online Protection (EOP)](anti-malware-protection.md), but before delivery to recipients.</span></span> <span data-ttu-id="89560-110">詳細については [、「Safe Attachments in Microsoft Defender for microsoft Defender for Office 365」を参照してください](atp-safe-attachments.md)。</span><span class="sxs-lookup"><span data-stu-id="89560-110">For more information, see [Safe Attachments in Microsoft Defender for Office 365](atp-safe-attachments.md).</span></span>

<span data-ttu-id="89560-111">組み込みまたは既定の安全な添付ファイル ポリシーはありません。</span><span class="sxs-lookup"><span data-stu-id="89560-111">There's no built-in or default Safe Attachments policy.</span></span> <span data-ttu-id="89560-112">電子メール メッセージの添付ファイルの安全な添付ファイルのスキャンを取得するには、この記事で説明するように、1 つ以上の安全な添付ファイル ポリシーを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="89560-112">To get Safe Attachments scanning of email message attachments, you need to create one or more Safe Attachments policies as described in this article.</span></span>

<span data-ttu-id="89560-113">安全な添付ファイル ポリシーは、セキュリティ & コンプライアンス センターまたは PowerShell (Exchange Online のメールボックスを持つ対象となる Microsoft 365 組織の Exchange Online PowerShell、Exchange Online メールボックスのない組織のスタンドアロン EOP PowerShell、ただし Defender for Office 365 アドオン サブスクリプション) で構成できます。</span><span class="sxs-lookup"><span data-stu-id="89560-113">You can configure Safe Attachments policies in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Defender for Office 365 add-on subscriptions).</span></span>

<span data-ttu-id="89560-114">安全な添付ファイル ポリシーの基本的な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="89560-114">The basic elements of a Safe Attachments policy are:</span></span>

- <span data-ttu-id="89560-115">**安全な** 添付ファイル ポリシー: 不明なマルウェア検出のアクション、マルウェアの添付ファイルを含むメッセージを指定した電子メール アドレスに送信するかどうか、および安全な添付ファイルのスキャンが完了できない場合にメッセージを配信するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="89560-115">**The safe attachment policy**: Specifies the actions for unknown malware detections, whether to send messages with malware attachments to a specified email address, and whether to deliver messages if Safe Attachments scanning can't complete.</span></span>
- <span data-ttu-id="89560-116">**安全な添付ファイルルール**: 優先度と受信者フィルター (ポリシーが適用されるユーザー) を指定します。</span><span class="sxs-lookup"><span data-stu-id="89560-116">**The safe attachment rule**: Specifies the priority and recipient filters (who the policy applies to).</span></span>

<span data-ttu-id="89560-117">セキュリティ コンプライアンス センターで安全な添付ファイルポリシーを管理する場合、これら 2 つの要素の違いは&ではありません。</span><span class="sxs-lookup"><span data-stu-id="89560-117">The difference between these two elements isn't obvious when you manage Safe Attachments polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="89560-118">安全な添付ファイル ポリシーを作成する場合、両方に同じ名前を使用して、実際に安全な添付ファイル ルールと関連付けられた安全な添付ファイル ポリシーを同時に作成します。</span><span class="sxs-lookup"><span data-stu-id="89560-118">When you create a Safe Attachments policy, you're actually creating a safe attachment rule and the associated safe attachment policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="89560-119">安全な添付ファイル ポリシーを変更すると、名前、優先度、有効または無効、および受信者フィルターに関連する設定によって、安全な添付ファイル ルールが変更されます。</span><span class="sxs-lookup"><span data-stu-id="89560-119">When you modify a Safe Attachments policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the safe attachment rule.</span></span> <span data-ttu-id="89560-120">その他の設定はすべて、関連付けられた安全な添付ファイル ポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="89560-120">All other settings modify the associated safe attachment policy.</span></span>
- <span data-ttu-id="89560-121">安全な添付ファイル ポリシーを削除すると、安全な添付ファイル ルールと関連付けられた安全な添付ファイル ポリシーが削除されます。</span><span class="sxs-lookup"><span data-stu-id="89560-121">When you remove a Safe Attachments policy, the safe attachment rule and the associated safe attachment policy are removed.</span></span>

<span data-ttu-id="89560-122">Exchange Online PowerShell またはスタンドアロン EOP PowerShell では、ポリシーとルールを個別に管理します。</span><span class="sxs-lookup"><span data-stu-id="89560-122">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="89560-123">詳細については、この記事の後半の [「Exchange Online PowerShell](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies) またはスタンドアロン EOP PowerShell を使用して安全な添付ファイル ポリシーを構成する」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="89560-123">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Attachments policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies) section later in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="89560-124">[安全な添付ファイル] 設定のグローバル設定領域で、安全な添付ファイル ポリシーに依存しない機能を構成します。</span><span class="sxs-lookup"><span data-stu-id="89560-124">In the global settings area of Safe Attachments settings, you configure features that are not dependent on Safe Attachments policies.</span></span> <span data-ttu-id="89560-125">手順については [、「SharePoint、OneDrive、Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md) の安全な添付ファイルを有効にする」および [「Microsoft 365 E5](safe-docs.md)の安全なドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89560-125">For instructions see [Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md) and [Safe Documents in Microsoft 365 E5](safe-docs.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="89560-126">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="89560-126">What do you need to know before you begin?</span></span>

- <span data-ttu-id="89560-127"><https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="89560-127">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="89560-128">[安全な添付ファイル] ページ **に直接移動するには** 、 を使用します <https://protection.office.com/safeattachmentv2> 。</span><span class="sxs-lookup"><span data-stu-id="89560-128">To go directly to the **Safe Attachments** page, use <https://protection.office.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="89560-129">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89560-129">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="89560-130">スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89560-130">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="89560-131">この記事の手順を実行するには、アクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="89560-131">You need to be assigned permissions before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="89560-132">安全な添付ファイル ポリシーを作成、変更、および削除するには、セキュリティ & コンプライアンス センターの組織の管理またはセキュリティ管理者の役割グループのメンバーであり、Exchange Onlineの組織の管理役割グループのメンバーである必要があります。  </span><span class="sxs-lookup"><span data-stu-id="89560-132">To create, modify, and delete Safe Attachments policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Security & Compliance Center **and** a member of the **Organization Management** role group in Exchange Online.</span></span>
  - <span data-ttu-id="89560-133">安全な添付ファイル ポリシーへの読み取り専用アクセスでは、セキュリティ コンプライアンスセンターのグローバルリーダーまたはセキュリティ リーダーの役割グループ&必要があります。</span><span class="sxs-lookup"><span data-stu-id="89560-133">For read-only access to Safe Attachments policies, you need to be a member of the **Global Reader** or **Security Reader** role groups in the Security & Compliance Center.</span></span>

  <span data-ttu-id="89560-134">詳細については、「セキュリティ コンプライアンス [センターのアクセス許可」と「exchange Online &アクセス](permissions-in-the-security-and-compliance-center.md) 許可 [」を参照してください](/exchange/permissions-exo/permissions-exo)。</span><span class="sxs-lookup"><span data-stu-id="89560-134">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) and [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="89560-135">**注**:</span><span class="sxs-lookup"><span data-stu-id="89560-135">**Notes**:</span></span>

  - <span data-ttu-id="89560-136">Microsoft 365 管理センターで、対応する Azure Active Directory の役割にユーザーを追加すると、ユーザーには、セキュリティ/コンプライアンス センター の必要なアクセス許可 _および_ Microsoft 365 のその他の機能に必要なアクセス許可が付与されます。</span><span class="sxs-lookup"><span data-stu-id="89560-136">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="89560-137">詳細については、「[管理者の役割について](../../admin/add-users/about-admin-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89560-137">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="89560-138">[Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) の **閲覧専用の組織管理** の役割グループが この機能への読み取り専用アクセス権も付与します。</span><span class="sxs-lookup"><span data-stu-id="89560-138">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="89560-139">安全な添付ファイル ポリシーの推奨設定については、「安全な添付ファイルの [設定」を参照してください](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings)。</span><span class="sxs-lookup"><span data-stu-id="89560-139">For our recommended settings for Safe Attachments policies, see [Safe Attachments settings](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings).</span></span>

- <span data-ttu-id="89560-140">新しいポリシーまたは更新されたポリシーを適用するには、最大 30 分かかります。</span><span class="sxs-lookup"><span data-stu-id="89560-140">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

## <a name="use-the-security--compliance-center-to-create-safe-attachments-policies"></a><span data-ttu-id="89560-141">セキュリティ コンプライアンス センター&使用して安全な添付ファイル ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="89560-141">Use the Security & Compliance Center to create Safe Attachments policies</span></span>

<span data-ttu-id="89560-142">セキュリティ & コンプライアンス センターでカスタムの安全な添付ファイル ポリシーを作成すると、両方に同じ名前を使用して、安全な添付ファイル ルールと関連付けられた安全な添付ファイル ポリシーが同時に作成されます。</span><span class="sxs-lookup"><span data-stu-id="89560-142">Creating a custom Safe Attachments policy in the Security & Compliance Center creates the safe attachment rule and the associated safe attachment policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="89560-143">セキュリティ コンプライアンス センター&、 **脅威管理ポリシー** ATP \> **の安全な添付** \> **ファイルに移動します**。</span><span class="sxs-lookup"><span data-stu-id="89560-143">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="89560-144">[安全な **添付ファイル] ページで** 、[作成] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="89560-144">On the **Safe Attachments** page, click **Create**.</span></span>

3. <span data-ttu-id="89560-145">[ **新しい安全な添付ファイル] ポリシー ウィザード** が開きます。</span><span class="sxs-lookup"><span data-stu-id="89560-145">The **New Safe Attachments policy** wizard opens.</span></span> <span data-ttu-id="89560-146">[ポリシーに **名前を付け] ページ** で、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="89560-146">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="89560-147">**[名前]**: わかりやすい一意のポリシー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="89560-147">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="89560-148">**[説明]**: ポリシーについての説明を入力します (オプション)。</span><span class="sxs-lookup"><span data-stu-id="89560-148">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="89560-149">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="89560-149">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="89560-150">表示される **[設定** ] ページで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="89560-150">On the **Settings** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="89560-151">**[安全な添付ファイル] 不明なマルウェアの応答**: 次のいずれかの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="89560-151">**Safe Attachments unknown malware response**: Select one of the following values:</span></span>

     - <span data-ttu-id="89560-152">**Off**: 通常、この値はお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="89560-152">**Off**: Typically, we don't recommend this value.</span></span>
     - <span data-ttu-id="89560-153">**モニター**</span><span class="sxs-lookup"><span data-stu-id="89560-153">**Monitor**</span></span>
     - <span data-ttu-id="89560-154">**ブロック**: これは既定値で、Standard および Strict の事前設定されたセキュリティ ポリシーで [推奨される値です](preset-security-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="89560-154">**Block**: This is the default value, and the recommended value in Standard and Strict [preset security policies](preset-security-policies.md).</span></span>
     - <span data-ttu-id="89560-155">**Replace**</span><span class="sxs-lookup"><span data-stu-id="89560-155">**Replace**</span></span>
     - <span data-ttu-id="89560-156">**動的配信 (プレビュー機能)**</span><span class="sxs-lookup"><span data-stu-id="89560-156">**Dynamic Delivery (Preview Feature)**</span></span>

     <span data-ttu-id="89560-157">これらの値については、「安全な添付ファイル [ポリシー設定」で説明します](atp-safe-attachments.md#safe-attachments-policy-settings)。</span><span class="sxs-lookup"><span data-stu-id="89560-157">These values are explained in [Safe Attachments policy settings](atp-safe-attachments.md#safe-attachments-policy-settings).</span></span>

   - <span data-ttu-id="89560-158">**添付ファイル** を次の電子メール アドレスに送信する:アクション値 [ブロック]、[監視]、または [置換] の場合は、[リダイレクトを有効にする] を選択して、指定した内部または外部の電子メール アドレスにマルウェアの添付ファイルを含むメッセージを送信して、分析と調査を行います。 </span><span class="sxs-lookup"><span data-stu-id="89560-158">**Send the attachment to the following email address**: For the action values **Block**, **Monitor**, or **Replace**, you can select **Enable redirect** to send messages that contain malware attachments to the specified internal or external email address for analysis and investigation.</span></span>

     <span data-ttu-id="89560-159">標準ポリシーと厳密なポリシー設定の推奨事項は、リダイレクトを有効にしてください。</span><span class="sxs-lookup"><span data-stu-id="89560-159">The recommendation for Standard and Strict policy settings is to enable redirection.</span></span> <span data-ttu-id="89560-160">詳細については、「安全な添付ファイル [の設定」を参照してください](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings)。</span><span class="sxs-lookup"><span data-stu-id="89560-160">For more information, see [Safe Attachments settings](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings).</span></span>

   - <span data-ttu-id="89560-161">**添付ファイルのマルウェア** スキャンが時間切れまたはエラーが発生した場合は、上記の選択を適用します。安全な添付ファイルのスキャンが完了できない場合でも、メッセージに対して安全な添付ファイルの不明なマルウェア応答で指定されたアクションが実行されます。</span><span class="sxs-lookup"><span data-stu-id="89560-161">**Apply the above selection if malware scanning for attachments times out or error occurs**: The action specified by **Safe Attachments unknown malware response** is taken on messages even when Safe Attachments scanning can't complete.</span></span> <span data-ttu-id="89560-162">このオプションを選択した場合は、常に [リダイレクトの有効化 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="89560-162">If you selected this option, always select **Enabled redirect**.</span></span> <span data-ttu-id="89560-163">それ以外の場合、メッセージが失われる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="89560-163">Otherwise, messages might be lost.</span></span>

   <span data-ttu-id="89560-164">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="89560-164">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="89560-165">表示される **[適用先]** ページで、ポリシーが適用される内部受信者を特定します。</span><span class="sxs-lookup"><span data-stu-id="89560-165">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="89560-166">各条件や例外は 1 回しか使用できませんが、条件や例外には複数の値を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="89560-166">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="89560-167">同じ条件や例外に複数の値がある場合、OR ロジック (たとえば、_\<recipient1\>_ または _\<recipient2\>_) が適用されます。</span><span class="sxs-lookup"><span data-stu-id="89560-167">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="89560-168">a別の条件や例外がある場合は AND ロジック (たとえば、_\<recipient1\>_ かつ _\<member of group 1\>_) が適用されます。</span><span class="sxs-lookup"><span data-stu-id="89560-168">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="89560-169">[条件 **の追加] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="89560-169">Click **Add a condition**.</span></span> <span data-ttu-id="89560-170">表示されるドロップダウンで、[適用する場合] で条件 **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="89560-170">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="89560-171">**受信者は:** 組織内の 1 つ以上のメールボックス、メール ユーザー、またはメール連絡先を指定します。</span><span class="sxs-lookup"><span data-stu-id="89560-171">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="89560-172">**受信者は: のメンバーです**。組織内の 1 つ以上のグループを指定します。</span><span class="sxs-lookup"><span data-stu-id="89560-172">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="89560-173">**[受信者のドメインが次の値である]**: 組織内で構成済みの 1 つ以上の承認済みドメイン内の受信者を指定します。</span><span class="sxs-lookup"><span data-stu-id="89560-173">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in your organization.</span></span>

   <span data-ttu-id="89560-174">条件を選択すると、対応するドロップダウンが [Any of **these] ボックスと一緒に表示** されます。</span><span class="sxs-lookup"><span data-stu-id="89560-174">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="89560-175">ボックス内をクリックし、値の一覧をスクロールして選択します。</span><span class="sxs-lookup"><span data-stu-id="89560-175">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="89560-176">ボックス内をクリックし、入力を開始してリストをフィルター処理し、値を選択します。</span><span class="sxs-lookup"><span data-stu-id="89560-176">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="89560-177">追加の値を追加するには、ボックス内の空の領域をクリックします。</span><span class="sxs-lookup"><span data-stu-id="89560-177">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="89560-178">個々のエントリを削除するには、値 **の [削除]** ![ ](../../media/scc-remove-icon.png) アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="89560-178">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="89560-179">条件全体を削除するには、条件 **の [削除]** ![ ](../../media/scc-remove-icon.png) アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="89560-179">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="89560-180">追加の条件を追加するには、[条件の追加] **をクリックし** 、[適用する場合] で残りの値 **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="89560-180">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="89560-181">例外を追加するには、[条件の追加] **をクリックし** 、[条件を除く] で例外 **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="89560-181">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="89560-182">設定と動作は、条件とまったく同じです。</span><span class="sxs-lookup"><span data-stu-id="89560-182">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="89560-183">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="89560-183">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="89560-184">表示される **[設定の確認]** ページで、設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="89560-184">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="89560-185">各設定で **[編集]** をクリックして変更できます。</span><span class="sxs-lookup"><span data-stu-id="89560-185">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="89560-186">完了したら、 **[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="89560-186">When you're finished, click **Finish**.</span></span>

## <a name="use-the-security--compliance-center-to-view-safe-attachments-policies"></a><span data-ttu-id="89560-187">セキュリティ コンプライアンス センターを&して、安全な添付ファイル ポリシーを表示する</span><span class="sxs-lookup"><span data-stu-id="89560-187">Use the Security & Compliance Center to view Safe Attachments policies</span></span>

1. <span data-ttu-id="89560-188">セキュリティ コンプライアンス センター&、 **脅威管理ポリシー** ATP \> **の安全な添付** \> **ファイルに移動します**。</span><span class="sxs-lookup"><span data-stu-id="89560-188">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="89560-189">[安全な **添付ファイル** ] ページで、一覧からポリシーを選択し、そのポリシーをクリックします (チェック ボックスをオンにしない)。</span><span class="sxs-lookup"><span data-stu-id="89560-189">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

   <span data-ttu-id="89560-190">ポリシーの詳細がフライアウトに表示される</span><span class="sxs-lookup"><span data-stu-id="89560-190">The policy details appear in a fly out</span></span>

## <a name="use-the-security--compliance-center-to-modify-safe-attachments-policies"></a><span data-ttu-id="89560-191">セキュリティ コンプライアンス センターを&安全な添付ファイル ポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="89560-191">Use the Security & Compliance Center to modify Safe Attachments policies</span></span>

1. <span data-ttu-id="89560-192">セキュリティ コンプライアンス センター&、 **脅威管理ポリシー** ATP \> **の安全な添付** \> **ファイルに移動します**。</span><span class="sxs-lookup"><span data-stu-id="89560-192">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="89560-193">[安全な **添付ファイル** ] ページで、一覧からポリシーを選択し、そのポリシーをクリックします (チェック ボックスをオンにしない)。</span><span class="sxs-lookup"><span data-stu-id="89560-193">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="89560-194">表示されるポリシーの詳細が表示されたら、[ポリシーの編集] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="89560-194">In the policy details fly out that appears, click **Edit policy**.</span></span>

<span data-ttu-id="89560-195">表示されるフライアウトで使用可能な設定は、「セキュリティ コンプライアンス センターを使用して安全な添付ファイル&作成する」セクション [で説明されている設定と同](#use-the-security--compliance-center-to-create-safe-attachments-policies) じです。</span><span class="sxs-lookup"><span data-stu-id="89560-195">The available settings in the fly out that appears are identical to those described in the [Use the Security & Compliance Center to create Safe Attachments policies](#use-the-security--compliance-center-to-create-safe-attachments-policies) section.</span></span>

<span data-ttu-id="89560-196">ポリシーを有効または無効にするか、ポリシーの優先順位を設定するには、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="89560-196">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-safe-attachments-policies"></a><span data-ttu-id="89560-197">安全な添付ファイル ポリシーを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="89560-197">Enable or disable Safe Attachments policies</span></span>

1. <span data-ttu-id="89560-198">セキュリティ コンプライアンス センター&、 **脅威管理ポリシー** ATP \> **の安全な添付** \> **ファイルに移動します**。</span><span class="sxs-lookup"><span data-stu-id="89560-198">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="89560-199">[状態] 列の値 **に注意** してください。</span><span class="sxs-lookup"><span data-stu-id="89560-199">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="89560-200">トグルを左に移動する</span><span class="sxs-lookup"><span data-stu-id="89560-200">Move the toggle to the left</span></span> ![ポリシーをオフにする](../../media/scc-toggle-off.png) <span data-ttu-id="89560-202">をクリックしてポリシーを無効にします。</span><span class="sxs-lookup"><span data-stu-id="89560-202">to disable the policy.</span></span>

   - <span data-ttu-id="89560-203">トグルを右に移動する</span><span class="sxs-lookup"><span data-stu-id="89560-203">Move the toggle to the right</span></span> ![ポリシーを有効にする](../../media/scc-toggle-on.png) <span data-ttu-id="89560-205">をクリックしてポリシーを有効にします。</span><span class="sxs-lookup"><span data-stu-id="89560-205">to enable the policy.</span></span>

### <a name="set-the-priority-of-safe-attachments-policies"></a><span data-ttu-id="89560-206">安全な添付ファイル ポリシーの優先度を設定する</span><span class="sxs-lookup"><span data-stu-id="89560-206">Set the priority of Safe Attachments policies</span></span>

<span data-ttu-id="89560-207">既定では、安全な添付ファイル ポリシーには、作成された順序に基づく優先度が与えられる (新しいポリシーは、古いポリシーよりも優先度が低くなります)。</span><span class="sxs-lookup"><span data-stu-id="89560-207">By default, Safe Attachments policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="89560-208">優先度番号が小さいほど、ポリシーの優先度が高くなる (0 が最優先) ことを意味し、ポリシーは優先順位に従って処理されます (優先度の高いポリシーは、優先度の低いポリシーよりも先に処理されます)。</span><span class="sxs-lookup"><span data-stu-id="89560-208">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="89560-209">2つのポリシーが同じ優先順位を持つことはできません。最初のポリシーが適用されると、ポリシーの処理は停止します。</span><span class="sxs-lookup"><span data-stu-id="89560-209">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="89560-210">優先順位と複数のポリシーを評価し適用する方法の詳細については、「[メール保護の優先順位](how-policies-and-protections-are-combined.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89560-210">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="89560-211">安全な添付ファイル ポリシーは、処理された順序で表示されます (最初のポリシーの **優先度** の値は 0 です)。</span><span class="sxs-lookup"><span data-stu-id="89560-211">Safe Attachments policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span>

<span data-ttu-id="89560-212">**注**: セキュリティ &コンプライアンス センターでは、安全な添付ファイル ポリシーを作成した後にのみ、優先度を変更できます。</span><span class="sxs-lookup"><span data-stu-id="89560-212">**Note**: In the Security & Compliance Center, you can only change the priority of the Safe Attachments policy after you create it.</span></span> <span data-ttu-id="89560-213">PowerShell では、安全な添付ファイル ルールを作成するときに既定の優先度を上書きできます (既存のルールの優先度に影響を与える可能性があります)。</span><span class="sxs-lookup"><span data-stu-id="89560-213">In PowerShell, you can override the default priority when you create the safe attachment rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="89560-214">ポリシーの優先度を変更するには、リスト内で上下に移動させます (セキュリティ/コンプライアンス センター内で直接、**優先順位** 番号を変更することはできません)。</span><span class="sxs-lookup"><span data-stu-id="89560-214">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="89560-215">セキュリティ コンプライアンス センター&、 **脅威管理ポリシー** ATP \> **の安全な添付** \> **ファイルに移動します**。</span><span class="sxs-lookup"><span data-stu-id="89560-215">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="89560-216">[安全な **添付ファイル** ] ページで、一覧からポリシーを選択し、そのポリシーをクリックします (チェック ボックスをオンにしない)。</span><span class="sxs-lookup"><span data-stu-id="89560-216">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="89560-217">表示されるポリシーの詳細が表示されたら、使用可能な優先度ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="89560-217">In the policy details fly out that appears, click the available priority button.</span></span>

   - <span data-ttu-id="89560-218">優先度の値が **0** の **安全な添付** ファイル ポリシーには、[優先度の下がり]**ボタンしか** 使用できません。</span><span class="sxs-lookup"><span data-stu-id="89560-218">The Safe Attachments policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="89560-219">優先度の値が最も低い安全な添付ファイル **ポリシー** ( **たとえば、3)** には、[優先度の引き上げ] **ボタンのみを** 使用できます。</span><span class="sxs-lookup"><span data-stu-id="89560-219">The Safe Attachments policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="89560-220">3 つ以上の安全な添付ファイル ポリシーがある場合、優先度の高い値と最も低い優先度の値の間のポリシーには、[優先度の引き上げ] ボタンと [優先度の下げ] ボタンの **両方があります。**</span><span class="sxs-lookup"><span data-stu-id="89560-220">If you have three or more Safe Attachments policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="89560-221">[優先度 **の増加] または** **[優先度の下げ** ] をクリックして、 **優先度の値を変更** します。</span><span class="sxs-lookup"><span data-stu-id="89560-221">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="89560-222">完了したら、**[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="89560-222">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-safe-attachments-policies"></a><span data-ttu-id="89560-223">セキュリティ コンプライアンス センター&使用して安全な添付ファイル ポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="89560-223">Use the Security & Compliance Center to remove Safe Attachments policies</span></span>

1. <span data-ttu-id="89560-224">セキュリティ コンプライアンス センター&、 **脅威管理ポリシー** ATP \> **の安全な添付** \> **ファイルに移動します**。</span><span class="sxs-lookup"><span data-stu-id="89560-224">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="89560-225">[安全な **添付ファイル** ] ページで、一覧からポリシーを選択し、そのポリシーをクリックします (チェック ボックスをオンにしない)。</span><span class="sxs-lookup"><span data-stu-id="89560-225">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="89560-226">表示されるポリシーの詳細が表示されたら、[ポリシーの削除] をクリックし、表示される警告ダイアログで **[は** い] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="89560-226">In the policy details fly out that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies"></a><span data-ttu-id="89560-227">Exchange Online PowerShell またはスタンドアロン EOP PowerShell を使用して安全な添付ファイル ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="89560-227">Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Attachments policies</span></span>

<span data-ttu-id="89560-228">前述したように、安全な添付ファイル ポリシーは、安全な添付ファイル ポリシーと安全な添付ファイル ルールで構成されます。</span><span class="sxs-lookup"><span data-stu-id="89560-228">As previously described, a Safe Attachments policy consists of a safe attachment policy and a safe attachment rule.</span></span>

<span data-ttu-id="89560-229">PowerShell では、安全な添付ファイル ポリシーと安全な添付ファイルルールの違いが明らかです。</span><span class="sxs-lookup"><span data-stu-id="89560-229">In PowerShell, the difference between safe attachment policies and safe attachment rules is apparent.</span></span> <span data-ttu-id="89560-230">**\* -SafeAttachmentPolicy** コマンドレットを使用して安全な添付ファイル ポリシーを管理し **\* 、-SafeAttachmentRule** コマンドレットを使用して安全な添付ファイル ルールを管理します。</span><span class="sxs-lookup"><span data-stu-id="89560-230">You manage safe attachment policies by using the **\*-SafeAttachmentPolicy** cmdlets, and you manage safe attachment rules by using the **\*-SafeAttachmentRule** cmdlets.</span></span>

- <span data-ttu-id="89560-231">PowerShell では、最初に安全な添付ファイル ポリシーを作成してから、ルールが適用されるポリシーを識別する安全な添付ファイル ルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="89560-231">In PowerShell, you create the safe attachment policy first, then you create the safe attachment rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="89560-232">PowerShell では、安全な添付ファイル ポリシーと安全な添付ファイルルールの設定を個別に変更します。</span><span class="sxs-lookup"><span data-stu-id="89560-232">In PowerShell, you modify the settings in the safe attachment policy and the safe attachment rule separately.</span></span>
- <span data-ttu-id="89560-233">PowerShell から安全な添付ファイル ポリシーを削除しても、対応する安全な添付ファイル ルールは自動的には削除されません。その逆も同様です。</span><span class="sxs-lookup"><span data-stu-id="89560-233">When you remove a safe attachment policy from PowerShell, the corresponding safe attachment rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-safe-attachments-policies"></a><span data-ttu-id="89560-234">PowerShell を使用して安全な添付ファイル ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="89560-234">Use PowerShell to create Safe Attachments policies</span></span>

<span data-ttu-id="89560-235">PowerShell で安全な添付ファイル ポリシーを作成するには、次の 2 つの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="89560-235">Creating a Safe Attachments policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="89560-236">安全な添付ファイル ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="89560-236">Create the safe attachment policy.</span></span>
2. <span data-ttu-id="89560-237">ルールが適用される安全な添付ファイル ポリシーを指定する安全な添付ファイル ルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="89560-237">Create the safe attachment rule that specifies the safe attachment policy that the rule applies to.</span></span>

 <span data-ttu-id="89560-238">**注**:</span><span class="sxs-lookup"><span data-stu-id="89560-238">**Notes**:</span></span>

- <span data-ttu-id="89560-239">新しい安全な添付ファイル ルールを作成し、関連付けされていない既存の安全な添付ファイル ポリシーを割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="89560-239">You can create a new safe attachment rule and assign an existing, unassociated safe attachment policy to it.</span></span> <span data-ttu-id="89560-240">安全な添付ファイル ルールを複数の安全な添付ファイル ポリシーに関連付けできない。</span><span class="sxs-lookup"><span data-stu-id="89560-240">A safe attachment rule can't be associated with more than one safe attachment policy.</span></span>

- <span data-ttu-id="89560-241">ポリシーを作成するまで、セキュリティ & コンプライアンス センターで使用できない PowerShell の新しい安全な添付ファイル ポリシーに対して、次の設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="89560-241">You can configure the following settings on new safe attachment policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>
  - <span data-ttu-id="89560-242">新しいポリシーを無効として作成 _します_ `$false` **(New-SafeAttachmentRule コマンドレットで有効** )。</span><span class="sxs-lookup"><span data-stu-id="89560-242">Create the new policy as disabled (_Enabled_ `$false` on the **New-SafeAttachmentRule** cmdlet).</span></span>
  - <span data-ttu-id="89560-243"> _\<Number\>_ **New-SafeAttachmentRule** コマンドレットの作成時にポリシーの優先度 (優先度) を設定します。</span><span class="sxs-lookup"><span data-stu-id="89560-243">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-SafeAttachmentRule** cmdlet).</span></span>

- <span data-ttu-id="89560-244">PowerShell で作成した新しい安全な添付ファイル ポリシーは、ポリシーを安全な添付ファイル ルールに割り当てるまで、セキュリティ & コンプライアンス センターには表示されません。</span><span class="sxs-lookup"><span data-stu-id="89560-244">A new safe attachment policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a safe attachment rule.</span></span>

#### <a name="step-1-use-powershell-to-create-a-safe-attachment-policy"></a><span data-ttu-id="89560-245">手順 1: PowerShell を使用して安全な添付ファイル ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="89560-245">Step 1: Use PowerShell to create a safe attachment policy</span></span>

<span data-ttu-id="89560-246">安全な添付ファイル ポリシーを作成するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="89560-246">To create a safe attachment policy, use this syntax:</span></span>

```PowerShell
New-SafeAttachmentPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-Action <Allow | Block | Replace | DynamicDelivery>] [-Redirect <$true | $false>] [-RedirectAddress <SMTPEmailAddress>] [-ActionOnError <$true | $false>]
```

<span data-ttu-id="89560-247">この例では、Contoso All という名前の安全な添付ファイル ポリシーを次の値で作成します。</span><span class="sxs-lookup"><span data-stu-id="89560-247">This example creates a safe attachment policy named Contoso All with the following values:</span></span>

- <span data-ttu-id="89560-248">セーフ ドキュメント スキャンによってマルウェアが含まれていると見つかったメッセージをブロックします _(Action_ パラメーターは使用していないので、既定値はです `Block` )。</span><span class="sxs-lookup"><span data-stu-id="89560-248">Block messages that are found to contain malware by Safe Documents scanning (we aren't using the _Action_ parameter, and the default value is `Block`).</span></span>
- <span data-ttu-id="89560-249">リダイレクトが有効になっていると、マルウェアが含まれていると検出されたメッセージは、分析と調査のために sec-ops@contoso.com に送信されます。</span><span class="sxs-lookup"><span data-stu-id="89560-249">Redirection is enabled, and messages that are found to contain malware are sent to sec-ops@contoso.com for analysis and investigation.</span></span>
- <span data-ttu-id="89560-250">安全な添付ファイルのスキャンが使用できない場合、またはエラーが発生した場合は、メッセージを配信しません _(ActionOnError_ パラメーターは使用していないので、既定値はです `$true` )。</span><span class="sxs-lookup"><span data-stu-id="89560-250">If Safe Attachments scanning isn't available or encounters errors, don't deliver the message (we aren't using the _ActionOnError_ parameter, and the default value is `$true`).</span></span>

```PowerShell
New-SafeAttachmentPolicy -Name "Contoso All" -Redirect $true -RedirectAddress sec-ops@contoso.com
```

<span data-ttu-id="89560-251">構文とパラメーターの詳細については [、「New-SafeAttachmentPolicy」を参照してください](/powershell/module/exchange/new-safeattachmentpolicy)。</span><span class="sxs-lookup"><span data-stu-id="89560-251">For detailed syntax and parameter information, see [New-SafeAttachmentPolicy](/powershell/module/exchange/new-safeattachmentpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-a-safe-attachment-rule"></a><span data-ttu-id="89560-252">手順 2: PowerShell を使用して安全な添付ファイル ルールを作成する</span><span class="sxs-lookup"><span data-stu-id="89560-252">Step 2: Use PowerShell to create a safe attachment rule</span></span>

<span data-ttu-id="89560-253">安全な添付ファイル ルールを作成するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="89560-253">To create a safe attachment rule, use this syntax:</span></span>

```PowerShell
New-SafeAttachmentRule -Name "<RuleName>" -SafeAttachmentPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

<span data-ttu-id="89560-254">この例では、Contoso All という名前の安全な添付ファイル ルールを次の条件で作成します。</span><span class="sxs-lookup"><span data-stu-id="89560-254">This example creates a safe attachment rule named Contoso All with the following conditions:</span></span>

- <span data-ttu-id="89560-255">このルールは、Contoso All という名前の安全な添付ファイル ポリシーに関連付けられている。</span><span class="sxs-lookup"><span data-stu-id="89560-255">The rule is associated with the safe attachment policy named Contoso All.</span></span>
- <span data-ttu-id="89560-256">ルールは、ドメイン内のすべての受信者に contoso.com されます。</span><span class="sxs-lookup"><span data-stu-id="89560-256">The rule applies to all recipients in the contoso.com domain.</span></span>
- <span data-ttu-id="89560-257">Priority パラメーターを使用していないので _、既定_ の優先度が使用されます。</span><span class="sxs-lookup"><span data-stu-id="89560-257">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>
- <span data-ttu-id="89560-258">ルールが有効になっています (Enabled パラメーターは使用しませんが、既定値はです `$true` )。</span><span class="sxs-lookup"><span data-stu-id="89560-258">The rule is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>

```powershell
New-SafeAttachmentRule -Name "Contoso All" -SafeAttachmentPolicy "Contoso All" -RecipientDomainIs contoso.com
```

<span data-ttu-id="89560-259">構文とパラメーターの詳細については [、「New-SafeAttachmentRule」を参照してください](/powershell/module/exchange/new-safeattachmentrule)。</span><span class="sxs-lookup"><span data-stu-id="89560-259">For detailed syntax and parameter information, see [New-SafeAttachmentRule](/powershell/module/exchange/new-safeattachmentrule).</span></span>

### <a name="use-powershell-to-view-safe-attachment-policies"></a><span data-ttu-id="89560-260">PowerShell を使用して安全な添付ファイル ポリシーを表示する</span><span class="sxs-lookup"><span data-stu-id="89560-260">Use PowerShell to view safe attachment policies</span></span>

<span data-ttu-id="89560-261">既存の安全な添付ファイル ポリシーを表示するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="89560-261">To view existing safe attachment policies, use the following syntax:</span></span>

```PowerShell
Get-SafeAttachmentPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="89560-262">この例では、すべての安全な添付ファイル ポリシーの概要一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="89560-262">This example returns a summary list of all safe attachment policies.</span></span>

```PowerShell
Get-SafeAttachmentPolicy
```

<span data-ttu-id="89560-263">この例では、Contoso Executives という名前の安全な添付ファイル ポリシーの詳細情報を返します。</span><span class="sxs-lookup"><span data-stu-id="89560-263">This example returns detailed information for the safe attachment policy named Contoso Executives.</span></span>

```PowerShell
Get-SafeAttachmentPolicy -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="89560-264">構文とパラメーターの詳細については [、「Get-SafeAttachmentPolicy」を参照してください](/powershell/module/exchange/get-safeattachmentpolicy)。</span><span class="sxs-lookup"><span data-stu-id="89560-264">For detailed syntax and parameter information, see [Get-SafeAttachmentPolicy](/powershell/module/exchange/get-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-view-safe-attachment-rules"></a><span data-ttu-id="89560-265">PowerShell を使用して安全な添付ファイル ルールを表示する</span><span class="sxs-lookup"><span data-stu-id="89560-265">Use PowerShell to view safe attachment rules</span></span>

<span data-ttu-id="89560-266">既存の安全な添付ファイル ルールを表示するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="89560-266">To view existing safe attachment rules, use the following syntax:</span></span>

```PowerShell
Get-SafeAttachmentRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="89560-267">次の使用例は、すべての安全な添付ファイル ルールの概要リストを返します。</span><span class="sxs-lookup"><span data-stu-id="89560-267">This example returns a summary list of all safe attachment rules.</span></span>

```PowerShell
Get-SafeAttachmentRule
```

<span data-ttu-id="89560-268">ルールを有効または無効にしてリストをフィルター処理するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="89560-268">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-SafeAttachmentRule -State Disabled
```

```PowerShell
Get-SafeAttachmentRule -State Enabled
```

<span data-ttu-id="89560-269">この例では、Contoso Executives という名前の安全な添付ファイル ルールの詳細情報を返します。</span><span class="sxs-lookup"><span data-stu-id="89560-269">This example returns detailed information for the safe attachment rule named Contoso Executives.</span></span>

```PowerShell
Get-SafeAttachmentRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="89560-270">構文とパラメーターの詳細については [、「Get-SafeAttachmentRule」を参照してください](/powershell/module/exchange/get-safeattachmentrule)。</span><span class="sxs-lookup"><span data-stu-id="89560-270">For detailed syntax and parameter information, see [Get-SafeAttachmentRule](/powershell/module/exchange/get-safeattachmentrule).</span></span>

### <a name="use-powershell-to-modify-safe-attachment-policies"></a><span data-ttu-id="89560-271">PowerShell を使用して安全な添付ファイル ポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="89560-271">Use PowerShell to modify safe attachment policies</span></span>

<span data-ttu-id="89560-272">PowerShell で安全な添付ファイル ポリシーの名前を変更することはできません **(Set-SafeAttachmentPolicy** コマンドレットには _Name_ パラメーターはありません)。</span><span class="sxs-lookup"><span data-stu-id="89560-272">You can't rename a safe attachment policy in PowerShell (the **Set-SafeAttachmentPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="89560-273">セキュリティ コンプライアンス センターで安全な添付ファイル ポリシー&変更する場合は、安全な添付ファイル ルールの名前を変更 _する必要があります_。</span><span class="sxs-lookup"><span data-stu-id="89560-273">When you rename a Safe Attachments policy in the Security & Compliance Center, you're only renaming the safe attachment _rule_.</span></span>

<span data-ttu-id="89560-274">それ以外の場合は、この記事の「手順 [1: PowerShell](#step-1-use-powershell-to-create-a-safe-attachment-policy) を使用して安全な添付ファイル ポリシーを作成する」セクションで説明したように、安全な添付ファイル ポリシーを作成するときに同じ設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="89560-274">Otherwise, the same settings are available when you create a safe attachment policy as described in the [Step 1: Use PowerShell to create a safe attachment policy](#step-1-use-powershell-to-create-a-safe-attachment-policy) section earlier in this article.</span></span>

<span data-ttu-id="89560-275">安全な添付ファイル ポリシーを変更するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="89560-275">To modify a safe attachment policy, use this syntax:</span></span>

```PowerShell
Set-SafeAttachmentPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="89560-276">構文とパラメーターの詳細については [、「Set-SafeAttachmentPolicy」を参照してください](/powershell/module/exchange/set-safeattachmentpolicy)。</span><span class="sxs-lookup"><span data-stu-id="89560-276">For detailed syntax and parameter information, see [Set-SafeAttachmentPolicy](/powershell/module/exchange/set-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-modify-safe-attachment-rules"></a><span data-ttu-id="89560-277">PowerShell を使用して安全な添付ファイル ルールを変更する</span><span class="sxs-lookup"><span data-stu-id="89560-277">Use PowerShell to modify safe attachment rules</span></span>

<span data-ttu-id="89560-278">PowerShell で安全な添付ファイル ルールを変更するときに使用できない唯一の設定は、無効なルールを作成できる _Enabled_ パラメーターです。</span><span class="sxs-lookup"><span data-stu-id="89560-278">The only setting that's not available when you modify a safe attachment rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="89560-279">既存の安全な添付ファイル ルールを有効または無効にするには、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="89560-279">To enable or disable existing safe attachment rules, see the next section.</span></span>

<span data-ttu-id="89560-280">それ以外の場合は、「手順 [2: PowerShell](#step-2-use-powershell-to-create-a-safe-attachment-rule) を使用して安全な添付ファイルルールを作成する」セクションで説明したように、ルールを作成するときに同じ設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="89560-280">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create a safe attachment rule](#step-2-use-powershell-to-create-a-safe-attachment-rule) section earlier in this article.</span></span>

<span data-ttu-id="89560-281">安全な添付ファイル ルールを変更するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="89560-281">To modify a safe attachment rule, use this syntax:</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="89560-282">構文とパラメーターの詳細については [、「Set-SafeAttachmentRule」を参照してください](/powershell/module/exchange/set-safeattachmentrule)。</span><span class="sxs-lookup"><span data-stu-id="89560-282">For detailed syntax and parameter information, see [Set-SafeAttachmentRule](/powershell/module/exchange/set-safeattachmentrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-safe-attachment-rules"></a><span data-ttu-id="89560-283">PowerShell を使用して安全な添付ファイル ルールを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="89560-283">Use PowerShell to enable or disable safe attachment rules</span></span>

<span data-ttu-id="89560-284">PowerShell で安全な添付ファイル ルールを有効または無効にすると、安全な添付ファイル ポリシー (安全な添付ファイル ルールと割り当てられた安全な添付ファイル ポリシー) 全体が有効または無効となります。</span><span class="sxs-lookup"><span data-stu-id="89560-284">Enabling or disabling a safe attachment rule in PowerShell enables or disables the whole Safe Attachments policy (the safe attachment rule and the assigned safe attachment policy).</span></span>

<span data-ttu-id="89560-285">PowerShell で安全な添付ファイル ルールを有効または無効にするには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="89560-285">To enable or disable a safe attachment rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-SafeAttachmentRule | Disable-SafeAttachmentRule> -Identity "<RuleName>"
```

<span data-ttu-id="89560-286">この例では、Marketing Department という名前の安全な添付ファイル ルールを無効にします。</span><span class="sxs-lookup"><span data-stu-id="89560-286">This example disables the safe attachment rule named Marketing Department.</span></span>

```PowerShell
Disable-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="89560-287">この例では、同じルールを有効化します。</span><span class="sxs-lookup"><span data-stu-id="89560-287">This example enables same rule.</span></span>

```PowerShell
Enable-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="89560-288">構文とパラメーターの詳細については [、「Enable-SafeAttachmentRule」](/powershell/module/exchange/enable-safeattachmentrule) および [「Disable-SafeAttachmentRule」を参照してください](/powershell/module/exchange/disable-safeattachmentrule)。</span><span class="sxs-lookup"><span data-stu-id="89560-288">For detailed syntax and parameter information, see [Enable-SafeAttachmentRule](/powershell/module/exchange/enable-safeattachmentrule) and [Disable-SafeAttachmentRule](/powershell/module/exchange/disable-safeattachmentrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-safe-attachment-rules"></a><span data-ttu-id="89560-289">PowerShell を使用して安全な添付ファイル ルールの優先度を設定する</span><span class="sxs-lookup"><span data-stu-id="89560-289">Use PowerShell to set the priority of safe attachment rules</span></span>

<span data-ttu-id="89560-290">ルールに設定できる優先度の最高値値は 0 です。</span><span class="sxs-lookup"><span data-stu-id="89560-290">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="89560-291">設定できる最低値はルールの数に依存します。</span><span class="sxs-lookup"><span data-stu-id="89560-291">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="89560-292">たとえば、ルールが五つある場合、使用できる優先度の値は 0 から 4 です。</span><span class="sxs-lookup"><span data-stu-id="89560-292">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="89560-293">既存の一つのルールの優先度を変更すると、他のルールにも連鎖的な影響が起こりえます。</span><span class="sxs-lookup"><span data-stu-id="89560-293">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="89560-294">たとえば、カスタム ルールが 5 つあって (優先度 0 から 4)、1 つのルールの優先度を 2 に変更した場合には、既存の優先度 2 のルールは優先度 3 に変更され、優先度 3 は優先度 4 に変更されます。</span><span class="sxs-lookup"><span data-stu-id="89560-294">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="89560-295">PowerShell で安全な添付ファイル ルールの優先度を設定するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="89560-295">To set the priority of a safe attachment rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="89560-p124">この例では、Marketing Department というルールの優先度を 2 に設定しています。優先度が 2 以下のすべての既存のルールは、優先度が 1 ずつ下がります (優先度番号が 1 ずつ増加します)。</span><span class="sxs-lookup"><span data-stu-id="89560-p124">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="89560-298">**注**: 新しいルールを作成するときに優先度を設定するには **、New-SafeAttachmentRule** コマンドレットの Priority パラメーターを使用します。 </span><span class="sxs-lookup"><span data-stu-id="89560-298">**Note**: To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-SafeAttachmentRule** cmdlet instead.</span></span>

<span data-ttu-id="89560-299">構文とパラメーターの詳細については [、「Set-SafeAttachmentRule」を参照してください](/powershell/module/exchange/set-safeattachmentrule)。</span><span class="sxs-lookup"><span data-stu-id="89560-299">For detailed syntax and parameter information, see [Set-SafeAttachmentRule](/powershell/module/exchange/set-safeattachmentrule).</span></span>

### <a name="use-powershell-to-remove-safe-attachment-policies"></a><span data-ttu-id="89560-300">PowerShell を使用して安全な添付ファイル ポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="89560-300">Use PowerShell to remove safe attachment policies</span></span>

<span data-ttu-id="89560-301">PowerShell を使用して安全な添付ファイル ポリシーを削除しても、対応する安全な添付ファイル ルールは削除されません。</span><span class="sxs-lookup"><span data-stu-id="89560-301">When you use PowerShell to remove a safe attachment policy, the corresponding safe attachment rule isn't removed.</span></span>

<span data-ttu-id="89560-302">PowerShell で安全な添付ファイル ポリシーを削除するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="89560-302">To remove a safe attachment policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeAttachmentPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="89560-303">この例では、Marketing Department という名前の安全な添付ファイル ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="89560-303">This example removes the safe attachment policy named Marketing Department.</span></span>

```PowerShell
Remove-SafeAttachmentPolicy -Identity "Marketing Department"
```

<span data-ttu-id="89560-304">構文とパラメーターの詳細については [、「Remove-SafeAttachmentPolicy」を参照してください](/powershell/module/exchange/remove-safeattachmentpolicy)。</span><span class="sxs-lookup"><span data-stu-id="89560-304">For detailed syntax and parameter information, see [Remove-SafeAttachmentPolicy](/powershell/module/exchange/remove-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-remove-safe-attachment-rules"></a><span data-ttu-id="89560-305">PowerShell を使用して安全な添付ファイル ルールを削除する</span><span class="sxs-lookup"><span data-stu-id="89560-305">Use PowerShell to remove safe attachment rules</span></span>

<span data-ttu-id="89560-306">PowerShell を使用して安全な添付ファイル ルールを削除しても、対応する安全な添付ファイル ポリシーは削除されません。</span><span class="sxs-lookup"><span data-stu-id="89560-306">When you use PowerShell to remove a safe attachment rule, the corresponding safe attachment policy isn't removed.</span></span>

<span data-ttu-id="89560-307">PowerShell で安全な添付ファイル ルールを削除するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="89560-307">To remove a safe attachment rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeAttachmentRule -Identity "<PolicyName>"
```

<span data-ttu-id="89560-308">この例では、Marketing Department という名前の安全な添付ファイル ルールを削除します。</span><span class="sxs-lookup"><span data-stu-id="89560-308">This example removes the safe attachment rule named Marketing Department.</span></span>

```PowerShell
Remove-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="89560-309">構文とパラメーターの詳細については [、「Remove-SafeAttachmentRule」を参照してください](/powershell/module/exchange/remove-safeattachmentrule)。</span><span class="sxs-lookup"><span data-stu-id="89560-309">For detailed syntax and parameter information, see [Remove-SafeAttachmentRule](/powershell/module/exchange/remove-safeattachmentrule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="89560-310">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="89560-310">How do you know these procedures worked?</span></span>

<span data-ttu-id="89560-311">安全な添付ファイル ポリシーが正常に作成、変更、または削除されたことを確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="89560-311">To verify that you've successfully created, modified, or removed Safe Attachments policies, do any of the following steps:</span></span>

- <span data-ttu-id="89560-312">セキュリティ コンプライアンス センター&、 **脅威管理ポリシー** ATP \> **の安全な添付** \> **ファイルに移動します**。</span><span class="sxs-lookup"><span data-stu-id="89560-312">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span> <span data-ttu-id="89560-313">ポリシー、その状態の値、および **優先度** の値の一覧を **確認** します。</span><span class="sxs-lookup"><span data-stu-id="89560-313">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="89560-314">詳細を表示するには、一覧からポリシーを選択し、詳細をフライアウトで表示します。</span><span class="sxs-lookup"><span data-stu-id="89560-314">To view more details, select the policy from the list, and view the details in the fly out.</span></span>

- <span data-ttu-id="89560-315">Exchange Online PowerShell または Exchange Online Protection PowerShell で、ポリシーまたはルールの名前に置き換え、次のコマンドを実行し、 \<Name\> 設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="89560-315">In Exchange Online PowerShell or Exchange Online Protection PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-SafeAttachmentPolicy -Identity "<Name>" | Format-List
  ```

  ```PowerShell
  Get-SafeAttachmentRule -Identity "<Name>" | Format-List
  ```

<span data-ttu-id="89560-316">安全な添付ファイルがメッセージをスキャンしているのを確認するには、365 レポートで使用可能な Defender Office確認します。</span><span class="sxs-lookup"><span data-stu-id="89560-316">To verify that Safe Attachments is scanning messages, check the available Defender for Office 365 reports.</span></span> <span data-ttu-id="89560-317">詳細については、「View [reports for Defender for Office 365」](view-reports-for-atp.md) および「Use Explorer in the Security & [コンプライアンス センター」を参照してください](threat-explorer.md)。</span><span class="sxs-lookup"><span data-stu-id="89560-317">For more information, see [View reports for Defender for Office 365](view-reports-for-atp.md) and [Use Explorer in the Security & Compliance Center](threat-explorer.md).</span></span>