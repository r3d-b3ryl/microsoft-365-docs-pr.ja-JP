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
ms.openlocfilehash: 1fb948d63f7bc42839d6fae8a2138d4ad48d81f6
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879170"
---
# <a name="user-tags-in-microsoft-defender-for-office-365"></a><span data-ttu-id="ce5df-104">Microsoft Defender のユーザー タグ (Office 365</span><span class="sxs-lookup"><span data-stu-id="ce5df-104">User tags in Microsoft Defender for Office 365</span></span>

> [!NOTE]
> <span data-ttu-id="ce5df-105">ユーザー タグ機能はプレビュー機能であり、すべてのユーザーが利用できるとは言え、変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ce5df-105">The user tags feature is in Preview, isn't available to everyone, and is subject to change.</span></span> <span data-ttu-id="ce5df-106">リリース スケジュールの詳細については、次のロードマップ[をMicrosoft 365してください](https://www.microsoft.com/microsoft-365/roadmap)。</span><span class="sxs-lookup"><span data-stu-id="ce5df-106">For information about the release schedule, check out the [Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span></span>

<span data-ttu-id="ce5df-107">ユーザー タグは、Microsoft [Defender](defender-for-office-365.md)のユーザーの特定のグループの識別子Office 365。</span><span class="sxs-lookup"><span data-stu-id="ce5df-107">User tags are identifiers for specific groups of users in [Microsoft Defender for Office 365](defender-for-office-365.md).</span></span> <span data-ttu-id="ce5df-108">ユーザー タグには次の 2 種類があります。</span><span class="sxs-lookup"><span data-stu-id="ce5df-108">There are two types of user tags:</span></span>

- <span data-ttu-id="ce5df-109">**システム タグ**: 現在、 [優先度アカウント](../../admin/setup/priority-accounts.md) はシステム タグの唯一の種類です。</span><span class="sxs-lookup"><span data-stu-id="ce5df-109">**System tags**: Currently, [Priority accounts](../../admin/setup/priority-accounts.md) is the only type of system tag.</span></span>
- <span data-ttu-id="ce5df-110">**カスタム タグ**: これらのユーザー タグは、自分で作成します。</span><span class="sxs-lookup"><span data-stu-id="ce5df-110">**Custom tags**: You create these user tags yourself.</span></span>

<span data-ttu-id="ce5df-111">組織に Defender for Office 365 プラン 2 (サブスクリプションまたはアドオンとして含まれる) がある場合は、優先度アカウント タグの使用に加えて、カスタム ユーザー タグを作成できます。</span><span class="sxs-lookup"><span data-stu-id="ce5df-111">If your organization has Defender for Office 365 Plan 2 (included in your subscription or as an add-on), you can create custom user tags in addition to using the priority accounts tag.</span></span>

> [!NOTE]
> <span data-ttu-id="ce5df-112">現時点では、メールボックス ユーザーにのみユーザー タグを適用できます。</span><span class="sxs-lookup"><span data-stu-id="ce5df-112">Currently, you can only apply user tags to mailbox users.</span></span>

<span data-ttu-id="ce5df-113">システム タグまたはカスタム タグをユーザーに適用した後、これらのタグをアラート、レポート、調査のフィルターとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="ce5df-113">After you apply system tags or custom tags to users, you can use those tags as filters in alerts, reports, and investigations:</span></span>

- [<span data-ttu-id="ce5df-114">Alerts</span><span class="sxs-lookup"><span data-stu-id="ce5df-114">Alerts</span></span>](alerts.md)
- [<span data-ttu-id="ce5df-115">脅威エクスプローラーとリアルタイム検出</span><span class="sxs-lookup"><span data-stu-id="ce5df-115">Threat Explorer and real-time detections</span></span>](threat-explorer.md)
- [<span data-ttu-id="ce5df-116">脅威保護の状態レポート</span><span class="sxs-lookup"><span data-stu-id="ce5df-116">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="ce5df-117">キャンペーン ビュー</span><span class="sxs-lookup"><span data-stu-id="ce5df-117">Campaign Views</span></span>](campaigns.md)
- <span data-ttu-id="ce5df-118">優先度アカウントの場合は、管理センター [](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) (EAC) の [優先アカウントの電子メールExchangeレポートを使用できます。</span><span class="sxs-lookup"><span data-stu-id="ce5df-118">For priority accounts, you can use the [Email issues for priority accounts report](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) in the Exchange admin center (EAC).</span></span>

<span data-ttu-id="ce5df-119">この記事では、Defender ポータルでユーザー タグを構成するMicrosoft 365説明します。</span><span class="sxs-lookup"><span data-stu-id="ce5df-119">This article explains how to configure user tags in the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="ce5df-120">ユーザー タグを管理するためのMicrosoft 365 Defender ポータルにはコマンドレットはありません。</span><span class="sxs-lookup"><span data-stu-id="ce5df-120">There are no cmdlets in Microsoft 365 Defender portal to manage user tags.</span></span>

<span data-ttu-id="ce5df-121">影響の大きなユーザー アカウントを保護するための戦略の一部であるユーザー タグの詳細については、「セキュリティに関する推奨事項」を参照[Microsoft 365。](security-recommendations-for-priority-accounts.md)</span><span class="sxs-lookup"><span data-stu-id="ce5df-121">To see how user tags are part of the strategy to help protect high-impact user accounts, see [Security recommendations for priority accounts in Microsoft 365](security-recommendations-for-priority-accounts.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="ce5df-122">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="ce5df-122">What do you need to know before you begin?</span></span>

- <span data-ttu-id="ce5df-123">Defender ポータルのMicrosoft 365開きます <https://security.microsoft.com/> 。</span><span class="sxs-lookup"><span data-stu-id="ce5df-123">You open the Microsoft 365 Defender portal at <https://security.microsoft.com/>.</span></span> <span data-ttu-id="ce5df-124">[ユーザー タグ] ページに **直接移動するには** 、を開きます <https://security.microsoft.com/securitysettings/userTags> 。</span><span class="sxs-lookup"><span data-stu-id="ce5df-124">To go directly to the **User tags** page, open <https://security.microsoft.com/securitysettings/userTags>.</span></span>

- <span data-ttu-id="ce5df-125">この記事の手順を実行するには、Microsoft 365 Defender ポータルでアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="ce5df-125">You need to be assigned permissions in the Microsoft 365 Defender portal before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="ce5df-126">ユーザー タグを作成、変更、および削除するには、組織の管理役割グループまたはセキュリティ管理者役割グループ **のメンバーである** 必要があります。</span><span class="sxs-lookup"><span data-stu-id="ce5df-126">To create, modify, and delete user tags, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="ce5df-127">既存のユーザー タグのメンバーを追加および削除するには、組織の管理、セキュリティ管理者、またはセキュリティオペレーターの役割グループ **のメンバーである** 必要があります。</span><span class="sxs-lookup"><span data-stu-id="ce5df-127">To add and remove members from existing user tags, you need to be a member of the **Organization Management**, **Security Administrator**, or **Security Operator** role groups</span></span>
  - <span data-ttu-id="ce5df-128">ユーザー タグへの読み取り専用アクセスでは、グローバル リーダーまたはセキュリティリーダーの役割グループ **のメンバーである** 必要があります。</span><span class="sxs-lookup"><span data-stu-id="ce5df-128">For read-only access to user tags, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="ce5df-129">詳細については、「Defender ポータル[のアクセス許可」をMicrosoft 365してください](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="ce5df-129">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-in-the-security-and-compliance-center.md).</span></span>

  > [!NOTE]
  >
  > - <span data-ttu-id="ce5df-130">Microsoft 365 管理センターの対応する Azure Active Directory ロールにユーザーを追加すると、Microsoft 365 Defender ポータルで必要なアクセス許可と、Microsoft 365の他の機能に対するアクセス許可がユーザーに付与されます。</span><span class="sxs-lookup"><span data-stu-id="ce5df-130">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="ce5df-131">詳細については、「[管理者の役割について](../../admin/add-users/about-admin-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ce5df-131">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  >
  > - <span data-ttu-id="ce5df-132">ユーザー タグ管理は、タグ リーダーと **タグ マネージャー** の **役割によって制御** されます。</span><span class="sxs-lookup"><span data-stu-id="ce5df-132">User tag management is controlled by the **Tag Reader** and **Tag Manager** roles.</span></span>

- <span data-ttu-id="ce5df-133">また、管理センターで優先度アカウントを管理Microsoft 365監視することもできます。</span><span class="sxs-lookup"><span data-stu-id="ce5df-133">You can also manage and monitor priority accounts in the Microsoft 365 admin center.</span></span> <span data-ttu-id="ce5df-134">手順については、「優先度アカウントの [管理と監視」を参照してください](../../admin/setup/priority-accounts.md)。</span><span class="sxs-lookup"><span data-stu-id="ce5df-134">For instructions, see [Manage and monitor priority accounts](../../admin/setup/priority-accounts.md).</span></span>

- <span data-ttu-id="ce5df-135">特権アカウント (管理者アカウント) _のセキュリティ保護の詳細については_ 、このトピックを [参照してください](/azure/architecture/framework/security/critical-impact-accounts)。</span><span class="sxs-lookup"><span data-stu-id="ce5df-135">For information about securing _privileged accounts_ (admin accounts), see [this topic](/azure/architecture/framework/security/critical-impact-accounts).</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-create-user-tags"></a><span data-ttu-id="ce5df-136">Defender ポータルMicrosoft 365を使用してユーザー タグを作成する</span><span class="sxs-lookup"><span data-stu-id="ce5df-136">Use the Microsoft 365 Defender portal to create user tags</span></span>

1. <span data-ttu-id="ce5df-137">[Defender ポータルMicrosoft 365] で、[メール]  \> **設定[ユーザー&] に** \> **移動します**。</span><span class="sxs-lookup"><span data-stu-id="ce5df-137">In the Microsoft 365 Defender portal, go to **Settings** \> **Email & collaboration** \> **User tags**.</span></span>

2. <span data-ttu-id="ce5df-138">[ユーザー タグ **] ページで** 、[タグの作成] ![ アイコン [タグの ](../../media/m365-cc-sc-create-icon.png) **作成] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="ce5df-138">On the **User tags** page, click ![Create tag icon](../../media/m365-cc-sc-create-icon.png) **Create tag**.</span></span>

3. <span data-ttu-id="ce5df-139">タグ **の作成ウィザード** が新しいフライアウトで開きます。</span><span class="sxs-lookup"><span data-stu-id="ce5df-139">The **Create tag** wizard opens in a new flyout.</span></span> <span data-ttu-id="ce5df-140">[タグの **定義] ページ** で、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="ce5df-140">On the **Define tag** page, configure the following settings:</span></span>
   - <span data-ttu-id="ce5df-141">**名前**: タグの一意でわかりやすい名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="ce5df-141">**Name**: Enter a unique, descriptive name for the tag.</span></span> <span data-ttu-id="ce5df-142">これは、表示および使用する値です。</span><span class="sxs-lookup"><span data-stu-id="ce5df-142">This is the value that you'll see and use.</span></span> <span data-ttu-id="ce5df-143">タグを作成した後は、名前を変更できない点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="ce5df-143">Note that you can't rename a tag after you create it.</span></span>
   - <span data-ttu-id="ce5df-144">**説明**: タグのオプションの説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="ce5df-144">**Description**: Enter an optional description for the tag.</span></span>

   <span data-ttu-id="ce5df-145">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ce5df-145">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="ce5df-146">[メンバーの **割り当て** ] ページで、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="ce5df-146">On the **Assign members** page, do either of the following steps:</span></span>
   - <span data-ttu-id="ce5df-147">[メンバー ![ の追加] アイコン [ ](../../media/m365-cc-sc-create-icon.png) **メンバーの追加] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="ce5df-147">Click ![Add members icon](../../media/m365-cc-sc-create-icon.png) **Add members**.</span></span> <span data-ttu-id="ce5df-148">表示されるフライアウトで、次の手順を実行して個々のユーザーまたはグループを追加します。</span><span class="sxs-lookup"><span data-stu-id="ce5df-148">In the fly out that appears, do any of the following steps to add individual users or groups:</span></span>
     - <span data-ttu-id="ce5df-149">ボックス内をクリックし、リストをスクロールしてユーザーまたはグループを選択します。</span><span class="sxs-lookup"><span data-stu-id="ce5df-149">Click in the box and scroll through the list to select a user or group.</span></span>
     - <span data-ttu-id="ce5df-150">ボックス内をクリックし、入力を開始してリストをフィルター処理し、ユーザーまたはグループを選択します。</span><span class="sxs-lookup"><span data-stu-id="ce5df-150">Click in the box and start typing to filter the list and select a user or group.</span></span>
     - <span data-ttu-id="ce5df-151">追加の値を追加するには、ボックス内の空の領域をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ce5df-151">To add additional values, click in an empty area in the box.</span></span>
     - <span data-ttu-id="ce5df-152">個々のエントリを削除するには、</span><span class="sxs-lookup"><span data-stu-id="ce5df-152">To remove individual entries, click</span></span> ![[エントリの削除] アイコン](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="ce5df-154">ボックス内のエントリの横に表示されます。</span><span class="sxs-lookup"><span data-stu-id="ce5df-154">next to the entry in the box.</span></span>
     - <span data-ttu-id="ce5df-155">すべてのエントリを削除するには、ボックスの下にある [選択された nn ユーザーと nn グループ] アイテムの [エントリの削除 ![ ](../../media/m365-cc-sc-remove-selection-icon.png) ] アイコンをクリックします。 </span><span class="sxs-lookup"><span data-stu-id="ce5df-155">To remove all entries, click ![Remove entry icon](../../media/m365-cc-sc-remove-selection-icon.png) on the **Selected nn users and nn groups** item below the box.</span></span>

     <span data-ttu-id="ce5df-156">完了したら、**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ce5df-156">When you're finished, click **Add**.</span></span>

     <span data-ttu-id="ce5df-157">[メンバーの割 **り当て** ] ページに戻って、エントリの横にある [削除] アイコンをクリックしてエントリ ![ ](../../media/m365-cc-sc-delete-icon.png) を削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="ce5df-157">Back on the **Assign members** page, you can also remove entries by clicking ![Delete icon](../../media/m365-cc-sc-delete-icon.png) next to the entry.</span></span>

   - <span data-ttu-id="ce5df-158">[ **インポート] を** クリックして、ユーザーまたはグループの電子メール アドレスを含むテキスト ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="ce5df-158">Click **Import** to select a text file that contains the email addresses of the users or groups.</span></span> <span data-ttu-id="ce5df-159">テキスト ファイルに 1 行に 1 つのエントリが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ce5df-159">Be sure the text file contains one entry per line.</span></span>

   <span data-ttu-id="ce5df-160">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ce5df-160">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="ce5df-161">表示される **[タグの確認** ] ページで、設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="ce5df-161">On the **Review tag** page that appears, review your settings.</span></span> <span data-ttu-id="ce5df-162">各セクションで **[編集]** を選択して、そのセクション内の設定を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="ce5df-162">You can select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="ce5df-163">または、**[戻る]** をクリックするか、ウィザードで特定のページを選択します。</span><span class="sxs-lookup"><span data-stu-id="ce5df-163">Or you can click **Back** or select the specific page in the wizard.</span></span>

   <span data-ttu-id="ce5df-164">完了したら、[送信] をクリック **し**、[完了] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="ce5df-164">When you're finished, click **Submit**, and then click **Done**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-view-user-tags"></a><span data-ttu-id="ce5df-165">Defender ポータルMicrosoft 365を使用してユーザー タグを表示する</span><span class="sxs-lookup"><span data-stu-id="ce5df-165">Use the Microsoft 365 Defender portal to view user tags</span></span>

1. <span data-ttu-id="ce5df-166">[Defender ポータルMicrosoft 365] で、[メール]  \> **設定[ユーザー&] に** \> **移動します**。</span><span class="sxs-lookup"><span data-stu-id="ce5df-166">In the Microsoft 365 Defender portal, go to **Settings** \> **Email & collaboration** \> **User tags**.</span></span>

2. <span data-ttu-id="ce5df-167">[ユーザー タグ **] ページ** では、ユーザー タグの一覧に次のプロパティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ce5df-167">On the **User tags** page, the following properties are displayed in the list of user tags:</span></span>

   - <span data-ttu-id="ce5df-168">**タグ**: ユーザー タグの名前。</span><span class="sxs-lookup"><span data-stu-id="ce5df-168">**Tag**: The name of the user tag.</span></span> <span data-ttu-id="ce5df-169">これには、組み込みの Priority アカウント システム **タグが** 含まれます。</span><span class="sxs-lookup"><span data-stu-id="ce5df-169">Note that this includes the built-in **Priority account** system tag.</span></span>
   - <span data-ttu-id="ce5df-170">**適用 :** メンバーの数</span><span class="sxs-lookup"><span data-stu-id="ce5df-170">**Applied to**: The number of members</span></span>
   - <span data-ttu-id="ce5df-171">**最終更新日時**</span><span class="sxs-lookup"><span data-stu-id="ce5df-171">**Last modified**</span></span>
   - <span data-ttu-id="ce5df-172">**作成日**</span><span class="sxs-lookup"><span data-stu-id="ce5df-172">**Created on**</span></span>

3. <span data-ttu-id="ce5df-173">名前をクリックしてユーザー タグを選択すると、詳細がフライアウトに表示されます。</span><span class="sxs-lookup"><span data-stu-id="ce5df-173">When you select a user tag by clicking on the name, the details are displayed in a flyout.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-modify-user-tags"></a><span data-ttu-id="ce5df-174">Defender ポータルMicrosoft 365を使用してユーザー タグを変更する</span><span class="sxs-lookup"><span data-stu-id="ce5df-174">Use the Microsoft 365 Defender portal to modify user tags</span></span>

1. <span data-ttu-id="ce5df-175">[Defender ポータルMicrosoft 365] で、[メール]  \> **設定[ユーザー&] に** \> **移動します**。</span><span class="sxs-lookup"><span data-stu-id="ce5df-175">In the Microsoft 365 Defender portal, go to **Settings** \> **Email & collaboration** \> **User tags**.</span></span>

2. <span data-ttu-id="ce5df-176">[ユーザー タグ **] ページで** 、リストからユーザー タグを選択し、[タグの編集] アイコン [タグの編集] ![ ](../../media/m365-cc-sc-edit-icon.png) **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="ce5df-176">On the **User tags** page, select the user tag from the list, and then click ![Edit tag icon](../../media/m365-cc-sc-edit-icon.png) **Edit tag**.</span></span>

3. <span data-ttu-id="ce5df-177">表示される詳細フライアウトでは、この記事の[「Microsoft 365 Defender](#use-the-microsoft-365-defender-portal-to-create-user-tags)ポータルを使用してユーザー タグを作成する」セクションで説明したように、同じウィザードと設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="ce5df-177">In the details flyout that appears, the same wizard and settings are available as described in the [Use the Microsoft 365 Defender portal to create user tags](#use-the-microsoft-365-defender-portal-to-create-user-tags) section earlier in this article.</span></span>

   <span data-ttu-id="ce5df-178">**注**:</span><span class="sxs-lookup"><span data-stu-id="ce5df-178">**Notes**:</span></span>

   - <span data-ttu-id="ce5df-179">[ **タグの定義** ] ページは組み込みの **Priority アカウント** システム タグでは使用できないので、このタグの名前を変更したり、説明を変更したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="ce5df-179">The **Define tag** page is not available for the built-in **Priority account** system tag, so you can't rename this tag or change the description.</span></span>
   - <span data-ttu-id="ce5df-180">カスタム タグの名前は変更できますが、説明は変更できます。</span><span class="sxs-lookup"><span data-stu-id="ce5df-180">You can't rename a custom tag, but you can change the description.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-remove-user-tags"></a><span data-ttu-id="ce5df-181">Defender ポータルMicrosoft 365使用してユーザー タグを削除する</span><span class="sxs-lookup"><span data-stu-id="ce5df-181">Use the Microsoft 365 Defender portal to remove user tags</span></span>

> [!NOTE]
> <span data-ttu-id="ce5df-182">組み込みの Priority アカウント システム タグ **は** 削除できません。</span><span class="sxs-lookup"><span data-stu-id="ce5df-182">You can't remove the built-in **Priority account** system tag.</span></span>

1. <span data-ttu-id="ce5df-183">[Defender ポータルMicrosoft 365] で、[メール]  \> **設定[ユーザー&] に** \> **移動します**。</span><span class="sxs-lookup"><span data-stu-id="ce5df-183">In the Microsoft 365 Defender portal, go to **Settings** \> **Email & collaboration** \> **User tags**.</span></span>

2. <span data-ttu-id="ce5df-184">[ユーザー タグ **] ページ** で、リストからユーザー タグを選択し、[タグの削除] アイコン [タグの削除] ![ ](../../media/m365-cc-sc-delete-icon.png) **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="ce5df-184">On the **User tags** page, select the user tag from the list, and then click ![Delete tag icon](../../media/m365-cc-sc-delete-icon.png) **Delete tag**.</span></span>

3. <span data-ttu-id="ce5df-185">表示される確認ダイアログで警告を読み、[はい、削除] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="ce5df-185">Read the warning in the confirmation dialog that appears, and then click **Yes, remove**.</span></span>
