---
title: Microsoft Defender for Office 365 のユーザータグ
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 管理者は、Office 365 プラン2の Microsoft Defender でユーザータグを使用して、ユーザーの特定のグループを特定する方法について説明します。 タグフィルターは、Microsoft Defender for Office 365 のアラート、レポート、および調査に対して利用でき、タグ付きユーザーをすばやく識別できます。
ms.openlocfilehash: fcc13a04ed603712bb2a45ccaadbaf161702c502
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "48842882"
---
# <a name="user-tags-in-microsoft-defender-for-office-365"></a><span data-ttu-id="39b44-104">Microsoft Defender for Office 365 のユーザータグ</span><span class="sxs-lookup"><span data-stu-id="39b44-104">User tags in Microsoft Defender for Office 365</span></span>

> [!NOTE]
> <span data-ttu-id="39b44-105">ユーザータグ機能はプレビューでは、すべてのユーザーが利用できるわけではなく、変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="39b44-105">The user tags feature is in Preview, isn't available to everyone, and is subject to change.</span></span> <span data-ttu-id="39b44-106">リリーススケジュールの詳細については、 [Microsoft 365 ロードマップ](https://www.microsoft.com/microsoft-365/roadmap)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="39b44-106">For information about the release schedule, check out the [Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span></span>

<span data-ttu-id="39b44-107">ユーザータグは、 [Office 365 の Defender](office-365-atp.md)にある特定のユーザーグループの識別子です。</span><span class="sxs-lookup"><span data-stu-id="39b44-107">User tags are identifiers for specific groups of users in [Defender for Office 365](office-365-atp.md).</span></span> <span data-ttu-id="39b44-108">ユーザータグには、次の2種類があります。</span><span class="sxs-lookup"><span data-stu-id="39b44-108">There are two types of user tags:</span></span>

- <span data-ttu-id="39b44-109">**システムタグ** : 現時点では、 [優先度のアカウント](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) のみがシステムタグの種類です。</span><span class="sxs-lookup"><span data-stu-id="39b44-109">**System tags** : Currently, [Priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) is the only type of system tag.</span></span>
- <span data-ttu-id="39b44-110">**カスタムタグ** : これらのユーザータグは自分で作成します。</span><span class="sxs-lookup"><span data-stu-id="39b44-110">**Custom tags** : You create these user tags yourself.</span></span>

<span data-ttu-id="39b44-111">組織が Office 365 プラン 2 (サブスクリプションに含まれているか、またはアドオン) に対して Defender を使用している場合は、[優先度のアカウント] タグを使用するだけでなく、カスタムユーザータグを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="39b44-111">If your organization has Defender for Office 365 Plan 2 (included in your subscription or as an add-on), you can create custom user tags in addition to using the priority accounts tag.</span></span>

<span data-ttu-id="39b44-112">システムタグまたはカスタムタグをユーザーに適用した後、それらのタグを警告、レポート、および調査のフィルターとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="39b44-112">After you apply system tags or custom tags to users, you can use those tags as filters in alerts, reports, and investigations:</span></span>

- [<span data-ttu-id="39b44-113">セキュリティ & コンプライアンスセンターのアラート</span><span class="sxs-lookup"><span data-stu-id="39b44-113">Alerts in the Security & Compliance Center</span></span>](alerts.md)
- [<span data-ttu-id="39b44-114">脅威エクスプローラーとリアルタイム検出</span><span class="sxs-lookup"><span data-stu-id="39b44-114">Threat Explorer and real-time detections</span></span>](threat-explorer.md)
- [<span data-ttu-id="39b44-115">脅威保護の状態レポート</span><span class="sxs-lookup"><span data-stu-id="39b44-115">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="39b44-116">キャンペーン ビュー</span><span class="sxs-lookup"><span data-stu-id="39b44-116">Campaign Views</span></span>](campaigns.md)

<span data-ttu-id="39b44-117">この記事では、セキュリティ & コンプライアンスセンターでユーザータグを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="39b44-117">This article explains how to configure user tags in the Security & Compliance Center.</span></span> <span data-ttu-id="39b44-118">セキュリティ & コンプライアンスセンターでユーザータグを管理するためのコマンドレットはありません。</span><span class="sxs-lookup"><span data-stu-id="39b44-118">There are no cmdlets in Security & Compliance Center to manage user tags.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="39b44-119">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="39b44-119">What do you need to know before you begin?</span></span>

- <span data-ttu-id="39b44-120"><https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="39b44-120">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="39b44-121">[ **ユーザータグ** ] ページに直接移動するには、を開き <https://protection.office.com/userTags> ます。</span><span class="sxs-lookup"><span data-stu-id="39b44-121">To go directly to the **User tags** page, open <https://protection.office.com/userTags>.</span></span>

- <span data-ttu-id="39b44-122">**カスタムユーザータグ** を作成、変更、または削除するには、セキュリティ & コンプライアンスセンターの [ **組織の管理** ] または [ **セキュリティ管理者** ] 役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="39b44-122">To create, modify, or remove **custom user tags** , you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="39b44-123">詳細については、「[セキュリティ/コンプライアンス センターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="39b44-123">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="39b44-124">優先アカウント (システムタグ) を構成するには、 [全体管理](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) 者または [Exchange 管理者](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#exchange-administrator)である必要があります。</span><span class="sxs-lookup"><span data-stu-id="39b44-124">To configure priority accounts (system tags), you need to be a [Global Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) or an [Exchange Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#exchange-administrator).</span></span>

  <span data-ttu-id="39b44-125">また、Microsoft 365 管理センターで優先アカウントを管理および監視することもできます。</span><span class="sxs-lookup"><span data-stu-id="39b44-125">You can also manage and monitor priority accounts in the Microsoft 365 admin center.</span></span> <span data-ttu-id="39b44-126">手順については、「 [優先度のアカウントの管理と監視](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="39b44-126">For instructions, see [Manage and monitor priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).</span></span>

## <a name="use-the-security-center-to-create-user-tags"></a><span data-ttu-id="39b44-127">セキュリティセンターを使用してユーザータグを作成する</span><span class="sxs-lookup"><span data-stu-id="39b44-127">Use the Security Center to create user tags</span></span>

1. <span data-ttu-id="39b44-128">セキュリティセンターで、[ **脅威管理** \> **ユーザータグ** ] に移動します。</span><span class="sxs-lookup"><span data-stu-id="39b44-128">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="39b44-129">表示される [ **ユーザータグ** ] ページで、[ **タグの作成** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="39b44-129">On the **User tags** page that opens, click **Create tag**.</span></span>

3. <span data-ttu-id="39b44-130">**タグ作成** ウィザードが新しいフライアウトで開きます。[ **タグの定義** ] ページで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="39b44-130">The **Create tag** wizard opens in a new fly out. On the **Define tag** page, configure the following settings:</span></span>

   - <span data-ttu-id="39b44-131">[ **名前** ]: タグのわかりやすい一意の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="39b44-131">**Name** : Enter a unique, descriptive name for the tag.</span></span> <span data-ttu-id="39b44-132">これは、表示され、使用される値です。</span><span class="sxs-lookup"><span data-stu-id="39b44-132">This is the value that you'll see and use.</span></span>

   - <span data-ttu-id="39b44-133">**説明** : タグの説明 (省略可能) を入力します。</span><span class="sxs-lookup"><span data-stu-id="39b44-133">**Description** : Enter an optional description for the tag.</span></span>

   <span data-ttu-id="39b44-134">完了したら、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="39b44-134">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="39b44-135">[ **メールボックスの割り当て** ] ページで、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="39b44-135">On the **Assign mailboxes** page, do either of the following steps:</span></span>

   - <span data-ttu-id="39b44-136">[ **メールボックスの追加** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="39b44-136">Click **Add mailboxes**.</span></span> <span data-ttu-id="39b44-137">スライドが表示されたら、次のいずれかの手順を実行して、個々のユーザーまたはグループを追加します。</span><span class="sxs-lookup"><span data-stu-id="39b44-137">In the fly out that appears, do any of the following steps to add individual users or groups:</span></span>

     - <span data-ttu-id="39b44-138">ボックスをクリックしてリストをスクロールし、ユーザーまたはグループを選択します。</span><span class="sxs-lookup"><span data-stu-id="39b44-138">Click in the box and scroll through the list to select a user or group.</span></span>
     - <span data-ttu-id="39b44-139">ボックス内をクリックして入力を開始し、リストにフィルターを適用してユーザーまたはグループを選択します。</span><span class="sxs-lookup"><span data-stu-id="39b44-139">Click in the box and start typing to filter the list and select a user or group.</span></span>
     - <span data-ttu-id="39b44-140">その他の値を追加するには、ボックスの空の領域をクリックします。</span><span class="sxs-lookup"><span data-stu-id="39b44-140">To add additional values, click in an empty area in the box.</span></span>
     - <span data-ttu-id="39b44-141">ボックスから個々のエントリを削除するに **Remove** は、 ![ ](../../media/scc-remove-icon.png) ボックスで、ユーザーまたはグループの [削除] アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="39b44-141">To remove individual entries from the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user or group in the box.</span></span>
     - <span data-ttu-id="39b44-142">ボックスの一覧から既存のエントリを削除するには **、[削除** ] アイコンをクリックしてエントリを削除し ![ ](../../media/scc-remove-icon.png) ます。</span><span class="sxs-lookup"><span data-stu-id="39b44-142">To remove existing entries from the list below the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) the entry.</span></span>

     <span data-ttu-id="39b44-143">完了したら、[ **追加** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="39b44-143">When you're finished, click **Add**.</span></span>

   - <span data-ttu-id="39b44-144">[ **インポート** ] をクリックして、ユーザーまたはグループの電子メールアドレスが含まれるテキストファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="39b44-144">Click **Import** to select a text file that contains the email addresses of the users or groups.</span></span> <span data-ttu-id="39b44-145">テキストファイルには、行ごとに1つのエントリが含まれていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="39b44-145">Be sure the text file contains one entry per line.</span></span>

   <span data-ttu-id="39b44-146">完了したら、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="39b44-146">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="39b44-147">[ **タグの確認** ] ページで、設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="39b44-147">On the **Review tag** page, review your settings.</span></span> <span data-ttu-id="39b44-148">特定のセクションの [ **編集** ] をクリックして、変更を加えることができます。</span><span class="sxs-lookup"><span data-stu-id="39b44-148">You can click **Edit** in the specific section to make changes.</span></span>

   <span data-ttu-id="39b44-149">完了したら、[ **送信** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="39b44-149">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security-center-to-view-user-tags"></a><span data-ttu-id="39b44-150">セキュリティセンターを使用してユーザータグを表示する</span><span class="sxs-lookup"><span data-stu-id="39b44-150">Use the Security Center to view user tags</span></span>

1. <span data-ttu-id="39b44-151">セキュリティセンターで、[ **脅威管理** \> **ユーザータグ** ] に移動します。</span><span class="sxs-lookup"><span data-stu-id="39b44-151">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="39b44-152">表示される [ **ユーザータグ** ] ページで、表示するユーザータグを選択します (チェックボックスをクリックしないでください)。</span><span class="sxs-lookup"><span data-stu-id="39b44-152">On the **User tags** page that opens, select the user tag that you want to view (don't click on the checkbox).</span></span>

3. <span data-ttu-id="39b44-153">読み取り専用の詳細が表示されたら、設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="39b44-153">In the read-only details fly out that appears, review the settings.</span></span>

   <span data-ttu-id="39b44-154">完了したら、 **[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="39b44-154">When you're finished, click **Close**.</span></span>

## <a name="use-the-security-center-to-modify-user-tags"></a><span data-ttu-id="39b44-155">セキュリティセンターを使用してユーザータグを変更する</span><span class="sxs-lookup"><span data-stu-id="39b44-155">Use the Security Center to modify user tags</span></span>

1. <span data-ttu-id="39b44-156">セキュリティセンターで、[ **脅威管理** \> **ユーザータグ** ] に移動します。</span><span class="sxs-lookup"><span data-stu-id="39b44-156">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="39b44-157">表示される [ **user tags** ] ページで、表示するユーザータグを選択し、[タグの **編集** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="39b44-157">On the **User tags** page that opens, select the user tag that you want to view, and then click **Edit tag**.</span></span>

3. <span data-ttu-id="39b44-158">ポリシーウィザードは、 **編集タグ** で開きます。[ **次へ** ] をクリックして、設定を確認および変更します。</span><span class="sxs-lookup"><span data-stu-id="39b44-158">The policy wizard opens in an **Edit tag** fly out. Click **Next** to review and modify the settings.</span></span>

   <span data-ttu-id="39b44-159">完了したら、[ **送信** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="39b44-159">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security-center-to-remove-user-tags"></a><span data-ttu-id="39b44-160">セキュリティセンターを使用してユーザータグを削除する</span><span class="sxs-lookup"><span data-stu-id="39b44-160">Use the Security Center to remove user tags</span></span>

<span data-ttu-id="39b44-161">**注** : 組み込みの **優先度の account** タグを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="39b44-161">**Note** : You can't remove the built-in **Priority account** tag.</span></span>

1. <span data-ttu-id="39b44-162">セキュリティセンターで、[ **脅威管理** \> **ユーザータグ** ] に移動します。</span><span class="sxs-lookup"><span data-stu-id="39b44-162">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="39b44-163">表示される [ **ユーザータグ** ] ページで、削除するユーザータグを選択し、[ **タグの削除** ] をクリックしてから、[ **はい、削除** ] を選択します。この警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="39b44-163">On the **User tags** page that opens, select the user tag that you want to remove, click **Delete tag** , and then select **Yes, remove** in the warning that appears.</span></span>
