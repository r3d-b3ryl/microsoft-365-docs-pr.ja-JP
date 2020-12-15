---
title: Microsoft Defender で安全な添付ファイル ポリシーを Office 365 用にセットアップする
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 078eb946-819a-4e13-8673-fe0c0ad3a775
ms.collection:
- M365-security-compliance
description: 安全な添付ファイル ポリシーを定義して、電子メール内の悪意のあるファイルから組織を保護する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9105e7ed9e9bc376b3d86cd846d8c1d6eae8deea
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/15/2020
ms.locfileid: "49682915"
---
# <a name="set-up-safe-attachments-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="b7c7a-103">Microsoft Defender で安全な添付ファイル ポリシーを Office 365 用にセットアップする</span><span class="sxs-lookup"><span data-stu-id="b7c7a-103">Set up Safe Attachments policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> <span data-ttu-id="b7c7a-104">この記事は、[Microsoft Defender for Office 365](office-365-atp.md) をご利用の法人のお客様を対象としています。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-104">This article is intended for business customers who have [Microsoft Defender for Office 365](office-365-atp.md).</span></span> <span data-ttu-id="b7c7a-105">If you're a home user looking about attachment scanning in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span><span class="sxs-lookup"><span data-stu-id="b7c7a-105">If you're a home user looking for information about attachment scanning in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="b7c7a-106">「安全な添付ファイル」は、Exchange [Online Protection (EOP)](anti-malware-protection.md)のマルウェア対策保護によってスキャンされた後、受信者に配信する前に、仮想環境を使用して受信メール メッセージの添付ファイルを確認する[、Microsoft Defender for Office 365](office-365-atp.md)の機能です。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-106">Safe Attachments is a feature in [Microsoft Defender for Office 365](office-365-atp.md) that uses a virtual environment to check attachments in inbound email messages after they've been scanned by [anti-malware protection in Exchange Online Protection (EOP)](anti-malware-protection.md), but before delivery to recipients.</span></span> <span data-ttu-id="b7c7a-107">詳細については [、「Microsoft Defender の安全な添付ファイル」で Office 365](atp-safe-attachments.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-107">For more information, see [Safe Attachments in Microsoft Defender for Office 365](atp-safe-attachments.md).</span></span>

<span data-ttu-id="b7c7a-108">組み込みまたは既定の安全な添付ファイル ポリシーはありません。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-108">There's no built-in or default Safe Attachments policy.</span></span> <span data-ttu-id="b7c7a-109">電子メール メッセージの添付ファイルの安全な添付ファイル のスキャンを取得するには、この記事で説明するように、1 つ以上の安全な添付ファイル ポリシーを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-109">To get Safe Attachments scanning of email message attachments, you need to create one or more Safe Attachments policies as described in this article.</span></span>

<span data-ttu-id="b7c7a-110">安全な添付ファイル ポリシーは、セキュリティ & コンプライアンス センターまたは PowerShell で構成できます (Exchange Online のメールボックスを持つ対象の Microsoft 365 組織の場合は Exchange Online PowerShell、Exchange Online メールボックスのない組織の場合はスタンドアロンの EOP PowerShell、Defender for Office 365 アドオン サブスクリプションの場合)。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-110">You can configure Safe Attachments policies in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Defender for Office 365 add-on subscriptions).</span></span>

<span data-ttu-id="b7c7a-111">安全な添付ファイル ポリシーの基本的な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-111">The basic elements of a Safe Attachments policy are:</span></span>

- <span data-ttu-id="b7c7a-112">**安全** な添付ファイル ポリシー: 不明なマルウェア検出のアクション、マルウェアの添付ファイルを含むメッセージを指定された電子メール アドレスに送信するかどうか、および安全な添付ファイルのスキャンが完了できない場合にメッセージを配信するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-112">**The safe attachment policy**: Specifies the actions for unknown malware detections, whether to send messages with malware attachments to a specified email address, and whether to deliver messages if Safe Attachments scanning can't complete.</span></span>
- <span data-ttu-id="b7c7a-113">**安全な添付ファイルルール**: 優先度と受信者フィルター (ポリシーが適用されるユーザー) を指定します。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-113">**The safe attachment rule**: Specifies the priority and recipient filters (who the policy applies to).</span></span>

<span data-ttu-id="b7c7a-114">セキュリティ/コンプライアンス センターで安全な添付ファイル ポリシーを管理する場合、これら 2 つの要素の違い&明らかではありません。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-114">The difference between these two elements isn't obvious when you manage Safe Attachments polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="b7c7a-115">安全な添付ファイル ポリシーを作成する場合、実際には両方に同じ名前を使用して、安全な添付ファイル ルールと関連付けられた安全な添付ファイル ポリシーを同時に作成します。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-115">When you create a Safe Attachments policy, you're actually creating a safe attachment rule and the associated safe attachment policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="b7c7a-116">安全な添付ファイル ポリシーを変更すると、名前、優先度、有効または無効、および受信者フィルターに関連する設定によって、安全な添付ファイル ルールが変更されます。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-116">When you modify a Safe Attachments policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the safe attachment rule.</span></span> <span data-ttu-id="b7c7a-117">その他のすべての設定では、関連付けられている安全な添付ファイル ポリシーが変更されます。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-117">All other settings modify the associated safe attachment policy.</span></span>
- <span data-ttu-id="b7c7a-118">安全な添付ファイル ポリシーを削除すると、安全な添付ファイル ルールと関連付けられている安全な添付ファイル ポリシーが削除されます。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-118">When you remove a Safe Attachments policy, the safe attachment rule and the associated safe attachment policy are removed.</span></span>

<span data-ttu-id="b7c7a-119">Exchange Online PowerShell またはスタンドアロン EOP PowerShell では、ポリシーとルールを個別に管理します。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-119">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="b7c7a-120">詳細については、後の [「Exchange Online PowerShell またはスタンドアロンの EOP PowerShell](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies) を使用して安全な添付ファイル ポリシーを構成する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-120">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Attachments policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies) section later in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="b7c7a-121">安全な添付ファイルの設定のグローバル設定領域では、安全な添付ファイル ポリシーに依存しない機能を構成します。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-121">In the global settings area of Safe Attachments settings, you configure features that are not dependent on Safe Attachments policies.</span></span> <span data-ttu-id="b7c7a-122">手順については [、「SharePoint、OneDrive、Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md) の ATP と [Microsoft 365 E5](safe-docs.md)の安全なドキュメントを有効にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-122">For instructions see [Turn on ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md) and [Safe Documents in Microsoft 365 E5](safe-docs.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="b7c7a-123">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="b7c7a-123">What do you need to know before you begin?</span></span>

- <span data-ttu-id="b7c7a-124"><https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-124">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="b7c7a-125">[安全な添付ファイル] **ページに直接移動するには** 、次のコマンドを使用します <https://protection.office.com/safeattachmentv2> 。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-125">To go directly to the **Safe Attachments** page, use <https://protection.office.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="b7c7a-126">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-126">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="b7c7a-127">スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-127">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="b7c7a-128">この記事に記載の手順を行うには、セキュリティ/コンプライアンス センターのアクセス許可が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-128">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="b7c7a-129">安全な添付ファイル ポリシーを作成、変更、および削除するには、組織の管理役割グループまたはセキュリティ管理者役割グループのメンバー **である** 必要があります。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-129">To create, modify, and delete Safe Attachments policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="b7c7a-130">安全な添付ファイル ポリシーに読み取り専用でアクセスするには、グローバル閲覧者またはセキュリティ閲覧者の役割グループのメンバー **である** 必要があります。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-130">For read-only access to Safe Attachments policies, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="b7c7a-131">詳細については、「[セキュリティ/コンプライアンス センターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-131">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="b7c7a-132">**注**:</span><span class="sxs-lookup"><span data-stu-id="b7c7a-132">**Notes**:</span></span>

  - <span data-ttu-id="b7c7a-133">Microsoft 365 管理センターで、対応する Azure Active Directory の役割にユーザーを追加すると、ユーザーには、セキュリティ/コンプライアンス センター の必要なアクセス許可 _および_ Microsoft 365 のその他の機能に必要なアクセス許可が付与されます。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-133">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="b7c7a-134">詳細については、「[管理者の役割について](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-134">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="b7c7a-135">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) の **閲覧専用の組織管理** の役割グループが この機能への読み取り専用アクセス権も付与します。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-135">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="b7c7a-136">安全な添付ファイル ポリシーの推奨設定については、「安全な添付ファイルの [設定」を参照してください](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings)。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-136">For our recommended settings for Safe Attachments policies, see [Safe Attachments settings](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings).</span></span>

- <span data-ttu-id="b7c7a-137">新しいポリシーまたは更新されたポリシーを適用するには、最大 30 分かかります。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-137">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

## <a name="use-the-security--compliance-center-to-create-safe-attachments-policies"></a><span data-ttu-id="b7c7a-138">セキュリティ/コンプライアンス センター&使用して安全な添付ファイル ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="b7c7a-138">Use the Security & Compliance Center to create Safe Attachments policies</span></span>

<span data-ttu-id="b7c7a-139">セキュリティ & コンプライアンス センターでカスタムの安全な添付ファイル ポリシーを作成すると、両方に同じ名前を使用して、安全な添付ファイル ルールと関連付けられた安全な添付ファイル ポリシーが同時に作成されます。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-139">Creating a custom Safe Attachments policy in the Security & Compliance Center creates the safe attachment rule and the associated safe attachment policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="b7c7a-140">セキュリティ/コンプライアンス センター&、脅威 **管理** ポリシー ATP の安全な添付 \>  \> **ファイルに移動します**。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-140">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="b7c7a-141">[安全な **添付ファイル] ページで** 、[作成] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-141">On the **Safe Attachments** page, click **Create**.</span></span>

3. <span data-ttu-id="b7c7a-142">安全 **な添付ファイルの新しいポリシー** ウィザードが開きます。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-142">The **New Safe Attachments policy** wizard opens.</span></span> <span data-ttu-id="b7c7a-143">[ポリシー **に名前を付け] ページ** で、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-143">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="b7c7a-144">**[名前]**: わかりやすい一意のポリシー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-144">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="b7c7a-145">**[説明]**: ポリシーについての説明を入力します (オプション)。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-145">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="b7c7a-146">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-146">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="b7c7a-147">表示される **[設定** ] ページで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-147">On the **Settings** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="b7c7a-148">**「安全な添付ファイル」の不明なマルウェアの応答**: 次のいずれかの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-148">**Safe Attachments unknown malware response**: Select one of the following values:</span></span>

     - <span data-ttu-id="b7c7a-149">**オフ**: 通常、この値はお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-149">**Off**: Typically, we don't recommend this value.</span></span>
     - <span data-ttu-id="b7c7a-150">**モニター**</span><span class="sxs-lookup"><span data-stu-id="b7c7a-150">**Monitor**</span></span>
     - <span data-ttu-id="b7c7a-151">**Block**: これは既定値であり、Standard および Strict の既定のセキュリティ ポリシーの [推奨値です](preset-security-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-151">**Block**: This is the default value, and the recommended value in Standard and Strict [preset security policies](preset-security-policies.md).</span></span>
     - <span data-ttu-id="b7c7a-152">**Replace**</span><span class="sxs-lookup"><span data-stu-id="b7c7a-152">**Replace**</span></span>
     - <span data-ttu-id="b7c7a-153">**動的配信 (プレビュー機能)**</span><span class="sxs-lookup"><span data-stu-id="b7c7a-153">**Dynamic Delivery (Preview Feature)**</span></span>

     <span data-ttu-id="b7c7a-154">これらの値については、「安全な添付ファイル [」ポリシー設定で説明されています](atp-safe-attachments.md#safe-attachments-policy-settings)。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-154">These values are explained in [Safe Attachments policy settings](atp-safe-attachments.md#safe-attachments-policy-settings).</span></span>

   - <span data-ttu-id="b7c7a-155">添付ファイルを次の電子メール アドレスに送信します。アクションの値が  **Block、Monitor、** または Replace の場合は、[リダイレクトを有効にする] を選択して、マルウェアの添付ファイルを含むメッセージを、分析と調査のために指定された内部または外部の電子メール アドレスに送信できます。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-155">**Send the attachment to the following email address**: For the action values **Block**, **Monitor**, or **Replace**, you can select **Enable redirect** to send messages that contain malware attachments to the specified internal or external email address for analysis and investigation.</span></span>

     <span data-ttu-id="b7c7a-156">標準ポリシーと厳密なポリシー設定では、リダイレクトを有効にしてください。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-156">The recommendation for Standard and Strict policy settings is to enable redirection.</span></span> <span data-ttu-id="b7c7a-157">詳細については、「安全な添付ファイル [の設定」を参照してください](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings)。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-157">For more information, see [Safe Attachments settings](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings).</span></span>

   - <span data-ttu-id="b7c7a-158">**添付ファイルのマルウェア** スキャンがタイム アウトまたはエラーが発生した場合は、上記の選択を適用します。「安全な添付ファイル」のスキャンが完了できない場合でも、メッセージに対して「安全な添付ファイル」の不明なマルウェア応答によって指定されたアクションが実行されます。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-158">**Apply the above selection if malware scanning for attachments times out or error occurs**: The action specified by **Safe Attachments unknown malware response** is taken on messages even when Safe Attachments scanning can't complete.</span></span> <span data-ttu-id="b7c7a-159">[有効なリダイレクト] を選択する場合は、常 **にこのオプションを選択します**。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-159">Always select this option if you select **Enabled redirect**.</span></span> <span data-ttu-id="b7c7a-160">そうしないと、メッセージが失われる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-160">Otherwise, messages might be lost.</span></span>

   <span data-ttu-id="b7c7a-161">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-161">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="b7c7a-162">表示される **[適用先** ] ページで、ポリシーが適用される内部受信者を特定します。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-162">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="b7c7a-163">各条件や例外は 1 回しか使用できませんが、条件や例外には複数の値を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-163">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="b7c7a-164">同じ条件や例外に複数の値がある場合、OR ロジック (たとえば、_\<recipient1\>_ または _\<recipient2\>_) が適用されます。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-164">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="b7c7a-165">a別の条件や例外がある場合は AND ロジック (たとえば、_\<recipient1\>_ かつ _\<member of group 1\>_) が適用されます。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-165">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="b7c7a-166">[条件 **の追加] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-166">Click **Add a condition**.</span></span> <span data-ttu-id="b7c7a-167">表示されるドロップダウンで、[適用] の下の条件を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-167">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="b7c7a-168">**受信者は、** 組織内の 1 つ以上のメールボックス、メール ユーザー、またはメール連絡先を指定します。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-168">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="b7c7a-169">**受信者が次のメンバーである**: 組織内の 1 つ以上のグループを指定します。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-169">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="b7c7a-170">**[受信者のドメインが次の値である]**: 組織内で構成済みの 1 つ以上の承認済みドメイン内の受信者を指定します。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-170">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in your organization.</span></span>

   <span data-ttu-id="b7c7a-171">条件を選択すると、対応するドロップダウンが [任意] ボックス **と一緒に表示** されます。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-171">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="b7c7a-172">ボックス内をクリックし、値の一覧をスクロールして選択します。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-172">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="b7c7a-173">ボックス内をクリックし、入力を開始してリストをフィルター処理し、値を選択します。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-173">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="b7c7a-174">値を追加するには、ボックス内の空の領域をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-174">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="b7c7a-175">個々のエントリを削除するには、値の **[削除]** ![ ](../../media/scc-remove-icon.png) アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-175">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="b7c7a-176">条件全体を削除するには、条件の **[削除**] ![ ](../../media/scc-remove-icon.png) アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-176">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="b7c7a-177">追加の条件を追加するには、[条件の追加] **をクリック** し、[適用する条件] の下の残りの値 **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-177">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="b7c7a-178">例外を追加するには、[条件の追加] をクリックし、[条件以外] で例外 **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-178">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="b7c7a-179">設定と動作は、条件とまったく同じです。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-179">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="b7c7a-180">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-180">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="b7c7a-181">表示される **[設定の確認** ] ページで、設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-181">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="b7c7a-182">各設定で **[編集]** をクリックして変更できます。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-182">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="b7c7a-183">完了したら、 **[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-183">When you're finished, click **Finish**.</span></span>

## <a name="use-the-security--compliance-center-to-view-safe-attachments-policies"></a><span data-ttu-id="b7c7a-184">セキュリティ/コンプライアンス センター&使用して安全な添付ファイル ポリシーを表示する</span><span class="sxs-lookup"><span data-stu-id="b7c7a-184">Use the Security & Compliance Center to view Safe Attachments policies</span></span>

1. <span data-ttu-id="b7c7a-185">セキュリティ/コンプライアンス センター&、脅威 **管理** ポリシー ATP の安全な添付 \>  \> **ファイルに移動します**。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-185">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="b7c7a-186">[安全 **な添付ファイル** ] ページで、一覧からポリシーを選択し、それをクリックします (チェック ボックスをオンにしない)。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-186">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

   <span data-ttu-id="b7c7a-187">ポリシーの詳細がフライアウトに表示される</span><span class="sxs-lookup"><span data-stu-id="b7c7a-187">The policy details appear in a fly out</span></span>

## <a name="use-the-security--compliance-center-to-modify-safe-attachments-policies"></a><span data-ttu-id="b7c7a-188">セキュリティ/コンプライアンス センター&使用して安全な添付ファイル ポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="b7c7a-188">Use the Security & Compliance Center to modify Safe Attachments policies</span></span>

1. <span data-ttu-id="b7c7a-189">セキュリティ/コンプライアンス センター&、脅威 **管理** ポリシー ATP の安全な添付 \>  \> **ファイルに移動します**。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-189">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="b7c7a-190">[安全 **な添付ファイル** ] ページで、一覧からポリシーを選択し、それをクリックします (チェック ボックスをオンにしない)。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-190">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="b7c7a-191">表示されたポリシーの詳細が表示されたら、[ポリシーの編集] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-191">In the policy details fly out that appears, click **Edit policy**.</span></span>

<span data-ttu-id="b7c7a-192">表示されるフライアウトで使用可能な設定は、「セキュリティ/コンプライアンス センターを使用して安全な添付ファイル ポリシーを作成する」セクション&説明 [されている設定と同](#use-the-security--compliance-center-to-create-safe-attachments-policies) じです。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-192">The available settings in the fly out that appears are identical to those described in the [Use the Security & Compliance Center to create Safe Attachments policies](#use-the-security--compliance-center-to-create-safe-attachments-policies) section.</span></span>

<span data-ttu-id="b7c7a-193">ポリシーを有効または無効にするか、ポリシーの優先順位を設定するには、以下のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-193">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-safe-attachments-policies"></a><span data-ttu-id="b7c7a-194">安全な添付ファイル ポリシーを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="b7c7a-194">Enable or disable Safe Attachments policies</span></span>

1. <span data-ttu-id="b7c7a-195">セキュリティ/コンプライアンス センター&、脅威 **管理** ポリシー ATP の安全な添付 \>  \> **ファイルに移動します**。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-195">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="b7c7a-196">[状態] 列の値 **に注意** してください。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-196">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="b7c7a-197">トグルを左に移動する</span><span class="sxs-lookup"><span data-stu-id="b7c7a-197">Move the toggle to the left</span></span> ![ポリシーをオフにする](../../media/scc-toggle-off.png) <span data-ttu-id="b7c7a-199">をクリックしてポリシーを無効にします。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-199">to disable the policy.</span></span>

   - <span data-ttu-id="b7c7a-200">トグルを右に移動する</span><span class="sxs-lookup"><span data-stu-id="b7c7a-200">Move the toggle to the right</span></span> ![ポリシーを有効にする](../../media/scc-toggle-on.png) <span data-ttu-id="b7c7a-202">をクリックしてポリシーを有効にしてください。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-202">to enable the policy.</span></span>

### <a name="set-the-priority-of-safe-attachments-policies"></a><span data-ttu-id="b7c7a-203">安全な添付ファイル ポリシーの優先度を設定する</span><span class="sxs-lookup"><span data-stu-id="b7c7a-203">Set the priority of Safe Attachments policies</span></span>

<span data-ttu-id="b7c7a-204">既定では、安全な添付ファイル ポリシーには、作成された順序に基づく優先度が設定されます (新しいポリシーは、古いポリシーよりも優先度が低くなります)。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-204">By default, Safe Attachments policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="b7c7a-205">優先度番号が小さいほど、ポリシーの優先度が高くなる (0 が最優先) ことを意味し、ポリシーは優先順位に従って処理されます (優先度の高いポリシーは、優先度の低いポリシーよりも先に処理されます)。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-205">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="b7c7a-206">2つのポリシーが同じ優先順位を持つことはできません。最初のポリシーが適用されると、ポリシーの処理は停止します。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-206">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="b7c7a-207">優先順位と複数のポリシーを評価し適用する方法の詳細については、「[メール保護の優先順位](how-policies-and-protections-are-combined.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-207">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="b7c7a-208">安全な添付ファイル ポリシーは、処理順に表示されます (最初のポリシーの **優先度** の値は 0 です)。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-208">Safe Attachments policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span>

<span data-ttu-id="b7c7a-209">**注**: セキュリティ/コンプライアンス センター&、安全な添付ファイル ポリシーの優先度は、作成後にのみ変更できます。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-209">**Note**: In the Security & Compliance Center, you can only change the priority of the Safe Attachments policy after you create it.</span></span> <span data-ttu-id="b7c7a-210">PowerShell では、安全な添付ファイル ルールを作成するときに既定の優先度を上書きできます (既存のルールの優先度に影響を与える可能性があります)。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-210">In PowerShell, you can override the default priority when you create the safe attachment rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="b7c7a-211">ポリシーの優先度を変更するには、リスト内で上下に移動させます (セキュリティ/コンプライアンス センター内で直接、**優先順位** 番号を変更することはできません)。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-211">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="b7c7a-212">セキュリティ/コンプライアンス センター&、脅威 **管理** ポリシー ATP の安全な添付 \>  \> **ファイルに移動します**。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-212">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="b7c7a-213">[安全 **な添付ファイル** ] ページで、一覧からポリシーを選択し、それをクリックします (チェック ボックスをオンにしない)。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-213">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="b7c7a-214">ポリシーの詳細が表示されたら、使用可能な優先度ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-214">In the policy details fly out that appears, click the available priority button.</span></span>

   - <span data-ttu-id="b7c7a-215">優先度の値が **0\*\*\*\*の安全** な添付ファイル ポリシーには、[優先度の下がり]**ボタン** しか使用できません。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-215">The Safe Attachments policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="b7c7a-216">優先度の値が最も低い安全な添付ファイル ポリシー (**たとえば、3)** には、[優先度の引き上げ]**ボタン** しか使用できません。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-216">The Safe Attachments policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="b7c7a-217">3 つ以上の安全な添付ファイル ポリシーがある場合は、優先度の高い値と最も低い値の間のポリシーの [優先度の引き上げ] ボタンと [優先度の下げ] ボタンの **両方を使用** できます。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-217">If you have three or more Safe Attachments policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="b7c7a-218">[優先度 **の引き上げ** ] または **[優先度の下げ** ] をクリックして、[優先度] の **値を変更** します。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-218">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="b7c7a-219">完了したら、**[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-219">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-safe-attachments-policies"></a><span data-ttu-id="b7c7a-220">セキュリティ/コンプライアンス センター&使用して安全な添付ファイル ポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="b7c7a-220">Use the Security & Compliance Center to remove Safe Attachments policies</span></span>

1. <span data-ttu-id="b7c7a-221">セキュリティ/コンプライアンス センター&、脅威 **管理** ポリシー ATP の安全な添付 \>  \> **ファイルに移動します**。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-221">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="b7c7a-222">[安全 **な添付ファイル** ] ページで、一覧からポリシーを選択し、それをクリックします (チェック ボックスをオンにしない)。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-222">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="b7c7a-223">表示されたポリシーの詳細が表示されたら、[ポリシーの削除] をクリックし、表示される警告ダイアログで [はい] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-223">In the policy details fly out that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies"></a><span data-ttu-id="b7c7a-224">Exchange Online PowerShell またはスタンドアロンの EOP PowerShell を使用して安全な添付ファイル ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="b7c7a-224">Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Attachments policies</span></span>

<span data-ttu-id="b7c7a-225">前述のように、安全な添付ファイル ポリシーは、安全な添付ファイル ポリシーと安全な添付ファイル ルールで構成されます。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-225">As previously described, a Safe Attachments policy consists of a safe attachment policy and a safe attachment rule.</span></span>

<span data-ttu-id="b7c7a-226">PowerShell では、安全な添付ファイル ポリシーと安全な添付ファイルルールの違いは明白です。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-226">In PowerShell, the difference between safe attachment policies and safe attachment rules is apparent.</span></span> <span data-ttu-id="b7c7a-227">**\* -SafeAttachmentPolicy** コマンドレットを使用して安全な添付ファイル ポリシーを管理し **\* 、-SafeAttachmentRule** コマンドレットを使用して安全な添付ファイル ルールを管理します。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-227">You manage safe attachment policies by using the **\*-SafeAttachmentPolicy** cmdlets, and you manage safe attachment rules by using the **\*-SafeAttachmentRule** cmdlets.</span></span>

- <span data-ttu-id="b7c7a-228">PowerShell では、最初に安全な添付ファイル ポリシーを作成してから、ルールが適用されるポリシーを識別する安全な添付ファイル ルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-228">In PowerShell, you create the safe attachment policy first, then you create the safe attachment rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="b7c7a-229">PowerShell では、安全な添付ファイル ポリシーと安全な添付ファイルルールの設定を個別に変更します。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-229">In PowerShell, you modify the settings in the safe attachment policy and the safe attachment rule separately.</span></span>
- <span data-ttu-id="b7c7a-230">PowerShell から安全な添付ファイル ポリシーを削除しても、対応する安全な添付ファイル ルールは自動的には削除されません。その逆も同様です。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-230">When you remove a safe attachment policy from PowerShell, the corresponding safe attachment rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-safe-attachments-policies"></a><span data-ttu-id="b7c7a-231">PowerShell を使用して安全な添付ファイル ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="b7c7a-231">Use PowerShell to create Safe Attachments policies</span></span>

<span data-ttu-id="b7c7a-232">PowerShell で安全な添付ファイル ポリシーを作成するには、次の 2 つの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-232">Creating a Safe Attachments policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="b7c7a-233">安全な添付ファイル ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-233">Create the safe attachment policy.</span></span>
2. <span data-ttu-id="b7c7a-234">ルールが適用される安全な添付ファイル ポリシーを指定する安全な添付ファイル ルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-234">Create the safe attachment rule that specifies the safe attachment policy that the rule applies to.</span></span>

 <span data-ttu-id="b7c7a-235">**注**:</span><span class="sxs-lookup"><span data-stu-id="b7c7a-235">**Notes**:</span></span>

- <span data-ttu-id="b7c7a-236">新しい安全な添付ファイル ルールを作成し、関連付けされていない既存の安全な添付ファイル ポリシーをそのルールに割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-236">You can create a new safe attachment rule and assign an existing, unassociated safe attachment policy to it.</span></span> <span data-ttu-id="b7c7a-237">安全な添付ファイル ルールは、複数の安全な添付ファイル ポリシーに関連付け設定できます。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-237">A safe attachment rule can't be associated with more than one safe attachment policy.</span></span>

- <span data-ttu-id="b7c7a-238">ポリシーを作成するまで、セキュリティ/コンプライアンス センターでは使用できない新しい安全な添付ファイル ポリシーに関する次&設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-238">You can configure the following settings on new safe attachment policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>
  - <span data-ttu-id="b7c7a-239">新しいポリシーを無効な状態 _で作成_ `$false` します **(New-SafeAttachmentRule コマンドレットで有効** )。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-239">Create the new policy as disabled (_Enabled_ `$false` on the **New-SafeAttachmentRule** cmdlet).</span></span>
  - <span data-ttu-id="b7c7a-240"> _\<Number\>_ **New-SafeAttachmentRule** コマンドレットで、作成時のポリシーの優先度 (優先度) を設定します。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-240">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-SafeAttachmentRule** cmdlet).</span></span>

- <span data-ttu-id="b7c7a-241">PowerShell で作成した新しい安全な添付ファイル ポリシーは、そのポリシーを安全な添付ファイル ルールに割り当てるまで、セキュリティ & コンプライアンス センターに表示されません。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-241">A new safe attachment policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a safe attachment rule.</span></span>

#### <a name="step-1-use-powershell-to-create-a-safe-attachment-policy"></a><span data-ttu-id="b7c7a-242">手順 1: PowerShell を使用して安全な添付ファイル ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="b7c7a-242">Step 1: Use PowerShell to create a safe attachment policy</span></span>

<span data-ttu-id="b7c7a-243">安全な添付ファイル ポリシーを作成するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-243">To create a safe attachment policy, use this syntax:</span></span>

```PowerShell
New-SafeAttachmentPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-Action <Allow | Block | Replace | DynamicDelivery>] [-Redirect <$true | $false>] [-RedirectAddress <SMTPEmailAddress>] [-ActionOnError <$true | $false>]
```

<span data-ttu-id="b7c7a-244">この例では、Contoso All という名前の安全な添付ファイル ポリシーを次の値で作成します。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-244">This example creates a safe attachment policy named Contoso All with the following values:</span></span>

- <span data-ttu-id="b7c7a-245">安全なドキュメント のスキャンによってマルウェアが含まれていると検出されたメッセージをブロックします _(Action_ パラメーターは使用しません。既定値は次のとおりです `Block` )。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-245">Block messages that are found to contain malware by Safe Documents scanning (we aren't using the _Action_ parameter, and the default value is `Block`).</span></span>
- <span data-ttu-id="b7c7a-246">リダイレクトが有効にされ、マルウェアが含まれていると検出されたメッセージは、分析と調査のためにsec-ops@contoso.comに送信されます。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-246">Redirection is enabled, and messages that are found to contain malware are sent to sec-ops@contoso.com for analysis and investigation.</span></span>
- <span data-ttu-id="b7c7a-247">安全な添付ファイルのスキャンが使用できないか、エラーが発生した場合は、メッセージを配信しません _(ActionOnError_ パラメーターは使用しません。既定値は次のとおりです `$true` )。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-247">If Safe Attachments scanning isn't available or encounters errors, don't deliver the message (we aren't using the _ActionOnError_ parameter, and the default value is `$true`).</span></span>

```PowerShell
New-SafeAttachmentPolicy -Name "Contoso All" -Redirect $true -RedirectAddress sec-ops@contoso.com
```

<span data-ttu-id="b7c7a-248">構文およびパラメーターの詳細については [、「New-SafeAttachmentPolicy」を参照してください](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentpolicy)。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-248">For detailed syntax and parameter information, see [New-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-a-safe-attachment-rule"></a><span data-ttu-id="b7c7a-249">手順 2: PowerShell を使用して安全な添付ファイル ルールを作成する</span><span class="sxs-lookup"><span data-stu-id="b7c7a-249">Step 2: Use PowerShell to create a safe attachment rule</span></span>

<span data-ttu-id="b7c7a-250">安全な添付ファイル ルールを作成するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-250">To create a safe attachment rule, use this syntax:</span></span>

```PowerShell
New-SafeAttachmentRule -Name "<RuleName>" -SafeAttachmentPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

<span data-ttu-id="b7c7a-251">この例では、Contoso All という名前の安全な添付ファイル ルールを次の条件で作成します。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-251">This example creates a safe attachment rule named Contoso All with the following conditions:</span></span>

- <span data-ttu-id="b7c7a-252">ルールは、Contoso All という名前の安全な添付ファイル ポリシーに関連付けられている。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-252">The rule is associated with the safe attachment policy named Contoso All.</span></span>
- <span data-ttu-id="b7c7a-253">ルールは、ドメイン内のすべての受信者にcontoso.comされます。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-253">The rule applies to all recipients in the contoso.com domain.</span></span>
- <span data-ttu-id="b7c7a-254">_Priority_ パラメーターを使用していないので、既定の優先度が使用されます。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-254">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>
- <span data-ttu-id="b7c7a-255">ルールは有効です _(Enabled_ パラメーターは使用しません。既定値は有効です `$true` )。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-255">The rule is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>

```powershell
New-SafeAttachmentRule -Name "Contoso All" -SafeAttachmentPolicy "Contoso All" -RecipientDomainIs contoso.com
```

<span data-ttu-id="b7c7a-256">構文およびパラメーターの詳細については [、「New-SafeAttachmentRule」を参照してください](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentrule)。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-256">For detailed syntax and parameter information, see [New-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentrule).</span></span>

### <a name="use-powershell-to-view-safe-attachment-policies"></a><span data-ttu-id="b7c7a-257">PowerShell を使用して安全な添付ファイル ポリシーを表示する</span><span class="sxs-lookup"><span data-stu-id="b7c7a-257">Use PowerShell to view safe attachment policies</span></span>

<span data-ttu-id="b7c7a-258">既存の安全な添付ファイル ポリシーを表示するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-258">To view existing safe attachment policies, use the following syntax:</span></span>

```PowerShell
Get-SafeAttachmentPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="b7c7a-259">この例では、すべての安全な添付ファイル ポリシーの要約リストを返します。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-259">This example returns a summary list of all safe attachment policies.</span></span>

```PowerShell
Get-SafeAttachmentPolicy
```

<span data-ttu-id="b7c7a-260">この例では、Contoso Executives という名前の安全な添付ファイル ポリシーの詳細情報を返します。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-260">This example returns detailed information for the safe attachment policy named Contoso Executives.</span></span>

```PowerShell
Get-SafeAttachmentPolicy -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="b7c7a-261">構文およびパラメーターの詳細については [、「Get-SafeAttachmentPolicy」を参照してください](https://docs.microsoft.com/powershell/module/exchange/get-safeattachmentpolicy)。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-261">For detailed syntax and parameter information, see [Get-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/get-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-view-safe-attachment-rules"></a><span data-ttu-id="b7c7a-262">PowerShell を使用して安全な添付ファイル ルールを表示する</span><span class="sxs-lookup"><span data-stu-id="b7c7a-262">Use PowerShell to view safe attachment rules</span></span>

<span data-ttu-id="b7c7a-263">既存の安全な添付ファイルルールを表示するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-263">To view existing safe attachment rules, use the following syntax:</span></span>

```PowerShell
Get-SafeAttachmentRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="b7c7a-264">この例では、すべての安全な添付ファイル ルールの要約リストを返します。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-264">This example returns a summary list of all safe attachment rules.</span></span>

```PowerShell
Get-SafeAttachmentRule
```

<span data-ttu-id="b7c7a-265">ルールを有効または無効にしてリストをフィルター処理するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-265">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-SafeAttachmentRule -State Disabled
```

```PowerShell
Get-SafeAttachmentRule -State Enabled
```

<span data-ttu-id="b7c7a-266">この例では、Contoso Executives という名前の安全な添付ファイル ルールの詳細情報を返します。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-266">This example returns detailed information for the safe attachment rule named Contoso Executives.</span></span>

```PowerShell
Get-SafeAttachmentRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="b7c7a-267">構文およびパラメーターの詳細については [、「Get-SafeAttachmentRule」を参照してください](https://docs.microsoft.com/powershell/module/exchange/get-safeattachmentrule)。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-267">For detailed syntax and parameter information, see [Get-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/get-safeattachmentrule).</span></span>

### <a name="use-powershell-to-modify-safe-attachment-policies"></a><span data-ttu-id="b7c7a-268">PowerShell を使用して安全な添付ファイル ポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="b7c7a-268">Use PowerShell to modify safe attachment policies</span></span>

<span data-ttu-id="b7c7a-269">PowerShell で安全な添付ファイル ポリシーの名前を変更することはできません **(Set-SafeAttachmentPolicy** コマンドレットには _Name_ パラメーターはありません)。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-269">You can't rename a safe attachment policy in PowerShell (the **Set-SafeAttachmentPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="b7c7a-270">セキュリティ & コンプライアンス センターで安全な添付ファイル ポリシーの名前を変更する場合は、安全な添付ファイル ルールの名前のみを変更 _します_。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-270">When you rename a Safe Attachments policy in the Security & Compliance Center, you're only renaming the safe attachment _rule_.</span></span>

<span data-ttu-id="b7c7a-271">それ以外の場合は、「手順 [1: PowerShell](#step-1-use-powershell-to-create-a-safe-attachment-policy) を使用して安全な添付ファイル ポリシーを作成する」セクションで説明したように、安全な添付ファイル ポリシーを作成する場合と同じ設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-271">Otherwise, the same settings are available when you create a safe attachment policy as described in the [Step 1: Use PowerShell to create a safe attachment policy](#step-1-use-powershell-to-create-a-safe-attachment-policy) section earlier in this article.</span></span>

<span data-ttu-id="b7c7a-272">安全な添付ファイル ポリシーを変更するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-272">To modify a safe attachment policy, use this syntax:</span></span>

```PowerShell
Set-SafeAttachmentPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="b7c7a-273">構文およびパラメーターの詳細については [、「Set-SafeAttachmentPolicy」を参照してください](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentpolicy)。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-273">For detailed syntax and parameter information, see [Set-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-modify-safe-attachment-rules"></a><span data-ttu-id="b7c7a-274">PowerShell を使用して安全な添付ファイル ルールを変更する</span><span class="sxs-lookup"><span data-stu-id="b7c7a-274">Use PowerShell to modify safe attachment rules</span></span>

<span data-ttu-id="b7c7a-275">PowerShell で安全な添付ファイル ルールを変更する場合に使用できない唯一の設定は、無効にされたルールを作成できる _Enabled_ パラメーターです。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-275">The only setting that's not available when you modify a safe attachment rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="b7c7a-276">既存の安全な添付ファイル ルールを有効または無効にするには、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-276">To enable or disable existing safe attachment rules, see the next section.</span></span>

<span data-ttu-id="b7c7a-277">それ以外の場合は、「手順 [2: PowerShell](#step-2-use-powershell-to-create-a-safe-attachment-rule) を使用して安全な添付ファイル ルールを作成する」セクションで説明したルールを作成する場合と同じ設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-277">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create a safe attachment rule](#step-2-use-powershell-to-create-a-safe-attachment-rule) section earlier in this article.</span></span>

<span data-ttu-id="b7c7a-278">安全な添付ファイル ルールを変更するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-278">To modify a safe attachment rule, use this syntax:</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="b7c7a-279">構文およびパラメーターの詳細については [、「Set-SafeAttachmentRule」を参照してください](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentrule)。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-279">For detailed syntax and parameter information, see [Set-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-safe-attachment-rules"></a><span data-ttu-id="b7c7a-280">PowerShell を使用して安全な添付ファイル ルールを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="b7c7a-280">Use PowerShell to enable or disable safe attachment rules</span></span>

<span data-ttu-id="b7c7a-281">PowerShell で安全な添付ファイルルールを有効または無効にすると、安全な添付ファイル ポリシー全体 (安全な添付ファイル ルールと割り当てられた安全な添付ファイル ポリシー) を有効または無効にできます。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-281">Enabling or disabling a safe attachment rule in PowerShell enables or disables the whole Safe Attachments policy (the safe attachment rule and the assigned safe attachment policy).</span></span>

<span data-ttu-id="b7c7a-282">PowerShell で安全な添付ファイル ルールを有効または無効にするには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-282">To enable or disable a safe attachment rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-SafeAttachmentRule | Disable-SafeAttachmentRule> -Identity "<RuleName>"
```

<span data-ttu-id="b7c7a-283">この例では、Marketing Department という名前の安全な添付ファイル ルールを無効にします。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-283">This example disables the safe attachment rule named Marketing Department.</span></span>

```PowerShell
Disable-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="b7c7a-284">この例では、同じルールを有効化します。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-284">This example enables same rule.</span></span>

```PowerShell
Enable-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="b7c7a-285">構文およびパラメーターの詳細については [、「Enable-SafeAttachmentRule」](https://docs.microsoft.com/powershell/module/exchange/enable-safeattachmentrule) および [「Disable-SafeAttachmentRule」を参照してください](https://docs.microsoft.com/powershell/module/exchange/disable-safeattachmentrule)。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-285">For detailed syntax and parameter information, see [Enable-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/enable-safeattachmentrule) and [Disable-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/disable-safeattachmentrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-safe-attachment-rules"></a><span data-ttu-id="b7c7a-286">PowerShell を使用して安全な添付ファイル ルールの優先度を設定する</span><span class="sxs-lookup"><span data-stu-id="b7c7a-286">Use PowerShell to set the priority of safe attachment rules</span></span>

<span data-ttu-id="b7c7a-287">ルールに設定できる優先度の最高値値は 0 です。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-287">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="b7c7a-288">設定できる最低値はルールの数に依存します。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-288">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="b7c7a-289">たとえば、ルールが五つある場合、使用できる優先度の値は 0 から 4 です。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-289">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="b7c7a-290">既存の一つのルールの優先度を変更すると、他のルールにも連鎖的な影響が起こりえます。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-290">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="b7c7a-291">たとえば、カスタム ルールが 5 つあって (優先度 0 から 4)、1 つのルールの優先度を 2 に変更した場合には、既存の優先度 2 のルールは優先度 3 に変更され、優先度 3 は優先度 4 に変更されます。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-291">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="b7c7a-292">PowerShell で安全な添付ファイル ルールの優先度を設定するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-292">To set the priority of a safe attachment rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="b7c7a-p124">この例では、Marketing Department というルールの優先度を 2 に設定しています。優先度が 2 以下のすべての既存のルールは、優先度が 1 ずつ下がります (優先度番号が 1 ずつ増加します)。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-p124">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="b7c7a-295">**注**: 新しいルールを作成するときに優先度を設定するには、代わりに **New-SafeAttachmentRule** コマンドレットの _Priority_ パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-295">**Note**: To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-SafeAttachmentRule** cmdlet instead.</span></span>

<span data-ttu-id="b7c7a-296">構文およびパラメーターの詳細については [、「Set-SafeAttachmentRule」を参照してください](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentrule)。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-296">For detailed syntax and parameter information, see [Set-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentrule).</span></span>

### <a name="use-powershell-to-remove-safe-attachment-policies"></a><span data-ttu-id="b7c7a-297">PowerShell を使用して安全な添付ファイル ポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="b7c7a-297">Use PowerShell to remove safe attachment policies</span></span>

<span data-ttu-id="b7c7a-298">PowerShell を使用して安全な添付ファイル ポリシーを削除する場合、対応する安全な添付ファイルルールは削除されません。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-298">When you use PowerShell to remove a safe attachment policy, the corresponding safe attachment rule isn't removed.</span></span>

<span data-ttu-id="b7c7a-299">PowerShell で安全な添付ファイル ポリシーを削除するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-299">To remove a safe attachment policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeAttachmentPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="b7c7a-300">この例では、Marketing Department という名前の安全な添付ファイル ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-300">This example removes the safe attachment policy named Marketing Department.</span></span>

```PowerShell
Remove-SafeAttachmentPolicy -Identity "Marketing Department"
```

<span data-ttu-id="b7c7a-301">構文およびパラメーターの詳細については [、「Remove-SafeAttachmentPolicy」を参照してください](https://docs.microsoft.com/powershell/module/exchange/remove-safeattachmentpolicy)。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-301">For detailed syntax and parameter information, see [Remove-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-remove-safe-attachment-rules"></a><span data-ttu-id="b7c7a-302">PowerShell を使用して安全な添付ファイル ルールを削除する</span><span class="sxs-lookup"><span data-stu-id="b7c7a-302">Use PowerShell to remove safe attachment rules</span></span>

<span data-ttu-id="b7c7a-303">PowerShell を使用して安全な添付ファイル ルールを削除する場合、対応する安全な添付ファイル ポリシーは削除されません。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-303">When you use PowerShell to remove a safe attachment rule, the corresponding safe attachment policy isn't removed.</span></span>

<span data-ttu-id="b7c7a-304">PowerShell で安全な添付ファイル ルールを削除するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-304">To remove a safe attachment rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeAttachmentRule -Identity "<PolicyName>"
```

<span data-ttu-id="b7c7a-305">この例では、Marketing Department という名前の安全な添付ファイル ルールを削除します。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-305">This example removes the safe attachment rule named Marketing Department.</span></span>

```PowerShell
Remove-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="b7c7a-306">構文およびパラメーターの詳細については [、「Remove-SafeAttachmentRule」を参照してください](https://docs.microsoft.com/powershell/module/exchange/remove-safeattachmentrule)。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-306">For detailed syntax and parameter information, see [Remove-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/remove-safeattachmentrule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="b7c7a-307">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="b7c7a-307">How do you know these procedures worked?</span></span>

<span data-ttu-id="b7c7a-308">安全な添付ファイル ポリシーが正常に作成、変更、または削除されたことを確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-308">To verify that you've successfully created, modified, or removed Safe Attachments policies, do any of the following steps:</span></span>

- <span data-ttu-id="b7c7a-309">セキュリティ/コンプライアンス センター&、脅威 **管理** ポリシー ATP の安全な添付 \>  \> **ファイルに移動します**。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-309">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span> <span data-ttu-id="b7c7a-310">ポリシーの一覧、その状態の値、 **および優先度** の値を **確認** します。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-310">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="b7c7a-311">詳細を表示するには、一覧からポリシーを選択し、詳細をフライアウトで表示します。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-311">To view more details, select the policy from the list, and view the details in the fly out.</span></span>

- <span data-ttu-id="b7c7a-312">Exchange Online PowerShell または Exchange Online Protection PowerShell で、ポリシーまたはルールの名前に置き換え、次のコマンドを実行して、設定 \<Name\> を確認します。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-312">In Exchange Online PowerShell or Exchange Online Protection PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-SafeAttachmentPolicy -Identity "<Name>" | Format-List
  ```

  ```PowerShell
  Get-SafeAttachmentRule -Identity "<Name>" | Format-List
  ```

<span data-ttu-id="b7c7a-313">安全な添付ファイルがメッセージをスキャンしているのを確認するには、365 レポートの利用可能な Defender Office確認します。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-313">To verify that Safe Attachments is scanning messages, check the available Defender for Office 365 reports.</span></span> <span data-ttu-id="b7c7a-314">詳細については、「Defender [for Office 365](view-reports-for-atp.md) のレポートを表示する」および「セキュリティ/コンプライアンス センターでエクスプローラー [&参照してください](threat-explorer.md)。</span><span class="sxs-lookup"><span data-stu-id="b7c7a-314">For more information, see [View reports for Defender for Office 365](view-reports-for-atp.md) and [Use Explorer in the Security & Compliance Center](threat-explorer.md).</span></span>
