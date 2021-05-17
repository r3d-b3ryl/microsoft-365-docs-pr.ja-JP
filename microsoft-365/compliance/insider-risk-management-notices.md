---
title: インサイダー リスク管理通知のテンプレート
description: インサイダー リスク管理通知テンプレートの詳細については、Microsoft 365
keywords: Microsoft 365、インサイダーリスク管理、リスク管理、コンプライアンス
localization_priority: Normal
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: 3a74c62e84c1cb9e4c749a364c0e5b6da25a8af9
ms.sourcegitcommit: 74ef7179887eedc696c975a82c865b2d4b3808fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/09/2020
ms.locfileid: "47416481"
---
# <a name="insider-risk-management-notice-templates"></a><span data-ttu-id="bee67-104">インサイダー リスク管理通知のテンプレート</span><span class="sxs-lookup"><span data-stu-id="bee67-104">Insider risk management notice templates</span></span>

<span data-ttu-id="bee67-105">Insider リスク管理通知テンプレートを使用すると、ユーザーのアクティビティでポリシーの一致と通知が生成された場合に、電子メール メッセージをユーザーに送信できます。</span><span class="sxs-lookup"><span data-stu-id="bee67-105">Insider risk management notice templates allow you to send email messages to users when their activities generate a policy match and alert.</span></span> <span data-ttu-id="bee67-106">ほとんどの場合、アラートを生成するユーザー アクションは、誤った意図のない間違いや不注意なアクティビティの結果です。</span><span class="sxs-lookup"><span data-stu-id="bee67-106">In most cases, user actions that generate alerts are the result of mistakes or inadvertent activities without ill intent.</span></span> <span data-ttu-id="bee67-107">通知は、ユーザーに対して、より注意深く、リフレッシュ トレーニングや企業ポリシー リソースへのリンクを提供する簡単なリマインダーとして機能します。</span><span class="sxs-lookup"><span data-stu-id="bee67-107">Notices serve as simple reminders to users to be more careful, to provide links to information for refresher training, or to corporate policy resources.</span></span> <span data-ttu-id="bee67-108">通知は、内部コンプライアンス トレーニング プログラムの重要な部分であり、定期的なリスク アクティビティを持つユーザーの文書化された監査証跡を作成するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="bee67-108">Notices can be an important part of your internal compliance training program and can help create a documented audit trail for users with recurring risk activities.</span></span>

<span data-ttu-id="bee67-109">問題解決プロセスの一環として、ポリシーの一致に関する通知メールをユーザーに送信する場合は、通知テンプレートを作成します。</span><span class="sxs-lookup"><span data-stu-id="bee67-109">Create notice templates if you want to send users an email reminder notice for policy matches as part of the issue resolution process.</span></span> <span data-ttu-id="bee67-110">通知は、確認中の特定のアラートに関連付けられたユーザーの電子メール アドレスにのみ送信できます。</span><span class="sxs-lookup"><span data-stu-id="bee67-110">Notices can only be sent to the user email address associated with the specific alert being reviewed.</span></span> <span data-ttu-id="bee67-111">ポリシーの一致に適用する通知テンプレートを選択する場合は、テンプレートで定義されているフィールド値を受け入れるか、必要に応じてフィールドを上書きすることもできます。</span><span class="sxs-lookup"><span data-stu-id="bee67-111">When selecting a notice template to apply to a policy match, you can choose to accept the field values defined in the template or overwrite the fields as needed.</span></span>

## <a name="notice-templates-dashboard"></a><span data-ttu-id="bee67-112">通知テンプレート ダッシュボード</span><span class="sxs-lookup"><span data-stu-id="bee67-112">Notice templates dashboard</span></span>

<span data-ttu-id="bee67-113">**通知テンプレートダッシュボード** には、構成された通知テンプレートのリストが表示され、新しい通知テンプレートを作成できます。</span><span class="sxs-lookup"><span data-stu-id="bee67-113">The **Notices templates dashboard** displays a list of configured notice templates and allows you to create new notice templates.</span></span> <span data-ttu-id="bee67-114">通知テンプレートは、最新の通知テンプレートを最初に、日付の逆順でリストに表示されます。</span><span class="sxs-lookup"><span data-stu-id="bee67-114">The notice templates are listed in reverse date order with the most recent notice template listed first.</span></span>

![Insider リスク管理通知テンプレート ダッシュボード](../media/insider-risk-notices-dashboard.png)

## <a name="html-for-notices"></a><span data-ttu-id="bee67-116">通知の HTML</span><span class="sxs-lookup"><span data-stu-id="bee67-116">HTML for notices</span></span>

<span data-ttu-id="bee67-117">通知用の単純なテキスト ベースの電子メール メッセージ以上のメッセージを作成する場合は、通知テンプレートのメッセージ本文フィールドに HTML を使用して、より詳細なメッセージを作成できます。</span><span class="sxs-lookup"><span data-stu-id="bee67-117">If you'd like to create more than a simple text-based email message for notifications, you can create a more detailed message by using HTML in the message body field of a notice template.</span></span> <span data-ttu-id="bee67-118">次の例では、基本的な HTML ベースの電子メール通知テンプレートのメッセージ本文形式を示します。</span><span class="sxs-lookup"><span data-stu-id="bee67-118">The following example provides the message body format for a basic HTML-based email notification template:</span></span>

```HTML
<!DOCTYPE html>
<html>
<body>
<h2>Action Required: Contoso User Code of Conduct Policy Training</h2>
<p>A recent activity you've performed has generated a risk alert prohibited by the Contoso User <a href='https://www.contoso.com'>Code of Conduct Policy</a>.</p>
<p>You are required to attend the Contoso User Code of Conduct <a href='https://www.contoso.com'>training</a> within the next 14 days. Please contact <a href='mailto:hr@contoso.com'>Human Resources</a> with any questions about this training request.</p>
<p>Thank you,</p>
<p><em>Human Resources</em></p>
</body>
</html>
```

> [!NOTE]
> <span data-ttu-id="bee67-119">現在、インサイダー リスク管理通知テンプレートの HTML href 属性の実装では、URL 参照の二重引用符ではなく単一引用符のみをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="bee67-119">HTML href attribute implementation in the insider risk management notice templates currently support only single quotation marks instead of double quotation marks for URL references.</span></span>

## <a name="create-a-new-notice-template"></a><span data-ttu-id="bee67-120">新しい通知テンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="bee67-120">Create a new notice template</span></span>

<span data-ttu-id="bee67-121">新しいインサイダー リスク管理通知テンプレートを作成するには、コンプライアンス センターの **Insider** リスク管理ソリューションで通知ウィザードMicrosoft 365します。</span><span class="sxs-lookup"><span data-stu-id="bee67-121">To create a new insider risk management notice template, you'll use the notice wizard in **Insider risk management** solution in the Microsoft 365 compliance center.</span></span>

<span data-ttu-id="bee67-122">新しいインサイダー リスク管理通知テンプレートを作成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="bee67-122">Complete the following steps to create a new insider risk management notice template:</span></span>

1. <span data-ttu-id="bee67-123">コンプライアンス センターで [Microsoft 365 Insider](https://compliance.microsoft.com)リスク管理に **移動** し、[通知テンプレート **] タブを選択** します。</span><span class="sxs-lookup"><span data-stu-id="bee67-123">In the [Microsoft 365 compliance center](https://compliance.microsoft.com), go to **Insider risk management** and select the **Notice templates** tab.</span></span>
2. <span data-ttu-id="bee67-124">[通知 **テンプレートの作成] を** 選択して通知ウィザードを開きます。</span><span class="sxs-lookup"><span data-stu-id="bee67-124">Select **Create notice template** to open the notice wizard.</span></span>
3. <span data-ttu-id="bee67-125">[新しい **通知テンプレートの作成] ページで** 、次のフィールドに入力します。</span><span class="sxs-lookup"><span data-stu-id="bee67-125">On the **Create a new notice template** page, complete the following fields:</span></span>
    - <span data-ttu-id="bee67-126">**テンプレート名**: 通知の表示名を入力します。</span><span class="sxs-lookup"><span data-stu-id="bee67-126">**Template name**: Enter a friendly name for the notice.</span></span> <span data-ttu-id="bee67-127">この名前は、ケースから通知を送信するときに、通知ダッシュボードの通知の一覧と通知の選択リストに表示されます。</span><span class="sxs-lookup"><span data-stu-id="bee67-127">This name appears on the list of notices on the notice dashboard and in the notice selection list when sending notices from a case.</span></span>
    - <span data-ttu-id="bee67-128">**[送信先**]: 通知の送信者の電子メール アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="bee67-128">**Send from**: Enter the sender email address for the notice.</span></span> <span data-ttu-id="bee67-129">このアドレスは、ケースから通知を送信するときに変更されない限り、ユーザーに送信される通知の **[From:]** フィールドに表示されます。</span><span class="sxs-lookup"><span data-stu-id="bee67-129">This address will appear in the **From:** field in all notices sent to users unless changed when sending a notice from a case.</span></span>
    - <span data-ttu-id="bee67-130">**Cc フィールドと Bcc** フィールド: サブスクリプションの Active Directory から選択したポリシー一致の通知を受け取るオプションのユーザーまたはグループ。</span><span class="sxs-lookup"><span data-stu-id="bee67-130">**Cc and Bcc** fields: Optional users or groups to be notified of the policy match, selected from the Active Directory for your subscription.</span></span>
    - <span data-ttu-id="bee67-131">**件名**: メッセージの件名行に表示される情報は、テキスト文字をサポートします。</span><span class="sxs-lookup"><span data-stu-id="bee67-131">**Subject**: Information that appears in the subject line of the message, supports text characters.</span></span>
    - <span data-ttu-id="bee67-132">**メッセージ本文**: メッセージ本文に表示される情報は、テキスト値または HTML 値をサポートします。</span><span class="sxs-lookup"><span data-stu-id="bee67-132">**Message body**: Information that appears in the message body, supports text or HTML values.</span></span>
4. <span data-ttu-id="bee67-133">[**作成] を** 選択して通知テンプレートを作成して保存するか、[キャンセル] を選択して通知テンプレートを保存せずに閉じます。</span><span class="sxs-lookup"><span data-stu-id="bee67-133">Select **Create** to create and save the notice template or select **Cancel** to close without saving the notice template.</span></span>

## <a name="update-a-notice-template"></a><span data-ttu-id="bee67-134">通知テンプレートの更新</span><span class="sxs-lookup"><span data-stu-id="bee67-134">Update a notice template</span></span>

<span data-ttu-id="bee67-135">既存のインサイダー リスク管理通知テンプレートを更新するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="bee67-135">To update an existing insider risk management notice template, complete the following steps:</span></span>

1. <span data-ttu-id="bee67-136">コンプライアンス センターで [Microsoft 365 Insider](https://compliance.microsoft.com)リスク管理に **移動** し、[通知テンプレート **] タブを選択** します。</span><span class="sxs-lookup"><span data-stu-id="bee67-136">In the [Microsoft 365 compliance center](https://compliance.microsoft.com), go to **Insider risk management** and select the **Notice templates** tab.</span></span>
2. <span data-ttu-id="bee67-137">通知ダッシュボードで、管理する通知テンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="bee67-137">On the notice dashboard, select the notice template you want to manage.</span></span>
3. <span data-ttu-id="bee67-138">通知の詳細ページで、[編集] を **選択します。**</span><span class="sxs-lookup"><span data-stu-id="bee67-138">On the notice details page, select **Edit**</span></span>
4. <span data-ttu-id="bee67-139">[編集 **] ページ** で、次のフィールドを編集できます。</span><span class="sxs-lookup"><span data-stu-id="bee67-139">On the **Edit** page, you can edit the following fields:</span></span>
    - <span data-ttu-id="bee67-140">**テンプレート名**: 通知の新しい表示名を入力します。</span><span class="sxs-lookup"><span data-stu-id="bee67-140">**Template name**: Enter a new friendly name for the notice.</span></span> <span data-ttu-id="bee67-141">この名前は、ケースから通知を送信するときに、通知ダッシュボードの通知の一覧と通知の選択リストに表示されます。</span><span class="sxs-lookup"><span data-stu-id="bee67-141">This name appears on the list of notices on the notice dashboard and in the notice selection list when sending notices from a case.</span></span>
    - <span data-ttu-id="bee67-142">**送信:** 通知の送信者の電子メール アドレスを更新します。</span><span class="sxs-lookup"><span data-stu-id="bee67-142">**Send from**: Update the sender email address for the notice.</span></span> <span data-ttu-id="bee67-143">このアドレスは、ケースから通知を送信するときに変更されない限り、ユーザーに送信される通知の **[From:]** フィールドに表示されます。</span><span class="sxs-lookup"><span data-stu-id="bee67-143">This address will appear in the **From:** field in all notices sent to users unless changed when sending a notice from a case.</span></span>
    - <span data-ttu-id="bee67-144">**Cc フィールドと Bcc** フィールド: サブスクリプションの Active Directory から選択したポリシー一致の通知を受け取るオプションのユーザーまたはグループを更新します。</span><span class="sxs-lookup"><span data-stu-id="bee67-144">**Cc and Bcc** fields: Update optional users or groups to be notified of the policy match, selected from the Active Directory for your subscription.</span></span>
    - <span data-ttu-id="bee67-145">**件名**: メッセージの件名行に表示される情報を更新し、テキスト文字をサポートします。</span><span class="sxs-lookup"><span data-stu-id="bee67-145">**Subject**: Update information that appears in the subject line of the message, supports text characters.</span></span>
    - <span data-ttu-id="bee67-146">**メッセージ本文**: メッセージ本文に表示される情報を更新し、テキスト値または HTML 値をサポートします。</span><span class="sxs-lookup"><span data-stu-id="bee67-146">**Message body**: Update information that appears in the message body, supports text or HTML values.</span></span>
5. <span data-ttu-id="bee67-147">[ **保存] を** 選択して通知を更新して保存するか、[キャンセル] を **選択して通知** テンプレートを保存せずに閉じます。</span><span class="sxs-lookup"><span data-stu-id="bee67-147">Select **Save** to update and save the notice or select **Cancel** to close without saving the notice template.</span></span>

## <a name="delete-a-notice-template"></a><span data-ttu-id="bee67-148">通知テンプレートを削除する</span><span class="sxs-lookup"><span data-stu-id="bee67-148">Delete a notice template</span></span>

<span data-ttu-id="bee67-149">既存のインサイダー リスク管理通知テンプレートを削除するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="bee67-149">To delete an existing insider risk management notice template, complete the following steps:</span></span>

1. <span data-ttu-id="bee67-150">コンプライアンス センターで [Microsoft 365 Insider](https://compliance.microsoft.com)リスク管理に **移動** し、[通知テンプレート **] タブを選択** します。</span><span class="sxs-lookup"><span data-stu-id="bee67-150">In the [Microsoft 365 compliance center](https://compliance.microsoft.com), go to **Insider risk management** and select the **Notice templates** tab.</span></span>
2. <span data-ttu-id="bee67-151">通知ダッシュボードで、削除する通知テンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="bee67-151">On the notice dashboard, select the notice template you want to delete.</span></span>
3. <span data-ttu-id="bee67-152">ツールバーの **[削除** ] アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="bee67-152">Select the **Delete** icon on the toolbar.</span></span>
4. <span data-ttu-id="bee67-153">通知テンプレートを削除するには、削除ダイアログ **で [は** い] を選択します。</span><span class="sxs-lookup"><span data-stu-id="bee67-153">To delete the notice template, select **Yes** in the delete dialog.</span></span> <span data-ttu-id="bee67-154">削除を取り消す場合は、[キャンセル] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="bee67-154">To cancel the deletion, select **Cancel**.</span></span>
