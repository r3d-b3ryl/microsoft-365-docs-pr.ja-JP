---
title: Microsoft Defender for Office 365 のユーザー タグ
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
description: 管理者は、Microsoft Defender for Office 365 プラン 2 でユーザー タグを持つユーザーの特定のグループを識別する方法について説明します。 タグ フィルターは、Microsoft Defender for Office 365 でアラート、レポート、調査を通じて利用して、タグ付けされたユーザーをすばやく識別できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ed91492e652773b3a48373df49b20d97887df6ee
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931436"
---
# <a name="user-tags-in-microsoft-defender-for-office-365"></a><span data-ttu-id="cf8fa-104">Microsoft Defender for Office 365 のユーザー タグ</span><span class="sxs-lookup"><span data-stu-id="cf8fa-104">User tags in Microsoft Defender for Office 365</span></span>

> [!NOTE]
> <span data-ttu-id="cf8fa-105">ユーザー タグ機能はプレビュー中であり、すべてのユーザーが利用できるとは言え、変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="cf8fa-105">The user tags feature is in Preview, isn't available to everyone, and is subject to change.</span></span> <span data-ttu-id="cf8fa-106">リリース スケジュールの詳細については [、Microsoft 365 ロードマップを参照してください](https://www.microsoft.com/microsoft-365/roadmap)。</span><span class="sxs-lookup"><span data-stu-id="cf8fa-106">For information about the release schedule, check out the [Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span></span>

<span data-ttu-id="cf8fa-107">ユーザー タグは、Microsoft [Defender 365](office-365-atp.md)の特定のユーザー グループOfficeです。</span><span class="sxs-lookup"><span data-stu-id="cf8fa-107">User tags are identifiers for specific groups of users in [Microsoft Defender for Office 365](office-365-atp.md).</span></span> <span data-ttu-id="cf8fa-108">ユーザー タグには、次の 2 種類があります。</span><span class="sxs-lookup"><span data-stu-id="cf8fa-108">There are two types of user tags:</span></span>

- <span data-ttu-id="cf8fa-109">**システム タグ**: 現在、 [システム](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) タグの種類は Priority アカウントのみです。</span><span class="sxs-lookup"><span data-stu-id="cf8fa-109">**System tags**: Currently, [Priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) is the only type of system tag.</span></span>
- <span data-ttu-id="cf8fa-110">**カスタム タグ**: これらのユーザー タグは自分で作成します。</span><span class="sxs-lookup"><span data-stu-id="cf8fa-110">**Custom tags**: You create these user tags yourself.</span></span>

<span data-ttu-id="cf8fa-111">組織に Office 365 プラン 2 用の Defender がある場合 (サブスクリプションまたはアドオンに含まれている場合)、優先度アカウント タグを使用する以外に、カスタム ユーザー タグを作成できます。</span><span class="sxs-lookup"><span data-stu-id="cf8fa-111">If your organization has Defender for Office 365 Plan 2 (included in your subscription or as an add-on), you can create custom user tags in addition to using the priority accounts tag.</span></span>

<span data-ttu-id="cf8fa-112">システム タグまたはカスタム タグをユーザーに適用した後、これらのタグをアラート、レポート、調査のフィルターとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="cf8fa-112">After you apply system tags or custom tags to users, you can use those tags as filters in alerts, reports, and investigations:</span></span>

- [<span data-ttu-id="cf8fa-113">セキュリティ/コンプライアンス センター&アラート</span><span class="sxs-lookup"><span data-stu-id="cf8fa-113">Alerts in the Security & Compliance Center</span></span>](alerts.md)
- [<span data-ttu-id="cf8fa-114">脅威エクスプローラーとリアルタイムの検出</span><span class="sxs-lookup"><span data-stu-id="cf8fa-114">Threat Explorer and real-time detections</span></span>](threat-explorer.md)
- [<span data-ttu-id="cf8fa-115">脅威保護の状態レポート</span><span class="sxs-lookup"><span data-stu-id="cf8fa-115">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="cf8fa-116">キャンペーン ビュー</span><span class="sxs-lookup"><span data-stu-id="cf8fa-116">Campaign Views</span></span>](campaigns.md)
- <span data-ttu-id="cf8fa-117">優先度アカウントの場合は、Exchange[](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)管理センター (EAC) の [優先度アカウントのメールの問題] レポートを使用できます。</span><span class="sxs-lookup"><span data-stu-id="cf8fa-117">For priority accounts, you can use the [Email issues for priority accounts report](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) in the Exchange admin center (EAC).</span></span>

<span data-ttu-id="cf8fa-118">この記事では、セキュリティ/コンプライアンス センターでユーザー タグを構成&説明します。</span><span class="sxs-lookup"><span data-stu-id="cf8fa-118">This article explains how to configure user tags in the Security & Compliance Center.</span></span> <span data-ttu-id="cf8fa-119">セキュリティ/コンプライアンス センターには、ユーザー &管理するためのコマンドレットはありません。</span><span class="sxs-lookup"><span data-stu-id="cf8fa-119">There are no cmdlets in Security & Compliance Center to manage user tags.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="cf8fa-120">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="cf8fa-120">What do you need to know before you begin?</span></span>

- <span data-ttu-id="cf8fa-121"><https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="cf8fa-121">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="cf8fa-122">ユーザー タグ ページに直接 **移動するには** 、開きます <https://protection.office.com/userTags> 。</span><span class="sxs-lookup"><span data-stu-id="cf8fa-122">To go directly to the **User tags** page, open <https://protection.office.com/userTags>.</span></span>

- <span data-ttu-id="cf8fa-123">この記事に記載の手順を行うには、セキュリティ/コンプライアンス センターのアクセス許可が割り当てられている必要があります:</span><span class="sxs-lookup"><span data-stu-id="cf8fa-123">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="cf8fa-124">ユーザー タグを作成、変更、および削除するには、組織の管理役割グループまたはセキュリティ管理者役割グループのメンバー **である** 必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf8fa-124">To create, modify, and delete user tags, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="cf8fa-125">既存のユーザー タグのメンバーを追加および削除するには、組織の管理、セキュリティ管理者、またはセキュリティオペレーターの役割グループ **のメンバーである** 必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf8fa-125">To add and remove members from existing user tags, you need to be a member of the **Organization Management**, **Security Administrator**, or **Security Operator** role groups</span></span>
  - <span data-ttu-id="cf8fa-126">ユーザー タグへの読み取り専用アクセスの場合、グローバル閲覧者またはセキュリティ閲覧者の役割グループのメンバー **である** 必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf8fa-126">For read-only access to user tags, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="cf8fa-127">詳細については、「[セキュリティ/コンプライアンス センターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cf8fa-127">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="cf8fa-128">**注**:</span><span class="sxs-lookup"><span data-stu-id="cf8fa-128">**Notes**:</span></span>

  - <span data-ttu-id="cf8fa-129">Microsoft 365 管理センターで、対応する Azure Active Directory の役割にユーザーを追加すると、ユーザーには、セキュリティ/コンプライアンス センター の必要なアクセス許可 _および_ Microsoft 365 のその他の機能に必要なアクセス許可が付与されます。</span><span class="sxs-lookup"><span data-stu-id="cf8fa-129">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="cf8fa-130">詳細については、「[管理者の役割について](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cf8fa-130">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="cf8fa-131">ユーザー タグ管理は、タグリーダー 、タグ投稿者、**および** タグ マネージャー **の役割によって制御** されます。</span><span class="sxs-lookup"><span data-stu-id="cf8fa-131">User tag management is controlled by the **Tag Reader**, **Tag Contributor**, and **Tag Manager** roles.</span></span>

- <span data-ttu-id="cf8fa-132">Microsoft 365 管理センターで優先度アカウントを管理および監視することもできます。</span><span class="sxs-lookup"><span data-stu-id="cf8fa-132">You can also manage and monitor priority accounts in the Microsoft 365 admin center.</span></span> <span data-ttu-id="cf8fa-133">手順については、「優先度アカウントの [管理と監視」を参照してください](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts)。</span><span class="sxs-lookup"><span data-stu-id="cf8fa-133">For instructions, see [Manage and monitor priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).</span></span>

## <a name="use-the-security-center-to-create-user-tags"></a><span data-ttu-id="cf8fa-134">セキュリティ センターを使用してユーザー タグを作成する</span><span class="sxs-lookup"><span data-stu-id="cf8fa-134">Use the Security Center to create user tags</span></span>

1. <span data-ttu-id="cf8fa-135">セキュリティ センターで、脅威管理の **ユーザー タグに** \> **移動します**。</span><span class="sxs-lookup"><span data-stu-id="cf8fa-135">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="cf8fa-136">表示された **[ユーザー タグ]** ページで、[タグの作成] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="cf8fa-136">On the **User tags** page that opens, click **Create tag**.</span></span>

3. <span data-ttu-id="cf8fa-137">タグ **の作成ウィザード** が新しいフライアウトで開きます。[タグ **の定義] ページ** で、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="cf8fa-137">The **Create tag** wizard opens in a new fly out. On the **Define tag** page, configure the following settings:</span></span>
   - <span data-ttu-id="cf8fa-138">**Name**: タグのわかりやすい一意の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="cf8fa-138">**Name**: Enter a unique, descriptive name for the tag.</span></span> <span data-ttu-id="cf8fa-139">これは、表示および使用される値です。</span><span class="sxs-lookup"><span data-stu-id="cf8fa-139">This is the value that you'll see and use.</span></span>
   - <span data-ttu-id="cf8fa-140">**説明**: タグのオプションの説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="cf8fa-140">**Description**: Enter an optional description for the tag.</span></span>

   <span data-ttu-id="cf8fa-141">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cf8fa-141">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="cf8fa-142">[ユーザーの **割り当て]** ページで、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="cf8fa-142">On the **Assign users** page, do either of the following steps:</span></span>

   - <span data-ttu-id="cf8fa-143">[ユーザー **の追加] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="cf8fa-143">Click **Add users**.</span></span> <span data-ttu-id="cf8fa-144">表示されるフライアウトで、次の手順を実行して個々のユーザーまたはグループを追加します。</span><span class="sxs-lookup"><span data-stu-id="cf8fa-144">In the fly out that appears, do any of the following steps to add individual users or groups:</span></span>
     - <span data-ttu-id="cf8fa-145">ボックス内をクリックし、一覧をスクロールしてユーザーまたはグループを選択します。</span><span class="sxs-lookup"><span data-stu-id="cf8fa-145">Click in the box and scroll through the list to select a user or group.</span></span>
     - <span data-ttu-id="cf8fa-146">ボックスをクリックし、入力を開始してリストをフィルター処理し、ユーザーまたはグループを選択します。</span><span class="sxs-lookup"><span data-stu-id="cf8fa-146">Click in the box and start typing to filter the list and select a user or group.</span></span>
     - <span data-ttu-id="cf8fa-147">値を追加するには、ボックス内の空の領域をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cf8fa-147">To add additional values, click in an empty area in the box.</span></span>
     - <span data-ttu-id="cf8fa-148">個々のエントリをボックスから削除するには、ボックス内のユーザーまたはグループの [削除] ![ ](../../media/scc-remove-icon.png) アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="cf8fa-148">To remove individual entries from the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user or group in the box.</span></span>
     - <span data-ttu-id="cf8fa-149">ボックスの下の一覧から既存のエントリを削除するには、[削除] アイコン ![ を ](../../media/scc-remove-icon.png) クリックします。</span><span class="sxs-lookup"><span data-stu-id="cf8fa-149">To remove existing entries from the list below the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) the entry.</span></span>

     <span data-ttu-id="cf8fa-150">完了したら、[追加] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="cf8fa-150">When you're finished, click **Add**.</span></span>

   - <span data-ttu-id="cf8fa-151">[ **インポート]** をクリックして、ユーザーまたはグループの電子メール アドレスを含むテキスト ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="cf8fa-151">Click **Import** to select a text file that contains the email addresses of the users or groups.</span></span> <span data-ttu-id="cf8fa-152">テキスト ファイルに 1 行に 1 つのエントリが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf8fa-152">Be sure the text file contains one entry per line.</span></span>

   <span data-ttu-id="cf8fa-153">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cf8fa-153">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="cf8fa-154">[タグ **の確認] ページ** で、設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="cf8fa-154">On the **Review tag** page, review your settings.</span></span> <span data-ttu-id="cf8fa-155">特定のセクションで **[編集** ] をクリックして変更を加えます。</span><span class="sxs-lookup"><span data-stu-id="cf8fa-155">You can click **Edit** in the specific section to make changes.</span></span>

   <span data-ttu-id="cf8fa-156">完了したら、[送信] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="cf8fa-156">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security-center-to-view-user-tags"></a><span data-ttu-id="cf8fa-157">セキュリティ センターを使用してユーザー タグを表示する</span><span class="sxs-lookup"><span data-stu-id="cf8fa-157">Use the Security Center to view user tags</span></span>

1. <span data-ttu-id="cf8fa-158">セキュリティ センターで、脅威管理の **ユーザー タグに** \> **移動します**。</span><span class="sxs-lookup"><span data-stu-id="cf8fa-158">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="cf8fa-159">開いた **[ユーザー タグ** ] ページで、表示するユーザー タグを選択します (チェック ボックスをオンにしない)。</span><span class="sxs-lookup"><span data-stu-id="cf8fa-159">On the **User tags** page that opens, select the user tag that you want to view (don't click on the checkbox).</span></span>

3. <span data-ttu-id="cf8fa-160">表示される読み取り専用の詳細フライアウトで、設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="cf8fa-160">In the read-only details fly out that appears, review the settings.</span></span>

   <span data-ttu-id="cf8fa-161">完了したら、**[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cf8fa-161">When you're finished, click **Close**.</span></span>

## <a name="use-the-security-center-to-modify-user-tags"></a><span data-ttu-id="cf8fa-162">セキュリティ センターを使用してユーザー タグを変更する</span><span class="sxs-lookup"><span data-stu-id="cf8fa-162">Use the Security Center to modify user tags</span></span>

1. <span data-ttu-id="cf8fa-163">セキュリティ センターで、脅威管理の **ユーザー タグに** \> **移動します**。</span><span class="sxs-lookup"><span data-stu-id="cf8fa-163">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="cf8fa-164">表示される **[ユーザー タグ** ] ページで、表示するユーザー タグを選択し、[タグの編集] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="cf8fa-164">On the **User tags** page that opens, select the user tag that you want to view, and then click **Edit tag**.</span></span>

3. <span data-ttu-id="cf8fa-165">ポリシー ウィザードが編集タグ **フライアウトで** 開きます。[ **次へ] を** クリックして設定を確認および変更します。</span><span class="sxs-lookup"><span data-stu-id="cf8fa-165">The policy wizard opens in an **Edit tag** fly out. Click **Next** to review and modify the settings.</span></span>

   <span data-ttu-id="cf8fa-166">完了したら、[送信] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="cf8fa-166">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security-center-to-remove-user-tags"></a><span data-ttu-id="cf8fa-167">セキュリティ センターを使用してユーザー タグを削除する</span><span class="sxs-lookup"><span data-stu-id="cf8fa-167">Use the Security Center to remove user tags</span></span>

<span data-ttu-id="cf8fa-168">**注**: 組み込みの Priority アカウント タグ **は削除** できません。</span><span class="sxs-lookup"><span data-stu-id="cf8fa-168">**Note**: You can't remove the built-in **Priority account** tag.</span></span>

1. <span data-ttu-id="cf8fa-169">セキュリティ センターで、脅威管理の **ユーザー タグに** \> **移動します**。</span><span class="sxs-lookup"><span data-stu-id="cf8fa-169">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="cf8fa-170">開く **[ユーザー** タグ] ページで、削除するユーザー タグを選択し、[タグの削除] をクリックして、[**は** い]、表示される警告で [削除] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="cf8fa-170">On the **User tags** page that opens, select the user tag that you want to remove, click **Delete tag**, and then select **Yes, remove** in the warning that appears.</span></span>
