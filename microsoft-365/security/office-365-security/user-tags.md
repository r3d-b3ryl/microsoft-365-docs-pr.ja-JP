---
title: Microsoft Defender のユーザー タグ (Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 04/21/2021
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 管理者は、プラン 2 の Microsoft Defender でユーザー タグを持つユーザーの特定のグループOffice 365学習できます。 タグ フィルターは、Microsoft Defender のアラート、レポート、および調査で、タグ付けされたユーザーをすばやく識別Office 365に使用できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 44b925840700c00c6b2d28c445ac26abd6624d1c
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782863"
---
# <a name="user-tags-in-microsoft-defender-for-office-365"></a><span data-ttu-id="20770-104">Microsoft Defender のユーザー タグ (Office 365</span><span class="sxs-lookup"><span data-stu-id="20770-104">User tags in Microsoft Defender for Office 365</span></span>

> [!NOTE]
> <span data-ttu-id="20770-105">ユーザー タグ機能はプレビュー機能であり、すべてのユーザーが利用できるとは言え、変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="20770-105">The user tags feature is in Preview, isn't available to everyone, and is subject to change.</span></span> <span data-ttu-id="20770-106">リリース スケジュールの詳細については、次のロードマップ[をMicrosoft 365してください](https://www.microsoft.com/microsoft-365/roadmap)。</span><span class="sxs-lookup"><span data-stu-id="20770-106">For information about the release schedule, check out the [Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span></span>

<span data-ttu-id="20770-107">ユーザー タグは、Microsoft [Defender](defender-for-office-365.md)のユーザーの特定のグループの識別子Office 365。</span><span class="sxs-lookup"><span data-stu-id="20770-107">User tags are identifiers for specific groups of users in [Microsoft Defender for Office 365](defender-for-office-365.md).</span></span> <span data-ttu-id="20770-108">ユーザー タグには次の 2 種類があります。</span><span class="sxs-lookup"><span data-stu-id="20770-108">There are two types of user tags:</span></span>

- <span data-ttu-id="20770-109">**システム タグ**: 現在、 [優先度アカウント](../../admin/setup/priority-accounts.md) はシステム タグの唯一の種類です。</span><span class="sxs-lookup"><span data-stu-id="20770-109">**System tags**: Currently, [Priority accounts](../../admin/setup/priority-accounts.md) is the only type of system tag.</span></span>
- <span data-ttu-id="20770-110">**カスタム タグ**: これらのユーザー タグは、自分で作成します。</span><span class="sxs-lookup"><span data-stu-id="20770-110">**Custom tags**: You create these user tags yourself.</span></span>

<span data-ttu-id="20770-111">組織に Defender for Office 365 プラン 2 (サブスクリプションまたはアドオンとして含まれる) がある場合は、優先度アカウント タグの使用に加えて、カスタム ユーザー タグを作成できます。</span><span class="sxs-lookup"><span data-stu-id="20770-111">If your organization has Defender for Office 365 Plan 2 (included in your subscription or as an add-on), you can create custom user tags in addition to using the priority accounts tag.</span></span>

> [!NOTE]
> <span data-ttu-id="20770-112">現時点では、メールボックス ユーザーにのみユーザー タグを適用できます。</span><span class="sxs-lookup"><span data-stu-id="20770-112">Currently, you can only apply user tags to mailbox users.</span></span>

<span data-ttu-id="20770-113">システム タグまたはカスタム タグをユーザーに適用した後、これらのタグをアラート、レポート、調査のフィルターとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="20770-113">After you apply system tags or custom tags to users, you can use those tags as filters in alerts, reports, and investigations:</span></span>

- [<span data-ttu-id="20770-114">セキュリティ コンプライアンス センター&アラート</span><span class="sxs-lookup"><span data-stu-id="20770-114">Alerts in the Security & Compliance Center</span></span>](alerts.md)
- [<span data-ttu-id="20770-115">脅威エクスプローラーとリアルタイム検出</span><span class="sxs-lookup"><span data-stu-id="20770-115">Threat Explorer and real-time detections</span></span>](threat-explorer.md)
- [<span data-ttu-id="20770-116">脅威保護の状態レポート</span><span class="sxs-lookup"><span data-stu-id="20770-116">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="20770-117">キャンペーン ビュー</span><span class="sxs-lookup"><span data-stu-id="20770-117">Campaign Views</span></span>](campaigns.md)
- <span data-ttu-id="20770-118">優先度アカウントの場合は、管理センター [](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) (EAC) の [優先アカウントの電子メールExchangeレポートを使用できます。</span><span class="sxs-lookup"><span data-stu-id="20770-118">For priority accounts, you can use the [Email issues for priority accounts report](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) in the Exchange admin center (EAC).</span></span>

<span data-ttu-id="20770-119">この記事では、セキュリティ コンプライアンス センターでユーザー タグを構成する&説明します。</span><span class="sxs-lookup"><span data-stu-id="20770-119">This article explains how to configure user tags in the Security & Compliance Center.</span></span> <span data-ttu-id="20770-120">ユーザー タグを管理するセキュリティ &コンプライアンス センターにはコマンドレットはありません。</span><span class="sxs-lookup"><span data-stu-id="20770-120">There are no cmdlets in Security & Compliance Center to manage user tags.</span></span>

<span data-ttu-id="20770-121">影響の大きなユーザー アカウントを保護するための戦略の一部であるユーザー タグの詳細については、「セキュリティに関する推奨事項」を参照[Microsoft 365。](security-recommendations-for-priority-accounts.md)</span><span class="sxs-lookup"><span data-stu-id="20770-121">To see how user tags are part of the strategy to help protect high-impact user accounts, see [Security recommendations for priority accounts in Microsoft 365](security-recommendations-for-priority-accounts.md).</span></span>

> [!NOTE]
> <span data-ttu-id="20770-122">統合セキュリティ センターを使用Microsoft 365、次のタグを設定できます https://security.microsoft.com/securitysettings/userTags 。</span><span class="sxs-lookup"><span data-stu-id="20770-122">If you use the unified Microsoft 365 security center, you can set tags here: https://security.microsoft.com/securitysettings/userTags.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="20770-123">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="20770-123">What do you need to know before you begin?</span></span>

- <span data-ttu-id="20770-124"><https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="20770-124">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="20770-125">[ユーザー タグ] ページに **直接移動するには** 、を開きます <https://protection.office.com/userTags> 。</span><span class="sxs-lookup"><span data-stu-id="20770-125">To go directly to the **User tags** page, open <https://protection.office.com/userTags>.</span></span>

- <span data-ttu-id="20770-126">この記事に記載の手順を行うには、セキュリティ/コンプライアンス センターのアクセス許可が割り当てられている必要があります:</span><span class="sxs-lookup"><span data-stu-id="20770-126">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="20770-127">ユーザー タグを作成、変更、および削除するには、組織の管理役割グループまたはセキュリティ管理者役割グループ **のメンバーである** 必要があります。</span><span class="sxs-lookup"><span data-stu-id="20770-127">To create, modify, and delete user tags, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="20770-128">既存のユーザー タグのメンバーを追加および削除するには、組織の管理、セキュリティ管理者、またはセキュリティオペレーターの役割グループ **のメンバーである** 必要があります。</span><span class="sxs-lookup"><span data-stu-id="20770-128">To add and remove members from existing user tags, you need to be a member of the **Organization Management**, **Security Administrator**, or **Security Operator** role groups</span></span>
  - <span data-ttu-id="20770-129">ユーザー タグへの読み取り専用アクセスでは、グローバル リーダーまたはセキュリティリーダーの役割グループ **のメンバーである** 必要があります。</span><span class="sxs-lookup"><span data-stu-id="20770-129">For read-only access to user tags, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="20770-130">詳細については、「[セキュリティ/コンプライアンス センターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="20770-130">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  > [!NOTE]
  >
  > - <span data-ttu-id="20770-131">Microsoft 365 管理センターで、対応する Azure Active Directory の役割にユーザーを追加すると、ユーザーには、セキュリティ/コンプライアンス センター の必要なアクセス許可 _および_ Microsoft 365 のその他の機能に必要なアクセス許可が付与されます。</span><span class="sxs-lookup"><span data-stu-id="20770-131">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="20770-132">詳細については、「[管理者の役割について](../../admin/add-users/about-admin-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="20770-132">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  >
  > - <span data-ttu-id="20770-133">ユーザー タグ管理は、タグ リーダーと **タグ マネージャー** の **役割によって制御** されます。</span><span class="sxs-lookup"><span data-stu-id="20770-133">User tag management is controlled by the **Tag Reader** and **Tag Manager** roles.</span></span>

- <span data-ttu-id="20770-134">また、管理センターで優先度アカウントを管理Microsoft 365監視することもできます。</span><span class="sxs-lookup"><span data-stu-id="20770-134">You can also manage and monitor priority accounts in the Microsoft 365 admin center.</span></span> <span data-ttu-id="20770-135">手順については、「優先度アカウントの [管理と監視」を参照してください](../../admin/setup/priority-accounts.md)。</span><span class="sxs-lookup"><span data-stu-id="20770-135">For instructions, see [Manage and monitor priority accounts](../../admin/setup/priority-accounts.md).</span></span>

- <span data-ttu-id="20770-136">特権アカウント (管理者アカウント) _のセキュリティ保護の詳細については_ 、このトピックを [参照してください](/azure/architecture/framework/security/critical-impact-accounts)。</span><span class="sxs-lookup"><span data-stu-id="20770-136">For information about securing _privileged accounts_ (admin accounts), see [this topic](/azure/architecture/framework/security/critical-impact-accounts).</span></span>

## <a name="use-the-security--compliance-center-to-create-user-tags"></a><span data-ttu-id="20770-137">セキュリティ コンプライアンス センターを&ユーザー タグを作成する</span><span class="sxs-lookup"><span data-stu-id="20770-137">Use the Security & Compliance Center to create user tags</span></span>

1. <span data-ttu-id="20770-138">セキュリティ コンプライアンス センター&、脅威管理 **のユーザー タグに** \> **移動します**。</span><span class="sxs-lookup"><span data-stu-id="20770-138">In the Security & Compliance Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="20770-139">開く **[ユーザー タグ] ページ** で、[タグの作成] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="20770-139">On the **User tags** page that opens, click **Create tag**.</span></span>

3. <span data-ttu-id="20770-140">タグ **の作成ウィザード** が新しいフライアウトで開きます。[タグの **定義] ページ** で、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="20770-140">The **Create tag** wizard opens in a new fly out. On the **Define tag** page, configure the following settings:</span></span>
   - <span data-ttu-id="20770-141">**名前**: タグの一意でわかりやすい名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="20770-141">**Name**: Enter a unique, descriptive name for the tag.</span></span> <span data-ttu-id="20770-142">これは、表示および使用する値です。</span><span class="sxs-lookup"><span data-stu-id="20770-142">This is the value that you'll see and use.</span></span>
   - <span data-ttu-id="20770-143">**説明**: タグのオプションの説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="20770-143">**Description**: Enter an optional description for the tag.</span></span>

   <span data-ttu-id="20770-144">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="20770-144">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="20770-145">[ユーザーの **割り当て** ] ページで、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="20770-145">On the **Assign users** page, do either of the following steps:</span></span>

   - <span data-ttu-id="20770-146">[ユーザー **の追加] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="20770-146">Click **Add users**.</span></span> <span data-ttu-id="20770-147">表示されるフライアウトで、次の手順を実行して個々のユーザーまたはグループを追加します。</span><span class="sxs-lookup"><span data-stu-id="20770-147">In the fly out that appears, do any of the following steps to add individual users or groups:</span></span>
     - <span data-ttu-id="20770-148">ボックス内をクリックし、リストをスクロールしてユーザーまたはグループを選択します。</span><span class="sxs-lookup"><span data-stu-id="20770-148">Click in the box and scroll through the list to select a user or group.</span></span>
     - <span data-ttu-id="20770-149">ボックス内をクリックし、入力を開始してリストをフィルター処理し、ユーザーまたはグループを選択します。</span><span class="sxs-lookup"><span data-stu-id="20770-149">Click in the box and start typing to filter the list and select a user or group.</span></span>
     - <span data-ttu-id="20770-150">追加の値を追加するには、ボックス内の空の領域をクリックします。</span><span class="sxs-lookup"><span data-stu-id="20770-150">To add additional values, click in an empty area in the box.</span></span>
     - <span data-ttu-id="20770-151">ボックスから個々のエントリを削除するには、ボックス **内の** ユーザーまたはグループの [削除] ![ ](../../media/scc-remove-icon.png) アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="20770-151">To remove individual entries from the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user or group in the box.</span></span>
     - <span data-ttu-id="20770-152">ボックスの下のリストから既存のエントリを削除するには、[削除 **]** アイコン ![ を ](../../media/scc-remove-icon.png) クリックします。</span><span class="sxs-lookup"><span data-stu-id="20770-152">To remove existing entries from the list below the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) the entry.</span></span>

     <span data-ttu-id="20770-153">完了したら、**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="20770-153">When you're finished, click **Add**.</span></span>

   - <span data-ttu-id="20770-154">[ **インポート] を** クリックして、ユーザーまたはグループの電子メール アドレスを含むテキスト ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="20770-154">Click **Import** to select a text file that contains the email addresses of the users or groups.</span></span> <span data-ttu-id="20770-155">テキスト ファイルに 1 行に 1 つのエントリが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="20770-155">Be sure the text file contains one entry per line.</span></span>

   <span data-ttu-id="20770-156">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="20770-156">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="20770-157">[タグの **確認] ページ** で、設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="20770-157">On the **Review tag** page, review your settings.</span></span> <span data-ttu-id="20770-158">特定のセクションで **[編集]** をクリックして変更を加えます。</span><span class="sxs-lookup"><span data-stu-id="20770-158">You can click **Edit** in the specific section to make changes.</span></span>

   <span data-ttu-id="20770-159">完了したら、[送信] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="20770-159">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security--compliance-center-to-view-user-tags"></a><span data-ttu-id="20770-160">セキュリティ コンプライアンス センターを&ユーザー タグを表示する</span><span class="sxs-lookup"><span data-stu-id="20770-160">Use the Security & Compliance Center to view user tags</span></span>

1. <span data-ttu-id="20770-161">セキュリティ コンプライアンス センター&、脅威管理 **のユーザー タグに** \> **移動します**。</span><span class="sxs-lookup"><span data-stu-id="20770-161">In the Security & Compliance Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="20770-162">開いた **[ユーザー タグ]** ページで、表示するユーザー タグを選択します (チェック ボックスをオンにしない)。</span><span class="sxs-lookup"><span data-stu-id="20770-162">On the **User tags** page that opens, select the user tag that you want to view (don't click on the checkbox).</span></span>

3. <span data-ttu-id="20770-163">表示される読み取り専用の詳細が表示されたら、設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="20770-163">In the read-only details fly out that appears, review the settings.</span></span>

   <span data-ttu-id="20770-164">完了したら、**[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="20770-164">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-user-tags"></a><span data-ttu-id="20770-165">コンプライアンス センターのセキュリティ &を使用してユーザー タグを変更する</span><span class="sxs-lookup"><span data-stu-id="20770-165">Use the Security & Compliance Center to modify user tags</span></span>

1. <span data-ttu-id="20770-166">セキュリティ コンプライアンス センター&、脅威管理 **のユーザー タグに** \> **移動します**。</span><span class="sxs-lookup"><span data-stu-id="20770-166">In the Security & Compliance Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="20770-167">開く **[ユーザー タグ]** ページで、表示するユーザー タグを選択し、[タグの編集] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="20770-167">On the **User tags** page that opens, select the user tag that you want to view, and then click **Edit tag**.</span></span>

3. <span data-ttu-id="20770-168">ポリシー ウィザードが [編集] タグ **のフライアウトで** 開きます。[次 **へ] を** クリックして設定を確認および変更します。</span><span class="sxs-lookup"><span data-stu-id="20770-168">The policy wizard opens in an **Edit tag** fly out. Click **Next** to review and modify the settings.</span></span>

   <span data-ttu-id="20770-169">完了したら、[送信] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="20770-169">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-user-tags"></a><span data-ttu-id="20770-170">コンプライアンス センターのセキュリティ &を使用してユーザー タグを削除する</span><span class="sxs-lookup"><span data-stu-id="20770-170">Use the Security & Compliance Center to remove user tags</span></span>

> [!NOTE]
> <span data-ttu-id="20770-171">組み込みの Priority アカウント タグ **は削除** できません。</span><span class="sxs-lookup"><span data-stu-id="20770-171">You can't remove the built-in **Priority account** tag.</span></span>

1. <span data-ttu-id="20770-172">セキュリティ コンプライアンス センター&、脅威管理 **のユーザー タグに** \> **移動します**。</span><span class="sxs-lookup"><span data-stu-id="20770-172">In the Security & Compliance Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="20770-173">開く **[ユーザー タグ]** ページで、削除するユーザー タグを選択し、[タグの削除] をクリックし、表示される警告で **[はい、** 削除] を選択します。</span><span class="sxs-lookup"><span data-stu-id="20770-173">On the **User tags** page that opens, select the user tag that you want to remove, click **Delete tag**, and then select **Yes, remove** in the warning that appears.</span></span>
