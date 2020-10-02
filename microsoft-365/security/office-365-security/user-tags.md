---
title: Office 365 ATP のユーザー タグ
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
description: 管理者は、Office 365 ATP Plan 2 でユーザータグを使用して特定のユーザーグループを特定する方法について説明します。 タグフィルターは、Office 365 ATP のアラート、レポート、および調査に対して利用でき、タグ付きユーザーをすばやく識別できます。
ms.openlocfilehash: 9522499b3861f0f0e44fcbf09896a5c93feed95d
ms.sourcegitcommit: 3f8e573244bc082518125e339a385c41ef6ee800
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2020
ms.locfileid: "48337255"
---
# <a name="user-tags-in-office-365-atp"></a><span data-ttu-id="d61d5-104">Office 365 ATP のユーザー タグ</span><span class="sxs-lookup"><span data-stu-id="d61d5-104">User tags in Office 365 ATP</span></span>

<span data-ttu-id="d61d5-105">ユーザータグは、 [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md)のユーザーグループの識別子です。</span><span class="sxs-lookup"><span data-stu-id="d61d5-105">User tags are identifiers for specific groups of users in [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md).</span></span> <span data-ttu-id="d61d5-106">[優先度アカウント](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) は、ユーザータグの一種です。</span><span class="sxs-lookup"><span data-stu-id="d61d5-106">[Priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts) are a type of user tag.</span></span> <span data-ttu-id="d61d5-107">組織で Office 365 ATP Plan 2 (サブスクリプションに含まれているかアドオンとして含まれる) がある場合は、[優先度のアカウント] タグを使用するだけでなく、カスタムのユーザータグを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="d61d5-107">If your organization has Office 365 ATP Plan 2 (included in your subscription or as an add-on), you can create custom user tags in addition to using the priority accounts tag.</span></span>

<span data-ttu-id="d61d5-108">タグを特定のユーザーに適用した後、それらのタグをアラート、レポート、および調査のフィルターとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="d61d5-108">After you apply tags to specific users, you can use those tags as filters in alerts, reports, and investigations:</span></span>

- [<span data-ttu-id="d61d5-109">セキュリティ & コンプライアンスセンターのアラート</span><span class="sxs-lookup"><span data-stu-id="d61d5-109">Alerts in the Security & Compliance Center</span></span>](alerts.md)
- [<span data-ttu-id="d61d5-110">脅威エクスプローラーとリアルタイム検出</span><span class="sxs-lookup"><span data-stu-id="d61d5-110">Threat Explorer and real-time detections</span></span>](threat-explorer.md)
- [<span data-ttu-id="d61d5-111">脅威保護の状態レポート</span><span class="sxs-lookup"><span data-stu-id="d61d5-111">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="d61d5-112">キャンペーン ビュー</span><span class="sxs-lookup"><span data-stu-id="d61d5-112">Campaign Views</span></span>](campaigns.md)

<span data-ttu-id="d61d5-113">この記事では、セキュリティ & コンプライアンスセンターでユーザータグを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d61d5-113">This article explains how to configure user tags in the Security & Compliance Center.</span></span> <span data-ttu-id="d61d5-114">セキュリティ & コンプライアンスセンターでユーザータグを管理するためのコマンドレットはありません。</span><span class="sxs-lookup"><span data-stu-id="d61d5-114">There are no cmdlets in Security & Compliance Center to manage user tags.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="d61d5-115">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="d61d5-115">What do you need to know before you begin?</span></span>

- <span data-ttu-id="d61d5-116"><https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="d61d5-116">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="d61d5-117">[ **ユーザータグ** ] ページに直接移動するには、を開き <https://protection.office.com/userTags> ます。</span><span class="sxs-lookup"><span data-stu-id="d61d5-117">To go directly to the **User tags** page, open <https://protection.office.com/userTags>.</span></span>

- <span data-ttu-id="d61d5-118">ユーザータグを作成、変更、または削除するには、セキュリティ & コンプライアンスセンターの [ **組織の管理** ] または [ **セキュリティ管理者** ] 役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="d61d5-118">To create, modify, or remove user tags, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="d61d5-119">詳細については、「[セキュリティ/コンプライアンス センターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d61d5-119">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="d61d5-120">また、Microsoft 365 管理センターで優先アカウントを管理および監視することもできます。</span><span class="sxs-lookup"><span data-stu-id="d61d5-120">You can also manage and monitor priority accounts in the Microsoft 365 admin center.</span></span> <span data-ttu-id="d61d5-121">手順については、「 [優先度のアカウントの管理と監視](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d61d5-121">For instructions, see [Manage and monitor priority accounts](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).</span></span>

## <a name="use-the-security-center-to-create-user-tags"></a><span data-ttu-id="d61d5-122">セキュリティセンターを使用してユーザータグを作成する</span><span class="sxs-lookup"><span data-stu-id="d61d5-122">Use the Security Center to create user tags</span></span>

1. <span data-ttu-id="d61d5-123">セキュリティセンターで、[ **脅威管理** \> **ユーザータグ**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="d61d5-123">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="d61d5-124">表示される [ **ユーザータグ** ] ページで、[ **タグの作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d61d5-124">On the **User tags** page that opens, click **Create tag**.</span></span>

3. <span data-ttu-id="d61d5-125">**タグ作成**ウィザードが新しいフライアウトで開きます。[**タグの定義**] ページで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="d61d5-125">The **Create tag** wizard opens in a new fly out. On the **Define tag** page, configure the following settings:</span></span>

   - <span data-ttu-id="d61d5-126">[**名前**]: タグのわかりやすい一意の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="d61d5-126">**Name**: Enter a unique, descriptive name for the tag.</span></span> <span data-ttu-id="d61d5-127">これは、表示され、使用される値です。</span><span class="sxs-lookup"><span data-stu-id="d61d5-127">This is the value that you'll see and use.</span></span>

   - <span data-ttu-id="d61d5-128">**説明**: タグの説明 (省略可能) を入力します。</span><span class="sxs-lookup"><span data-stu-id="d61d5-128">**Description**: Enter an optional description for the tag.</span></span>

   <span data-ttu-id="d61d5-129">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d61d5-129">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="d61d5-130">[ **メールボックスの割り当て** ] ページで、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="d61d5-130">On the **Assign mailboxes** page, do either of the following steps:</span></span>

   - <span data-ttu-id="d61d5-131">[ **メールボックスの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d61d5-131">Click **Add mailboxes**.</span></span> <span data-ttu-id="d61d5-132">スライドが表示されたら、次のいずれかの手順を実行して、個々のユーザーまたはグループを追加します。</span><span class="sxs-lookup"><span data-stu-id="d61d5-132">In the fly out that appears, do any of the following steps to add individual users or groups:</span></span>

     - <span data-ttu-id="d61d5-133">ボックスをクリックしてリストをスクロールし、ユーザーまたはグループを選択します。</span><span class="sxs-lookup"><span data-stu-id="d61d5-133">Click in the box and scroll through the list to select a user or group.</span></span>
     - <span data-ttu-id="d61d5-134">ボックス内をクリックして入力を開始し、リストにフィルターを適用してユーザーまたはグループを選択します。</span><span class="sxs-lookup"><span data-stu-id="d61d5-134">Click in the box and start typing to filter the list and select a user or group.</span></span>
     - <span data-ttu-id="d61d5-135">その他の値を追加するには、ボックスの空の領域をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d61d5-135">To add additional values, click in an empty area in the box.</span></span>
     - <span data-ttu-id="d61d5-136">ボックスから個々のエントリを削除するに**Remove**は、 ![ ](../../media/scc-remove-icon.png) ボックスで、ユーザーまたはグループの [削除] アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d61d5-136">To remove individual entries from the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user or group in the box.</span></span>
     - <span data-ttu-id="d61d5-137">ボックスの一覧から既存のエントリを削除するには **、[削除**] アイコンをクリックしてエントリを削除し ![ ](../../media/scc-remove-icon.png) ます。</span><span class="sxs-lookup"><span data-stu-id="d61d5-137">To remove existing entries from the list below the box, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) the entry.</span></span>

     <span data-ttu-id="d61d5-138">完了したら、[ **追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d61d5-138">When you're finished, click **Add**.</span></span>

   - <span data-ttu-id="d61d5-139">[ **インポート** ] をクリックして、ユーザーまたはグループの電子メールアドレスが含まれるテキストファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="d61d5-139">Click **Import** to select a text file that contains the email addresses of the users or groups.</span></span> <span data-ttu-id="d61d5-140">テキストファイルには、行ごとに1つのエントリが含まれていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="d61d5-140">Be sure the text file contains one entry per line.</span></span>

   <span data-ttu-id="d61d5-141">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d61d5-141">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="d61d5-142">[ **タグの確認** ] ページで、設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="d61d5-142">On the **Review tag** page, review your settings.</span></span> <span data-ttu-id="d61d5-143">特定のセクションの [ **編集** ] をクリックして、変更を加えることができます。</span><span class="sxs-lookup"><span data-stu-id="d61d5-143">You can click **Edit** in the specific section to make changes.</span></span>

   <span data-ttu-id="d61d5-144">完了したら、[ **送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d61d5-144">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security-center-to-view-user-tags"></a><span data-ttu-id="d61d5-145">セキュリティセンターを使用してユーザータグを表示する</span><span class="sxs-lookup"><span data-stu-id="d61d5-145">Use the Security Center to view user tags</span></span>

1. <span data-ttu-id="d61d5-146">セキュリティセンターで、[ **脅威管理** \> **ユーザータグ**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="d61d5-146">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="d61d5-147">表示される [ **ユーザータグ** ] ページで、表示するユーザータグを選択します (チェックボックスをクリックしないでください)。</span><span class="sxs-lookup"><span data-stu-id="d61d5-147">On the **User tags** page that opens, select the user tag that you want to view (don't click on the checkbox).</span></span>

3. <span data-ttu-id="d61d5-148">読み取り専用の詳細が表示されたら、設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="d61d5-148">In the read-only details fly out that appears, review the settings.</span></span>

   <span data-ttu-id="d61d5-149">完了したら、**[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d61d5-149">When you're finished, click **Close**.</span></span>

## <a name="use-the-security-center-to-modify-user-tags"></a><span data-ttu-id="d61d5-150">セキュリティセンターを使用してユーザータグを変更する</span><span class="sxs-lookup"><span data-stu-id="d61d5-150">Use the Security Center to modify user tags</span></span>

1. <span data-ttu-id="d61d5-151">セキュリティセンターで、[ **脅威管理** \> **ユーザータグ**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="d61d5-151">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="d61d5-152">表示される [ **user tags** ] ページで、表示するユーザータグを選択し、[タグの **編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d61d5-152">On the **User tags** page that opens, select the user tag that you want to view, and then click **Edit tag**.</span></span>

3. <span data-ttu-id="d61d5-153">ポリシーウィザードは、 **編集タグ** で開きます。[ **次へ** ] をクリックして、設定を確認および変更します。</span><span class="sxs-lookup"><span data-stu-id="d61d5-153">The policy wizard opens in an **Edit tag** fly out. Click **Next** to review and modify the settings.</span></span>

   <span data-ttu-id="d61d5-154">完了したら、[ **送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d61d5-154">When you're finished, click **Submit**.</span></span>

## <a name="use-the-security-center-to-remove-user-tags"></a><span data-ttu-id="d61d5-155">セキュリティセンターを使用してユーザータグを削除する</span><span class="sxs-lookup"><span data-stu-id="d61d5-155">Use the Security Center to remove user tags</span></span>

<span data-ttu-id="d61d5-156">**注**: 組み込みの **優先度の account** タグを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="d61d5-156">**Note**: You can't remove the built-in **Priority account** tag.</span></span>

1. <span data-ttu-id="d61d5-157">セキュリティセンターで、[ **脅威管理** \> **ユーザータグ**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="d61d5-157">In the Security Center, go to **Threat management** \> **User tags**.</span></span>

2. <span data-ttu-id="d61d5-158">表示される [ **ユーザータグ** ] ページで、削除するユーザータグを選択し、[ **タグの削除**] をクリックしてから、[ **はい、削除** ] を選択します。この警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d61d5-158">On the **User tags** page that opens, select the user tag that you want to remove, click **Delete tag**, and then select **Yes, remove** in the warning that appears.</span></span>
