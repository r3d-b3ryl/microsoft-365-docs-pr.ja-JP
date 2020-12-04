---
title: 検疫タグ
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: ''
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
ROBOTS: NOINDEX
description: 管理者は、検疫タグを使用して、検疫済みメッセージに対してユーザーが実行できる操作を制御する方法を学習できます。
ms.openlocfilehash: 68f28e2dff3bdeada2685ef6806489f5e57f5daf
ms.sourcegitcommit: d81c7cea85af6ad5fef81d3c930514a51464368c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/04/2020
ms.locfileid: "49572671"
---
# <a name="quarantine-tags"></a><span data-ttu-id="af145-103">検疫タグ</span><span class="sxs-lookup"><span data-stu-id="af145-103">Quarantine tags</span></span>

> [!NOTE]
> <span data-ttu-id="af145-104">この記事で説明されている機能は現在プレビュー段階であり、すべてのユーザーが利用できるわけではありません。変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="af145-104">The features that are described in this article are currently in Preview, aren't available to everyone, and are subject to change.</span></span>

<span data-ttu-id="af145-105">Exchange Online Protection (EOP) の検疫タグは、検疫済みメッセージの受信方法に基づいて、ユーザーが検疫済みメッセージに対して実行できる操作を制御することを許可します。</span><span class="sxs-lookup"><span data-stu-id="af145-105">Quarantine tags in Exchange Online Protection (EOP) allow admins to control what users are able to do to their quarantined messages based on how the message arrived in quarantine.</span></span>

<span data-ttu-id="af145-106">EOP は、従来、 [検疫](find-and-release-quarantined-messages-as-a-user.md) のメッセージと [エンドユーザーのスパム通知](use-spam-notifications-to-release-and-report-quarantined-messages.md)の特定のレベルの対話を許可または禁止しています。</span><span class="sxs-lookup"><span data-stu-id="af145-106">EOP has traditionally allowed or prevented certain levels of interactivity for messages in [quarantine](find-and-release-quarantined-messages-as-a-user.md) and in [end-user spam notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span> <span data-ttu-id="af145-107">たとえば、エンドユーザーはスパム対策フィルターによって検疫されたメッセージをスパムや一括で表示したり、解放したりすることはできますが、信頼性の高いフィッシングとして検疫されたメッセージを表示または解放することはできません。</span><span class="sxs-lookup"><span data-stu-id="af145-107">For example, end-users can view and release messages that were quarantined by anti-spam filtering as spam or bulk, but they can't view or release messages that were quarantined as high confidence phishing.</span></span>

<span data-ttu-id="af145-108">[サポートされている保護機能](#step-2-assign-a-quarantine-tag-to-supported-features)については、検疫タグでは、エンドユーザーのスパム通知メッセージで許可されるユーザーと、検疫内の検疫済みメッセージ (ユーザーが受信者であるメッセージ) を指定します。</span><span class="sxs-lookup"><span data-stu-id="af145-108">For [supported protection features](#step-2-assign-a-quarantine-tag-to-supported-features), quarantine tags specify what users are allowed to do in end-user spam notification messages and in their quarantined messages in quarantine (messages where the user is a recipient).</span></span> <span data-ttu-id="af145-109">検疫済みメッセージに対してエンドユーザーの履歴機能を強制するために、既定の検疫タグが自動的に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="af145-109">Default quarantine tags are automatically assigned to enforce the historical capabilities for end-users on quarantined messages.</span></span> <span data-ttu-id="af145-110">または、隔離されたメッセージに対してエンドユーザーが特定の操作を実行することを許可または禁止する、カスタムの検疫タグを作成して割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="af145-110">Or, you can create and assign custom quarantine tags to allow or prevent end-users from performing specific actions on quarantined messages.</span></span>

<span data-ttu-id="af145-111">個々のアクセス許可は、次の事前設定されたアクセス許可グループに統合されます。</span><span class="sxs-lookup"><span data-stu-id="af145-111">The individual permissions are combined into the following preset permission groups:</span></span>

- <span data-ttu-id="af145-112">アクセスなし</span><span class="sxs-lookup"><span data-stu-id="af145-112">No access</span></span>
- <span data-ttu-id="af145-113">制限付きアクセス</span><span class="sxs-lookup"><span data-stu-id="af145-113">Limited access</span></span>
- <span data-ttu-id="af145-114">フルアクセス</span><span class="sxs-lookup"><span data-stu-id="af145-114">Full access</span></span>

<span data-ttu-id="af145-115">次の表では、使用可能な個々のアクセス許可と、事前設定されたアクセス許可グループに含まれているかどうかについて説明します。</span><span class="sxs-lookup"><span data-stu-id="af145-115">The available individual permissions and what's included or not included in the preset permission groups are described in the following table:</span></span>

|<span data-ttu-id="af145-116">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="af145-116">Permission</span></span>|<span data-ttu-id="af145-117">アクセスなし</span><span class="sxs-lookup"><span data-stu-id="af145-117">No access</span></span>|<span data-ttu-id="af145-118">制限付きアクセス</span><span class="sxs-lookup"><span data-stu-id="af145-118">Limited access</span></span>|<span data-ttu-id="af145-119">フルアクセス</span><span class="sxs-lookup"><span data-stu-id="af145-119">Full access</span></span>|
|---|:---:|:---:|:---:|
|<span data-ttu-id="af145-120">**送信者を許可する** (_permissiontoallowsender_)</span><span class="sxs-lookup"><span data-stu-id="af145-120">**Allow sender** (_PermissionToAllowSender_)</span></span>|||![チェック マーク](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="af145-122">**受信拒否** (_permissiontoblocksender_)</span><span class="sxs-lookup"><span data-stu-id="af145-122">**Block sender** (_PermissionToBlockSender_)</span></span>||![チェック マーク](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="af145-125">**削除** (_PermissionToDelete_)</span><span class="sxs-lookup"><span data-stu-id="af145-125">**Delete** (_PermissionToDelete_)</span></span>||![チェック マーク](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="af145-128">**プレビュー** (_permissiontopreview_)</span><span class="sxs-lookup"><span data-stu-id="af145-128">**Preview** (_PermissionToPreview_)</span></span>||![チェック マーク](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="af145-131">**受信者が検疫からメッセージを解放することを許可する** (_PermissionToRelease_)</span><span class="sxs-lookup"><span data-stu-id="af145-131">**Allow recipients to release a message from quarantine** (_PermissionToRelease_)</span></span>|||![チェック マーク](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="af145-133">**受信者が検疫から解放されるメッセージを要求できるように** する (_PermissionToRequestRelease_)</span><span class="sxs-lookup"><span data-stu-id="af145-133">**Allow recipients to request a message to be released from quarantine** (_PermissionToRequestRelease_)</span></span>||![チェック マーク](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|

<span data-ttu-id="af145-135">事前設定されたアクセス許可グループの既定のアクセス許可が気に入らない場合は、カスタムの検疫タグを作成または変更するときにカスタムアクセス許可を使用できます。</span><span class="sxs-lookup"><span data-stu-id="af145-135">If you don't like the default permissions in the preset permission groups, you can use custom permissions when you create or modify custom quarantine tags.</span></span> <span data-ttu-id="af145-136">各アクセス許可の詳細については、この記事の後半の「 [検疫タグのアクセス許可の詳細](#quarantine-tag-permission-details) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="af145-136">For more information about what each permission does, see the [Quarantine tag permission details](#quarantine-tag-permission-details) section later in this article.</span></span>

<span data-ttu-id="af145-137">検疫タグは、セキュリティ & コンプライアンスセンターまたは PowerShell (Microsoft 365 組織の exchange online PowerShell で exchange online メールボックスを使用しない EOP 組織では、exchange online のメールボックスを使用せずに、スタンドアロンの EOP PowerShell で作成および割り当てを行います。</span><span class="sxs-lookup"><span data-stu-id="af145-137">You create and assign quarantine tags in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with Exchange Online Mailboxes; standalone EOP PowerShell in EOP organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="af145-138">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="af145-138">What do you need to know before you begin?</span></span>

- <span data-ttu-id="af145-139"><https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="af145-139">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="af145-140">[ **タグの検疫** ] ページに直接移動するには、を開き <https://protection.office.com/quarantineTags> ます。</span><span class="sxs-lookup"><span data-stu-id="af145-140">To go directly to the **Quarantine tags** page, open <https://protection.office.com/quarantineTags>.</span></span>

- <span data-ttu-id="af145-141">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="af145-141">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="af145-142">スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="af145-142">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="af145-143">検疫タグを表示、作成、変更、または削除するには、[セキュリティ & コンプライアンスセンター](permissions-in-the-security-and-compliance-center.md)で、[**組織の管理**] または [**セキュリティ管理者**] の役割のメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="af145-143">To view, create, modify, or remove quarantine tags, you need to be a member of the **Organization Management** or **Security Administrator** roles in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="step-1-create-quarantine-tags-in-the-security--compliance-center"></a><span data-ttu-id="af145-144">手順 1: セキュリティ & コンプライアンスセンターで検疫タグを作成する</span><span class="sxs-lookup"><span data-stu-id="af145-144">Step 1: Create quarantine tags in the Security & Compliance Center</span></span>

1. <span data-ttu-id="af145-145">セキュリティ & コンプライアンスセンターで、[ **脅威管理** \> **ポリシー** ] に移動し、[ **タグの検疫**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="af145-145">In the Security & Compliance Center, go to **Threat management** \> **Policy** and then select **Quarantine tags**.</span></span>

2. <span data-ttu-id="af145-146">[ **タグの検疫** ] ページで、[ **カスタムタグの追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="af145-146">On the **Quarantine tags** page, select **Add custom tag**.</span></span>

3. <span data-ttu-id="af145-147">[ **新しいタグ** ] ウィザードが開きます。</span><span class="sxs-lookup"><span data-stu-id="af145-147">The **New tag** wizard opens.</span></span> <span data-ttu-id="af145-148">[ **タグ名** ] ページで、[ **タグ名** ] フィールドに簡単な一意の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="af145-148">On the **Tag name** page, enter a brief but unique name in the **Tag name** field.</span></span> <span data-ttu-id="af145-149">次の手順で、タグを識別して、名前で選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="af145-149">You'll need to identify and select the tag by name in upcoming steps.</span></span> <span data-ttu-id="af145-150">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="af145-150">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="af145-151">[ **受信者メッセージアクセス** ] ページで、次のいずれかの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="af145-151">On the **Recipient message access** page, select one of the following values:</span></span>
   - <span data-ttu-id="af145-152">**アクセスなし**</span><span class="sxs-lookup"><span data-stu-id="af145-152">**No access**</span></span>
   - <span data-ttu-id="af145-153">**制限付きアクセス**</span><span class="sxs-lookup"><span data-stu-id="af145-153">**Limited access**</span></span>
   - <span data-ttu-id="af145-154">**フルアクセス**</span><span class="sxs-lookup"><span data-stu-id="af145-154">**Full access**</span></span>

   <span data-ttu-id="af145-155">これらのアクセス許可グループに含まれる個々のアクセス許可については、この記事の前半で説明します。</span><span class="sxs-lookup"><span data-stu-id="af145-155">The individual permissions that are included in these permission groups are described earlier in this article.</span></span>

   <span data-ttu-id="af145-156">カスタムアクセス許可を指定するには、[特定のアクセス権を **設定 (詳細)** ] を選択し、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="af145-156">To specify custom permissions, select **Set specific access (Advanced)** and configure the following settings:</span></span>

     - <span data-ttu-id="af145-157">**[リリースアクションの設定] を選択** します。次のいずれかの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="af145-157">**Select release action preference**: Select one of the following values:</span></span>
       - <span data-ttu-id="af145-158">[**解放アクションなし**: これは既定値です。</span><span class="sxs-lookup"><span data-stu-id="af145-158">**No release action**: This is the default value.</span></span>
       - <span data-ttu-id="af145-159">**受信者が検疫からメッセージを解放することを許可する**</span><span class="sxs-lookup"><span data-stu-id="af145-159">**Allow recipients to release a message from quarantine**</span></span>
       - <span data-ttu-id="af145-160">**受信者が検疫から解放されるメッセージを要求できるようにする**</span><span class="sxs-lookup"><span data-stu-id="af145-160">**Allow recipients to request a message to be released from quarantine**</span></span>

     - <span data-ttu-id="af145-161">**受信者が検疫済みメッセージに対して実行できる追加のアクションを選択** します。以下のいずれかの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="af145-161">**Select additional actions recipients can take on quarantined messages**: Select some, all, or none of the following values:</span></span>
       - <span data-ttu-id="af145-162">**Delete**</span><span class="sxs-lookup"><span data-stu-id="af145-162">**Delete**</span></span>
       - <span data-ttu-id="af145-163">**プレビュー**</span><span class="sxs-lookup"><span data-stu-id="af145-163">**Preview**</span></span>
       - <span data-ttu-id="af145-164">**送信者を許可する**</span><span class="sxs-lookup"><span data-stu-id="af145-164">**Allow sender**</span></span>
       - <span data-ttu-id="af145-165">**受信拒否**</span><span class="sxs-lookup"><span data-stu-id="af145-165">**Block sender**</span></span>

   <span data-ttu-id="af145-166">これらのアクセス許可と、エンドユーザーのスパム通知に対するこれらのアクセス許可とその影響については、この記事の後半の「 [検疫タグのアクセス許可の詳細](#quarantine-tag-permission-details) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="af145-166">These permissions and their effect on quarantined messages and in end-user spam notifications are described in the [Quarantine tag permission details](#quarantine-tag-permission-details) section later in this article.</span></span>

   <span data-ttu-id="af145-167">完了したら、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="af145-167">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="af145-168">表示される **要約** ページで、設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="af145-168">On the **Summary** page that appears, review your settings.</span></span> <span data-ttu-id="af145-169">各設定で [ **編集** ] をクリックして、変更を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="af145-169">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="af145-170">完了したら、[ **送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="af145-170">When you're finished, click **Submit**.</span></span>

6. <span data-ttu-id="af145-171">表示される確認ページで [ **完了** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="af145-171">Click **Done** on the confirmation page that appears.</span></span>

<span data-ttu-id="af145-172">これで、[ [ステップ 2](#step-2-assign-a-quarantine-tag-to-supported-features) ] セクションに記載されているように、検疫タグを検疫機能に割り当てる準備ができました。</span><span class="sxs-lookup"><span data-stu-id="af145-172">Now you are ready to assign the quarantine tag to a quarantine feature as described in the [Step 2](#step-2-assign-a-quarantine-tag-to-supported-features) section.</span></span>

### <a name="create-quarantine-tags-in-powershell"></a><span data-ttu-id="af145-173">PowerShell で検疫タグを作成する</span><span class="sxs-lookup"><span data-stu-id="af145-173">Create quarantine tags in PowerShell</span></span>

<span data-ttu-id="af145-174">PowerShell を使用して検疫タグを作成する場合は、Exchange Online PowerShell または Exchange Online Protection PowerShell に接続して、 **QuarantineTag** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="af145-174">If you'd rather use PowerShell to create quarantine tags, connect to Exchange Online PowerShell or Exchange Online Protection PowerShell and use the **New-QuarantineTag** cmdlet.</span></span> <span data-ttu-id="af145-175">次の2種類の方法から選択できます。</span><span class="sxs-lookup"><span data-stu-id="af145-175">You have two different methods to choose from:</span></span>

- <span data-ttu-id="af145-176">_EndUserQuarantinePermissionsValue_ パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="af145-176">Use the _EndUserQuarantinePermissionsValue_ parameter.</span></span>
- <span data-ttu-id="af145-177">_EndUserQuarantinePermissions_ パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="af145-177">Use the _EndUserQuarantinePermissions_ parameter.</span></span>

<span data-ttu-id="af145-178">これらのメソッドについては、以下のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="af145-178">These methods are described in the following sections.</span></span>

#### <a name="use-the-enduserquarantinepermissionsvalue-parameter"></a><span data-ttu-id="af145-179">EndUserQuarantinePermissionsValue パラメーターを使用する</span><span class="sxs-lookup"><span data-stu-id="af145-179">Use the EndUserQuarantinePermissionsValue parameter</span></span>

<span data-ttu-id="af145-180">_EndUserQuarantinePermissionsValue_ パラメーターを使用して検疫タグを作成するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="af145-180">To create a quarantine tag using the _EndUserQuarantinePermissionsValue_ parameter, use the following syntax:</span></span>

```powershell
New-QuarantineTag -Name "<UniqueName>" -EndUserQuarantinePermissionsValue <0 to 236>
```

<span data-ttu-id="af145-181">_EndUserQuarantinePermissionsValue_ パラメーターは、バイナリ値から変換された10進数の値を使用します。</span><span class="sxs-lookup"><span data-stu-id="af145-181">The _EndUserQuarantinePermissionsValue_ parameter uses a decimal value that's converted from a binary value.</span></span> <span data-ttu-id="af145-182">Binary 値は、指定された順序で使用可能なエンドユーザーの検疫アクセス許可に対応します。</span><span class="sxs-lookup"><span data-stu-id="af145-182">The binary value corresponds to the available end-user quarantine permissions in a specific order.</span></span> <span data-ttu-id="af145-183">各アクセス許可について、値1は True になり、値0は False に等しくなります。</span><span class="sxs-lookup"><span data-stu-id="af145-183">For each permission, the value 1 equals True and the value 0 equals False.</span></span>

<span data-ttu-id="af145-184">次の表では、事前設定されたアクセス許可グループの各アクセス許可に必要な順序と値について説明します。</span><span class="sxs-lookup"><span data-stu-id="af145-184">The required order and values for each individual permission in preset permission groups are described in the following table:</span></span>

****

|<span data-ttu-id="af145-185">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="af145-185">Permission</span></span>|<span data-ttu-id="af145-186">アクセスなし</span><span class="sxs-lookup"><span data-stu-id="af145-186">No access</span></span>|<span data-ttu-id="af145-187">制限付きアクセス</span><span class="sxs-lookup"><span data-stu-id="af145-187">Limited access</span></span>|<span data-ttu-id="af145-188">フルアクセス</span><span class="sxs-lookup"><span data-stu-id="af145-188">Full access</span></span>|
|---|:---:|:---:|:---:|
|<span data-ttu-id="af145-189">PermissionToAllowSender</span><span class="sxs-lookup"><span data-stu-id="af145-189">PermissionToAllowSender</span></span>|<span data-ttu-id="af145-190">.0</span><span class="sxs-lookup"><span data-stu-id="af145-190">0</span></span>|<span data-ttu-id="af145-191">.0</span><span class="sxs-lookup"><span data-stu-id="af145-191">0</span></span>|<span data-ttu-id="af145-192">1 </span><span class="sxs-lookup"><span data-stu-id="af145-192">1</span></span>|
|<span data-ttu-id="af145-193">PermissionToBlockSender</span><span class="sxs-lookup"><span data-stu-id="af145-193">PermissionToBlockSender</span></span>|<span data-ttu-id="af145-194">.0</span><span class="sxs-lookup"><span data-stu-id="af145-194">0</span></span>|<span data-ttu-id="af145-195">1 </span><span class="sxs-lookup"><span data-stu-id="af145-195">1</span></span>|<span data-ttu-id="af145-196">1 </span><span class="sxs-lookup"><span data-stu-id="af145-196">1</span></span>|
|<span data-ttu-id="af145-197">PermissionToDelete</span><span class="sxs-lookup"><span data-stu-id="af145-197">PermissionToDelete</span></span>|<span data-ttu-id="af145-198">.0</span><span class="sxs-lookup"><span data-stu-id="af145-198">0</span></span>|<span data-ttu-id="af145-199">1 </span><span class="sxs-lookup"><span data-stu-id="af145-199">1</span></span>|<span data-ttu-id="af145-200">1 </span><span class="sxs-lookup"><span data-stu-id="af145-200">1</span></span>|
|<span data-ttu-id="af145-201">PermissionToDownload<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="af145-201">PermissionToDownload<sup>\*</sup></span></span>|<span data-ttu-id="af145-202">.0</span><span class="sxs-lookup"><span data-stu-id="af145-202">0</span></span>|<span data-ttu-id="af145-203">.0</span><span class="sxs-lookup"><span data-stu-id="af145-203">0</span></span>|<span data-ttu-id="af145-204">.0</span><span class="sxs-lookup"><span data-stu-id="af145-204">0</span></span>|
|<span data-ttu-id="af145-205">PermissionToPreview</span><span class="sxs-lookup"><span data-stu-id="af145-205">PermissionToPreview</span></span>|<span data-ttu-id="af145-206">.0</span><span class="sxs-lookup"><span data-stu-id="af145-206">0</span></span>|<span data-ttu-id="af145-207">1 </span><span class="sxs-lookup"><span data-stu-id="af145-207">1</span></span>|<span data-ttu-id="af145-208">1 </span><span class="sxs-lookup"><span data-stu-id="af145-208">1</span></span>|
|<span data-ttu-id="af145-209">PermissionToRelease<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="af145-209">PermissionToRelease<sup>\*\*</sup></span></span>|<span data-ttu-id="af145-210">.0</span><span class="sxs-lookup"><span data-stu-id="af145-210">0</span></span>|<span data-ttu-id="af145-211">.0</span><span class="sxs-lookup"><span data-stu-id="af145-211">0</span></span>|<span data-ttu-id="af145-212">1 </span><span class="sxs-lookup"><span data-stu-id="af145-212">1</span></span>|
|<span data-ttu-id="af145-213">PermissionToRequestRelease<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="af145-213">PermissionToRequestRelease<sup>\*\*</sup></span></span>|<span data-ttu-id="af145-214">.0</span><span class="sxs-lookup"><span data-stu-id="af145-214">0</span></span>|<span data-ttu-id="af145-215">1 </span><span class="sxs-lookup"><span data-stu-id="af145-215">1</span></span>|<span data-ttu-id="af145-216">.0</span><span class="sxs-lookup"><span data-stu-id="af145-216">0</span></span>|
|<span data-ttu-id="af145-217">PermissionToViewHeader<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="af145-217">PermissionToViewHeader<sup>\*</sup></span></span>|<span data-ttu-id="af145-218">.0</span><span class="sxs-lookup"><span data-stu-id="af145-218">0</span></span>|<span data-ttu-id="af145-219">.0</span><span class="sxs-lookup"><span data-stu-id="af145-219">0</span></span>|<span data-ttu-id="af145-220">.0</span><span class="sxs-lookup"><span data-stu-id="af145-220">0</span></span>|
|<span data-ttu-id="af145-221">バイナリ値</span><span class="sxs-lookup"><span data-stu-id="af145-221">Binary value</span></span>|<span data-ttu-id="af145-222">00000000</span><span class="sxs-lookup"><span data-stu-id="af145-222">00000000</span></span>|<span data-ttu-id="af145-223">01101010</span><span class="sxs-lookup"><span data-stu-id="af145-223">01101010</span></span>|<span data-ttu-id="af145-224">11101100</span><span class="sxs-lookup"><span data-stu-id="af145-224">11101100</span></span>|
|<span data-ttu-id="af145-225">使用する10進値</span><span class="sxs-lookup"><span data-stu-id="af145-225">Decimal value to use</span></span>|<span data-ttu-id="af145-226">.0</span><span class="sxs-lookup"><span data-stu-id="af145-226">0</span></span>|<span data-ttu-id="af145-227">106</span><span class="sxs-lookup"><span data-stu-id="af145-227">106</span></span>|<span data-ttu-id="af145-228">236</span><span class="sxs-lookup"><span data-stu-id="af145-228">236</span></span>|

<span data-ttu-id="af145-229"><sup>\*</sup> 現時点では、この値は常に0です。</span><span class="sxs-lookup"><span data-stu-id="af145-229"><sup>\*</sup> Currently, this value is always 0.</span></span> <span data-ttu-id="af145-230">PermissionToViewHeader の場合、値0を指定すると、検疫済みメッセージの詳細に [ **メッセージヘッダーの表示** ] ボタンが表示されません (ボタンは常に使用可能)。</span><span class="sxs-lookup"><span data-stu-id="af145-230">For PermissionToViewHeader, the value 0 doesn't hide the **View message header** button in the details of the quarantined message (the button is always available).</span></span>

<span data-ttu-id="af145-231"><sup>\*\*</sup> 両方の値を1に設定しないでください。</span><span class="sxs-lookup"><span data-stu-id="af145-231"><sup>\*\*</sup> Don't set both of these values to 1.</span></span> <span data-ttu-id="af145-232">1を1に設定し、もう一方を0に設定するか、または両方を0に設定します。</span><span class="sxs-lookup"><span data-stu-id="af145-232">Set one to 1 and the other to 0, or set both to 0.</span></span>

<span data-ttu-id="af145-233">この例では、前の表で説明されているアクセス許可を割り当てずに、新しい検疫タグ名 NoAccess を作成します。</span><span class="sxs-lookup"><span data-stu-id="af145-233">This example creates a new quarantine tag name NoAccess that assigns the No access permissions as described in the previous table.</span></span>

```powershell
New-QuarantineTag -Name NoAccess -EndUserQuarantinePermissionsValue 0
```

<span data-ttu-id="af145-234">制限付きアクセスのアクセス許可の場合は、値106を使用します。</span><span class="sxs-lookup"><span data-stu-id="af145-234">For Limited access permissions, use the value 106.</span></span> <span data-ttu-id="af145-235">フルアクセスのアクセス許可については、値236を使用します。</span><span class="sxs-lookup"><span data-stu-id="af145-235">For Full access permissions, use the value 236.</span></span>

<span data-ttu-id="af145-236">カスタムアクセス許可の場合、前の表を使用して、必要なアクセス許可に対応するバイナリ値を取得します。</span><span class="sxs-lookup"><span data-stu-id="af145-236">For custom permissions, use the previous table to get the binary value that corresponds to the permissions you want.</span></span> <span data-ttu-id="af145-237">Binary 値を10進値に変換し、 _EndUserQuarantinePermissionsValue_ パラメーターに10進数の値を使用します。</span><span class="sxs-lookup"><span data-stu-id="af145-237">Convert the binary value to a decimal value and use the decimal value for the _EndUserQuarantinePermissionsValue_ parameter.</span></span>

<span data-ttu-id="af145-238">構文およびパラメーターの詳細については、「 [QuarantineTag](https://docs.microsoft.com/powershell/module/exchange/new-quarantinetag)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="af145-238">For detailed syntax and parameter information, see [New-QuarantineTag](https://docs.microsoft.com/powershell/module/exchange/new-quarantinetag).</span></span>

#### <a name="use-the-enduserquarantinepermissions-parameter"></a><span data-ttu-id="af145-239">EndUserQuarantinePermissions パラメーターを使用する</span><span class="sxs-lookup"><span data-stu-id="af145-239">Use the EndUserQuarantinePermissions parameter</span></span>

<span data-ttu-id="af145-240">_EndUserQuarantinePermissionsValue_ パラメーターを使用して検疫タグを作成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="af145-240">To create a quarantine tag using the _EndUserQuarantinePermissionsValue_ parameter, do the following steps:</span></span>

<span data-ttu-id="af145-241">A.</span><span class="sxs-lookup"><span data-stu-id="af145-241">A.</span></span> <span data-ttu-id="af145-242">**QuarantinePermissions** コマンドレットを使用して、変数に検疫アクセス許可オブジェクトを格納します。</span><span class="sxs-lookup"><span data-stu-id="af145-242">Store a quarantine permissions object in a variable using the **New-QuarantinePermissions** cmdlet.</span></span>
<br/>
<span data-ttu-id="af145-243">B.</span><span class="sxs-lookup"><span data-stu-id="af145-243">B.</span></span> <span data-ttu-id="af145-244">変数は、 **QuarantineTag** コマンドの _EndUserQuarantinePermissions_ 値として使用します。</span><span class="sxs-lookup"><span data-stu-id="af145-244">Use the variable as the _EndUserQuarantinePermissions_ value in the **New-QuarantineTag** command.</span></span>

##### <a name="step-a-store-a-quarantine-permissions-object-in-a-variable"></a><span data-ttu-id="af145-245">手順 A: 検疫アクセス許可オブジェクトを変数に格納する</span><span class="sxs-lookup"><span data-stu-id="af145-245">Step A: Store a quarantine permissions object in a variable</span></span>

<span data-ttu-id="af145-246">次の構文を使用してください。</span><span class="sxs-lookup"><span data-stu-id="af145-246">Use the following syntax:</span></span>

```powershell
$<VariableName> = New-QuarantinePermissions [-PermissionToAllowSender <$true | $False>] [-PermissionToBlockSender <$true | $False>] [-PermissionToDelete <$true | $False>] [-PermissionToPreview <$true | $False>] [-PermissionToRelease <$true | $False>] [-PermissionToRequestRelease <$true | $False>]
```

<span data-ttu-id="af145-247">使用されていないパラメーターの既定値は `$false` であるため、値をに設定するパラメーターのみを使用する必要があり `$true` ます。</span><span class="sxs-lookup"><span data-stu-id="af145-247">The default value for any unused parameters is `$false`, so you only need to use the parameters where you want to set value to `$true`.</span></span>

<span data-ttu-id="af145-248">次の例は、事前設定されたアクセス許可グループに対応する permission オブジェクトを作成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="af145-248">The following examples show how to create permission objects that correspond to the preset permissions groups:</span></span>

- <span data-ttu-id="af145-249">**アクセス不可**:</span><span class="sxs-lookup"><span data-stu-id="af145-249">**No access**:</span></span>

  ```powershell
  $NoAccess = New-QuarantinePermissions
  ```

- <span data-ttu-id="af145-250">**限定的なアクセス**:</span><span class="sxs-lookup"><span data-stu-id="af145-250">**Limited access**:</span></span>

  ```powershell
  $LimitedAccess = New-QuarantinePermissions -PermissionToBlockSender $true -PermissionToDelete $true -PermissionToPreview $true -PermissionToRequestRelease $true
  ```

- <span data-ttu-id="af145-251">**フルアクセス**:</span><span class="sxs-lookup"><span data-stu-id="af145-251">**Full access**:</span></span>

  ```powershell
  $FullAccess = New-QuarantinePermissions -PermissionToAllowSender $true -PermissionToBlockSender $true -PermissionToDelete $true -PermissionToPreview $true -PermissionToRelease $true
  ```

<span data-ttu-id="af145-252">設定した値を表示するには、変数名をコマンドとして実行します (たとえば、コマンドを実行し `$NoAccess` ます)。</span><span class="sxs-lookup"><span data-stu-id="af145-252">To see the values that you've set, run the variable name as a command (for example, run the command `$NoAccess`).</span></span>

<span data-ttu-id="af145-253">カスタム権限の場合、 _PermissionToRelease_ パラメーターと _PermissionToRequestRelease_ パラメーターの両方をに設定しないで `$true` ください。</span><span class="sxs-lookup"><span data-stu-id="af145-253">For custom permissions, don't set both the _PermissionToRelease_ and _PermissionToRequestRelease_ parameters to `$true`.</span></span> <span data-ttu-id="af145-254">をに設定 `$true` してそのままにするか、のままにし `$false` `$false` ます。</span><span class="sxs-lookup"><span data-stu-id="af145-254">Set one to `$true` and leave the other as `$false`, or leave both as `$false`.</span></span>

<span data-ttu-id="af145-255">また、 **QuarantinePermissions** コマンドレットを使用して、以前に作成した後で使用する前に、既存のアクセス許可オブジェクト変数を変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="af145-255">You can also modify an existing permissions object variable after you create but before you use it by using the **Set-QuarantinePermissions** cmdlet.</span></span>

<span data-ttu-id="af145-256">構文およびパラメーターの詳細については、「 [QuarantinePermissions](https://docs.microsoft.com/powershell/module/exchange/new-quarantinepermissions) 」および「 [QuarantinePermissions](https://docs.microsoft.com/powershell/module/exchange/set-quarantinepermissions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="af145-256">For detailed syntax and parameter information, see [New-QuarantinePermissions](https://docs.microsoft.com/powershell/module/exchange/new-quarantinepermissions) and [Set-QuarantinePermissions](https://docs.microsoft.com/powershell/module/exchange/set-quarantinepermissions).</span></span>

##### <a name="step-b-use-the-variable-in-the-new-quarantinetag-command"></a><span data-ttu-id="af145-257">手順 B: New-QuarantineTag コマンドで変数を使用する</span><span class="sxs-lookup"><span data-stu-id="af145-257">Step B: Use the variable in the New-QuarantineTag command</span></span>

<span data-ttu-id="af145-258">アクセス許可オブジェクトを作成して変数に格納した後、次の **QuarantineTag** コマンドで _EndUserQuarantinePermission_ パラメーターの値として変数を使用します。</span><span class="sxs-lookup"><span data-stu-id="af145-258">After you've created and stored the permissions object in a variable, use the variable for the _EndUserQuarantinePermission_ parameter value in the following **New-QuarantineTag** command:</span></span>

```powershell
New-QuarantineTag -Name "<UniqueName>" -EndUserQuarantinePermissions $<VariableName>
```

<span data-ttu-id="af145-259">この例では、 `$LimitedAccess` 前の手順で説明して作成したアクセス許可オブジェクトを使用して、LimitedAccess という名前の新しい quarantine タグを作成します。</span><span class="sxs-lookup"><span data-stu-id="af145-259">This example creates a new quarantine tag named LimitedAccess using the `$LimitedAccess` permissions object that was described and created in the previous step.</span></span>

```powershell
New-QuarantineTag -Name LimitedAccess -EndUserQuarantinePermissions $LimitedAccess
```

<span data-ttu-id="af145-260">構文およびパラメーターの詳細については、「 [QuarantineTag](https://docs.microsoft.com/powershell/module/exchange/new-quarantinetag)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="af145-260">For detailed syntax and parameter information, see [New-QuarantineTag](https://docs.microsoft.com/powershell/module/exchange/new-quarantinetag).</span></span>

## <a name="step-2-assign-a-quarantine-tag-to-supported-features"></a><span data-ttu-id="af145-261">手順 2: サポートされている機能に検疫タグを割り当てる</span><span class="sxs-lookup"><span data-stu-id="af145-261">Step 2: Assign a quarantine tag to supported features</span></span>

<span data-ttu-id="af145-262">メッセージまたはファイルを検疫する、 _サポートされ_ ている保護機能 (自動または構成可能なアクションとして) では、検疫タグを利用可能な検疫アクションに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="af145-262">In _supported_ protection features that quarantine messages or files (automatically or as a configurable action), you can assign a quarantine tag to the available quarantine actions.</span></span> <span data-ttu-id="af145-263">次の表では、メッセージを検疫し、検疫タグを使用できるようにする機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="af145-263">Features that quarantine messages and the availability of quarantine tags are described in the following table:</span></span>

****

|<span data-ttu-id="af145-264">機能</span><span class="sxs-lookup"><span data-stu-id="af145-264">Feature</span></span>|<span data-ttu-id="af145-265">検疫タグはサポートされていますか?</span><span class="sxs-lookup"><span data-stu-id="af145-265">Quarantine tags supported?</span></span>|<span data-ttu-id="af145-266">使用される既定の検疫タグ</span><span class="sxs-lookup"><span data-stu-id="af145-266">Default quarantine tags used</span></span>|
|---|:---:|---|
|<span data-ttu-id="af145-267">[スパム対策ポリシー](configure-your-spam-filter-policies.md):</span><span class="sxs-lookup"><span data-stu-id="af145-267">[Anti-spam policies](configure-your-spam-filter-policies.md):</span></span> <ul><li><span data-ttu-id="af145-268">**スパム** (_SpamAction_)</span><span class="sxs-lookup"><span data-stu-id="af145-268">**Spam** (_SpamAction_)</span></span></li><li><span data-ttu-id="af145-269">**信頼度の高いスパム** (_HighConfidenceSpamAction_)</span><span class="sxs-lookup"><span data-stu-id="af145-269">**High confidence spam** (_HighConfidenceSpamAction_)</span></span></li><li><span data-ttu-id="af145-270">**フィッシング電子メール** (_PhishSpamAction_)</span><span class="sxs-lookup"><span data-stu-id="af145-270">**Phishing email** (_PhishSpamAction_)</span></span></li><li><span data-ttu-id="af145-271">**高信頼フィッシング電子メール** (_HighConfidencePhishAction_)</span><span class="sxs-lookup"><span data-stu-id="af145-271">**High confidence phishing email** (_HighConfidencePhishAction_)</span></span></li><li><span data-ttu-id="af145-272">**バルクメール** (_BulkSpamAction_)</span><span class="sxs-lookup"><span data-stu-id="af145-272">**Bulk email** (_BulkSpamAction_)</span></span></li></ul>|<span data-ttu-id="af145-273">必要</span><span class="sxs-lookup"><span data-stu-id="af145-273">Yes</span></span>|<ul><li><span data-ttu-id="af145-274">DefaultSpamTag (フルアクセス)</span><span class="sxs-lookup"><span data-stu-id="af145-274">DefaultSpamTag (Full access)</span></span></li><li><span data-ttu-id="af145-275">DefaultHighConfSpamTag (フルアクセス)</span><span class="sxs-lookup"><span data-stu-id="af145-275">DefaultHighConfSpamTag (Full access)</span></span></li><li><span data-ttu-id="af145-276">DefaultPhishTag (フルアクセス)</span><span class="sxs-lookup"><span data-stu-id="af145-276">DefaultPhishTag (Full access)</span></span></li><li><span data-ttu-id="af145-277">DefaultHighConfPhishTag (アクセス不可)</span><span class="sxs-lookup"><span data-stu-id="af145-277">DefaultHighConfPhishTag (No access)</span></span></li><li><span data-ttu-id="af145-278">DefaultBulkTag (フルアクセス)</span><span class="sxs-lookup"><span data-stu-id="af145-278">DefaultBulkTag (Full access)</span></span></li></ul>
|<span data-ttu-id="af145-279">フィッシング対策ポリシー:</span><span class="sxs-lookup"><span data-stu-id="af145-279">Anti-phishing policies:</span></span> <ul><li><span data-ttu-id="af145-280">[スプーフィングインテリジェンス保護](set-up-anti-phishing-policies.md#spoof-settings) (_authenticationfailaction_)</span><span class="sxs-lookup"><span data-stu-id="af145-280">[Spoof intelligence protection](set-up-anti-phishing-policies.md#spoof-settings) (_AuthenticationFailAction_)</span></span></li><li><span data-ttu-id="af145-281">[偽装保護](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365):<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="af145-281">[Impersonation protection](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365):<sup>\*</sup></span></span> <ul><li><span data-ttu-id="af145-282">**偽装ユーザーによって電子メールが送信される場合** (_targeteduserprotectionaction_)</span><span class="sxs-lookup"><span data-stu-id="af145-282">**If email is sent by an impersonated user** (_TargetedUserProtectionAction_)</span></span></li><li><span data-ttu-id="af145-283">**偽装ドメインによって電子メールが送信される場合** (_targeteddomainprotectionaction_)</span><span class="sxs-lookup"><span data-stu-id="af145-283">**If email is sent by an impersonated domain** (_TargetedDomainProtectionAction_)</span></span></li><li><span data-ttu-id="af145-284">**メールボックスインテリジェンス** \>**偽装ユーザーによって電子メールが送信される場合**(_MailboxIntelligenceProtectionAction_)</span><span class="sxs-lookup"><span data-stu-id="af145-284">**Mailbox intelligence** \> **If email is sent by an impersonated user** (_MailboxIntelligenceProtectionAction_)</span></span></li></ul></li></ul></ul>|<span data-ttu-id="af145-285">いいえ</span><span class="sxs-lookup"><span data-stu-id="af145-285">No</span></span>|<span data-ttu-id="af145-286">該当なし</span><span class="sxs-lookup"><span data-stu-id="af145-286">n/a</span></span>|
|<span data-ttu-id="af145-287">[マルウェア対策ポリシー](configure-anti-malware-policies.md): 検出されたすべてのメッセージが常に検疫されます。</span><span class="sxs-lookup"><span data-stu-id="af145-287">[Anti-malware policies](configure-anti-malware-policies.md): All detected messages are always quarantined.</span></span>|<span data-ttu-id="af145-288">いいえ</span><span class="sxs-lookup"><span data-stu-id="af145-288">No</span></span>|<span data-ttu-id="af145-289">該当なし</span><span class="sxs-lookup"><span data-stu-id="af145-289">n/a</span></span>|
|[<span data-ttu-id="af145-290">SharePoint、OneDrive、Microsoft Teams 用の ATP</span><span class="sxs-lookup"><span data-stu-id="af145-290">ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>](atp-for-spo-odb-and-teams.md)|<span data-ttu-id="af145-291">いいえ</span><span class="sxs-lookup"><span data-stu-id="af145-291">No</span></span>|<span data-ttu-id="af145-292">該当なし</span><span class="sxs-lookup"><span data-stu-id="af145-292">n/a</span></span>|
|<span data-ttu-id="af145-293">アクションを使用した [メールフロールール](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)(トランスポートルールとも呼ばれる): ホストされた検疫 (_検疫_)**にメッセージを配信** します。</span><span class="sxs-lookup"><span data-stu-id="af145-293">[Mail flow rules](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) with the action: **Deliver the message to the hosted quarantine** (_Quarantine_).</span></span>|<span data-ttu-id="af145-294">いいえ</span><span class="sxs-lookup"><span data-stu-id="af145-294">No</span></span>|<span data-ttu-id="af145-295">該当なし</span><span class="sxs-lookup"><span data-stu-id="af145-295">n/a</span></span>|
|

<span data-ttu-id="af145-296"><sup>\*</sup> 偽装保護の設定は、Microsoft Defender for Office 365 のフィッシング対策ポリシーでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="af145-296"><sup>\*</sup> Impersonation protection settings are available only in anti-phishing policies in Microsoft Defender for Office 365.</span></span>

<span data-ttu-id="af145-297">既定の検疫タグで提供されるエンドユーザーのアクセス許可に満足している場合は、何もする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="af145-297">If you're happy with the end-user permissions that are provided by the default quarantine tags, you don't need to do anything.</span></span> <span data-ttu-id="af145-298">エンドユーザーのスパム通知または検疫されたメッセージの詳細でエンドユーザー機能 (利用可能なボタン) をカスタマイズする場合は、カスタム検疫タグを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="af145-298">If you want to customize the end-user capabilities (available buttons) in end-user spam notifications or in quarantined message details, you can assign a custom quarantine tag.</span></span>

### <a name="assign-quarantine-tags-in-anti-spam-policies-in-the-security--compliance-center"></a><span data-ttu-id="af145-299">セキュリティ & コンプライアンスセンターのスパム対策ポリシーで検疫タグを割り当てる</span><span class="sxs-lookup"><span data-stu-id="af145-299">Assign quarantine tags in anti-spam policies in the Security & Compliance Center</span></span>

<span data-ttu-id="af145-300">スパム対策ポリシーを作成および変更する詳細な手順については、「 [CONFIGURE EOP」の「スパム対策ポリシーを構成](configure-your-spam-filter-policies.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="af145-300">Full instructions for creating and modifying anti-spam policies are described in [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

1. <span data-ttu-id="af145-301">[セキュリティ & コンプライアンスセンター] で、[ **脅威管理** \> **ポリシー** ] に移動し \> てから、[ **スパム対策**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="af145-301">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> and then select **Anti-spam**.</span></span> <span data-ttu-id="af145-302">または、を開き <https://protection.office.com/antispam> ます。</span><span class="sxs-lookup"><span data-stu-id="af145-302">Or, open <https://protection.office.com/antispam>.</span></span>

2. <span data-ttu-id="af145-303">編集する既存のスパム対策ポリシーを検索して選択するか、新しいスパム対策ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="af145-303">Find and select an existing anti-spam policy to edit, or create a new anti-spam policy.</span></span>

3. <span data-ttu-id="af145-304">ポリシーの詳細ポップアップで、[ **スパムと一括アクション** ] セクションを展開します。</span><span class="sxs-lookup"><span data-stu-id="af145-304">In the policy details flyout, expand the **Spam and bulk actions** section.</span></span>
  
4. <span data-ttu-id="af145-305">[利用可能なスパムフィルター処理] verdict のアクションに対して [ **検疫メッセージ** ] を選択した場合、[ **検疫ポリシータグを適用** します] ボックスを使用して、その verdict の検疫タグを選択できます。</span><span class="sxs-lookup"><span data-stu-id="af145-305">If you've selected **Quarantine message** for the action of an available spam filtering verdict, the **Apply quarantine policy tag** box is available for you to select the quarantine tag for that verdict.</span></span>

   <span data-ttu-id="af145-306">**注**: 新しいポリシーを作成すると、スパムフィルター verdict の空の検疫タグ値は、その verdict が使用されている既定の quarantine タグを示します。</span><span class="sxs-lookup"><span data-stu-id="af145-306">**Note**: When you create a new policy, a blank quarantine tag value for a spam filtering verdict indicates the default quarantine tag for that verdict is used.</span></span> <span data-ttu-id="af145-307">後でポリシーを編集すると、空の値は、前の表で説明したように、実際の既定の検査タグ名に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="af145-307">When you later edit the policy, the blank values are replaced by the actual default quarantine tag names as described in the previous table.</span></span>
  
   ![スパム対策ポリシーでのタグ選択の検疫](../../media/quarantine-tags-in-anti-spam-policies.png)

5. <span data-ttu-id="af145-309">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="af145-309">When you're finished, click **Save**.</span></span>

#### <a name="assign-quarantine-tags-in-anti-spam-policies-in-powershell"></a><span data-ttu-id="af145-310">PowerShell でスパム対策ポリシーの検疫タグを割り当てる</span><span class="sxs-lookup"><span data-stu-id="af145-310">Assign quarantine tags in anti-spam policies in PowerShell</span></span>

<span data-ttu-id="af145-311">PowerShell を使用してスパム対策ポリシーで検疫タグを割り当てる場合は、Exchange Online PowerShell または Exchange Online Protection PowerShell に接続し、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="af145-311">If you'd rather use PowerShell to assign quarantine tags in anti-spam policies, connect to Exchange Online PowerShell or Exchange Online Protection PowerShell and use the following syntax:</span></span>

```powershell
<New-HostedContentFilterPolicy -Name "<Unique name>" | Set-HostedContentFilterPolicy -Identity "<Policy name>">  [-SpamAction Quarantine] [-SpamQuarantineTag <QuarantineTagName>] [-HighConfidenceSpamAction Quarantine] [-HighConfidenceSpamQuarantineTag <QuarantineTagName>] [-PhishSpamAction Quarantine] [-PhishQuarantineTag <QuarantineTagName>] [-HighConfidencePhishQuarantineTag <QuarantineTagName>] [-BulkSpamAction Quarantine] [-BulkQuarantineTag <QuarantineTagName>] ...
```

<span data-ttu-id="af145-312">**注**:</span><span class="sxs-lookup"><span data-stu-id="af145-312">**Notes**:</span></span>

- <span data-ttu-id="af145-313">_HighConfidencePhishAction_ パラメーターの既定値は Quarantine なので、新しいスパム対策ポリシーで信頼度の高いフィッシングを検出するための検疫アクションを設定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="af145-313">The default value for the _HighConfidencePhishAction_ parameter is Quarantine, so you don't need to set the Quarantine action for high confidence phishing detections in new anti-spam policies.</span></span> <span data-ttu-id="af145-314">新規または既存のスパム対策ポリシーで、他のすべてのスパムフィルター verdicts の場合、検疫タグは、アクションの値が Quarantine の場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="af145-314">For all other spam filtering verdicts in new or existing anti-spam policies, the quarantine tag is only effective if the action value is Quarantine.</span></span> <span data-ttu-id="af145-315">既存のスパム対策ポリシーのアクション値を確認するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="af145-315">To see the action values in existing anti-spam policies, run the following command:</span></span>

  ```powershell
  Get-HostedContentFilterPolicy | Format-Table Name,*SpamAction,HighConfidencePhishAction
  ```

  <span data-ttu-id="af145-316">標準および厳密の既定のアクション値および推奨されるアクション値の詳細については、「 [EOP spam policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="af145-316">For information about the default action values and the recommended action values for Standard and Strict, see [EOP anti-spam policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings).</span></span>

- <span data-ttu-id="af145-317">スパムフィルター verdict に対応する quarantine タグパラメーターがない場合は、その verdict の [既定の quarantine タグ](#step-2-assign-a-quarantine-tag-to-supported-features) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="af145-317">A spam filtering verdict without a corresponding quarantine tag parameter means the [default quarantine tag](#step-2-assign-a-quarantine-tag-to-supported-features) for that verdict is used.</span></span>

  <span data-ttu-id="af145-318">検疫されたメッセージに対する既定のエンドユーザーの機能を変更する場合は、既定の検疫タグをカスタム検疫タグに置き換えるだけで済みます。</span><span class="sxs-lookup"><span data-stu-id="af145-318">You only need to replace a default quarantine tag with a custom quarantine tag if you want to change the default end-user capabilities on quarantined messages.</span></span>

- <span data-ttu-id="af145-319">PowerShell の新しいスパム対策ポリシーには、 **set-hostedcontentfilterpolicy** コマンドレットを使用したスパムフィルターポリシー (設定) と、 **disable-hostedcontentfilterrule** コマンドレットを使用する新しいスパムフィルタールール (受信者フィルター) が必要です。</span><span class="sxs-lookup"><span data-stu-id="af145-319">A new anti-spam policy in PowerShell requires a spam filter policy (settings) using the **New-HostedContentFilterPolicy** cmdlet and a new spam filter rule (recipient filters) using the **New-HostedContentFilterRule** cmdlet.</span></span> <span data-ttu-id="af145-320">手順については、「 [PowerShell を使用してスパム対策ポリシーを作成する](configure-your-spam-filter-policies.md#use-powershell-to-create-anti-spam-policies)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="af145-320">For instructions, see [Use PowerShell to create anti-spam policies](configure-your-spam-filter-policies.md#use-powershell-to-create-anti-spam-policies).</span></span>

<span data-ttu-id="af145-321">この例では、Research Department という名前の新しいスパムフィルターポリシーを次の設定で作成します。</span><span class="sxs-lookup"><span data-stu-id="af145-321">This example creates a new spam filter policy named Research Department with the following settings:</span></span>

- <span data-ttu-id="af145-322">すべてのスパムフィルタリング verdicts のアクションは、検疫に設定されます。</span><span class="sxs-lookup"><span data-stu-id="af145-322">The action for all spam filtering verdicts is set to Quarantine.</span></span>
- <span data-ttu-id="af145-323">**アクセス許可が** 割り当てられていない NoAccess という名前のカスタム検疫タグは、既定では、**アクセス許可が** 割り当てられていない既定の検疫タグに置き換わります。</span><span class="sxs-lookup"><span data-stu-id="af145-323">The custom quarantine tag named NoAccess that assigns **No access** permissions replaces any default quarantine tags that don't already assign **No access** permissions by default.</span></span>

```powershell
New-HostedContentFilterPolicy -Name Research Department -SpamAction Quarantine -SpamQuarantineTag NoAccess -HighConfidenceSpamAction Quarantine -HighConfidenceSpamQuarantineTag NoAction -PhishSpamAction Quarantine -PhishQuarantineTag NoAction -BulkSpamAction Quarantine -BulkQuarantineTag NoAccess
```

<span data-ttu-id="af145-324">構文とパラメーターの詳細については、「[New-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="af145-324">For detailed syntax and parameter information, see [New-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterpolicy).</span></span>

<span data-ttu-id="af145-325">この例では、人的リソースという名前の既存のスパムフィルターポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="af145-325">This example modifies the existing spam filter policy named Human Resources.</span></span> <span data-ttu-id="af145-326">スパム検疫 verdict のアクションは検疫に設定され、NoAccess という名前のカスタム検疫タグが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="af145-326">The action for the spam quarantine verdict is set to Quarantine, and the custom quarantine tag named NoAccess is assigned.</span></span>

```powershell
Set-HostedContentFilterPolicy -Identity "Human Resources" -SpamAction Quarantine -SpamQuarantineTag NoAccess
```

<span data-ttu-id="af145-327">構文とパラメーターの詳細については、「[Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedcontentfilterpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="af145-327">For detailed syntax and parameter information, see [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedcontentfilterpolicy).</span></span>

## <a name="configure-global-quarantine-notification-settings-in-the-security--compliance-center"></a><span data-ttu-id="af145-328">セキュリティ & コンプライアンスセンターでのグローバル検疫通知設定の構成</span><span class="sxs-lookup"><span data-stu-id="af145-328">Configure global quarantine notification settings in the Security & Compliance Center</span></span>

<span data-ttu-id="af145-329">検疫タグのグローバル設定を使用すると、検疫されたメッセージの受信者に送信されるエンドユーザーのスパム通知をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="af145-329">The global settings for quarantine tags allow you to customize the end-user spam notifications that are sent to recipients of messages that were quarantined.</span></span> <span data-ttu-id="af145-330">これらの通知の詳細については、「 [エンドユーザーのスパム通知](use-spam-notifications-to-release-and-report-quarantined-messages.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="af145-330">For more information about these notifications, see [End-user spam notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

1. <span data-ttu-id="af145-331">セキュリティ & コンプライアンスセンターで、[ **脅威管理** \> **ポリシー** ] に移動し、[ **タグの検疫**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="af145-331">In the Security & Compliance Center, go to **Threat management** \> **Policy** and then select **Quarantine tags**.</span></span>

2. <span data-ttu-id="af145-332">[ **タグの検疫** ] ページで、[ **グローバル設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="af145-332">On the **Quarantine tags** page, select **Global settings**.</span></span>

3. <span data-ttu-id="af145-333">[ **検疫通知の設定** ] ポップアップが表示されたら、次の設定の一部または全部を構成します。</span><span class="sxs-lookup"><span data-stu-id="af145-333">In the **Quarantine notification settings** flyout that opens, configure some or all of the following settings:</span></span>

   - <span data-ttu-id="af145-334">**会社のロゴを使用** する: エンドユーザーのスパム通知の上位で使用されている既定の Microsoft ロゴを置き換えるには、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="af145-334">**Use my company logo**: Select this option to replace the default Microsoft logo that's use at the top of end-user spam notifications.</span></span> <span data-ttu-id="af145-335">この手順を実行する前に、「 [Microsoft 365 テーマをカスタマイズ](https://docs.microsoft.com/microsoft-365/admin/setup/customize-your-organization-theme) する」の「カスタムロゴをアップロードするには」の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="af145-335">Before you do this, you need to follow the instructions in [Customize the Microsoft 365 theme for your organization](https://docs.microsoft.com/microsoft-365/admin/setup/customize-your-organization-theme) to upload your custom logo.</span></span>

     <span data-ttu-id="af145-336">次のスクリーンショットは、エンドユーザーのスパム通知のカスタムロゴを示しています。</span><span class="sxs-lookup"><span data-stu-id="af145-336">The following screenshot shows a custom logo in an end-user spam notification:</span></span>

     ![エンドユーザーのスパム通知のカスタムロゴ](../../media/quarantine-tags-esn-customization-logo.png)

   - <span data-ttu-id="af145-338">**言語の選択**: エンドユーザーのスパム通知は、受信者の言語設定に基づいて既にローカライズされています。</span><span class="sxs-lookup"><span data-stu-id="af145-338">**Choose language**: End-user spam notifications are already localized based on the recipient's language settings.</span></span> <span data-ttu-id="af145-339">[ **表示名** ] と [ **免責事項** ] の値に対して、カスタマイズしたテキストをさまざまな言語で指定できます。</span><span class="sxs-lookup"><span data-stu-id="af145-339">You can specify customized text in different languages for the **Display name** and **Disclaimer** values.</span></span>

     <span data-ttu-id="af145-340">[最初の言語] ボックスから少なくとも1つの言語を選択し、[ **追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="af145-340">Select at least one language from the first language box and then click **Add**.</span></span> <span data-ttu-id="af145-341">複数の言語を選択するには、1つずつ [ **追加** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="af145-341">You can select multiple languages by clicking **Add** after each one.</span></span> <span data-ttu-id="af145-342">セクションの言語ボックスに、選択したすべての言語が表示されます。</span><span class="sxs-lookup"><span data-stu-id="af145-342">A section language box shows all of the languages that you've selected:</span></span>

     ![検疫タグのグローバル検疫通知設定の [2 番目の言語] ボックスで選択されている言語](../../media/quarantine-tags-esn-customization-selected-languages.png)

   - <span data-ttu-id="af145-344">[**表示名**: エンドユーザーのスパム通知で使用される送信者の表示名をカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="af145-344">**Display name**: Customize the sender's display name that's used in end-user spam notifications.</span></span>

     <span data-ttu-id="af145-345">追加した言語ごとに、[2 番目の言語] ボックス ([X] をクリックしない) で言語を選択し、[ **表示名** ] ボックスに必要なテキスト値を入力します。</span><span class="sxs-lookup"><span data-stu-id="af145-345">For each language that you've added, select the language in the second language box (don't click on the X) and enter the text value you want in the **Display name** box.</span></span>

     <span data-ttu-id="af145-346">次のスクリーンショットは、エンドユーザーのスパム通知のカスタマイズされた表示名を示しています。</span><span class="sxs-lookup"><span data-stu-id="af145-346">The following screenshot shows the customized display name in an end-user spam notification:</span></span>

     ![エンドユーザーのスパム通知にカスタマイズされた送信者の表示名](../../media/quarantine-tags-esn-customization-display-name.png)

   - <span data-ttu-id="af145-348">**免責** 事項: エンドユーザーのスパム通知の下にカスタムの免責事項を追加します。</span><span class="sxs-lookup"><span data-stu-id="af145-348">**Disclaimer**: Add a custom disclaimer to the bottom of end-user spam notifications.</span></span> <span data-ttu-id="af145-349">ローカライズされたテキスト、 **組織からの免責事項** は常に最初に含まれ、その後に指定するテキストが続きます。</span><span class="sxs-lookup"><span data-stu-id="af145-349">The localized text, **A disclaimer from your organization:** is always included first, followed by the text you specify.</span></span>

     <span data-ttu-id="af145-350">追加した言語ごとに、[2 番目の言語] ボックス ([X] をクリックしないでください) の言語を選択し、[ **免責事項** ] ボックスに必要なテキスト値を入力します。</span><span class="sxs-lookup"><span data-stu-id="af145-350">For each language that you've added, select the language in the second language box  (don't click the X) and enter the text value you want in the **Disclaimer** box.</span></span>

     <span data-ttu-id="af145-351">次のスクリーンショットは、エンドユーザーのスパム通知のカスタマイズされた免責事項を示しています。</span><span class="sxs-lookup"><span data-stu-id="af145-351">The following screenshot shows the customized disclaimer in an end-user spam notification:</span></span>

     ![エンドユーザーのスパム通知の下部にあるカスタム免責事項](../../media/quarantine-tags-esn-customization-disclaimer.png)

## <a name="view-quarantine-tags-in-the-security--compliance-center"></a><span data-ttu-id="af145-353">セキュリティ & コンプライアンスセンターの検疫タグを表示する</span><span class="sxs-lookup"><span data-stu-id="af145-353">View quarantine tags in the Security & Compliance Center</span></span>

1. <span data-ttu-id="af145-354">セキュリティ & コンプライアンスセンターで、[ **脅威管理** \> **ポリシー** ] に移動し、[ **タグの検疫**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="af145-354">In the Security & Compliance Center, go to **Threat management** \> **Policy** and then select **Quarantine tags**.</span></span>

- <span data-ttu-id="af145-355">組み込みまたはカスタムの検疫タグの設定を表示するには、リストから [quarantine] タグを選択します (チェックボックスをオンにしないでください)。</span><span class="sxs-lookup"><span data-stu-id="af145-355">To view the settings of built-in or custom quarantine tags, select the quarantine tag from the list (don't select the check box).</span></span>

- <span data-ttu-id="af145-356">グローバル設定を表示するには、[**グローバル設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="af145-356">To view the global settings, select **Global settings**</span></span>

### <a name="view-quarantine-tags-in-powershell"></a><span data-ttu-id="af145-357">PowerShell で検疫タグを表示する</span><span class="sxs-lookup"><span data-stu-id="af145-357">View quarantine tags in PowerShell</span></span>

<span data-ttu-id="af145-358">PowerShell を使用して検疫タグを表示する場合は、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="af145-358">If you'd rather use PowerShell to view quarantine tags, do any of the following steps:</span></span>

- <span data-ttu-id="af145-359">すべての組み込みまたはカスタムタグの要約リストを表示するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="af145-359">To view a summary list of all built-in or custom tags, run the following command:</span></span>

  ```powershell
  Get-QuarantineTag | Format-Table Name
  ```

- <span data-ttu-id="af145-360">組み込みまたはカスタムの検疫タグの設定を表示するには、を \<TagName\> quarantine タグの名前に置き換えて、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="af145-360">To view the settings of built-in or custom quarantine tags, replace \<TagName\> with the name of the quarantine tag, and run the following command:</span></span>

  ```powershell
  Get-QuarantineTag -Identity "<TagName>"
  ```

- <span data-ttu-id="af145-361">グローバル設定を表示するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="af145-361">To view the global settings, run the following command:</span></span>

  ```powershell
  Get-QuarantineTag -QuarantineTagType GlobalQuarantineTag
  ```

<span data-ttu-id="af145-362">構文とパラメーターの詳細については、「[Get-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedcontentfilterpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="af145-362">For detailed syntax and parameter information, see [Get-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedcontentfilterpolicy).</span></span>

## <a name="remove-quarantine-tags-in-the-security--compliance-center"></a><span data-ttu-id="af145-363">セキュリティ & コンプライアンスセンターで検疫タグを削除する</span><span class="sxs-lookup"><span data-stu-id="af145-363">Remove quarantine tags in the Security & Compliance Center</span></span>

<span data-ttu-id="af145-364">**注**:</span><span class="sxs-lookup"><span data-stu-id="af145-364">**Notes**:</span></span>

- <span data-ttu-id="af145-365">組み込みの検疫タグを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="af145-365">You can't remove built-in quarantine tags.</span></span>

- <span data-ttu-id="af145-366">カスタム検疫タグを削除する前に、そのタグが使用されていないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="af145-366">Before you remove a custom quarantine tag, verify that it's not being used.</span></span> <span data-ttu-id="af145-367">たとえば、PowerShell で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="af145-367">For example, run the following command in PowerShell:</span></span>

  ```powershell
  Get-HostedContentFilterPolicy | Format-List Name,*QuarantineTag
  ```

  <span data-ttu-id="af145-368">検疫タグが使用されている場合は、削除する前に、 [割り当てられている検疫タグを置き換え](#step-2-assign-a-quarantine-tag-to-supported-features) ます。</span><span class="sxs-lookup"><span data-stu-id="af145-368">If the quarantine tag is being used, [replace the assigned quarantine tag](#step-2-assign-a-quarantine-tag-to-supported-features) before you remove it.</span></span>

1. <span data-ttu-id="af145-369">セキュリティ & コンプライアンスセンターで、[ **脅威管理** \> **ポリシー** ] に移動し、[ **タグの検疫**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="af145-369">In the Security & Compliance Center, go to **Threat management** \> **Policy** and then select **Quarantine tags**.</span></span>

2. <span data-ttu-id="af145-370">[ **タグの検疫** ] ページで、削除するカスタム検疫タグを選択し、[ **削除タグ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="af145-370">On the **Quarantine tags** page, select the custom quarantine tag that you want to remove, and the click **Delete tag**.</span></span>

3. <span data-ttu-id="af145-371">表示される確認ダイアログで、[ **タグの削除** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="af145-371">Click **Remove tag** in the confirmation dialog that appears.</span></span>

### <a name="remove-quarantine-tags-in-powershell"></a><span data-ttu-id="af145-372">PowerShell で検疫タグを削除する</span><span class="sxs-lookup"><span data-stu-id="af145-372">Remove quarantine tags in PowerShell</span></span>

<span data-ttu-id="af145-373">PowerShell を使用してカスタム検疫タグを削除する場合は、を \<TagName\> quarantine タグの名前に置き換えて、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="af145-373">If you'd rather use PowerShell to remove a custom quarantine tag, replace \<TagName\> with the name of the quarantine tag, and run the following command:</span></span>

```powershell
Remove-QuarantineTag -Identity "<TagName>"
```

<span data-ttu-id="af145-374">構文およびパラメーターの詳細については、「 [QuarantineTag](https://docs.microsoft.com/powershell/module/exchange/remove-quarantinetag)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="af145-374">For detailed syntax and parameter information, see [Remove-QuarantineTag](https://docs.microsoft.com/powershell/module/exchange/remove-quarantinetag).</span></span>

## <a name="quarantine-tag-permission-details"></a><span data-ttu-id="af145-375">検疫タグのアクセス許可の詳細</span><span class="sxs-lookup"><span data-stu-id="af145-375">Quarantine tag permission details</span></span>

<span data-ttu-id="af145-376">次のセクションでは、事前設定されたメッセージとエンドユーザーのスパム通知の詳細に対する、事前設定されたアクセス許可グループと個々のアクセス許可の影響について説明します。</span><span class="sxs-lookup"><span data-stu-id="af145-376">The following sections describe the effects of preset permission groups and individual permissions in the details of quarantined messages and in end-user spam notifications.</span></span>

### <a name="preset-permissions-groups"></a><span data-ttu-id="af145-377">事前設定のアクセス許可グループ</span><span class="sxs-lookup"><span data-stu-id="af145-377">Preset permissions groups</span></span>

<span data-ttu-id="af145-378">事前設定されたアクセス許可グループに含まれる個々のアクセス許可を、この記事の冒頭の表に示します。</span><span class="sxs-lookup"><span data-stu-id="af145-378">The individual permissions that are included in preset permission groups are listed in the table at the beginning of this article.</span></span>

#### <a name="no-access"></a><span data-ttu-id="af145-379">アクセスなし</span><span class="sxs-lookup"><span data-stu-id="af145-379">No access</span></span>

<span data-ttu-id="af145-380">検疫タグが **アクセス許可なし** (アクセス許可なし) に割り当てられている場合でも、ユーザーには依然としていくつかの基準機能があります。</span><span class="sxs-lookup"><span data-stu-id="af145-380">If the quarantine tag assigns the **No access** permissions (no permissions), users still get some baseline capabilities:</span></span>

- <span data-ttu-id="af145-381">**検疫済みメッセージの詳細**: [ **メッセージヘッダーの表示** ] ボタンは常に使用可能です。</span><span class="sxs-lookup"><span data-stu-id="af145-381">**Quarantined message details**: The **View message header** button is always available.</span></span>

  ![検疫タグによってユーザーにアクセス許可が付与されていない場合に、検疫済みメッセージの詳細で使用可能なボタン](../../media/quarantine-tags-quarantined-message-details-no-access.png)

- <span data-ttu-id="af145-383">**エンドユーザーのスパム通知**: 検疫中にユーザーにメッセージを表示する [ **確認** ] ボタンを常に使用できます。</span><span class="sxs-lookup"><span data-stu-id="af145-383">**End-user spam notifications**: The **Review** button that takes the user to the message in quarantine is always available.</span></span>

  ![検疫タグでユーザーにアクセス許可が与えられていない場合、エンドユーザーのスパム通知で使用可能なボタン](../../media/quarantine-tags-esn-no-access.png)

#### <a name="limited-access"></a><span data-ttu-id="af145-385">制限付きアクセス</span><span class="sxs-lookup"><span data-stu-id="af145-385">Limited access</span></span>

<span data-ttu-id="af145-386">検疫タグに **制限付きアクセス** のアクセス許可が割り当てられている場合、ユーザーは次の機能を利用できます。</span><span class="sxs-lookup"><span data-stu-id="af145-386">If the quarantine tag assigns the **Limited access** permissions, users get the following capabilities:</span></span>

- <span data-ttu-id="af145-387">**検疫済みメッセージの詳細**: 次のボタンを使用できます。</span><span class="sxs-lookup"><span data-stu-id="af145-387">**Quarantined message details**: The following buttons are available:</span></span>
  - <span data-ttu-id="af145-388">**リリースの依頼**</span><span class="sxs-lookup"><span data-stu-id="af145-388">**Request release**</span></span>
  - <span data-ttu-id="af145-389">**メッセージヘッダーを表示する**</span><span class="sxs-lookup"><span data-stu-id="af145-389">**View message header**</span></span>
  - <span data-ttu-id="af145-390">**プレビューメッセージ**</span><span class="sxs-lookup"><span data-stu-id="af145-390">**Preview message**</span></span>
  - <span data-ttu-id="af145-391">**受信拒否**</span><span class="sxs-lookup"><span data-stu-id="af145-391">**Block sender**</span></span>
  - <span data-ttu-id="af145-392">**検疫から削除する**</span><span class="sxs-lookup"><span data-stu-id="af145-392">**Remove from quarantine**</span></span>

  ![検疫タグによってユーザーに制限付きアクセスのアクセス許可が付与されている場合に、検疫済みメッセージの詳細で使用可能なボタン](../../media/quarantine-tags-quarantined-message-details-limited-access.png)

- <span data-ttu-id="af145-394">**エンドユーザーのスパム通知**: 次のボタンが使用できます。</span><span class="sxs-lookup"><span data-stu-id="af145-394">**End-user spam notifications**: The following buttons are available:</span></span>
  - <span data-ttu-id="af145-395">**受信拒否**</span><span class="sxs-lookup"><span data-stu-id="af145-395">**Block sender**</span></span>
  - <span data-ttu-id="af145-396">**確認**</span><span class="sxs-lookup"><span data-stu-id="af145-396">**Review**</span></span>

  ![検疫タグでユーザーに制限付きアクセスのアクセス許可が付与されている場合、エンドユーザーのスパム通知で使用可能なボタン](../../media/quarantine-tags-esn-limited-access.png)

#### <a name="full-access"></a><span data-ttu-id="af145-398">フルアクセス</span><span class="sxs-lookup"><span data-stu-id="af145-398">Full access</span></span>

<span data-ttu-id="af145-399">検疫タグによって **フルアクセス** のアクセス許可 (利用可能なすべてのアクセス許可) が割り当てられている場合、ユーザーは次の機能を利用できます。</span><span class="sxs-lookup"><span data-stu-id="af145-399">If the quarantine tag assigns the **Full access** permissions (all available permissions), users get the following capabilities:</span></span>

- <span data-ttu-id="af145-400">**検疫済みメッセージの詳細**: 次のボタンを使用できます。</span><span class="sxs-lookup"><span data-stu-id="af145-400">**Quarantined message details**: The following buttons are available:</span></span>
  - <span data-ttu-id="af145-401">**メッセージを解放する**</span><span class="sxs-lookup"><span data-stu-id="af145-401">**Release message**</span></span>
  - <span data-ttu-id="af145-402">**メッセージヘッダーを表示する**</span><span class="sxs-lookup"><span data-stu-id="af145-402">**View message header**</span></span>
  - <span data-ttu-id="af145-403">**プレビューメッセージ**</span><span class="sxs-lookup"><span data-stu-id="af145-403">**Preview message**</span></span>
  - <span data-ttu-id="af145-404">**受信拒否**</span><span class="sxs-lookup"><span data-stu-id="af145-404">**Block sender**</span></span>
  - <span data-ttu-id="af145-405">**送信者を許可する**</span><span class="sxs-lookup"><span data-stu-id="af145-405">**Allow sender**</span></span>
  - <span data-ttu-id="af145-406">**検疫から削除する**</span><span class="sxs-lookup"><span data-stu-id="af145-406">**Remove from quarantine**</span></span>

  ![検疫タグによってユーザーにフルアクセスのアクセス許可が付与されている場合に、検疫済みメッセージの詳細で使用可能なボタン](../../media/quarantine-tags-quarantined-message-details-full-access.png)

- <span data-ttu-id="af145-408">**エンドユーザーのスパム通知**: 次のボタンが使用できます。</span><span class="sxs-lookup"><span data-stu-id="af145-408">**End-user spam notifications**: The following buttons are available:</span></span>
  - <span data-ttu-id="af145-409">**受信拒否**</span><span class="sxs-lookup"><span data-stu-id="af145-409">**Block sender**</span></span>
  - <span data-ttu-id="af145-410">**Release**</span><span class="sxs-lookup"><span data-stu-id="af145-410">**Release**</span></span>
  - <span data-ttu-id="af145-411">**確認**</span><span class="sxs-lookup"><span data-stu-id="af145-411">**Review**</span></span>

  ![検疫タグでユーザーにフルアクセスのアクセス許可が付与されている場合、エンドユーザーのスパム通知で使用可能なボタン](../../media/quarantine-tags-esn-full-access.png)

### <a name="individual-permissions"></a><span data-ttu-id="af145-413">個別のアクセス許可</span><span class="sxs-lookup"><span data-stu-id="af145-413">Individual permissions</span></span>

> [!NOTE]
> <span data-ttu-id="af145-414">ユーザーが [ [アクセス不可](#no-access) ] セクションに表示されているボタンを常に取得することを覚えておいてください。</span><span class="sxs-lookup"><span data-stu-id="af145-414">Remember, users always get the buttons described in the [No access](#no-access) section.</span></span> <span data-ttu-id="af145-415">これらのボタンは、個々のアクセス許可の説明には含まれません。</span><span class="sxs-lookup"><span data-stu-id="af145-415">These buttons are not included in the individual permission descriptions.</span></span>

#### <a name="allow-sender-permission"></a><span data-ttu-id="af145-416">送信者のアクセス許可を許可する</span><span class="sxs-lookup"><span data-stu-id="af145-416">Allow sender permission</span></span>

<span data-ttu-id="af145-417">**送信者** のアクセス許可 (_Permissiontoallowsender_) はボタンへのアクセスを制御します。これにより、ユーザーは検疫済みメッセージ送信者を安全な差出人のリストに簡単に追加できます。</span><span class="sxs-lookup"><span data-stu-id="af145-417">The **Allow sender** permission (_PermissionToAllowSender_) controls access to the button that allows users to conveniently add the quarantined message sender to their Safe Senders list.</span></span>

- <span data-ttu-id="af145-418">**検疫済みメッセージの詳細**:</span><span class="sxs-lookup"><span data-stu-id="af145-418">**Quarantined message details**:</span></span>
  - <span data-ttu-id="af145-419">[送信者アクセス許可を有効に **する**]: [**送信者を許可** する] ボタンを使用できます。</span><span class="sxs-lookup"><span data-stu-id="af145-419">**Allow sender** permission enabled: The **Allow sender** button is available.</span></span>
  - <span data-ttu-id="af145-420">[**送信者** のアクセス許可を無効にする]: [**送信者を許可** する] ボタンは使用できません。</span><span class="sxs-lookup"><span data-stu-id="af145-420">**Allow sender** permission disabled: The **Allow sender** button is not available.</span></span>

- <span data-ttu-id="af145-421">**エンドユーザーのスパム通知**: 効果なし。</span><span class="sxs-lookup"><span data-stu-id="af145-421">**End-user spam notifications**: No effect.</span></span>

<span data-ttu-id="af145-422">差出人セーフリストの詳細については、「 [信頼された送信者からのブロックを禁止](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379666) する」と「 [Exchange Online PowerShell を使用してメールボックスのセーフリストコレクションを構成する](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="af145-422">For more information about the Safe Senders list, see [Prevent trusted senders from being blocked](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379666) and [Use Exchange Online PowerShell to configure the safelist collection on a mailbox](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox).</span></span>

#### <a name="block-sender-permission"></a><span data-ttu-id="af145-423">送信者のアクセス許可をブロックする</span><span class="sxs-lookup"><span data-stu-id="af145-423">Block sender permission</span></span>

<span data-ttu-id="af145-424">**送信者のブロック** アクセス許可 (_Permissiontoblocksender_) は、ユーザーが検疫済みメッセージ送信者を受信拒否リストに簡単に追加できるようにするボタンへのアクセスを制御します。</span><span class="sxs-lookup"><span data-stu-id="af145-424">The **Block sender** permission (_PermissionToBlockSender_) controls access to the button that allows users to conveniently add the quarantined message sender to their Blocked Senders list.</span></span>

- <span data-ttu-id="af145-425">**検疫済みメッセージの詳細**:</span><span class="sxs-lookup"><span data-stu-id="af145-425">**Quarantined message details**:</span></span>
  - <span data-ttu-id="af145-426">[**送信者のブロック**] アクセス許可を有効にする: [送信者を **ブロック** する] ボタンを使用できます。</span><span class="sxs-lookup"><span data-stu-id="af145-426">**Block sender** permission enabled: The **Block sender** button is available.</span></span>
  - <span data-ttu-id="af145-427">[**送信者のブロック**] アクセス許可を無効にする: [送信者を **ブロック** する] ボタンは使用できません。</span><span class="sxs-lookup"><span data-stu-id="af145-427">**Block sender** permission disabled: The **Block sender** button is not available.</span></span>

- <span data-ttu-id="af145-428">**エンドユーザーのスパム通知**:</span><span class="sxs-lookup"><span data-stu-id="af145-428">**End-user spam notifications**:</span></span>
  - <span data-ttu-id="af145-429">[**送信者のブロック**] アクセス許可を無効にする: [送信者を **ブロック** する] ボタンは使用できません。</span><span class="sxs-lookup"><span data-stu-id="af145-429">**Block sender** permission disabled: The **Block sender** button is not available.</span></span>
  - <span data-ttu-id="af145-430">[**送信者のブロック**] アクセス許可を有効にする: [送信者を **ブロック** する] ボタンを使用できます。</span><span class="sxs-lookup"><span data-stu-id="af145-430">**Block sender** permission enabled: The **Block sender** button is available.</span></span>

<span data-ttu-id="af145-431">受信拒否リストの詳細については、「 [ユーザーからのメッセージをブロック](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379667) する」と「 [Exchange Online の PowerShell を使用してメールボックスのセーフリストコレクションを構成する](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="af145-431">For more information about the Blocked Senders list, see [Block messages from someone](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379667) and [Use Exchange Online PowerShell to configure the safelist collection on a mailbox](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox).</span></span>

#### <a name="delete-permission"></a><span data-ttu-id="af145-432">アクセス許可を削除する</span><span class="sxs-lookup"><span data-stu-id="af145-432">Delete permission</span></span>

<span data-ttu-id="af145-433">**Delete** アクセス許可 (_PermissionToDelete_) は、検疫からユーザーが自分のメッセージ (ユーザーが受信者であるメッセージ) を削除する機能を制御します。</span><span class="sxs-lookup"><span data-stu-id="af145-433">The **Delete** permission (_PermissionToDelete_) controls the ability to of users to delete their messages (messages where the user is a recipient) from quarantine.</span></span>

- <span data-ttu-id="af145-434">**検疫済みメッセージの詳細**:</span><span class="sxs-lookup"><span data-stu-id="af145-434">**Quarantined message details**:</span></span>
  - <span data-ttu-id="af145-435">[**削除**] アクセス許可が有効: [**検疫から削除**] ボタンを使用できます。</span><span class="sxs-lookup"><span data-stu-id="af145-435">**Delete** permission enabled: The **Remove from quarantine** button is available.</span></span>
  - <span data-ttu-id="af145-436">**削除** 権限が無効: [ **検疫から削除** ] ボタンは使用できません。</span><span class="sxs-lookup"><span data-stu-id="af145-436">**Delete** permission disabled: The **Remove from quarantine** button is not available.</span></span>

- <span data-ttu-id="af145-437">**エンドユーザーのスパム通知**: 効果なし。</span><span class="sxs-lookup"><span data-stu-id="af145-437">**End-user spam notifications**: No effect.</span></span>

#### <a name="preview-permission"></a><span data-ttu-id="af145-438">プレビューのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="af145-438">Preview permission</span></span>

<span data-ttu-id="af145-439">**プレビュー** アクセス許可 (_permissiontopreview_) は、ユーザーが検疫でメッセージをプレビューできるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="af145-439">The **Preview** permission (_PermissionToPreview_) controls the ability to of users to preview their messages in quarantine.</span></span>

- <span data-ttu-id="af145-440">**検疫済みメッセージの詳細**:</span><span class="sxs-lookup"><span data-stu-id="af145-440">**Quarantined message details**:</span></span>
  - <span data-ttu-id="af145-441">**プレビュー** 権限が有効: [ **メッセージのプレビュー** ] ボタンを使用できます。</span><span class="sxs-lookup"><span data-stu-id="af145-441">**Preview** permission enabled: The **Preview message** button is available.</span></span>
  - <span data-ttu-id="af145-442">**プレビュー** アクセス許可が無効: [ **メッセージのプレビュー** ] ボタンは使用できません。</span><span class="sxs-lookup"><span data-stu-id="af145-442">**Preview** permission disabled: The **Preview message** button is not available.</span></span>

- <span data-ttu-id="af145-443">**エンドユーザーのスパム通知**: 効果なし。</span><span class="sxs-lookup"><span data-stu-id="af145-443">**End-user spam notifications**: No effect.</span></span>

#### <a name="allow-recipients-to-release-a-message-from-quarantine-permission"></a><span data-ttu-id="af145-444">受信者に検疫アクセス許可からメッセージを解放することを許可する</span><span class="sxs-lookup"><span data-stu-id="af145-444">Allow recipients to release a message from quarantine permission</span></span>

<span data-ttu-id="af145-445">[ **受信者に検疫のメッセージを解放することを許可する** ] (_PermissionToRelease_) は、ユーザーが、管理者の承認なしに、検疫済みメッセージを直接解放する機能を制御します。</span><span class="sxs-lookup"><span data-stu-id="af145-445">The **Allow recipients to release a message from quarantine** permission (_PermissionToRelease_) controls the ability of users to release their quarantined messages directly and without the approval of an admin.</span></span>

- <span data-ttu-id="af145-446">**検疫済みメッセージの詳細**:</span><span class="sxs-lookup"><span data-stu-id="af145-446">**Quarantined message details**:</span></span>
  - <span data-ttu-id="af145-447">アクセス許可: [ **メッセージの解放** ] ボタンを使用できます。</span><span class="sxs-lookup"><span data-stu-id="af145-447">Permission enabled: The **Release message** button is available.</span></span>
  - <span data-ttu-id="af145-448">アクセス許可が無効: [ **メッセージの解放** ] ボタンは使用できません。</span><span class="sxs-lookup"><span data-stu-id="af145-448">Permission disabled: The **Release message** button is not available.</span></span>
  
- <span data-ttu-id="af145-449">**エンドユーザーのスパム通知**:</span><span class="sxs-lookup"><span data-stu-id="af145-449">**End-user spam notifications**:</span></span>
  - <span data-ttu-id="af145-450">アクセス許可: [ **リリース** ] ボタンを使用できます。</span><span class="sxs-lookup"><span data-stu-id="af145-450">Permission enabled: The **Release** button is available.</span></span>
  - <span data-ttu-id="af145-451">アクセス許可が無効: **リリース** ボタンは使用できません。</span><span class="sxs-lookup"><span data-stu-id="af145-451">Permission disabled: The **Release** button is not available.</span></span>

#### <a name="allow-recipients-to-request-a-message-to-be-released-from-quarantine-permission"></a><span data-ttu-id="af145-452">受信者が、検疫アクセス許可から解放されるメッセージを要求できるようにする</span><span class="sxs-lookup"><span data-stu-id="af145-452">Allow recipients to request a message to be released from quarantine permission</span></span>

<span data-ttu-id="af145-453">[受信者に検疫 (quarantine)] アクセス許可 (_PermissionToRequestRelease_)**からメッセージを解放するよう要求する** ことで、ユーザーが検疫済みメッセージのリリースを _要求_ する機能を制御します。</span><span class="sxs-lookup"><span data-stu-id="af145-453">The **Allow recipients to request a message to be released from quarantine** permission (_PermissionToRequestRelease_) controls the ability of users to _request_ the release of their quarantined messages.</span></span> <span data-ttu-id="af145-454">このメッセージは、管理者が要求を承認した後にのみ解放されます。</span><span class="sxs-lookup"><span data-stu-id="af145-454">The message is only released after an admin approves the request.</span></span>

- <span data-ttu-id="af145-455">**検疫済みメッセージの詳細**:</span><span class="sxs-lookup"><span data-stu-id="af145-455">**Quarantined message details**:</span></span>
  - <span data-ttu-id="af145-456">アクセス許可: [ **リリースの要求** ] ボタンを使用できます。</span><span class="sxs-lookup"><span data-stu-id="af145-456">Permission enabled: The **Request release** button is available.</span></span>
  - <span data-ttu-id="af145-457">アクセス許可が無効: [ **要求のリリース** ] ボタンは使用できません。</span><span class="sxs-lookup"><span data-stu-id="af145-457">Permission disabled: The **Request release** button is not available.</span></span>

- <span data-ttu-id="af145-458">**エンドユーザーのスパム通知**: [ **リリース** ] ボタンは使用できません。</span><span class="sxs-lookup"><span data-stu-id="af145-458">**End-user spam notifications**: The **Release** button is not available.</span></span>
